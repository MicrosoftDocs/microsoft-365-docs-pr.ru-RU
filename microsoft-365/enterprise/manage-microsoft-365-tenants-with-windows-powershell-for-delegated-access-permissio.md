---
title: Управление Microsoft 365 с помощью Windows PowerShell для партнеров DAP
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: f92d5116-5b66-4150-ad20-1452fc3dd712
description: В этой статье вы узнаете, как использовать PowerShell для Microsoft 365 управления клиентом.
ms.openlocfilehash: 96c2c148b64d638ea977922f6a0ae3d5e23a8ace
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289107"
---
# <a name="manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a>Управление Microsoft 365 с помощью Windows PowerShell партнеров по делегированию разрешений доступа (DAP)

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Windows PowerShell позволяет партнерам синдикации и поставщик облачных решений (CSP) легко управлять и сообщать о параметрах аренды клиентов, недоступных в Центр администрирования Microsoft 365. Обратите внимание, что для подключения учетной записи администратора-партнера к клиентской учетной записи требуется администрирование от имени (AOBO).

Партнеры по делегированным правам доступа (DAP)  партнеры по синдикации и поставщики облачных решений (CSP). Они часто бывают поставщиками сети или телекоммуникационных услуг в других компаниях. Они Microsoft 365 подписок в свои предложения по обслуживанию для своих клиентов. Когда они продают подписку Microsoft 365, они автоматически получают разрешения администрирования от имени (AOBO) для клиентов tenancies, чтобы они могли администрирование и отчет о клиентских tenancies.
## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

Процедуры в этом разделе требуют подключения Подключение [к Microsoft 365 PowerShell](connect-to-microsoft-365-powershell.md).

Вам также необходимы учетные данные администратора для клиента партнера.

## <a name="what-do-you-want-to-do"></a>Что нужно сделать

### <a name="list-all-tenant-ids"></a>Список всех идентификаторов клиентов

> [!NOTE]
> Если у вас более 500 клиентов, ограничьте область синтаксиса командлета параметром  _-All_ или _-MaxResultsParameter_. Это применимо и к другим командлетам, которые могут выдавать большое количество данных, например **Get-MsolUser**.

Чтобы получить список всех идентификаторов пользовательских клиентов, к которым у вас есть доступ, выполните эту команду.

```powershell
Get-MsolPartnerContract -All | Select-Object TenantId
```

Отобразится список всех пользовательских клиентов по идентификатору **TenantId**.

>[!Note]
>В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени. Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.
>

### <a name="get-a-tenant-id-by-using-the-domain-name"></a>Получение идентификатора клиента по доменному имени

Чтобы получить **TenantId** определенного пользовательского клиента по доменному имени, выполните эту команду. Замените _<domainname.onmicrosoft.com>_ фактическим доменным именем нужного пользовательского клиента.

```powershell
Get-MsolPartnerContract -DomainName <domainname.onmicrosoft.com> | Select-Object TenantId
```

### <a name="list-all-domains-for-a-tenant"></a>Список всех доменов для клиента

Чтобы получить все домены для любого пользовательского клиента, выполните эту команду. Замените  _<customer TenantId value>_ фактическим значением.

```powershell
Get-MsolDomain -TenantId <customer TenantId value>
```

Если вы зарегистрировали дополнительные домены, будут возвращены все домены, связанные с **TenantId** пользователя.

### <a name="get-a-mapping-of-all-tenants-and-registered-domains"></a>Получение сопоставления всех клиентов и зарегистрированных доменов

Предыдущие команды PowerShell для Microsoft 365 показали, как извлекать или имена клиента или домены, но не одновременно и без четкого сопоставления между ними. Эта команда создает список всех идентификаторов пользовательских клиентов и их доменов.

```powershell
$Tenants = Get-MsolPartnerContract -All; $Tenants | foreach {$Domains = $_.TenantId; Get-MsolDomain -TenantId $Domains | fl @{Label="TenantId";Expression={$Domains}},name}
```

### <a name="get-all-users-for-a-tenant"></a>Получение всех пользователей для клиента

Эта команда выведен на экран **UserPrincipalName**, **DisplayName** и состояние **isLicensed** для всех пользователей определенного клиента. Замените _<customer TenantId value>_ фактическим значением.

```powershell
Get-MsolUser -TenantID <customer TenantId value>
```

### <a name="get-all-details-about-a-user"></a>Получение всех сведений о пользователе

Чтобы увидеть все свойства определенного пользователя, выполните эту команду. Замените  _<customer TenantId value>_ и _<user principal name value>_ фактическими значениями.

```powershell
Get-MsolUser -TenantId <customer TenantId value> -UserPrincipalName <user principal name value>
```

### <a name="add-users-set-options-and-assign-licenses"></a>Добавление пользователей настройка параметров и назначение лицензий

Массовое создание, конфигурация и лицензирование пользователей Microsoft 365 особенно эффективно с помощью PowerShell для Microsoft 365. В этом двухшаговом процессе сначала создайте записи для всех пользователей, которые необходимо добавить в файл с разделенным запятой значением (CSV), а затем импортируете этот файл с помощью PowerShell для Microsoft 365.

#### <a name="create-a-csv-file"></a>Создание CSV-файла

Создайте CSV-файл, используя следующий формат:

`UserPrincipalName,FirstName,LastName,DisplayName,Password,TenantId,UsageLocation,LicenseAssignment`

где:

- **UsageLocation**. Это значение  двухбуквенный код страны или региона пользователя в формате ISO. Такие коды можно найти на сайте [веб-платформы сведений об ISO](https://go.microsoft.com/fwlink/p/?LinkId=532703). Например, код США  US, а Бразилии  BR.

- **LicenseAssignment**. Это значение имеет следующий формат: `syndication-account:<PROVISIONING_ID>`. Например, при назначении пользователям клиентов лицензий O365_Business_Premium значение **LicenseAssignment** имеет следующий вид: **syndication-account:O365_Business_Premium**. Идентификаторы PROVISIONING_ID можно найти на портале партнеров синдикации, к которому вы имеете доступ как партнер службы синдикации или CSP.

#### <a name="import-the-csv-file-and-create-the-users"></a>Импорт CSV-файла и создание пользователей

После создания CSV-файла выполните эту команду, чтобы создать учетные записи пользователей с бессрочными паролями, которые пользователи должны изменить при первом входе, и назначить им указанную лицензию. Не забудьте указать правильное имя CSV-файла.

```powershell
Import-Csv .\FILENAME.CSV | foreach {New-MsolUser -UserPrincipalName $_.UserPrincipalName -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -Password $_.Password -UsageLocation $_.UsageLocation -LicenseAssignment $_.LicenseAssignment -ForceChangePassword:$true -PasswordNeverExpires:$true -TenantId $_.TenantId}
```

## <a name="see-also"></a>См. также

[Справка для партнеров](https://go.microsoft.com/fwlink/p/?LinkId=533477)
