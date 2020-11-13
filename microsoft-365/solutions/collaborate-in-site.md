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
description: Сведения о действиях по настройке Microsoft 365, необходимых для настройки сайта SharePoint для совместной работы с гостями.
ms.openlocfilehash: df9068ef4b4eb35f946b78d8f7fefa01c254c79c
ms.sourcegitcommit: 8a726ed7ec19a8728c079780fa4d343a5f759fbb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2020
ms.locfileid: "49029997"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="6f173-103">Совместная работа с гостями на сайте</span><span class="sxs-lookup"><span data-stu-id="6f173-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="6f173-104">При необходимости совместной работы с гостями в документах, данных и списках можно использовать сайт SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6f173-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="6f173-105">Современные сайты SharePoint подключены к группам Microsoft 365 и могут управлять членством в сайтах и предоставлять дополнительные инструменты для совместной работы, такие как общий почтовый ящик и календарь.</span><span class="sxs-lookup"><span data-stu-id="6f173-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and a calendar.</span></span>

<span data-ttu-id="6f173-106">В этой статье мы рассмотрим действия по настройке Microsoft 365, необходимые для настройки сайта SharePoint для совместной работы с гостями.</span><span class="sxs-lookup"><span data-stu-id="6f173-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="6f173-107">Видеодемонстрация</span><span class="sxs-lookup"><span data-stu-id="6f173-107">Video demonstration</span></span>

<span data-ttu-id="6f173-108">В этом видеоролике показаны действия по настройке, описанные в этом документе.</span><span class="sxs-lookup"><span data-stu-id="6f173-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="6f173-109">Параметры внешней совместной работы Azure</span><span class="sxs-lookup"><span data-stu-id="6f173-109">Azure external collaboration settings</span></span>

