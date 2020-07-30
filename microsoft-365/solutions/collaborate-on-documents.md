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
ms.openlocfilehash: cb3c527304f0d286b4a1a0147d07537b0fae4eda
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527922"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="7ebb5-103">Совместная работа с гостями над документом</span><span class="sxs-lookup"><span data-stu-id="7ebb5-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="7ebb5-104">Если вам требуется совместная работа с пользователями, не входящими в вашу организацию, в документы в SharePoint или OneDrive, вы можете отправить им ссылку для совместного доступа к документу.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing link to the document.</span></span> <span data-ttu-id="7ebb5-105">В этой статье мы рассмотрим действия по настройке Microsoft 365, необходимые для настройки ссылок общего доступа для SharePoint и OneDrive в целях организации.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="7ebb5-106">Видеодемонстрация</span><span class="sxs-lookup"><span data-stu-id="7ebb5-106">Video demonstration</span></span>

<span data-ttu-id="7ebb5-107">В этом видеоролике показаны действия по настройке, описанные в этом документе.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="7ebb5-108">Параметры связей в Организации Azure</span><span class="sxs-lookup"><span data-stu-id="7ebb5-108">Azure Organizational relationships settings</span></span>

<span data-ttu-id="7ebb5-109">Общий доступ в Microsoft 365 регулируется на самом высоком уровне параметрами организационных отношений в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-109">Sharing in Microsoft 365 is governed at its highest level by the organizational relationships settings in Azure Active Directory.</span></span> <span data-ttu-id="7ebb5-110">Если общий доступ к гостям отключен или ограничен в Azure AD, все параметры общего доступа, настроенные в Microsoft 365, будут переопределены.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-110">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="7ebb5-111">Проверьте параметры организационных отношений, чтобы предотвратить блокировку общего доступа с гостями.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-111">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Снимок экрана: страница параметров организационных связей Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="7ebb5-113">Настройка параметров организационных отношений</span><span class="sxs-lookup"><span data-stu-id="7ebb5-113">To set organizational relationship settings</span></span>

