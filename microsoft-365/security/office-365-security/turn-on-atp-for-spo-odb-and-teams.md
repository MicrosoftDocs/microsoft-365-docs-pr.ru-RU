---
title: 'Включение Office 365 ATP: SharePoint, OneDrive & Teams'
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Узнайте, как включить ATP для SharePoint, OneDrive и Teams, включая настройку оповещений для обнаруженных файлов.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1cd345ae74b81c23f92b9e9b7d712efa8b875503
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326909"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="43aa7-103">Включить ATP для SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="43aa7-103">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="43aa7-104">Office 365 Advanced Threat protection (ATP) для SharePoint, OneDrive и Microsoft Teams защищает организацию от случайного предоставления вредоносных файлов.</span><span class="sxs-lookup"><span data-stu-id="43aa7-104">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="43aa7-105">Для получения дополнительных сведений ознакомьтесь [со статьей ATP для SharePoint, OneDrive и Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="43aa7-105">For more information, see [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="43aa7-106">В этой статье описывается включение и настройка ATP для SharePoint, OneDrive и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="43aa7-106">This article contains the steps for enabling and configuring ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="43aa7-107">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="43aa7-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="43aa7-108">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="43aa7-108">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="43aa7-109">Чтобы перейти непосредственно к странице **безопасных вложений ATP** , откройте <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="43aa7-109">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="43aa7-110">Чтобы включить ATP для SharePoint, OneDrive и Microsoft Teams, необходимо быть участником группы ролей " **Управление организацией** " или " **администратор безопасности** " в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="43aa7-110">To turn on ATP for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="43aa7-111">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="43aa7-111">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="43aa7-112">Чтобы запретить пользователям загружать вредоносные файлы с помощью PowerShell из SharePoint Online, необходимо быть участником роли [глобального администратора](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) или [администратора SharePoint](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="43aa7-112">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="43aa7-113">Убедитесь, что ведение журнала аудита включено для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="43aa7-113">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="43aa7-114">Дополнительные сведения см. в статье [Включение и отключение поиска в журнале аудита](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="43aa7-114">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="43aa7-115">Дождитесь вступления параметров в силу до 30 минут.</span><span class="sxs-lookup"><span data-stu-id="43aa7-115">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-security--compliance-center-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="43aa7-116">Шаг 1: воспользуйтесь центром безопасности & соответствия требованиям, чтобы включить ATP для SharePoint, OneDrive и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="43aa7-116">Step 1: Use the Security & Compliance Center to turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="43aa7-117">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** : \> **Policy** \> **безопасные вложения ATP**и щелкните **глобальные параметры**.</span><span class="sxs-lookup"><span data-stu-id="43aa7-117">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and click **Global settings**.</span></span>

2. <span data-ttu-id="43aa7-118">В открывшемся окне **глобальные параметры** перейдите к параметру **включить ATP для SharePoint, OneDrive и Microsoft Teams** .</span><span class="sxs-lookup"><span data-stu-id="43aa7-118">In the **Global settings** fly out that appears, go to the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span> <span data-ttu-id="43aa7-119">Установите переключатель вправо, ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) чтобы включить ATP для SharePoint, OneDrive и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="43aa7-119">Move the toggle to the right ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) to turn on ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="43aa7-120">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="43aa7-120">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="43aa7-121">Включение ATP для SharePoint, OneDrive и Microsoft Teams с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="43aa7-121">Use Exchange Online PowerShell to turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="43aa7-122">Если вы предпочитаете использовать PowerShell, чтобы включить ATP для SharePoint, OneDrive и Microsoft Teams, [подключитесь к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="43aa7-122">If you'd rather use PowerShell to turn on ATP for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="43aa7-123">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="43aa7-123">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="43aa7-124">Шаг 2: (рекомендуется) используйте PowerShell из SharePoint Online, чтобы запретить пользователям скачивать вредоносные файлы</span><span class="sxs-lookup"><span data-stu-id="43aa7-124">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="43aa7-125">По умолчанию пользователи не могут открывать, перемещать, копировать и совместно использовать вредоносные файлы, обнаруженные ATP.</span><span class="sxs-lookup"><span data-stu-id="43aa7-125">By default, users can't open, move, copy, or share malicious files that are detected by ATP.</span></span> <span data-ttu-id="43aa7-126">Тем не менее, они могут удалять и загружать вредоносные файлы.</span><span class="sxs-lookup"><span data-stu-id="43aa7-126">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="43aa7-127">Чтобы запретить пользователям скачивать вредоносные файлы, [подключитесь к SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="43aa7-127">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="43aa7-128">**Примечания.**</span><span class="sxs-lookup"><span data-stu-id="43aa7-128">**Notes**:</span></span>

- <span data-ttu-id="43aa7-129">Этот параметр влияет на пользователей и администраторов.</span><span class="sxs-lookup"><span data-stu-id="43aa7-129">This setting affects both users and admins.</span></span>
- <span data-ttu-id="43aa7-130">Пользователи по-прежнему могут удалить вредоносные файлы.</span><span class="sxs-lookup"><span data-stu-id="43aa7-130">People can still delete malicious files.</span></span>

<span data-ttu-id="43aa7-131">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="43aa7-131">For detailed syntax and parameter information, see [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="43aa7-132">Шаг 3 (рекомендуется) использование центра безопасности & соответствия требованиям для создания политики оповещений для обнаруженных файлов</span><span class="sxs-lookup"><span data-stu-id="43aa7-132">Step 3 (Recommended) Use the Security & Compliance Center to create an alert policy for detected files</span></span>

<span data-ttu-id="43aa7-133">Вы можете создать политику оповещений, которая сообщит вам и другим администраторам, когда ATP для SharePoint, OneDrive и Microsoft Teams обнаружит вредоносный файл.</span><span class="sxs-lookup"><span data-stu-id="43aa7-133">You can create an alert policy that notifies you and other admins when ATP for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="43aa7-134">Чтобы узнать больше об оповещениях, ознакомьтесь со статьей [Создание оповещений о действиях в центре безопасности & соответствия требованиям](../../compliance/create-activity-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="43aa7-134">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="43aa7-135">В [центре безопасности & соответствия требованиям](https://protection.office.com)перейдите к разделу **оповещения** о \> **политиках оповещений** или откройте окно "оповещения" <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="43aa7-135">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="43aa7-136">На странице **политики оповещений** щелкните **создать политику оповещений**.</span><span class="sxs-lookup"><span data-stu-id="43aa7-136">On the **Alert policies** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="43aa7-137">Мастер **создания политики оповещений** открывается на лету. На странице " **назвать оповещение** " настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="43aa7-137">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>

   - <span data-ttu-id="43aa7-138">**Name**: введите уникальное описательное имя.</span><span class="sxs-lookup"><span data-stu-id="43aa7-138">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="43aa7-139">Например, вредоносные файлы в библиотеках.</span><span class="sxs-lookup"><span data-stu-id="43aa7-139">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="43aa7-140">**Описание**: введите необязательное описание.</span><span class="sxs-lookup"><span data-stu-id="43aa7-140">**Description**: Type an optional description.</span></span> <span data-ttu-id="43aa7-141">Например, уведомляет администраторов об обнаружении вредоносных файлов в SharePoint Online, OneDrive или Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="43aa7-141">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="43aa7-142">**Severity**: **оставьте значение по** умолчанию — "средний" или " **средний** " или " **высокий**".</span><span class="sxs-lookup"><span data-stu-id="43aa7-142">**Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.</span></span>
   - <span data-ttu-id="43aa7-143">**Выберите категорию**: выберите **Управление угрозами**.</span><span class="sxs-lookup"><span data-stu-id="43aa7-143">**Select a category**: Select **Threat management**.</span></span>

   <span data-ttu-id="43aa7-144">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="43aa7-144">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="43aa7-145">На странице " **Создание параметров оповещений** " настройте следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="43aa7-145">On the **Create alert settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="43aa7-146">**Что вы хотите оповещать?: действие**: выберите **обнаруженную вредоносную программу в файле**.</span><span class="sxs-lookup"><span data-stu-id="43aa7-146">**What do you want to alert on?: Activity is**: Select **Detected malware in file**.</span></span>
   - <span data-ttu-id="43aa7-147">**Как вы хотите инициировать оповещение?**: оставьте значение по умолчанию при **каждом соответствии действия выбранному правилу** .</span><span class="sxs-lookup"><span data-stu-id="43aa7-147">**How do you want the alert to be triggered?**: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="43aa7-148">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="43aa7-148">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="43aa7-149">На странице " **Настройка получателей** " настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="43aa7-149">On the **Set your recipients** page, configure the following settings:</span></span>

   - <span data-ttu-id="43aa7-150">**Отправлять уведомления по электронной почте**: Убедитесь, что этот параметр выбран.</span><span class="sxs-lookup"><span data-stu-id="43aa7-150">**Send email notifications**: Verify this setting is selected.</span></span> <span data-ttu-id="43aa7-151">В поле **получатели электронной почты** выберите одного или нескольких глобальных администраторов, администраторов безопасности или средств чтения безопасности, которые должны получать уведомление при обнаружении вредоносного файла.</span><span class="sxs-lookup"><span data-stu-id="43aa7-151">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="43aa7-152">**Максимальное количество ежедневных уведомлений**: оставьте значение по умолчанию **не** выбрано.</span><span class="sxs-lookup"><span data-stu-id="43aa7-152">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="43aa7-153">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="43aa7-153">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="43aa7-154">На странице " **Проверка параметров** " Проверьте параметры и нажмите кнопку **изменить** в любом из разделов, чтобы внести изменения.</span><span class="sxs-lookup"><span data-stu-id="43aa7-154">On the **Review your settings** page, review the settings, and click **Edit** in any of the sections to make changes.</span></span>

   <span data-ttu-id="43aa7-155">В разделе вы **хотите включить политику** сразу же? оставьте значение по умолчанию **Да, включить его сразу после** выбора.</span><span class="sxs-lookup"><span data-stu-id="43aa7-155">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="43aa7-156">Закончив, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="43aa7-156">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="43aa7-157">Создание политики оповещений для обнаруженных файлов с помощью PowerShell & обеспечения безопасности</span><span class="sxs-lookup"><span data-stu-id="43aa7-157">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="43aa7-158">Если вы предпочитаете использовать PowerShell, чтобы создать ту же политику оповещений, как описано в предыдущем разделе, [подключитесь к PowerShell центра безопасности & центра соответствия требованиям](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="43aa7-158">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="43aa7-159">**Note**: значение _степени серьезности_ по умолчанию — мала.</span><span class="sxs-lookup"><span data-stu-id="43aa7-159">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="43aa7-160">Чтобы указать средний или высокий уровень, включите параметр _Severity_ и значение в команду.</span><span class="sxs-lookup"><span data-stu-id="43aa7-160">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="43aa7-161">Подробные сведения о синтаксисе и параметрах можно найти в статье [New – ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).</span><span class="sxs-lookup"><span data-stu-id="43aa7-161">For detailed syntax and parameter information, see [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="43aa7-162">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="43aa7-162">How do you know these procedures worked?</span></span>

- <span data-ttu-id="43aa7-163">Чтобы убедиться, что вы успешно включили ATP для SharePoint, OneDrive и Microsoft Teams, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="43aa7-163">To verify that you've successfully turned on ATP for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="43aa7-164">В [центре безопасности & соответствия требованиям](https://protection.office.com)перейдите к разделу политика **управления угрозами** : \> **Policy** \> **безопасные вложения ATP**, выберите **глобальные параметры**и проверьте значение параметра **включить ATP для SharePoint, OneDrive и Microsoft Teams** .</span><span class="sxs-lookup"><span data-stu-id="43aa7-164">In the [Security & Compliance Center](https://protection.office.com), go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, select **Global settings**, and verify the value of the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="43aa7-165">В Exchange Online PowerShell выполните следующую команду, чтобы проверить значение свойства:</span><span class="sxs-lookup"><span data-stu-id="43aa7-165">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="43aa7-166">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="43aa7-166">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="43aa7-167">Чтобы убедиться, что пользователи успешно заблокировали загрузку вредоносных файлов, Откройте SharePoint Online PowerShell и выполните следующую команду, чтобы проверить значение свойства:</span><span class="sxs-lookup"><span data-stu-id="43aa7-167">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="43aa7-168">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="43aa7-168">For detailed syntax and parameter information, see [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="43aa7-169">Чтобы убедиться, что вы успешно настроили политику оповещений для обнаруженных файлов, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="43aa7-169">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>

  - <span data-ttu-id="43aa7-170">В центре безопасности & соответствия требованиям перейдите к разделу **оповещения** о политиках оповещений \> **Alert policies** \> , выберите политику оповещений и проверьте параметры.</span><span class="sxs-lookup"><span data-stu-id="43aa7-170">In the Security & Compliance Center, go to **Alerts** \> **Alert policies** \> select the alert policy, and verify the settings.</span></span>

  - <span data-ttu-id="43aa7-171">В PowerShell центра безопасности & соответствия требованиям замените \<AlertPolicyName\> имя политики оповещений, выполните следующую команду и проверьте значения свойств:</span><span class="sxs-lookup"><span data-stu-id="43aa7-171">In Security & Compliance Center PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="43aa7-172">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).</span><span class="sxs-lookup"><span data-stu-id="43aa7-172">For detailed syntax and parameter information, see [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="43aa7-173">Используйте [отчет о состоянии защиты от угроз](view-email-security-reports.md#threat-protection-status-report) для просмотра сведений об обнаруженных файлах в SharePoint, OneDrive и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="43aa7-173">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="43aa7-174">В частности, вы можете использовать представление " **Просмотр данных: контент \> от вредоносных программ** ".</span><span class="sxs-lookup"><span data-stu-id="43aa7-174">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
