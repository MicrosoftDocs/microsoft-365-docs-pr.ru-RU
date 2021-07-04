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
# <a name="manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="17109-103">Управление Microsoft 365 с помощью Windows PowerShell партнеров по делегированию разрешений доступа (DAP)</span><span class="sxs-lookup"><span data-stu-id="17109-103">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="17109-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="17109-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="17109-105">Windows PowerShell позволяет партнерам синдикации и поставщик облачных решений (CSP) легко управлять и сообщать о параметрах аренды клиентов, недоступных в Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="17109-105">Windows PowerShell allows Syndication and Cloud Solution Provider (CSP) partners to easily administer and report on customer tenancy settings that are not available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="17109-106">Обратите внимание, что для подключения учетной записи администратора-партнера к клиентской учетной записи требуется администрирование от имени (AOBO).</span><span class="sxs-lookup"><span data-stu-id="17109-106">Note that Administer on Behalf Of (AOBO) permissions are required for the partner administrator account to connect to its customer tenancies.</span></span>

<span data-ttu-id="17109-107">Партнеры по делегированным правам доступа (DAP)  партнеры по синдикации и поставщики облачных решений (CSP).</span><span class="sxs-lookup"><span data-stu-id="17109-107">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="17109-108">Они часто бывают поставщиками сети или телекоммуникационных услуг в других компаниях.</span><span class="sxs-lookup"><span data-stu-id="17109-108">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="17109-109">Они Microsoft 365 подписок в свои предложения по обслуживанию для своих клиентов.</span><span class="sxs-lookup"><span data-stu-id="17109-109">They bundle Microsoft 365 subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="17109-110">Когда они продают подписку Microsoft 365, они автоматически получают разрешения администрирования от имени (AOBO) для клиентов tenancies, чтобы они могли администрирование и отчет о клиентских tenancies.</span><span class="sxs-lookup"><span data-stu-id="17109-110">When they sell a Microsoft 365 subscription, they are automatically granted Administer On Behalf Of (AOBO) permissions to the customer tenancies so they can administer and report on the customer tenancies.</span></span>
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="17109-111">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="17109-111">What do you need to know before you begin?</span></span>

