---
title: Настройка расширенных аудитов в Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: В этой статье описано, как настроить расширенный аудит, чтобы можно было проводить судебно-медицинские расследования при взломе учетных записей пользователей или расследования других инцидентов, связанных с безопасностью.
ms.openlocfilehash: d1752ee7714056254a6c0e5c009aa9aa79ddff3b
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2021
ms.locfileid: "52314412"
---
# <a name="set-up-advanced-audit-in-microsoft-365"></a><span data-ttu-id="42595-103">Настройка расширенных аудитов в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="42595-103">Set up Advanced Audit in Microsoft 365</span></span>

<span data-ttu-id="42595-104">Если в вашей организации имеется лицензия на подписку и лицензирование конечных пользователей, которое поддерживает расширенный аудит, выполните следующие действия по настройкам и использованию дополнительных возможностей в advanced Audit.</span><span class="sxs-lookup"><span data-stu-id="42595-104">If your organization has a subscription and end user licensing that supports Advanced Audit, perform the following steps to set up and use the additional capabilities in Advanced Audit.</span></span>

![Рабочий процесс настройки расширенного аудита](../media/AdvancedAuditWorkflow.png)

## <a name="step1-set-up-advanced-audit-for-users"></a><span data-ttu-id="42595-106">Шаг 1. Настройка расширенных аудитов для пользователей</span><span class="sxs-lookup"><span data-stu-id="42595-106">Step1: Set up Advanced Audit for users</span></span>

<span data-ttu-id="42595-107">Возможности расширенного аудита, такие как регистрация важных событий, например MailItemsAccessed и Send, требуют назначения соответствующей лицензии E5 пользователям.</span><span class="sxs-lookup"><span data-stu-id="42595-107">Advanced Audit features such as the ability to log crucial events such as MailItemsAccessed and Send require an appropriate E5 license assigned to users.</span></span> <span data-ttu-id="42595-108">Кроме того, для этих пользователей должен быть включен план приложения или службы расширенного аудита.</span><span class="sxs-lookup"><span data-stu-id="42595-108">Additionally, the Advanced Auditing app/service plan must be enabled for those users.</span></span> <span data-ttu-id="42595-109">Чтобы убедиться, что пользователям назначено приложение расширенного аудита, выполните следующие действия для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="42595-109">To verify that the Advanced Auditing app is assigned to users, perform the following steps for each user:</span></span>

