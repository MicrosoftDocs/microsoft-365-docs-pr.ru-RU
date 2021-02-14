---
title: Этап 1. Федерарная проверка подлинности для высокой доступности
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
ms.assetid: 91266aac-4d00-4b5f-b424-86a1a837792c
description: Сводка. Настройка инфраструктуры Microsoft Azure для проведения федерационной проверки подлинности с высоким уровнем доступности для Microsoft 365.
ms.openlocfilehash: d2a9fe3c31468cd53576a82639e0e61901192d8e
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332344"
---
# <a name="high-availability-federated-authentication-phase-1-configure-azure"></a>Этап 1. Федеративная проверка подлинности для обеспечения высокой доступности: настройка Azure

На этом этапе создаются группы ресурсов, виртуальная сеть (VNet) и группы доступности в Azure, которые будут принимать виртуальные машины на этапах 2, 3 и 4. Прежде чем переходить к разделу [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md), необходимо завершить этот этап. См. все этапы развертывания федерационной проверки подлинности с высоким уровнем доступности для [Microsoft 365](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) в Azure.
  
В Azure должны быть предусмотрены указанные базовые компоненты.
  
- Группы ресурсов
    
- Нелокальная виртуальная сеть Azure с подсетями для размещения виртуальных машин Azure
    
- Группы безопасности сети для изоляции подсети
    
- Группы доступности
    
## <a name="configure-azure-components"></a>Настройка компонентов Azure

Перед настройкой компонентов Azure заполните указанные ниже таблицы. Распечатайте этот раздел и запишите необходимую информацию или скопируйте его в документ и заполните там. Укажите параметры виртуальной сети в таблице V.
  