<span data-ttu-id="17109-112">Процедуры в этом разделе требуют подключения Подключение [к Microsoft 365 PowerShell](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="17109-112">The procedures in this topic require you to connect to [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="17109-113">Вам также необходимы учетные данные администратора для клиента партнера.</span><span class="sxs-lookup"><span data-stu-id="17109-113">You also need your partner tenant administrator credentials.</span></span>

## <a name="what-do-you-want-to-do"></a><span data-ttu-id="17109-114">Что нужно сделать</span><span class="sxs-lookup"><span data-stu-id="17109-114">What do you want to do?</span></span>

### <a name="list-all-tenant-ids"></a><span data-ttu-id="17109-115">Список всех идентификаторов клиентов</span><span class="sxs-lookup"><span data-stu-id="17109-115">List all tenant IDs</span></span>

> [!NOTE]
> <span data-ttu-id="17109-p103">Если у вас более 500 клиентов, ограничьте область синтаксиса командлета параметром  _-All_ или _-MaxResultsParameter_. Это применимо и к другим командлетам, которые могут выдавать большое количество данных, например **Get-MsolUser**.</span><span class="sxs-lookup"><span data-stu-id="17109-p103">If you have more than 500 tenants, scope the cmdlet syntax with either  _-All_ or _-MaxResultsParameter_. This applies to other cmdlets that can give a large output, such as **Get-MsolUser**.</span></span>

<span data-ttu-id="17109-118">Чтобы получить список всех идентификаторов пользовательских клиентов, к которым у вас есть доступ, выполните эту команду.</span><span class="sxs-lookup"><span data-stu-id="17109-118">To list all customer tenant Ids that you have access to, run this command.</span></span>

```powershell
Get-MsolPartnerContract -All | Select-Object TenantId
```

<span data-ttu-id="17109-119">Отобразится список всех пользовательских клиентов по идентификатору **TenantId**.</span><span class="sxs-lookup"><span data-stu-id="17109-119">This will display a listing of all your customer tenants by **TenantId**.</span></span>

>[!Note]
><span data-ttu-id="17109-120">В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени.</span><span class="sxs-lookup"><span data-stu-id="17109-120">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="17109-121">Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17109-121">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

### <a name="get-a-tenant-id-by-using-the-domain-name"></a><span data-ttu-id="17109-122">Получение идентификатора клиента по доменному имени</span><span class="sxs-lookup"><span data-stu-id="17109-122">Get a tenant ID by using the domain name</span></span>

<span data-ttu-id="17109-p105">Чтобы получить **TenantId** определенного пользовательского клиента по доменному имени, выполните эту команду. Замените _<domainname.onmicrosoft.com>_ фактическим доменным именем нужного пользовательского клиента.</span><span class="sxs-lookup"><span data-stu-id="17109-p105">To get the **TenantId** for a specific customer tenant by domain name, run this command. Replace _<domainname.onmicrosoft.com>_ with the actual domain name of the customer tenant that you want.</span></span>

```powershell
Get-MsolPartnerContract -DomainName <domainname.onmicrosoft.com> | Select-Object TenantId
```

### <a name="list-all-domains-for-a-tenant"></a><span data-ttu-id="17109-125">Список всех доменов для клиента</span><span class="sxs-lookup"><span data-stu-id="17109-125">List all domains for a tenant</span></span>

<span data-ttu-id="17109-p106">Чтобы получить все домены для любого пользовательского клиента, выполните эту команду. Замените  _<customer TenantId value>_ фактическим значением.</span><span class="sxs-lookup"><span data-stu-id="17109-p106">To get all domains for any one customer tenant, run this command. Replace  _<customer TenantId value>_ with the actual value.</span></span>

```powershell
Get-MsolDomain -TenantId <customer TenantId value>
```

<span data-ttu-id="17109-128">Если вы зарегистрировали дополнительные домены, будут возвращены все домены, связанные с **TenantId** пользователя.</span><span class="sxs-lookup"><span data-stu-id="17109-128">If you have registered additional domains, this will return all domains associated with the customer **TenantId**.</span></span>

### <a name="get-a-mapping-of-all-tenants-and-registered-domains"></a><span data-ttu-id="17109-129">Получение сопоставления всех клиентов и зарегистрированных доменов</span><span class="sxs-lookup"><span data-stu-id="17109-129">Get a mapping of all tenants and registered domains</span></span>

<span data-ttu-id="17109-130">Предыдущие команды PowerShell для Microsoft 365 показали, как извлекать или имена клиента или домены, но не одновременно и без четкого сопоставления между ними.</span><span class="sxs-lookup"><span data-stu-id="17109-130">The previous PowerShell for Microsoft 365 commands showed you how to retrieve either tenant IDs or domains but not both at the same time, and with no clear mapping between them all.</span></span> <span data-ttu-id="17109-131">Эта команда создает список всех идентификаторов пользовательских клиентов и их доменов.</span><span class="sxs-lookup"><span data-stu-id="17109-131">This command generates a listing of all your customer tenant IDs and their domains.</span></span>

```powershell
$Tenants = Get-MsolPartnerContract -All; $Tenants | foreach {$Domains = $_.TenantId; Get-MsolDomain -TenantId $Domains | fl @{Label="TenantId";Expression={$Domains}},name}
```

### <a name="get-all-users-for-a-tenant"></a><span data-ttu-id="17109-132">Получение всех пользователей для клиента</span><span class="sxs-lookup"><span data-stu-id="17109-132">Get all users for a tenant</span></span>

<span data-ttu-id="17109-p108">Эта команда выведен на экран **UserPrincipalName**, **DisplayName** и состояние **isLicensed** для всех пользователей определенного клиента. Замените _<customer TenantId value>_ фактическим значением.</span><span class="sxs-lookup"><span data-stu-id="17109-p108">This will display the **UserPrincipalName**, the **DisplayName**, and the **isLicensed** status for all users for a particular tenant. Replace _<customer TenantId value>_ with the actual value.</span></span>

```powershell
Get-MsolUser -TenantID <customer TenantId value>
```

### <a name="get-all-details-about-a-user"></a><span data-ttu-id="17109-135">Получение всех сведений о пользователе</span><span class="sxs-lookup"><span data-stu-id="17109-135">Get all details about a user</span></span>

<span data-ttu-id="17109-p109">Чтобы увидеть все свойства определенного пользователя, выполните эту команду. Замените  _<customer TenantId value>_ и _<user principal name value>_ фактическими значениями.</span><span class="sxs-lookup"><span data-stu-id="17109-p109">If you want to see all the properties of a particular user, run this command. Replace  _<customer TenantId value>_ and _<user principal name value>_ with the actual values.</span></span>

```powershell
Get-MsolUser -TenantId <customer TenantId value> -UserPrincipalName <user principal name value>
```

### <a name="add-users-set-options-and-assign-licenses"></a><span data-ttu-id="17109-138">Добавление пользователей настройка параметров и назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="17109-138">Add users, set options, and assign licenses</span></span>

<span data-ttu-id="17109-139">Массовое создание, конфигурация и лицензирование пользователей Microsoft 365 особенно эффективно с помощью PowerShell для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="17109-139">The bulk creation, configuration, and licensing of Microsoft 365 users is particularly efficient by using PowerShell for Microsoft 365.</span></span> <span data-ttu-id="17109-140">В этом двухшаговом процессе сначала создайте записи для всех пользователей, которые необходимо добавить в файл с разделенным запятой значением (CSV), а затем импортируете этот файл с помощью PowerShell для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="17109-140">In this two-step process, you first create entries for all the users you want to add in a comma-separated value (CSV) file and then import that file by using PowerShell for Microsoft 365.</span></span>

#### <a name="create-a-csv-file"></a><span data-ttu-id="17109-141">Создание CSV-файла</span><span class="sxs-lookup"><span data-stu-id="17109-141">Create a CSV file</span></span>

<span data-ttu-id="17109-142">Создайте CSV-файл, используя следующий формат:</span><span class="sxs-lookup"><span data-stu-id="17109-142">Create a CSV file by using this format:</span></span>

`UserPrincipalName,FirstName,LastName,DisplayName,Password,TenantId,UsageLocation,LicenseAssignment`

<span data-ttu-id="17109-143">где:</span><span class="sxs-lookup"><span data-stu-id="17109-143">where:</span></span>

- <span data-ttu-id="17109-p111">**UsageLocation**. Это значение  двухбуквенный код страны или региона пользователя в формате ISO. Такие коды можно найти на сайте [веб-платформы сведений об ISO](https://go.microsoft.com/fwlink/p/?LinkId=532703). Например, код США  US, а Бразилии  BR.</span><span class="sxs-lookup"><span data-stu-id="17109-p111">**UsageLocation**: The value for this is the two-letter ISO country/region code of the user. The country/region codes can be looked up at the[ISO Online Browsing Platform](https://go.microsoft.com/fwlink/p/?LinkId=532703). For example, the code for the United States is US, and the code for Brazil is BR.</span></span>

- <span data-ttu-id="17109-p112">**LicenseAssignment**. Это значение имеет следующий формат: `syndication-account:<PROVISIONING_ID>`. Например, при назначении пользователям клиентов лицензий O365_Business_Premium значение **LicenseAssignment** имеет следующий вид: **syndication-account:O365_Business_Premium**. Идентификаторы PROVISIONING_ID можно найти на портале партнеров синдикации, к которому вы имеете доступ как партнер службы синдикации или CSP.</span><span class="sxs-lookup"><span data-stu-id="17109-p112">**LicenseAssignment**: The value for this uses this format: `syndication-account:<PROVISIONING_ID>`. For example, if you are assigning customer tenant users O365_Business_Premium licenses, the **LicenseAssignment** value looks like this: **syndication-account:O365_Business_Premium**. You will find the PROVISIONING_IDs in the Syndication Partner Portal that you have access to as a Syndication or CSP partner.</span></span>

#### <a name="import-the-csv-file-and-create-the-users"></a><span data-ttu-id="17109-150">Импорт CSV-файла и создание пользователей</span><span class="sxs-lookup"><span data-stu-id="17109-150">Import the CSV file and create the users</span></span>

<span data-ttu-id="17109-p113">После создания CSV-файла выполните эту команду, чтобы создать учетные записи пользователей с бессрочными паролями, которые пользователи должны изменить при первом входе, и назначить им указанную лицензию. Не забудьте указать правильное имя CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="17109-p113">After you have your CSV file created, run this command to create user accounts with non-expiring passwords that the user must change at first sign-in and that assigns the license you specify. Be sure to substitute the correct CSV file name.</span></span>

```powershell
Import-Csv .\FILENAME.CSV | foreach {New-MsolUser -UserPrincipalName $_.UserPrincipalName -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -Password $_.Password -UsageLocation $_.UsageLocation -LicenseAssignment $_.LicenseAssignment -ForceChangePassword:$true -PasswordNeverExpires:$true -TenantId $_.TenantId}
```

## <a name="see-also"></a><span data-ttu-id="17109-153">См. также</span><span class="sxs-lookup"><span data-stu-id="17109-153">See also</span></span>

[<span data-ttu-id="17109-154">Справка для партнеров</span><span class="sxs-lookup"><span data-stu-id="17109-154">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=533477)