1. <span data-ttu-id="42595-110">В [Центре администрирования Microsoft 365](https://admin.microsoft.com/Adminportal) перейдите в раздел **Пользователи** > **Активные пользователи** и выберите пользователя.</span><span class="sxs-lookup"><span data-stu-id="42595-110">In the [Microsoft 365 admin center](https://admin.microsoft.com/Adminportal), go to **Users** > **Active users**, and select a user.</span></span>

2. <span data-ttu-id="42595-111">На всплывающей странице свойств пользователя щелкните **Лицензии и приложения**.</span><span class="sxs-lookup"><span data-stu-id="42595-111">On the user properties flyout page, click **Licenses and apps**.</span></span>

3. <span data-ttu-id="42595-112">В разделе **Лицензии** убедитесь, что пользователю назначена лицензия E5 или назначена соответствующая надстройка.</span><span class="sxs-lookup"><span data-stu-id="42595-112">In the **Licenses** section, verify that the user is assigned an E5 license or is assigned an appropriate add-on license.</span></span> <span data-ttu-id="42595-113">Список лицензий, поддерживаюющих расширенный аудит, см. в дополнительных требованиях к [лицензированию аудита.](auditing-solutions-overview.md#advanced-audit-1)</span><span class="sxs-lookup"><span data-stu-id="42595-113">For a list of licenses that support Advanced Audit, see [Advanced Audit licensing requirements](auditing-solutions-overview.md#advanced-audit-1).</span></span>

4. <span data-ttu-id="42595-114">Разверните раздел **Приложение** и убедитесь, что установлен флажок **Расширенный аудит Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="42595-114">Expand the **Apps** section, and verify that the **Microsoft 365 Advanced Auditing** checkbox is selected.</span></span>

5. <span data-ttu-id="42595-115">Если контрольный ящик не выбран, выберите его и нажмите кнопку **Сохранить изменения.**</span><span class="sxs-lookup"><span data-stu-id="42595-115">If the checkbox isn't selected, select it, and then click **Save changes.**</span></span>

   <span data-ttu-id="42595-116">Ведение журнала записей аудита для MailItemsAccessed и Send начнется в течение 24 часов.</span><span class="sxs-lookup"><span data-stu-id="42595-116">The logging of audit records for MailItemsAccessed and Send will begin within 24 hours.</span></span> <span data-ttu-id="42595-117">Необходимо выполнить шаг 3, чтобы начать ведение журнала двух других важных событий аудита: SearchQueryInitiatedExchange и SearchQueryInitiatedSharePoint.</span><span class="sxs-lookup"><span data-stu-id="42595-117">You have to perform Step 3 to start logging of two other Advanced Audit crucial events: SearchQueryInitiatedExchange and SearchQueryInitiatedSharePoint.</span></span>

<span data-ttu-id="42595-118">Организациям, которые назначили лицензии группам пользователей с помощью группового лицензирования, нужно отключить лицензирование улучшенного аудита Microsoft 365 для этой группы.</span><span class="sxs-lookup"><span data-stu-id="42595-118">For organizations that assign licenses to groups of users by using group-based licensing, you have to turn off the licensing assignment for Microsoft 365 Advanced Auditing for the group.</span></span> <span data-ttu-id="42595-119">После сохранения изменений убедитесь в том, что для этой группы отключен улучшенный аудит Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="42595-119">After you save your changes, verify that Microsoft 365 Advanced Auditing is turned off for the group.</span></span> <span data-ttu-id="42595-120">Затем снова включите лицензирование для этой группы.</span><span class="sxs-lookup"><span data-stu-id="42595-120">Then turn the licensing assignment for the group back on.</span></span> <span data-ttu-id="42595-121">Инструкции в отношении группового лицензирования см. в статье [Назначение лицензий пользователям в соответствии с членством в группах в Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="42595-121">For instructions about group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="42595-122">Кроме того, если вы настраивали действия почтовых ящиков, которые регистрируются в почтовых ящиках пользователей или общих почтовых ящиках, любые новые важные события, выпущенные Корпорацией Майкрософт, не будут автоматически проверяться на этих почтовых ящиках.</span><span class="sxs-lookup"><span data-stu-id="42595-122">Also, if you have customized the mailbox actions that are logged on user mailboxes or shared mailboxes, any new crucial events released by Microsoft will not be automatically audited on those mailboxes.</span></span> <span data-ttu-id="42595-123">Сведения об изменении действий с почтовыми ящиками, аудит которых проводится для каждого типа входа, см. в разделе "Изменение или восстановление действий с почтовыми ящиками, зарегистрированных по умолчанию" статьи [Управление аудитом почтовых ящиков](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default).</span><span class="sxs-lookup"><span data-stu-id="42595-123">For information about changing the mailbox actions that are audited for each logon type, see the "Change or restore mailbox actions logged by default" section in [Manage mailbox auditing](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default).</span></span>

## <a name="step-2-enable-crucial-events"></a><span data-ttu-id="42595-124">Шаг 2. Включить важные события</span><span class="sxs-lookup"><span data-stu-id="42595-124">Step 2: Enable crucial events</span></span>

<span data-ttu-id="42595-125">Необходимо включить два важных события (SearchQueryInitiatedExchange и SearchQueryInitiatedSharePoint) для входа в систему при выполнении пользователями поиска в Exchange Online и SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="42595-125">You have to enable two crucial events (SearchQueryInitiatedExchange and SearchQueryInitiatedSharePoint) to be logged when users perform searches in Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="42595-126">Чтобы обеспечить аудит этих двух событий для пользователей, запустите следующую команду (для каждого пользователя) [в Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="42595-126">To enable these two events to be audited for users, run the following command (for each user) in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```powershell
Set-Mailbox <user> -AuditOwner @{Add="SearchQueryInitiated"}
```

<span data-ttu-id="42595-127">В среде с несколькими географическими условиями необходимо выполнить предыдущую команду **Set-Mailbox** в лесу, где находится почтовый ящик пользователя.</span><span class="sxs-lookup"><span data-stu-id="42595-127">In a multi-geo environment, you must run the previous **Set-Mailbox** command in the forest where the user's mailbox is located.</span></span> <span data-ttu-id="42595-128">Чтобы определить расположение почтового ящика пользователя, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="42595-128">To identify the user's mailbox location, run the following command:</span></span> 

```powershell
Get-Mailbox <user identity> | FL MailboxLocations
```

<span data-ttu-id="42595-129">Если команда для обеспечения аудита поисковых запросов ранее запускалась в лесу, который отличается от того, в котором находится почтовый ящик пользователя, необходимо удалить значение SearchQueryInitiated из почтового ящика пользователя, запущенное, а затем добавить его в почтовый ящик пользователя в лесу, где находится почтовый ящик `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` пользователя.</span><span class="sxs-lookup"><span data-stu-id="42595-129">If the command to enable the auditing of search queries was previously run in a forest that's different than the one the user's mailbox is located in, then you must remove the SearchQueryInitiated value from the user's mailbox by running `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` and then add it to the user's mailbox in the forest where the user's mailbox is located.</span></span>

## <a name="step-3-set-up-audit-retention-policies"></a><span data-ttu-id="42595-130">Шаг 3. Настройка политик хранения аудита</span><span class="sxs-lookup"><span data-stu-id="42595-130">Step 3: Set up audit retention policies</span></span>

<span data-ttu-id="42595-131">Кроме политики по умолчанию, в соответствии с которой записи аудита в Exchange, SharePoint и Azure AD хранятся в течение одного года, можно создать дополнительные политики хранения журнала аудита в соответствии с требованиями службы безопасности организации, ИТ-команды и группы по обеспечению соответствия.</span><span class="sxs-lookup"><span data-stu-id="42595-131">In additional to the default policy that retains Exchange, SharePoint, and Azure AD audit records for one year, you can create additional audit log retention policies to meet the requirements of your organization's security operations, IT, and compliance teams.</span></span> <span data-ttu-id="42595-132">Дополнительные сведения см. в статье [Управление политиками хранения журнала аудита](audit-log-retention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="42595-132">For more information, see [Manage audit log retention policies](audit-log-retention-policies.md).</span></span>

## <a name="step-4-search-for-crucial-events"></a><span data-ttu-id="42595-133">Шаг 4. Поиск важных событий</span><span class="sxs-lookup"><span data-stu-id="42595-133">Step 4: Search for crucial events</span></span>

<span data-ttu-id="42595-134">Теперь, когда для организации установлен расширенный аудит, при проведении судебно-медицинских исследований можно искать важные события и другие действия.</span><span class="sxs-lookup"><span data-stu-id="42595-134">Now that you have Advanced Audit set up for your organization, you can search for crucial events and other activities when conducting forensic investigations.</span></span> <span data-ttu-id="42595-135">После завершения 1-го и 2-го этапов можно искать журнал аудита для важных событий и других действий во время судебно-медицинских исследований скомпрометированных учетных записей и других типов расследований безопасности или соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="42595-135">After completing Step 1 and Step 2, you can search the audit log for crucial events and other activities during forensic investigations of compromised accounts and other types of security or compliance investigations.</span></span> <span data-ttu-id="42595-136">Дополнительные сведения о проведении судебно-медицинской экспертизы скомпрометированных учетных записей [](mailitemsaccessed-forensics-investigations.md)пользователей с помощью важного события MailItemsAccessed см. в этой версии.</span><span class="sxs-lookup"><span data-stu-id="42595-136">For more information about conducting a forensics investigation of compromised user accounts by using the MailItemsAccessed crucial event, see [Use Advanced Audit to investigate compromised accounts](mailitemsaccessed-forensics-investigations.md).</span></span>