<span data-ttu-id="6f173-110">Общий доступ в Microsoft 365 регулируется на самом высоком уровне [параметрами организационных отношений в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="6f173-110">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="6f173-111">Если общий доступ к гостям отключен или ограничен в Azure AD, этот параметр переопределяет все параметры общего доступа, настроенные в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6f173-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="6f173-112">Проверьте параметры внешних совместной работы и убедитесь, что совместное использование с гостями не заблокировано.</span><span class="sxs-lookup"><span data-stu-id="6f173-112">Check the external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Снимок экрана: страница параметров внешней совместной работы Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="6f173-114">Настройка параметров внешней совместной работы</span><span class="sxs-lookup"><span data-stu-id="6f173-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="6f173-115">Выполните вход в Azure Active Directory по адресу [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="6f173-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="6f173-116">В области навигации слева выберите **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="6f173-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="6f173-117">Щелкните **Внешние удостоверения**.</span><span class="sxs-lookup"><span data-stu-id="6f173-117">Click **External identities**.</span></span>
4. <span data-ttu-id="6f173-118">На экране "начало **работы** " в левой области навигации щелкните элемент **внешние параметры совместной работы**.</span><span class="sxs-lookup"><span data-stu-id="6f173-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="6f173-119">Убедитесь, что у **администраторов и пользователей в роли гостя может быть приглашение** , а **Участники** — значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="6f173-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="6f173-120">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="6f173-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="6f173-121">Обратите внимание на параметры в разделе **ограничения совместной работы** .</span><span class="sxs-lookup"><span data-stu-id="6f173-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="6f173-122">Убедитесь, что домены гостей, с которыми вы хотите работать совместно, не заблокированы.</span><span class="sxs-lookup"><span data-stu-id="6f173-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="6f173-123">Если вы работаете с гостями в нескольких организациях, вам может потребоваться ограничить их возможности доступа к данным каталога.</span><span class="sxs-lookup"><span data-stu-id="6f173-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="6f173-124">Это не позволит им увидеть, кто еще является гостем в каталоге.</span><span class="sxs-lookup"><span data-stu-id="6f173-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="6f173-125">Для этого в разделе **ограничения доступа пользователей гостей** выберите пункт **гости-пользователи имеют ограниченный доступ к свойствам и членству в параметрах объектов каталогов** или **доступ гостей к свойствам и членству собственных объектов каталога**.</span><span class="sxs-lookup"><span data-stu-id="6f173-125">To do this, under **Guest user access restrictions** , select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="6f173-126">Параметры гостей для групп Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6f173-126">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="6f173-127">Современные сайты SharePoint используют группы Microsoft 365 для управления доступом к сайту.</span><span class="sxs-lookup"><span data-stu-id="6f173-127">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="6f173-128">Для работы гостевых сайтов SharePoint необходимо включить параметры гостевых групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6f173-128">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Снимок экрана: гостевые параметры для групп Microsoft 365 в Центре администрирования Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="6f173-130">Настройка параметров гостя для групп Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6f173-130">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="6f173-131">В центре администрирования Microsoft 365 в левой области навигации разверните узел **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="6f173-131">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="6f173-132">Щелкните **Параметры организации**.</span><span class="sxs-lookup"><span data-stu-id="6f173-132">Click **Org settings**.</span></span>
3. <span data-ttu-id="6f173-133">В списке выберите пункт **Microsoft 365 группы**.</span><span class="sxs-lookup"><span data-stu-id="6f173-133">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="6f173-134">Убедитесь, что **владельцы групп Let добавляют пользователей за пределом "гости" в Microsoft 365 группы как гости** и получают флажки **доступ к группе "участники гостевой группы** ".</span><span class="sxs-lookup"><span data-stu-id="6f173-134">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="6f173-135">Если вы внесли изменения, нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="6f173-135">If you made changes, click **Save changes**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="6f173-136">Параметры общего доступа на уровне Организации SharePoint</span><span class="sxs-lookup"><span data-stu-id="6f173-136">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="6f173-137">Чтобы гости могли иметь доступ к сайтам SharePoint, параметры общего доступа на уровне Организации SharePoint должны разрешить совместное использование с гостями.</span><span class="sxs-lookup"><span data-stu-id="6f173-137">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="6f173-138">Параметры на уровне Организации определяют параметры, которые будут доступны для отдельных сайтов.</span><span class="sxs-lookup"><span data-stu-id="6f173-138">The organization-level settings determine the settings that will be available for individual sites.</span></span> <span data-ttu-id="6f173-139">Параметры сайта не могут быть более разрешительнои, чем параметры на уровне Организации.</span><span class="sxs-lookup"><span data-stu-id="6f173-139">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="6f173-140">Если требуется разрешить общий доступ к файлам и папкам без проверки подлинности, выберите пункт **все**.</span><span class="sxs-lookup"><span data-stu-id="6f173-140">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="6f173-141">Если необходимо обеспечить проверку подлинности всех пользователей за презнакомой Организации, выберите **новые и существующие гости**.</span><span class="sxs-lookup"><span data-stu-id="6f173-141">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="6f173-142">Выберите наиболее разрешительное значение, которое потребуется всем сайтам в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="6f173-142">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Снимок экрана: параметры общего доступа в SharePoint на уровне организации](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="6f173-144">Настройка параметров общего доступа на уровне Организации для SharePoint</span><span class="sxs-lookup"><span data-stu-id="6f173-144">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="6f173-145">В центре администрирования Microsoft 365 в левой области навигации в разделе **центры администрирования** щелкните **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="6f173-145">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers** , click **SharePoint**.</span></span>
2. <span data-ttu-id="6f173-146">В центре администрирования SharePoint в левой области навигации в разделе **политики** щелкните **общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="6f173-146">In the SharePoint admin center, in the left navigation pane, under **Policies** , click **Sharing**.</span></span>
3. <span data-ttu-id="6f173-147">Убедитесь, что для внешнего общего доступа для SharePoint задано значение " **любой пользователь** " или " **новые и существующие гости** ".</span><span class="sxs-lookup"><span data-stu-id="6f173-147">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="6f173-148">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="6f173-148">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="6f173-149">Создание сайта</span><span class="sxs-lookup"><span data-stu-id="6f173-149">Create a site</span></span>

<span data-ttu-id="6f173-150">Следующий шаг — создание сайта, который планируется использовать для совместной работы с гостями.</span><span class="sxs-lookup"><span data-stu-id="6f173-150">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="6f173-151">Создание сайта</span><span class="sxs-lookup"><span data-stu-id="6f173-151">To create a site</span></span>
1. <span data-ttu-id="6f173-152">В Центре администрирования SharePoint в разделе **Сайты** щелкните **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="6f173-152">In the SharePoint admin center, under **Sites** , click **Active sites**.</span></span>
2. <span data-ttu-id="6f173-153">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="6f173-153">Click **Create**.</span></span>
3. <span data-ttu-id="6f173-154">Щелкните **сайт группы**.</span><span class="sxs-lookup"><span data-stu-id="6f173-154">Click **Team site**.</span></span>
4. <span data-ttu-id="6f173-155">Введите имя сайта и введите имя владельца группы (владельца сайта).</span><span class="sxs-lookup"><span data-stu-id="6f173-155">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="6f173-156">В разделе **Дополнительные параметры** выберите, если вы хотите, чтобы этот сайт был общедоступным или частным.</span><span class="sxs-lookup"><span data-stu-id="6f173-156">Under **Advanced settings** , choose if you want this site to be a public or private one.</span></span>
6. <span data-ttu-id="6f173-157">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6f173-157">Click **Next**.</span></span>
7. <span data-ttu-id="6f173-158">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="6f173-158">Click **Finish**.</span></span>

<span data-ttu-id="6f173-159">Мы будем приглашать пользователей позже.</span><span class="sxs-lookup"><span data-stu-id="6f173-159">We'll invite users later.</span></span> <span data-ttu-id="6f173-160">После этого важно проверить параметры общего доступа на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="6f173-160">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="6f173-161">Параметры общего доступа на уровне сайта SharePoint</span><span class="sxs-lookup"><span data-stu-id="6f173-161">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="6f173-162">Проверьте параметры общего доступа на уровне сайта, чтобы убедиться в том, что они допускают тип доступа, который вы хотите использовать для этого сайта.</span><span class="sxs-lookup"><span data-stu-id="6f173-162">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="6f173-163">Например, если вы настроили параметры на уровне Организации для всех **пользователей** , но хотите, чтобы все гости прошли проверку подлинности для этого сайта, убедитесь, что для параметров общего доступа на уровне сайта задано значение " **новые и существующие гости** ".</span><span class="sxs-lookup"><span data-stu-id="6f173-163">For example, if you set the organization-level settings to **Anyone** , but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="6f173-164">Обратите внимание на то, что сайт не может быть открыт для пользователей, не прошедших проверку подлинности (параметр " **все** "), но для отдельных файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="6f173-164">Note that the site cannot be shared with unauthenticated people ( **Anyone** setting), but individual files and folders can.</span></span>

![Снимок экрана: параметры внешнего общего доступа к сайту SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="6f173-166">Установка параметров общего доступа на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="6f173-166">To set site-level sharing settings</span></span>
1. <span data-ttu-id="6f173-167">Откройте Центр администрирования SharePoint, затем на панели навигации слева разверните меню **Сайты** и нажмите **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="6f173-167">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="6f173-168">Выберите сайт, к которому вы хотите предоставить общий доступ.</span><span class="sxs-lookup"><span data-stu-id="6f173-168">Select the site that you want to share.</span></span>
3. <span data-ttu-id="6f173-169">Нажмите кнопку..., а затем выберите **общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="6f173-169">Click ..., and click **Sharing**.</span></span>
4. <span data-ttu-id="6f173-170">Убедитесь, что для общего доступа задано значение " **любой пользователь** " или " **новые и существующие гости** ".</span><span class="sxs-lookup"><span data-stu-id="6f173-170">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="6f173-171">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="6f173-171">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="6f173-172">Приглашение пользователей</span><span class="sxs-lookup"><span data-stu-id="6f173-172">Invite users</span></span>

<span data-ttu-id="6f173-173">Параметры общего доступа к гостевой сети настроены, поэтому вы можете добавить внутренних пользователей и гостей на сайт.</span><span class="sxs-lookup"><span data-stu-id="6f173-173">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="6f173-174">Доступ к сайту осуществляется через связанную группу Microsoft 365, поэтому мы будем добавлять пользователей.</span><span class="sxs-lookup"><span data-stu-id="6f173-174">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="6f173-175">Приглашение внутренних пользователей в группу</span><span class="sxs-lookup"><span data-stu-id="6f173-175">To invite internal users to a group</span></span>
1. <span data-ttu-id="6f173-176">Перейдите на сайт, где вы хотите добавить пользователей.</span><span class="sxs-lookup"><span data-stu-id="6f173-176">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="6f173-177">Нажмите ссылку **Members (участники** ) в правом верхнем углу, которая обозначает количество участников.</span><span class="sxs-lookup"><span data-stu-id="6f173-177">Click **Members** link in the upper right which denotes the member count.</span></span>
3. <span data-ttu-id="6f173-178">Нажмите **Добавить участников**.</span><span class="sxs-lookup"><span data-stu-id="6f173-178">Click **Add members**.</span></span>
4. <span data-ttu-id="6f173-179">Введите имена или адреса электронной почты пользователей, которых вы хотите пригласить на сайт, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="6f173-179">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="6f173-180">Гостевые пользователи не могут добавляться с сайта.</span><span class="sxs-lookup"><span data-stu-id="6f173-180">Guest users can't be added from the site.</span></span> <span data-ttu-id="6f173-181">Их необходимо добавить с помощью Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="6f173-181">You need to add them using Outlook on the web.</span></span> <span data-ttu-id="6f173-182">Таким образом, чтобы добавить и пригласить гостей в группу, щелкните URL-адрес сайта в столбце **URL-адреса**  , чтобы перейти на страницу, зависящую от сайта.</span><span class="sxs-lookup"><span data-stu-id="6f173-182">Therefore, as a prerequisite to add and invite guests to a group, click the URL of the site in the **URL**  column to navigate to the site-specific page.</span></span> <span data-ttu-id="6f173-183">На этой странице щелкните значок средства **запуска приложений** и выберите **Outlook**.</span><span class="sxs-lookup"><span data-stu-id="6f173-183">From this page, click the **App launcher** icon and select **Outlook**.</span></span> <span data-ttu-id="6f173-184">Это экран, с которого вы можете пригласить гостей в группу, для которой описана процедура, описанная ниже.</span><span class="sxs-lookup"><span data-stu-id="6f173-184">This is the screen from which you can invite guests into a group, for which procedure is described below.</span></span>

<span data-ttu-id="6f173-185">Приглашение гостей в группу</span><span class="sxs-lookup"><span data-stu-id="6f173-185">To invite guests to a group</span></span>
1. <span data-ttu-id="6f173-186">В разделе **группы** выберите группу, в которую вы хотите пригласить гостей.</span><span class="sxs-lookup"><span data-stu-id="6f173-186">Under **Groups** , click the group to which you want to invite guests.</span></span>
2. <span data-ttu-id="6f173-187">Откройте карточку контакта группы, щелкните ссылку **Участники** в правом верхнем углу (ссылка, указывающая на число участников).</span><span class="sxs-lookup"><span data-stu-id="6f173-187">Open the group contact card, click **Members** link in the upper right (the link which denotes the member count).</span></span>
3. <span data-ttu-id="6f173-188">Нажмите кнопку **Добавить участников**.</span><span class="sxs-lookup"><span data-stu-id="6f173-188">click **Add members**.</span></span>
4. <span data-ttu-id="6f173-189">Введите адреса электронной почты гостей, которых вы хотите пригласить, и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="6f173-189">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
5. <span data-ttu-id="6f173-190">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="6f173-190">Click **Close**.</span></span>
<span data-ttu-id="6f173-191">Обратите внимание, что вам нужно нажать кнопку **Закрыть** только в том случае, если вы не являетесь владельцем группы, и в результате не можете добавить гостя в группу.</span><span class="sxs-lookup"><span data-stu-id="6f173-191">Note that you need to click **Close** only if you are not the owner of the group and as a result, you are not allowed to add the guest into the group.</span></span> <span data-ttu-id="6f173-192">В таких случаях запрос на добавление гостя в группу передается владельцу группы для утверждения.</span><span class="sxs-lookup"><span data-stu-id="6f173-192">In such cases, the request to add the guest into the group is transferred to the group owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f173-193">См. также</span><span class="sxs-lookup"><span data-stu-id="6f173-193">See also</span></span>

[<span data-ttu-id="6f173-194">Рекомендации по предоставлению общего доступа к файлам и папкам непроверенным пользователям</span><span class="sxs-lookup"><span data-stu-id="6f173-194">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="6f173-195">Ограничение возможности случайного раскрытия файлов при предоставлении доступа гостям</span><span class="sxs-lookup"><span data-stu-id="6f173-195">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="6f173-196">Создание безопасной среды гостевого общего доступа</span><span class="sxs-lookup"><span data-stu-id="6f173-196">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="6f173-197">Создание экстрасети B2B с управляемыми гостями</span><span class="sxs-lookup"><span data-stu-id="6f173-197">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="6f173-198">Интеграция SharePoint и OneDrive с помощью Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="6f173-198">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
