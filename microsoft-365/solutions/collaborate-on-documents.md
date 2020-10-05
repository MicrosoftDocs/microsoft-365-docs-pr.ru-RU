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
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: В этой статье вы узнаете, как совместно работать с гостями в документе в SharePoint и OneDrive.
ms.openlocfilehash: 1a7591915efa82f1995ce2789e181dc350cd3784
ms.sourcegitcommit: 8589323c1b4ab43aab30597ee66303b0a0eb71ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357786"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="696b6-103">Совместная работа с гостями над документом</span><span class="sxs-lookup"><span data-stu-id="696b6-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="696b6-104">Если вам требуется совместная работа с пользователями, не входящими в вашу организацию, в документы в SharePoint или OneDrive, вы можете отправить им ссылку для совместного доступа к документу.</span><span class="sxs-lookup"><span data-stu-id="696b6-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing link to the document.</span></span> <span data-ttu-id="696b6-105">В этой статье мы рассмотрим действия по настройке Microsoft 365, необходимые для настройки ссылок общего доступа для SharePoint и OneDrive в целях организации.</span><span class="sxs-lookup"><span data-stu-id="696b6-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="696b6-106">Видеодемонстрация</span><span class="sxs-lookup"><span data-stu-id="696b6-106">Video demonstration</span></span>

<span data-ttu-id="696b6-107">В этом видеоролике показаны действия по настройке, описанные в этом документе.</span><span class="sxs-lookup"><span data-stu-id="696b6-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="696b6-108">Параметры связей в Организации Azure</span><span class="sxs-lookup"><span data-stu-id="696b6-108">Azure Organizational relationships settings</span></span>

