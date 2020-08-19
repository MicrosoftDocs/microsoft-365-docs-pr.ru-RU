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
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Сведения о действиях по настройке Microsoft 365, необходимых для настройки сайта SharePoint для совместной работы с гостями.
ms.openlocfilehash: c04114218342a2d65b318c71d061c2a0ed815fab
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "46797820"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="5147d-103">Совместная работа с гостями на сайте</span><span class="sxs-lookup"><span data-stu-id="5147d-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="5147d-104">При необходимости совместной работы с гостями в документах, данных и списках можно использовать сайт SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5147d-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="5147d-105">Современные сайты SharePoint подключены к группам Microsoft 365 и могут управлять членством в сайтах и предоставлять дополнительные инструменты для совместной работы, такие как общий почтовый ящик и календарь.</span><span class="sxs-lookup"><span data-stu-id="5147d-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and calendar.</span></span>

<span data-ttu-id="5147d-106">В этой статье мы рассмотрим действия по настройке Microsoft 365, необходимые для настройки сайта SharePoint для совместной работы с гостями.</span><span class="sxs-lookup"><span data-stu-id="5147d-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="5147d-107">Видеодемонстрация</span><span class="sxs-lookup"><span data-stu-id="5147d-107">Video demonstration</span></span>

<span data-ttu-id="5147d-108">В этом видеоролике показаны действия по настройке, описанные в этом документе.</span><span class="sxs-lookup"><span data-stu-id="5147d-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="5147d-109">Параметры связей в Организации Azure</span><span class="sxs-lookup"><span data-stu-id="5147d-109">Azure Organizational relationships settings</span></span>

