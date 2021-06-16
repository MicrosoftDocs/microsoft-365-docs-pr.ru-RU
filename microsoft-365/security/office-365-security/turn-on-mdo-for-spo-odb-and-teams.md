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
description: Администраторы могут узнать, как включить Сейф вложения для SharePoint, OneDrive и Microsoft Teams, включая набор оповещений для обнаруженных файлов.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a654db40e5dec8d23d07ec7455216fe4e0a8c0e7
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/15/2021
ms.locfileid: "52933015"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="4f2a2-103">Включение безопасных вложений для SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4f2a2-103">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4f2a2-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="4f2a2-104">**Applies to**</span></span>
- [<span data-ttu-id="4f2a2-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="4f2a2-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="4f2a2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4f2a2-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="4f2a2-107">Microsoft Defender для Office 365 для SharePoint, OneDrive и Microsoft Teams защищает организацию от случайного обмена вредоносными файлами.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-107">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="4f2a2-108">Дополнительные сведения см. [в Сейф вложениях SharePoint, OneDrive и Microsoft Teams.](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="4f2a2-108">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="4f2a2-109">В этой статье содержатся действия для включения и настройки Сейф вложений для SharePoint, OneDrive и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-109">This article contains the steps for enabling and configuring Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4f2a2-110">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="4f2a2-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4f2a2-111">Чтобы открыть портал Microsoft 365 Defender, перейдите на сайт <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-111">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="4f2a2-112">Чтобы перейти непосредственно **на страницу Сейф вложения,** откройте <https://security.microsoft.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="4f2a2-112">To go directly to the **Safe Attachments** page, open <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="4f2a2-113">Чтобы включить Сейф вложения для SharePoint, OneDrive и Microsoft Teams, необходимо быть членом групп ролей управления организацией  или  администратора безопасности на портале Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-113">To turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="4f2a2-114">Дополнительные сведения см. [в сайте Permissions in the Microsoft 365 Defender.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="4f2a2-114">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="4f2a2-115">Чтобы использовать SharePoint PowerShell для предотвращения скачивания вредоносных файлов, необходимо [](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) быть членом [](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) глобального администратора или администратора SharePoint в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-115">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="4f2a2-116">Убедитесь, что журнал аудита включен для организации.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-116">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="4f2a2-117">Дополнительные сведения см. в статье [Включение и отключение поиска в журнале аудита](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="4f2a2-117">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="4f2a2-118">Разрешить до 30 минут, чтобы параметры вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-118">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="4f2a2-119">Шаг 1. Используйте портал Microsoft 365 Defender, чтобы включить Сейф вложения для SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4f2a2-119">Step 1: Use the Microsoft 365 Defender portal to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="4f2a2-120">На портале Microsoft 365 Defender **перейдите** в раздел Политики & правила политики угрозы Сейф \>  \>  \> **вложения.**</span><span class="sxs-lookup"><span data-stu-id="4f2a2-120">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="4f2a2-121">На странице **Сейф вложения нажмите** **глобальные параметры**.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-121">On the **Safe Attachments** page, click **Global settings**.</span></span>

3. <span data-ttu-id="4f2a2-122">В **глобальной настройки** вылет, который появляется, перейдите к защите файлов **в SharePoint, OneDrive и Microsoft Teams** разделе.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-122">In the **Global settings** fly out that appears, go to the **Protect files in SharePoint, OneDrive, and Microsoft Teams** section.</span></span>

   <span data-ttu-id="4f2a2-123">Переместите включаем **защитника для Office 365 для SharePoint, OneDrive** и Microsoft Teams переключив вправо, чтобы включить Сейф вложения для ![ ](../../media/scc-toggle-on.png) SharePoint, OneDrive и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-123">Move the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="4f2a2-124">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-124">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="4f2a2-125">Используйте Exchange Online PowerShell, чтобы включить Сейф вложения для SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4f2a2-125">Use Exchange Online PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="4f2a2-126">Если вы хотите использовать [PowerShell,](/powershell/exchange/connect-to-exchange-online-powershell) чтобы включить Сейф вложения для SharePoint, OneDrive и Microsoft Teams, подключите Exchange Online PowerShell и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4f2a2-126">If you'd rather use PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="4f2a2-127">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-AtpPolicyForO365.](/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="4f2a2-127">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="4f2a2-128">Шаг 2. (Рекомендуется) Использование SharePoint PowerShell для предотвращения скачивания пользователями вредоносных файлов</span><span class="sxs-lookup"><span data-stu-id="4f2a2-128">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="4f2a2-129">По умолчанию пользователи не могут открывать, перемещать, копировать или делиться вредоносными файлами, обнаруженными Сейф вложениями для SharePoint, OneDrive и <sup>\*</sup> Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-129">By default, users can't open, move, copy, or share<sup>\*</sup> malicious files that are detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="4f2a2-130">Однако они могут удалять и скачивать вредоносные файлы.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-130">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="4f2a2-131"><sup>\*</sup> Если пользователи перейдут **на управление доступом,** параметр **Share** по-прежнему доступен.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-131"><sup>\*</sup> If users go to **Manage access**, the **Share** option is still available.</span></span>

<span data-ttu-id="4f2a2-132">Чтобы запретить пользователям скачивать вредоносные файлы, [подключите SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4f2a2-132">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="4f2a2-133">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="4f2a2-133">**Notes**:</span></span>

- <span data-ttu-id="4f2a2-134">Этот параметр влияет как на пользователей, так и на администраторов.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-134">This setting affects both users and admins.</span></span>
- <span data-ttu-id="4f2a2-135">Люди по-прежнему могут удалять вредоносные файлы.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-135">People can still delete malicious files.</span></span>

<span data-ttu-id="4f2a2-136">Подробные сведения о синтаксисах и параметрах см. [в инструкции Set-SPOTenant.](/powershell/module/sharepoint-online/Set-SPOTenant)</span><span class="sxs-lookup"><span data-stu-id="4f2a2-136">For detailed syntax and parameter information, see [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-microsoft-365-defender-portal-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="4f2a2-137">Шаг 3 (Рекомендуется) Использование портала Microsoft 365 Defender для создания политики оповещения для обнаруженных файлов</span><span class="sxs-lookup"><span data-stu-id="4f2a2-137">Step 3 (Recommended) Use the Microsoft 365 Defender portal to create an alert policy for detected files</span></span>

<span data-ttu-id="4f2a2-138">Вы можете создать политику оповещения, которая оповещает вас и других администраторов, Сейф вложения для SharePoint, OneDrive и Microsoft Teams обнаруживает вредоносный файл.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-138">You can create an alert policy that notifies you and other admins when Safe Attachments for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="4f2a2-139">Дополнительные дополнительные информацию о оповещениях см. в [сайте Create activity alerts in the Microsoft 365 Defender.](../../compliance/create-activity-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="4f2a2-139">To learn more about alerts, see [Create activity alerts in the Microsoft 365 Defender portal](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="4f2a2-140">На портале Microsoft 365 Defender перейдите к политике & **правил Оповещения** или \>  откройте <https://security.microsoft.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="4f2a2-140">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Alert policy** or open <https://security.microsoft.com/alertpolicies>.</span></span>

2. <span data-ttu-id="4f2a2-141">На странице **Политика оповещения** нажмите кнопку Новая **политика оповещения**.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-141">On the **Alert policy** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="4f2a2-142">Мастер **политики оповещения открывается** при вылете. На странице **Имя оповещений** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="4f2a2-142">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>
   - <span data-ttu-id="4f2a2-143">**Имя.** Введите уникальное и описательное имя.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-143">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="4f2a2-144">Например, вредоносные файлы в библиотеках.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-144">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="4f2a2-145">**Описание.** Введите необязательное описание.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-145">**Description**: Type an optional description.</span></span> <span data-ttu-id="4f2a2-146">Например, сообщает администраторам об обнаружении вредоносных файлов в SharePoint Online, OneDrive или Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-146">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="4f2a2-147">**Серьезность:** Выберите **низкий,** **средний** или **высокий** из списка выпаданий.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-147">**Severity**: Select **Low**, **Medium**, or **High** from the drop down list.</span></span>
   - <span data-ttu-id="4f2a2-148">**Категория.** Выберите **управление угрозами** из списка выпаданий.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-148">**Category**: Select **Threat management** from the drop down list.</span></span>

   <span data-ttu-id="4f2a2-149">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="4f2a2-150">На странице **Создание параметров оповещения** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="4f2a2-150">On the **Create alert settings** page, configure the following settings:</span></span>
   - <span data-ttu-id="4f2a2-151">**О чем нужно оповещать?** Раздел \> **Действия — это** \> выберите **обнаруженную вредоносную программу в файле** из списка drop down.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-151">**What do you want to alert on?** section \> **Activity is** \> Select **Detected malware in file** from the drop down list.</span></span>
   - <span data-ttu-id="4f2a2-152">**Как срабатывает оповещение?** раздел. Оставьте значение по умолчанию **каждый раз,** когда действие соответствует выбранному правилу.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-152">**How do you want the alert to be triggered?** section: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="4f2a2-153">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-153">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="4f2a2-154">На странице **Set your recipients** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="4f2a2-154">On the **Set your recipients** page, configure the following settings:</span></span>
   - <span data-ttu-id="4f2a2-155">Проверка **выбора уведомлений отправки** электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-155">Verify **Send email notifications** is selected.</span></span> <span data-ttu-id="4f2a2-156">В поле **получателей** электронной почты выберите одного или несколько глобальных администраторов, администраторов безопасности или читателей безопасности, которые должны получать уведомления при обнаружении вредоносного файла.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-156">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="4f2a2-157">**Дневное ограничение** уведомлений. Оставьте выбранное **значение без ограничения** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-157">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="4f2a2-158">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-158">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="4f2a2-159">На странице **Обзор параметров** просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-159">On the **Review your settings** page, review your settings.</span></span> <span data-ttu-id="4f2a2-160">Вы можете выбрать **Изменить** в любом разделе, чтобы изменить параметры в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-160">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="4f2a2-161">Вы также можете щелкнуть **Назад** или выбрать определенную страницу в мастере.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-161">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="4f2a2-162">В разделе Вы хотите включить политику **сразу?** оставьте значение **Да,** включив ее сразу же выбранной.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-162">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="4f2a2-163">Закончив, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-163">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="4f2a2-164">Используйте службу & powerShell для создания политики оповещения для обнаруженных файлов</span><span class="sxs-lookup"><span data-stu-id="4f2a2-164">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="4f2a2-165">Если вы хотите использовать PowerShell для создания той же политики оповещений, что и в предыдущем разделе, подключись к центру обеспечения безопасности [& PowerShell](/powershell/exchange/connect-to-scc-powershell) и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4f2a2-165">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="4f2a2-166">**Примечание.** Значение _серьезности по умолчанию_ является низким.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-166">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="4f2a2-167">Чтобы указать Medium или High, включай параметр _Severity_ и значение в команду.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-167">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="4f2a2-168">Подробные сведения о синтаксисах и параметрах см. [в обзоре New-ActivityAlert.](/powershell/module/exchange/new-activityalert)</span><span class="sxs-lookup"><span data-stu-id="4f2a2-168">For detailed syntax and parameter information, see [New-ActivityAlert](/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="4f2a2-169">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="4f2a2-169">How do you know these procedures worked?</span></span>

- <span data-ttu-id="4f2a2-170">Чтобы убедиться, что вы успешно включили Сейф вложения для SharePoint, OneDrive и Microsoft Teams, используйте один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="4f2a2-170">To verify that you've successfully turned on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="4f2a2-171">На портале Microsoft 365 Defender **перейдите** в раздел Политики & правила политики угроз Сейф Вложения, выберите глобальные параметры и проверьте значение параметра Turn on Defender для Office 365 для \>  \>  \>  **SharePoint, OneDrive и Microsoft Teams.** </span><span class="sxs-lookup"><span data-stu-id="4f2a2-171">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Attachments**, select **Global settings**, and verify the value of the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="4f2a2-172">В Exchange Online PowerShell запустите следующую команду, чтобы проверить параметр свойства:</span><span class="sxs-lookup"><span data-stu-id="4f2a2-172">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="4f2a2-173">Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-AtpPolicyForO365.](/powershell/module/exchange/get-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="4f2a2-173">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="4f2a2-174">Чтобы убедиться, что вы успешно заблокировали загрузку вредоносных файлов, откройте SharePoint PowerShell и запустите следующую команду, чтобы проверить значение свойства:</span><span class="sxs-lookup"><span data-stu-id="4f2a2-174">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="4f2a2-175">Подробные сведения о синтаксисах и параметрах см. [в обзоре Get-SPOTenant.](/powershell/module/sharepoint-online/Set-SPOTenant)</span><span class="sxs-lookup"><span data-stu-id="4f2a2-175">For detailed syntax and parameter information, see [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="4f2a2-176">Чтобы убедиться, что вы успешно настроили политику оповещения для обнаруженных файлов, используйте любой из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="4f2a2-176">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>
  - <span data-ttu-id="4f2a2-177">На портале Microsoft 365 Defender **перейдите** к политике & правила Оповещения выберите политику оповещения и проверьте \>  \> параметры.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-177">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Alert policy** \> select the alert policy, and verify the settings.</span></span>
  - <span data-ttu-id="4f2a2-178">В Microsoft 365 портала Defender PowerShell замените имя политики оповещения, запустите следующую команду и проверьте \<AlertPolicyName\> значения свойств:</span><span class="sxs-lookup"><span data-stu-id="4f2a2-178">In Microsoft 365 Defender portal PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="4f2a2-179">Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-ActivityAlert.](/powershell/module/exchange/get-activityalert)</span><span class="sxs-lookup"><span data-stu-id="4f2a2-179">For detailed syntax and parameter information, see [Get-ActivityAlert](/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="4f2a2-180">Используйте отчет [о состоянии защиты от](view-email-security-reports.md#threat-protection-status-report) угроз, чтобы просмотреть сведения о обнаруженных файлах в SharePoint, OneDrive и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-180">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="4f2a2-181">В частности, вы можете использовать **данные View по: Просмотр \> вредоносных программ** контента.</span><span class="sxs-lookup"><span data-stu-id="4f2a2-181">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
