---
title: Включение Office 365 ATP для SharePoint, OneDrive и Microsoft Teams
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
ms.openlocfilehash: 720b14100409ab607eab7370644ee3e8ff96dca9
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971657"
---
# <a name="turn-on-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="bbc58-103">Включение Office 365 ATP для SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bbc58-103">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bbc58-104">Эта статья предназначена для бизнес-клиентов, у которых есть [Office 365 Advanced Threat Protection](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="bbc58-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="bbc58-105">Если вы являетесь домашним пользователем, который ищет сведения о безопасных ссылках в Outlook, ознакомьтесь со статьей [Advanced Outlook.com Security](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="bbc58-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="bbc58-106">[Office 365 ATP для SharePoint, OneDrive и Microsoft Teams](atp-for-spo-odb-and-teams.md) защищает организацию от случайного предоставления вредоносных файлов.</span><span class="sxs-lookup"><span data-stu-id="bbc58-106">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="bbc58-107">При обнаружении вредоносного файла этот файл блокируется, чтобы никто не мог открыть, скопировать, переместить или предоставить к нему общий доступ до тех пор, пока не будут предприняты дальнейшие действия группы безопасности Организации.</span><span class="sxs-lookup"><span data-stu-id="bbc58-107">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="bbc58-108">В этой статье описано, как включить ATP для SharePoint, OneDrive и Teams, настроить оповещения о обнаруженных файлах и выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bbc58-108">Read this article to turn on ATP for SharePoint, OneDrive, and Teams, set up alerts to be notified about detected files, and take your next steps.</span></span>
  
<span data-ttu-id="bbc58-109">Для определения (или изменения) политик ATP необходимо назначить соответствующую роль.</span><span class="sxs-lookup"><span data-stu-id="bbc58-109">To define (or edit) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="bbc58-110">Некоторые примеры описаны в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="bbc58-110">Some examples are described in the following table:</span></span>

