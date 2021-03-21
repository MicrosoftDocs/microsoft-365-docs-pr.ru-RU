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
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
description: Узнайте, как использовать комлет AllowSelfServicePurchase PowerShell для отключения покупки самообслужива.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 9fb5593855f9523198a3d70548e444a831e82c80
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918246"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>Использование AllowSelfServicePurchase для модуля MSCommerce PowerShell

Модуль **MSCommerce** PowerShell теперь доступен в [Галерее PowerShell.](https://aka.ms/allowselfservicepurchase-powershell-gallery) Модуль содержит значение **параметра PolicyID** для **AllowSelfServicePurchase,** которое позволяет контролировать, могут ли пользователи в организации делать покупки с помощью самообслужива.

Модуль **MSCommerce** PowerShell можно использовать для:

- Просмотр состояния параметра **AllowSelfServicePurchase** по умолчанию — включено оно или отключено.
- Просмотр списка применимых продуктов и включена ли покупка самообслуживки или отключена
- Просмотр или изменение текущего параметра для определенного продукта, чтобы включить или отключить его

## <a name="requirements"></a>Требования

Чтобы использовать **модуль MSCommerce** PowerShell, необходимо:

- Устройство Windows 10
- Разрешение администратора для устройства
- Роль администратора глобального или биллинга для клиента

## <a name="install-the-mscommerce-powershell-module"></a>Установка модуля MSCommerce PowerShell

Один раз **установите модуль MSCommerce** PowerShell на устройстве Windows 10 и импортируете его в каждую начинаемую сессию PowerShell. Скачайте **модуль MSCommerce** PowerShell из [галереи PowerShell.](https://aka.ms/allowselfservicepurchase-powershell-gallery)

Чтобы установить **модуль MSCommerce** PowerShell с **PowerShellGet,** запустите следующую команду:

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>Импорт MSCommerce в сеанс PowerShell

После установки модуля на устройстве Windows 10 вы импортируете его в каждую начинаемую сессию PowerShell. Чтобы импортировать его в сеанс PowerShell, запустите следующую команду:

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>Подключение к MSCommerce с учетными данными

Чтобы подключиться к модуле PowerShell с учетными данными, запустите следующую команду.

```powershell
Connect-MSCommerce
```

Эта команда соединяет текущий сеанс PowerShell с клиентом Azure Active Directory. Команда подсказыет вам имя пользователя и пароль для клиента, к который необходимо подключиться. Если для учетных данных включена многофакторная проверка подлинности, для входа в систему используется интерактивный параметр.

## <a name="view-details-for-allowselfservicepurchase"></a>Просмотр сведений для AllowSelfServicePurchase

Чтобы просмотреть описание значения параметров **AllowSelfServicePurchase** и состояния по умолчанию, основанного на организации, запустите следующую команду:

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>Просмотр списка продуктов самообслуживки и их состояния

Чтобы просмотреть список всех доступных продуктов самообслуживки и состояние каждого из них, запустите следующую команду:

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

В следующей таблице перечислены доступные продукты и **их ProductId.**

| Продукт | ProductId |
|-----------------------------|--------------|
| Power Apps на пользователя | CFQ7TTC0KP0P |
| Power Automate для каждого пользователя | CFQ7TTC0KP0N |
| Power Automate RPA | CFQ7TTC0KXG6  |
| Power BI Premium (автономный) | CFQ7TTC0KXG7  |
| Power BI Pro | CFQ7TTC0L3PB |
| Project Plan 1 | CFQ7TTC0KXND |
| Project Plan 3 | CFQ7TTC0KXNC |
| Visio Plan 1 | CFQ7TTC0KXN9 |
| Visio Plan 2 | CFQ7TTC0KXN8 |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>Просмотр или настройка состояния для AllowSelfServicePurchase

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

В следующем примере вы можете узнать, как импортировать модуль **MSCommerce,** войти в учетную запись, получить **ProductId** для power Automate, а затем отключить **AllowSelfServicePurchase** для этого продукта.

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a>Устранение неполадок

### <a name="problem"></a>Проблема

Вы видите следующее сообщение об ошибке:

> HandleError. Не удалось получить политику с помощью PolicyId "AllowSelfServicePurchase", ErrorMessage . Первое подключение было закрыто: при отправке произошла неожиданная ошибка.

Это может быть связано со старой версией безопасности транспортного слоя (TLS). Чтобы подключить эту службу, необходимо использовать TLS 1.2 или более

### <a name="solution"></a>Решение

Обновление до TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->