|**Элемент**|**Параметр конфигурации**|**Описание**|**Значение**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |Имя виртуальной сети  <br/> |Имя виртуальной сети (например, FedAuthNet).  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |Расположение виртуальной сети  <br/> |Региональный центр обработки данных Azure, в котором будет расположена виртуальная сеть.  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |IP-адрес VPN-устройства  <br/> |Общедоступный IPv4-адрес интерфейса VPN-устройства в Интернете.  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
|4.  <br/> |Адресное пространство виртуальной сети  <br/> |Адресное пространство виртуальной сети. Чтобы определить это адресное пространство, обратитесь в ИТ-отдел.  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
|5.  <br/> |Общий ключ IPsec  <br/> |32-значный случайный буквенно-цифровой ключ для аутентификации обеих сторон VPN-подключения типа "сеть-сеть". Чтобы определить значение этого ключа, обратитесь в ИТ-отдел. Вы также можете ознакомиться со статьей [Создание случайной строки для предварительного ключа IPsec](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
   
 **Таблица V. Настройка распределенной виртуальной сети**
  
После этого укажите подсети этого решения в таблице S. Все адресные пространства должны быть указаны в формате CIDR (формате префиксов сети). Пример: 10.24.64.0/20.
  
Для первых трех подсетей укажите имя и одно пространство IP-адресов на основе адресного пространства виртуальной сети. Для подсети шлюза определите 27-битовое адресное пространство (с длиной префикса /27) для подсети шлюза Azure шлюза. Для этого выполните следующие действия:
  
1. Для переменных битов в адресном пространстве виртуальной сети задайте значение 1 (не больше бит, используемых подсетью шлюза), а для остальных битов задайте значение 0.
    
2. Преобразуйте результат в десятичное число и выразите его как адресное пространство, длина префикса которого соответствует размеру подсети шлюза.
    
См. [калькулятор адресного](address-space-calculator-for-azure-gateway-subnets.md) пространства для подсетей шлюза Azure для блока команд PowerShell и консольного приложения C# или Python, которое выполняет эти вычисления за вас.
  
Определите эти адресные пространства из адресного пространства виртуальной сети при поддержке ИТ-отдела.
  
|**Элемент**|**Имя подсети**|**Адресное пространство подсети**|**Назначение**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |Подсеть, используемая контроллером домена доменных служб Active Directory (AD DS) и виртуальными машинами (ВМ) сервера синхронизации каталогов.  <br/> |
|2.  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |Подсеть, используемая виртуальными машинами AD FS.  <br/> |
|3.  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |Подсеть, используемая виртуальными машинами прокси-серверов веб-приложений.  <br/> |
|4.  <br/> |GatewaySubnet  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |Подсеть, используемая виртуальными машинами шлюза Azure.  <br/> |
   
 **Таблица S. Подсети виртуальной сети**
  
После этого укажите статические IP-адреса, назначенные виртуальным машинам и экземплярам балансировщика нагрузки, в таблице I.
  
|**Элемент**|**Назначение**|**IP-адрес в подсети**|**Значение**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |Статический IP-адрес первого контроллера домена  <br/> |Четвертый возможный IP-адрес для адресного пространства подсети, определенной в элементе 1 таблицы S.  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |Статический IP-адрес второго контроллера домена  <br/> |Пятый возможный IP-адрес адресного пространства подсети, определенной в элементе 1 таблицы S.  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |Статический IP-адрес сервера синхронизации каталогов  <br/> |Шестой возможный IP-адрес адресного пространства подсети, определенной в элементе 1 таблицы S.  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
|4.  <br/> |Статический IP-адрес внутреннего балансировщика нагрузки для серверов AD FS  <br/> |Четвертый возможный IP-адрес для адресного пространства подсети, определенный в элементе 2 таблицы S.  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
|5.  <br/> |Статический IP-адрес первого сервера AD FS  <br/> |Пятый возможный IP-адрес адресного пространства подсети, определенной в элементе 2 таблицы S.  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
|6.  <br/> |Статический IP-адрес второго сервера AD FS  <br/> |Шестой возможный IP-адрес адресного пространства подсети, определенной в элементе 2 таблицы S.  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
|7.  <br/> |Статический IP-адрес первого прокси-сервера веб-приложений  <br/> |Четвертый возможный IP-адрес для адресного пространства подсети, определенный в элементе 3 таблицы S.  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
|8.  <br/> |Статический IP-адрес второго прокси-сервера веб-приложений  <br/> |Пятый возможный IP-адрес адресного пространства подсети, определенной в элементе 3 таблицы S.  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
   
 **Таблица I. Статические IP-адреса в виртуальной сети**
  
В таблице D укажите два DNS-сервера в локальной сети, которые необходимо использовать при начальной настройке контроллеров домена в виртуальной сети. Чтобы определить этот список, обратитесь в ИТ-отдел.
  
|**Элемент**|**Понятное имя DNS-сервера**|**IP-адрес DNS-сервера**|
|:-----|:-----|:-----|
|1.  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
   
 **Таблица D. Локальные DNS-сервера**
  
Для маршрутизации пакетов из нелокализованной сети в сеть организации через VPN-подключение "сеть-сеть" необходимо настроить виртуальную сеть с локальной сетью со списком адресных пространств (в нотации CIDR) для всех досяжимых местоположений в локальной сети организации. Список адресных пространств, которые определяют локальную сеть, должен быть уникален и не должен пересекаться с адресным пространством, используемым для других виртуальных или локальных сетей.
  
Укажите список адресных пространств локальной сети в таблице L. Обратите внимание, что представлено три пустых поля, но обычно требуется больше. Определите этот список адресных пространств при поддержке ИТ-отдела.
  
|**Элемент**|**Адресное пространство локальной сети**|
|:-----|:-----|
|1.  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
   
 **Таблица L. Префиксы адресов для локальной сети**
  
Теперь приступить к построению инфраструктуры Azure для федеращей проверки подлинности для Microsoft 365.
  
> [!NOTE]
> Для указанных ниже последовательностей команд используется последняя версия Azure PowerShell. См. ["Начало работы с Azure PowerShell".](https://docs.microsoft.com/powershell/azure/get-started-azureps) 
  
Запустите командную строку Azure PowerShell и войдите в свою учетную запись.
  
```powershell
Connect-AzAccount
```

> [!TIP]
> Чтобы создать готовые командные блоки PowerShell на основе пользовательских параметров, используйте эту книгу конфигурации [Microsoft Excel.](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx) 

Получите имя подписки с помощью следующей команды.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Для более старых версий Azure PowerShell используйте эту команду.
  
```powershell
Get-AzSubscription | Sort Name | Select SubscriptionName
```

Укажите свою подписку Azure. Замените все символы в кавычках правильным \< and > именем.
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

После этого создайте новые группы ресурсов. Чтобы задать уникальные имена, отобразите уже существующие группы ресурсов с помощью указанной команды.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Укажите уникальные имена групп ресурсов в следующей таблице.
  
|**Элемент**|**Имя группы ресурсов**|**Назначение**|
|:-----|:-----|:-----|
|1.  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |Контроллеры доменов  <br/> |
|2.  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |Серверы AD FS  <br/> |
|3.  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |Прокси-серверы веб-приложений  <br/> |
|4.  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |Элементы инфраструктуры  <br/> |
   
 **Таблица R. Группы ресурсов**
  
Создайте новые группы ресурсов с помощью этих команд.
  
```powershell
$locName="<an Azure location, such as West US>"
$rgName="<Table R - Item 1 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
$rgName="<Table R - Item 2 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
$rgName="<Table R - Item 3 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
$rgName="<Table R - Item 4 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
```

Затем создайте виртуальную сеть Azure и подсети.
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$vnetAddrPrefix="<Table V - Item 4 - Value column>"
$dnsServers=@( "<Table D - Item 1 - DNS server IP address column>", "<Table D - Item 2 - DNS server IP address column>" )
# Get the shortened version of the location
$locShortName=(Get-AzResourceGroup -Name $rgName).Location

# Create the subnets
$subnet1Name="<Table S - Item 1 - Subnet name column>"
$subnet1Prefix="<Table S - Item 1 - Subnet address space column>"
$subnet1=New-AzVirtualNetworkSubnetConfig -Name $subnet1Name -AddressPrefix $subnet1Prefix
$subnet2Name="<Table S - Item 2 - Subnet name column>"
$subnet2Prefix="<Table S - Item 2 - Subnet address space column>"
$subnet2=New-AzVirtualNetworkSubnetConfig -Name $subnet2Name -AddressPrefix $subnet2Prefix
$subnet3Name="<Table S - Item 3 - Subnet name column>"
$subnet3Prefix="<Table S - Item 3 - Subnet address space column>"
$subnet3=New-AzVirtualNetworkSubnetConfig -Name $subnet3Name -AddressPrefix $subnet3Prefix
$gwSubnet4Prefix="<Table S - Item 4 - Subnet address space column>"
$gwSubnet=New-AzVirtualNetworkSubnetConfig -Name "GatewaySubnet" -AddressPrefix $gwSubnet4Prefix

# Create the virtual network
New-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName -Location $locName -AddressPrefix $vnetAddrPrefix -Subnet $gwSubnet,$subnet1,$subnet2,$subnet3 -DNSServer $dnsServers

```

Затем создайте группы безопасности сети для каждой подсети с виртуальными машинами. Чтобы выполнить изоляцию подсети, можно добавить правила для определенных типов трафика, разрешенного или запрещенного в группу безопасности сети подсети.
  
```powershell
# Create network security groups
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName

New-AzNetworkSecurityGroup -Name $subnet1Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet1Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet1Name -AddressPrefix $subnet1Prefix -NetworkSecurityGroup $nsg

New-AzNetworkSecurityGroup -Name $subnet2Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet2Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet2Name -AddressPrefix $subnet2Prefix -NetworkSecurityGroup $nsg

New-AzNetworkSecurityGroup -Name $subnet3Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet3Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet3Name -AddressPrefix $subnet3Prefix -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

Затем используйте следующие команды, чтобы создать шлюзы для VPN-подключения типа "сеть-сеть".
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$locName="<Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name "GatewaySubnet"

# Attach a virtual network gateway to a public IP address and the gateway subnet
$publicGatewayVipName="PublicIPAddress"
$vnetGatewayIpConfigName="PublicIPConfig"
New-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$publicGatewayVip=Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName
$vnetGatewayIpConfig=New-AzVirtualNetworkGatewayIpConfig -Name $vnetGatewayIpConfigName -PublicIpAddressId $publicGatewayVip.Id -Subnet $subnet

# Create the Azure gateway
$vnetGatewayName="AzureGateway"
$vnetGateway=New-AzVirtualNetworkGateway -Name $vnetGatewayName -ResourceGroupName $rgName -Location $locName -GatewayType Vpn -VpnType RouteBased -IpConfigurations $vnetGatewayIpConfig

# Create the gateway for the local network
$localGatewayName="LocalNetGateway"
$localGatewayIP="<Table V - Item 3 - Value column>"
$localNetworkPrefix=@( <comma-separated, double-quote enclosed list of the local network address prefixes from Table L, example: "10.1.0.0/24", "10.2.0.0/24"> )
$localGateway=New-AzLocalNetworkGateway -Name $localGatewayName -ResourceGroupName $rgName -Location $locName -GatewayIpAddress $localGatewayIP -AddressPrefix $localNetworkPrefix

# Define the Azure virtual network VPN connection
$vnetConnectionName="S2SConnection"
$vnetConnectionKey="<Table V - Item 5 - Value column>"
$vnetConnection=New-AzVirtualNetworkGatewayConnection -Name $vnetConnectionName -ResourceGroupName $rgName -Location $locName -ConnectionType IPsec -SharedKey $vnetConnectionKey -VirtualNetworkGateway1 $vnetGateway -LocalNetworkGateway2 $localGateway

```

> [!NOTE]
> Федеративная проверка подлинности для отдельных пользователей не зависит от локальных ресурсов. Однако если это VPN-подключение "сеть-сеть" становится недоступным, контроллеры домена в VNet не будут получать обновления учетных записей пользователей и групп, сделанные в локальной службе доменов Active Directory. Чтобы этого не произошло, можно настроить высокую доступность VPN-подключения "сеть-сеть". Дополнительные сведения см. в сведениях о высокодоступных подключениях между локальной и [VNet- и VNet](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-highlyavailable)
  
После этого запишите общедоступный IPv4-адрес VPN-шлюза Azure для виртуальной сети из результата этой команды:
  
```powershell
Get-AzPublicIpAddress -Name $publicGatewayVipName -ResourceGroupName $rgName
```

Затем настройте локальное VPN-устройство для подключения к VPN-шлюзу Azure. Дополнительные сведения см. в [подстройке "Настройка VPN-устройства".](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpn-devices)
  
Чтобы настроить локальное VPN-устройство, вам потребуется следующее:
  
- Общедоступный IPv4-адрес VPN-шлюза Azure.
    
- Предварительный ключ IPsec для VPN-подключения "сеть-сеть" (таблица V, элемент 5. Столбец "Значение").
    
Убедитесь, что адресное пространство виртуальной сети доступно из локальной сети. Для этого добавьте маршрут, соответствующий адресному пространству виртуальной сети на вашем VPN-устройстве и сообщите этот маршрут остальной инфраструктуре маршрутизации в сети организации. Чтобы определить, как это сделать, обратитесь в ИТ-отдел.
  
После этого определите имена четырех групп доступности. Заполните таблицу A. 
  
|**Элемент**|**Назначение**|**Имя группы доступности**|
|:-----|:-----|:-----|
|1.  <br/> |Контроллеры доменов  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |Серверы AD FS  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |Прокси-серверы веб-приложений  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
   
 **Таблица A. Группы доступности**
  
Вам потребуются эти имена при создании виртуальных машин на этапах 2, 3 и 4.
  
Создайте новые группы доступности с помощью этих команд Azure PowerShell.
  
```powershell
$locName="<the Azure location for your new resource group>"
$rgName="<Table R - Item 1 - Resource group name column>"
$avName="<Table A - Item 1 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
$rgName="<Table R - Item 2 - Resource group name column>"
$avName="<Table A - Item 2 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
$rgName="<Table R - Item 3 - Resource group name column>"
$avName="<Table A - Item 3 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
```

Ниже показана конфигурация, полученная в результате успешного выполнения этого этапа.
  
**Этап 1. Инфраструктура Azure для федерационной проверки подлинности с высоким уровнем доступности для Microsoft 365**

![Этап 1 федерационной проверки подлинности Microsoft 365 с высоким уровнем доступности в Azure с инфраструктурой Azure](../media/4e7ba678-07df-40ce-b372-021bf7fc91fa.png)
  
## <a name="next-step"></a>Следующий этап

Этап [2. Настройка контроллеров](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) домена для продолжения настройки этой рабочей нагрузки.
  
## <a name="see-also"></a>См. также

[Развертывание федеративной проверки подлинности для обеспечения высокой доступности Microsoft 365 в Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Федератное удостоверение для среды тестирования и тестирования Microsoft 365](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Центр архитектуры и решений Microsoft 365](../solutions/solution-architecture-center.md)

[Понимание удостоверений Microsoft 365 и Azure Active Directory](about-microsoft-365-identity.md)


