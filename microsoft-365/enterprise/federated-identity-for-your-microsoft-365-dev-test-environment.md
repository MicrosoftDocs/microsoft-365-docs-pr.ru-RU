---
title: Федеративная идентификация для среды тестирования Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: 65a6d687-a16a-4415-9fd5-011ba9c5fd80
description: Сводка. Сведения о настройке федеративной аутентификации для среды тестирования Microsoft 365.
ms.openlocfilehash: 0fb8c55f5b7291cdc6bcec636981a9d31015e723
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487688"
---
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a><span data-ttu-id="569f8-103">Федеративная идентификация для среды тестирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="569f8-103">Federated identity for your Microsoft 365 test environment</span></span>

<span data-ttu-id="569f8-104">*Это руководство по лаборатории тестирования можно использовать как для Microsoft 365 Enterprise, так и для корпоративных тестовых сред Office 365.*</span><span class="sxs-lookup"><span data-stu-id="569f8-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="569f8-p101">Microsoft 365 поддерживает федеративную идентификацию. Это означает, что Microsoft 365 не проверяет непосредственно учетные данные, а направляет подключающегося пользователя на сервер федеративной проверки подлинности, которому доверяет Microsoft 365. Если учетные данные пользователя правильны, сервер федеративной проверки подлинности выдает маркер безопасности, который клиент затем отправляет в Microsoft 365 как подтверждение проверки подлинности. Федеративная идентификация позволяет разгрузить и масштабировать проверку подлинности для подписки Microsoft 365, а также реализовать расширенные сценарии проверки подлинности и безопасности.</span><span class="sxs-lookup"><span data-stu-id="569f8-p101">Microsoft 365 supports federated identity. This means that instead of performing the validation of credentials itself, Microsoft 365 refers the connecting user to a federated authentication server that Microsoft 365 trusts. If the user's credentials are correct, the federated authentication server issues a security token that the client then sends to Microsoft 365 as proof of authentication. Federated identity allows for the offloading and scaling up of authentication for a Microsoft 365 subscription and advanced authentication and security scenarios.</span></span>
  
<span data-ttu-id="569f8-109">В этой статье описывается настройка федеративной проверки подлинности для тестовой среды Microsoft 365, в результате чего выполняется следующее:</span><span class="sxs-lookup"><span data-stu-id="569f8-109">This article describes how to configure federated authentication for your Microsoft 365 test environment, resulting in the following:</span></span>