<span data-ttu-id="696b6-109">Общий доступ в Microsoft 365 регулируется на самом высоком уровне [параметрами организационных отношений в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="696b6-109">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="696b6-110">Если общий доступ к гостям отключен или ограничен в Azure AD, все параметры общего доступа, настроенные в Microsoft 365, будут переопределены.</span><span class="sxs-lookup"><span data-stu-id="696b6-110">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="696b6-111">Проверьте параметры организационных отношений, чтобы предотвратить блокировку общего доступа с гостями.</span><span class="sxs-lookup"><span data-stu-id="696b6-111">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Снимок экрана: страница параметров организационных связей Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="696b6-113">Настройка параметров организационных отношений</span><span class="sxs-lookup"><span data-stu-id="696b6-113">To set organizational relationship settings</span></span>

1. <span data-ttu-id="696b6-114">Выполните вход в Microsoft Azure по адресу [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="696b6-114">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="696b6-115">В области навигации слева выберите **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="696b6-115">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="696b6-116">В области **Обзор** щелкните **организационные связи**.</span><span class="sxs-lookup"><span data-stu-id="696b6-116">In the **Overview** pane, click **Organizational relationships**.</span></span>
4. <span data-ttu-id="696b6-117">В области **организационные связи** щелкните **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="696b6-117">In the **Organizational relationships** pane, click **Settings**.</span></span>
5. <span data-ttu-id="696b6-118">Убедитесь, что у **администраторов и пользователей в роли гостя может быть приглашение** , а **Участники** — значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="696b6-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="696b6-119">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="696b6-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="696b6-120">Обратите внимание на параметры в разделе **ограничения совместной работы** .</span><span class="sxs-lookup"><span data-stu-id="696b6-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="696b6-121">Убедитесь, что домены гостей, с которыми вы хотите работать совместно, не заблокированы.</span><span class="sxs-lookup"><span data-stu-id="696b6-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="696b6-122">Если вы работаете с гостями в нескольких организациях, вам может потребоваться ограничить их возможности доступа к данным каталога.</span><span class="sxs-lookup"><span data-stu-id="696b6-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="696b6-123">Это не позволит им увидеть, кто еще является гостем в каталоге.</span><span class="sxs-lookup"><span data-stu-id="696b6-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="696b6-124">Для этого в разделе **ограничения доступа пользователей гостей**выберите пункт **гости-пользователи имеют ограниченный доступ к свойствам и членству в параметрах объектов каталогов** или **доступ гостей к свойствам и членству собственных объектов каталога**.</span><span class="sxs-lookup"><span data-stu-id="696b6-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="696b6-125">Параметры общего доступа на уровне Организации SharePoint</span><span class="sxs-lookup"><span data-stu-id="696b6-125">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="696b6-126">Чтобы пользователи за преданной организацией могли иметь доступ к документу в SharePoint или OneDrive, параметры общего доступа на уровне Организации в SharePoint и OneDrive должны предоставлять доступ пользователям за прев Организации.</span><span class="sxs-lookup"><span data-stu-id="696b6-126">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="696b6-127">Параметры на уровне Организации для SharePoint определяют параметры, доступные для отдельных сайтов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="696b6-127">The organization-level settings for SharePoint determine what settings are available for individual SharePoint sites.</span></span> <span data-ttu-id="696b6-128">Параметры сайта не могут быть более разрешительнои, чем параметры на уровне Организации.</span><span class="sxs-lookup"><span data-stu-id="696b6-128">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="696b6-129">Настройка уровня Организации для OneDrive определяет уровень общего доступа, доступный в библиотеках OneDrive пользователей.</span><span class="sxs-lookup"><span data-stu-id="696b6-129">The organization-level setting for OneDrive determines what level of sharing is available in users' OneDrive libraries.</span></span>

<span data-ttu-id="696b6-130">Для SharePoint и OneDrive, чтобы разрешить общий доступ к файлам и папкам, не прошедших проверку подлинности, выберите пункт **все**.</span><span class="sxs-lookup"><span data-stu-id="696b6-130">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="696b6-131">Чтобы убедиться, что пользователи, не входящие в организацию, не прошли проверку подлинности, выберите **новые и существующие гости**.</span><span class="sxs-lookup"><span data-stu-id="696b6-131">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="696b6-132">Ссылки на *любой пользователь* проще всего сделать общими: пользователи, не входящие в вашу организацию, могут открывать эту ссылку без проверки подлинности и свободно передавать их другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="696b6-132">*Anyone* links are the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="696b6-133">В разделе SharePoint выберите параметры с наибольшим количеством разрешений, которые будут необходимы любому сайту в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="696b6-133">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Снимок экрана: параметры общего доступа в SharePoint на уровне организации](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="696b6-135">Настройка параметров общего доступа на уровне Организации SharePoint</span><span class="sxs-lookup"><span data-stu-id="696b6-135">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="696b6-136">В центре администрирования Microsoft 365 в области навигации слева в разделе **центры администрирования**щелкните **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="696b6-136">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="696b6-137">Откройте Центр администрирования SharePoint и на панели навигации слева нажмите кнопку **Доступ**.</span><span class="sxs-lookup"><span data-stu-id="696b6-137">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="696b6-138">Убедитесь, что для внешнего общего доступа для SharePoint или OneDrive задано значение " **любой пользователь** " или " **новые и существующие гости**".</span><span class="sxs-lookup"><span data-stu-id="696b6-138">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="696b6-139">(Обратите внимание, что параметр OneDrive не может быть более разрешающим, чем параметр SharePoint.)</span><span class="sxs-lookup"><span data-stu-id="696b6-139">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="696b6-140">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="696b6-140">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="696b6-141">Параметры ссылок по умолчанию на уровне Организации SharePoint</span><span class="sxs-lookup"><span data-stu-id="696b6-141">SharePoint organization level default link settings</span></span>

<span data-ttu-id="696b6-142">Параметры ссылки по умолчанию для файлов и папок определяют, какой вариант ссылки отображается для пользователя по умолчанию при предоставлении общего доступа к файлу или папке.</span><span class="sxs-lookup"><span data-stu-id="696b6-142">The default file and folder link settings determine which link option is shown to the user by default when they share a file or folder.</span></span> <span data-ttu-id="696b6-143">При необходимости пользователи могут изменить тип ссылки на один из других вариантов, прежде чем предоставлять общий доступ.</span><span class="sxs-lookup"><span data-stu-id="696b6-143">Users can change the link type to one of the other options before sharing if desired.</span></span>

<span data-ttu-id="696b6-144">Имейте в виду, что этот параметр влияет на сайты SharePoint в Организации, а также на OneDrive.</span><span class="sxs-lookup"><span data-stu-id="696b6-144">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="696b6-145">Выберите тип ссылки, выбранной по умолчанию, когда пользователи совместно используют файлы и папки:</span><span class="sxs-lookup"><span data-stu-id="696b6-145">Choose the type of link that's selected by default when users share files and folders:</span></span>

- <span data-ttu-id="696b6-146">**Любой пользователь, имеющий ссылку,** — выбрать этот вариант, если вы собираетесь делать большой объем доступа к файлам и папкам, не прошедшим проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="696b6-146">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="696b6-147">Если вы хотите разрешить ссылки для *всех пользователей* , но беспокоитесь о случайном совместном доступе без проверки подлинности, рассмотрите один из других параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="696b6-147">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="696b6-148">Этот тип ссылки доступен только в том случае, если вы включили **общий доступ** .</span><span class="sxs-lookup"><span data-stu-id="696b6-148">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="696b6-149">**Только люди из вашей организации** — выберите этот вариант, если вы хотите, чтобы большая часть общего доступа к файлам и папкам была доступна пользователям в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="696b6-149">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="696b6-150">**Specific people** Если вы собираетесь делать большой объем общего доступа к файлам и папкам для гостей, используйте этот вариант.</span><span class="sxs-lookup"><span data-stu-id="696b6-150">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="696b6-151">Этот тип ссылки работает с гостями и требует проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="696b6-151">This type of link works with guests and requires them to authenticate.</span></span>
 
![Снимок экрана: параметры общего доступа к файлам и папкам в SharePoint на уровне организации](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="696b6-153">Настройка параметров ссылок по умолчанию на уровне Организации в SharePoint и OneDrive</span><span class="sxs-lookup"><span data-stu-id="696b6-153">To set the SharePoint and OneDrive organization level default link settings</span></span>

1. <span data-ttu-id="696b6-154">Перейдите на страницу "общий доступ" в центре администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="696b6-154">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="696b6-155">В разделе **ссылки на файлы и папки**выберите ссылку для совместного доступа по умолчанию, которую нужно использовать.</span><span class="sxs-lookup"><span data-stu-id="696b6-155">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="696b6-156">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="696b6-156">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="696b6-157">Параметры общего доступа на уровне сайта SharePoint</span><span class="sxs-lookup"><span data-stu-id="696b6-157">SharePoint site level sharing settings</span></span>

<span data-ttu-id="696b6-158">Если вы используете файлы и папки на сайте SharePoint, вам также нужно проверить параметры общего доступа на уровне сайта для этого сайта.</span><span class="sxs-lookup"><span data-stu-id="696b6-158">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![Снимок экрана: параметры внешнего общего доступа к сайту SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="696b6-160">Установка параметров общего доступа на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="696b6-160">To set site-level sharing settings</span></span>
1. <span data-ttu-id="696b6-161">Откройте Центр администрирования SharePoint, затем на панели навигации слева разверните меню **Сайты** и нажмите **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="696b6-161">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="696b6-162">Выберите сайт, который вы только что создали.</span><span class="sxs-lookup"><span data-stu-id="696b6-162">Select the site that you just created.</span></span>
3. <span data-ttu-id="696b6-163">На ленте выберите **Доступ**.</span><span class="sxs-lookup"><span data-stu-id="696b6-163">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="696b6-164">Убедитесь, что для общего доступа задано значение " **любой пользователь** " или " **новые и существующие гости**".</span><span class="sxs-lookup"><span data-stu-id="696b6-164">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="696b6-165">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="696b6-165">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="696b6-166">Приглашение пользователей</span><span class="sxs-lookup"><span data-stu-id="696b6-166">Invite users</span></span>

<span data-ttu-id="696b6-167">Параметры общего доступа к гостевой сети настроены, поэтому теперь пользователи могут предоставлять общий доступ к файлам и папкам пользователям, не входящим в вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="696b6-167">Guest sharing settings are now configured, so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="696b6-168">Для получения дополнительных сведений см. [общий доступ к файлам и папкам OneDrive](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) и [общий доступ к файлам и папкам SharePoint](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) .</span><span class="sxs-lookup"><span data-stu-id="696b6-168">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="696b6-169">См. также</span><span class="sxs-lookup"><span data-stu-id="696b6-169">See Also</span></span>

[<span data-ttu-id="696b6-170">Рекомендации по предоставлению общего доступа к файлам и папкам непроверенным пользователям</span><span class="sxs-lookup"><span data-stu-id="696b6-170">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="696b6-171">Ограничение возможности случайного раскрытия файлов при предоставлении доступа гостям</span><span class="sxs-lookup"><span data-stu-id="696b6-171">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="696b6-172">Интеграция SharePoint и OneDrive с помощью Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="696b6-172">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)