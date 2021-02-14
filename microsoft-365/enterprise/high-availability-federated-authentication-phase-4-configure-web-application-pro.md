---
title: Этап 4. Настройка прокси-серверов веб-приложений для федерационной проверки подлинности для высокой доступности
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 1c903173-67cd-47da-86d9-d333972dda80
description: Сводка. Настройте прокси-серверы веб-приложений для федерационной проверки подлинности с высоким уровнем доступности для Microsoft 365 в Microsoft Azure.
ms.openlocfilehash: fd63274ffb9528cedb88fc2ba77834cfd56664d4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693343"
---
# <a name="high-availability-federated-authentication-phase-4-configure-web-application-proxies"></a>Этап 4. Федеративная проверка подлинности для обеспечения высокой доступности: настройка прокси веб-приложений

На этом этапе развертывания федераированной проверки подлинности Microsoft 365 с высоким уровнем доступности в службах инфраструктуры Azure создается внутренний балансировщик нагрузки и два сервера AD FS.
  
Перед переходом к этапу 5: настройка федерационной проверки подлинности [для Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md)необходимо завершить этот этап. См. все этапы развертывания федерационной проверки подлинности с высоким уровнем доступности для [Microsoft 365](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) в Azure.
  
## <a name="create-the-internet-facing-load-balancer-in-azure"></a>Создание балансировки нагрузки с доступом к Интернету в Azure

Необходимо создать балансировку нагрузки с доступом к Интернету, чтобы Azure равномерно распределяла входящий трафик проверки подлинности клиентов из Интернета между двумя прокси-серверами веб-приложений.
  
> [!NOTE]
> Для указанных ниже последовательностей команд используется последняя версия Azure PowerShell. См. ["Начало работы с Azure PowerShell".](https://docs.microsoft.com/powershell/azure/get-started-azureps) 
  
После того как вы предоставили значения расположения и группы ресурсов, запустите итоговый блок в командной области Azure PowerShell или в isE PowerShell.
  
> [!TIP]
> Чтобы создать готовые командные блоки PowerShell на основе пользовательских параметров, используйте эту книгу конфигурации [Microsoft Excel.](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx) 

```powershell
# Set up key variables
$locName="<your Azure location>"
$rgName="<Table R - Item 4 - Resource group name column>"

$publicIP=New-AzPublicIpAddress -ResourceGroupName $rgName -Name "WebProxyPublicIP" -Location $LocName -AllocationMethod "Static"
$frontendIP=New-AzLoadBalancerFrontendIpConfig -Name "WebAppProxyServers-LBFE" -PublicIpAddress $publicIP
$beAddressPool=New-AzLoadBalancerBackendAddressPoolConfig -Name "WebAppProxyServers-LBBE"
$healthProbe=New-AzLoadBalancerProbeConfig -Name "WebServersProbe" -Protocol "TCP" -Port 443 -IntervalInSeconds 15 -ProbeCount 2
$lbrule=New-AzLoadBalancerRuleConfig -Name "WebTraffic" -FrontendIpConfiguration $frontendIP -BackendAddressPool $beAddressPool -Probe $healthProbe -Protocol "TCP" -FrontendPort 443 -BackendPort 443
New-AzLoadBalancer -ResourceGroupName $rgName -Name "WebAppProxyServers" -Location $locName -LoadBalancingRule $lbrule -BackendAddressPool $beAddressPool -Probe $healthProbe -FrontendIpConfiguration $frontendIP
```

Чтобы отобразить общедоступный IP-адрес, присвоенный вашему балансированию нагрузки с доступом к Интернету, запустите указанные здесь команды в командной командной области Azure PowerShell на локальном компьютере.
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "WebProxyPublicIP" -ResourceGroup $rgName).IPAddress
```

## <a name="determine-your-federation-service-fqdn-and-create-dns-records"></a>Определение FQDN службы федерации и создание записей DNS

Необходимо определить DNS-имя для идентификации имени службы федерации в Интернете. Azure AD Connect настроит Microsoft 365 с этим именем на этапе 5, который станет частью URL-адреса, отправляемого Microsoft 365 подключающихся клиентов для получения маркера безопасности. Пример: fs.contoso.com (fs означает службу федерации).
  
После создания FDQN службы федерации создайте общедоступный домен DNS-записи A для FDQN службы федерации, которая соединена с общедоступным IP-адресом службы балансировки нагрузки с доступом к Интернету в Azure.
  
|**Имя**|**Type** (Тип)|**TTL** (Срок жизни)|**Значение**|
|:-----|:-----|:-----|:-----|
|FDQN службы федерации  <br/> |A  <br/> |3600  <br/> |общедоступный IP-адрес службы балансировки нагрузки с доступом к Интернету в Azure (отображается командой **write-Host** в предыдущем разделе) <br/> |
   
Вот пример:
  
|**Имя**|**Type** (Тип)|**TTL** (Срок жизни)|**Значение**|
|:-----|:-----|:-----|:-----|
|fs.contoso.com  <br/> |A  <br/> |3600  <br/> |131.107.249.117  <br/> |
   
Затем добавьте запись DNS-адреса в частное пространство имен DNS вашей организации, которое соединено с FQDN службы федерации в частный IP-адрес, присвоенный внутренней подстройке нагрузки для серверов AD FS (таблица I, элемент 4, столбец "Значение").
  
## <a name="create-the-web-application-proxy-server-virtual-machines-in-azure"></a>Создание виртуальных машин прокси-сервера веб-приложения в Azure

Используйте следующий блок команд Azure PowerShell для создания виртуальных машин для двух прокси-серверов веб-приложений. 
  
Обратите внимание, что в следующих наборах команд Azure PowerShell используются значения из следующих таблиц:
  
- таблица M (для виртуальных машин);
    
- таблица R (для групп ресурсов);
    
- таблица V (для параметров виртуальной сети);
    
- таблица S (для подсетей);
    
- таблица I (для статических IP-адресов);
    
- таблица A (для групп доступности).
    
Помните, что вы определили таблицу M на этапе [2.](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) Настройка контроллеров домена и таблиц R, V, S, I и A на этапе [1. Настройка Azure.](high-availability-federated-authentication-phase-1-configure-azure.md)
  
Задав правильные значения, выполните полученный блок в командной строке Azure PowerShell или в интегрированной среде сценариев PowerShell.
  
```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table R - Item 3 - Subnet name column>"
$avName="<Table A - Item 3 - Availability set name column>"
$rgNameTier="<Table R - Item 3 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName
$backendSubnet=Get-AzVirtualNetworkSubnetConfig -Name $subnetName -VirtualNetwork $vnet
$webLB=Get-AzLoadBalancer -ResourceGroupName $rgName -Name "WebAppProxyServers"

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName

