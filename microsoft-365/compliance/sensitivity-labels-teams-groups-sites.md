---
title: Использование меток конфиденциальности на сайтах Microsoft Teams, в группах Microsoft 365 и на сайтах SharePoint (общедоступная предварительная версия)
f1.keywords:
- NOCSH
ms.author: cabailey
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
description: Чтобы защитить контент на сайтах SharePoint и Microsoft Teams, а также в группах Microsoft 365, используйте метки конфиденциальности.
ms.openlocfilehash: ead28675a24b0364b89948fe582277862eaab3b8
ms.sourcegitcommit: e9cb10d0d617742a5040d7c09d1d36fd1ee25e5d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "44649408"
---
# <a name="use-sensitivity-labels-to-protect-content-in-microsoft-teams-microsoft-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="554ab-103">Использование меток конфиденциальности для защиты контента на сайтах Microsoft Teams, в группах Microsoft 365 и на сайтах SharePoint (общедоступная предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="554ab-103">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites (public preview)</span></span>

><span data-ttu-id="554ab-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="554ab-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="554ab-105">Создав метки конфиденциальности в [Центре соответствия требованиям Microsoft 365](https://protection.office.com/), вы можете применять их к следующим контейнерам: сайты Microsoft Teams, группы Microsoft 365 ([прежнее название — группы Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) и сайты SharePoint.</span><span class="sxs-lookup"><span data-stu-id="554ab-105">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to the following containers: Microsoft Teams sites, Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)), and SharePoint sites.</span></span> <span data-ttu-id="554ab-106">Используйте следующие параметры метки, чтобы защитить содержимое этих контейнеров:</span><span class="sxs-lookup"><span data-stu-id="554ab-106">Use the following label settings to help protect the content in those containers:</span></span>

- <span data-ttu-id="554ab-107">Конфиденциальность сайтов групп (общедоступных или закрытых), подключенных к группам Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="554ab-107">Privacy (public or private) of Microsoft 365 group-connected teams sites</span></span>
- <span data-ttu-id="554ab-108">Доступ внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="554ab-108">External users access</span></span>
- <span data-ttu-id="554ab-109">Доступ с неуправляемых устройств</span><span class="sxs-lookup"><span data-stu-id="554ab-109">Access from unmanaged devices</span></span> 

<span data-ttu-id="554ab-110">Когда вы применяете эту метку к поддерживаемому контейнеру, метка автоматически применяет настроенные параметры к подключенному сайту или группе.</span><span class="sxs-lookup"><span data-stu-id="554ab-110">When you apply this label to a supported container, the label automatically applies the configured options to the connected site or group.</span></span> 

<span data-ttu-id="554ab-111">Однако содержимое таких контейнеров не наследует метки для таких параметров, как имя метки, наглядная маркировка или шифрование.</span><span class="sxs-lookup"><span data-stu-id="554ab-111">Content in those containers however, do not inherit the labels for settings such as the label name, visual markings, or encryption.</span></span> <span data-ttu-id="554ab-112">Чтобы пользователи могли маркировать свои документы на сайтах SharePoint или групповых сайтах, [включите метки чувствительности для файлов Office в SharePoint и OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="554ab-112">So that users can label their documents in SharePoint sites or team sites, [enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a><span data-ttu-id="554ab-113">Сведения об общедоступной предварительной версии для сайтов Microsoft Teams, групп Microsoft 365 и сайтов SharePoint</span><span class="sxs-lookup"><span data-stu-id="554ab-113">About the public preview for Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="554ab-114">Функция меток конфиденциальности для сайтов Microsoft Teams, групп Microsoft 365 и сайтов SharePoint существует в предварительной версии и может измениться до окончательного выпуска.</span><span class="sxs-lookup"><span data-stu-id="554ab-114">Sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites is in preview and might change before final release.</span></span> <span data-ttu-id="554ab-115">Эта общедоступная предварительная версия не работает в сетях доставки содержимого Office 365 (CDN).</span><span class="sxs-lookup"><span data-stu-id="554ab-115">This public preview doesn't work with Office 365 Content Delivery Networks (CDNs).</span></span>

<span data-ttu-id="554ab-116">До включения этой предварительной версии и настройки новых параметров меток конфиденциальности пользователи могут просматривать и применять метки конфиденциальности в своих приложениях.</span><span class="sxs-lookup"><span data-stu-id="554ab-116">Before you enable this preview and configure sensitivity labels for the new settings, users can see and apply sensitivity labels in their apps.</span></span> <span data-ttu-id="554ab-117">Например, в Word:</span><span class="sxs-lookup"><span data-stu-id="554ab-117">For example, from Word:</span></span>

![Метка конфиденциальности, отображаемая в классическом приложении Word](../media/sensitivity-label-word.png)

<span data-ttu-id="554ab-119">После включения и настройки этой предварительной версии пользователи смогут дополнительно просматривать и применять метки конфиденциальности к сайтам Microsoft Teams, группам Microsoft 365 и сайтам SharePoint.</span><span class="sxs-lookup"><span data-stu-id="554ab-119">After you enable and configure this preview, users can additionally see and apply sensitivity labels to Microsoft Teams, Microsoft 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="554ab-120">Например, при создании нового сайта группы в SharePoint:</span><span class="sxs-lookup"><span data-stu-id="554ab-120">For example, when you create a new team site from SharePoint:</span></span>

![Метка конфиденциальности при создании сайта группы в SharePoint](../media/sensitivity-labels-new-team-site.png)

## <a name="enable-this-preview-and-synchronize-labels"></a><span data-ttu-id="554ab-122">Включение этой предварительной версии и синхронизация меток</span><span class="sxs-lookup"><span data-stu-id="554ab-122">Enable this preview and synchronize labels</span></span>

1. <span data-ttu-id="554ab-123">Так как эта функция использует функциональные возможности Azure AD, то для включения предварительной версии следуйте инструкциям из документации Azure AD: [Назначение меток конфиденциальности группам Microsoft 365 в Azure Active Directory (предварительная версия)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="554ab-123">Because this feature uses Azure AD functionality, follow the instructions in the Azure AD documentation to enable the preview: [Assign sensitivity labels to Microsoft 365 groups in Azure Active Directory (preview)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span></span>

2. <span data-ttu-id="554ab-124">Теперь [подключитесь к PowerShell Центра безопасности и соответствия требованиям Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="554ab-124">Now [connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span> 
    
    <span data-ttu-id="554ab-125">Например, в сеансе PowerShell, который вы запускаете как администратор, войдите в систему с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="554ab-125">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

3. <span data-ttu-id="554ab-126">Выполните следующие команды для синхронизации ваших меток конфиденциальности с Azure AD, чтобы их можно было использовать с группами Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="554ab-126">Run the following command to synchronize your sensitivity labels to Azure AD, so that they can be used with Microsoft 365 groups:</span></span>
    
    ```powershell
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a><span data-ttu-id="554ab-127">Настройка параметров сайта и группы при создании или изменении меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="554ab-127">How to configure site and group settings when you create or edit sensitivity labels</span></span>

<span data-ttu-id="554ab-128">Теперь вы можете создавать или изменять метки конфиденциальности, которые должны быть доступны для сайтов и групп.</span><span class="sxs-lookup"><span data-stu-id="554ab-128">You're now ready to create or edit sensitivity labels that you want to be available for sites and groups.</span></span> <span data-ttu-id="554ab-129">При включении предварительной версии в мастере присвоения меток конфиденциальности появится новая страница: **Параметры сайта и группы**.</span><span class="sxs-lookup"><span data-stu-id="554ab-129">Enabling the preview makes a new page visible in the sensitivity labeling wizards: **Site and group settings**</span></span>

<span data-ttu-id="554ab-130">Если вам нужна помощь по созданию или изменению метки конфиденциальности, см. инструкции в статье [Создание и настройка меток конфиденциальности](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="554ab-130">If you need help with creating or editing a sensitivity label, see the instructions from [Create and configure sensitivity labels](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span></span>

<span data-ttu-id="554ab-131">На этой новой странице **Параметры сайта и группы** настройте параметры:</span><span class="sxs-lookup"><span data-stu-id="554ab-131">On this new **Site and group settings** page, configure the settings:</span></span>

- <span data-ttu-id="554ab-132">**Конфиденциальность сайтов команд, подключенных к группам Office 365**. Сохраняйте стандартное значение **Общедоступный. Это означает, что любой пользователь из организации может получить доступ к сайту**, если вы хотите, чтобы любой пользователь в организации имел доступ к сайту команды или к группе, к которым применена эта метка.</span><span class="sxs-lookup"><span data-stu-id="554ab-132">**Privacy of Office 365 group-connected teams sites**: Keep the default of **Public - anyone in the organization can access the site** if you want anyone in your organization to access the team site or group where this label is applied.</span></span>
    
    <span data-ttu-id="554ab-133">Если вы хотите предоставить доступ только утвержденным пользователям в организации, выберите **Закрытый**.</span><span class="sxs-lookup"><span data-stu-id="554ab-133">Select **Private** if you want access to be restricted to only approved members in your organization.</span></span>
    
    <span data-ttu-id="554ab-134">Выберите **Отсутствует – позволить пользователю выбрать, кто имеет доступ к сайту**, если вы хотите защитить контент в контейнере с помощью метки конфиденциальности, но при этом разрешить пользователям самим настраивать параметры конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="554ab-134">Select **None - let user chose who can access the site** when you want to protect content in the container by using the sensitivity label, but still let users configure the privacy setting themselves.</span></span>
    
    <span data-ttu-id="554ab-135">Параметры **Общедоступный** или **Закрытый** устанавливают и блокируют параметр конфиденциальности при применении этой метки к контейнеру.</span><span class="sxs-lookup"><span data-stu-id="554ab-135">The settings of **Public** or **Private** set and lock the privacy setting when you apply this label to the container.</span></span> <span data-ttu-id="554ab-136">Выбранный вами параметр заменяет любой предыдущий параметр конфиденциальности, который мог быть настроен для команды или группы, и блокирует значение конфиденциальности, которое можно будет изменить только после удаления метки конфиденциальности из контейнера.</span><span class="sxs-lookup"><span data-stu-id="554ab-136">Your chosen seting replaces any previous privacy setting that might be configured for the team or group, and locks the privacy value so it can be changed only by first removing the sensitivity label from the container.</span></span> <span data-ttu-id="554ab-137">После удаления метки чувствительности настройки конфиденциальности из метки остаются, и пользователи теперь могут изменить их снова.</span><span class="sxs-lookup"><span data-stu-id="554ab-137">After you remove the sensitivity label, the privacy setting from the label remains and users can now change it again.</span></span>

- <span data-ttu-id="554ab-138">**Доступ внешних пользователей**. Определяет, может ли владелец группы [добавлять гостей в группу](/office365/admin/create-groups/manage-guest-access-in-groups).</span><span class="sxs-lookup"><span data-stu-id="554ab-138">**External users access**: Control whether the group owner can [add guests to the group](/office365/admin/create-groups/manage-guest-access-in-groups).</span></span>

- <span data-ttu-id="554ab-139">**Неуправляемые устройства**. Для [неуправляемых устройств](/sharepoint/control-access-from-unmanaged-devices) можно разрешить полный доступ, доступ только через Интернет или полностью заблокировать доступ.</span><span class="sxs-lookup"><span data-stu-id="554ab-139">**Unmanaged devices**: For [unmanaged devices](/sharepoint/control-access-from-unmanaged-devices), allow full access, web only access, or block access completely.</span></span> <span data-ttu-id="554ab-140">Если вы настроили этот параметр на уровне клиента или для определенного сайта, указываемый здесь параметр будет применен, только если он более строгий.</span><span class="sxs-lookup"><span data-stu-id="554ab-140">If you have configured this setting at the tenant level or for a specific site, the setting you specify here will be applied only if it's more restrictive.</span></span>

![Вкладка "Параметры сайта и группы"](../media/edit-sensitivity-label-site-group2.png)

> [!IMPORTANT]
> <span data-ttu-id="554ab-142">Когда вы применяете метку к команде, группе или сайту, в силу вступают только эти параметры сайта и группы.</span><span class="sxs-lookup"><span data-stu-id="554ab-142">Only these site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="554ab-143">Другие параметры метки, например шифрование и маркировка контента, не применяются к содержимому в команде, группе или на сайте.</span><span class="sxs-lookup"><span data-stu-id="554ab-143">Other label settings, such as encryption and content marking, aren't applied to the content within the team, group, or site.</span></span>
> 
> <span data-ttu-id="554ab-144">Постепенное развертывание для арендаторов: только ярлыки с настройками сайта и группы будут доступны для выбора при создании пользователями групп, групп и сайтов.</span><span class="sxs-lookup"><span data-stu-id="554ab-144">Gradually rolling out to tenants: Only labels with the site and group settings will be available to select when users create teams, groups, and sites.</span></span> <span data-ttu-id="554ab-145">Если в настоящее время вы можете применить метку к контейнеру, когда для метки не включены настройки сайта и группы, к контейнеру применяется только имя метки.</span><span class="sxs-lookup"><span data-stu-id="554ab-145">If you can currently apply a label to a container when the label doesn't have the site and group settings enabled, only the label name is applied to the container.</span></span>

<span data-ttu-id="554ab-146">Если метка конфиденциальности еще не опубликована, опубликуйте ее, [добавив в политику меток конфиденциальности](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span><span class="sxs-lookup"><span data-stu-id="554ab-146">If your sensitivity label isn't already published, now publish it by [adding it to a sensitivity label policy](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span> <span data-ttu-id="554ab-147">Пользователи, которым назначена политика меток конфиденциальности, включающая эту метку, смогут выбирать ее для сайтов и групп.</span><span class="sxs-lookup"><span data-stu-id="554ab-147">The users who are assigned a sensitivity label policy that includes this label will be able to select it for sites and groups.</span></span>

<span data-ttu-id="554ab-148">Из политики меток только параметр политики **Применить эту метку по умолчанию к документам**, и электронная почта применима при применении этой метки к контейнерам.</span><span class="sxs-lookup"><span data-stu-id="554ab-148">From the label policy, only the policy setting **Apply this label by default to documents and email** is applicable when you apply this label to containers.</span></span> <span data-ttu-id="554ab-149">Другие параметры политики не применяются, включая обязательную маркировку, требующую обоснования пользователя и ссылку на пользовательскую страницу справки.</span><span class="sxs-lookup"><span data-stu-id="554ab-149">Other policy settings are not applied, which include mandatory labeling, requiring user justification, and a link to the custom help page.</span></span>

## <a name="sensitivity-label-management"></a><span data-ttu-id="554ab-150">Управление метками конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="554ab-150">Sensitivity label management</span></span>

> [!WARNING]
> <span data-ttu-id="554ab-151">Создание, изменение и удаление меток конфиденциальности, используемых для сайтов Microsoft Teams, групп Microsoft 365 и сайтов SharePoint, требует тщательного соотнесения с политикой публикации меток для пользователей.</span><span class="sxs-lookup"><span data-stu-id="554ab-151">Creating, modifying, and deleting sensitivity labels that you use for Microsoft Teams, Microsoft 365 groups, and SharePoint sites requires careful coordination with publishing label policies to users.</span></span> 

<span data-ttu-id="554ab-152">Чтобы избежать создания ошибок для сайтов и групп, которые могут повлиять на всех пользователей, воспользуйтесь следующим руководством.</span><span class="sxs-lookup"><span data-stu-id="554ab-152">Avoid creation errors for sites and groups that can affect all users by using the following guidance.</span></span>

<span data-ttu-id="554ab-153">**Создание и публикация меток**</span><span class="sxs-lookup"><span data-stu-id="554ab-153">**Creating and publishing labels:**</span></span>

<span data-ttu-id="554ab-154">После создания и публикации метки может потребоваться до 24 часов, чтобы она стала видимой для пользователей команд, групп и сайтов.</span><span class="sxs-lookup"><span data-stu-id="554ab-154">After a sensitivity label is created and published, it can take up to 24 hours for the label to become visible for users in teams, groups, and sites.</span></span> <span data-ttu-id="554ab-155">Чтобы опубликовать метку для всех пользователей в клиенте, используйте следующие действия:</span><span class="sxs-lookup"><span data-stu-id="554ab-155">Use the following steps to publish a label for all users in the tenant:</span></span>

1. <span data-ttu-id="554ab-156">Создайте метку конфиденциальности и опубликуйте ее лишь для нескольких учетных записей пользователей в клиенте.</span><span class="sxs-lookup"><span data-stu-id="554ab-156">Create the sensitivity label and publish it for just a few user accounts in the tenant.</span></span>

2. <span data-ttu-id="554ab-157">Подождите 24 часа.</span><span class="sxs-lookup"><span data-stu-id="554ab-157">Wait for 24 hours.</span></span>

3. <span data-ttu-id="554ab-158">После 24-часового ожидания используйте одну из учетных записей пользователей, указанных в действии 1, чтобы создать команду, группу Microsoft 365 или сайт SharePoint с меткой, созданной в действии 1.</span><span class="sxs-lookup"><span data-stu-id="554ab-158">After this 24 hours wait, use one of the user accounts you specified in step 1 to create a team, Microsoft 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="554ab-159">Если в действии 3 операции создания не возникают ошибки, опубликуйте метку для всех пользователей в клиенте.</span><span class="sxs-lookup"><span data-stu-id="554ab-159">If there are no errors during the creation operation for step 3, publish the label for all users in your tenant.</span></span> <span data-ttu-id="554ab-160">При возникновении ошибок обратитесь в [службу поддержки Майкрософт](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="554ab-160">If there are errors, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

<span data-ttu-id="554ab-161">**Изменение и удаление опубликованных меток**</span><span class="sxs-lookup"><span data-stu-id="554ab-161">**Modifying and deleting published labels:**</span></span>

<span data-ttu-id="554ab-162">Если вы измените или удалите метку чувствительности с включенными настройками сайта и группы, и эта метка будет включена в одну или несколько политик меток, эти действия могут привести к сбоям при создании для всех команд, групп и сайтов.</span><span class="sxs-lookup"><span data-stu-id="554ab-162">If you modify or delete a sensitivity label with the site and group settings enabled, and that label is included in one or more label policies, these actions can result in creation failures for all teams, groups, and sites.</span></span> <span data-ttu-id="554ab-163">Чтобы избежать этой ситуации, используйте следующее руководство:</span><span class="sxs-lookup"><span data-stu-id="554ab-163">To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="554ab-164">Удалите метку конфиденциальности из всех политик меток, содержащих ее.</span><span class="sxs-lookup"><span data-stu-id="554ab-164">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="554ab-165">Подождите 48 часов.</span><span class="sxs-lookup"><span data-stu-id="554ab-165">Wait for 48 hours.</span></span>

3. <span data-ttu-id="554ab-166">После 48-часового ожидания попробуйте создать команду, группу или сайт и убедитесь, что метка больше не отображается.</span><span class="sxs-lookup"><span data-stu-id="554ab-166">After the 48 hours wait, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="554ab-167">Если метка конфиденциальности не отображается, вы можете безопасно изменить или удалить ее.</span><span class="sxs-lookup"><span data-stu-id="554ab-167">If the sensitivity label isn't visible, you can now safely modify or delete the label.</span></span> <span data-ttu-id="554ab-168">Если метка по-прежнему отображается, обратитесь в [службу поддержки Майкрософт](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="554ab-168">If the label is still visible, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

## <a name="assign-sensitivity-labels-to-microsoft-365-groups"></a><span data-ttu-id="554ab-169">Назначение меток конфиденциальности группам Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="554ab-169">Assign sensitivity labels to Microsoft 365 groups</span></span>

<span data-ttu-id="554ab-170">Теперь вы можете применить метки или метку конфиденциальности к группам Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="554ab-170">You're now ready to apply the sensitivity label or labels to Microsoft 365 groups.</span></span> <span data-ttu-id="554ab-171">Инструкции см. в документации Azure AD:</span><span class="sxs-lookup"><span data-stu-id="554ab-171">Return to the Azure AD documentation for instructions:</span></span>

- [<span data-ttu-id="554ab-172">Назначение метки новой группе на портале Azure</span><span class="sxs-lookup"><span data-stu-id="554ab-172">Assign a label to a new group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)

-  [<span data-ttu-id="554ab-173">Назначение метки существующей группе на портале Azure</span><span class="sxs-lookup"><span data-stu-id="554ab-173">Assign a label to an existing group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

-  <span data-ttu-id="554ab-174">[Удаление метки из существующей группы на портале Azure](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="554ab-174">[Remove a label from an existing group in Azure portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="554ab-175">Применение метки конфиденциальности к новой команде</span><span class="sxs-lookup"><span data-stu-id="554ab-175">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="554ab-176">Пользователи могут выбирать метки конфиденциальности при создании новых команд в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="554ab-176">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="554ab-177">При выборе метки в раскрывающемся списке **Чувствительность** параметр конфиденциальности может измениться, чтобы отразить конфигурацию метки.</span><span class="sxs-lookup"><span data-stu-id="554ab-177">When they select the label from the **Sensitivity** dropdown, the privacy setting might change to reflect the label configuration.</span></span> <span data-ttu-id="554ab-178">В зависимости от параметра доступа внешних пользователей, выбранного для метки, пользователи могут или не могут добавлять в команду людей из-за пределов организации.</span><span class="sxs-lookup"><span data-stu-id="554ab-178">Depending on the external users access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="554ab-179">Дополнительные сведения о метках конфиденциальности для Teams</span><span class="sxs-lookup"><span data-stu-id="554ab-179">Learn more about sensitivity labels for Teams</span></span>](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![Параметр конфиденциальности при создании новой команды](../media/privacy-setting-new-team.png)

<span data-ttu-id="554ab-181">После создания команды метка конфиденциальности отображается в правом верхнем углу всех каналов.</span><span class="sxs-lookup"><span data-stu-id="554ab-181">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![Отображение метки конфиденциальности в команде](../media/privacy-setting-teams.png)

<span data-ttu-id="554ab-183">Служба автоматически применяет такую же метку конфиденциальности к группе Microsoft 365 и подключенному сайту команды SharePoint.</span><span class="sxs-lookup"><span data-stu-id="554ab-183">The service automatically applies the same sensitivity label to the Microsoft 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a><span data-ttu-id="554ab-184">Применение метки конфиденциальности к новой группе в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="554ab-184">Apply a sensitivity label to a new group in Outlook on the web</span></span>

<span data-ttu-id="554ab-185">В Outlook в Интернете при создании группы можно выбрать или изменить параметр **Конфиденциальность** для опубликованных меток:</span><span class="sxs-lookup"><span data-stu-id="554ab-185">In Outlook on the web, when you create a new group, you can select or change the **Sensitivity** option for published labels:</span></span>

![Создание группы и выбор параметра в разделе "Конфиденциальность"](../media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="554ab-187">Применение метки конфиденциальности к новому сайту</span><span class="sxs-lookup"><span data-stu-id="554ab-187">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="554ab-188">Администраторы и конечные пользователи могут выбирать метки чувствительности [при создании современных сайтов групп и сайтов связи](/sharepoint/create-site-collection) и расширять **дополнительные параметры**:</span><span class="sxs-lookup"><span data-stu-id="554ab-188">Admins and end users can select sensitivity labels when they [create modern team sites and communication sites](/sharepoint/create-site-collection), and expand **Advanced settings**:</span></span>

![Создание сайта и выбор параметра в разделе "Конфиденциальность"](../media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="554ab-190">В раскрывающемся списке отображаются имена меток для выбора, а значок справки отображает все имена меток с их подсказкой, которая может помочь пользователям определить правильную метку для применения.</span><span class="sxs-lookup"><span data-stu-id="554ab-190">The dropdown box displays the label names for the selection, and the help icon displays all the label names with their tooltip, which can help users determine the correct label to apply.</span></span>

<span data-ttu-id="554ab-191">Когда метка применяется, и пользователи переходят на сайт, они видят название метки и применяемые политики.</span><span class="sxs-lookup"><span data-stu-id="554ab-191">When the label is applied, and users browse to the site, they see the name of the label and applied policies.</span></span> <span data-ttu-id="554ab-192">Например, этот сайт был помечен как **конфиденциальный**, а для параметра конфиденциальности установлено значение **Личное**:</span><span class="sxs-lookup"><span data-stu-id="554ab-192">For example, this site has been labeled as **Confidential**, and the privacy setting is set to **Private**:</span></span>

![Сайт с примененной меткой конфиденциальности](../media/sensitivity-label-site.png)

## <a name="view-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="554ab-194">Просмотр меток конфиденциальности в Центре администрирования SharePoint</span><span class="sxs-lookup"><span data-stu-id="554ab-194">View sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="554ab-195">Чтобы просмотреть примененные метки конфиденциальности, используйте страницу **Активные сайты** в новом Центре администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="554ab-195">To view the applied sensitivity labels, use the **Active sites** page in the new SharePoint admin center.</span></span> <span data-ttu-id="554ab-196">Возможно, сначала потребуется добавить столбец **Конфиденциальность**:</span><span class="sxs-lookup"><span data-stu-id="554ab-196">You might need to first add the **Sensitivity** column:</span></span>

![Столбец "Конфиденциальность" на странице "Активные сайты"](../media/manage-site-sensitivity-labels.png)

<span data-ttu-id="554ab-198">[Дополнительные сведения об управлении сайтами в новом Центре администрирования SharePoint](/sharepoint/manage-sites-in-new-admin-center).</span><span class="sxs-lookup"><span data-stu-id="554ab-198">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="554ab-199">Изменение параметров сайта и группы для метки</span><span class="sxs-lookup"><span data-stu-id="554ab-199">Change site and group settings for a label</span></span>

<span data-ttu-id="554ab-200">Когда осуществляется изменение параметров сайта и группы для метки, требуется выполнить следующие команды PowerShell, чтобы ваши команды, сайты и группы могли использовать новые параметры.</span><span class="sxs-lookup"><span data-stu-id="554ab-200">Whenever you make a change to site and group settings for a label, you must run the following PowerShell commands so that your teams, sites, and groups can use the new settings.</span></span> <span data-ttu-id="554ab-201">Рекомендуется не изменять параметры сайта и группы для метки после применения метки конфиденциальности к нескольким командам, группам или сайтам.</span><span class="sxs-lookup"><span data-stu-id="554ab-201">As a best practice, don't the change site and group settings for a label after you've applied the sensitivity label to several teams, groups, or sites.</span></span>

1. <span data-ttu-id="554ab-202">Сначала [подключитесь к PowerShell Центра безопасности и соответствия требованиям Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="554ab-202">First, [connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span> 
    
    <span data-ttu-id="554ab-203">Например, в сеансе PowerShell, который вы запускаете как администратор, войдите в систему с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="554ab-203">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. <span data-ttu-id="554ab-204">Получите список меток конфиденциальности с их GUID с помощью командлета [Get-Label](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="554ab-204">Get the list of sensitivity labels and their GUIDs by using the [Get-Label](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps) cmdlet:</span></span>
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

3. <span data-ttu-id="554ab-205">Запишите GUID для измененных меток.</span><span class="sxs-lookup"><span data-stu-id="554ab-205">Make a note of the GUID for the label or labels you have changed.</span></span>

4. <span data-ttu-id="554ab-206">Теперь [подключитесь к PowerShell Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="554ab-206">Now [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
    <span data-ttu-id="554ab-207">Например,</span><span class="sxs-lookup"><span data-stu-id="554ab-207">For example:</span></span>
    
    ```powershell
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    ```
    
5. <span data-ttu-id="554ab-208">запустите командлет [Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/get-unifiedgroup?view=exchange-ps), указав GUID вашей метки вместо GUID примера "e48058ea-98e8-4940-8db0-ba1310fd955e":</span><span class="sxs-lookup"><span data-stu-id="554ab-208">Run the [Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/get-unifiedgroup?view=exchange-ps) cmdlet, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span> 
    
    ```powershell
    $Groups= Get-UnifiedGroup | Where {$_.SensitivityLabel  -eq "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

6. <span data-ttu-id="554ab-209">Для каждой группы повторно примените метку конфиденциальности, указав GUID метки вместо GUID примера "e48058ea-98e8-4940-8db0-ba1310fd955e":</span><span class="sxs-lookup"><span data-stu-id="554ab-209">For each group, reapply the sensitivity label, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span>
    
    ```powershell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

## <a name="support-for-the-sensitivity-labels"></a><span data-ttu-id="554ab-210">Поддержка меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="554ab-210">Support for the sensitivity labels</span></span>

<span data-ttu-id="554ab-211">Вы можете использовать метки конфиденциальности, настроенные для параметров сайта и группы, в следующих приложениях и службах:</span><span class="sxs-lookup"><span data-stu-id="554ab-211">You can use the sensitivity labels that you've configured for site and group settings with the following apps and services:</span></span>

- <span data-ttu-id="554ab-212">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="554ab-212">SharePoint Online</span></span>
- <span data-ttu-id="554ab-213">Teams</span><span class="sxs-lookup"><span data-stu-id="554ab-213">Teams</span></span>
- <span data-ttu-id="554ab-214">Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="554ab-214">Outlook on the web</span></span>
- <span data-ttu-id="554ab-215">Центр администрирования SharePoint</span><span class="sxs-lookup"><span data-stu-id="554ab-215">SharePoint admin center</span></span>
- <span data-ttu-id="554ab-216">Центр администрирования Azure AD</span><span class="sxs-lookup"><span data-stu-id="554ab-216">Azure AD admin center</span></span>

<span data-ttu-id="554ab-217">Другие приложения и службы, в которых пока нельзя использовать метки конфиденциальности, настроенные для параметров сайта и группы, включают:</span><span class="sxs-lookup"><span data-stu-id="554ab-217">Other apps and services that you can't currently use the sensitivity labels that you've configured for site and group settings include:</span></span>

- <span data-ttu-id="554ab-218">Outlook для Mac</span><span class="sxs-lookup"><span data-stu-id="554ab-218">Outlook for the Mac</span></span>
- <span data-ttu-id="554ab-219">Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="554ab-219">Outlook mobile</span></span>
- <span data-ttu-id="554ab-220">Классическая версия Outlook для Windows</span><span class="sxs-lookup"><span data-stu-id="554ab-220">Outlook desktop for Windows</span></span>
- <span data-ttu-id="554ab-221">Forms</span><span class="sxs-lookup"><span data-stu-id="554ab-221">Forms</span></span>
- <span data-ttu-id="554ab-222">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="554ab-222">Dynamics 365</span></span>
- <span data-ttu-id="554ab-223">Yammer</span><span class="sxs-lookup"><span data-stu-id="554ab-223">Yammer</span></span>
- <span data-ttu-id="554ab-224">Stream</span><span class="sxs-lookup"><span data-stu-id="554ab-224">Stream</span></span>
- <span data-ttu-id="554ab-225">Планировщик</span><span class="sxs-lookup"><span data-stu-id="554ab-225">Planner</span></span>
- <span data-ttu-id="554ab-226">Project</span><span class="sxs-lookup"><span data-stu-id="554ab-226">Project</span></span>
- <span data-ttu-id="554ab-227">PowerBI</span><span class="sxs-lookup"><span data-stu-id="554ab-227">PowerBI</span></span>
- <span data-ttu-id="554ab-228">Центр администрирования Teams</span><span class="sxs-lookup"><span data-stu-id="554ab-228">Teams admin center</span></span>
- <span data-ttu-id="554ab-229">Центр администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="554ab-229">Microsoft 365 admin center</span></span>
- <span data-ttu-id="554ab-230">Центр администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="554ab-230">Exchange admin center</span></span>


## <a name="classic-azure-ad-group-classification"></a><span data-ttu-id="554ab-231">Классическая классификация групп Azure AD</span><span class="sxs-lookup"><span data-stu-id="554ab-231">Classic Azure AD group classification</span></span>

<span data-ttu-id="554ab-232">Если вы включите эту предварительную версию, Microsoft 365 больше не будет поддерживать старые классификации для новых групп Microsoft 365 и сайтов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="554ab-232">Microsoft 365 no longer supports the old classifications for new Microsoft 365 groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="554ab-233">Однако существующие группы и сайты по-прежнему будут отображать старые значения классификации, если их не преобразовать для использования меток конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="554ab-233">However, existing groups and sites still display the old classification values unless you convert them to use sensitivity labels.</span></span>

<span data-ttu-id="554ab-234">В качестве примера использования старой классификации групп для SharePoint см. статью [Классификация "современных" сайтов SharePoint](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span><span class="sxs-lookup"><span data-stu-id="554ab-234">As an example of how you might have used the old group classification for SharePoint, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="554ab-235">Эти классификации были настроены с помощью Azure AD PowerShell или основной библиотеки PnP и определяют значения параметра `ClassificationList`.</span><span class="sxs-lookup"><span data-stu-id="554ab-235">These classifications were configured by using Azure AD PowerShell or the PnP Core library and defining values for the `ClassificationList` setting.</span></span> <span data-ttu-id="554ab-236">Если в вашем клиенте определены значения классификации, они отображаются при выполнении следующей команды из [модуля AzureADPreview PowerShell](https://www.powershellgallery.com/packages/AzureADPreview):</span><span class="sxs-lookup"><span data-stu-id="554ab-236">If your tenant has classification values defined, they are shown when you run the following command from the [AzureADPreview PowerShell module](https://www.powershellgallery.com/packages/AzureADPreview):</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="554ab-237">Чтобы преобразовать старые классификации для использования меток конфиденциальности, выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="554ab-237">To convert your old classifications to sensitivity labels, do one of the following:</span></span>

- <span data-ttu-id="554ab-238">Используйте существующие метки. Укажите нужные параметры меток для сайтов и групп, изменив опубликованные метки конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="554ab-238">Use existing labels: Specify the label settings you want for sites and groups by editing existing sensitivity labels that are already published.</span></span>

- <span data-ttu-id="554ab-239">Создайте новые метки. Укажите нужные параметры меток для сайтов и групп, создав и опубликовав новые метки конфиденциальности с такими же именами, как в существующих классификациях.</span><span class="sxs-lookup"><span data-stu-id="554ab-239">Create new labels: Specify the label settings you want for sites and groups by creating and publishing new sensitivity labels that have the same names as your existing classifications.</span></span>

<span data-ttu-id="554ab-240">Затем:</span><span class="sxs-lookup"><span data-stu-id="554ab-240">Then:</span></span> 

1. <span data-ttu-id="554ab-241">Используйте PowerShell, чтобы применить метки конфиденциальности к существующим группам Microsoft 365 и сайтам SharePoint с помощью сопоставления имен.</span><span class="sxs-lookup"><span data-stu-id="554ab-241">Use PowerShell to apply the sensitivity labels to existing Microsoft 365 groups and SharePoint sites by using name mapping.</span></span> <span data-ttu-id="554ab-242">Соответствующие инструкции см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="554ab-242">See the next section for instructions.</span></span>

2. <span data-ttu-id="554ab-243">Удалите старые классификации из существующих групп и сайтов.</span><span class="sxs-lookup"><span data-stu-id="554ab-243">Remove the old classifications from the existing groups and sites.</span></span>

<span data-ttu-id="554ab-244">Хотя вы не можете запретить пользователям создавать группы в приложениях и службах, которые пока не поддерживают метки конфиденциальности, вы можете запустить повторяющийся скрипт PowerShell для поиска новых групп, созданных пользователями со старыми классификациями, и их преобразования для использования меток конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="554ab-244">Although you can't prevent users from creating new groups in apps and services that don't yet support sensitivity labels, you can run a recurring PowerShell script to look for new groups that users have created with the old classifications, and convert these to use sensitivity labels.</span></span> 

#### <a name="use-powershell-to-convert-classifications-for-microsoft-365-groups-to-sensitivity-labels"></a><span data-ttu-id="554ab-245">Преобразование классификаций для групп Microsoft 365 в метки конфиденциальности с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="554ab-245">Use PowerShell to convert classifications for Microsoft 365 groups to sensitivity labels</span></span>

1. <span data-ttu-id="554ab-246">Сначала [подключитесь к PowerShell Центра безопасности и соответствия требованиям Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="554ab-246">First, [connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span> 
    
    <span data-ttu-id="554ab-247">Например, в сеансе PowerShell, который вы запускаете как администратор, войдите в систему с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="554ab-247">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. <span data-ttu-id="554ab-248">Получите список меток конфиденциальности с их GUID с помощью командлета [Get-Label](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="554ab-248">Get the list of sensitivity labels and their GUIDs by using the [Get-Label](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps) cmdlet:</span></span>
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

3. <span data-ttu-id="554ab-249">Запишите GUID для меток конфиденциальности, которые нужно применить к группам Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="554ab-249">Make a note of the GUIDs for the sensitivity labels you want to apply to your Microsoft 365 groups.</span></span>

4. <span data-ttu-id="554ab-250">Теперь [подключитесь к PowerShell Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="554ab-250">Now [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
    <span data-ttu-id="554ab-251">Например:</span><span class="sxs-lookup"><span data-stu-id="554ab-251">For example:</span></span>
    
    ```powershell
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    ```

5. <span data-ttu-id="554ab-252">Используйте следующую команду в качестве примера, чтобы получить список групп, использующих в настоящее время классификацию General (Общее).</span><span class="sxs-lookup"><span data-stu-id="554ab-252">Use the following command as an example to get the list of groups that currently have the classification of "General":</span></span>

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="554ab-253">Для каждой группы добавьте GUID новой метки конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="554ab-253">For each group, add the new sensitivity label GUID.</span></span> <span data-ttu-id="554ab-254">Например,</span><span class="sxs-lookup"><span data-stu-id="554ab-254">For example:</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

7. <span data-ttu-id="554ab-255">Повторите действия 5 и 6 для остальных категорий групп.</span><span class="sxs-lookup"><span data-stu-id="554ab-255">Repeat steps 5 and 6 for your remaining group classifications.</span></span>

## <a name="auditing-sensitivity-label-activities"></a><span data-ttu-id="554ab-256">Аудит действий с метками конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="554ab-256">Auditing sensitivity label activities</span></span>

<span data-ttu-id="554ab-257">Если пользователь отправляет документ на сайт, защищенный с помощью метки конфиденциальности, и метка конфиденциальности документа имеет [более высокий приоритет](sensitivity-labels.md#label-priority-order-matters), чем метка конфиденциальности, примененная к сайту, это действие не блокируется.</span><span class="sxs-lookup"><span data-stu-id="554ab-257">If somebody uploads a document to a site that's protected with a sensitivity label and their document has a [higher priority](sensitivity-labels.md#label-priority-order-matters) sensitivity label than the sensitivity label applied to the site, this action isn't blocked.</span></span> <span data-ttu-id="554ab-258">Например, вы применили метку **Общее** к сайту SharePoint, а другой пользователь отправляет на этот сайт документ с меткой **Конфиденциально**.</span><span class="sxs-lookup"><span data-stu-id="554ab-258">For example, you've applied the **General** label to a SharePoint site, and somebody uploads to this site a document labeled **Confidential**.</span></span> <span data-ttu-id="554ab-259">Так как метка конфиденциальности с более высоким приоритетом определяет более конфиденциальное содержимое, чем содержимое с меткой меньшего приоритета, эта ситуация может являться проблемой безопасности.</span><span class="sxs-lookup"><span data-stu-id="554ab-259">Because a sensitivity label with a higher priority identifies content that is more sensitivity than content that has a lower priority order, this situation could be a security concern.</span></span>

<span data-ttu-id="554ab-260">Хотя действие не блокируется, оно подвергается аудиту и автоматически создает письмо для пользователя, отправившего документ, и для администратора сайта.</span><span class="sxs-lookup"><span data-stu-id="554ab-260">Although the action isn't blocked, it is audited and automatically generates an email to the person who uploaded the document and the site administrator.</span></span> <span data-ttu-id="554ab-261">В результате пользователь и администраторы могут определить документы с таким несоответствием приоритетов меток и принять необходимые меры.</span><span class="sxs-lookup"><span data-stu-id="554ab-261">As a result, both the user and administrators can identify documents that have this misalignment of label priority and take action if needed.</span></span> <span data-ttu-id="554ab-262">Например, удалить или переместить отправленный документ с сайта.</span><span class="sxs-lookup"><span data-stu-id="554ab-262">For example, delete or move the uploaded document from the site.</span></span> 

<span data-ttu-id="554ab-263">Проблема безопасности не возникает, если метка конфиденциальности документа имеет более низкий приоритет, чем метка конфиденциальности, примененная к сайту.</span><span class="sxs-lookup"><span data-stu-id="554ab-263">It wouldn't be a security concern if the document has a lower priority sensitivity label than the sensitivity label applied to the site.</span></span> <span data-ttu-id="554ab-264">Например, документ с меткой **Общее** отправляется на сайт с меткой **Конфиденциально**.</span><span class="sxs-lookup"><span data-stu-id="554ab-264">For example, a document labeled **General** is uploaded to a site labeled **Confidential**.</span></span> <span data-ttu-id="554ab-265">В этом сценарии событие аудита и письмо не создаются.</span><span class="sxs-lookup"><span data-stu-id="554ab-265">In this scenario, an auditing event and email isn't generated.</span></span>

<span data-ttu-id="554ab-266">Чтобы найти это событие в журнале аудита, выполните поиск по запросу **Обнаружено несоответствие конфиденциальности документа** в категории **Действия с файлами и страницами**.</span><span class="sxs-lookup"><span data-stu-id="554ab-266">To search the audit log for this event, look for **Detected document sensitivity mismatch** from the **File and page activities** category.</span></span> 

<span data-ttu-id="554ab-267">Автоматически созданное письмо получает тему **Обнаружена несовместимая метка конфиденциальности**, а текст письма разъясняет несоответствие примененных меток и содержит ссылку на отправленный документ и сайт.</span><span class="sxs-lookup"><span data-stu-id="554ab-267">The automatically generated email has the subject **Incompatible sensitivity label detected** and the email message explains the labeling mismatch with a link to the uploaded document and site.</span></span> <span data-ttu-id="554ab-268">В нем также содержится ссылка на документацию, объясняющую, как пользователи могут изменить метку конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="554ab-268">It also contains a documentation link that explains how users can change the sensitivity label.</span></span> <span data-ttu-id="554ab-269">В настоящее время эти автоматические письма нельзя отключить или настроить.</span><span class="sxs-lookup"><span data-stu-id="554ab-269">Currently, these automated emails cannot be disabled or customized.</span></span>

<span data-ttu-id="554ab-270">Когда кто-нибудь добавляет или удаляет метку конфиденциальности на сайте или в группе, такие действия также подвергаются аудиту, но без автоматического создания письма.</span><span class="sxs-lookup"><span data-stu-id="554ab-270">When somebody adds or removes a sensitivity label to or from a site or group, these activities are also audited but without automatically generating an email.</span></span> 

<span data-ttu-id="554ab-271">Все эти события аудита можно найти в категории [Действия с метками конфиденциальности](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities).</span><span class="sxs-lookup"><span data-stu-id="554ab-271">All these auditing events can be found in the [Sensitivity label activities](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) category.</span></span> <span data-ttu-id="554ab-272">Инструкции по поиску в журнале аудита см. в статье [Поиск по журналу аудита в Центре безопасности и соответствия требованиям](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="554ab-272">For instructions to search the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="troubleshoot-sensitivity-label-deployment"></a><span data-ttu-id="554ab-273">Устранение неполадок при развертывании меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="554ab-273">Troubleshoot sensitivity label deployment</span></span>

<span data-ttu-id="554ab-274">Возникают проблемы с метками конфиденциальности для сайтов Microsoft Teams, групп Microsoft 365 и сайтов SharePoint?</span><span class="sxs-lookup"><span data-stu-id="554ab-274">Having problems with sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites?</span></span> <span data-ttu-id="554ab-275">Проверьте следующее:</span><span class="sxs-lookup"><span data-stu-id="554ab-275">Check the following:</span></span>

### <a name="labels-not-visible-after-publishing"></a><span data-ttu-id="554ab-276">Метки не отображаются после публикации</span><span class="sxs-lookup"><span data-stu-id="554ab-276">Labels not visible after publishing</span></span>
<span data-ttu-id="554ab-277">Если у вас возникают проблемы при создании сайта или группы Microsoft 365 после включения этих параметров или изменения имени или всплывающей подсказки метки конфиденциальности, подождите несколько часов после сохранения изменений метки, а затем попробуйте снова создать команду или группу.</span><span class="sxs-lookup"><span data-stu-id="554ab-277">If you experience issues when you create a site or Microsoft 365 group after you enable these settings or modify a sensitivity label's name or tooltip, wait a few hours after saving the label changes, and then try to create the team or group again.</span></span> <span data-ttu-id="554ab-278">Сведения см. в разделе [Планирование развертывания после создания или изменения метки конфиденциальности](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span><span class="sxs-lookup"><span data-stu-id="554ab-278">For information, see [Schedule roll-out after you create or change a sensitivity label](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span></span>

<span data-ttu-id="554ab-279">Если вы все еще не видите новую метку чувствительности в SharePoint Online, обратитесь в [службу поддержки Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="554ab-279">If you still can't see the new sensitivity label from SharePoint Online, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

### <a name="team-group-or-sharepoint-site-creation-errors"></a><span data-ttu-id="554ab-280">Ошибки при создании команды, группы или сайта SharePoint</span><span class="sxs-lookup"><span data-stu-id="554ab-280">Team, group, or SharePoint site creation errors</span></span>
<span data-ttu-id="554ab-281">Если в режиме общедоступного предварительного просмотра возникают ошибки создания, вы можете отключить метки конфиденциальности для сайтов Microsoft Teams, групп Microsoft 365 и сайтов SharePoint, используя те же инструкции из раздела [Включить поддержку меток конфиденциальности в PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span><span class="sxs-lookup"><span data-stu-id="554ab-281">If you experience creation errors during the public preview, you can turn off sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites by using the same instructions from [Enable sensitivity label support in PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span></span> <span data-ttu-id="554ab-282">Но чтобы отключить предварительную версию на шаге 5, отключите функцию с помощью `$setting["EnableMIPLabels"] = "False"`.</span><span class="sxs-lookup"><span data-stu-id="554ab-282">However, to disable the preview, in step 5, disable the feature by using `$setting["EnableMIPLabels"] = "False"`.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="554ab-283">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="554ab-283">Additional resources</span></span>

<span data-ttu-id="554ab-284">Просмотрите запись вебинара и ответы на вопросы об [использовании меток конфиденциальности в Microsoft Teams, группах Office 365 и сайтах SharePoint Online](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380).</span><span class="sxs-lookup"><span data-stu-id="554ab-284">See the webinar recording and answered questions for [Using Sensitivity labels with Microsoft Teams, O365 Groups and SharePoint Online sites](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380).</span></span>

