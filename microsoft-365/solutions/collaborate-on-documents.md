---
title: Совместная работа с гостями над документом
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: В этой статье вы узнаете, как совместно работать с гостями в документе в SharePoint и OneDrive.
ms.openlocfilehash: e3492732756aecb176eb21f0bdfd0d394013975e
ms.sourcegitcommit: 8a726ed7ec19a8728c079780fa4d343a5f759fbb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030009"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="48d0d-103">Совместная работа с гостями над документом</span><span class="sxs-lookup"><span data-stu-id="48d0d-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="48d0d-104">Если вам требуется совместная работа с пользователями, не входящими в вашу организацию, в документы в SharePoint или OneDrive, вы можете отправить им ссылку для совместного доступа к документу.</span><span class="sxs-lookup"><span data-stu-id="48d0d-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing-link to the document.</span></span> <span data-ttu-id="48d0d-105">В этой статье мы рассмотрим действия по настройке Microsoft 365, необходимые для настройки ссылок общего доступа для SharePoint и OneDrive в целях организации.</span><span class="sxs-lookup"><span data-stu-id="48d0d-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing-links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="48d0d-106">Видеодемонстрация</span><span class="sxs-lookup"><span data-stu-id="48d0d-106">Video demonstration</span></span>

<span data-ttu-id="48d0d-107">В этом видеоролике показаны действия по настройке, описанные в этом документе.</span><span class="sxs-lookup"><span data-stu-id="48d0d-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="48d0d-108">Параметры связей в Организации Azure</span><span class="sxs-lookup"><span data-stu-id="48d0d-108">Azure organizational relationships settings</span></span>

