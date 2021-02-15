---
title: Совместная работа с гостями на сайте
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
description: Узнайте о действиях по настройке Microsoft 365, необходимых для настройки сайта SharePoint для совместной работы с гостями.
ms.openlocfilehash: 6862fe715fe2f19b968b773bc6df6c70c207a44f
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663528"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="5a041-103">Совместная работа с гостями на сайте</span><span class="sxs-lookup"><span data-stu-id="5a041-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="5a041-104">Если вам нужно совместно работать с гостями в документах, данных и списках, можно использовать сайт SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5a041-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="5a041-105">Современные сайты SharePoint подключены к группам Microsoft 365 и могут управлять членством на сайте и предоставлять дополнительные средства совместной работы, такие как общий почтовый ящик и календарь.</span><span class="sxs-lookup"><span data-stu-id="5a041-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and a calendar.</span></span>

<span data-ttu-id="5a041-106">В этой статье мы разберем действия по настройке Microsoft 365, необходимые для настройки сайта SharePoint для совместной работы с гостями.</span><span class="sxs-lookup"><span data-stu-id="5a041-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="5a041-107">Видеодемонстрация</span><span class="sxs-lookup"><span data-stu-id="5a041-107">Video demonstration</span></span>

<span data-ttu-id="5a041-108">В этом видео показаны действия по настройке, описанные в этом документе.</span><span class="sxs-lookup"><span data-stu-id="5a041-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="5a041-109">Параметры внешней совместной работы Azure</span><span class="sxs-lookup"><span data-stu-id="5a041-109">Azure external collaboration settings</span></span>