![Федеративная аутентификация для среды тестирования Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
<span data-ttu-id="569f8-111">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="569f8-111">This configuration consists of:</span></span>
  
- <span data-ttu-id="569f8-112">Пробную или производственную подписку Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="569f8-112">A Microsoft 365 E5 trial or production subscription.</span></span>
    
- <span data-ttu-id="569f8-113">Упрощенная интрасеть Организации, подключенная к Интернету и состоящая из пяти виртуальных машин в подсети виртуальной сети Azure (DC1, APP1, CLIENT1, ADFS1 и PROXY1).</span><span class="sxs-lookup"><span data-stu-id="569f8-113">A simplified organization intranet connected to the internet, consisting of five virtual machines on a subnet of an Azure virtual network (DC1, APP1, CLIENT1, ADFS1, and PROXY1).</span></span> <span data-ttu-id="569f8-114">Azure AD Connect работает на APP1 для синхронизации списка учетных записей в домене доменных служб Active Directory с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="569f8-114">Azure AD Connect runs on APP1 to synchronize the list of accounts in the Active Directory Domain Services domain to Microsoft 365.</span></span> <span data-ttu-id="569f8-115">PROXY1 получает входящие запросы аутентификации.</span><span class="sxs-lookup"><span data-stu-id="569f8-115">PROXY1 receives the incoming authentication requests.</span></span> <span data-ttu-id="569f8-116">ADFS1 проверяет учетные данные с помощью DC1 и выдает маркеры безопасности.</span><span class="sxs-lookup"><span data-stu-id="569f8-116">ADFS1 validates credentials with DC1 and issues security tokens.</span></span>
    
<span data-ttu-id="569f8-117">Настройка этой тестовой среды состоит из пяти этапов:</span><span class="sxs-lookup"><span data-stu-id="569f8-117">Setting up this test environment involves five phases:</span></span>
- [<span data-ttu-id="569f8-118">Этап 1. Настройка синхронизации хэша паролей для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="569f8-118">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="569f8-119">Этап 2. Создание сервера AD FS</span><span class="sxs-lookup"><span data-stu-id="569f8-119">Phase 2: Create the AD FS server</span></span>](#phase-2-create-the-ad-fs-server)
- [<span data-ttu-id="569f8-120">Этап 3. Создание веб-прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="569f8-120">Phase 3: Create the web proxy server</span></span>](#phase-3-create-the-web-proxy-server)
- [<span data-ttu-id="569f8-121">Этап 4. Создание самозаверяющего сертификата и настройка ADFS1 и PROXY1</span><span class="sxs-lookup"><span data-stu-id="569f8-121">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>](#phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1)
- [<span data-ttu-id="569f8-122">Этап 5. Настройка федеративной идентификации для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="569f8-122">Phase 5: Configure Microsoft 365 for federated identity</span></span>](#phase-5-configure-microsoft-365-for-federated-identity)
    
> [!NOTE]
> <span data-ttu-id="569f8-123">Вы не можете настроить эту тестовую среду с помощью пробной подписки на Azure.</span><span class="sxs-lookup"><span data-stu-id="569f8-123">You can't configure this test environment with an Azure Trial subscription.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="569f8-124">Этап 1. Настройка синхронизации хэша паролей для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="569f8-124">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="569f8-125">Следуйте инструкциям в статье [Синхронизация хэша паролей для Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="569f8-125">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="569f8-126">Результирующая конфигурация выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="569f8-126">Your resulting configuration looks like this:</span></span>
  
![Тестовая среда смоделированной организации с синхронизацией хэша паролей](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase1.png)
  
<span data-ttu-id="569f8-128">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="569f8-128">This configuration consists of:</span></span>
  
- <span data-ttu-id="569f8-129">Пробная или платная подписка Microsoft 365, или платная подписка.</span><span class="sxs-lookup"><span data-stu-id="569f8-129">A Microsoft 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="569f8-130">Упрощенная интрасеть Организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети виртуальной сети Azure.</span><span class="sxs-lookup"><span data-stu-id="569f8-130">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="569f8-131">Azure AD Connect работает на APP1 для периодической синхронизации домена доменных служб Active Directory TESTLAB (AD DS) с клиентом Azure AD ваших подписок Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="569f8-131">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscriptions periodically.</span></span>

## <a name="phase-2-create-the-ad-fs-server"></a><span data-ttu-id="569f8-132">Этап 2. Создание сервера AD FS</span><span class="sxs-lookup"><span data-stu-id="569f8-132">Phase 2: Create the AD FS server</span></span>

<span data-ttu-id="569f8-133">Сервер AD FS обеспечивает федеративную аутентификацию между Microsoft 365 и учетными записями в домене corp.contoso.com, размещенном на DC1.</span><span class="sxs-lookup"><span data-stu-id="569f8-133">An AD FS server provides federated authentication between Microsoft 365 and the accounts in the corp.contoso.com domain hosted on DC1.</span></span>
  
<span data-ttu-id="569f8-134">Чтобы создать виртуальную машину Azure для ADFS1, укажите имя своей подписки, группы ресурсов и расположение Azure для базовой конфигурации, а затем выполните указанные ниже команды в командной строке Azure PowerShell на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="569f8-134">To create an Azure virtual machine for ADFS1, fill in the name of your subscription and the resource group and Azure location for your Base Configuration, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$subscrName="<your Azure subscription name>"
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
Connect-AzAccount
Select-AzSubscription -SubscriptionName $subscrName
$staticIP="10.0.0.100"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name ADFS1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic = New-AzNetworkInterface -Name ADFS1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName ADFS1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for ADFS1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName ADFS1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "ADFS-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="569f8-135">После этого на [портале Azure](https://portal.azure.com) подключитесь к виртуальной машине ADFS1, используя имя и пароль учетной записи локального администратора ADFS1. Затем откройте командную строку Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="569f8-135">Next, use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the ADFS1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="569f8-136">Чтобы проверить разрешение имен и сетевое подключение между ADFS1 и DC1, выполните команду **ping dc1.corp.contoso.com** и убедитесь, что поступило четыре ответа.</span><span class="sxs-lookup"><span data-stu-id="569f8-136">To check name resolution and network communication between ADFS1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="569f8-137">Далее присоедините виртуальную машину ADFS1 к домену CORP, выполнив указанные ниже команды в командной строке Windows PowerShell на ADFS1.</span><span class="sxs-lookup"><span data-stu-id="569f8-137">Next, join the ADFS1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on ADFS1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="569f8-138">Результирующая конфигурация выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="569f8-138">Your resulting configuration looks like this:</span></span>
  
![Сервер AD FS добавлен в DirSync для среды тестирования Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase2.png)
  
## <a name="phase-3-create-the-web-proxy-server"></a><span data-ttu-id="569f8-140">Этап 3. Создание веб-прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="569f8-140">Phase 3: Create the web proxy server</span></span>

<span data-ttu-id="569f8-141">PROXY1 обеспечивает передачу сообщений аутентификации через прокси-соединения между подключающимися пользователями и ADFS1.</span><span class="sxs-lookup"><span data-stu-id="569f8-141">PROXY1 provides proxying of authentication messages between users trying to authenticate and ADFS1.</span></span>
  
<span data-ttu-id="569f8-142">Чтобы создать виртуальную машину Azure для PROXY1, укажите имя группы ресурсов, расположение Azure, а затем выполните указанные ниже команды в командной строке Azure PowerShell на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="569f8-142">To create an Azure virtual machine for PROXY1, fill in the name of your resource group and Azure location, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
$staticIP="10.0.0.101"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name PROXY1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Static
$nic = New-AzNetworkInterface -Name PROXY1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName PROXY1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for PROXY1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName PROXY1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "PROXY1-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> <span data-ttu-id="569f8-143">Машине PROXY1 присваивается статический общедоступный IP-адрес, который не должен меняться при перезапуске виртуальной машины PROXY1, так как на него указывает созданная вами общедоступная запись DNS.</span><span class="sxs-lookup"><span data-stu-id="569f8-143">PROXY1 is assigned a static public IP address because you will create a public DNS record that points to it and it must not change when you restart the PROXY1 virtual machine.</span></span>
  
<span data-ttu-id="569f8-144">Затем добавьте правило в группу безопасности сети для подсети корпоративной сети, чтобы разрешить незапрошенный входящий трафик из Интернета в PROXY1's частный IP-адрес и TCP-порт 443.</span><span class="sxs-lookup"><span data-stu-id="569f8-144">Next, add a rule to the network security group for the CorpNet subnet to allow unsolicited inbound traffic from the internet to PROXY1's private IP address and TCP port 443.</span></span> <span data-ttu-id="569f8-145">Выполните эти команды в командной строке Azure PowerShell на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="569f8-145">Run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
Get-AzNetworkSecurityGroup -Name CorpNet -ResourceGroupName $rgName | Add-AzNetworkSecurityRuleConfig -Name "HTTPS-to-PROXY1" -Description "Allow TCP 443 to PROXY1" -Access "Allow" -Protocol "Tcp" -Direction "Inbound" -Priority 101 -SourceAddressPrefix "Internet" -SourcePortRange "*" -DestinationAddressPrefix "10.0.0.101" -DestinationPortRange "443" | Set-AzNetworkSecurityGroup
```

<span data-ttu-id="569f8-146">После этого подключитесь к виртуальной машине PROXY1 на [портале Azure](https://portal.azure.com), используя имя и пароль учетной записи локального администратора PROXY1. Затем откройте командную строку Windows PowerShell на PROXY1.</span><span class="sxs-lookup"><span data-stu-id="569f8-146">Next, use the [Azure portal](https://portal.azure.com) to connect to the PROXY1 virtual machine using the PROXY1 local administrator account name and password, and then open a Windows PowerShell command prompt on PROXY1.</span></span>
  
<span data-ttu-id="569f8-147">Чтобы проверить разрешение имен и сетевое подключение между PROXY1 и DC1, выполните команду **ping dc1.corp.contoso.com** и убедитесь, что поступило четыре ответа.</span><span class="sxs-lookup"><span data-stu-id="569f8-147">To check name resolution and network communication between PROXY1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="569f8-148">Далее присоедините виртуальную машину PROXY1 к домену CORP, выполнив указанные ниже команды в командной строке Windows PowerShell на PROXY1.</span><span class="sxs-lookup"><span data-stu-id="569f8-148">Next, join the PROXY1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on PROXY1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="569f8-149">Отобразите общедоступный IP-адрес PROXY1 с помощью этих команд Azure PowerShell на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="569f8-149">Display the public IP address of PROXY1 with these Azure PowerShell commands on your local computer.</span></span>
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

<span data-ttu-id="569f8-p106">После этого обратитесь к своему поставщику общедоступных DNS и создайте запись A для имени **fs.testlab.**\<*your DNS domain name*>, которая разрешается в IP-адрес, отображаемый командой **Write-Host**. Имя **fs.testlab.**\<*your DNS domain name*> далее именуется *FQDN службы федерации*.</span><span class="sxs-lookup"><span data-stu-id="569f8-p106">Next, work with your public DNS provider and create a new public DNS A record for **fs.testlab.**\<*your DNS domain name*> that resolves to the IP address displayed by the **Write-Host** command. The **fs.testlab.**\<*your DNS domain name*> is hereafter referred to as the  *federation service FQDN*.</span></span>
  
<span data-ttu-id="569f8-154">После этого воспользуйтесь учетными данными CORP\\User1 на [портале Azure](https://portal.azure.com), чтобы подключиться к виртуальной машине DC1, а затем выполните следующие команды в командной строке Windows PowerShell, открытой от имени администратора:</span><span class="sxs-lookup"><span data-stu-id="569f8-154">Next, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then run the following commands at an administrator-level Windows PowerShell command prompt:</span></span>
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
<span data-ttu-id="569f8-155">Эти команды создают внутреннюю DNS-запись A, чтобы виртуальные машины в виртуальной сети Azure могли разрешить полное доменное имя службы федерации в частный IP-адрес ADFS1's.</span><span class="sxs-lookup"><span data-stu-id="569f8-155">These commands create an internal DNS A record so that virtual machines on the Azure virtual network can resolve the internal federation service FQDN to ADFS1's private IP address.</span></span>
  
<span data-ttu-id="569f8-156">Результирующая конфигурация выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="569f8-156">Your resulting configuration looks like this:</span></span>
  
![Прокси-сервер веб-приложений добавлен в DirSync для среды тестирования Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a><span data-ttu-id="569f8-158">Этап 4. Создание самозаверяющего сертификата и настройка ADFS1 и PROXY1</span><span class="sxs-lookup"><span data-stu-id="569f8-158">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>

<span data-ttu-id="569f8-159">На этом этапе создается самозаверяющий цифровой сертификат для полного доменного имени службы федерации и настраиваются ADFS1 и PROXY1 как ферма AD FS.</span><span class="sxs-lookup"><span data-stu-id="569f8-159">In this phase, you create a self-signed digital certificate for your federation service FQDN and configure ADFS1 and PROXY1 as an AD FS farm.</span></span>
  
<span data-ttu-id="569f8-160">Сначала подключитесь к виртуальной машине DC1 на [портале Azure](https://portal.azure.com), используя учетные данные CORP\\User1, а затем откройте командную строку Windows PowerShell от имени администратора. </span><span class="sxs-lookup"><span data-stu-id="569f8-160">First, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="569f8-161">Затем создайте учетную запись службы AD FS с помощью этой команды в командной строке Windows PowerShell на контроллере DC1:</span><span class="sxs-lookup"><span data-stu-id="569f8-161">Next, create an AD FS service account with this command at the Windows PowerShell command prompt on DC1:</span></span>
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
<span data-ttu-id="569f8-162">Обратите внимание, что при выполнении этой команды вам будет предложено ввести пароль учетной записи.</span><span class="sxs-lookup"><span data-stu-id="569f8-162">Note that this command prompts you to supply the account password.</span></span> <span data-ttu-id="569f8-163">Выберите надежный пароль и запишите его в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="569f8-163">Choose a strong password and record it in a secured location.</span></span> <span data-ttu-id="569f8-164">Он потребуется для этого этапа и для этапа 5.</span><span class="sxs-lookup"><span data-stu-id="569f8-164">You will need it for this phase and for Phase 5.</span></span>
  
<span data-ttu-id="569f8-p108">Подключитесь к виртуальной машине ADFS1 на [портале Azure](https://portal.azure.com), используя учетные данные CORP\\User1. Откройте командную строку Windows PowerShell на ADFS1 от имени администратора, введите FQDN службы федерации и выполните следующие команды для создания самозаверяющего сертификата:</span><span class="sxs-lookup"><span data-stu-id="569f8-p108">Use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the CORP\\User1 credentials. Open an administrator-level Windows PowerShell command prompt on ADFS1, fill in your federation service FQDN, and then run these commands to create a self-signed certificate:</span></span>
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

<span data-ttu-id="569f8-167">После этого выполните указанные ниже действия, чтобы сохранить новый самозаверяющий сертификат в виде файла.</span><span class="sxs-lookup"><span data-stu-id="569f8-167">Next, use these steps to save the new self-signed certificate as a file.</span></span>
  
1. <span data-ttu-id="569f8-168">Нажмите кнопку **Пуск**, введите **mmc.exe**, а затем нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="569f8-168">Select **Start**, enter **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="569f8-169">Выберите **команду**  >  **Добавить или удалить оснастку**.</span><span class="sxs-lookup"><span data-stu-id="569f8-169">Select **File** > **Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="569f8-170">В разделе **Добавление и удаление оснасток**дважды щелкните пункт **Сертификаты** в списке доступных оснасток, выберите пункт **учетная запись компьютера**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="569f8-170">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="569f8-171">В списке **выберите компьютер**нажмите кнопку **Готово**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="569f8-171">In **Select Computer**, select **Finish**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="569f8-172">В области дерева выберите **Сертификаты (локальный компьютер) > Личное > Сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="569f8-172">In the tree pane, open **Certificates (Local Computer) > Personal > Certificates**.</span></span>
    
6. <span data-ttu-id="569f8-173">Выберите и удерживайте (или щелкните правой кнопкой мыши) сертификат с полным доменным именем службы федерации, выберите **все задачи**, а затем выберите **Экспорт**.</span><span class="sxs-lookup"><span data-stu-id="569f8-173">Select and hold (or right-click) the certificate with your federation service FQDN, select **All tasks**, and then select **Export**.</span></span>
    
7. <span data-ttu-id="569f8-174">На странице **приветствия** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="569f8-174">On the **Welcome** page, select **Next**.</span></span>
    
8. <span data-ttu-id="569f8-175">На странице " **Экспорт закрытого ключа** **" выберите Да**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="569f8-175">On the **Export Private Key** page, select **Yes**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="569f8-176">На странице **Формат экспортируемого файла** выберите **экспортировать все расширенные свойства**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="569f8-176">On the **Export File Format** page, select **Export all extended properties**, and then select **Next**.</span></span>
    
10. <span data-ttu-id="569f8-177">На странице " **Безопасность** " выберите **пароль** и введите пароль в поле **пароль** и **Подтвердите пароль.**</span><span class="sxs-lookup"><span data-stu-id="569f8-177">On the **Security** page, select **Password** and enter a password in **Password** and **Confirm password.**</span></span>
    
11. <span data-ttu-id="569f8-178">На странице " **файл для экспорта** " нажмите кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="569f8-178">On the **File to Export** page, select **Browse**.</span></span>
    
12. <span data-ttu-id="569f8-179">Перейдите в папку \*\* \\ Сертификаты C:\*\* , введите **SSL** в поле **имя файла**, а затем нажмите кнопку **Сохранить.**</span><span class="sxs-lookup"><span data-stu-id="569f8-179">Browse to the **C:\\Certs** folder, enter **SSL** in **File name**, and then select **Save.**</span></span>
    
13. <span data-ttu-id="569f8-180">На странице " **файл для экспорта** " нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="569f8-180">On the **File to Export** page, select **Next**.</span></span>
    
14. <span data-ttu-id="569f8-181">На странице **Завершение работы мастера экспорта сертификатов** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="569f8-181">On the **Completing the Certificate Export Wizard** page, select **Finish**.</span></span> <span data-ttu-id="569f8-182">При появлении соответствующего запроса нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="569f8-182">When prompted, select **OK**.</span></span>
    
<span data-ttu-id="569f8-183">После этого установите службу AD FS, выполнив следующую команду в командной строке Windows PowerShell на ADFS1:</span><span class="sxs-lookup"><span data-stu-id="569f8-183">Next, install the AD FS service with this command at the Windows PowerShell command prompt on ADFS1:</span></span>
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

<span data-ttu-id="569f8-184">Дождитесь завершения установки.</span><span class="sxs-lookup"><span data-stu-id="569f8-184">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="569f8-185">После этого выполните указанные ниже действия, чтобы настроить службу AD FS.</span><span class="sxs-lookup"><span data-stu-id="569f8-185">Next, configure the AD FS service with these steps:</span></span>
  
1. <span data-ttu-id="569f8-186">Нажмите кнопку **Пуск**и выберите значок **Диспетчер серверов** .</span><span class="sxs-lookup"><span data-stu-id="569f8-186">Select **Start**, and then select the **Server Manager** icon.</span></span>
    
2. <span data-ttu-id="569f8-187">В области дерева диспетчера серверов выберите **AD FS**.</span><span class="sxs-lookup"><span data-stu-id="569f8-187">In the tree pane of Server Manager, select **AD FS**.</span></span>
    
3. <span data-ttu-id="569f8-188">На панели инструментов вверху нажмите оранжевый символ предупреждения, а затем выберите **настроить службу федерации на этом сервере**.</span><span class="sxs-lookup"><span data-stu-id="569f8-188">In the tool bar at the top, select the orange caution symbol, and then select **Configure the federation service on this server**.</span></span>
    
4. <span data-ttu-id="569f8-189">На странице **Добро пожаловать** в мастере настройки служб федерации Active Directory нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="569f8-189">On the **Welcome** page of the Active Directory Federation Services Configuration Wizard, select **Next**.</span></span>
    
5. <span data-ttu-id="569f8-190">На странице **Подключение к AD DS** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="569f8-190">On the **Connect to AD DS** page, select **Next**.</span></span>
    
6. <span data-ttu-id="569f8-191">На странице **Настройка свойств службы**:</span><span class="sxs-lookup"><span data-stu-id="569f8-191">On the **Specify Service Properties** page:</span></span>
    
  - <span data-ttu-id="569f8-192">Чтобы получить **SSL-сертификат**, нажмите стрелку вниз, а затем выберите сертификат с именем FQDN службы федерации.</span><span class="sxs-lookup"><span data-stu-id="569f8-192">For **SSL Certificate**, select the down arrow, and then select the certificate with the name of your federation service FQDN.</span></span>
    
  - <span data-ttu-id="569f8-193">В поле **Отображаемое имя службы федерации**введите имя вымышленной организации.</span><span class="sxs-lookup"><span data-stu-id="569f8-193">In **Federation Service Display Name**, enter the name of your fictional organization.</span></span>
    
  - <span data-ttu-id="569f8-194">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="569f8-194">Select **Next**.</span></span>
    
7. <span data-ttu-id="569f8-195">На странице **Указание учетной записи службы** выберите **пункт выбрать** для **учетной**записи.</span><span class="sxs-lookup"><span data-stu-id="569f8-195">On the **Specify Service Account** page, select **Select** for **Account name**.</span></span>
    
8. <span data-ttu-id="569f8-196">В поле **выберите пользователя или учетную запись службы**введите **ADFS — служба**, выберите **Проверить имена**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="569f8-196">In **Select User or Service Account**, enter **ADFS-Service**, select **Check Names**, and then select **OK**.</span></span>
    
9. <span data-ttu-id="569f8-197">В поле **пароль учетной записи**введите пароль для учетной записи ADFS-Service, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="569f8-197">In **Account Password**, enter the password for the ADFS-Service account, and then select **Next**.</span></span>
    
10. <span data-ttu-id="569f8-198">На странице **Выбор базы данных конфигурации** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="569f8-198">On the **Specify Configuration Database** page, select **Next**.</span></span>
    
11. <span data-ttu-id="569f8-199">На странице " **Параметры проверки** " нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="569f8-199">On the **Review Options** page, select **Next**.</span></span>
    
12. <span data-ttu-id="569f8-200">На странице **Проверка предварительных требований** выберите пункт **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="569f8-200">On the **Pre-requisite Checks** page, select **Configure**.</span></span>

13. <span data-ttu-id="569f8-201">На странице **результаты** нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="569f8-201">On the **Results** page, select **Close**.</span></span>
    
14. <span data-ttu-id="569f8-202">Нажмите кнопку **Пуск**, выберите значок Power, выберите **перезапустить**, а затем нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="569f8-202">Select **Start**, select the power icon, select **Restart**, and then select **Continue**.</span></span>
    
<span data-ttu-id="569f8-203">Откройте [портал Azure](https://portal.azure.com) и подключитесь к PROXY1, используя учетные данные CORP\\User1.</span><span class="sxs-lookup"><span data-stu-id="569f8-203">From the [Azure portal](https://portal.azure.com), connect to PROXY1 with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="569f8-204">После этого выполните указанные ниже действия, чтобы установить самозаверяющий сертификат на **PROXY1 и APP1**.</span><span class="sxs-lookup"><span data-stu-id="569f8-204">Next, use these steps to install the self-signed certificate on **both PROXY1 and APP1**.</span></span>
  
1. <span data-ttu-id="569f8-205">Нажмите кнопку **Пуск**, введите **mmc.exe**, а затем нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="569f8-205">Select **Start**, enter **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="569f8-206">Выберите **файл > добавить или удалить оснастку**.</span><span class="sxs-lookup"><span data-stu-id="569f8-206">Select **File > Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="569f8-207">В разделе **Добавление и удаление оснасток**дважды щелкните пункт **Сертификаты** в списке доступных оснасток, выберите пункт **учетная запись компьютера**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="569f8-207">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="569f8-208">В списке **выберите компьютер**нажмите кнопку **Готово**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="569f8-208">In **Select Computer**, select **Finish**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="569f8-209">В области дерева откройте узел личные **Сертификаты (локальный компьютер)**  >  **Personal**  >  **Certificates**.</span><span class="sxs-lookup"><span data-stu-id="569f8-209">In the tree pane, open **Certificates (Local Computer)** > **Personal** > **Certificates**.</span></span>
    
6. <span data-ttu-id="569f8-210">Выберите и удерживайте (или щелкните правой кнопкой мыши) **персональный**, выберите **все задачи**, а затем нажмите кнопку **Импорт**.</span><span class="sxs-lookup"><span data-stu-id="569f8-210">Select and hold (or right-click) **Personal**, select **All tasks**, and then select **Import**.</span></span>
    
7. <span data-ttu-id="569f8-211">На странице **приветствия** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="569f8-211">On the **Welcome** page, select **Next**.</span></span>
    
8. <span data-ttu-id="569f8-212">На странице **импортируемый файл** введите \*\* \\ \\ adfs1 \\ Сертификаты \\ SSL. pfx\*\*, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="569f8-212">On the **File to Import** page, enter **\\\\adfs1\\certs\\ssl.pfx**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="569f8-213">На странице **защита закрытого ключа** введите пароль сертификата в поле **пароль**, а затем нажмите кнопку **Далее.**</span><span class="sxs-lookup"><span data-stu-id="569f8-213">On the **Private key protection** page, enter the certificate password in **Password**, and then select **Next.**</span></span>
    
10. <span data-ttu-id="569f8-214">На странице **хранилище сертификатов** нажмите кнопку **Далее.**</span><span class="sxs-lookup"><span data-stu-id="569f8-214">On the **Certificate store** page, select **Next.**</span></span>
    
11. <span data-ttu-id="569f8-215">На странице **Завершение** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="569f8-215">On the **Completing** page, select **Finish**.</span></span>
    
12. <span data-ttu-id="569f8-216">На странице **хранилище сертификатов** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="569f8-216">On the **Certificate Store** page, select **Next**.</span></span>
    
13. <span data-ttu-id="569f8-217">При появлении соответствующего запроса нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="569f8-217">When prompted, select **OK**.</span></span>
    
14. <span data-ttu-id="569f8-218">В области дерева выберите **Сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="569f8-218">In the tree pane, select **Certificates**.</span></span>
    
15. <span data-ttu-id="569f8-219">Нажмите и удерживайте (или щелкните правой кнопкой мыши) сертификат, а затем выберите пункт **Копировать**.</span><span class="sxs-lookup"><span data-stu-id="569f8-219">Select and hold (or right-click) the certificate, and then select **Copy**.</span></span>
    
16. <span data-ttu-id="569f8-220">В области дерева откройте Сертификаты **доверенных корневых центров сертификации**  >  **Certificates**.</span><span class="sxs-lookup"><span data-stu-id="569f8-220">In the tree pane, open **Trusted Root Certification Authorities** > **Certificates**.</span></span>
    
17. <span data-ttu-id="569f8-221">Переместите указатель мыши под списком установленных сертификатов, нажмите и удерживайте (или щелкните правой кнопкой мыши), а затем выберите команду **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="569f8-221">Move your mouse pointer below the list of installed certificates, select and hold (or right-click), and then select **Paste**.</span></span>
    
<span data-ttu-id="569f8-222">Откройте командную строку администратора PowerShell и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="569f8-222">Open an administrator-level PowerShell command prompt and run the following command:</span></span>
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

<span data-ttu-id="569f8-223">Дождитесь завершения установки.</span><span class="sxs-lookup"><span data-stu-id="569f8-223">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="569f8-224">Сделайте так, чтобы прокси-служба веб-приложения использовала ADFS1 в качестве сервера федерации:</span><span class="sxs-lookup"><span data-stu-id="569f8-224">Use these steps to configure the web application proxy service to use ADFS1 as its federation server:</span></span>
  
1. <span data-ttu-id="569f8-225">Нажмите кнопку **Пуск**и выберите пункт **Диспетчер серверов**.</span><span class="sxs-lookup"><span data-stu-id="569f8-225">Select **Start**, and then select **Server Manager**.</span></span>
    
2. <span data-ttu-id="569f8-226">В области дерева выберите **Удаленный доступ**.</span><span class="sxs-lookup"><span data-stu-id="569f8-226">In the tree pane, select **Remote Access**.</span></span>
    
3. <span data-ttu-id="569f8-227">На панели инструментов вверху нажмите оранжевый символ предупреждения, а затем выберите пункт **открыть мастер прокси-сервера веб-приложений**.</span><span class="sxs-lookup"><span data-stu-id="569f8-227">In the tool bar at the top, select the orange caution symbol, and then select **Open the Web Application Proxy Wizard**.</span></span>
    
4. <span data-ttu-id="569f8-228">На странице **приветствия** мастера настройки прокси-сервера веб-приложений нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="569f8-228">On the **Welcome** page of the Web Application Proxy Configuration Wizard, select **Next**.</span></span>
    
5. <span data-ttu-id="569f8-229">На странице **Сервер федерации**:</span><span class="sxs-lookup"><span data-stu-id="569f8-229">On the **Federation Server** page:</span></span>
    
  - <span data-ttu-id="569f8-230">В поле **имя службы федерации** введите полное доменное имя службы федерации.</span><span class="sxs-lookup"><span data-stu-id="569f8-230">In the **Federation service name** box, enter your federation service FQDN.</span></span>
    
  - <span data-ttu-id="569f8-231">В поле **имя пользователя** введите **Corp \\ User1**.</span><span class="sxs-lookup"><span data-stu-id="569f8-231">In the **User name** box, enter **CORP\\User1**.</span></span>
    
  - <span data-ttu-id="569f8-232">В поле **пароль** введите пароль для учетной записи User1.</span><span class="sxs-lookup"><span data-stu-id="569f8-232">In the **Password** box, enter the password for the User1 account.</span></span>
    
  - <span data-ttu-id="569f8-233">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="569f8-233">Select **Next**.</span></span>
    
6. <span data-ttu-id="569f8-234">На странице **сертификат прокси-сервера AD FS** щелкните стрелку вниз, выберите сертификат с полным доменным именем службы федерации, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="569f8-234">On the **AD FS Proxy Certificate** page, select the down arrow, select the certificate with your federation service FQDN, and then select **Next**.</span></span>
    
7. <span data-ttu-id="569f8-235">На странице **Подтверждение** нажмите кнопку **настроить**.</span><span class="sxs-lookup"><span data-stu-id="569f8-235">On the **Confirmation** page, select **Configure**.</span></span>
    
8. <span data-ttu-id="569f8-236">На странице **результаты** нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="569f8-236">On the **Results** page, select **Close**.</span></span>
    
## <a name="phase-5-configure-microsoft-365-for-federated-identity"></a><span data-ttu-id="569f8-237">Этап 5. Настройка федеративной идентификации для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="569f8-237">Phase 5: Configure Microsoft 365 for federated identity</span></span>

<span data-ttu-id="569f8-238">Используйте учетные данные CORP\\User1 на [портале Azure](https://portal.azure.com), чтобы подключиться к виртуальной машине APP1.</span><span class="sxs-lookup"><span data-stu-id="569f8-238">Use the [Azure portal](https://portal.azure.com) to connect to the APP1 virtual machine with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="569f8-239">Выполните следующие действия, чтобы настроить федеративную проверку подлинности для Azure AD Connect и подписки Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="569f8-239">Use these steps to configure Azure AD Connect and your Microsoft 365 subscription for federated authentication:</span></span>
  
1. <span data-ttu-id="569f8-240">На рабочем столе дважды щелкните значок **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="569f8-240">From the desktop, double-click **Azure AD Connect**.</span></span>
    
2. <span data-ttu-id="569f8-241">На странице **Добро пожаловать в Azure AD Connect** нажмите кнопку **настроить**.</span><span class="sxs-lookup"><span data-stu-id="569f8-241">On the **Welcome to Azure AD Connect** page, select **Configure**.</span></span>
    
3. <span data-ttu-id="569f8-242">На странице **Дополнительные задачи** выберите **изменить вход пользователя**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="569f8-242">On the **Additional tasks** page, select **Change user sign-in**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="569f8-243">На странице **Подключение к Azure AD** введите имя и пароль учетной записи глобального администратора, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="569f8-243">On the **Connect to Azure AD** page, enter your global administrator account name and password, and then select **Next**.</span></span>
    
5. <span data-ttu-id="569f8-244">На странице **Вход пользователя** выберите **Федерация с AD FS**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="569f8-244">On the **User sign-in** page, select **Federation with AD FS**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="569f8-245">На странице **ферма AD FS** выберите **использовать СУЩЕСТВУЮЩУЮ ферму AD FS**, введите **ADFS1** в поле **имя сервера** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="569f8-245">On the **AD FS farm** page, select **Use an existing AD FS farm**, enter **ADFS1** in the **Server Name** box, and then select **Next**.</span></span>
    
7. <span data-ttu-id="569f8-246">При запросе учетных данных сервера введите учетные данные для \\ учетной записи "Corp user1" и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="569f8-246">When prompted for server credentials, enter the credentials of the CORP\\User1 account, and then select **OK**.</span></span>
    
8. <span data-ttu-id="569f8-247">На странице "учетные данные **администратора домена** " введите **Corp \\ User1** в поле **имя пользователя** , введите пароль учетной записи в поле **пароль** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="569f8-247">On the **Domain Administrator** credentials page, enter **CORP\\User1** in the **Username** box, enter the account password in the **Password** box, and then select **Next**.</span></span>
    
9. <span data-ttu-id="569f8-248">На странице **учетная запись службы AD FS** в поле **имя пользователя домена** введите пароль учетной записи в поле **пароль пользователя домена** , а затем нажмите кнопку **Далее**. \*\* \\ \*\*</span><span class="sxs-lookup"><span data-stu-id="569f8-248">On the **AD FS service account** page, enter **CORP\\ADFS-Service** in the **Domain Username** box, enter the account password in the **Domain User Password** box, and then select **Next**.</span></span>
    
10. <span data-ttu-id="569f8-249">На странице **домен Azure AD** в разделе **Domain (домен**) выберите имя домена, созданного ранее и добавленного в подписку на этапе 1, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="569f8-249">On the **Azure AD Domain** page, in **Domain**, select the name of the domain that you previously created and added to your subscription in Phase 1, and then select **Next**.</span></span>
    
11. <span data-ttu-id="569f8-250">На странице **Готово к настройке** нажмите кнопку **настроить**.</span><span class="sxs-lookup"><span data-stu-id="569f8-250">On the **Ready to configure** page, select **Configure**.</span></span>
    
12. <span data-ttu-id="569f8-251">На странице **Установка завершена** нажмите кнопку **проверить**.</span><span class="sxs-lookup"><span data-stu-id="569f8-251">On the **Installation complete** page, select **Verify**.</span></span>
    
    <span data-ttu-id="569f8-252">Должны появиться сообщения о том, что были проверены параметры интрасети и Интернета.</span><span class="sxs-lookup"><span data-stu-id="569f8-252">You should see messages indicating that both the intranet and internet configuration was verified.</span></span>
    
13. <span data-ttu-id="569f8-253">На странице **Установка завершена** нажмите кнопку **выход**.</span><span class="sxs-lookup"><span data-stu-id="569f8-253">On the **Installation complete** page, select **Exit**.</span></span>
    
<span data-ttu-id="569f8-254">Действия для демонстрации работы федеративной аутентификации:</span><span class="sxs-lookup"><span data-stu-id="569f8-254">To demonstrate that federated authentication is working:</span></span>
  
1. <span data-ttu-id="569f8-255">Откройте новый частный экземпляр браузера на локальном компьютере и перейдите по адресу [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="569f8-255">Open a new private instance of your browser on your local computer and go to [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="569f8-256">Введите user1@ для учетных данных для входа **user1@** \<*the domain created in Phase 1*> .</span><span class="sxs-lookup"><span data-stu-id="569f8-256">For the sign-in credentials, enter **user1@**\<*the domain created in Phase 1*>.</span></span>
    
    <span data-ttu-id="569f8-257">Например, если тестовый домен — **testlab.contoso.com**, введите "user1@testlab.contoso.com".</span><span class="sxs-lookup"><span data-stu-id="569f8-257">For example, if your test domain is **testlab.contoso.com**, you would enter "user1@testlab.contoso.com".</span></span> <span data-ttu-id="569f8-258">Нажмите клавишу **Tab** или дождитесь автоматического перенаправления Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="569f8-258">Press the **Tab** key or allow Microsoft 365 to automatically redirect you.</span></span>
    
    <span data-ttu-id="569f8-259">Теперь вы можете увидеть **ваше подключение не частная** страница.</span><span class="sxs-lookup"><span data-stu-id="569f8-259">You should now see a **Your connection is not private** page.</span></span> <span data-ttu-id="569f8-260">Вы видите его, так как вы установили самозаверяющий сертификат на ADFS1, который компьютер не может проверить.</span><span class="sxs-lookup"><span data-stu-id="569f8-260">You are seeing this because you installed a self-signed certificate on ADFS1 that your desktop computer can't validate.</span></span> <span data-ttu-id="569f8-261">В рабочем развертывании федеративной проверки подлинности можно использовать сертификат из доверенного центра сертификации, а пользователи не увидят эту страницу.</span><span class="sxs-lookup"><span data-stu-id="569f8-261">In a production deployment of federated authentication, you would use a certificate from a trusted certification authority and your users would not see this page.</span></span>
    
3. <span data-ttu-id="569f8-262">На странице **подключение не частный** , выберите **Дополнительно**, а затем нажмите кнопку \*\*Перейти \<*your federation service FQDN*> к \*\*.</span><span class="sxs-lookup"><span data-stu-id="569f8-262">On the **Your connection is not private** page, select **Advanced**, and then select **Proceed to \<*your federation service FQDN*>**.</span></span> 
    
4. <span data-ttu-id="569f8-263">На странице с именем вымышленной организации войдите с помощью следующих учетных данных:</span><span class="sxs-lookup"><span data-stu-id="569f8-263">On the page with the name of your fictional organization, sign in with the following:</span></span>
    
  - <span data-ttu-id="569f8-264">имя **CORP\\User1**;</span><span class="sxs-lookup"><span data-stu-id="569f8-264">**CORP\\User1** for the name</span></span>
    
  - <span data-ttu-id="569f8-265">пароль учетной записи User1.</span><span class="sxs-lookup"><span data-stu-id="569f8-265">The password for the User1 account</span></span>
    
    <span data-ttu-id="569f8-266">Откроется **Домашняя страница Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="569f8-266">You should see the **Microsoft Office Home** page.</span></span>
    
<span data-ttu-id="569f8-p112">Эта процедура демонстрирует, что между пробной подпиской и доменом AD DS corp.contoso.com, размещенным на DC1, настроена федеративная проверка подлинности. Вот как устроен процесс проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="569f8-p112">This procedure demonstrates that your trial subscription is federated with the AD DS corp.contoso.com domain hosted on DC1. Here are the basics of the authentication process:</span></span>
  
1. <span data-ttu-id="569f8-269">Когда вы используете федеративный домен, созданный на этапе 1, в имени учетной записи для входа, Microsoft 365 перенаправляет ваш браузер на полное доменное имя службы федерации и PROXY1.</span><span class="sxs-lookup"><span data-stu-id="569f8-269">When you use the federated domain that you created in Phase 1 within the sign-in account name, Microsoft 365 redirects your browser to your federation service FQDN and PROXY1.</span></span>
    
2. <span data-ttu-id="569f8-270">PROXY1 направляет локальный компьютер на страницу входа вымышленной организации.</span><span class="sxs-lookup"><span data-stu-id="569f8-270">PROXY1 sends your local computer the fictional company sign-in page.</span></span>
    
3. <span data-ttu-id="569f8-271">Когда вы отправляете имя CORP\\User1 и пароль на PROXY1, сервер пересылает эти данные на ADFS1.</span><span class="sxs-lookup"><span data-stu-id="569f8-271">When you send CORP\\User1 and the password to PROXY1, it forwards them to ADFS1.</span></span>
    
4. <span data-ttu-id="569f8-272">ADFS1 проверяет имя CORP\\User1 и пароль с помощью DC1 и отправляет на локальный компьютер токен безопасности.</span><span class="sxs-lookup"><span data-stu-id="569f8-272">ADFS1 validates CORP\\User1 and the password with DC1 and sends your local computer a security token.</span></span>
    
5. <span data-ttu-id="569f8-273">Локальный компьютер отправляет маркер безопасности в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="569f8-273">Your local computer sends the security token to Microsoft 365.</span></span>
    
6. <span data-ttu-id="569f8-274">Microsoft 365 проверяет, действительно ли маркер безопасности создан в ADFS1, и разрешает доступ.</span><span class="sxs-lookup"><span data-stu-id="569f8-274">Microsoft 365 validates that the security token was created by ADFS1 and allows access.</span></span>
    
<span data-ttu-id="569f8-p113">Теперь для вашей пробной подписки настроена федеративная проверка подлинности. Вы можете использовать эту среду разработки и тестирования для расширенных сценариев проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="569f8-p113">Your trial subscription is now configured with federated authentication. You can use this dev/test environment for advanced authentication scenarios.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="569f8-277">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="569f8-277">Next step</span></span>

<span data-ttu-id="569f8-278">Когда вы будете готовы к развертыванию федеративной проверки подлинности с высоким уровнем доступности для Microsoft 365 в Azure, ознакомьтесь со статьей [развертывание федеративной проверки подлинности с высоким уровнем доступности для microsoft 365 в Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md).</span><span class="sxs-lookup"><span data-stu-id="569f8-278">When you are ready to deploy production-ready, high availability federated authentication for Microsoft 365 in Azure, see [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md).</span></span>
  
