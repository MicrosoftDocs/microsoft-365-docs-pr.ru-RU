---
title: Включение безопасных вложений для SharePoint, OneDrive и Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Администраторы могут узнать, как включить безопасные вложения для SharePoint, OneDrive и Microsoft Teams, включая набор оповещений для обнаруженных файлов.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 300cb3e004010e8ff22de7393d3f3e039bf8cfdd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921148"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="930dd-103">Включение безопасных вложений для SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="930dd-103">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="930dd-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="930dd-104">**Applies to**</span></span>
- [<span data-ttu-id="930dd-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="930dd-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="930dd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="930dd-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="930dd-107">Microsoft Defender для Office 365 для SharePoint, OneDrive и Microsoft Teams защищает организацию от непреднамеренного обмена вредоносными файлами.</span><span class="sxs-lookup"><span data-stu-id="930dd-107">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="930dd-108">Дополнительные сведения см. в [разделЕ Безопасные вложения для SharePoint, OneDrive и Microsoft Teams.](atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="930dd-108">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="930dd-109">В этой статье содержатся действия для включения и настройки безопасных вложений для SharePoint, OneDrive и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="930dd-109">This article contains the steps for enabling and configuring Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="930dd-110">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="930dd-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="930dd-111">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="930dd-111">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="930dd-112">Чтобы перейти непосредственно на страницу БЕЗОПАСНЫЕ вложения **ATP,** откройте <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="930dd-112">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="930dd-113">Чтобы включить безопасные вложения для SharePoint, OneDrive и Microsoft Teams,  необходимо  быть членом групп ролей управления организацией или администратора безопасности в Центре & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="930dd-113">To turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="930dd-114">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="930dd-114">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="930dd-115">Чтобы использовать SharePoint Online PowerShell для предотвращения скачивания вредоносных [](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) файлов, необходимо быть членом роли глобального администратора или администратора [SharePoint](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="930dd-115">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="930dd-116">Убедитесь, что журнал аудита включен для организации.</span><span class="sxs-lookup"><span data-stu-id="930dd-116">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="930dd-117">Дополнительные сведения см. в статье [Включение и отключение поиска в журнале аудита](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="930dd-117">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="930dd-118">Разрешить до 30 минут, чтобы параметры вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="930dd-118">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-security--compliance-center-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="930dd-119">Шаг 1. Использование Центра & безопасности для вложения в SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="930dd-119">Step 1: Use the Security & Compliance Center to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="930dd-120">В Центре & безопасности перейдите к  политике управления угрозами \>  \> **ATP Safe Attachments** и щелкните **глобальные параметры.**</span><span class="sxs-lookup"><span data-stu-id="930dd-120">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and click **Global settings**.</span></span>

2. <span data-ttu-id="930dd-121">В глобальных **параметрах,** которые появляются, перейдите к параметру **Turn on Defender для Office 365 для SharePoint, OneDrive и Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="930dd-121">In the **Global settings** fly out that appears, go to the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span> <span data-ttu-id="930dd-122">Переместите окантовку вправо, чтобы включить безопасные вложения ![ ](../../media/scc-toggle-on.png) для SharePoint, OneDrive и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="930dd-122">Move the toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="930dd-123">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="930dd-123">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="930dd-124">Используйте PowerShell Exchange Online, чтобы включить безопасные вложения для SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="930dd-124">Use Exchange Online PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="930dd-125">Если вы хотите использовать [PowerShell,](/powershell/exchange/connect-to-exchange-online-powershell) чтобы включить безопасные вложения для SharePoint, OneDrive и Microsoft Teams, подключитесь к Exchange Online PowerShell и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="930dd-125">If you'd rather use PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="930dd-126">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-AtpPolicyForO365.](/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="930dd-126">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="930dd-127">Шаг 2. (Рекомендуется) Использование SharePoint Online PowerShell для предотвращения скачивания пользователями вредоносных файлов</span><span class="sxs-lookup"><span data-stu-id="930dd-127">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="930dd-128">По умолчанию пользователи не могут открывать, перемещать, копировать или делиться вредоносными файлами, обнаруженными ATP.</span><span class="sxs-lookup"><span data-stu-id="930dd-128">By default, users can't open, move, copy, or share malicious files that are detected by ATP.</span></span> <span data-ttu-id="930dd-129">Однако они могут удалять и скачивать вредоносные файлы.</span><span class="sxs-lookup"><span data-stu-id="930dd-129">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="930dd-130">Чтобы запретить пользователям скачивать вредоносные файлы, подключитесь [к SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="930dd-130">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="930dd-131">**Примечания.**</span><span class="sxs-lookup"><span data-stu-id="930dd-131">**Notes**:</span></span>

- <span data-ttu-id="930dd-132">Этот параметр влияет как на пользователей, так и на администраторов.</span><span class="sxs-lookup"><span data-stu-id="930dd-132">This setting affects both users and admins.</span></span>
- <span data-ttu-id="930dd-133">Люди по-прежнему могут удалять вредоносные файлы.</span><span class="sxs-lookup"><span data-stu-id="930dd-133">People can still delete malicious files.</span></span>

<span data-ttu-id="930dd-134">Подробные сведения о синтаксисах и параметрах см. [в инструкции Set-SPOTenant.](/powershell/module/sharepoint-online/Set-SPOTenant)</span><span class="sxs-lookup"><span data-stu-id="930dd-134">For detailed syntax and parameter information, see [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="930dd-135">Шаг 3 (Рекомендуется) Использование Центра & безопасности для создания политики оповещения для обнаруженных файлов</span><span class="sxs-lookup"><span data-stu-id="930dd-135">Step 3 (Recommended) Use the Security & Compliance Center to create an alert policy for detected files</span></span>

<span data-ttu-id="930dd-136">Вы можете создать политику оповещения, которая оповещает вас и других администраторов, когда безопасные вложения для SharePoint, OneDrive и Microsoft Teams обнаруживают вредоносный файл.</span><span class="sxs-lookup"><span data-stu-id="930dd-136">You can create an alert policy that notifies you and other admins when Safe Attachments for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="930dd-137">Дополнительные дополнительные информацию о оповещениях см. в центре Создания оповещений о действиях в центре [& безопасности.](../../compliance/create-activity-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="930dd-137">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="930dd-138">В Центре [& безопасности](https://protection.office.com)перейдите к политикам **оповещения** оповещений или \>  откройте <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="930dd-138">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="930dd-139">На странице **Политики оповещения** нажмите кнопку Новая **политика оповещения**.</span><span class="sxs-lookup"><span data-stu-id="930dd-139">On the **Alert policies** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="930dd-140">Мастер **политики оповещения открывается** при вылете. На странице **Имя оповещений** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="930dd-140">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>

   - <span data-ttu-id="930dd-141">**Имя.** Введите уникальное и описательное имя.</span><span class="sxs-lookup"><span data-stu-id="930dd-141">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="930dd-142">Например, вредоносные файлы в библиотеках.</span><span class="sxs-lookup"><span data-stu-id="930dd-142">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="930dd-143">**Описание.** Введите необязательное описание.</span><span class="sxs-lookup"><span data-stu-id="930dd-143">**Description**: Type an optional description.</span></span> <span data-ttu-id="930dd-144">Например, сообщает администраторам, когда вредоносные файлы обнаруживаются в SharePoint Online, OneDrive или Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="930dd-144">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="930dd-145">**Серьезность.** Оставьте значение **Low** выбранное по умолчанию или выберите **Medium** или **High**.</span><span class="sxs-lookup"><span data-stu-id="930dd-145">**Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.</span></span>
   - <span data-ttu-id="930dd-146">**Выберите категорию**: Выберите **управление угрозами.**</span><span class="sxs-lookup"><span data-stu-id="930dd-146">**Select a category**: Select **Threat management**.</span></span>

   <span data-ttu-id="930dd-147">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="930dd-147">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="930dd-148">На странице **Создание параметров оповещения** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="930dd-148">On the **Create alert settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="930dd-149">**Что нужно предупредить?: Действие:** Выберите **обнаруженную** вредоносную программу в файле .</span><span class="sxs-lookup"><span data-stu-id="930dd-149">**What do you want to alert on?: Activity is**: Select **Detected malware in file**.</span></span>
   - <span data-ttu-id="930dd-150">**Как срабатывает** оповещение? : Оставьте значение по умолчанию каждый раз, когда действие соответствует **выбранному** правилу.</span><span class="sxs-lookup"><span data-stu-id="930dd-150">**How do you want the alert to be triggered?**: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="930dd-151">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="930dd-151">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="930dd-152">На странице **Set your recipients** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="930dd-152">On the **Set your recipients** page, configure the following settings:</span></span>

   - <span data-ttu-id="930dd-153">**Отправка уведомлений электронной** почты. Убедитесь, что выбран этот параметр.</span><span class="sxs-lookup"><span data-stu-id="930dd-153">**Send email notifications**: Verify this setting is selected.</span></span> <span data-ttu-id="930dd-154">В поле **получателей** электронной почты выберите одного или несколько глобальных администраторов, администраторов безопасности или читателей безопасности, которые должны получать уведомления при обнаружении вредоносного файла.</span><span class="sxs-lookup"><span data-stu-id="930dd-154">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="930dd-155">**Дневное ограничение** уведомлений. Оставьте выбранное **значение без ограничения** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="930dd-155">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="930dd-156">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="930dd-156">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="930dd-157">На странице **Обзор параметров** просмотрите параметры и нажмите **кнопку Изменить** в любом из разделов, чтобы внести изменения.</span><span class="sxs-lookup"><span data-stu-id="930dd-157">On the **Review your settings** page, review the settings, and click **Edit** in any of the sections to make changes.</span></span>

   <span data-ttu-id="930dd-158">В разделе Вы хотите включить политику **сразу?** оставьте значение **Да,** включив ее сразу же выбранной.</span><span class="sxs-lookup"><span data-stu-id="930dd-158">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="930dd-159">Закончив, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="930dd-159">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="930dd-160">Используйте службу & powerShell для создания политики оповещения для обнаруженных файлов</span><span class="sxs-lookup"><span data-stu-id="930dd-160">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="930dd-161">Если вы хотите использовать PowerShell для создания той же политики оповещений, что и в предыдущем разделе, подключись к центру обеспечения безопасности [& PowerShell](/powershell/exchange/connect-to-scc-powershell) и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="930dd-161">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="930dd-162">**Примечание.** Значение _серьезности по умолчанию_ является низким.</span><span class="sxs-lookup"><span data-stu-id="930dd-162">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="930dd-163">Чтобы указать Medium или High, включай параметр _Severity_ и значение в команду.</span><span class="sxs-lookup"><span data-stu-id="930dd-163">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="930dd-164">Подробные сведения о синтаксисах и параметрах см. [в обзоре New-ActivityAlert.](/powershell/module/exchange/new-activityalert)</span><span class="sxs-lookup"><span data-stu-id="930dd-164">For detailed syntax and parameter information, see [New-ActivityAlert](/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="930dd-165">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="930dd-165">How do you know these procedures worked?</span></span>

- <span data-ttu-id="930dd-166">Чтобы убедиться, что вы успешно включили безопасные вложения для SharePoint, OneDrive и Microsoft Teams, используйте один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="930dd-166">To verify that you've successfully turned on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="930dd-167">В Центре обеспечения [&](https://protection.office.com)безопасности перейдите  к политике управления угрозами ATP Safe Attachments, выберите глобальные параметры и проверьте значение параметра Turn \>  \> on Defender для **Office 365 для SharePoint, OneDrive** и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="930dd-167">In the [Security & Compliance Center](https://protection.office.com), go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, select **Global settings**, and verify the value of the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="930dd-168">В Exchange Online PowerShell запустите следующую команду, чтобы проверить параметр свойства:</span><span class="sxs-lookup"><span data-stu-id="930dd-168">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="930dd-169">Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-AtpPolicyForO365.](/powershell/module/exchange/get-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="930dd-169">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="930dd-170">Чтобы убедиться, что вы успешно заблокировали загрузку вредоносных файлов, откройте SharePoint Online PowerShell и запустите следующую команду, чтобы проверить значение свойства:</span><span class="sxs-lookup"><span data-stu-id="930dd-170">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="930dd-171">Подробные сведения о синтаксисах и параметрах см. [в обзоре Get-SPOTenant.](/powershell/module/sharepoint-online/Set-SPOTenant)</span><span class="sxs-lookup"><span data-stu-id="930dd-171">For detailed syntax and parameter information, see [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="930dd-172">Чтобы убедиться, что вы успешно настроили политику оповещения для обнаруженных файлов, используйте любой из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="930dd-172">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>

  - <span data-ttu-id="930dd-173">В Центре & безопасности перейдите к политикам **оповещения** оповещений, выберите политику оповещения и проверьте \>  \> параметры.</span><span class="sxs-lookup"><span data-stu-id="930dd-173">In the Security & Compliance Center, go to **Alerts** \> **Alert policies** \> select the alert policy, and verify the settings.</span></span>

  - <span data-ttu-id="930dd-174">В центре & безопасности PowerShell замените имя политики оповещения, запустите следующую команду и проверьте \<AlertPolicyName\> значения свойств:</span><span class="sxs-lookup"><span data-stu-id="930dd-174">In Security & Compliance Center PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="930dd-175">Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-ActivityAlert.](/powershell/module/exchange/get-activityalert)</span><span class="sxs-lookup"><span data-stu-id="930dd-175">For detailed syntax and parameter information, see [Get-ActivityAlert](/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="930dd-176">Используйте отчет [о состоянии защиты от угроз,](view-email-security-reports.md#threat-protection-status-report) чтобы просмотреть сведения о обнаруженных файлах в SharePoint, OneDrive и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="930dd-176">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="930dd-177">В частности, вы можете использовать **данные View по: Просмотр \> вредоносных программ** контента.</span><span class="sxs-lookup"><span data-stu-id="930dd-177">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>