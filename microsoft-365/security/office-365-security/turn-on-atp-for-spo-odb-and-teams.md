---
title: 'Включить Microsoft Defender для Office 365 : SharePoint, OneDrive, & Teams'
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Узнайте, как включить ATP для SharePoint, OneDrive и Teams, включая настройка оповещений для обнаруженных файлов.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 44d487810156d5de5ae152e08040e8dccd2a4ee0
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682599"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="bf0cf-103">Включение ATP для SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bf0cf-103">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bf0cf-104">Microsoft Defender для Office 365 для SharePoint, OneDrive и Microsoft Teams защищает организацию от случайного совместного использования вредоносных файлов.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-104">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="bf0cf-105">Дополнительные сведения см. в [atP для SharePoint, OneDrive и Microsoft Teams.](atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="bf0cf-105">For more information, see [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="bf0cf-106">В этой статье представлены действия по включаю и настройке ATP для SharePoint, OneDrive и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-106">This article contains the steps for enabling and configuring ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bf0cf-107">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="bf0cf-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bf0cf-108">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-108">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="bf0cf-109">Чтобы перейти непосредственно на страницу безопасных **вложений ATP,** откройте <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="bf0cf-109">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="bf0cf-110">Чтобы включить ATP для SharePoint, OneDrive и Microsoft Teams, необходимо  быть  членом группы ролей "Управление организацией" или "Администратор безопасности" в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-110">To turn on ATP for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="bf0cf-111">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="bf0cf-111">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="bf0cf-112">Чтобы запретить скачивание вредоносных файлов с помощью SharePoint Online PowerShell, необходимо быть участником ролей глобального администратора или администратора [SharePoint](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) в Azure AD. [](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator)</span><span class="sxs-lookup"><span data-stu-id="bf0cf-112">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="bf0cf-113">Убедитесь, что ведение журнала аудита включено для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-113">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="bf0cf-114">Дополнительные сведения см. в статье [Включение и отключение поиска в журнале аудита](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="bf0cf-114">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="bf0cf-115">Чтобы параметры вступили в силу, в течение 30 минут.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-115">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-security--compliance-center-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="bf0cf-116">Шаг 1. В Центре безопасности & соответствия требованиям включит ATP для SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bf0cf-116">Step 1: Use the Security & Compliance Center to turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="bf0cf-117">В Центре безопасности & соответствия требованиям  перейдите в центр безопасных вложений ATP политики управления угрозами и щелкните \>  \>  **"Глобальные параметры".**</span><span class="sxs-lookup"><span data-stu-id="bf0cf-117">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and click **Global settings**.</span></span>

2. <span data-ttu-id="bf0cf-118">In the **Global settings** fly out that appears, go to the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** setting.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-118">In the **Global settings** fly out that appears, go to the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span> <span data-ttu-id="bf0cf-119">Переместите выключатель вправо, чтобы включить ATP для ![ ](../../media/scc-toggle-on.png) SharePoint, OneDrive и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-119">Move the toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="bf0cf-120">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-120">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="bf0cf-121">Использование Exchange Online PowerShell для включить ATP для SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bf0cf-121">Use Exchange Online PowerShell to turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="bf0cf-122">Если вы хотите включить ATP для SharePoint, OneDrive и Microsoft Teams с помощью [PowerShell,](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) подключитесь к Exchange Online PowerShell и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bf0cf-122">If you'd rather use PowerShell to turn on ATP for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="bf0cf-123">Подробные сведения о синтаксис и параметрах см. в описании [Set-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="bf0cf-123">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="bf0cf-124">Шаг 2. (Рекомендуется) Использование SharePoint Online PowerShell для предотвращения загрузки пользователями вредоносных файлов</span><span class="sxs-lookup"><span data-stu-id="bf0cf-124">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="bf0cf-125">По умолчанию пользователи не могут открывать, перемещать, копировать или совместно использовать вредоносные файлы, обнаруженные ATP.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-125">By default, users can't open, move, copy, or share malicious files that are detected by ATP.</span></span> <span data-ttu-id="bf0cf-126">Однако они могут удалять и скачивать вредоносные файлы.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-126">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="bf0cf-127">Чтобы запретить пользователям скачивать вредоносные файлы, подключитесь [к SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bf0cf-127">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="bf0cf-128">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="bf0cf-128">**Notes**:</span></span>

- <span data-ttu-id="bf0cf-129">Этот параметр влияет как на пользователей, так и на администраторов.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-129">This setting affects both users and admins.</span></span>
- <span data-ttu-id="bf0cf-130">Злоумышленники по-прежнему могут удалять вредоносные файлы.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-130">People can still delete malicious files.</span></span>

<span data-ttu-id="bf0cf-131">Подробные сведения о синтаксисах и параметрах см. в [описании Set-SPOTenant.](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)</span><span class="sxs-lookup"><span data-stu-id="bf0cf-131">For detailed syntax and parameter information, see [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="bf0cf-132">Шаг 3 (рекомендуется) Создание политики оповещений для обнаруженных файлов с помощью Центра безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="bf0cf-132">Step 3 (Recommended) Use the Security & Compliance Center to create an alert policy for detected files</span></span>

<span data-ttu-id="bf0cf-133">Вы можете создать политику оповещений, которая оповещает вас и других администраторов о том, что ATP для SharePoint, OneDrive и Microsoft Teams обнаруживает вредоносный файл.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-133">You can create an alert policy that notifies you and other admins when ATP for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="bf0cf-134">Дополнительные информацию об оповещениях см. в центре безопасности [и & соответствия требованиям.](../../compliance/create-activity-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="bf0cf-134">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="bf0cf-135">В Центре [безопасности & соответствия](https://protection.office.com)требованиям  перейдите к политикам оповещений \> **или** откройте <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="bf0cf-135">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="bf0cf-136">На странице **"Политики оповещений"** щелкните **"Новая политика оповещений".**</span><span class="sxs-lookup"><span data-stu-id="bf0cf-136">On the **Alert policies** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="bf0cf-137">Откроется **мастер новой политики** оповещений. На странице **"Назовите оповещение"** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="bf0cf-137">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>

   - <span data-ttu-id="bf0cf-138">**Имя:** введите уникальное и описательное имя.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-138">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="bf0cf-139">Например, вредоносные файлы в библиотеках.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-139">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="bf0cf-140">**Описание:** введите необязательное описание.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-140">**Description**: Type an optional description.</span></span> <span data-ttu-id="bf0cf-141">Например, он сообщает администраторам об обнаружении вредоносных файлов в SharePoint Online, OneDrive или Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-141">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="bf0cf-142">**Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-142">**Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.</span></span>
   - <span data-ttu-id="bf0cf-143">**Выберите категорию**: выберите **управление угрозами.**</span><span class="sxs-lookup"><span data-stu-id="bf0cf-143">**Select a category**: Select **Threat management**.</span></span>

   <span data-ttu-id="bf0cf-144">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-144">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="bf0cf-145">На странице **"Создание параметров оповещений"** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="bf0cf-145">On the **Create alert settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="bf0cf-146">**Что нужно оповещать?: Действие:** выберите **обнаруженную вредоносную программу в файле.**</span><span class="sxs-lookup"><span data-stu-id="bf0cf-146">**What do you want to alert on?: Activity is**: Select **Detected malware in file**.</span></span>
   - <span data-ttu-id="bf0cf-147">**Как следует запускать** оповещение? Оставьте значение по умолчанию каждый раз, когда действие соответствует **выбранному правилу.**</span><span class="sxs-lookup"><span data-stu-id="bf0cf-147">**How do you want the alert to be triggered?**: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="bf0cf-148">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-148">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="bf0cf-149">На странице **"Настройка получателей"** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="bf0cf-149">On the **Set your recipients** page, configure the following settings:</span></span>

   - <span data-ttu-id="bf0cf-150">**Отправка уведомлений по электронной** почте: убедитесь, что этот параметр выбран.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-150">**Send email notifications**: Verify this setting is selected.</span></span> <span data-ttu-id="bf0cf-151">В поле **получателей** электронной почты выберите одного или несколько глобальных администраторов, администраторов безопасности или читателей безопасности, которые должны получать уведомления при обнаружении вредоносного файла.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-151">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="bf0cf-152">**Ограничение на количество уведомлений за** день: оставьте значение по умолчанию **без** ограничения.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-152">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="bf0cf-153">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-153">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="bf0cf-154">На странице **"Просмотр параметров"** просмотрите параметры и нажмите кнопку **"Изменить"** в любом из разделов, чтобы внести изменения.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-154">On the **Review your settings** page, review the settings, and click **Edit** in any of the sections to make changes.</span></span>

   <span data-ttu-id="bf0cf-155">В разделе "Включить политику **сразу?",** оставьте значение по умолчанию **"Да",** включив его сразу же.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-155">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="bf0cf-156">Закончив, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-156">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="bf0cf-157">Использование PowerShell & безопасности для обеспечения соответствия требованиям для создания политики оповещений для обнаруженных файлов</span><span class="sxs-lookup"><span data-stu-id="bf0cf-157">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="bf0cf-158">Если вы хотите использовать PowerShell для создания той же политики оповещений, которая описана в предыдущем разделе, подключите к [PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) Центра безопасности & соответствия требованиям и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bf0cf-158">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="bf0cf-159">**Примечание.** Значение _серьезности по_ умолчанию — Low.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-159">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="bf0cf-160">Чтобы указать значение Medium или High, включив в команду параметр _Severity_ и его значение.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-160">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="bf0cf-161">Подробные сведения о синтаксисах и параметрах см. в описании [New-ActivityAlert.](https://docs.microsoft.com/powershell/module/exchange/new-activityalert)</span><span class="sxs-lookup"><span data-stu-id="bf0cf-161">For detailed syntax and parameter information, see [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="bf0cf-162">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="bf0cf-162">How do you know these procedures worked?</span></span>

- <span data-ttu-id="bf0cf-163">Чтобы убедиться, что вы успешно включили ATP для SharePoint, OneDrive и Microsoft Teams, используйте одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="bf0cf-163">To verify that you've successfully turned on ATP for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="bf0cf-164">In the [Security & Compliance Center,](https://protection.office.com)go to **Threat management** \> **Policy** \> **ATP Safe Attachments,** select **Global settings**, and verify the value of the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** setting.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-164">In the [Security & Compliance Center](https://protection.office.com), go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, select **Global settings**, and verify the value of the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="bf0cf-165">В Exchange Online PowerShell запустите следующую команду, чтобы проверить параметр свойства:</span><span class="sxs-lookup"><span data-stu-id="bf0cf-165">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="bf0cf-166">Подробные сведения о синтаксисах и параметрах см. в описании [get-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="bf0cf-166">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="bf0cf-167">Чтобы убедиться, что вы успешно заблокировали загрузку вредоносных файлов, откройте SharePoint Online PowerShell и запустите следующую команду, чтобы проверить значение свойства:</span><span class="sxs-lookup"><span data-stu-id="bf0cf-167">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="bf0cf-168">Подробные сведения о синтаксисах и параметрах см. в описании [Get-SPOTenant.](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)</span><span class="sxs-lookup"><span data-stu-id="bf0cf-168">For detailed syntax and parameter information, see [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="bf0cf-169">Чтобы убедиться, что вы успешно настроили политику оповещений для обнаруженных файлов, с помощью любого из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="bf0cf-169">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>

  - <span data-ttu-id="bf0cf-170">В Центре безопасности & соответствия требованиям  перейдите к политикам оповещений, выберите политику оповещений и проверьте \>  \> параметры.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-170">In the Security & Compliance Center, go to **Alerts** \> **Alert policies** \> select the alert policy, and verify the settings.</span></span>

  - <span data-ttu-id="bf0cf-171">В PowerShell Центра & безопасности замените имя политики оповещений, запустите следующую команду и проверьте \<AlertPolicyName\> значения свойств:</span><span class="sxs-lookup"><span data-stu-id="bf0cf-171">In Security & Compliance Center PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="bf0cf-172">Подробные сведения о синтаксисах и параметрах см. в описании [get-ActivityAlert.](https://docs.microsoft.com/powershell/module/exchange/get-activityalert)</span><span class="sxs-lookup"><span data-stu-id="bf0cf-172">For detailed syntax and parameter information, see [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="bf0cf-173">Используйте отчет [о состоянии защиты от угроз для](view-email-security-reports.md#threat-protection-status-report) просмотра сведений об обнаруженных файлах в SharePoint, OneDrive и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bf0cf-173">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="bf0cf-174">В частности, можно использовать данные просмотра: **представление "Вредоносные \> программы для** содержимого".</span><span class="sxs-lookup"><span data-stu-id="bf0cf-174">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
