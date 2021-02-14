---
title: Использование AllowSelfServicePurchase для модуля MSCommerce PowerShell
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Узнайте, как включить или отключить самообслуживную покупку с помощью cmdlet AllowSelfServicePurchase PowerShell.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 79ee2d96fa1ae6f49f0402f49ddec34e69257082
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653717"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>Использование AllowSelfServicePurchase для модуля MSCommerce PowerShell

Модуль **MSCommerce** PowerShell теперь доступен в [коллекции PowerShell.](https://aka.ms/allowselfservicepurchase-powershell-gallery) Модуль содержит значение параметра **PolicyID** для **AllowSelfServicePurchase,** которое позволяет контролировать возможность самостоятельного приобретения пользователями в организации.

Модуль **MSCommerce** PowerShell можно использовать для:

- Просмотр состояния по умолчанию значения параметра **AllowSelfServicePurchase** — включено ли оно или отключено
- Просмотр списка применимых продуктов и включения или отключения самостоятельной покупки
- Просмотр или изменение текущего параметра для определенного продукта, чтобы включить или отключить его

## <a name="requirements"></a>Requirements

Чтобы использовать модуль **MSCommerce** PowerShell, необходимо:

- Устройство с Windows 10
- Разрешение администратора для устройства
- Роль глобального администратора или администратора вы выставления счета для вашего клиента

## <a name="install-the-mscommerce-powershell-module"></a>Установка модуля MSCommerce PowerShell

Модуль **MSCommerce** PowerShell устанавливается на устройстве с Windows 10 один раз, а затем импортируется в каждый запускаемого сеанса PowerShell. Скачайте **модуль MSCommerce** PowerShell из коллекции [PowerShell.](https://aka.ms/allowselfservicepurchase-powershell-gallery)

Чтобы установить модуль **MSCommerce** PowerShell с **помощью PowerShellGet,** запустите следующую команду:

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>Импорт MSCommerce в сеанс PowerShell

После установки модуля на устройстве с Windows 10 его необходимо импортировать в каждый запуск сеанса PowerShell. Чтобы импортировать его в сеанс PowerShell, запустите следующую команду:

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>Подключение к MSCommerce с помощью учетных данных

Чтобы подключиться к модуле PowerShell с помощью учетных данных, запустите следующую команду.

```powershell
Connect-MSCommerce
```

Эта команда подключает текущий сеанс PowerShell к клиенту Azure Active Directory. Команда запросит имя пользователя и пароль для клиента, к который вы хотите подключиться. Если для учетных данных включена многофакторная проверка подлинности, для входа используется интерактивный параметр.

## <a name="view-details-for-allowselfservicepurchase"></a>Просмотр сведений для AllowSelfServicePurchase

Чтобы просмотреть описание значения параметра **AllowSelfServicePurchase** и состояния по умолчанию в зависимости от организации, запустите следующую команду:

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>Просмотр списка продуктов самообслуживки и их состояния

Чтобы просмотреть список всех доступных продуктов самообслуживанию и состояние каждого из них, запустите следующую команду:

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

В следующей таблице перечислены доступные продукты и **их ProductId.**

| Продукт | ProductId |
|-----------------------------|--------------|
| Power Apps на пользователя | CFQ7TTC0KP0P |
| Power Automate для каждого пользователя | CFQ7TTC0KP0N |
| Power BI Pro | CFQ7TTC0L3PB |
| Проект (план 1) | CFQ7TTC0KXND |
| Проект (план 3) | CFQ7TTC0KXNC |
| Visio (план 1) | CFQ7TTC0KXN9 |
| Visio (план 2) | CFQ7TTC0KXN8 |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>Просмотр или настройка состояния allowSelfServicePurchase

После просмотра списка продуктов, доступных для самостоятельной покупки, можно просмотреть или изменить параметр для определенного продукта.

Чтобы получить параметр политики для определенного продукта, запустите следующую команду:

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

Чтобы включить параметр политики для определенного продукта, запустите следующую команду:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

Чтобы отключить параметр политики для определенного продукта, запустите следующую команду:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a>Пример сценария отключения AllowSelfServicePurchase

В следующем примере пошагово импортировать модуль **MSCommerce,** войти в систему с помощью учетной записи, получить **ProductId** для Power Automate, а затем отключить **AllowSelfServicePurchase** для этого продукта.

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a>Устранение неполадок

### <a name="problem"></a>Проблема

Вы увидите следующее сообщение об ошибке:

> HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying connection was closed: An unexpected error occurred on a send.

Это может быть связано с более старой версией TLS. Чтобы подключить эту службу, необходимо использовать TLS 1.2 или более

### <a name="solution"></a>Решение

Обновление до TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
