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
description: Администраторы могут узнать, как включить безопасные вложения для SharePoint, OneDrive и Microsoft Teams, включая настройка оповещений для обнаруженных файлов.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9688af82d194b1818d6bd3323d39bde51db20cb2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286373"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="f1a49-103">Включение безопасных вложений для SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f1a49-103">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f1a49-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="f1a49-104">**Applies to**</span></span>
- [<span data-ttu-id="f1a49-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="f1a49-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="f1a49-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f1a49-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="f1a49-107">Microsoft Defender для Office 365 для SharePoint, OneDrive и Microsoft Teams защищает организацию от случайного совместного использования вредоносных файлов.</span><span class="sxs-lookup"><span data-stu-id="f1a49-107">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="f1a49-108">Дополнительные сведения см. в записях ["Безопасные вложения" для SharePoint, OneDrive и Microsoft Teams.](atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="f1a49-108">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="f1a49-109">В этой статье содержатся действия по включаю и настройке безопасных вложений для SharePoint, OneDrive и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f1a49-109">This article contains the steps for enabling and configuring Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f1a49-110">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="f1a49-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f1a49-111">Откройте Центр безопасности и соответствия требованиям по ссылке <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="f1a49-111">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="f1a49-112">Чтобы перейти непосредственно на страницу безопасных **вложений ATP,** откройте <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="f1a49-112">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="f1a49-113">Чтобы включить функцию "Безопасные вложения" для SharePoint, OneDrive и  Microsoft  Teams, необходимо быть членом группы ролей "Управление организацией" или "Администратор безопасности" в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="f1a49-113">To turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="f1a49-114">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f1a49-114">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="f1a49-115">Чтобы запретить скачивание вредоносных файлов с помощью SharePoint Online PowerShell, необходимо быть участником ролей глобального администратора или администратора [SharePoint](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) в Azure AD. [](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator)</span><span class="sxs-lookup"><span data-stu-id="f1a49-115">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="f1a49-116">Убедитесь, что ведение журнала аудита включено для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f1a49-116">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="f1a49-117">Дополнительные сведения см. в статье [Включение и отключение поиска в журнале аудита](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="f1a49-117">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="f1a49-118">Чтобы параметры вступили в силу, в течение 30 минут.</span><span class="sxs-lookup"><span data-stu-id="f1a49-118">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-security--compliance-center-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="f1a49-119">Шаг 1. В Центре безопасности & соответствия требованиям включить безопасные вложения для SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f1a49-119">Step 1: Use the Security & Compliance Center to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="f1a49-120">В Центре безопасности & соответствия требованиям  перейдите в центр безопасных вложений ATP политики управления угрозами и щелкните \>  \>  **"Глобальные параметры".**</span><span class="sxs-lookup"><span data-stu-id="f1a49-120">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and click **Global settings**.</span></span>

2. <span data-ttu-id="f1a49-121">В **окнах** "Глобальные параметры" перейдите к параметру "Включить Защитник **для Office 365 для SharePoint, OneDrive** и Microsoft Teams".</span><span class="sxs-lookup"><span data-stu-id="f1a49-121">In the **Global settings** fly out that appears, go to the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span> <span data-ttu-id="f1a49-122">Переместите выключатель вправо, чтобы включить безопасные вложения для ![ ](../../media/scc-toggle-on.png) SharePoint, OneDrive и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f1a49-122">Move the toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="f1a49-123">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f1a49-123">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="f1a49-124">Включить безопасные вложения для SharePoint, OneDrive и Microsoft Teams с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1a49-124">Use Exchange Online PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="f1a49-125">Если вы хотите включить безопасные вложения для SharePoint, OneDrive и Microsoft Teams с помощью [PowerShell,](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) подключитесь к Exchange Online PowerShell и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f1a49-125">If you'd rather use PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="f1a49-126">Подробные сведения о синтаксис и параметрах см. в описании [Set-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="f1a49-126">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="f1a49-127">Шаг 2. (Рекомендуется) Использование SharePoint Online PowerShell для предотвращения загрузки пользователями вредоносных файлов</span><span class="sxs-lookup"><span data-stu-id="f1a49-127">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="f1a49-128">По умолчанию пользователи не могут открывать, перемещать, копировать или совместно использовать вредоносные файлы, обнаруженные ATP.</span><span class="sxs-lookup"><span data-stu-id="f1a49-128">By default, users can't open, move, copy, or share malicious files that are detected by ATP.</span></span> <span data-ttu-id="f1a49-129">Однако они могут удалять и скачивать вредоносные файлы.</span><span class="sxs-lookup"><span data-stu-id="f1a49-129">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="f1a49-130">Чтобы запретить пользователям скачивать вредоносные файлы, подключитесь [к SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f1a49-130">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="f1a49-131">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="f1a49-131">**Notes**:</span></span>

- <span data-ttu-id="f1a49-132">Этот параметр влияет как на пользователей, так и на администраторов.</span><span class="sxs-lookup"><span data-stu-id="f1a49-132">This setting affects both users and admins.</span></span>
- <span data-ttu-id="f1a49-133">Злоумышленники по-прежнему могут удалять вредоносные файлы.</span><span class="sxs-lookup"><span data-stu-id="f1a49-133">People can still delete malicious files.</span></span>

<span data-ttu-id="f1a49-134">Подробные сведения о синтаксисах и параметрах см. в [описании Set-SPOTenant.](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)</span><span class="sxs-lookup"><span data-stu-id="f1a49-134">For detailed syntax and parameter information, see [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="f1a49-135">Шаг 3 (рекомендуется) Создание политики оповещений для обнаруженных файлов с помощью Центра безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="f1a49-135">Step 3 (Recommended) Use the Security & Compliance Center to create an alert policy for detected files</span></span>

<span data-ttu-id="f1a49-136">Вы можете создать политику оповещений, которая будет оповещать вас и других администраторов о том, что безопасные вложения для SharePoint, OneDrive и Microsoft Teams обнаруживают вредоносный файл.</span><span class="sxs-lookup"><span data-stu-id="f1a49-136">You can create an alert policy that notifies you and other admins when Safe Attachments for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="f1a49-137">Дополнительные информацию об оповещениях см. в центре безопасности [& соответствия требованиям.](../../compliance/create-activity-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="f1a49-137">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="f1a49-138">В Центре [безопасности & соответствия](https://protection.office.com)требованиям  перейдите к политикам оповещений \> **или** откройте <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="f1a49-138">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="f1a49-139">На странице **"Политики оповещений"** щелкните **"Новая политика оповещений".**</span><span class="sxs-lookup"><span data-stu-id="f1a49-139">On the **Alert policies** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="f1a49-140">Мастер **новой политики оповещений** откроется во время вылета. На странице **"Назовите оповещение"** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f1a49-140">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>

   - <span data-ttu-id="f1a49-141">**Имя:** введите уникальное и описательное имя.</span><span class="sxs-lookup"><span data-stu-id="f1a49-141">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="f1a49-142">Например, вредоносные файлы в библиотеках.</span><span class="sxs-lookup"><span data-stu-id="f1a49-142">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="f1a49-143">**Описание:** введите необязательное описание.</span><span class="sxs-lookup"><span data-stu-id="f1a49-143">**Description**: Type an optional description.</span></span> <span data-ttu-id="f1a49-144">Например, администраторам сообщается об обнаружении вредоносных файлов в SharePoint Online, OneDrive или Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f1a49-144">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="f1a49-145">**Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.</span><span class="sxs-lookup"><span data-stu-id="f1a49-145">**Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.</span></span>
   - <span data-ttu-id="f1a49-146">**Выберите категорию**: выберите **управление угрозами.**</span><span class="sxs-lookup"><span data-stu-id="f1a49-146">**Select a category**: Select **Threat management**.</span></span>

   <span data-ttu-id="f1a49-147">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f1a49-147">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="f1a49-148">На странице **"Создание параметров оповещений"** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f1a49-148">On the **Create alert settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="f1a49-149">**Что нужно оповещать?: Действие:** выберите **обнаруженную вредоносную программу в файле.**</span><span class="sxs-lookup"><span data-stu-id="f1a49-149">**What do you want to alert on?: Activity is**: Select **Detected malware in file**.</span></span>
   - <span data-ttu-id="f1a49-150">**Как следует запускать** оповещение? Оставьте значение по умолчанию каждый раз, когда действие соответствует **выбранному правилу.**</span><span class="sxs-lookup"><span data-stu-id="f1a49-150">**How do you want the alert to be triggered?**: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="f1a49-151">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f1a49-151">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="f1a49-152">На странице **"Настройка получателей"** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f1a49-152">On the **Set your recipients** page, configure the following settings:</span></span>

   - <span data-ttu-id="f1a49-153">**Отправка уведомлений по электронной** почте: убедитесь, что этот параметр выбран.</span><span class="sxs-lookup"><span data-stu-id="f1a49-153">**Send email notifications**: Verify this setting is selected.</span></span> <span data-ttu-id="f1a49-154">В поле **получателей** электронной почты выберите одного или несколько глобальных администраторов, администраторов безопасности или читателей безопасности, которые должны получать уведомления при обнаружении вредоносного файла.</span><span class="sxs-lookup"><span data-stu-id="f1a49-154">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="f1a49-155">**Ограничение на количество уведомлений за** день: оставьте значение по умолчанию **без** ограничения.</span><span class="sxs-lookup"><span data-stu-id="f1a49-155">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="f1a49-156">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f1a49-156">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="f1a49-157">На странице **"Просмотр параметров"** просмотрите параметры и нажмите кнопку **"Изменить"** в любом из разделов, чтобы внести изменения.</span><span class="sxs-lookup"><span data-stu-id="f1a49-157">On the **Review your settings** page, review the settings, and click **Edit** in any of the sections to make changes.</span></span>

   <span data-ttu-id="f1a49-158">В разделе "Включить ли вы политику **сразу?",** оставьте значение по умолчанию **"Да",** включив ее сразу же.</span><span class="sxs-lookup"><span data-stu-id="f1a49-158">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="f1a49-159">Закончив, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="f1a49-159">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="f1a49-160">Использование PowerShell & безопасности для обеспечения соответствия требованиям для создания политики оповещений для обнаруженных файлов</span><span class="sxs-lookup"><span data-stu-id="f1a49-160">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="f1a49-161">Если вы хотите использовать PowerShell для создания той же политики оповещений, которая описана в предыдущем разделе, подключите к [PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) Центра безопасности & соответствия требованиям и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f1a49-161">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="f1a49-162">**Примечание.** Значение _серьезности по_ умолчанию — Low.</span><span class="sxs-lookup"><span data-stu-id="f1a49-162">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="f1a49-163">Чтобы указать medium или High, включаем параметр _Severity_ и значение в команду.</span><span class="sxs-lookup"><span data-stu-id="f1a49-163">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="f1a49-164">Подробные сведения о синтаксисах и параметрах см. в описании [New-ActivityAlert.](https://docs.microsoft.com/powershell/module/exchange/new-activityalert)</span><span class="sxs-lookup"><span data-stu-id="f1a49-164">For detailed syntax and parameter information, see [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="f1a49-165">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="f1a49-165">How do you know these procedures worked?</span></span>

- <span data-ttu-id="f1a49-166">Чтобы убедиться, что вы успешно включили безопасные вложения для SharePoint, OneDrive и Microsoft Teams, с помощью одного из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="f1a49-166">To verify that you've successfully turned on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="f1a49-167">В Центре [безопасности &](https://protection.office.com)соответствия требованиям  перейдите в раздел "Безопасные вложения ATP политики управления угрозами", выберите глобальные параметры и проверьте значение параметра "Включить Защитник для \>  \>  **Office 365 для SharePoint, OneDrive** и Microsoft Teams". </span><span class="sxs-lookup"><span data-stu-id="f1a49-167">In the [Security & Compliance Center](https://protection.office.com), go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, select **Global settings**, and verify the value of the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="f1a49-168">В Exchange Online PowerShell запустите следующую команду, чтобы проверить параметр свойства:</span><span class="sxs-lookup"><span data-stu-id="f1a49-168">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="f1a49-169">Подробные сведения о синтаксисах и параметрах см. в описании [get-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="f1a49-169">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="f1a49-170">Чтобы убедиться, что вы успешно заблокировали загрузку вредоносных файлов, откройте SharePoint Online PowerShell и запустите следующую команду, чтобы проверить значение свойства:</span><span class="sxs-lookup"><span data-stu-id="f1a49-170">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="f1a49-171">Подробные сведения о синтаксисах и параметрах см. в описании [Get-SPOTenant.](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)</span><span class="sxs-lookup"><span data-stu-id="f1a49-171">For detailed syntax and parameter information, see [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="f1a49-172">Чтобы убедиться, что вы успешно настроили политику оповещений для обнаруженных файлов, воспользуйтесь одним из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="f1a49-172">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>

  - <span data-ttu-id="f1a49-173">В Центре безопасности & соответствия требованиям  перейдите к политикам оповещений, выберите политику оповещений и проверьте \>  \> параметры.</span><span class="sxs-lookup"><span data-stu-id="f1a49-173">In the Security & Compliance Center, go to **Alerts** \> **Alert policies** \> select the alert policy, and verify the settings.</span></span>

  - <span data-ttu-id="f1a49-174">В PowerShell Центра & безопасности замените имя политики оповещений, запустите следующую команду и проверьте \<AlertPolicyName\> значения свойств:</span><span class="sxs-lookup"><span data-stu-id="f1a49-174">In Security & Compliance Center PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="f1a49-175">Подробные сведения о синтаксисах и параметрах см. в описании [get-ActivityAlert.](https://docs.microsoft.com/powershell/module/exchange/get-activityalert)</span><span class="sxs-lookup"><span data-stu-id="f1a49-175">For detailed syntax and parameter information, see [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="f1a49-176">Используйте отчет [о состоянии защиты от угроз для](view-email-security-reports.md#threat-protection-status-report) просмотра сведений об обнаруженных файлах в SharePoint, OneDrive и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f1a49-176">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="f1a49-177">В частности, можно использовать данные **просмотра: представление "Вредоносные \> программы для** содержимого".</span><span class="sxs-lookup"><span data-stu-id="f1a49-177">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