|<span data-ttu-id="bbc58-111">Role</span><span class="sxs-lookup"><span data-stu-id="bbc58-111">Role</span></span>  |<span data-ttu-id="bbc58-112">Где/как назначено</span><span class="sxs-lookup"><span data-stu-id="bbc58-112">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="bbc58-113">Глобальный администратор Office 365</span><span class="sxs-lookup"><span data-stu-id="bbc58-113">Office 365 Global Administrator</span></span> |<span data-ttu-id="bbc58-114">Пользователь, который подписывается на приобретение Office 365, по умолчанию является глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="bbc58-114">The person who signs up to buy Office 365 is a global admin by default.</span></span> <span data-ttu-id="bbc58-115">(Чтобы узнать больше, ознакомьтесь со статьей [о ролях администратора Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) .)</span><span class="sxs-lookup"><span data-stu-id="bbc58-115">(See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="bbc58-116">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="bbc58-116">Security Administrator</span></span> |<span data-ttu-id="bbc58-117">Центр администрирования Azure Active Directory ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="bbc58-117">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="bbc58-118">Управление организациями в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bbc58-118">Exchange Online Organization Management</span></span> |<span data-ttu-id="bbc58-119">Центр администрирования Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="bbc58-119">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="bbc58-120">или</span><span class="sxs-lookup"><span data-stu-id="bbc58-120">or</span></span> <br>  <span data-ttu-id="bbc58-121">Командлеты PowerShell (см. [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))</span><span class="sxs-lookup"><span data-stu-id="bbc58-121">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))</span></span> |
  
## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="bbc58-122">Включение ATP для SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bbc58-122">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="bbc58-123">**Прежде чем приступить к этой процедуре, убедитесь, что ведение журнала аудита для вашей среды Office 365 уже включено**.</span><span class="sxs-lookup"><span data-stu-id="bbc58-123">**Before you begin this procedure, make sure that audit logging is already turned on for your Office 365 environment**.</span></span> <span data-ttu-id="bbc58-124">Это обычно делается для пользователей, которым назначена роль "журналы аудита" в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="bbc58-124">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="bbc58-125">Дополнительную информацию можно узнать [в статье Включение и отключение поиска в журнале аудита Office 365](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="bbc58-125">For more information, see [Turn Office 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>
  
1. <span data-ttu-id="bbc58-126">Перейдите на [https://protection.office.com](https://protection.office.com)страницу и войдите с помощью рабочей или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="bbc58-126">Go to [https://protection.office.com](https://protection.office.com), and sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="bbc58-127">В центре &amp; безопасности и соответствия требованиям Office 365 в области навигации слева в разделе **Управление угрозами**выберите пункт **безопасные вложения** **политики** \> .</span><span class="sxs-lookup"><span data-stu-id="bbc58-127">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span> <br/><span data-ttu-id="bbc58-128">![В центре безопасности &amp; и соответствия требованиям выберите Политика управления \> угрозами](../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)</span><span class="sxs-lookup"><span data-stu-id="bbc58-128">![In the Security &amp; Compliance Center, choose Threat management \> Policy](../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)</span></span>
  
3. <span data-ttu-id="bbc58-129">Выберите **включить ATP для SharePoint, OneDrive и Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="bbc58-129">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span><br/><span data-ttu-id="bbc58-130">![Включение расширенной защиты от угроз для SharePoint Online, OneDrive для бизнеса и Microsoft Teams](../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)</span><span class="sxs-lookup"><span data-stu-id="bbc58-130">![Turn on Advanced Threat Protection for SharePoint Online, OneDrive for Business, and Microsoft Teams](../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)</span></span>
  
4. <span data-ttu-id="bbc58-131">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="bbc58-131">Click **Save**.</span></span>
    
5. <span data-ttu-id="bbc58-132">Просмотрите (и, соответственно, измените) [политики безопасных вложений](set-up-atp-safe-attachments-policies.md) в Организации и [политики безопасных ссылок](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="bbc58-132">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>
    
6. <span data-ttu-id="bbc58-133">Предложен В качестве глобального администратора или администратора SharePoint Online выполните командлет **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** с параметром **дисалловинфектедфиледовнлоад** , для которого задано *значение true*.</span><span class="sxs-lookup"><span data-stu-id="bbc58-133">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true*.</span></span> <br/>
      - <span data-ttu-id="bbc58-134">При установке для параметра значения *true* блокируются все действия для обнаруженных файлов (кроме DELETE).</span><span class="sxs-lookup"><span data-stu-id="bbc58-134">Setting the parameter to *true* blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="bbc58-135">Пользователи не могут открывать, перемещать и копировать обнаруженные файлы, а также предоставлять к ним общий доступ.</span><span class="sxs-lookup"><span data-stu-id="bbc58-135">People cannot open, move, copy, or share detected files.</span></span>
      - <span data-ttu-id="bbc58-136">Если задать для параметра *значение false* , все действия, кроме DELETE и download, блокируются.</span><span class="sxs-lookup"><span data-stu-id="bbc58-136">Setting the parameter to *false* blocks all actions except Delete and Download.</span></span> <span data-ttu-id="bbc58-137">Пользователи могут принять решение о риске и скачать обнаруженный файл.</span><span class="sxs-lookup"><span data-stu-id="bbc58-137">People can choose to accept the risk and download a detected file.</span></span>  
   
7. <span data-ttu-id="bbc58-138">Разрешите до 30 минут, пока ваши изменения распространяются на все центры обработки данных Office 365.</span><span class="sxs-lookup"><span data-stu-id="bbc58-138">Allow up to 30 minutes for your changes to spread to all Office 365 datacenters.</span></span>
    
8. <span data-ttu-id="bbc58-139">Предложен Перейдите к разделу Настройка оповещений для обнаруженных файлов.</span><span class="sxs-lookup"><span data-stu-id="bbc58-139">(Recommended) Proceed to set up alerts for detected files.</span></span>
    
<span data-ttu-id="bbc58-140">Для получения дополнительных сведений об использовании PowerShell с Office 365, ознакомьтесь со статьей [Управление office 365 с помощью PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="bbc58-140">To learn more about using PowerShell with Office 365, see [Manage Office 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).</span></span> 

<span data-ttu-id="bbc58-141">Чтобы узнать больше о пользовательском интерфейсе, когда файл был определен как вредоносный, посмотрите, [что делать, когда вредоносный файл обнаружен в SharePoint Online, OneDrive или Microsoft Teams](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span><span class="sxs-lookup"><span data-stu-id="bbc58-141">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span> 
  
## <a name="set-up-alerts-for-detected-files"></a><span data-ttu-id="bbc58-142">Настройка оповещений для обнаруженных файлов</span><span class="sxs-lookup"><span data-stu-id="bbc58-142">Set up alerts for detected files</span></span>

<span data-ttu-id="bbc58-143">Чтобы получать уведомления о том, что файл в SharePoint Online, OneDrive для бизнеса или Microsoft Teams определен как вредоносный, вы можете настроить оповещение.</span><span class="sxs-lookup"><span data-stu-id="bbc58-143">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>
  
1. <span data-ttu-id="bbc58-144">В [центре безопасности &amp; и соответствия требованиям Office 365](https://protection.office.com)выберите **оповещения** \> **Управление оповещениями**.</span><span class="sxs-lookup"><span data-stu-id="bbc58-144">In the [Office 365 Security &amp; Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>
    
2. <span data-ttu-id="bbc58-145">Выберите **создать политику оповещений**.</span><span class="sxs-lookup"><span data-stu-id="bbc58-145">Choose **New alert policy**.</span></span>
    
3. <span data-ttu-id="bbc58-146">Укажите имя оповещения.</span><span class="sxs-lookup"><span data-stu-id="bbc58-146">Specify a name for the alert.</span></span> <span data-ttu-id="bbc58-147">Например, можно ввести в библиотеки вредоносные файлы.</span><span class="sxs-lookup"><span data-stu-id="bbc58-147">For example, you could type Malicious Files in Libraries.</span></span>
    
4. <span data-ttu-id="bbc58-148">Введите описание оповещения.</span><span class="sxs-lookup"><span data-stu-id="bbc58-148">Type a description for the alert.</span></span> <span data-ttu-id="bbc58-149">Например, вы можете ввести уведомление администраторов об обнаружении вредоносных файлов в SharePoint Online, OneDrive или Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bbc58-149">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
    
5. <span data-ttu-id="bbc58-150">В разделе **отправить это оповещение, когда...** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="bbc58-150">In the **Send this alert when...** section, do the following:</span></span> 
    
    <span data-ttu-id="bbc58-151">а.</span><span class="sxs-lookup"><span data-stu-id="bbc58-151">a.</span></span> <span data-ttu-id="bbc58-152">В списке **действия** выберите **обнаруженная вредоносная программа в файле**.</span><span class="sxs-lookup"><span data-stu-id="bbc58-152">In the **Activities** list, choose **Detected malware in file**.</span></span>
    
    <span data-ttu-id="bbc58-153">б)</span><span class="sxs-lookup"><span data-stu-id="bbc58-153">b.</span></span> <span data-ttu-id="bbc58-154">Оставьте поле **Пользователи** пустым.</span><span class="sxs-lookup"><span data-stu-id="bbc58-154">Leave the **Users** field empty.</span></span> 
    
6. <span data-ttu-id="bbc58-155">В разделе **отправить это оповещение по...** выберите одного или нескольких глобальных администраторов, администраторов безопасности или средств чтения безопасности, которые должны получать уведомление при обнаружении вредоносного файла.</span><span class="sxs-lookup"><span data-stu-id="bbc58-155">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span> 
    
7. <span data-ttu-id="bbc58-156">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="bbc58-156">Click **Save**.</span></span>
    
<span data-ttu-id="bbc58-157">Чтобы узнать больше об оповещениях, ознакомьтесь со статьей [Создание оповещений о &amp; действиях в центре безопасности и соответствия требованиям Office 365](../../compliance/create-activity-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="bbc58-157">To learn more about alerts, see [Create activity alerts in the Office 365 Security &amp; Compliance Center](../../compliance/create-activity-alerts.md).</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="bbc58-158">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="bbc58-158">Next steps</span></span>

1. [<span data-ttu-id="bbc58-159">Просмотр сведений о вредоносных файлах, обнаруженных в SharePoint, OneDrive или Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bbc58-159">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
    
2. [<span data-ttu-id="bbc58-160">Управление сообщениями, помещенными в карантин, и файлами в качестве администратора в Office 365</span><span class="sxs-lookup"><span data-stu-id="bbc58-160">Manage quarantined messages and files as an administrator in Office 365</span></span>](manage-quarantined-messages-and-files.md)
    

  

