---
title: Использование меток конфиденциальности в Microsoft Teams, группах Office 365 и SharePoint (общедоступная предварительная версия)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/03/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Вы можете применять метки к Microsoft Teams, группам Office 365 и сайтам SharePoint.
ms.openlocfilehash: ebe5e00c3458782e1874274cb508326968461ce3
ms.sourcegitcommit: 1bd81cf48c7fab1b8aaf7c3f550ce42ab02136dc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "39822495"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="5cff9-103">Использование меток конфиденциальности в Microsoft Teams, группах Office 365 и SharePoint (общедоступная предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="5cff9-103">Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>

<span data-ttu-id="5cff9-104">Когда вы создаете метки конфиденциальности в [центре соответствия требованиям microsoft 365](https://protection.office.com/), вы можете применить их к Microsoft Teams, группам Office 365 и сайтам SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5cff9-104">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="5cff9-105">Вы можете связать политики с метками для управления:</span><span class="sxs-lookup"><span data-stu-id="5cff9-105">You can associate policies with the labels to control:</span></span>

- <span data-ttu-id="5cff9-106">Общедоступные и закрытые параметры</span><span class="sxs-lookup"><span data-stu-id="5cff9-106">Public/private settings</span></span>
- <span data-ttu-id="5cff9-107">Гостевой доступ</span><span class="sxs-lookup"><span data-stu-id="5cff9-107">Guest access</span></span>
- <span data-ttu-id="5cff9-108">Доступ с неуправляемых устройств</span><span class="sxs-lookup"><span data-stu-id="5cff9-108">Access from unmanaged devices</span></span>

<span data-ttu-id="5cff9-109">Когда вы применяете метку к группе или группе, метка автоматически применяется к подключенному сайту группы SharePoint и наоборот.</span><span class="sxs-lookup"><span data-stu-id="5cff9-109">When you apply a label to a team or group, the label automatically applies to the connected SharePoint team site and the other way around.</span></span>

<span data-ttu-id="5cff9-110">Теперь вы также можете включить метки конфиденциальности для файлов Office в SharePoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="5cff9-110">Now, You can also enable sensitivity labels for Office files in SharePoint and OneDrive.</span></span> <span data-ttu-id="5cff9-111">[Подробнее](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="5cff9-111">[Learn more](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a><span data-ttu-id="5cff9-112">Общие сведения об общедоступной предварительной версии для Microsoft Teams, Office 365 Groups и сайтов SharePoint</span><span class="sxs-lookup"><span data-stu-id="5cff9-112">About the public preview for Microsoft Teams, Office 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="5cff9-113">Метки конфиденциальности для Microsoft Teams, групп Office 365 и сайтов SharePoint постепенно выходят на клиентов и могут быть изменены до окончательного выпуска.</span><span class="sxs-lookup"><span data-stu-id="5cff9-113">Sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites is gradually rolling out to tenants and might change before final release.</span></span>

<span data-ttu-id="5cff9-114">Общедоступная Предварительная версия не работает с сетями доставки содержимого Office 365 (сети CDN).</span><span class="sxs-lookup"><span data-stu-id="5cff9-114">The public preview doesn't work with Office 365 Content Delivery Networks (CDNs).</span></span>

## <a name="overview"></a><span data-ttu-id="5cff9-115">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="5cff9-115">Overview</span></span>

<span data-ttu-id="5cff9-116">При публикации меток конфиденциальности пользователи в Office 365 имеют доступ к одному и тому же списку меток.</span><span class="sxs-lookup"><span data-stu-id="5cff9-116">When you publish sensitivity labels, users across Office 365 have access to the same list of labels.</span></span>

<span data-ttu-id="5cff9-117">На этих изображениях показаны:</span><span class="sxs-lookup"><span data-stu-id="5cff9-117">These images show:</span></span>

- <span data-ttu-id="5cff9-118">Способ отображения списка при создании нового сайта группы из SharePoint</span><span class="sxs-lookup"><span data-stu-id="5cff9-118">How the list appears when you create a new team site from SharePoint</span></span>

- <span data-ttu-id="5cff9-119">При просмотре списка в Word</span><span class="sxs-lookup"><span data-stu-id="5cff9-119">When you view the list in Word</span></span>

![Метка чувствительности при создании сайта группы из SharePoint](media/sensitivity-label-new-team-site.png)

![Метка конфиденциальности, отображаемая в классическом приложении Word](media/sensitivity-label-word.png)

## <a name="enable-this-preview-by-using-azure-powershell"></a><span data-ttu-id="5cff9-122">Включение этого предварительного просмотра с помощью Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="5cff9-122">Enable this preview by using Azure PowerShell</span></span>

1. <span data-ttu-id="5cff9-123">Войдите в Azure как глобальный администратор с помощью Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5cff9-123">Sign in to Azure as a global admin by using Azure PowerShell.</span></span> <span data-ttu-id="5cff9-124">Инструкции можно найти [в разделе Вход с помощью Azure PowerShell](/powershell/azure/authenticate-azureps).</span><span class="sxs-lookup"><span data-stu-id="5cff9-124">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="5cff9-125">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5cff9-125">Run the following command:</span></span>

```powershell
  Connect-AzureAD
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

<span data-ttu-id="5cff9-126">Office 365 больше не использует старые классификации для новых групп и сайтов SharePoint при включении этого предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="5cff9-126">Office 365 no longer uses the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="5cff9-127">Если вы использовали [классификацию сайтов Azure AD](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($Setting ["классификатионлист"]), существующие группы и сайты по-прежнему будут отображать старые классификации.</span><span class="sxs-lookup"><span data-stu-id="5cff9-127">If you used [Azure AD site classification](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"]), existing groups and sites still display the old classifications.</span></span> <span data-ttu-id="5cff9-128">Чтобы отобразить новые классификации, преобразуйте их.</span><span class="sxs-lookup"><span data-stu-id="5cff9-128">To display the new classifications, convert them.</span></span> <span data-ttu-id="5cff9-129">Сведения о том, как их преобразовать, можно узнать в статье [использование классического класса классификации сайта Azure AD](#if-you-used-classic-azure-ad-site-classification).</span><span class="sxs-lookup"><span data-stu-id="5cff9-129">For information about how to convert them, see [If you used classic Azure AD site classification](#if-you-used-classic-azure-ad-site-classification).</span></span> 

## <a name="set-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a><span data-ttu-id="5cff9-130">Настройка параметров сайтов и групп при создании или изменении меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="5cff9-130">Set site and group settings when you create or edit sensitivity labels</span></span>

<span data-ttu-id="5cff9-131">После включения предварительного просмотра выполните следующие действия, чтобы создать или изменить метки конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="5cff9-131">After you enable the preview, follow these steps to create or edit sensitivity labels.</span></span> <span data-ttu-id="5cff9-132">Вы должны выполнить эти действия, чтобы новые метки чувствительности работали с сайтами и группами, даже если вы уже определили метки.</span><span class="sxs-lookup"><span data-stu-id="5cff9-132">You must complete these steps for the new sensitivity labels to work with sites and groups, even if you already have labels defined.</span></span> <span data-ttu-id="5cff9-133">Для изменения этих параметров может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="5cff9-133">Changes to these settings may take up to 24 hours sync.</span></span>

1. <span data-ttu-id="5cff9-134">В центре соответствия требованиям Microsoft 365 выберите**метки чувствительности** **классификации** > .</span><span class="sxs-lookup"><span data-stu-id="5cff9-134">In the Microsoft 365 compliance center, select **Classification** > **Sensitivity labels**.</span></span>

2. <span data-ttu-id="5cff9-135">Выберите **создать метку**.</span><span class="sxs-lookup"><span data-stu-id="5cff9-135">Select **Create a label**.</span></span> <span data-ttu-id="5cff9-136">Если у вас уже есть метка, перейдите к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="5cff9-136">If you already have a label, skip to the next step.</span></span>

3. <span data-ttu-id="5cff9-137">Выберите нужные параметры, а затем на вкладке **Параметры сайта и группы** выберите:</span><span class="sxs-lookup"><span data-stu-id="5cff9-137">Select the options you want, and then on the **Site and group settings** tab, choose:</span></span>

    - <span data-ttu-id="5cff9-138">Конфиденциальность (общедоступная или частная): Частная означает, что в группе могут видеть только утвержденные участники.</span><span class="sxs-lookup"><span data-stu-id="5cff9-138">Privacy (Public/Private): Private means only approved members in your organization can see what's inside the group.</span></span> <span data-ttu-id="5cff9-139">Все остальные пользователи в вашей организации не могут видеть содержимое группы.</span><span class="sxs-lookup"><span data-stu-id="5cff9-139">Anyone else in your organization can't see what's in the group.</span></span> [<span data-ttu-id="5cff9-140">Подробнее</span><span class="sxs-lookup"><span data-stu-id="5cff9-140">Learn more</span></span>](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - <span data-ttu-id="5cff9-141">Гостевой доступ: вы можете указать, можно ли добавлять гостей в группу.</span><span class="sxs-lookup"><span data-stu-id="5cff9-141">Guest access: You can control if guests can be added to a group.</span></span> [<span data-ttu-id="5cff9-142">Сведения об управлении гостевым доступом в группах Office 365</span><span class="sxs-lookup"><span data-stu-id="5cff9-142">Learn about managing guest access in Office 365 Groups</span></span>](/office365/admin/create-groups/manage-guest-access-in-groups)
    - <span data-ttu-id="5cff9-143">Неуправляемые устройства: этот параметр позволяет заблокировать или ограничить доступ к контенту SharePoint с устройств, не являющихся гибридными или не связанными с Intune в Intune.</span><span class="sxs-lookup"><span data-stu-id="5cff9-143">Unmanaged devices: This setting lets you block or limit access to SharePoint content from devices that aren't hybrid AD joined or compliant in Intune.</span></span> <span data-ttu-id="5cff9-144">Если вы выбрали неуправляемые устройства, вам нужно перейти в Azure AD, чтобы завершить настройку политики.</span><span class="sxs-lookup"><span data-stu-id="5cff9-144">If you select Unmanaged devices, you need to go to Azure AD to finish setting up the policy.</span></span> <span data-ttu-id="5cff9-145">Сведения см. [в статье Управление доступом с неуправляемых устройств](/sharepoint/control-access-from-unmanaged-devices).</span><span class="sxs-lookup"><span data-stu-id="5cff9-145">For info, see [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span>

![Вкладка "Параметры сайта и групп"](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="5cff9-147">Только параметры сайта и групп вступают в силу при применении метки к команде, группе или сайту.</span><span class="sxs-lookup"><span data-stu-id="5cff9-147">Only the site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="5cff9-148">Другие параметры, такие как шифрование и маркировка содержимого, не применяются ко всему контенту в группе, группе или на сайте.</span><span class="sxs-lookup"><span data-stu-id="5cff9-148">Other settings, such as encryption and content marking, aren't applied to all content within the team, group, or site.</span></span> <span data-ttu-id="5cff9-149">Аналогичным образом, если вы создаете метку и не включаете параметры сайта и группы, метка будет доступна, когда пользователи создают команды, группы и сайты, но не будут ничего делать при его применении пользователями.</span><span class="sxs-lookup"><span data-stu-id="5cff9-149">Similarly, if you create a label and don't turn on site and group settings, the label will still be available when users create teams, groups, and sites, but it won't do anything when users apply it.</span></span>

[<span data-ttu-id="5cff9-150">Сведения о публикации метки чувствительности</span><span class="sxs-lookup"><span data-stu-id="5cff9-150">Learn how to publish a sensitivity label</span></span>](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="troubleshoot-sensitivity-label-deployment"></a><span data-ttu-id="5cff9-151">Устранение проблем с развертыванием меток чувствительности</span><span class="sxs-lookup"><span data-stu-id="5cff9-151">Troubleshoot sensitivity label deployment</span></span>

<span data-ttu-id="5cff9-152">Если при создании группы или группы Office 365 возникают проблемы, после того как вы включите эти параметры или внесете изменения в описание метки конфиденциальности, сохраните метку, подождите несколько часов, а затем попробуйте создать группу или группу Office 365 еще раз.</span><span class="sxs-lookup"><span data-stu-id="5cff9-152">If you experience issues when you create a Teams or Office 365 group after you enable these settings or make a change to a sensitivity label's description, save the label, wait a few hours, and then try to create the Team or Office 365 group again.</span></span>

<span data-ttu-id="5cff9-153">Если вы по-прежнему не можете увидеть новую метку конфиденциальности в SharePoint Online, немедленно обратитесь в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5cff9-153">If you are still not able to see the new sensitivity label from SharePoint Online, then contact Microsoft Support immediately.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="5cff9-154">Применение метки конфиденциальности к новой команде</span><span class="sxs-lookup"><span data-stu-id="5cff9-154">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="5cff9-155">Пользователи могут выбирать метки конфиденциальности при создании новых команд в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5cff9-155">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="5cff9-156">При выборе уровня чувствительности параметры конфиденциальности изменяются по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="5cff9-156">When they select the sensitivity level, the privacy setting changes as necessary.</span></span> <span data-ttu-id="5cff9-157">В зависимости от параметров гостевого доступа, выбранных для метки, пользователи могут или не могут добавлять людей, не входящих в организацию, в команду.</span><span class="sxs-lookup"><span data-stu-id="5cff9-157">Depending on the guest access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

![Параметр конфиденциальности при создании новой команды](media/privacy-setting-new-team.png)

<span data-ttu-id="5cff9-159">После создания команды метка чувствительности отображается в правом верхнем углу всех каналов.</span><span class="sxs-lookup"><span data-stu-id="5cff9-159">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![Метка чувствительности отображается в команде](media/privacy-setting-teams.png)

<span data-ttu-id="5cff9-161">Служба автоматически применяет ту же метку конфиденциальности к группе Office 365 и подключенному сайту группы SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5cff9-161">The service automatically applies the same sensitivity label to the Office 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group"></a><span data-ttu-id="5cff9-162">Применение метки конфиденциальности к новой группе</span><span class="sxs-lookup"><span data-stu-id="5cff9-162">Apply a sensitivity label to a new group</span></span>

<span data-ttu-id="5cff9-163">В Outlook в Интернете новое поле " **чувствительность** " содержит опубликованные метки.</span><span class="sxs-lookup"><span data-stu-id="5cff9-163">In Outlook on the web, the new **Sensitivity** box contains published labels.</span></span> <span data-ttu-id="5cff9-164">Если пользователям нужна дополнительная информация, они могут щелкнуть значок Справка, чтобы прочитать сведения о доступных метках и связанных с ними политиках.</span><span class="sxs-lookup"><span data-stu-id="5cff9-164">If users want more info, they can click the help icon to read details about the available labels and associated policies.</span></span>

![Создание группы и выбор параметра в разделе чувствительность](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="5cff9-166">Применение метки конфиденциальности к новому сайту</span><span class="sxs-lookup"><span data-stu-id="5cff9-166">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="5cff9-167">Администраторы и конечные пользователи могут выбирать метки конфиденциальности при создании современных сайтов группы и сайтов для общения.</span><span class="sxs-lookup"><span data-stu-id="5cff9-167">Admins and end users can select sensitivity labels when they create modern team sites and communication sites.</span></span>

[<span data-ttu-id="5cff9-168">Узнайте, как создать сайт в новом центре администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5cff9-168">Learn how to create a site in the new SharePoint admin center</span></span>](/sharepoint/create-site-collection)

<span data-ttu-id="5cff9-169">Когда пользователи создают современные группы и сайты для общения, метка чувствительности уже выбрана по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5cff9-169">When users create modern team and communication sites, a sensitivity label is already selected by default.</span></span> <span data-ttu-id="5cff9-170">Пользователи могут выбрать значок справки, чтобы узнать больше о метках.</span><span class="sxs-lookup"><span data-stu-id="5cff9-170">Users can select the help icon to learn more about the labels.</span></span>

![Создание сайта и выбор параметра в соответствии с чувствительностью](media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="5cff9-172">Когда пользователи просматривают сайт, они могут видеть имя метки и примененные политики.</span><span class="sxs-lookup"><span data-stu-id="5cff9-172">When users browse to the site, they can see the name of the label and applied policies.</span></span>

![Сайт, к которому применена метка чувствительности](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="5cff9-174">Управление метками конфиденциальности в центре администрирования SharePoint</span><span class="sxs-lookup"><span data-stu-id="5cff9-174">Manage sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="5cff9-175">Для просмотра и редактирования меток используйте страницу "активные сайты" в новом центре администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5cff9-175">To view and edit the labels, use the Active sites page in the new SharePoint admin center.</span></span>

![Столбец "чувствительность" на странице активных сайтов](media/manage-site-sensitivity-labels.png)

<span data-ttu-id="5cff9-177">[Узнайте больше об управлении сайтами в новом центре администрирования SharePoint](/sharepoint/manage-sites-in-new-admin-center).</span><span class="sxs-lookup"><span data-stu-id="5cff9-177">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="5cff9-178">Изменение параметров сайта и группы для метки</span><span class="sxs-lookup"><span data-stu-id="5cff9-178">Change site and group settings for a label</span></span>

<span data-ttu-id="5cff9-179">Рекомендуется не изменять параметры после применения метки к нескольким командам, группам или сайтам.</span><span class="sxs-lookup"><span data-stu-id="5cff9-179">As a best practice, don't change settings after you've applied a label to several teams, groups, or sites.</span></span> <span data-ttu-id="5cff9-180">Если необходимо внести изменения, необходимо использовать сценарий PowerShell для Azure AD для применения обновлений вручную.</span><span class="sxs-lookup"><span data-stu-id="5cff9-180">If you must make a change, you'll need to use an Azure AD PowerShell script to manually apply updates.</span></span> <span data-ttu-id="5cff9-181">Этот метод обеспечивает применение нового параметра ко всем существующим командам, сайтам и группам.</span><span class="sxs-lookup"><span data-stu-id="5cff9-181">This method ensures all existing teams, sites, and groups enforce the new setting.</span></span>

## <a name="support-for-the-new-sensitivity-labels"></a><span data-ttu-id="5cff9-182">Поддержка новых меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="5cff9-182">Support for the new sensitivity labels</span></span>

<span data-ttu-id="5cff9-183">Следующие приложения и службы поддерживают метки конфиденциальности в данном предварительном просмотре:</span><span class="sxs-lookup"><span data-stu-id="5cff9-183">The following apps and services support the sensitivity labels in this preview:</span></span>

- <span data-ttu-id="5cff9-184">Центр соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5cff9-184">Microsoft 365 compliance center</span></span>
- <span data-ttu-id="5cff9-185">SharePoint</span><span class="sxs-lookup"><span data-stu-id="5cff9-185">SharePoint</span></span>
- <span data-ttu-id="5cff9-186">Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="5cff9-186">Outlook on the web</span></span>
- <span data-ttu-id="5cff9-187">Teams</span><span class="sxs-lookup"><span data-stu-id="5cff9-187">Teams</span></span>
- <span data-ttu-id="5cff9-188">Центр администрирования SharePoint</span><span class="sxs-lookup"><span data-stu-id="5cff9-188">SharePoint admin center</span></span>
- <span data-ttu-id="5cff9-189">Центр администрирования Azure AD</span><span class="sxs-lookup"><span data-stu-id="5cff9-189">Azure AD admin center</span></span>

<span data-ttu-id="5cff9-190">Вы не можете использовать следующие приложения и службы для создания групп Office 365 с новыми метками конфиденциальности:</span><span class="sxs-lookup"><span data-stu-id="5cff9-190">You can't use the following apps and services to create Office 365 groups with the new sensitivity labels:</span></span>

- <span data-ttu-id="5cff9-191">Outlook для Mac</span><span class="sxs-lookup"><span data-stu-id="5cff9-191">Outlook for the Mac</span></span>
- <span data-ttu-id="5cff9-192">Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="5cff9-192">Outlook mobile</span></span>  
- <span data-ttu-id="5cff9-193">Настольный Outlook для Windows</span><span class="sxs-lookup"><span data-stu-id="5cff9-193">Outlook desktop for Windows</span></span>
- <span data-ttu-id="5cff9-194">Forms</span><span class="sxs-lookup"><span data-stu-id="5cff9-194">Forms</span></span>  
- <span data-ttu-id="5cff9-195">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="5cff9-195">Dynamics 365</span></span>  
- <span data-ttu-id="5cff9-196">Yammer</span><span class="sxs-lookup"><span data-stu-id="5cff9-196">Yammer</span></span>  
- <span data-ttu-id="5cff9-197">Stream</span><span class="sxs-lookup"><span data-stu-id="5cff9-197">Stream</span></span>  
- <span data-ttu-id="5cff9-198">Планировщик</span><span class="sxs-lookup"><span data-stu-id="5cff9-198">Planner</span></span>  
- <span data-ttu-id="5cff9-199">Project</span><span class="sxs-lookup"><span data-stu-id="5cff9-199">Project</span></span>  
- <span data-ttu-id="5cff9-200">PowerBI</span><span class="sxs-lookup"><span data-stu-id="5cff9-200">PowerBI</span></span>  
- <span data-ttu-id="5cff9-201">Центр администрирования Teams</span><span class="sxs-lookup"><span data-stu-id="5cff9-201">Teams admin center</span></span>  
- <span data-ttu-id="5cff9-202">Центр администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5cff9-202">Microsoft 365 admin center</span></span>  
- <span data-ttu-id="5cff9-203">Центр администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="5cff9-203">Exchange admin center</span></span>

## <a name="if-you-used-classic-azure-ad-site-classification"></a><span data-ttu-id="5cff9-204">Если вы использовали классическую классификацию сайтов Azure AD</span><span class="sxs-lookup"><span data-stu-id="5cff9-204">If you used classic Azure AD site classification</span></span>

<span data-ttu-id="5cff9-205">Office 365 больше не поддерживает старые классификации для новых групп и сайтов SharePoint при включении этого предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="5cff9-205">Office 365 no longer supports the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="5cff9-206">Однако существующие группы и сайты по-прежнему отображают старые классификации, пока не будут преобразованы.</span><span class="sxs-lookup"><span data-stu-id="5cff9-206">However, existing groups and sites still display the old classifications unless you convert them.</span></span> <span data-ttu-id="5cff9-207">Старые классификации включают "современные классификации сайтов, которые вы настроили, возможно, с помощью Azure AD PowerShell или библиотеки ядра PnP, которые задают определенные `ClassificationList` значения параметра.</span><span class="sxs-lookup"><span data-stu-id="5cff9-207">Old classifications include the "modern" sites classification you set up, possibly through Azure AD PowerShell or the PnP Core library, that defined values for the `ClassificationList` setting.</span></span>

<span data-ttu-id="5cff9-208">Например, в PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5cff9-208">For example, in PowerShell:</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="5cff9-209">Дополнительные сведения о старом методе классификации можно найти в разделе ["современные" классификации сайтов SharePoint](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span><span class="sxs-lookup"><span data-stu-id="5cff9-209">For more information about the old classification method, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="5cff9-210">В зависимости от текущего развертывания у вас есть два варианта преобразования старых классификаций в новые классификации.</span><span class="sxs-lookup"><span data-stu-id="5cff9-210">Based on your current deployment, you have two options to convert your old classifications to the new classifications.</span></span>

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="5cff9-211">Если вы никогда не использовали метки чувствительности (единой системы меток защиты информации Майкрософт) для файлов и электронной почты</span><span class="sxs-lookup"><span data-stu-id="5cff9-211">If you never used sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="5cff9-212">Мы рекомендуем вам:</span><span class="sxs-lookup"><span data-stu-id="5cff9-212">We recommend that you:</span></span>

1. <span data-ttu-id="5cff9-213">Создайте новые метки конфиденциальности в центре соответствия требованиям Microsoft 365, имена которых совпадают с именами существующих классификаций.</span><span class="sxs-lookup"><span data-stu-id="5cff9-213">Create new sensitivity labels in the Microsoft 365 compliance center that have the same names as your existing classifications.</span></span>
2. <span data-ttu-id="5cff9-214">Используйте PowerShell, чтобы применить новые метки к существующим группам Office 365 и сайтам SharePoint с помощью сопоставления имен.</span><span class="sxs-lookup"><span data-stu-id="5cff9-214">Use PowerShell to apply the new labels to existing Office 365 groups and SharePoint sites using name mapping.</span></span>
3. <span data-ttu-id="5cff9-215">Удалите старые классификации.</span><span class="sxs-lookup"><span data-stu-id="5cff9-215">Delete the old classifications.</span></span>

<span data-ttu-id="5cff9-216">Приложения и службы, которые поддерживают новые метки конфиденциальности, отобразят их.</span><span class="sxs-lookup"><span data-stu-id="5cff9-216">Apps and services that support the new sensitivity labels will show them.</span></span> <span data-ttu-id="5cff9-217">Новые метки создаются в новых командах, группах и сайтах.</span><span class="sxs-lookup"><span data-stu-id="5cff9-217">You create new teams, groups, and sites with the new labels.</span></span> <span data-ttu-id="5cff9-218">Пользователи по-прежнему могут создавать группы из приложений и служб, которые не поддерживают новые метки.</span><span class="sxs-lookup"><span data-stu-id="5cff9-218">Users can still create groups from apps and services that don't support the new labels.</span></span> <span data-ttu-id="5cff9-219">Однако пользователи не могут применить метку к этим группам.</span><span class="sxs-lookup"><span data-stu-id="5cff9-219">However, users can't apply a label to these groups.</span></span> <span data-ttu-id="5cff9-220">Используйте PowerShell, чтобы применить новые метки конфиденциальности для этих групп.</span><span class="sxs-lookup"><span data-stu-id="5cff9-220">Use PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="5cff9-221">Вы можете хранить старые классификации; Однако настоятельно рекомендуется использовать PowerShell, чтобы применить новые метки конфиденциальности к этим группам.</span><span class="sxs-lookup"><span data-stu-id="5cff9-221">You can keep your old classifications; however, we highly recommend using PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="5cff9-222">Приложения и службы, которые поддерживают новые метки конфиденциальности, будут созданы с новыми метками.</span><span class="sxs-lookup"><span data-stu-id="5cff9-222">Apps and services that support the new sensitivity labels will get created with the new labels.</span></span> <span data-ttu-id="5cff9-223">Когда пользователи создают группы из приложений и служб, которые не поддерживают новые метки, они могут выбрать классификацию.</span><span class="sxs-lookup"><span data-stu-id="5cff9-223">When users create groups from apps and services that don't support the new labels, they can select a classification.</span></span>

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="5cff9-224">Если вы используете метки конфиденциальности (Объединенные метки информационной защиты Майкрософт) для файлов и электронной почты</span><span class="sxs-lookup"><span data-stu-id="5cff9-224">If you use sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="5cff9-225">После включения этого предварительного просмотра перейдите к каждой метке в центре соответствия требованиям Microsoft 365 и примените нужные политики для сайтов и групп.</span><span class="sxs-lookup"><span data-stu-id="5cff9-225">As soon as you enable this preview, go to each label in the Microsoft 365 compliance center and apply the policies you want for sites and groups.</span></span> <span data-ttu-id="5cff9-226">Пользователи начнут просматривать существующие метки, доступные для сайтов и групп.</span><span class="sxs-lookup"><span data-stu-id="5cff9-226">Users will start seeing your existing labels available for sites and groups.</span></span>

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a><span data-ttu-id="5cff9-227">Подготовка командной консоли SharePoint Online перед переразметкой групп Office 365</span><span class="sxs-lookup"><span data-stu-id="5cff9-227">Prepare the SharePoint Online Management Shell before you relabel Office 365 groups</span></span>

<span data-ttu-id="5cff9-228">Перед применением новых меток убедитесь, что вы используете последнюю версию командной консоли SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5cff9-228">Before you apply new labels, ensure that you're running the latest SharePoint Online Management Shell.</span></span> <span data-ttu-id="5cff9-229">Если у вас уже есть последняя версия, вы можете [переметить группы Office 365 с помощью новых меток конфиденциальности](#relabel-office-365-groups-with-new-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="5cff9-229">If you already have the latest version, you can go ahead and [Relabel Office 365 groups with new sensitivity labels](#relabel-office-365-groups-with-new-sensitivity-labels).</span></span>

<span data-ttu-id="5cff9-230">Подготовка командной консоли SharePoint Online для предварительного просмотра:</span><span class="sxs-lookup"><span data-stu-id="5cff9-230">To prepare the SharePoint Online Management Shell for the preview:</span></span>

1. <span data-ttu-id="5cff9-231">Если вы установили предыдущую версию командной консоли SharePoint Online, перейдите к разделу **Установка и удаление программ** и удаление "Командная консоль SharePoint Online".</span><span class="sxs-lookup"><span data-stu-id="5cff9-231">If you installed a previous version of the SharePoint Online Management Shell, go to **Add or remove programs** and uninstall “SharePoint Online Management Shell”.</span></span>

2. <span data-ttu-id="5cff9-232">В веб-браузере перейдите на страницу центра загрузки и [скачайте последнюю версию командной консоли SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="5cff9-232">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

3. <span data-ttu-id="5cff9-233">Выберите язык и нажмите кнопку **скачать**.</span><span class="sxs-lookup"><span data-stu-id="5cff9-233">Select your language and then click **Download**.</span></span>

4. <span data-ttu-id="5cff9-234">Выберите файл в формате x64 и x86. msi.</span><span class="sxs-lookup"><span data-stu-id="5cff9-234">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="5cff9-235">Скачайте файл x64, если вы используете 64-разрядную версию Windows или файл x86, если вы запускаете 32-разрядную версию.</span><span class="sxs-lookup"><span data-stu-id="5cff9-235">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you’re run the 32-bit version.</span></span> <span data-ttu-id="5cff9-236">Если вы не знаете, посмотрите, [какая версия операционной системы Windows работает?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span><span class="sxs-lookup"><span data-stu-id="5cff9-236">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span>

5. <span data-ttu-id="5cff9-237">После загрузки файла запустите его и следуйте указаниям мастера установки.</span><span class="sxs-lookup"><span data-stu-id="5cff9-237">After you download the file, run the file and follow the steps in the Setup Wizard.</span></span>

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a><span data-ttu-id="5cff9-238">Переразметка групп Office 365 с помощью новых меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="5cff9-238">Relabel Office 365 groups with new sensitivity labels</span></span>

1. <span data-ttu-id="5cff9-239">Убедитесь, что вы используете последнюю версию командной консоли SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5cff9-239">Ensure that you're using the latest version of the SharePoint Online Management Shell.</span></span> <span data-ttu-id="5cff9-240">Инструкции можно найти [в статье Подготовка командной консоли SharePoint Online перед переразметкой групп Office 365](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="5cff9-240">For instructions, see [Prepare the SharePoint Online Management Shell before you relabel Office 365 groups](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).</span></span>

2. <span data-ttu-id="5cff9-241">С помощью рабочей или учебной учетной записи, имеющей права глобального администратора или администратора SharePoint в Office 365, подключитесь к консоли управления SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5cff9-241">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint Online Management Shell.</span></span> <span data-ttu-id="5cff9-242">Сведения о том, как это сделать, см. в статье [Начало работы с командной консолью SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="5cff9-242">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

3. <span data-ttu-id="5cff9-243">Выполните следующую команду, чтобы получить список меток конфиденциальности и их идентификаторы GUID.</span><span class="sxs-lookup"><span data-stu-id="5cff9-243">Run the following command to get the list of sensitivity labels and their GUIDs.</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. <span data-ttu-id="5cff9-244">Запишите GUID для метки, которую требуется перезаписать.</span><span class="sxs-lookup"><span data-stu-id="5cff9-244">Make a note of the GUID for the label you want to overwrite.</span></span> <span data-ttu-id="5cff9-245">Например, метка "Общие".</span><span class="sxs-lookup"><span data-stu-id="5cff9-245">For example, the "General" label.</span></span>

5. <span data-ttu-id="5cff9-246">Используйте следующую команду, чтобы получить список групп с классификацией "общий".</span><span class="sxs-lookup"><span data-stu-id="5cff9-246">Use the following command to get the list of groups that have the “General” classification.</span></span> <span data-ttu-id="5cff9-247">При выполнении этой команды вы будете подключаться к Exchange Online PowerShell и исполняем командлет Get-UnifiedGroup.</span><span class="sxs-lookup"><span data-stu-id="5cff9-247">When you run this command, you'll connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet.</span></span>

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   ```

6. <span data-ttu-id="5cff9-248">Для каждой группы добавьте новый GUID метки чувствительности.</span><span class="sxs-lookup"><span data-stu-id="5cff9-248">For each group, add the new sensitivity label GUID.</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
