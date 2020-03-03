---
title: Восстановление удаленной группы Office 365
ms.reviewer: arvaradh
f1.keywords:
- CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 'Узнайте, как восстановить удаленную группу Office 365 с помощью центра администрирования Exchange. '
ms.openlocfilehash: c88f10df27e5f3a0af79c93c7d0e347c5646abc9
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352440"
---
# <a name="restore-a-deleted-office-365-group"></a><span data-ttu-id="5c0f7-103">Восстановление удаленной группы Office 365</span><span class="sxs-lookup"><span data-stu-id="5c0f7-103">Restore a deleted Office 365 Group</span></span>

<span data-ttu-id="5c0f7-104">Если вы являетесь владельцем группы Office 365, вы можете самостоятельно восстановить эту группу, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-104">If you are the owner of an Office 365 group, you can restore the group yourself by following these steps.</span></span>

1. <span data-ttu-id="5c0f7-105">На [странице удаленные группы](https://outlook.office.com/people/group/deleted)выберите пункт **Управление группами** в узле **группы** , а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-105">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>
2. <span data-ttu-id="5c0f7-106">Щелкните вкладку **Восстановление** рядом с группой, которую требуется восстановить.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-106">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="5c0f7-107">Если удаленная группа не отображается здесь, обратитесь к администратору.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-107">If the deleted group doesn't appear here, contact an administrator.</span></span>
  
<span data-ttu-id="5c0f7-108">Если вы хотите восстановить группу Office 365, попросите администратора выполнить эти действия и обратиться в службу технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-108">If you're a user who wants to restore an Office 365 group, ask an administrator to do these steps for you or contact your help desk.</span></span>  
   
<span data-ttu-id="5c0f7-109">Если вы удалили группу, по умолчанию она будет храниться в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-109">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="5c0f7-110">Этот 30-дневный период считается "обратимым удалением", так как вы по-прежнему можете восстановить группу.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-110">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="5c0f7-111">По истечении 30 дней группа и связанное с ней содержимое безвозвратно удаляются и не могут быть восстановлены.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-111">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>
  
<span data-ttu-id="5c0f7-112">Если пользователь попытается получить доступ к сайту, в течение периода "Soft-Delete", если пользователь попытается получить доступ к сайту, он получит сообщение 404 _запрещено_ .</span><span class="sxs-lookup"><span data-stu-id="5c0f7-112">During the "soft-delete" period, if a user tries to access the site they will get a 404 _forbidden_ message.</span></span> <span data-ttu-id="5c0f7-113">По истечении этого периода, если пользователь пытается получить доступ к сайту, он получит сообщение 404 _не найдено_ .</span><span class="sxs-lookup"><span data-stu-id="5c0f7-113">After this period, if a user tries to access the site, they will get a 404 _not found_ message.</span></span>
  
<span data-ttu-id="5c0f7-114">Вместе с группой восстанавливается следующее содержимое:</span><span class="sxs-lookup"><span data-stu-id="5c0f7-114">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="5c0f7-115">Azure Active Directory (AD) Office 365 группирует объект, свойства и элементы.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-115">Azure Active Directory (AD) Office 365 groups object, properties, and members.</span></span>
    
- <span data-ttu-id="5c0f7-116">Адреса электронной почты группы.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-116">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="5c0f7-117">Общие папки "Входящие" и "Календарь" в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-117">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="5c0f7-118">Сайт группы SharePoint Online и файлы.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-118">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="5c0f7-119">записная книжка OneNote;</span><span class="sxs-lookup"><span data-stu-id="5c0f7-119">OneNote notebook</span></span>
    
- <span data-ttu-id="5c0f7-120">Planner.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-120">Planner</span></span>
    
- <span data-ttu-id="5c0f7-121">Teams</span><span class="sxs-lookup"><span data-stu-id="5c0f7-121">Teams</span></span>

- <span data-ttu-id="5c0f7-122">Группа Yammer и контент группы (если группа Office 365 была создана из Yammer)</span><span class="sxs-lookup"><span data-stu-id="5c0f7-122">Yammer group and group content (If the Office 365 group was created from Yammer)</span></span>
    
<span data-ttu-id="5c0f7-123">Вы можете [Окончательное удаление группы Office 365](#permanently-delete-an-office-365-group), если не хотите ждать окончания 30-дневного периода хранения, после которого содержимое удаляется безвозвратно.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-123">You can also [Permanently delete an Office 365 group](#permanently-delete-an-office-365-group) if you can't wait the 30 days for the retention period to expire for the content to be permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="5c0f7-124">Владелец удаленной группы Office 365 также может восстановить группу.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-124">The owner of the deleted Office 365 group is also able to restore the group.</span></span> <span data-ttu-id="5c0f7-125">Чтобы восстановить группу Office 365 с помощью разрешения владельца без разрешения администратора, ознакомьтесь со статьей [Восстановление группы office 365 с помощью PowerShell](#restore-an-office-365-group-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="5c0f7-125">To restore an office 365 group using owner permission without administrator permission, see [Restore an Office 365 Group using PowerShell](#restore-an-office-365-group-using-powershell).</span></span>

## <a name="restore-an-office-365-group-using-the-exchange-admin-center"></a><span data-ttu-id="5c0f7-126">Восстановление группы Office 365 через Центр администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="5c0f7-126">Restore an Office 365 Group using the Exchange admin center</span></span>

<span data-ttu-id="5c0f7-127">Необходимо иметь разрешения глобального администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-127">You must have Office 365 global administrator permissions.</span></span>

1. <span data-ttu-id="5c0f7-128">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Центр администрирования Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-128">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
    
2. <span data-ttu-id="5c0f7-129">В Центре администрирования Exchange выберите **получатели** и **группы**.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-129">In the Exchange admin center, select **recipients**, and then choose **groups**.</span></span> <span data-ttu-id="5c0f7-130">Вы можете проверить, является ли группа активной или обратимо удаленной.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-130">You can view whether the group is Active or soft-deleted.</span></span> <span data-ttu-id="5c0f7-131">Если группа была безвозвратно удалена, она не указывается в списке.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-131">If the group has been permanently deleted, it won't be listed at all.</span></span>
  
3. <span data-ttu-id="5c0f7-132">Чтобы просмотреть точное время, когда группа была обратимо удалена, выберите группу и просмотрите сведения на правой панели.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-132">To view the exact time when the group was soft-deleted, select the group and view the info in the right pane.</span></span>
      
4. <span data-ttu-id="5c0f7-133">Выберите группу, которую требуется восстановить, а затем щелкните значок восстановления.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-133">Select the group you want to restore, and then select the restore icon.</span></span>
    
    ![Выберите группу, которую требуется восстановить, и щелкните значок восстановления.](../../media/restore-group.png)
  
5. <span data-ttu-id="5c0f7-135">Нажмите кнопку Обновить.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-135">Select refresh</span></span> ![Значок "Обновить"](../../media/6464df90-2a91-4c1f-92a6-9a38c7696ac3.gif) <span data-ttu-id="5c0f7-137">для обновления данных на странице.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-137">to update the information on the page.</span></span> <span data-ttu-id="5c0f7-138">Группа станет активной.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-138">Your group will show as Active.</span></span> <span data-ttu-id="5c0f7-139">Все формы и данные форм, связанные с группой, также будут восстановлены.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-139">Any forms and form data associated with your group will also be restored.</span></span>
    
## <a name="restore-an-office-365-group-using-powershell"></a><span data-ttu-id="5c0f7-140">Восстановление группы Office 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c0f7-140">Restore an Office 365 Group using PowerShell</span></span>

<span data-ttu-id="5c0f7-141">Необходимо иметь разрешения глобального администратора Office 365 или являться первым владельцем удаленной группы Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-141">You must have Office 365 global administrator permissions, or be a former owner of the deleted Office 365 group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c0f7-142">При использовании командлета Remove – Мсолграуп в PowerShell для удаления группы эта группа будет удалена без возможности восстановления.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-142">If you use Remove-MsolGroup in PowerShell to delete a group, this will delete the group permanently.</span></span> <span data-ttu-id="5c0f7-143">При использовании PowerShell для удаления групп рекомендуется использовать командлет **Remove – азуреадмсграуп** для обратимого удаления группы Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-143">When using PowerShell to delete groups, it's best practice to use **Remove-AzureADMSGroup** to soft-delete the Office 365 group.</span></span> <span data-ttu-id="5c0f7-144">Таким образом, вы можете восстановить его, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-144">That way you can restore it if needed.</span></span> 
  
### <a name="install-the-preview-version-of-the-azure-active-directory-powershell-for-graph"></a><span data-ttu-id="5c0f7-145">Установка предварительной версии модуля Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c0f7-145">Install the preview version of the Azure Active Directory PowerShell for Graph</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c0f7-146">Вы не можете одновременно установить версии Preview и GA на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-146">You cannot install both the preview and GA versions on the same computer at the same time.</span></span>
  
<span data-ttu-id="5c0f7-147">Рекомендуется *всегда* оставаться актуальным, то есть удалить старую версию AzureADPreview или старую версию AzureAD и получить последнюю версию.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-147">As a best practice, we recommend *always* staying current, i.e. uninstall the old AzureADPreview or old AzureAD version and get the latest one.</span></span> 
  
 
1. <span data-ttu-id="5c0f7-148">В строке поиска введите Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-148">In your search bar, type Windows PowerShell.</span></span>
    
2. <span data-ttu-id="5c0f7-149">Щелкните программу **Windows PowerShell** правой кнопкой мыши и выберите пункт **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-149">Right-click on **Windows PowerShell** and select **Run as Administrator**.</span></span>
  
2. <span data-ttu-id="5c0f7-150">Проверьте установленные модули:</span><span class="sxs-lookup"><span data-stu-id="5c0f7-150">Review your installed modules:</span></span>
    
  ```
  Get-InstalledModule -Name "AzureAD*"
  ```

3. <span data-ttu-id="5c0f7-151">Чтобы удалить предыдущую версию AzureADPreview или AzureAD, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5c0f7-151">To uninstall a previous version of AzureADPreview or AzureAD, run this command:</span></span>
  
```
   Uninstall-Module AzureADPreview
```

<span data-ttu-id="5c0f7-152">или</span><span class="sxs-lookup"><span data-stu-id="5c0f7-152">or</span></span>
  
```
   Uninstall-Module AzureAD
```

4. <span data-ttu-id="5c0f7-153">To install the latest version of AzureADPreview, run this command:</span><span class="sxs-lookup"><span data-stu-id="5c0f7-153">To install the latest version of AzureADPreview, run this command:</span></span>
  
```
   Install-Module AzureADPreview
```



<span data-ttu-id="5c0f7-154">At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install. </span><span class="sxs-lookup"><span data-stu-id="5c0f7-154">At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install.</span></span>
  
### <a name="restore-the-deleted-group"></a><span data-ttu-id="5c0f7-155">Восстановление удаленной группы</span><span class="sxs-lookup"><span data-stu-id="5c0f7-155">Restore the deleted group</span></span>
  
1. <span data-ttu-id="5c0f7-156">Вы установили модуль **AzureADPreview** , как указано в разделе Превиоиус "Установка предварительной версии модуля Azure Active Directory для Windows PowerShell"?</span><span class="sxs-lookup"><span data-stu-id="5c0f7-156">Did you install the **AzureADPreview** module, as instructed in the previoius section "Install the preview version of the Azure Active Directory Module for Windows PowerShell"?</span></span>  <span data-ttu-id="5c0f7-157">Отсутствие актуальной **предварительной версии** модуля является основной причиной, по которой эти действия не дают результата.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-157">Not having the most current **preview** version is the #1 reason these steps don't work for people.</span></span> 
    
2. <span data-ttu-id="5c0f7-158">Откройте на компьютере окно Windows PowerShell (обычное окно Windows PowerShell или открытое с выбранным параметром **Запуск от имени администратора**).</span><span class="sxs-lookup"><span data-stu-id="5c0f7-158">If you haven't already, open a Windows PowerShell window on your computer (it doesn't matter if it's a normal Windows PowerShell window, or one you opened by selecting **Run as administrator**).</span></span>
    
3. <span data-ttu-id="5c0f7-159">Выполните следующие команды, нажимая клавишу **Ввод** после каждой из них:</span><span class="sxs-lookup"><span data-stu-id="5c0f7-159">Run the following commands by pressing **Enter** after each one:</span></span> 
    
  ```
  Import-Module AzureADPreview
  ```

  ```
  Connect-AzureAD
  ```



  <span data-ttu-id="5c0f7-160">На открывшемся экране **Вход в учетную запись** введите имя пользователя и пароль административной учетной записи, чтобы подключиться к службе Azure AD, и выберите **Вход**.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-160">On the **Sign in to your Account** screen that opens, enter your administrative account user name and password to connect you to your Azure AD service, and select **Sign in**.</span></span>
  
4. <span data-ttu-id="5c0f7-161">Выполните эту команду, чтобы отобразить все обратимо удаленные группы Office 365 в Организации, которые по-прежнему находятся в течение 30-дневного периода мягкого удаления:</span><span class="sxs-lookup"><span data-stu-id="5c0f7-161">Run this command to display all soft-deleted Office 365 groups in your organization that are still within the 30 day soft-deletion period:</span></span>
    
  ```
  Get-AzureADMSDeletedGroup
  ```

5. <span data-ttu-id="5c0f7-162">Запишите идентификатор объекта группы (или групп), которую хотите восстановить.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-162">Take note of the object ID of the group, or groups, you want to restore.</span></span> <span data-ttu-id="5c0f7-163">Если вы не видите группу, которую вы ищете в этом списке, вероятно, она уже очищена окончательно.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-163">If you don't see the group you're looking for on this list then it has likely been permanently purged already.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="5c0f7-164">Если была создана новая группа с тем же псевдонимом или SMTP-адресом, вам придется сначала удалить эту новую группу, чтобы потом восстановить удаленную.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-164">If a new group has been created with the same alias or SMTP address as your deleted group, you will have to delete that new group before you'll be able to restore your deleted group.</span></span> 
  
6. <span data-ttu-id="5c0f7-165">Чтобы восстановить эту группу, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5c0f7-165">To restore that group, run this command:</span></span>
    
  ```
  Restore-AzureADMSDeletedDirectoryObject -Id <objectId>
  ```

7. <span data-ttu-id="5c0f7-166">Этот процесс обычно занимает всего несколько минут, но в редких случаях может потребоваться до полного восстановления до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-166">This process usually takes just a few minutes but in a few rare cases it can take as long as 24 hours to be completely restored.</span></span> <span data-ttu-id="5c0f7-167">Чтобы убедиться, что группа успешно восстановлена, в PowerShell выполните эту команду:</span><span class="sxs-lookup"><span data-stu-id="5c0f7-167">To verify that the group has been successfully restored, run this command in PowerShell:</span></span>
    
  ```
  Get-AzureADGroup -ObjectId <objectId>
  ```

<span data-ttu-id="5c0f7-p110">После успешного восстановления группа должна снова появиться в области навигации Outlook и Outlook в Интернете, а весь восстановленный контент, включая из SharePoint и Планировщика, должен снова стать доступен участникам группы.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-p110">Once the restore has successfully completed, the group should reappear on the navigation pane in Outlook and Outlook on the web. All restored content, including SharePoint and Planner, should be available to the group members again.</span></span>
  
## <a name="permanently-delete-an-office-365-group"></a><span data-ttu-id="5c0f7-170">Окончательное удаление группы Office 365</span><span class="sxs-lookup"><span data-stu-id="5c0f7-170">Permanently delete an Office 365 group</span></span>

<span data-ttu-id="5c0f7-171">Иногда может потребоваться окончательно очистить группу, не дожидаясь периода действия 30 дней для мягкого удаления.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-171">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="5c0f7-172">Для этого запустите PowerShell и выполните эту команду, чтобы получить идентификатор объекта группы:</span><span class="sxs-lookup"><span data-stu-id="5c0f7-172">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="5c0f7-173">Запишите идентификатор объекта группы или групп, которые требуется окончательно удалить.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-173">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="5c0f7-174">При этом группа и все ее данные будут удалены навсегда.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-174">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="5c0f7-175">Чтобы окончательно удалить группу, в PowerShell выполните эту команду:</span><span class="sxs-lookup"><span data-stu-id="5c0f7-175">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="5c0f7-p112">Чтобы проверить, удалилась ли группа, снова запустите командлет  *Get-AzureADMSDeletedGroup*  и убедитесь, что группа отсутствует в списке обратимо удаленных. В некоторых случаях процесс полного окончательного удаления группы и всех ее данных может длиться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-p112">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-office-365-groups"></a><span data-ttu-id="5c0f7-178">У вас есть вопросы о группах Office 365?</span><span class="sxs-lookup"><span data-stu-id="5c0f7-178">Got questions about Office 365 Groups?</span></span>

<span data-ttu-id="5c0f7-179">Посетите [сообщество Майкрософт](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) для отправки вопросов и участия в беседах, посвященных группам Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c0f7-179">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Office 365 Groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="5c0f7-180">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="5c0f7-180">Related articles</span></span>

[<span data-ttu-id="5c0f7-181">Управление группами Office 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c0f7-181">Manage Office 365 Groups with PowerShell</span></span>](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[<span data-ttu-id="5c0f7-182">Удаление групп с помощью командлета Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="5c0f7-182">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="5c0f7-183">Управление параметрами сайта группы, подключенного к группе</span><span class="sxs-lookup"><span data-stu-id="5c0f7-183">Manage your group-connected team site settings</span></span>](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[<span data-ttu-id="5c0f7-184">Удаление группы в Outlook</span><span class="sxs-lookup"><span data-stu-id="5c0f7-184">Delete a group in Outlook</span></span>](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