# Create the first web application proxy server virtual machine
$vmName="<Table M - Item 6 - Virtual machine name column>"
$vmSize="<Table M - Item 6 - Minimum size column>"
$staticIP="<Table I - Item 7 - Value column>"
$diskStorageType="<Table M - Item 6 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first web application proxy server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second web application proxy virtual machine
$vmName="<Table M - Item 7 - Virtual machine name column>"
$vmSize="<Table M - Item 7 - Minimum size column>"
$staticIP="<Table I - Item 8 - Value column>"
$diskStorageType="<Table M - Item 7 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName  -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second web application proxy server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> Эти виртуальные машины предназначены для работы в интрасети, поэтому им не назначается общедоступный IP-адрес или метка доменного имени DNS и они не подключаются к Интернету. Однако это также означает, что к ним невозможно подключиться с помощью портала Azure. Команда **Подключиться** недоступна при просмотре свойств виртуальной машины. Используйте метод доступа к удаленному рабочему столу или другое средство удаленного рабочего стола для подключения к виртуальной машине с помощью частного IP-адреса или DNS-имени интрасети и учетных данных локальной учетной записи администратора.
  
Здесь показана конфигурация, полученная в результате успешного выполнения этого этапа (с заполнителями вместо имен компьютеров).
  
**Этап 4. Подстановка нагрузки для Интернета и прокси-серверы веб-приложений для инфраструктуры федерационной проверки подлинности с высоким уровнем доступности в Azure**

![Этап 4 инфраструктуры федераированной проверки подлинности Microsoft 365 с высоким уровнем доступности в Azure с прокси-серверами веб-приложений](../media/7e03183f-3b3b-4cbe-9028-89cc3f195a63.png)
  
## <a name="next-step"></a>Следующий этап

Этап [5. Настройка федерационной](high-availability-federated-authentication-phase-5-configure-federated-authentic.md) проверки подлинности для Microsoft 365 для продолжения настройки этой рабочей нагрузки.
  
## <a name="see-also"></a>См. также

[Развертывание федеративной проверки подлинности для обеспечения высокой доступности Microsoft 365 в Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Федератное удостоверение для среды тестирования и тестирования Microsoft 365](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Центр архитектуры и решений Microsoft 365](../solutions/solution-architecture-center.md)