<span data-ttu-id="5147d-110">Общий доступ в Microsoft 365 регулируется на самом высоком уровне [параметрами организационных отношений в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="5147d-110">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="5147d-111">Если общий доступ к гостям отключен или ограничен в Azure AD, все параметры общего доступа, настроенные в Microsoft 365, будут переопределены.</span><span class="sxs-lookup"><span data-stu-id="5147d-111">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="5147d-112">Проверьте параметры организационных отношений, чтобы предотвратить блокировку общего доступа с гостями.</span><span class="sxs-lookup"><span data-stu-id="5147d-112">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Снимок экрана: страница параметров организационных связей Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="5147d-114">Настройка параметров организационных отношений</span><span class="sxs-lookup"><span data-stu-id="5147d-114">To set organizational relationship settings</span></span>

1. <span data-ttu-id="5147d-115">Выполните вход в Microsoft Azure по адресу [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="5147d-115">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="5147d-116">В области навигации слева выберите **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="5147d-116">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="5147d-117">В области **Обзор** щелкните **организационные связи**.</span><span class="sxs-lookup"><span data-stu-id="5147d-117">In the **Overview** pane, click **Organizational relationships**.</span></span>
4. <span data-ttu-id="5147d-118">В области **организационные связи** щелкните **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="5147d-118">In the **Organizational relationships** pane, click **Settings**.</span></span>
5. <span data-ttu-id="5147d-119">Убедитесь, что у **администраторов и пользователей в роли гостя может быть приглашение** , а **Участники** — значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="5147d-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="5147d-120">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5147d-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="5147d-121">Обратите внимание на параметры в разделе **ограничения совместной работы** .</span><span class="sxs-lookup"><span data-stu-id="5147d-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="5147d-122">Убедитесь, что домены гостей, с которыми вы хотите работать совместно, не заблокированы.</span><span class="sxs-lookup"><span data-stu-id="5147d-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="5147d-123">Если вы работаете с гостями в нескольких организациях, вам может потребоваться ограничить их возможности доступа к данным каталога.</span><span class="sxs-lookup"><span data-stu-id="5147d-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="5147d-124">Это не позволит им увидеть, кто еще является гостем в каталоге.</span><span class="sxs-lookup"><span data-stu-id="5147d-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="5147d-125">Для этого в разделе **ограничения доступа пользователей гостей**выберите пункт **гости-пользователи имеют ограниченный доступ к свойствам и членству в параметрах объектов каталогов** или **доступ гостей к свойствам и членству собственных объектов каталога**.</span><span class="sxs-lookup"><span data-stu-id="5147d-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="5147d-126">Параметры гостей для групп Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5147d-126">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="5147d-127">Современные сайты SharePoint используют группы Microsoft 365 для управления доступом к сайту.</span><span class="sxs-lookup"><span data-stu-id="5147d-127">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="5147d-128">Для работы гостевых сайтов SharePoint необходимо включить параметры гостевых групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5147d-128">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Снимок экрана: гостевые параметры для групп Microsoft 365 в Центре администрирования Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="5147d-130">Настройка параметров гостя для групп Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5147d-130">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="5147d-131">В центре администрирования Microsoft 365 в левой панели навигации разверните узел **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="5147d-131">In the Microsoft 365 admin center, in the left navigation, expand **Settings**.</span></span>
2. <span data-ttu-id="5147d-132">Щелкните **службы & надстройки**.</span><span class="sxs-lookup"><span data-stu-id="5147d-132">Click **Services & add-ins**.</span></span>
3. <span data-ttu-id="5147d-133">В списке выберите пункт **Microsoft 365 группы**.</span><span class="sxs-lookup"><span data-stu-id="5147d-133">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="5147d-134">Убедитесь, что установлены флажки для членов группы, не входящих в **вашу организацию** , и **разрешите владельцам групп добавлять людей за пределом Организации в группы** .</span><span class="sxs-lookup"><span data-stu-id="5147d-134">Ensure that the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes are both checked.</span></span>
5. <span data-ttu-id="5147d-135">Если вы внесли изменения, нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="5147d-135">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="5147d-136">Параметры общего доступа на уровне Организации SharePoint</span><span class="sxs-lookup"><span data-stu-id="5147d-136">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="5147d-137">Чтобы гости могли иметь доступ к сайтам SharePoint, параметры общего доступа на уровне Организации SharePoint должны разрешить совместное использование с гостями.</span><span class="sxs-lookup"><span data-stu-id="5147d-137">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="5147d-138">Параметры на уровне Организации определяют параметры, доступные для отдельных сайтов.</span><span class="sxs-lookup"><span data-stu-id="5147d-138">The organization-level settings determine what settings are available for individual sites.</span></span> <span data-ttu-id="5147d-139">Параметры сайта не могут быть более разрешительнои, чем параметры на уровне Организации.</span><span class="sxs-lookup"><span data-stu-id="5147d-139">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="5147d-140">Если требуется разрешить общий доступ к файлам и папкам без проверки подлинности, выберите пункт **все**.</span><span class="sxs-lookup"><span data-stu-id="5147d-140">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="5147d-141">Если необходимо обеспечить проверку подлинности всех пользователей за презнакомой Организации, выберите **новые и существующие гости**.</span><span class="sxs-lookup"><span data-stu-id="5147d-141">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="5147d-142">Выберите наиболее разрешительное значение, которое потребуется всем сайтам в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5147d-142">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Снимок экрана: параметры общего доступа в SharePoint на уровне организации](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="5147d-144">Настройка параметров общего доступа на уровне Организации SharePoint</span><span class="sxs-lookup"><span data-stu-id="5147d-144">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="5147d-145">В центре администрирования Microsoft 365 в области навигации слева в разделе **центры администрирования**щелкните **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="5147d-145">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="5147d-146">Откройте Центр администрирования SharePoint и на панели навигации слева нажмите кнопку **Доступ**.</span><span class="sxs-lookup"><span data-stu-id="5147d-146">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="5147d-147">Убедитесь, что для внешнего общего доступа для SharePoint задано значение " **любой пользователь** " или " **новые и существующие гости**".</span><span class="sxs-lookup"><span data-stu-id="5147d-147">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="5147d-148">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5147d-148">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="5147d-149">Создание сайта</span><span class="sxs-lookup"><span data-stu-id="5147d-149">Create a site</span></span>

<span data-ttu-id="5147d-150">Следующий шаг — создание сайта, который планируется использовать для совместной работы с гостями.</span><span class="sxs-lookup"><span data-stu-id="5147d-150">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="5147d-151">Создание сайта</span><span class="sxs-lookup"><span data-stu-id="5147d-151">To create a site</span></span>
1. <span data-ttu-id="5147d-152">В Центре администрирования SharePoint в разделе **Сайты** щелкните **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="5147d-152">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="5147d-153">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="5147d-153">Click **Create**.</span></span>
3. <span data-ttu-id="5147d-154">Щелкните **сайт группы**.</span><span class="sxs-lookup"><span data-stu-id="5147d-154">Click **Team site**.</span></span>
4. <span data-ttu-id="5147d-155">Введите имя сайта и введите имя владельца группы (владельца сайта).</span><span class="sxs-lookup"><span data-stu-id="5147d-155">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="5147d-156">В разделе **Дополнительные параметры**выберите, если вы хотите, чтобы это был общедоступный или частный сайт.</span><span class="sxs-lookup"><span data-stu-id="5147d-156">Under **Advanced settings**, choose if you want this to be a public or private site.</span></span>
6. <span data-ttu-id="5147d-157">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5147d-157">Click **Next**.</span></span>
7. <span data-ttu-id="5147d-158">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="5147d-158">Click **Finish**.</span></span>

<span data-ttu-id="5147d-159">Мы будем приглашать пользователей позже.</span><span class="sxs-lookup"><span data-stu-id="5147d-159">We'll invite users later.</span></span> <span data-ttu-id="5147d-160">После этого важно проверить параметры общего доступа на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="5147d-160">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="5147d-161">Параметры общего доступа на уровне сайта SharePoint</span><span class="sxs-lookup"><span data-stu-id="5147d-161">SharePoint site level sharing settings</span></span>

<span data-ttu-id="5147d-162">Проверьте параметры общего доступа на уровне сайта, чтобы убедиться в том, что они допускают тип доступа, который вы хотите использовать для этого сайта.</span><span class="sxs-lookup"><span data-stu-id="5147d-162">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="5147d-163">Например, если вы настроили параметры на уровне Организации для всех **пользователей**, но хотите, чтобы все гости прошли проверку подлинности для этого сайта, убедитесь, что для параметров общего доступа на уровне сайта задано значение " **новые и существующие гости**".</span><span class="sxs-lookup"><span data-stu-id="5147d-163">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="5147d-164">Обратите внимание на то, что сайт не может быть открыт для пользователей, не прошедших проверку подлинности (параметр "**все** "), но для отдельных файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="5147d-164">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

![Снимок экрана: параметры внешнего общего доступа к сайту SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="5147d-166">Установка параметров общего доступа на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="5147d-166">To set site-level sharing settings</span></span>
1. <span data-ttu-id="5147d-167">Откройте Центр администрирования SharePoint, затем на панели навигации слева разверните меню **Сайты** и нажмите **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="5147d-167">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="5147d-168">Выберите сайт, который вы только что создали.</span><span class="sxs-lookup"><span data-stu-id="5147d-168">Select the site that you just created.</span></span>
3. <span data-ttu-id="5147d-169">На ленте выберите **Доступ**.</span><span class="sxs-lookup"><span data-stu-id="5147d-169">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="5147d-170">Убедитесь, что для общего доступа задано значение " **любой пользователь** " или " **новые и существующие гости**".</span><span class="sxs-lookup"><span data-stu-id="5147d-170">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="5147d-171">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5147d-171">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="5147d-172">Приглашение пользователей</span><span class="sxs-lookup"><span data-stu-id="5147d-172">Invite users</span></span>

<span data-ttu-id="5147d-173">Параметры общего доступа к гостевой сети настроены, поэтому вы можете добавить внутренних пользователей и гостей на сайт.</span><span class="sxs-lookup"><span data-stu-id="5147d-173">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="5147d-174">Доступ к сайту осуществляется через связанную группу Microsoft 365, поэтому мы будем добавлять пользователей.</span><span class="sxs-lookup"><span data-stu-id="5147d-174">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="5147d-175">Приглашение внутренних пользователей в группу</span><span class="sxs-lookup"><span data-stu-id="5147d-175">To invite internal users to a group</span></span>
1. <span data-ttu-id="5147d-176">Перейдите на сайт, где вы хотите добавить пользователей.</span><span class="sxs-lookup"><span data-stu-id="5147d-176">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="5147d-177">Щелкните **элементы** в правом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="5147d-177">Click **Members** in the upper right.</span></span>
3. <span data-ttu-id="5147d-178">Нажмите **Добавить участников**.</span><span class="sxs-lookup"><span data-stu-id="5147d-178">Click **Add members**.</span></span>
4. <span data-ttu-id="5147d-179">Введите имена или адреса электронной почты пользователей, которых вы хотите пригласить на сайт, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5147d-179">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="5147d-180">Гостевые пользователи не могут добавляться с сайта.</span><span class="sxs-lookup"><span data-stu-id="5147d-180">Guest users can't be added from the site.</span></span> <span data-ttu-id="5147d-181">Их необходимо добавить с помощью Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="5147d-181">You need to add them using Outlook on the web.</span></span>

<span data-ttu-id="5147d-182">Приглашение гостей в группу</span><span class="sxs-lookup"><span data-stu-id="5147d-182">To invite guests to a group</span></span>
1. <span data-ttu-id="5147d-183">В Outlook в Интернете в разделе **группы**выберите группу, в которую вы хотите добавить участников.</span><span class="sxs-lookup"><span data-stu-id="5147d-183">In Outlook on the web, under **Groups**, click the group where you want to add members.</span></span>
2. <span data-ttu-id="5147d-184">Откройте карточку контакта группы, а затем в разделе **Дополнительные параметры** (...) нажмите кнопку **Добавить участников**.</span><span class="sxs-lookup"><span data-stu-id="5147d-184">Open the group contact card, and then, under **More options** (...), click **Add members**.</span></span>
3. <span data-ttu-id="5147d-185">Введите адреса электронной почты гостей, которых вы хотите пригласить, и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="5147d-185">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
4. <span data-ttu-id="5147d-186">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="5147d-186">Click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="5147d-187">См. также</span><span class="sxs-lookup"><span data-stu-id="5147d-187">See Also</span></span>

[<span data-ttu-id="5147d-188">Рекомендации по предоставлению общего доступа к файлам и папкам непроверенным пользователям</span><span class="sxs-lookup"><span data-stu-id="5147d-188">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="5147d-189">Ограничение возможности случайного раскрытия файлов при предоставлении доступа гостям</span><span class="sxs-lookup"><span data-stu-id="5147d-189">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="5147d-190">Создание безопасной среды гостевого общего доступа</span><span class="sxs-lookup"><span data-stu-id="5147d-190">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="5147d-191">Создание экстрасети B2B с управляемыми гостями</span><span class="sxs-lookup"><span data-stu-id="5147d-191">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

