---
title: Использование меток конфиденциальности в Microsoft Teams, группах Office 365 и сайтах SharePoint (общедоступная предварительная версия)
ms.author: krowley
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Вы можете применять метки к Microsoft Teams, группам Office 365 и сайтам SharePoint.
ms.openlocfilehash: 0b5c4e8ef3611b417c59f7ac5b36f83a799e3397
ms.sourcegitcommit: a122fd1fce523171529c7f610bb7faf09d30a8bb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/18/2020
ms.locfileid: "41238446"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="898a9-103">Использование меток конфиденциальности в Microsoft Teams, группах Office 365 и сайтах SharePoint (общедоступная предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="898a9-103">Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>

<span data-ttu-id="898a9-104">При создании меток конфиденциальности в [Центре соответствия требованиям Microsoft 365](https://protection.office.com/) вы можете применить их в Microsoft Teams, к группам Office 365 и сайтам SharePoint.</span><span class="sxs-lookup"><span data-stu-id="898a9-104">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="898a9-105">Вы можете связать политики с метками, чтобы управлять следующими компонентами:</span><span class="sxs-lookup"><span data-stu-id="898a9-105">You can associate policies with the labels to control:</span></span>

- <span data-ttu-id="898a9-106">Открытые и закрытые параметры</span><span class="sxs-lookup"><span data-stu-id="898a9-106">Public/private settings</span></span>
- <span data-ttu-id="898a9-107">Гостевой доступ</span><span class="sxs-lookup"><span data-stu-id="898a9-107">Guest access</span></span>
- <span data-ttu-id="898a9-108">Доступ с неуправляемых устройств</span><span class="sxs-lookup"><span data-stu-id="898a9-108">Access from unmanaged devices</span></span>

<span data-ttu-id="898a9-109">Если вы применяете метку к команде или группе, эта метка автоматически применяется к подключенному сайту группы SharePoint и наоборот.</span><span class="sxs-lookup"><span data-stu-id="898a9-109">When you apply a label to a team or group, the label automatically applies to the connected SharePoint team site and the other way around.</span></span>

<span data-ttu-id="898a9-110">Теперь вы также можете включить метки конфиденциальности для файлов Office в SharePoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="898a9-110">You can now also enable sensitivity labels for Office files in SharePoint and OneDrive.</span></span> <span data-ttu-id="898a9-111">Дополнительные сведения см. в статье [Включение меток конфиденциальности для файлов Office в SharePoint и OneDrive (общедоступная предварительная версия)](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="898a9-111">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a><span data-ttu-id="898a9-112">Сведения об общедоступной предварительной версии для Microsoft Teams, групп Office 365 и сайтов SharePoint</span><span class="sxs-lookup"><span data-stu-id="898a9-112">About the public preview for Microsoft Teams, Office 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="898a9-113">Метки конфиденциальности для Microsoft Teams, групп Office 365 и сайтов SharePoint постепенно разворачиваются в клиентах и могут быть изменены до окончательного выпуска.</span><span class="sxs-lookup"><span data-stu-id="898a9-113">Sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites are gradually rolling out to tenants and might change before final release.</span></span>

<span data-ttu-id="898a9-114">Эта общедоступная предварительная версия не работает в сетях доставки содержимого Office 365 (CDN).</span><span class="sxs-lookup"><span data-stu-id="898a9-114">This public preview doesn't work with Office 365 Content Delivery Networks (CDNs).</span></span>

## <a name="overview"></a><span data-ttu-id="898a9-115">Обзор</span><span class="sxs-lookup"><span data-stu-id="898a9-115">Overview</span></span>

<span data-ttu-id="898a9-116">Когда вы публикуете метки конфиденциальности, пользователи в Office 365 получают доступ к этому списку меток.</span><span class="sxs-lookup"><span data-stu-id="898a9-116">When you publish sensitivity labels, users across Office 365 have access to the same list of labels.</span></span>

<span data-ttu-id="898a9-117">На изображениях ниже показано следующее:</span><span class="sxs-lookup"><span data-stu-id="898a9-117">These images show:</span></span>

- <span data-ttu-id="898a9-118">Способ отображения списка при создании нового сайта группы в SharePoint</span><span class="sxs-lookup"><span data-stu-id="898a9-118">How the list appears when you create a new team site from SharePoint</span></span>

- <span data-ttu-id="898a9-119">Просмотр списка в Word</span><span class="sxs-lookup"><span data-stu-id="898a9-119">When you view the list in Word</span></span>

<span data-ttu-id="898a9-120">Пример:</span><span class="sxs-lookup"><span data-stu-id="898a9-120">For example:</span></span>

![Метка конфиденциальности при создании сайта группы в SharePoint](media/sensitivity-label-new-team-site.png)

![Метка конфиденциальности, отображаемая в классическом приложении Word](media/sensitivity-label-word.png)

## <a name="enable-this-preview"></a><span data-ttu-id="898a9-123">Включение этой предварительной версии</span><span class="sxs-lookup"><span data-stu-id="898a9-123">Enable this preview</span></span>

<span data-ttu-id="898a9-124">Чтобы включить эту предварительную версию меток конфиденциальности в Microsoft Teams, группах Office 365 и на сайтах SharePoint, требуется использовать предварительную версию [Azure AD PowerShell для Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) (название модуля — **AzureADPreview**).</span><span class="sxs-lookup"><span data-stu-id="898a9-124">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) (module name **AzureADPreview**) to enable this preview of sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites:</span></span>

- <span data-ttu-id="898a9-125">Если вы еще не установили ни одной версии модуля Azure AD PowerShell, см. раздел [Установка модуля Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) и следуйте инструкциям по установке общедоступной предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="898a9-125">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="898a9-126">Если у вас установлена общедоступная версия 2.0 модуля Azure AD PowerShell (AzureAD), вам требуется удалить ее, выполнив команду `Uninstall-Module AzureAD` в сеансе PowerShell, а затем установить предварительную версию, выполнив команду `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="898a9-126">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="898a9-127">Если вы уже установили предварительную версию, выполните команду `Install-Module AzureADPreview`, чтобы убедиться, что это последняя версия модуля.</span><span class="sxs-lookup"><span data-stu-id="898a9-127">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="898a9-128">Теперь вы готовы к включению предварительной версии меток конфиденциальности в Microsoft Teams, группах Office 365 и на сайтах SharePoint:</span><span class="sxs-lookup"><span data-stu-id="898a9-128">You're now ready to enable the preview of sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites:</span></span>

1. <span data-ttu-id="898a9-129">В сеансе PowerShell с помощью рабочей или учебной учетной записи с правами глобального администратора подключитесь к Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="898a9-129">In a PowerShell session, using a work or school account that has global admin privileges, connect to Azure Active Directory.</span></span> <span data-ttu-id="898a9-130">Например, выполните команду:</span><span class="sxs-lookup"><span data-stu-id="898a9-130">For example, run:</span></span>
    
    ```powershell
    Connect-AzureAD
    ````
    
    <span data-ttu-id="898a9-131">Подробные инструкции см. в статье [Подключение к Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#connect-to-azure-ad).</span><span class="sxs-lookup"><span data-stu-id="898a9-131">For full instructions, see [Connect to Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#connect-to-azure-ad).</span></span>

2. <span data-ttu-id="898a9-132">Выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="898a9-132">Run the following commands:</span></span>
    
    ```powershell
    $setting=(Get-AzureADDirectorySetting | where -Property DisplayName -Value "Group.Unified" -EQ)
    if ($setting -eq $null)
    {
    $template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b
    $setting = $template.CreateDirectorySetting()
    $setting["EnableMIPLabels"] = "True"
    New-AzureADDirectorySetting -DirectorySetting $setting
    }
    else
    {
    $setting["EnableMIPLabels"] = "True"
    Set-AzureADDirectorySetting -Id $setting.Id -DirectorySetting $setting
    }
    ```
    
    > [!NOTE]
    > <span data-ttu-id="898a9-133">Если вы включите эту предварительную версию, Office 365 больше не будет использовать старые классификации для новых групп и сайтов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="898a9-133">Office 365 no longer uses the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="898a9-134">Если вы использовали [классификацию сайтов Azure AD](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"]), существующие группы и сайты по-прежнему будут отображать старые классификации.</span><span class="sxs-lookup"><span data-stu-id="898a9-134">If you used [Azure AD site classification](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"]), existing groups and sites still display the old classifications.</span></span> <span data-ttu-id="898a9-135">Чтобы отобразить новые классификации, преобразуйте их.</span><span class="sxs-lookup"><span data-stu-id="898a9-135">To display the new classifications, convert them.</span></span> <span data-ttu-id="898a9-136">Сведения о способе преобразования см. в разделе [Если вы использовали классическую классификацию сайтов Azure AD](#if-you-used-classic-azure-ad-site-classification).</span><span class="sxs-lookup"><span data-stu-id="898a9-136">For information about how to convert them, see [If you used classic Azure AD site classification](#if-you-used-classic-azure-ad-site-classification).</span></span> 

3. <span data-ttu-id="898a9-137">В том же сеансе PowerShell подключитесь к Центру безопасности и соответствия требованиям с помощью рабочей или учебной учетной записи с правами глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="898a9-137">In the same PowerShell session, now connect to the Security & Compliance Center by using a work or school account that has global admin privileges.</span></span> <span data-ttu-id="898a9-138">Инструкции см. в статье [Подключение к PowerShell Центра безопасности и соответствия требованиям Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="898a9-138">For instructions, see [Connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

4. <span data-ttu-id="898a9-139">Выполните следующие команды для синхронизации ваших меток с Azure AD, чтобы их можно было использовать с группами Office 365:</span><span class="sxs-lookup"><span data-stu-id="898a9-139">Run the following commands to synchronize your labels to Azure AD, so that they can used with Office 365 groups:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    Execute-AzureAdLabelSync
    ```
## <a name="set-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a><span data-ttu-id="898a9-140">Настройка параметров сайта и группы при создании или изменении меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="898a9-140">Set site and group settings when you create or edit sensitivity labels</span></span>

<span data-ttu-id="898a9-141">Включив предварительную версию, выполните указанные ниже действия, чтобы создать или изменить метки конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="898a9-141">After you enable the preview, use the following steps to create or edit sensitivity labels.</span></span> <span data-ttu-id="898a9-142">Вы должны выполнить эти действия, чтобы новые метки конфиденциальности поддерживались на сайтах и в группах, даже если вы уже определили метки.</span><span class="sxs-lookup"><span data-stu-id="898a9-142">You must complete these steps for the new sensitivity labels to work with sites and groups, even if you already have labels defined.</span></span> <span data-ttu-id="898a9-143">Синхронизация изменений этих параметров может занять до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="898a9-143">Changes to these settings might take up to 24 hours to synchronize.</span></span>

1. <span data-ttu-id="898a9-144">В Центре соответствия требованиям Microsoft 365 выберите **Классификация** > **Метки конфиденциальности**.</span><span class="sxs-lookup"><span data-stu-id="898a9-144">In the Microsoft 365 compliance center, select **Classification** > **Sensitivity labels**.</span></span>

2. <span data-ttu-id="898a9-145">Нажмите **Создать метку**.</span><span class="sxs-lookup"><span data-stu-id="898a9-145">Select **Create a label**.</span></span> <span data-ttu-id="898a9-146">Если у вас уже есть метка, перейдите к следующему действию.</span><span class="sxs-lookup"><span data-stu-id="898a9-146">If you already have a label, skip to the next step.</span></span>

3. <span data-ttu-id="898a9-147">Выберите нужные параметры, а затем на вкладке **Параметры сайта и группы** укажите следующее:</span><span class="sxs-lookup"><span data-stu-id="898a9-147">Select the options you want, and then on the **Site and group settings** tab, choose:</span></span>
    
    - <span data-ttu-id="898a9-148">Конфиденциальность (открытая или закрытая). Вариант "Закрытая" означает, что только утвержденные участники из вашей организации могут просматривать содержимое группы.</span><span class="sxs-lookup"><span data-stu-id="898a9-148">Privacy (Public/Private): Private means that only approved members in your organization can see what's inside the group.</span></span> <span data-ttu-id="898a9-149">Все другие сотрудники вашей организации не могут просматривать содержимое группы.</span><span class="sxs-lookup"><span data-stu-id="898a9-149">Anyone else in your organization can't see what's in the group.</span></span> [<span data-ttu-id="898a9-150">Подробнее</span><span class="sxs-lookup"><span data-stu-id="898a9-150">Learn more</span></span>](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - <span data-ttu-id="898a9-151">Гостевой доступ. Вы можете указать, можно ли добавлять гостей в группу.</span><span class="sxs-lookup"><span data-stu-id="898a9-151">Guest access: You can control if guests can be added to a group.</span></span> [<span data-ttu-id="898a9-152">Сведения об управлении гостевым доступом в группах Office 365</span><span class="sxs-lookup"><span data-stu-id="898a9-152">Learn about managing guest access in Office 365 Groups</span></span>](/office365/admin/create-groups/manage-guest-access-in-groups)
    - <span data-ttu-id="898a9-153">Неуправляемые устройства. Этот параметр позволяет заблокировать или ограничить доступ к контенту SharePoint с устройств, не присоединенных к гибридной среде AD или не соответствующих требованиям в Intune.</span><span class="sxs-lookup"><span data-stu-id="898a9-153">Unmanaged devices: This setting lets you block or limit access to SharePoint content from devices that aren't hybrid AD joined or compliant in Intune.</span></span> <span data-ttu-id="898a9-154">Если вы выбрали неуправляемые устройства, вам потребуется перейти в Azure AD, чтобы завершить настройку политики.</span><span class="sxs-lookup"><span data-stu-id="898a9-154">If you select Unmanaged devices, you must go to Azure AD to finish setting up the policy.</span></span> <span data-ttu-id="898a9-155">Сведения см. в статье [Управление доступом с неуправляемых устройств](/sharepoint/control-access-from-unmanaged-devices).</span><span class="sxs-lookup"><span data-stu-id="898a9-155">For info, see [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span>
    
    ![Вкладка "Параметры сайта и группы"](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="898a9-157">Когда вы применяете метку к команде, группе или сайту, в силу вступают только параметры сайта и группы.</span><span class="sxs-lookup"><span data-stu-id="898a9-157">Only the site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="898a9-158">Другие параметры, например шифрование и маркировка контента, не применяются ко всему содержимому в команде, группе или на сайте.</span><span class="sxs-lookup"><span data-stu-id="898a9-158">Other settings, such as encryption and content marking, aren't applied to all content within the team, group, or site.</span></span>
> 
> <span data-ttu-id="898a9-159">Аналогичным образом, если вы создаете метку и не включаете параметры сайта и группы, метка по-прежнему будет доступна при создании пользователями команд, групп и сайтов, но ее классификация будет использоваться без применения каких-либо параметров.</span><span class="sxs-lookup"><span data-stu-id="898a9-159">Similarly, if you create a label and don't turn on site and group settings, the label will still be available when users create teams, groups, and sites, but it will classify without applying any settings.</span></span>

[<span data-ttu-id="898a9-160">Дополнительные сведения о публикации меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="898a9-160">Learn more about publishing sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="sensitivity-label-management"></a><span data-ttu-id="898a9-161">Управление метками конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="898a9-161">Sensitivity label management</span></span>

> [!WARNING]
> <span data-ttu-id="898a9-162">Создание, изменение и удаление меток конфиденциальности, используемых для Microsoft Teams, групп Office 365 и сайтов SharePoint, требует тщательной координации с политиками публикации меток для пользователей.</span><span class="sxs-lookup"><span data-stu-id="898a9-162">Creating, modifying, and deleting sensitivity labels that you use for Microsoft Teams, Office 365 groups, and SharePoint sites requires careful coordination with publishing label policies to users.</span></span> 

<span data-ttu-id="898a9-163">Чтобы избежать создания ошибок для сайтов и групп, которые могут повлиять на всех пользователей, воспользуйтесь следующим руководством.</span><span class="sxs-lookup"><span data-stu-id="898a9-163">Avoid creation errors for sites and groups that can affect all users by using the following guidance.</span></span>

<span data-ttu-id="898a9-164">**Создание и публикация меток**</span><span class="sxs-lookup"><span data-stu-id="898a9-164">**Creating and publishing labels:**</span></span>

<span data-ttu-id="898a9-165">После создания и публикации метки может потребоваться до 24 часов, чтобы она стала видимой для пользователей команд, групп и сайтов.</span><span class="sxs-lookup"><span data-stu-id="898a9-165">After a sensitivity label is created and published, it can take up to 24 hours for the label to become visible for users in teams, groups, and sites.</span></span> <span data-ttu-id="898a9-166">Чтобы опубликовать метку для всех пользователей в клиенте, используйте следующие действия:</span><span class="sxs-lookup"><span data-stu-id="898a9-166">Use the following steps to publish a label for all users in the tenant:</span></span>

1. <span data-ttu-id="898a9-167">Создайте метку конфиденциальности и опубликуйте ее лишь для нескольких учетных записей пользователей в клиенте.</span><span class="sxs-lookup"><span data-stu-id="898a9-167">Create the sensitivity label and publish it for just a few user accounts in the tenant.</span></span>

2. <span data-ttu-id="898a9-168">Подождите 24 часа.</span><span class="sxs-lookup"><span data-stu-id="898a9-168">Wait for 24 hours.</span></span>

3. <span data-ttu-id="898a9-169">После 24-часового ожидания используйте одну из учетных записей пользователя, указанных в действии 1, чтобы создать команду, группу Office 365 или сайт SharePoint с меткой, созданной в действии 1.</span><span class="sxs-lookup"><span data-stu-id="898a9-169">After this 24 hours wait, use one of the user accounts you specified in step 1 to create a team, Office 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="898a9-170">Если в действии 3 операции создания не возникают ошибки, опубликуйте метку для всех пользователей в клиенте.</span><span class="sxs-lookup"><span data-stu-id="898a9-170">If there are no errors during the creation operation for step 3, publish the label for all users in your tenant.</span></span> <span data-ttu-id="898a9-171">При возникновении ошибок обратитесь в [службу поддержки Майкрософт](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="898a9-171">If there are errors, contact Microsoft Support.</span></span>

<span data-ttu-id="898a9-172">**Изменение и удаление опубликованных меток**</span><span class="sxs-lookup"><span data-stu-id="898a9-172">**Modifying and deleting published labels:**</span></span>

<span data-ttu-id="898a9-173">Если вы изменяете или удаляете метку конфиденциальности, относящуюся к одной или нескольким политикам меток, эти действия могут привести к сбоям при создании любых команд, групп и сайтов.</span><span class="sxs-lookup"><span data-stu-id="898a9-173">If you modify or delete a sensitivity label that is included in one or more label policies, these actions can result in creation failures for all teams, groups, and sites.</span></span> <span data-ttu-id="898a9-174">Чтобы избежать этой ситуации, используйте следующее руководство:</span><span class="sxs-lookup"><span data-stu-id="898a9-174">To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="898a9-175">Удалите метку конфиденциальности из всех политик меток, содержащих ее.</span><span class="sxs-lookup"><span data-stu-id="898a9-175">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="898a9-176">Подождите 48 часов.</span><span class="sxs-lookup"><span data-stu-id="898a9-176">Wait for 48 hours.</span></span>

3. <span data-ttu-id="898a9-177">После 48-часового ожидания попробуйте создать команду, группу или сайт и убедитесь, что метка больше не отображается.</span><span class="sxs-lookup"><span data-stu-id="898a9-177">After the 48 hours wait, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="898a9-178">Если метка конфиденциальности не отображается, вы можете безопасно изменить или удалить ее.</span><span class="sxs-lookup"><span data-stu-id="898a9-178">If the sensitivity label isn't visible, you can now safely modify or delete the label.</span></span> <span data-ttu-id="898a9-179">Если метка по-прежнему отображается, обратитесь в [службу поддержки Майкрософт](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="898a9-179">If the label is still visible, contact Microsoft Support.</span></span>

## <a name="troubleshoot-sensitivity-label-deployment"></a><span data-ttu-id="898a9-180">Устранение неполадок при развертывании меток</span><span class="sxs-lookup"><span data-stu-id="898a9-180">Troubleshoot sensitivity label deployment</span></span>

### <a name="labels-not-visible-after-publishing"></a><span data-ttu-id="898a9-181">Метки не отображаются после публикации</span><span class="sxs-lookup"><span data-stu-id="898a9-181">Labels not visible after publishing</span></span>
<span data-ttu-id="898a9-182">Если вы столкнулись с проблемами при создании команды или группы Office 365 после включения этих параметров или изменения описания метки конфиденциальности, сохраните метку, подождите несколько часов и вновь попробуйте создать команду или группу.</span><span class="sxs-lookup"><span data-stu-id="898a9-182">If you experience issues when you create a team or Office 365 group after you enable these settings or modify a sensitivity label's description, save the label, wait a few hours, and then try to create the team or group again.</span></span> <span data-ttu-id="898a9-183">Сведения см. в разделе [Планирование развертывания после создания или изменения метки конфиденциальности](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span><span class="sxs-lookup"><span data-stu-id="898a9-183">For information, see [Schedule roll-out after you create or change a sensitivity label](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span></span>

<span data-ttu-id="898a9-184">Если вы по-прежнему не видите новую метку конфиденциальности в SharePoint Online, обратитесь в [службу поддержки Майкрософт](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="898a9-184">If you are still not able to see the new sensitivity label from SharePoint Online, contact Microsoft Support.</span></span>

### <a name="team-group-or-sharepoint-site-creation-errors"></a><span data-ttu-id="898a9-185">Ошибки при создании команды, группы или сайта SharePoint</span><span class="sxs-lookup"><span data-stu-id="898a9-185">Team, group, or SharePoint site creation errors</span></span>
<span data-ttu-id="898a9-186">Если у вас возникают ошибки создания при использовании предварительной версии, у вас есть два варианта:</span><span class="sxs-lookup"><span data-stu-id="898a9-186">If you experience creation errors during the public preview, you have two options:</span></span>

- <span data-ttu-id="898a9-187">Убедитесь, что метки конфиденциальности не являются обязательными для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="898a9-187">Ensure that sensitivity labels are not mandatory for any user.</span></span>

- <span data-ttu-id="898a9-188">Вы можете отключить метки конфиденциальности для Microsoft Teams, групп Office 365 и сайтов SharePoint, выполнив те же инструкции из раздела [Включение этой предварительной версии](#enable-this-preview) на этой странице.</span><span class="sxs-lookup"><span data-stu-id="898a9-188">You can turn off sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites by using the same instructions from the [Enable this preview](#enable-this-preview) section on this page.</span></span> <span data-ttu-id="898a9-189">Но чтобы отключить предварительную версию, выполните поиск строки `$setting["EnableMIPLabels"] = "True"` и измените значение **True** на **False**.</span><span class="sxs-lookup"><span data-stu-id="898a9-189">However, to disable the preview, search for the line `$setting["EnableMIPLabels"] = "True"`, and change the **True** value to **False**.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="898a9-190">Применение метки конфиденциальности к новой команде</span><span class="sxs-lookup"><span data-stu-id="898a9-190">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="898a9-191">Пользователи могут выбирать метки конфиденциальности при создании новых команд в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="898a9-191">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="898a9-192">При выборе метки конфиденциальности параметры конфиденциальности изменяются по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="898a9-192">When they select the sensitivity level, the privacy setting changes as necessary.</span></span> <span data-ttu-id="898a9-193">В зависимости параметра гостевого доступа, выбранного для метки, пользователи могут или не могут добавлять в команду людей из-за пределов организации.</span><span class="sxs-lookup"><span data-stu-id="898a9-193">Depending on the guest access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="898a9-194">Дополнительные сведения о метках конфиденциальности для Teams</span><span class="sxs-lookup"><span data-stu-id="898a9-194">Learn more about sensitivity labels for Teams</span></span>](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![Параметр конфиденциальности при создании новой команды](media/privacy-setting-new-team.png)

<span data-ttu-id="898a9-196">После создания команды метка конфиденциальности отображается в правом верхнем углу всех каналов.</span><span class="sxs-lookup"><span data-stu-id="898a9-196">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![Отображение метки конфиденциальности в команде](media/privacy-setting-teams.png)

<span data-ttu-id="898a9-198">Служба автоматически применяет такую же метку конфиденциальности к группе Office 365 и подключенному сайту группы SharePoint.</span><span class="sxs-lookup"><span data-stu-id="898a9-198">The service automatically applies the same sensitivity label to the Office 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group"></a><span data-ttu-id="898a9-199">Применение метки конфиденциальности к новой группе</span><span class="sxs-lookup"><span data-stu-id="898a9-199">Apply a sensitivity label to a new group</span></span>

<span data-ttu-id="898a9-200">В Outlook в Интернете новое поле **Конфиденциальность** содержит опубликованные метки.</span><span class="sxs-lookup"><span data-stu-id="898a9-200">In Outlook on the web, the new **Sensitivity** box contains published labels.</span></span> <span data-ttu-id="898a9-201">Если пользователям нужны дополнительные сведения, они могут щелкнуть значок справки, чтобы ознакомиться с подробностями о доступных метках и связанных политиках.</span><span class="sxs-lookup"><span data-stu-id="898a9-201">If users want more info, they can click the help icon to read details about the available labels and associated policies.</span></span>

![Создание группы и выбор параметра в разделе "Конфиденциальность"](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="898a9-203">Применение метки конфиденциальности к новому сайту</span><span class="sxs-lookup"><span data-stu-id="898a9-203">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="898a9-204">Администраторы и конечные пользователи могут выбирать метки конфиденциальности при создании современных сайтов групп и информационных сайтов.</span><span class="sxs-lookup"><span data-stu-id="898a9-204">Admins and end users can select sensitivity labels when they create modern team sites and communication sites.</span></span>

[<span data-ttu-id="898a9-205">Сведения о создании сайта в новом Центре администрирования SharePoint</span><span class="sxs-lookup"><span data-stu-id="898a9-205">Learn how to create a site in the new SharePoint admin center</span></span>](/sharepoint/create-site-collection)

<span data-ttu-id="898a9-206">Когда пользователи создают современный сайт группы или информационный сайт, метка конфиденциальности уже выбрана по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="898a9-206">When users create modern team and communication sites, a sensitivity label is already selected by default.</span></span> <span data-ttu-id="898a9-207">Пользователи могут щелкнуть значок справки, чтобы узнать больше о метках.</span><span class="sxs-lookup"><span data-stu-id="898a9-207">Users can select the help icon to learn more about the labels.</span></span>

![Создание сайта и выбор параметра в разделе "Конфиденциальность"](media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="898a9-209">Когда пользователь переходит на сайт, он может увидеть имя метки и примененные политики.</span><span class="sxs-lookup"><span data-stu-id="898a9-209">When users browse to the site, they can see the name of the label and applied policies.</span></span>

![Сайт с примененной меткой конфиденциальности](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="898a9-211">Управление метками конфиденциальности в Центре администрирования SharePoint</span><span class="sxs-lookup"><span data-stu-id="898a9-211">Manage sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="898a9-212">Чтобы просмотреть и изменить метки, используйте страницу "Активные сайты" в новом Центре администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="898a9-212">To view and edit the labels, use the Active sites page in the new SharePoint admin center.</span></span>

![Столбец "Конфиденциальность" на странице "Активные сайты"](media/manage-site-sensitivity-labels.png)

<span data-ttu-id="898a9-214">[Дополнительные сведения об управлении сайтами в новом Центре администрирования SharePoint](/sharepoint/manage-sites-in-new-admin-center).</span><span class="sxs-lookup"><span data-stu-id="898a9-214">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="898a9-215">Изменение параметров сайта и группы для метки</span><span class="sxs-lookup"><span data-stu-id="898a9-215">Change site and group settings for a label</span></span>

<span data-ttu-id="898a9-216">Когда осуществляется изменение параметров сайта и группы для метки, требуется выполнить следующие команды PowerShell, чтобы ваши команды, сайты и группы могли использовать новые параметры.</span><span class="sxs-lookup"><span data-stu-id="898a9-216">Whenever you make a change to site and group settings for a label, you must run the following PowerShell commands so that your teams, sites, and groups can use the new settings.</span></span> <span data-ttu-id="898a9-217">Рекомендуется не изменять параметры сайта и группы для метки после применения метки к нескольким командам, группам или сайтам.</span><span class="sxs-lookup"><span data-stu-id="898a9-217">As a best practice, don't the change site and group settings for a label after you've applied the label to several teams, groups, or sites.</span></span>

1. <span data-ttu-id="898a9-218">Выполните следующие команды, чтобы подключиться к PowerShell Центра безопасности и соответствия требованиям Office 365 и получить список меток конфиденциальности и их идентификаторы GUID.</span><span class="sxs-lookup"><span data-stu-id="898a9-218">Run the following commands to connect to Office 365 Security & Compliance Center PowerShell and get the list of sensitivity labels and their GUIDs.</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid
    ```

2. <span data-ttu-id="898a9-219">Запишите GUID для измененных меток.</span><span class="sxs-lookup"><span data-stu-id="898a9-219">Make a note of the GUID for the label or labels you have changed.</span></span>

3. <span data-ttu-id="898a9-220">Подключитесь к Exchange Online PowerShell и выполните командлет Get-UnifiedGroup, указав GUID метки вместо GUID примера "e48058ea-98e8-4940-8db0-ba1310fd955e":</span><span class="sxs-lookup"><span data-stu-id="898a9-220">Now connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span> 
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    $Groups= Get-UnifiedGroup | Where {$_.SensitivityLabel  -eq "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

4. <span data-ttu-id="898a9-221">Для каждой группы повторно примените метку конфиденциальности, указав GUID метки вместо GUID примера "e48058ea-98e8-4940-8db0-ba1310fd955e":</span><span class="sxs-lookup"><span data-stu-id="898a9-221">For each group, reapply the sensitivity label, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span>
    
    ```powershell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

## <a name="support-for-the-new-sensitivity-labels"></a><span data-ttu-id="898a9-222">Поддержка новых меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="898a9-222">Support for the new sensitivity labels</span></span>

<span data-ttu-id="898a9-223">Следующие приложения и службы поддерживают метки конфиденциальности в этой предварительной версии:</span><span class="sxs-lookup"><span data-stu-id="898a9-223">The following apps and services support the sensitivity labels in this preview:</span></span>

- <span data-ttu-id="898a9-224">Центр соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="898a9-224">Microsoft 365 compliance center</span></span>
- <span data-ttu-id="898a9-225">SharePoint</span><span class="sxs-lookup"><span data-stu-id="898a9-225">SharePoint</span></span>
- <span data-ttu-id="898a9-226">Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="898a9-226">Outlook on the web</span></span>
- <span data-ttu-id="898a9-227">Teams</span><span class="sxs-lookup"><span data-stu-id="898a9-227">Teams</span></span>
- <span data-ttu-id="898a9-228">Центр администрирования SharePoint</span><span class="sxs-lookup"><span data-stu-id="898a9-228">SharePoint admin center</span></span>
- <span data-ttu-id="898a9-229">Центр администрирования Azure AD</span><span class="sxs-lookup"><span data-stu-id="898a9-229">Azure AD admin center</span></span>

<span data-ttu-id="898a9-230">Вы не можете использовать следующие приложения и службы для создания групп Office 365 с новыми метками конфиденциальности:</span><span class="sxs-lookup"><span data-stu-id="898a9-230">You can't use the following apps and services to create Office 365 groups with the new sensitivity labels:</span></span>

- <span data-ttu-id="898a9-231">Outlook для Mac</span><span class="sxs-lookup"><span data-stu-id="898a9-231">Outlook for the Mac</span></span>
- <span data-ttu-id="898a9-232">Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="898a9-232">Outlook mobile</span></span>  
- <span data-ttu-id="898a9-233">Классическая версия Outlook для Windows</span><span class="sxs-lookup"><span data-stu-id="898a9-233">Outlook desktop for Windows</span></span>
- <span data-ttu-id="898a9-234">Forms</span><span class="sxs-lookup"><span data-stu-id="898a9-234">Forms</span></span>  
- <span data-ttu-id="898a9-235">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="898a9-235">Dynamics 365</span></span>  
- <span data-ttu-id="898a9-236">Yammer</span><span class="sxs-lookup"><span data-stu-id="898a9-236">Yammer</span></span>  
- <span data-ttu-id="898a9-237">Stream</span><span class="sxs-lookup"><span data-stu-id="898a9-237">Stream</span></span>  
- <span data-ttu-id="898a9-238">Планировщик</span><span class="sxs-lookup"><span data-stu-id="898a9-238">Planner</span></span>  
- <span data-ttu-id="898a9-239">Project</span><span class="sxs-lookup"><span data-stu-id="898a9-239">Project</span></span>  
- <span data-ttu-id="898a9-240">PowerBI</span><span class="sxs-lookup"><span data-stu-id="898a9-240">PowerBI</span></span>  
- <span data-ttu-id="898a9-241">Центр администрирования Teams</span><span class="sxs-lookup"><span data-stu-id="898a9-241">Teams admin center</span></span>  
- <span data-ttu-id="898a9-242">Центр администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="898a9-242">Microsoft 365 admin center</span></span>  
- <span data-ttu-id="898a9-243">Центр администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="898a9-243">Exchange admin center</span></span>

## <a name="if-you-used-classic-azure-ad-site-classification"></a><span data-ttu-id="898a9-244">Если вы использовали классическую классификацию сайтов Azure AD</span><span class="sxs-lookup"><span data-stu-id="898a9-244">If you used classic Azure AD site classification</span></span>

<span data-ttu-id="898a9-245">Если вы включите эту предварительную версию, Office 365 больше не будет поддерживать старые классификации для новых групп и сайтов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="898a9-245">Office 365 no longer supports the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="898a9-246">Однако существующие группы и сайты по-прежнему будут отображать старые классификации, если их не преобразовать.</span><span class="sxs-lookup"><span data-stu-id="898a9-246">However, existing groups and sites still display the old classifications unless you convert them.</span></span> <span data-ttu-id="898a9-247">Старые классификации включают классификацию "современных" сайтов, которую вы настроили, с помощью Azure AD PowerShell или основной библиотеки PnP, определяющей значения параметра `ClassificationList`.</span><span class="sxs-lookup"><span data-stu-id="898a9-247">Old classifications include the "modern" sites classification you set up, possibly through Azure AD PowerShell or the PnP Core library, that defined values for the `ClassificationList` setting.</span></span>

<span data-ttu-id="898a9-248">Например, в PowerShell:</span><span class="sxs-lookup"><span data-stu-id="898a9-248">For example, in PowerShell:</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="898a9-249">Дополнительные сведения о старом методе классификации см. в статье [Классификация "современных" сайтов SharePoint](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span><span class="sxs-lookup"><span data-stu-id="898a9-249">For more information about the old classification method, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="898a9-250">Исходя из текущего развертывания, у вас есть два варианта преобразования старых классификаций в новые.</span><span class="sxs-lookup"><span data-stu-id="898a9-250">Based on your current deployment, you have two options to convert your old classifications to the new classifications.</span></span>

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="898a9-251">Если вы никогда не использовали метки конфиденциальности (единые метки защиты информации (Майкрософт)) для файлов и электронной почты</span><span class="sxs-lookup"><span data-stu-id="898a9-251">If you never used sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="898a9-252">Вот несколько рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="898a9-252">We recommend that you:</span></span>

1. <span data-ttu-id="898a9-253">Создайте метки конфиденциальности в Центре соответствия требованиям Microsoft 365 с такими же именами, как у существующих классификаций.</span><span class="sxs-lookup"><span data-stu-id="898a9-253">Create new sensitivity labels in the Microsoft 365 compliance center that have the same names as your existing classifications.</span></span>
2. <span data-ttu-id="898a9-254">Используйте PowerShell, чтобы применить новые метки к существующим группам Office 365 и сайтам SharePoint с помощью сопоставления имен.</span><span class="sxs-lookup"><span data-stu-id="898a9-254">Use PowerShell to apply the new labels to existing Office 365 groups and SharePoint sites using name mapping.</span></span>
3. <span data-ttu-id="898a9-255">Удалите старые классификации.</span><span class="sxs-lookup"><span data-stu-id="898a9-255">Delete the old classifications.</span></span>

<span data-ttu-id="898a9-256">Приложения и службы, поддерживающие новые метки конфиденциальности, отобразят их.</span><span class="sxs-lookup"><span data-stu-id="898a9-256">Apps and services that support the new sensitivity labels will show them.</span></span> <span data-ttu-id="898a9-257">Вы можете создавать команды, группы и сайты с новыми метками.</span><span class="sxs-lookup"><span data-stu-id="898a9-257">You create new teams, groups, and sites with the new labels.</span></span> <span data-ttu-id="898a9-258">Пользователи по-прежнему смогут создавать группы из приложений и служб, не поддерживающих новые метки.</span><span class="sxs-lookup"><span data-stu-id="898a9-258">Users can still create groups from apps and services that don't support the new labels.</span></span> <span data-ttu-id="898a9-259">Однако пользователи не могут применить метку к этим группам.</span><span class="sxs-lookup"><span data-stu-id="898a9-259">However, users can't apply a label to these groups.</span></span> <span data-ttu-id="898a9-260">Используйте PowerShell, чтобы применить новые метки конфиденциальности к этим группам.</span><span class="sxs-lookup"><span data-stu-id="898a9-260">Use PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="898a9-261">Вы можете сохранить старые классификации, но мы настоятельно рекомендуем использовать PowerShell, чтобы применить новые метки конфиденциальности к этим группам.</span><span class="sxs-lookup"><span data-stu-id="898a9-261">You can keep your old classifications; however, we highly recommend using PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="898a9-262">Приложения и службы, поддерживающие новые метки конфиденциальности, будут созданы с новыми метками.</span><span class="sxs-lookup"><span data-stu-id="898a9-262">Apps and services that support the new sensitivity labels will get created with the new labels.</span></span> <span data-ttu-id="898a9-263">Когда пользователи создают группы из приложений и служб, не поддерживающих новые метки, они могут выбрать классификацию.</span><span class="sxs-lookup"><span data-stu-id="898a9-263">When users create groups from apps and services that don't support the new labels, they can select a classification.</span></span>

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="898a9-264">Если вы используете метки конфиденциальности (единые метки защиты информации (Майкрософт)) для файлов и электронной почты</span><span class="sxs-lookup"><span data-stu-id="898a9-264">If you use sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="898a9-265">Как только вы включите эту предварительную версию, перейдите к каждой метке в Центре соответствия требованиям Microsoft 365 и примените нужные политики для сайтов и групп.</span><span class="sxs-lookup"><span data-stu-id="898a9-265">As soon as you enable this preview, go to each label in the Microsoft 365 compliance center and apply the policies you want for sites and groups.</span></span> <span data-ttu-id="898a9-266">Пользователи смогут просматривать существующие метки, доступные для сайтов и групп.</span><span class="sxs-lookup"><span data-stu-id="898a9-266">Users will start seeing your existing labels available for sites and groups.</span></span>

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a><span data-ttu-id="898a9-267">Подготовка командной консоли SharePoint Online перед переназначением меток групп Office 365</span><span class="sxs-lookup"><span data-stu-id="898a9-267">Prepare the SharePoint Online Management Shell before you relabel Office 365 groups</span></span>

<span data-ttu-id="898a9-268">Перед применением новых меток убедитесь, что вы используете последнюю версию командной консоли SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="898a9-268">Before you apply new labels, ensure that you're running the latest SharePoint Online Management Shell.</span></span> <span data-ttu-id="898a9-269">Если вы уже используете последнюю версию, вы можете продолжить и [переназначить метки групп Office 365 с помощью новых меток конфиденциальности](#relabel-office-365-groups-with-new-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="898a9-269">If you already have the latest version, you can go ahead and [Relabel Office 365 groups with new sensitivity labels](#relabel-office-365-groups-with-new-sensitivity-labels).</span></span>

<span data-ttu-id="898a9-270">Подготовка командной консоли SharePoint Online для предварительной версии:</span><span class="sxs-lookup"><span data-stu-id="898a9-270">To prepare the SharePoint Online Management Shell for the preview:</span></span>

1. <span data-ttu-id="898a9-271">Если вы установили предыдущую версию командной консоли SharePoint Online, перейдите к разделу **Установка и удаление программ** и удалите компонент "Командная консоль SharePoint Online".</span><span class="sxs-lookup"><span data-stu-id="898a9-271">If you installed a previous version of the SharePoint Online Management Shell, go to **Add or remove programs** and uninstall “SharePoint Online Management Shell”.</span></span>

2. <span data-ttu-id="898a9-272">В веб-браузере перейдите на страницу Центра загрузки и [скачайте последнюю версию командной консоли SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="898a9-272">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

3. <span data-ttu-id="898a9-273">Выберите язык и нажмите кнопку **Скачать**.</span><span class="sxs-lookup"><span data-stu-id="898a9-273">Select your language and then click **Download**.</span></span>

4. <span data-ttu-id="898a9-274">Выберите разрядность файла MSI (x64 или x86).</span><span class="sxs-lookup"><span data-stu-id="898a9-274">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="898a9-275">Для 64-разрядной версии Windows скачайте файл x64, а для 32-разрядной — файл x86.</span><span class="sxs-lookup"><span data-stu-id="898a9-275">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you’re run the 32-bit version.</span></span> <span data-ttu-id="898a9-276">Если вы не знаете свою разрядность, см. статью [Какая у меня версия операционной системы Windows?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span><span class="sxs-lookup"><span data-stu-id="898a9-276">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span>

5. <span data-ttu-id="898a9-277">После скачивания файла запустите его и следуйте инструкциям мастера настройки.</span><span class="sxs-lookup"><span data-stu-id="898a9-277">After you download the file, run the file and follow the steps in the Setup Wizard.</span></span>

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a><span data-ttu-id="898a9-278">Переназначение меток групп Office 365 с помощью новых меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="898a9-278">Relabel Office 365 groups with new sensitivity labels</span></span>

1. <span data-ttu-id="898a9-279">Убедитесь, что вы используете последнюю версию командной консоли SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="898a9-279">Ensure that you're using the latest version of the SharePoint Online Management Shell.</span></span> <span data-ttu-id="898a9-280">Инструкции см. в разделе [Подготовка командной консоли SharePoint Online перед переназначением меток групп Office 365](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="898a9-280">For instructions, see [Prepare the SharePoint Online Management Shell before you relabel Office 365 groups](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).</span></span>

2. <span data-ttu-id="898a9-281">Используя рабочую или учебную учетную запись с правами глобального администратора или администратора SharePoint в Office 365, подключитесь к командной консоли SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="898a9-281">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint Online Management Shell.</span></span> <span data-ttu-id="898a9-282">Сведения о том, как это сделать, см. в статье [Начало работы с командной консолью SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="898a9-282">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

3. <span data-ttu-id="898a9-283">Чтобы получить список меток конфиденциальности и их GUID, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="898a9-283">Run the following command to get the list of sensitivity labels and their GUIDs.</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. <span data-ttu-id="898a9-284">Запишите GUID для метки, которую нужно перезаписать.</span><span class="sxs-lookup"><span data-stu-id="898a9-284">Make a note of the GUID for the label you want to overwrite.</span></span> <span data-ttu-id="898a9-285">Например, для метки General (Общее).</span><span class="sxs-lookup"><span data-stu-id="898a9-285">For example, the "General" label.</span></span>

5. <span data-ttu-id="898a9-286">Используйте следующую команду, чтобы получить список групп с классификацией General (Общее).</span><span class="sxs-lookup"><span data-stu-id="898a9-286">Use the following command to get the list of groups that have the “General” classification.</span></span> <span data-ttu-id="898a9-287">При выполнении этой команды нужно подключиться к Exchange Online PowerShell и запустить командлет Get-UnifiedGroup.</span><span class="sxs-lookup"><span data-stu-id="898a9-287">When you run this command, you'll connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet.</span></span>

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="898a9-288">Для каждой группы добавьте GUID новой метки конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="898a9-288">For each group, add the new sensitivity label GUID.</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