1. <span data-ttu-id="7ebb5-114">Выполните вход в Microsoft Azure по адресу [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="7ebb5-114">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="7ebb5-115">В области навигации слева выберите **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-115">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="7ebb5-116">В области **Обзор** щелкните **организационные связи**.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-116">In the **Overview** pane, click **Organizational relationships**.</span></span>
4. <span data-ttu-id="7ebb5-117">В области **организационные связи** щелкните **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-117">In the **Organizational relationships** pane, click **Settings**.</span></span>
5. <span data-ttu-id="7ebb5-118">Убедитесь, что у **администраторов и пользователей в роли гостя может быть приглашение** , а **Участники** — значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="7ebb5-119">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="7ebb5-120">Обратите внимание на параметры в разделе **ограничения совместной работы** .</span><span class="sxs-lookup"><span data-stu-id="7ebb5-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="7ebb5-121">Убедитесь, что домены гостей, с которыми вы хотите работать совместно, не заблокированы.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="7ebb5-122">Параметры общего доступа на уровне Организации SharePoint</span><span class="sxs-lookup"><span data-stu-id="7ebb5-122">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="7ebb5-123">Чтобы пользователи за преданной организацией могли иметь доступ к документу в SharePoint или OneDrive, параметры общего доступа на уровне Организации в SharePoint и OneDrive должны предоставлять доступ пользователям за прев Организации.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-123">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="7ebb5-124">Параметры на уровне Организации для SharePoint определяют параметры, доступные для отдельных сайтов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-124">The organization-level settings for SharePoint determine what settings are available for individual SharePoint sites.</span></span> <span data-ttu-id="7ebb5-125">Параметры сайта не могут быть более разрешительнои, чем параметры на уровне Организации.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-125">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="7ebb5-126">Настройка уровня Организации для OneDrive определяет уровень общего доступа, доступный в библиотеках OneDrive пользователей.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-126">The organization-level setting for OneDrive determines what level of sharing is available in users' OneDrive libraries.</span></span>

<span data-ttu-id="7ebb5-127">Для SharePoint и OneDrive, чтобы разрешить общий доступ к файлам и папкам, не прошедших проверку подлинности, выберите пункт **все**.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-127">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="7ebb5-128">Чтобы убедиться, что пользователи, не входящие в организацию, не прошли проверку подлинности, выберите **новые и существующие гости**.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-128">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="7ebb5-129">Ссылки на *любой пользователь* проще всего сделать общими: пользователи, не входящие в вашу организацию, могут открывать эту ссылку без проверки подлинности и свободно передавать их другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-129">*Anyone* links are the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="7ebb5-130">В разделе SharePoint выберите параметры с наибольшим количеством разрешений, которые будут необходимы любому сайту в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-130">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Снимок экрана: параметры общего доступа в SharePoint на уровне организации](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="7ebb5-132">Настройка параметров общего доступа на уровне Организации SharePoint</span><span class="sxs-lookup"><span data-stu-id="7ebb5-132">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="7ebb5-133">В центре администрирования Microsoft 365 в области навигации слева в разделе **центры администрирования**щелкните **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-133">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="7ebb5-134">Откройте Центр администрирования SharePoint и на панели навигации слева нажмите кнопку **Доступ**.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-134">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="7ebb5-135">Убедитесь, что для внешнего общего доступа для SharePoint или OneDrive задано значение " **любой пользователь** " или " **новые и существующие гости**".</span><span class="sxs-lookup"><span data-stu-id="7ebb5-135">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="7ebb5-136">(Обратите внимание, что параметр OneDrive не может быть более разрешающим, чем параметр SharePoint.)</span><span class="sxs-lookup"><span data-stu-id="7ebb5-136">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="7ebb5-137">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-137">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="7ebb5-138">Параметры ссылок по умолчанию на уровне Организации SharePoint</span><span class="sxs-lookup"><span data-stu-id="7ebb5-138">SharePoint organization level default link settings</span></span>

<span data-ttu-id="7ebb5-139">Параметры ссылки по умолчанию для файлов и папок определяют, какой вариант ссылки отображается для пользователя по умолчанию при предоставлении общего доступа к файлу или папке.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-139">The default file and folder link settings determine which link option is shown to the user by default when they share a file or folder.</span></span> <span data-ttu-id="7ebb5-140">При необходимости пользователи могут изменить тип ссылки на один из других вариантов, прежде чем предоставлять общий доступ.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-140">Users can change the link type to one of the other options before sharing if desired.</span></span>

<span data-ttu-id="7ebb5-141">Имейте в виду, что этот параметр влияет на сайты SharePoint в Организации, а также на OneDrive.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-141">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="7ebb5-142">Выберите тип ссылки, выбранной по умолчанию, когда пользователи совместно используют файлы и папки:</span><span class="sxs-lookup"><span data-stu-id="7ebb5-142">Choose the type of link that's selected by default when users share files and folders:</span></span>

- <span data-ttu-id="7ebb5-143">**Любой пользователь, имеющий ссылку,** — выбрать этот вариант, если вы собираетесь делать большой объем доступа к файлам и папкам, не прошедшим проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-143">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="7ebb5-144">Если вы хотите разрешить ссылки для *всех пользователей* , но беспокоитесь о случайном совместном доступе без проверки подлинности, рассмотрите один из других параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-144">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="7ebb5-145">Этот тип ссылки доступен только в том случае, если вы включили **общий доступ** .</span><span class="sxs-lookup"><span data-stu-id="7ebb5-145">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="7ebb5-146">**Только люди из вашей организации** — выберите этот вариант, если вы хотите, чтобы большая часть общего доступа к файлам и папкам была доступна пользователям в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-146">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="7ebb5-147">**Specific people** Если вы собираетесь делать большой объем общего доступа к файлам и папкам для гостей, используйте этот вариант.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-147">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="7ebb5-148">Этот тип ссылки работает с гостями и требует проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-148">This type of link works with guests and requires them to authenticate.</span></span>
 
![Снимок экрана: параметры общего доступа к файлам и папкам в SharePoint на уровне организации](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="7ebb5-150">Настройка параметров ссылок по умолчанию на уровне Организации в SharePoint и OneDrive</span><span class="sxs-lookup"><span data-stu-id="7ebb5-150">To set the SharePoint and OneDrive organization level default link settings</span></span>

1. <span data-ttu-id="7ebb5-151">Перейдите на страницу "общий доступ" в центре администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-151">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="7ebb5-152">В разделе **ссылки на файлы и папки**выберите ссылку для совместного доступа по умолчанию, которую нужно использовать.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-152">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="7ebb5-153">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-153">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="7ebb5-154">Параметры общего доступа на уровне сайта SharePoint</span><span class="sxs-lookup"><span data-stu-id="7ebb5-154">SharePoint site level sharing settings</span></span>

<span data-ttu-id="7ebb5-155">При совместном использовании файлов и фодлерс, которые находятся на сайте SharePoint, необходимо также проверить параметры общего доступа на уровне сайта для этого сайта.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-155">If you're sharing files and fodlers that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![Снимок экрана: параметры внешнего общего доступа к сайту SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="7ebb5-157">Установка параметров общего доступа на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="7ebb5-157">To set site-level sharing settings</span></span>
1. <span data-ttu-id="7ebb5-158">Откройте Центр администрирования SharePoint, затем на панели навигации слева разверните меню **Сайты** и нажмите **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-158">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="7ebb5-159">Выберите сайт, который вы только что создали.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-159">Select the site that you just created.</span></span>
3. <span data-ttu-id="7ebb5-160">На ленте выберите **Доступ**.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-160">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="7ebb5-161">Убедитесь, что для общего доступа задано значение " **любой пользователь** " или " **новые и существующие гости**".</span><span class="sxs-lookup"><span data-stu-id="7ebb5-161">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="7ebb5-162">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-162">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="7ebb5-163">Приглашение пользователей</span><span class="sxs-lookup"><span data-stu-id="7ebb5-163">Invite users</span></span>

<span data-ttu-id="7ebb5-164">Параметры общего доступа к гостевой сети настроены, поэтому теперь пользователи могут предоставлять общий доступ к файлам и папкам пользователям, не входящим в вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="7ebb5-164">Guest sharing settings are now configured, so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="7ebb5-165">Для получения дополнительных сведений см. [общий доступ к файлам и папкам OneDrive](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) и [общий доступ к файлам и папкам SharePoint](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) .</span><span class="sxs-lookup"><span data-stu-id="7ebb5-165">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ebb5-166">См. также</span><span class="sxs-lookup"><span data-stu-id="7ebb5-166">See Also</span></span>

[<span data-ttu-id="7ebb5-167">Рекомендации по предоставлению общего доступа к файлам и папкам непроверенным пользователям</span><span class="sxs-lookup"><span data-stu-id="7ebb5-167">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="7ebb5-168">Ограничение возможности случайного раскрытия файлов при предоставлении доступа гостям</span><span class="sxs-lookup"><span data-stu-id="7ebb5-168">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)