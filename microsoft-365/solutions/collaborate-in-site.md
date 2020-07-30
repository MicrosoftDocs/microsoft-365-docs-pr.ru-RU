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
ms.openlocfilehash: 320fb21f19c9616e78f56e519cb804e3e03b2b45
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527910"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="df4c9-103">Совместная работа с гостями на сайте</span><span class="sxs-lookup"><span data-stu-id="df4c9-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="df4c9-104">При необходимости совместной работы с гостями в документах, данных и списках можно использовать сайт SharePoint.</span><span class="sxs-lookup"><span data-stu-id="df4c9-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="df4c9-105">Современные сайты SharePoint подключены к группам Microsoft 365 и могут управлять членством в сайтах и предоставлять дополнительные инструменты для совместной работы, такие как общий почтовый ящик и календарь.</span><span class="sxs-lookup"><span data-stu-id="df4c9-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and calendar.</span></span>

<span data-ttu-id="df4c9-106">В этой статье мы рассмотрим действия по настройке Microsoft 365, необходимые для настройки сайта SharePoint для совместной работы с гостями.</span><span class="sxs-lookup"><span data-stu-id="df4c9-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="df4c9-107">Видеодемонстрация</span><span class="sxs-lookup"><span data-stu-id="df4c9-107">Video demonstration</span></span>

<span data-ttu-id="df4c9-108">В этом видеоролике показаны действия по настройке, описанные в этом документе.</span><span class="sxs-lookup"><span data-stu-id="df4c9-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="df4c9-109">Параметры связей в Организации Azure</span><span class="sxs-lookup"><span data-stu-id="df4c9-109">Azure Organizational relationships settings</span></span>

<span data-ttu-id="df4c9-110">Общий доступ в Microsoft 365 регулируется на самом высоком уровне параметрами организационных отношений в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="df4c9-110">Sharing in Microsoft 365 is governed at its highest level by the organizational relationships settings in Azure Active Directory.</span></span> <span data-ttu-id="df4c9-111">Если общий доступ к гостям отключен или ограничен в Azure AD, все параметры общего доступа, настроенные в Microsoft 365, будут переопределены.</span><span class="sxs-lookup"><span data-stu-id="df4c9-111">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="df4c9-112">Проверьте параметры организационных отношений, чтобы предотвратить блокировку общего доступа с гостями.</span><span class="sxs-lookup"><span data-stu-id="df4c9-112">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Снимок экрана: страница параметров организационных связей Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="df4c9-114">Настройка параметров организационных отношений</span><span class="sxs-lookup"><span data-stu-id="df4c9-114">To set organizational relationship settings</span></span>