<span data-ttu-id="5a041-110">Общий доступ в Microsoft 365 управляется на самом высоком уровне с помощью параметров внешней совместной работы [B2B в Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)</span><span class="sxs-lookup"><span data-stu-id="5a041-110">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="5a041-111">Если в Azure AD отключен или запрещен гостевой общий доступ, этот параметр переопределит все параметры общего доступа, настроенные в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5a041-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="5a041-112">Проверьте параметры внешней совместной работы B2B, чтобы убедиться, что общий доступ гостям не заблокирован.</span><span class="sxs-lookup"><span data-stu-id="5a041-112">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Снимок экрана: страница параметров внешней совместной работы Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="5a041-114">Настройка параметров внешней совместной работы</span><span class="sxs-lookup"><span data-stu-id="5a041-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="5a041-115">Войдите в Azure Active Directory [https://aad.portal.azure.com](https://aad.portal.azure.com) по</span><span class="sxs-lookup"><span data-stu-id="5a041-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="5a041-116">В левой области навигации щелкните **Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="5a041-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="5a041-117">Щелкните **внешние удостоверения.**</span><span class="sxs-lookup"><span data-stu-id="5a041-117">Click **External identities**.</span></span>
4. <span data-ttu-id="5a041-118">На экране **"Начало работы"** в левой области навигации щелкните **параметры внешней совместной работы.**</span><span class="sxs-lookup"><span data-stu-id="5a041-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="5a041-119">**Убедитесь, что администраторы** и пользователи в  роли приглашенного гостя могут приглашать гостей, а для участников установлено значение **"Да".**</span><span class="sxs-lookup"><span data-stu-id="5a041-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="5a041-120">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5a041-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="5a041-121">Обратите внимание на параметры в разделе **"Ограничения для совместной работы".**</span><span class="sxs-lookup"><span data-stu-id="5a041-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="5a041-122">Убедитесь, что домены гостей, с которых вы хотите сотрудничать, не блокируются.</span><span class="sxs-lookup"><span data-stu-id="5a041-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="5a041-123">Если вы работаете с гостями из нескольких организаций, вы можете ограничить их возможность доступа к данным каталога.</span><span class="sxs-lookup"><span data-stu-id="5a041-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="5a041-124">Это не позволит им увидеть, кто еще является гостем в каталоге.</span><span class="sxs-lookup"><span data-stu-id="5a041-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="5a041-125">Для этого в соответствии с ограничениями  доступа гостевых пользователей доступ к гостевых пользователей ограничен доступом к свойствам и членством в параметрах объектов каталога или доступ гостевых пользователей ограничен свойствами и членством в их собственных объектах **каталогов.**</span><span class="sxs-lookup"><span data-stu-id="5a041-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="5a041-126">Гостевая настройка групп Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5a041-126">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="5a041-127">Современные сайты SharePoint используют группы Microsoft 365 для управления доступом к сайту.</span><span class="sxs-lookup"><span data-stu-id="5a041-127">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="5a041-128">Чтобы гостевой доступ на сайтах SharePoint работал, параметры гостей групп Microsoft 365 должны быть включены.</span><span class="sxs-lookup"><span data-stu-id="5a041-128">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Снимок экрана: гостевые параметры для групп Microsoft 365 в Центре администрирования Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="5a041-130">Настройка гостевых параметров групп Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5a041-130">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="5a041-131">В Центре администрирования Microsoft 365 в левой области навигации **разорите параметров.**</span><span class="sxs-lookup"><span data-stu-id="5a041-131">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="5a041-132">Щелкните **параметры организации.**</span><span class="sxs-lookup"><span data-stu-id="5a041-132">Click **Org settings**.</span></span>
3. <span data-ttu-id="5a041-133">В списке выберите **"Группы Microsoft 365".**</span><span class="sxs-lookup"><span data-stu-id="5a041-133">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="5a041-134">Убедитесь, что владельцы группы могут добавлять пользователей за пределами  вашей организации в группы **Microsoft 365** в качестве гостей, и чтобы участники группы гостей получили доступ к флажкам содержимого группы гостей.</span><span class="sxs-lookup"><span data-stu-id="5a041-134">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="5a041-135">Если вы влияли на изменения, нажмите **кнопку "Сохранить изменения".**</span><span class="sxs-lookup"><span data-stu-id="5a041-135">If you made changes, click **Save changes**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="5a041-136">Параметры общего доступа на уровне организации SharePoint</span><span class="sxs-lookup"><span data-stu-id="5a041-136">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="5a041-137">Чтобы у гостей был доступ к сайтам SharePoint, параметры общего доступа на уровне организации SharePoint должны разрешать общий доступ гостям.</span><span class="sxs-lookup"><span data-stu-id="5a041-137">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="5a041-138">Параметры на уровне организации определяют параметры, которые будут доступны для отдельных сайтов.</span><span class="sxs-lookup"><span data-stu-id="5a041-138">The organization-level settings determine the settings that will be available for individual sites.</span></span> <span data-ttu-id="5a041-139">Параметры сайта не могут быть более нео разрешательными, чем параметры на уровне организации.</span><span class="sxs-lookup"><span data-stu-id="5a041-139">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="5a041-140">Если вы хотите разрешить общий доступ к файлам и папам безauthenticated, выберите **"Все".**</span><span class="sxs-lookup"><span data-stu-id="5a041-140">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="5a041-141">Если вы хотите убедиться, что все люди за пределами организации должны проверить подлинность, выберите **"Новые" и "Существующие гости".**</span><span class="sxs-lookup"><span data-stu-id="5a041-141">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="5a041-142">Выберите самый недопустимый параметр, который потребуется любому сайту в организации.</span><span class="sxs-lookup"><span data-stu-id="5a041-142">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Снимок экрана: параметры общего доступа в SharePoint на уровне организации](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="5a041-144">Настройка параметров общего доступа на уровне организации SharePoint</span><span class="sxs-lookup"><span data-stu-id="5a041-144">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="5a041-145">В Центре администрирования Microsoft 365 в левой области навигации в центре администрирования **щелкните** **SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="5a041-145">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="5a041-146">В Центре администрирования SharePoint в области навигации слева в разделе **"Политики"** щелкните **"Общий доступ".**</span><span class="sxs-lookup"><span data-stu-id="5a041-146">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="5a041-147">Убедитесь, что для внешнего общего доступа для SharePoint установлено **"Любой"** или **"Новый" и "Существующие гости".**</span><span class="sxs-lookup"><span data-stu-id="5a041-147">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="5a041-148">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5a041-148">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="5a041-149">Создание сайта</span><span class="sxs-lookup"><span data-stu-id="5a041-149">Create a site</span></span>

<span data-ttu-id="5a041-150">Следующим шагом является создание сайта, который планируется использовать для совместной работы с гостями.</span><span class="sxs-lookup"><span data-stu-id="5a041-150">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="5a041-151">Создание сайта</span><span class="sxs-lookup"><span data-stu-id="5a041-151">To create a site</span></span>
1. <span data-ttu-id="5a041-152">В Центре администрирования SharePoint в разделе **Сайты** щелкните **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="5a041-152">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="5a041-153">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="5a041-153">Click **Create**.</span></span>
3. <span data-ttu-id="5a041-154">Щелкните **сайт группы.**</span><span class="sxs-lookup"><span data-stu-id="5a041-154">Click **Team site**.</span></span>
4. <span data-ttu-id="5a041-155">Введите имя сайта и введите имя владельца группы (владельца сайта).</span><span class="sxs-lookup"><span data-stu-id="5a041-155">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="5a041-156">В **области "Дополнительные параметры"** выберите, должен ли этот сайт быть общедоступным или частным.</span><span class="sxs-lookup"><span data-stu-id="5a041-156">Under **Advanced settings**, choose if you want this site to be a public or private one.</span></span>
6. <span data-ttu-id="5a041-157">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5a041-157">Click **Next**.</span></span>
7. <span data-ttu-id="5a041-158">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="5a041-158">Click **Finish**.</span></span>

<span data-ttu-id="5a041-159">Мы приглашаем пользователей позже.</span><span class="sxs-lookup"><span data-stu-id="5a041-159">We'll invite users later.</span></span> <span data-ttu-id="5a041-160">Затем важно проверить параметры общего доступа на уровне сайта для этого сайта.</span><span class="sxs-lookup"><span data-stu-id="5a041-160">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="5a041-161">Параметры общего доступа на уровне сайта SharePoint</span><span class="sxs-lookup"><span data-stu-id="5a041-161">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="5a041-162">Проверьте параметры общего доступа на уровне сайта, чтобы убедиться, что они позволяют использовать нужный тип доступа для этого сайта.</span><span class="sxs-lookup"><span data-stu-id="5a041-162">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="5a041-163">Например, если для параметров на уровне организации установлено "Все", но вы хотите, чтобы все гости могли проверить подлинность для этого сайта, убедитесь, что для параметров общего доступа на уровне сайта установлено "Новые" и "Существующие гости". </span><span class="sxs-lookup"><span data-stu-id="5a041-163">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="5a041-164">Обратите внимание, что доступ к сайту не может быть общим для непроверяющих людей **(параметр** "Любой"), но отдельные файлы и папки могут быть.</span><span class="sxs-lookup"><span data-stu-id="5a041-164">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

<span data-ttu-id="5a041-165">Вы также можете использовать [метки конфиденциальности для управления настройками](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)внешнего общего доступа для сайтов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5a041-165">You can also use [sensitivity labels to control external sharing settings for SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

![Снимок экрана: параметры внешнего общего доступа к сайту SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="5a041-167">Настройка параметров общего доступа на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="5a041-167">To set site-level sharing settings</span></span>
1. <span data-ttu-id="5a041-168">Откройте Центр администрирования SharePoint, затем на панели навигации слева разверните меню **Сайты** и нажмите **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="5a041-168">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="5a041-169">Выберите сайт, который вы хотите поделиться.</span><span class="sxs-lookup"><span data-stu-id="5a041-169">Select the site that you want to share.</span></span>
3. <span data-ttu-id="5a041-170">Щелкните ...и щелкните **"Общий доступ".**</span><span class="sxs-lookup"><span data-stu-id="5a041-170">Click ..., and click **Sharing**.</span></span>
4. <span data-ttu-id="5a041-171">Убедитесь, что для общего доступа установлено **"Все",** **"Создать" и "Существующие гости".**</span><span class="sxs-lookup"><span data-stu-id="5a041-171">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="5a041-172">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5a041-172">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="5a041-173">Приглашение пользователей</span><span class="sxs-lookup"><span data-stu-id="5a041-173">Invite users</span></span>

<span data-ttu-id="5a041-174">Теперь параметры гостевого общего доступа настроены, поэтому вы можете приступить к добавлению внутренних пользователей и гостей на сайт.</span><span class="sxs-lookup"><span data-stu-id="5a041-174">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="5a041-175">Доступ к сайту контролируется через связанную группу Microsoft 365, поэтому мы добавим в нее пользователей.</span><span class="sxs-lookup"><span data-stu-id="5a041-175">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="5a041-176">Приглашение внутренних пользователей в группу</span><span class="sxs-lookup"><span data-stu-id="5a041-176">To invite internal users to a group</span></span>
1. <span data-ttu-id="5a041-177">Перейдите на сайт, на который вы хотите добавить пользователей.</span><span class="sxs-lookup"><span data-stu-id="5a041-177">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="5a041-178">Щелкните **ссылку** "Участники" в правом верхнем правом направлении, обозначая количество участников.</span><span class="sxs-lookup"><span data-stu-id="5a041-178">Click **Members** link in the upper right which denotes the member count.</span></span>
3. <span data-ttu-id="5a041-179">Нажмите **Добавить участников**.</span><span class="sxs-lookup"><span data-stu-id="5a041-179">Click **Add members**.</span></span>
4. <span data-ttu-id="5a041-180">Введите имена или адреса электронной почты пользователей, которых вы хотите пригласить на сайт, и нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="5a041-180">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="5a041-181">Гостей нельзя добавить с сайта.</span><span class="sxs-lookup"><span data-stu-id="5a041-181">Guests can't be added from the site.</span></span> <span data-ttu-id="5a041-182">Их необходимо добавить с помощью Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="5a041-182">You need to add them using Outlook on the web.</span></span> <span data-ttu-id="5a041-183">Таким образом, чтобы добавить гостей в группу и пригласить их, необходимо  щелкнуть URL-адрес сайта в столбце URL-адреса, чтобы перейти на страницу для конкретного сайта.</span><span class="sxs-lookup"><span data-stu-id="5a041-183">Therefore, as a prerequisite to add and invite guests to a group, click the URL of the site in the **URL**  column to navigate to the site-specific page.</span></span> <span data-ttu-id="5a041-184">На этой странице щелкните **значок запуска** приложений и выберите **Outlook.**</span><span class="sxs-lookup"><span data-stu-id="5a041-184">From this page, click the **App launcher** icon and select **Outlook**.</span></span> <span data-ttu-id="5a041-185">Это экран, с которого можно приглашать гостей в группу, для которой описана процедура ниже.</span><span class="sxs-lookup"><span data-stu-id="5a041-185">This is the screen from which you can invite guests into a group, for which procedure is described below.</span></span>

<span data-ttu-id="5a041-186">Приглашение гостей в группу</span><span class="sxs-lookup"><span data-stu-id="5a041-186">To invite guests to a group</span></span>
1. <span data-ttu-id="5a041-187">В **группе** выберите группу, в которую вы хотите пригласить гостей.</span><span class="sxs-lookup"><span data-stu-id="5a041-187">Under **Groups**, click the group to which you want to invite guests.</span></span>
2. <span data-ttu-id="5a041-188">Откройте карточку контакта группы и щелкните **ссылку "Участники"** в правом верхнем (ссылка, обозначая количество участников).</span><span class="sxs-lookup"><span data-stu-id="5a041-188">Open the group contact card, click **Members** link in the upper right (the link which denotes the member count).</span></span>
3. <span data-ttu-id="5a041-189">Нажмите **кнопку "Добавить участников"**.</span><span class="sxs-lookup"><span data-stu-id="5a041-189">click **Add members**.</span></span>
4. <span data-ttu-id="5a041-190">Введите адреса электронной почты гостей, которые вы хотите пригласить, и нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="5a041-190">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
5. <span data-ttu-id="5a041-191">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="5a041-191">Click **Close**.</span></span>
<span data-ttu-id="5a041-192">Обратите внимание, что нажать кнопку **"Закрыть"** следует только в том случае, если вы не является владельцем группы, и в результате вы не сможете добавить гостя в группу.</span><span class="sxs-lookup"><span data-stu-id="5a041-192">Note that you need to click **Close** only if you are not the owner of the group and as a result, you are not allowed to add the guest into the group.</span></span> <span data-ttu-id="5a041-193">В таких случаях запрос на добавление гостя в группу передается владельцу группы для утверждения.</span><span class="sxs-lookup"><span data-stu-id="5a041-193">In such cases, the request to add the guest into the group is transferred to the group owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a041-194">См. также</span><span class="sxs-lookup"><span data-stu-id="5a041-194">See also</span></span>

[<span data-ttu-id="5a041-195">Рекомендации по предоставлению общего доступа к файлам и папкам непроверенным пользователям</span><span class="sxs-lookup"><span data-stu-id="5a041-195">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="5a041-196">Ограничение возможности случайного раскрытия файлов при предоставлении доступа гостям</span><span class="sxs-lookup"><span data-stu-id="5a041-196">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="5a041-197">Создание безопасной среды гостевого общего доступа</span><span class="sxs-lookup"><span data-stu-id="5a041-197">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="5a041-198">Создание экстрасети B2B с управляемыми гостями</span><span class="sxs-lookup"><span data-stu-id="5a041-198">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="5a041-199">Интеграция SharePoint и OneDrive с Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="5a041-199">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
