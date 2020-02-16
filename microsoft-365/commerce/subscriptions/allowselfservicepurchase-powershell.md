---
title: Использование Алловселфсервицепурчасе для модуля PowerShell Мскоммерце
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Узнайте, как использовать командлет PowerShell Алловселфсервицепурчасе для включения или отключения самостоятельной покупки.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 0e9f9e3ee87f62b903e4bf7069f31319253de62d
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42080346"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>Использование Алловселфсервицепурчасе для модуля PowerShell Мскоммерце

Теперь модуль PowerShell **мскоммерце** доступен в [коллекции PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery). Модуль включает значение параметра **полициид** для **алловселфсервицепурчасе** , позволяющее контролировать, могут ли пользователи в вашей организации совершать собственные покупки.

С помощью модуля PowerShell **мскоммерце** можно выполнять следующие действия:

- Просмотр состояния, используемого по умолчанию для значения параметра **алловселфсервицепурчасе** , независимо от того, включена он или отключен
- Просмотр списка доступных продуктов и включение или отключение самостоятельной покупки
- Просмотр или изменение текущего значения для конкретного продукта, чтобы включить или отключить его

## <a name="requirements"></a>Requirements

Чтобы использовать модуль PowerShell **мскоммерце** , вам потребуется следующее:

- Устройство с Windows 10
- Разрешение администратора для устройства
- Глобальная роль администратора или роль администратора выставления счетов для клиента

## <a name="install-the-mscommerce-powershell-module"></a>Установка модуля PowerShell Мскоммерце

Вы устанавливаете модуль PowerShell **мскоммерце** на устройстве с Windows 10, а затем импортируете его в каждый запущенный сеанс PowerShell. Скачайте модуль PowerShell **мскоммерце** из [коллекции PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery).

Чтобы установить модуль PowerShell **мскоммерце** с помощью **PowerShellGet**, выполните следующую команду:

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>Импорт Мскоммерце в сеанс PowerShell

После установки модуля на устройстве с Windows 10 импортируйте его в каждый запущенный сеанс PowerShell. Чтобы импортировать его в сеанс PowerShell, выполните следующую команду:

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>Подключение к Мскоммерце с вашими учетными данными

Чтобы подключиться к модулю PowerShell с вашими учетными данными, выполните следующую команду.

```powershell
Connect-MSCommerce
```

Эта команда подключает текущий сеанс PowerShell к клиенту Azure Active Directory. В командной строке запрашивается имя пользователя и пароль для клиента, к которому вы хотите подключиться. Если учетные данные включены с многофакторной проверкой подлинности, для входа используется интерактивный режим.

## <a name="view-details-for-allowselfservicepurchase"></a>Просмотр сведений для Алловселфсервицепурчасе

Чтобы просмотреть описание значения параметра **алловселфсервицепурчасе** и состояние по умолчанию на основе вашей организации, выполните следующую команду:

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>Просмотр списка самостоятельных продуктов покупки и их состояния

Чтобы просмотреть список всех доступных продуктов для самостоятельной покупки и состояние каждой из них, выполните следующую команду:

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

В следующей таблице перечислены доступные продукты и их **ProductID**.

| Продукт | ProductId |
|-----------------------------|--------------|
| Power Apps для каждого пользователя | CFQ7TTC0KP0P |
| Автоматизация управления питанием на пользователя | CFQ7TTC0KP0N |
| Power BI Pro | CFQ7TTC0L3PB |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>Просмотр или установка состояния Алловселфсервицепурчасе

После просмотра списка продуктов, доступных для самостоятельной покупки, вы можете просмотреть или изменить параметр для определенного продукта.

Чтобы получить параметр политики для определенного продукта, выполните следующую команду:

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

Чтобы включить параметр политики для определенного продукта, выполните следующую команду:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

Чтобы отключить параметр политики для определенного продукта, выполните следующую команду:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a>Пример скрипта для отключения Алловселфсервицепурчасе

В приведенном ниже примере показано, как импортировать модуль **мскоммерце** , войти с помощью учетной записи, получить **ProductID** для Power автоматизировать, а затем отключить **алловселфсервицепурчасе** для этого продукта.

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a>Устранение неполадок

**Проблема**

Отображается следующее сообщение об ошибке:

    HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying
    connection was closed: An unexpected error occurred on a send.

Это может быть вызвано более старой версией протокола TLS. Чтобы подключить эту службу, необходимо использовать протокол TLS 1,2 или более поздней версии

**Решение**

Обновление до TLS 1,2:[https://docs.microsoft.com/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/configmgr/core/plan-design/security/enable-tls-1-2)

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