1. <span data-ttu-id="df4c9-115">Выполните вход в Microsoft Azure по адресу [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="df4c9-115">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="df4c9-116">В области навигации слева выберите **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="df4c9-116">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="df4c9-117">В области **Обзор** щелкните **организационные связи**.</span><span class="sxs-lookup"><span data-stu-id="df4c9-117">In the **Overview** pane, click **Organizational relationships**.</span></span>
4. <span data-ttu-id="df4c9-118">В области **организационные связи** щелкните **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="df4c9-118">In the **Organizational relationships** pane, click **Settings**.</span></span>
5. <span data-ttu-id="df4c9-119">Убедитесь, что у **администраторов и пользователей в роли гостя может быть приглашение** , а **Участники** — значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="df4c9-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="df4c9-120">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="df4c9-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="df4c9-121">Обратите внимание на параметры в разделе **ограничения совместной работы** .</span><span class="sxs-lookup"><span data-stu-id="df4c9-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="df4c9-122">Убедитесь, что домены гостей, с которыми вы хотите работать совместно, не заблокированы.</span><span class="sxs-lookup"><span data-stu-id="df4c9-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="df4c9-123">Параметры гостей для групп Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="df4c9-123">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="df4c9-124">Современные сайты SharePoint используют группы Microsoft 365 для управления доступом к сайту.</span><span class="sxs-lookup"><span data-stu-id="df4c9-124">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="df4c9-125">Для работы гостевых сайтов SharePoint необходимо включить параметры гостевых групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="df4c9-125">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Снимок экрана: гостевые параметры для групп Microsoft 365 в Центре администрирования Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="df4c9-127">Настройка параметров гостя для групп Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="df4c9-127">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="df4c9-128">В центре администрирования Microsoft 365 в левой панели навигации разверните узел **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="df4c9-128">In the Microsoft 365 admin center, in the left navigation, expand **Settings**.</span></span>
2. <span data-ttu-id="df4c9-129">Щелкните **службы & надстройки**.</span><span class="sxs-lookup"><span data-stu-id="df4c9-129">Click **Services & add-ins**.</span></span>
3. <span data-ttu-id="df4c9-130">В списке выберите пункт **Microsoft 365 группы**.</span><span class="sxs-lookup"><span data-stu-id="df4c9-130">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="df4c9-131">Убедитесь, что установлены флажки для членов группы, не входящих в **вашу организацию** , и **разрешите владельцам групп добавлять людей за пределом Организации в группы** .</span><span class="sxs-lookup"><span data-stu-id="df4c9-131">Ensure that the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes are both checked.</span></span>
5. <span data-ttu-id="df4c9-132">Если вы внесли изменения, нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="df4c9-132">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="df4c9-133">Параметры общего доступа на уровне Организации SharePoint</span><span class="sxs-lookup"><span data-stu-id="df4c9-133">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="df4c9-134">Чтобы гости могли иметь доступ к сайтам SharePoint, параметры общего доступа на уровне Организации SharePoint должны разрешить совместное использование с гостями.</span><span class="sxs-lookup"><span data-stu-id="df4c9-134">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="df4c9-135">Параметры на уровне Организации определяют параметры, доступные для отдельных сайтов.</span><span class="sxs-lookup"><span data-stu-id="df4c9-135">The organization-level settings determine what settings are available for individual sites.</span></span> <span data-ttu-id="df4c9-136">Параметры сайта не могут быть более разрешительнои, чем параметры на уровне Организации.</span><span class="sxs-lookup"><span data-stu-id="df4c9-136">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="df4c9-137">Если требуется разрешить общий доступ к файлам и папкам без проверки подлинности, выберите пункт **все**.</span><span class="sxs-lookup"><span data-stu-id="df4c9-137">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="df4c9-138">Если необходимо обеспечить проверку подлинности всех пользователей за презнакомой Организации, выберите **новые и существующие гости**.</span><span class="sxs-lookup"><span data-stu-id="df4c9-138">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="df4c9-139">Выберите наиболее разрешительное значение, которое потребуется всем сайтам в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="df4c9-139">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Снимок экрана: параметры общего доступа в SharePoint на уровне организации](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="df4c9-141">Настройка параметров общего доступа на уровне Организации SharePoint</span><span class="sxs-lookup"><span data-stu-id="df4c9-141">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="df4c9-142">В центре администрирования Microsoft 365 в области навигации слева в разделе **центры администрирования**щелкните **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="df4c9-142">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="df4c9-143">Откройте Центр администрирования SharePoint и на панели навигации слева нажмите кнопку **Доступ**.</span><span class="sxs-lookup"><span data-stu-id="df4c9-143">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="df4c9-144">Убедитесь, что для внешнего общего доступа для SharePoint задано значение " **любой пользователь** " или " **новые и существующие гости**".</span><span class="sxs-lookup"><span data-stu-id="df4c9-144">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="df4c9-145">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="df4c9-145">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="df4c9-146">Создание сайта</span><span class="sxs-lookup"><span data-stu-id="df4c9-146">Create a site</span></span>

<span data-ttu-id="df4c9-147">Следующий шаг — создание сайта, который планируется использовать для совместной работы с гостями.</span><span class="sxs-lookup"><span data-stu-id="df4c9-147">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="df4c9-148">Создание сайта</span><span class="sxs-lookup"><span data-stu-id="df4c9-148">To create a site</span></span>
1. <span data-ttu-id="df4c9-149">В Центре администрирования SharePoint в разделе **Сайты** щелкните **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="df4c9-149">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="df4c9-150">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="df4c9-150">Click **Create**.</span></span>
3. <span data-ttu-id="df4c9-151">Щелкните **сайт группы**.</span><span class="sxs-lookup"><span data-stu-id="df4c9-151">Click **Team site**.</span></span>
4. <span data-ttu-id="df4c9-152">Введите имя сайта и введите имя владельца группы (владельца сайта).</span><span class="sxs-lookup"><span data-stu-id="df4c9-152">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="df4c9-153">В разделе **Дополнительные параметры**выберите, если вы хотите, чтобы это был общедоступный или частный сайт.</span><span class="sxs-lookup"><span data-stu-id="df4c9-153">Under **Advanced settings**, choose if you want this to be a public or private site.</span></span>
6. <span data-ttu-id="df4c9-154">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="df4c9-154">Click **Next**.</span></span>
7. <span data-ttu-id="df4c9-155">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="df4c9-155">Click **Finish**.</span></span>

<span data-ttu-id="df4c9-156">Мы будем приглашать пользователей позже.</span><span class="sxs-lookup"><span data-stu-id="df4c9-156">We'll invite users later.</span></span> <span data-ttu-id="df4c9-157">После этого важно проверить параметры общего доступа на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="df4c9-157">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="df4c9-158">Параметры общего доступа на уровне сайта SharePoint</span><span class="sxs-lookup"><span data-stu-id="df4c9-158">SharePoint site level sharing settings</span></span>

<span data-ttu-id="df4c9-159">Проверьте параметры общего доступа на уровне сайта, чтобы убедиться в том, что они допускают тип доступа, который вы хотите использовать для этого сайта.</span><span class="sxs-lookup"><span data-stu-id="df4c9-159">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="df4c9-160">Например, если вы настроили параметры на уровне Организации для всех **пользователей**, но хотите, чтобы все гости прошли проверку подлинности для этого сайта, убедитесь, что для параметров общего доступа на уровне сайта задано значение " **новые и существующие гости**".</span><span class="sxs-lookup"><span data-stu-id="df4c9-160">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="df4c9-161">Обратите внимание на то, что сайт не может быть открыт для пользователей, не прошедших проверку подлинности (параметр "**все** "), но для отдельных файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="df4c9-161">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

![Снимок экрана: параметры внешнего общего доступа к сайту SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="df4c9-163">Установка параметров общего доступа на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="df4c9-163">To set site-level sharing settings</span></span>
1. <span data-ttu-id="df4c9-164">Откройте Центр администрирования SharePoint, затем на панели навигации слева разверните меню **Сайты** и нажмите **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="df4c9-164">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="df4c9-165">Выберите сайт, который вы только что создали.</span><span class="sxs-lookup"><span data-stu-id="df4c9-165">Select the site that you just created.</span></span>
3. <span data-ttu-id="df4c9-166">На ленте выберите **Доступ**.</span><span class="sxs-lookup"><span data-stu-id="df4c9-166">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="df4c9-167">Убедитесь, что для общего доступа задано значение " **любой пользователь** " или " **новые и существующие гости**".</span><span class="sxs-lookup"><span data-stu-id="df4c9-167">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="df4c9-168">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="df4c9-168">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="df4c9-169">Приглашение пользователей</span><span class="sxs-lookup"><span data-stu-id="df4c9-169">Invite users</span></span>

<span data-ttu-id="df4c9-170">Параметры общего доступа к гостевой сети настроены, поэтому вы можете добавить внутренних пользователей и гостей на сайт.</span><span class="sxs-lookup"><span data-stu-id="df4c9-170">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="df4c9-171">Доступ к сайту осуществляется через связанную группу Microsoft 365, поэтому мы будем добавлять пользователей.</span><span class="sxs-lookup"><span data-stu-id="df4c9-171">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="df4c9-172">Приглашение внутренних пользователей в группу</span><span class="sxs-lookup"><span data-stu-id="df4c9-172">To invite internal users to a group</span></span>
1. <span data-ttu-id="df4c9-173">Перейдите на сайт, где вы хотите добавить пользователей.</span><span class="sxs-lookup"><span data-stu-id="df4c9-173">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="df4c9-174">Щелкните **элементы** в правом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="df4c9-174">Click **Members** in the upper right.</span></span>
3. <span data-ttu-id="df4c9-175">Нажмите **Добавить участников**.</span><span class="sxs-lookup"><span data-stu-id="df4c9-175">Click **Add members**.</span></span>
4. <span data-ttu-id="df4c9-176">Введите имена или адреса электронной почты пользователей, которых вы хотите пригласить на сайт, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="df4c9-176">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="df4c9-177">Гостевые пользователи не могут добавляться с сайта.</span><span class="sxs-lookup"><span data-stu-id="df4c9-177">Guest users can't be added from the site.</span></span> <span data-ttu-id="df4c9-178">Их необходимо добавить с помощью Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="df4c9-178">You need to add them using Outlook on the web.</span></span>

<span data-ttu-id="df4c9-179">Приглашение гостей в группу</span><span class="sxs-lookup"><span data-stu-id="df4c9-179">To invite guests to a group</span></span>
1. <span data-ttu-id="df4c9-180">В Outlook в Интернете в разделе **группы**выберите группу, в которую вы хотите добавить участников.</span><span class="sxs-lookup"><span data-stu-id="df4c9-180">In Outlook on the web, under **Groups**, click the group where you want to add members.</span></span>
2. <span data-ttu-id="df4c9-181">Откройте карточку контакта группы, а затем в разделе **Дополнительные параметры** (...) нажмите кнопку **Добавить участников**.</span><span class="sxs-lookup"><span data-stu-id="df4c9-181">Open the group contact card, and then, under **More options** (...), click **Add members**.</span></span>
3. <span data-ttu-id="df4c9-182">Введите адреса электронной почты гостей, которых вы хотите пригласить, и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="df4c9-182">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
4. <span data-ttu-id="df4c9-183">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="df4c9-183">Click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="df4c9-184">См. также</span><span class="sxs-lookup"><span data-stu-id="df4c9-184">See Also</span></span>

[<span data-ttu-id="df4c9-185">Рекомендации по предоставлению общего доступа к файлам и папкам непроверенным пользователям</span><span class="sxs-lookup"><span data-stu-id="df4c9-185">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="df4c9-186">Ограничение возможности случайного раскрытия файлов при предоставлении доступа гостям</span><span class="sxs-lookup"><span data-stu-id="df4c9-186">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="df4c9-187">Создание безопасной среды гостевого общего доступа</span><span class="sxs-lookup"><span data-stu-id="df4c9-187">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="df4c9-188">Создание экстрасети B2B с управляемыми гостями</span><span class="sxs-lookup"><span data-stu-id="df4c9-188">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