<span data-ttu-id="48d0d-109">Общий доступ в Microsoft 365 регулируется на самом высоком уровне [параметрами организационных отношений в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="48d0d-109">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="48d0d-110">Если общий доступ к гостевым учетным данным отключен или ограничен в Azure AD, этот параметр переопределяет все параметры общего доступа, настроенные в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="48d0d-110">If guest-sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="48d0d-111">Проверьте параметры организационных отношений, чтобы предотвратить блокировку общего доступа с гостями.</span><span class="sxs-lookup"><span data-stu-id="48d0d-111">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Снимок экрана: страница параметров организационных связей Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="48d0d-113">Настройка параметров организационных отношений</span><span class="sxs-lookup"><span data-stu-id="48d0d-113">To set organizational relationship settings</span></span>

<span data-ttu-id="48d0d-114">Настройка параметров внешней совместной работы</span><span class="sxs-lookup"><span data-stu-id="48d0d-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="48d0d-115">Выполните вход в Azure Active Directory по адресу [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="48d0d-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="48d0d-116">В области навигации слева выберите **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="48d0d-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="48d0d-117">Щелкните **Внешние удостоверения**.</span><span class="sxs-lookup"><span data-stu-id="48d0d-117">Click **External identities**.</span></span>
4. <span data-ttu-id="48d0d-118">На экране "начало **работы** " в левой области навигации щелкните элемент **внешние параметры совместной работы**.</span><span class="sxs-lookup"><span data-stu-id="48d0d-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="48d0d-119">Убедитесь, что у **администраторов и пользователей в роли гостя может быть приглашение** , а **Участники** — значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="48d0d-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="48d0d-120">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="48d0d-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="48d0d-121">Обратите внимание на параметры в разделе **ограничения совместной работы** .</span><span class="sxs-lookup"><span data-stu-id="48d0d-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="48d0d-122">Убедитесь, что домены гостей, с которыми вы хотите работать совместно, не заблокированы.</span><span class="sxs-lookup"><span data-stu-id="48d0d-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="48d0d-123">Если вы работаете с гостями в нескольких организациях, вам может потребоваться ограничить их возможности доступа к данным каталога.</span><span class="sxs-lookup"><span data-stu-id="48d0d-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="48d0d-124">Это не позволит им увидеть, кто еще является гостем в каталоге.</span><span class="sxs-lookup"><span data-stu-id="48d0d-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="48d0d-125">Для этого в разделе **ограничения доступа пользователей гостей** выберите пункт **гости-пользователи имеют ограниченный доступ к свойствам и членству в параметрах объектов каталогов** или **доступ гостей к свойствам и членству собственных объектов каталога**.</span><span class="sxs-lookup"><span data-stu-id="48d0d-125">To do this, under **Guest user access restrictions** , select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="48d0d-126">Параметры общего доступа на уровне Организации SharePoint</span><span class="sxs-lookup"><span data-stu-id="48d0d-126">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="48d0d-127">Чтобы пользователи за преданной организацией могли иметь доступ к документу в SharePoint или OneDrive, параметры общего доступа на уровне Организации в SharePoint и OneDrive должны предоставлять доступ пользователям за прев Организации.</span><span class="sxs-lookup"><span data-stu-id="48d0d-127">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="48d0d-128">Параметры на уровне Организации для SharePoint определяют параметры, которые будут доступны для отдельных сайтов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="48d0d-128">The organization-level settings for SharePoint determine the settings that will be available for individual SharePoint sites.</span></span> <span data-ttu-id="48d0d-129">Параметры сайта не могут быть более разрешительнои, чем параметры на уровне Организации.</span><span class="sxs-lookup"><span data-stu-id="48d0d-129">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="48d0d-130">Настройка на уровне Организации для OneDrive определяет уровень общего доступа, который будет доступен в библиотеках OneDrive пользователей.</span><span class="sxs-lookup"><span data-stu-id="48d0d-130">The organization-level setting for OneDrive determines the level of sharing that will be available in users' OneDrive libraries.</span></span>

<span data-ttu-id="48d0d-131">Для SharePoint и OneDrive, чтобы разрешить общий доступ к файлам и папкам, не прошедших проверку подлинности, выберите пункт **все**.</span><span class="sxs-lookup"><span data-stu-id="48d0d-131">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="48d0d-132">Чтобы убедиться, что пользователи, не входящие в организацию, не прошли проверку подлинности, выберите **новые и существующие гости**.</span><span class="sxs-lookup"><span data-stu-id="48d0d-132">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="48d0d-133">Ссылки на *любой пользователь* — это самый простой способ предоставления общего доступа: пользователи, не входящие в вашу организацию, могут открывать эту ссылку без проверки подлинности и свободно передавать ее другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="48d0d-133">*Anyone* links is the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="48d0d-134">В разделе SharePoint выберите параметры с наибольшим количеством разрешений, которые будут необходимы любому сайту в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="48d0d-134">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Снимок экрана: параметры общего доступа в SharePoint на уровне организации](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="48d0d-136">Настройка параметров общего доступа на уровне Организации для SharePoint</span><span class="sxs-lookup"><span data-stu-id="48d0d-136">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="48d0d-137">В центре администрирования Microsoft 365 в левой области навигации в разделе **центры администрирования** щелкните **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="48d0d-137">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers** , click **SharePoint**.</span></span>
2. <span data-ttu-id="48d0d-138">В центре администрирования SharePoint в левой области навигации в разделе **политики** щелкните **общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="48d0d-138">In the SharePoint admin center, in the left navigation pane, under **Policies** , click **Sharing**.</span></span>
3. <span data-ttu-id="48d0d-139">Убедитесь, что для внешнего общего доступа для SharePoint или OneDrive задано значение " **любой пользователь** " или " **новые и существующие гости** ".</span><span class="sxs-lookup"><span data-stu-id="48d0d-139">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="48d0d-140">(Обратите внимание, что параметр OneDrive не может быть более разрешающим, чем параметр SharePoint.)</span><span class="sxs-lookup"><span data-stu-id="48d0d-140">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="48d0d-141">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="48d0d-141">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="48d0d-142">Параметры ссылок по умолчанию на уровне Организации SharePoint</span><span class="sxs-lookup"><span data-stu-id="48d0d-142">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="48d0d-143">Параметры ссылок, которые будут отображаться для пользователей по умолчанию при предоставлении общего доступа к файлам или папкам, определяются параметрами по умолчанию для файлов и ссылок на папки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="48d0d-143">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="48d0d-144">При необходимости пользователи могут изменить тип ссылки на один из других вариантов перед предоставлением общего доступа.</span><span class="sxs-lookup"><span data-stu-id="48d0d-144">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="48d0d-145">Имейте в виду, что этот параметр влияет на сайты SharePoint в Организации, а также на OneDrive.</span><span class="sxs-lookup"><span data-stu-id="48d0d-145">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="48d0d-146">Выберите ссылку из следующих типов, которые затем выбираются по умолчанию, когда пользователи совместно используют файлы и папки:</span><span class="sxs-lookup"><span data-stu-id="48d0d-146">Choose a link from any of the following types which is then selected by default when users share files and folders:</span></span>

- <span data-ttu-id="48d0d-147">**Любой пользователь, имеющий ссылку,** — выбрать этот вариант, если вы собираетесь делать большой объем доступа к файлам и папкам, не прошедшим проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="48d0d-147">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="48d0d-148">Если вы хотите разрешить ссылки для *всех пользователей* , но беспокоитесь о случайном совместном доступе без проверки подлинности, рассмотрите один из других параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="48d0d-148">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="48d0d-149">Этот тип ссылки доступен только в том случае, если вы включили **общий доступ** .</span><span class="sxs-lookup"><span data-stu-id="48d0d-149">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="48d0d-150">**Только люди из вашей организации** — выберите этот вариант, если вы хотите, чтобы большая часть общего доступа к файлам и папкам была доступна пользователям в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="48d0d-150">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="48d0d-151">**Specific people** Если вы собираетесь делать большой объем общего доступа к файлам и папкам для гостей, используйте этот вариант.</span><span class="sxs-lookup"><span data-stu-id="48d0d-151">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="48d0d-152">Этот тип ссылки работает с гостями и требует проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="48d0d-152">This type of link works with guests and requires them to authenticate.</span></span>
 
![Снимок экрана: параметры общего доступа к файлам и папкам в SharePoint на уровне организации](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="48d0d-154">Настройка параметров по умолчанию для ссылок на уровне Организации в SharePoint и OneDrive</span><span class="sxs-lookup"><span data-stu-id="48d0d-154">To set the SharePoint and OneDrive organization-level default link settings</span></span>

1. <span data-ttu-id="48d0d-155">Перейдите на страницу "общий доступ" в центре администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="48d0d-155">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="48d0d-156">В разделе **ссылки на файлы и папки** выберите ссылку для совместного доступа по умолчанию, которую нужно использовать.</span><span class="sxs-lookup"><span data-stu-id="48d0d-156">Under **File and folder links** , select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="48d0d-157">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="48d0d-157">If you made changes, click **Save**.</span></span>

<span data-ttu-id="48d0d-158">Чтобы задать разрешение для ссылки совместного доступа, в разделе **выберите разрешение, выбранное по умолчанию для ссылок для общего доступа.**</span><span class="sxs-lookup"><span data-stu-id="48d0d-158">To set the permission for the sharing link, under **Choose the permission that's selected by default for sharing links.**</span></span>

1. <span data-ttu-id="48d0d-159">Выберите **Просмотр** , если не требуется, чтобы пользователи, не прошедшие проверку подлинности, не могли вносить изменения в файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="48d0d-159">Select **View** if you do not want unauthenticated users to make changes to the files and folders.</span></span>
2. <span data-ttu-id="48d0d-160">Нажмите кнопку **изменить** , если хотите разрешить пользователям, не прошедшим проверку подлинности, вносить изменения в файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="48d0d-160">Select **Edit** if you want to allow unauthenticated users to make changes to the files and folders.</span></span>

<span data-ttu-id="48d0d-161">Обратите внимание на то, что приведенные выше два варианта преддействия могут быть применены не только к гостям и внешним пользователям, но и к внутренним пользователям.</span><span class="sxs-lookup"><span data-stu-id="48d0d-161">Note that the above two premission-options can be applied not only for guests/external users but also for internal users.</span></span> <span data-ttu-id="48d0d-162">Выбор параметра разрешения определяется самоосторожностью.</span><span class="sxs-lookup"><span data-stu-id="48d0d-162">The permission-option you choose is determined by self-discretion.</span></span>

<span data-ttu-id="48d0d-163">Настройка разрешений для ссылок, которые позволяют предоставлять общий доступ всем пользователям</span><span class="sxs-lookup"><span data-stu-id="48d0d-163">To set permissions for links that allow sharing with anyone</span></span>

1. <span data-ttu-id="48d0d-164">С помощью **этих ссылок можно предоставить следующие разрешения:** вложенная область,</span><span class="sxs-lookup"><span data-stu-id="48d0d-164">Under the **These links can give these permissions:** sub-pane,</span></span> 
    1. <span data-ttu-id="48d0d-165">В раскрывающемся списке **файлы** выберите</span><span class="sxs-lookup"><span data-stu-id="48d0d-165">From the **Files** drop-down list,</span></span> 
        1. <span data-ttu-id="48d0d-166">Выберите **Просмотр и редактирование** , если хотите разрешить пользователям, не прошедшим проверку подлинности, вносить изменения в файлы.</span><span class="sxs-lookup"><span data-stu-id="48d0d-166">Select **View and edit** if you want to allow unauthenticated users to make changes to the files.</span></span>
        2. <span data-ttu-id="48d0d-167">Выберите **Просмотр** , если не требуется, чтобы пользователи, не прошедшие проверку подлинности, не могли вносить изменения в файлы.</span><span class="sxs-lookup"><span data-stu-id="48d0d-167">Select **View** if you do not want unauthenticated users to make changes to the files.</span></span>
    2. <span data-ttu-id="48d0d-168">В раскрывающемся списке **папки** выберите</span><span class="sxs-lookup"><span data-stu-id="48d0d-168">From the **Folders** drop-down list,</span></span>
        1. <span data-ttu-id="48d0d-169">Выберите **Просмотр, редактирование и отправка** , если вы хотите разрешить пользователям, не прошедшим проверку подлинности, вносить изменения в папки.</span><span class="sxs-lookup"><span data-stu-id="48d0d-169">Select **View, edit, and upload** if you want to allow unauthenticated users to make changes to the folders.</span></span>
        2. <span data-ttu-id="48d0d-170">Выберите **Просмотр** , если не требуется, чтобы пользователи, не прошедшие проверку подлинности, не могли вносить изменения в папки.</span><span class="sxs-lookup"><span data-stu-id="48d0d-170">Select **View** if you do not want unauthenticated users to make changes to the folders.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="48d0d-171">Параметры общего доступа на уровне сайта SharePoint</span><span class="sxs-lookup"><span data-stu-id="48d0d-171">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="48d0d-172">Если вы используете файлы и папки на сайте SharePoint, вам также нужно проверить параметры общего доступа на уровне сайта для этого сайта.</span><span class="sxs-lookup"><span data-stu-id="48d0d-172">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![Снимок экрана: параметры внешнего общего доступа к сайту SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="48d0d-174">Установка параметров общего доступа на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="48d0d-174">To set site-level sharing settings</span></span>

1. <span data-ttu-id="48d0d-175">В центре администрирования SharePoint в левой области навигации разверните узел **сайты** и выберите пункт **активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="48d0d-175">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="48d0d-176">Выберите сайт, на котором вы хотите предоставить общий доступ к файлам и папкам гостями.</span><span class="sxs-lookup"><span data-stu-id="48d0d-176">Select the site on which you want to share files and folders with guests.</span></span>
3. <span data-ttu-id="48d0d-177">Прокрутите строку вправо (где присутствует выбранный сайт) и щелкните в любом месте **внешнего общего доступа** .</span><span class="sxs-lookup"><span data-stu-id="48d0d-177">Scroll right across the row (in which the selected site is present) and click anywhere in the **External sharing** column.</span></span>
4. <span data-ttu-id="48d0d-178">На открывшейся странице выберите вкладку **политики** .</span><span class="sxs-lookup"><span data-stu-id="48d0d-178">From the page that pops up, click **Policies** tab.</span></span>
5. <span data-ttu-id="48d0d-179">В области **внешний общий доступ** нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="48d0d-179">Under the **External sharing** pane, click **Edit**.</span></span>
6. <span data-ttu-id="48d0d-180">Убедитесь, что для общего доступа задано значение " **любой пользователь** " или " **новые и существующие гости** ".</span><span class="sxs-lookup"><span data-stu-id="48d0d-180">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
7. <span data-ttu-id="48d0d-181">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="48d0d-181">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="48d0d-182">Приглашение пользователей</span><span class="sxs-lookup"><span data-stu-id="48d0d-182">Invite users</span></span>

<span data-ttu-id="48d0d-183">Параметры общего доступа к гостевому доступу теперь настроены; Теперь пользователи могут предоставлять общий доступ к файлам и папкам пользователям, не входящим в вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="48d0d-183">Guest-sharing settings are now configured; so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="48d0d-184">Для получения дополнительных сведений см. [общий доступ к файлам и папкам OneDrive](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) и [общий доступ к файлам и папкам SharePoint](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) .</span><span class="sxs-lookup"><span data-stu-id="48d0d-184">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="48d0d-185">См. также</span><span class="sxs-lookup"><span data-stu-id="48d0d-185">See also</span></span>

[<span data-ttu-id="48d0d-186">Рекомендации по предоставлению общего доступа к файлам и папкам непроверенным пользователям</span><span class="sxs-lookup"><span data-stu-id="48d0d-186">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="48d0d-187">Ограничение возможности случайного раскрытия файлов при предоставлении доступа гостям</span><span class="sxs-lookup"><span data-stu-id="48d0d-187">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="48d0d-188">Интеграция SharePoint и OneDrive с помощью Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="48d0d-188">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
