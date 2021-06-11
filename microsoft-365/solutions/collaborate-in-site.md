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
recommendations: false
description: Узнайте о шагах Microsoft 365 конфигурации, необходимых для SharePoint сайта для совместной работы с гостями.
ms.openlocfilehash: f91b9c64dbdca8ed7e3ada3315cb57f1c728f838
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539255"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="a2dfe-103">Совместная работа с гостями на сайте</span><span class="sxs-lookup"><span data-stu-id="a2dfe-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="a2dfe-104">Если вам необходимо сотрудничать с гостями в документах, данных и списках, вы можете использовать SharePoint сайт.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="a2dfe-105">Современные SharePoint подключены к Microsoft 365 и могут управлять членством на сайте и предоставлять дополнительные средства совместной работы, такие как общий почтовый ящик и календарь.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and a calendar.</span></span>

<span data-ttu-id="a2dfe-106">В этой статье мы проявим Microsoft 365 действий по настройке, необходимых для SharePoint сайта для совместной работы с гостями.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="a2dfe-107">Видеодемонстрация</span><span class="sxs-lookup"><span data-stu-id="a2dfe-107">Video demonstration</span></span>

<span data-ttu-id="a2dfe-108">В этом видео показаны действия по настройке, описанные в этом документе.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="a2dfe-109">Параметры внешней совместной работы Azure</span><span class="sxs-lookup"><span data-stu-id="a2dfe-109">Azure external collaboration settings</span></span>

<span data-ttu-id="a2dfe-110">Общий доступ в Microsoft 365 настраивается на самом высоком уровне с помощью [параметров внешней совместной работы B2B в Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="a2dfe-110">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="a2dfe-111">Если гостевой общий доступ отключен или ограничен в Azure AD, этот параметр переопределит все параметры общего доступа, настроенные в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="a2dfe-112">Проверьте параметры внешней совместной работы B2B, чтобы обеспечить, чтобы общий доступ к гостям не был заблокирован.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-112">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Снимок экрана Azure Active Directory внешней Параметры страницы](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="a2dfe-114">Чтобы настроить параметры внешней совместной работы, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="a2dfe-115">Войдите в Azure Active Directory на сайте [https://aad.portal.azure.com](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="a2dfe-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="a2dfe-116">В области навигации слева щелкните **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="a2dfe-117">Нажмите **Внешние удостоверения**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-117">Click **External identities**.</span></span>
4. <span data-ttu-id="a2dfe-118">На экране **Начало работы** в области навигации слева щелкните **Параметры внешней совместной работы**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="a2dfe-119">Убедитесь, что для параметров **Администраторы и пользователи с ролью "Приглашающий гостей" могут приглашать** и **Участники могут приглашать** установлено значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="a2dfe-120">Если вы внесли изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="a2dfe-121">Обратите внимание на параметры в разделе **Ограничения совместной работы**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="a2dfe-122">Убедитесь, что домены гостей, с которыми вы хотите сотрудничать, не заблокированы.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="a2dfe-123">Если вы работаете с гостями из нескольких организаций, вы можете ограничить их доступ к данным каталога.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="a2dfe-124">Это не позволит им видеть других гостей в каталоге.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="a2dfe-125">Для этого в разделе **Ограничения доступа гостевых пользователей** выберите **Гостевые пользователи имеют ограниченный доступ к свойствам и членству в параметрах объектов каталога** или **Доступ гостевых пользователей ограничен свойствами и членством в их собственных объектах каталога**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="a2dfe-126">Настройка параметров гостей для групп Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a2dfe-126">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="a2dfe-127">Современные SharePoint используют Microsoft 365 группы для управления доступом к сайту.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-127">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="a2dfe-128">Параметры Microsoft 365 групп необходимо включить для того, чтобы гостевой доступ SharePoint для работы сайтов.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-128">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Снимок экрана: настройка параметров гостей для групп Microsoft 365 в Центре администрирования Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="a2dfe-130">Чтобы настроить параметры гостей для групп Microsoft 365, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-130">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="a2dfe-131">В Центре администрирования Microsoft 365 в области навигации слева разверните раздел **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-131">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="a2dfe-132">Нажмите **Параметры организации**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-132">Click **Org settings**.</span></span>
3. <span data-ttu-id="a2dfe-133">Выберите в списке **Группы Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-133">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="a2dfe-134">Убедитесь, что рядом с пунктами **Разрешить владельцам групп добавлять людей за пределами вашей организации в группы Microsoft 365 в качестве гостей** и **Разрешить гостевым участникам группы получать доступ к содержимому группы** установлены флажки.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-134">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="a2dfe-135">Если вы внесли изменения, нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-135">If you made changes, click **Save changes**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="a2dfe-136">SharePoint параметров общего доступа на уровне организации</span><span class="sxs-lookup"><span data-stu-id="a2dfe-136">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="a2dfe-137">Чтобы у гостей был доступ к сайтам SharePoint, параметры SharePoint на уровне организации должны разрешать общий доступ к гостям.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-137">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="a2dfe-138">Параметры уровня организации определяют параметры, доступные для отдельных сайтов.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-138">The organization-level settings determine the settings that will be available for individual sites.</span></span> <span data-ttu-id="a2dfe-139">Параметры сайта не могут разрешать больше, чем параметры на уровне организации.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-139">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="a2dfe-140">Если вы хотите разрешить неавентированное совместное использование файлов и папок, выберите **Anyone**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-140">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="a2dfe-141">Если вы хотите убедиться, что все люди за пределами организации должны проверить подлинность, выберите **новые и существующие гости.**</span><span class="sxs-lookup"><span data-stu-id="a2dfe-141">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="a2dfe-142">Выберите наиболее разрешительный параметр, который будет необходим любому сайту в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-142">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Снимок экрана: настройка параметров общего доступа для SharePoint на уровне организации](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="a2dfe-144">Чтобы настроить общий доступ для SharePoint на уровне организации, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-144">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="a2dfe-145">В Центре администрирования Microsoft 365 в области навигации слева в разделе **Центры администрирования** выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-145">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="a2dfe-146">В центре администрирования SharePoint в левой области навигации в разделе **Политики** нажмите **кнопку Общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-146">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="a2dfe-147">Убедитесь, что для параметра внешнего общего доступа SharePoint задано значение **Все** или **Новые и существующие гости**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-147">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="a2dfe-148">Если вы внесли изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-148">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="a2dfe-149">Создание сайта</span><span class="sxs-lookup"><span data-stu-id="a2dfe-149">Create a site</span></span>

<span data-ttu-id="a2dfe-150">Следующий шаг — создание сайта, который планируется использовать для совместной работы с гостями.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-150">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="a2dfe-151">Создание сайта</span><span class="sxs-lookup"><span data-stu-id="a2dfe-151">To create a site</span></span>
1. <span data-ttu-id="a2dfe-152">В Центре администрирования SharePoint в разделе **Сайты** щелкните **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-152">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="a2dfe-153">Щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-153">Click **Create**.</span></span>
3. <span data-ttu-id="a2dfe-154">Щелкните **сайт Team**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-154">Click **Team site**.</span></span>
4. <span data-ttu-id="a2dfe-155">Введите имя сайта и введите имя владельца группы (владельца сайта).</span><span class="sxs-lookup"><span data-stu-id="a2dfe-155">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="a2dfe-156">В **расширенных параметрах** выберите, если вы хотите, чтобы этот сайт был общедоступным или закрытым.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-156">Under **Advanced settings**, choose if you want this site to be a public or private one.</span></span>
6. <span data-ttu-id="a2dfe-157">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-157">Click **Next**.</span></span>
7. <span data-ttu-id="a2dfe-158">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-158">Click **Finish**.</span></span>

<span data-ttu-id="a2dfe-159">Инструкции по приглашению пользователей приводятся далее.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-159">We'll invite users later.</span></span> <span data-ttu-id="a2dfe-160">Далее важно проверить параметры общего доступа на уровне сайта для этого сайта.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-160">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="a2dfe-161">Настройка параметров общего доступа на уровне сайта SharePoint</span><span class="sxs-lookup"><span data-stu-id="a2dfe-161">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="a2dfe-162">Проверьте параметры общего доступа на уровне сайта, чтобы убедиться, что они позволяют получать доступ к этому сайту.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-162">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="a2dfe-163">Например, если вы задайте параметры на уровне организации любому, но вы хотите, чтобы все гости могли проверить подлинность этого сайта, убедитесь, что параметры общего доступа на уровне сайта задайте новым и существующим **гостям.**</span><span class="sxs-lookup"><span data-stu-id="a2dfe-163">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="a2dfe-164">Обратите внимание, что сайт не может быть общим для неавентированных людей **(любой** параметр), но отдельные файлы и папки могут.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-164">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

<span data-ttu-id="a2dfe-165">Вы также можете использовать [метки конфиденциальности](../compliance/sensitivity-labels-teams-groups-sites.md)для управления внешними настройками общего доступа для SharePoint сайтов.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-165">You can also use [sensitivity labels to control external sharing settings for SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

![Снимок экрана: настройка параметров внешнего общего доступа для сайта SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="a2dfe-167">Чтобы настроить параметры общего доступа на уровне сайта, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-167">To set site-level sharing settings</span></span>
1. <span data-ttu-id="a2dfe-168">Откройте Центр администрирования SharePoint, затем на панели навигации слева разверните меню **Сайты** и нажмите **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-168">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="a2dfe-169">Выберите сайт, который вы хотите поделиться.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-169">Select the site that you want to share.</span></span>
3. <span data-ttu-id="a2dfe-170">Нажмите кнопку ..., и нажмите **кнопку Общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-170">Click ..., and click **Sharing**.</span></span>
4. <span data-ttu-id="a2dfe-171">Убедитесь, что для параметра общего доступа установлено значение **Все** или **Новые и существующие гости**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-171">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="a2dfe-172">Если вы внесли изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-172">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="a2dfe-173">Приглашение пользователей</span><span class="sxs-lookup"><span data-stu-id="a2dfe-173">Invite users</span></span>

<span data-ttu-id="a2dfe-174">Параметры гостевых обменов теперь настроены, чтобы можно было начать добавлять внутренних пользователей и гостей на свой сайт.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-174">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="a2dfe-175">Доступ к сайту контролируется через связанную группу Microsoft 365, поэтому мы будем добавлять пользователей туда.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-175">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="a2dfe-176">Приглашение внутренних пользователей в группу</span><span class="sxs-lookup"><span data-stu-id="a2dfe-176">To invite internal users to a group</span></span>
1. <span data-ttu-id="a2dfe-177">Перейдите на сайт, на котором нужно добавить пользователей.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-177">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="a2dfe-178">Щелкните **ссылку** Участники в правом верхнем справа, которая обозначает количество участников.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-178">Click **Members** link in the upper right which denotes the member count.</span></span>
3. <span data-ttu-id="a2dfe-179">Нажмите **Добавить участников**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-179">Click **Add members**.</span></span>
4. <span data-ttu-id="a2dfe-180">Введите имена или адреса электронной почты пользователей, которых вы хотите пригласить на сайт, а затем нажмите **кнопку Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-180">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="a2dfe-181">Гости не могут быть добавлены с сайта.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-181">Guests can't be added from the site.</span></span> <span data-ttu-id="a2dfe-182">Их необходимо добавить с помощью Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-182">You need to add them using Outlook on the web.</span></span> <span data-ttu-id="a2dfe-183">Поэтому в качестве обязательного условия для добавления и приглашения гостей в группу щелкните URL-адрес сайта в столбце **URL-адрес,**  чтобы перейти на страницу конкретного сайта.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-183">Therefore, as a prerequisite to add and invite guests to a group, click the URL of the site in the **URL**  column to navigate to the site-specific page.</span></span> <span data-ttu-id="a2dfe-184">На этой странице щелкните **значок запуска приложения** и выберите **Outlook**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-184">From this page, click the **App launcher** icon and select **Outlook**.</span></span> <span data-ttu-id="a2dfe-185">Это экран, с которого можно приглашать гостей в группу, для которой процедура описана ниже.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-185">This is the screen from which you can invite guests into a group, for which procedure is described below.</span></span>

<span data-ttu-id="a2dfe-186">Приглашение гостей в группу</span><span class="sxs-lookup"><span data-stu-id="a2dfe-186">To invite guests to a group</span></span>
1. <span data-ttu-id="a2dfe-187">В **группах** щелкните группу, в которую нужно приглашать гостей.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-187">Under **Groups**, click the group to which you want to invite guests.</span></span>
2. <span data-ttu-id="a2dfe-188">Откройте контактную карточку группы, щелкните **ссылку Участники** в правом верхнем справа (ссылка, которая обозначает количество участников).</span><span class="sxs-lookup"><span data-stu-id="a2dfe-188">Open the group contact card, click **Members** link in the upper right (the link which denotes the member count).</span></span>
3. <span data-ttu-id="a2dfe-189">нажмите **кнопку Добавить членов**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-189">click **Add members**.</span></span>
4. <span data-ttu-id="a2dfe-190">Введите адреса электронной почты гостей, которые вы хотите пригласить, а затем нажмите **кнопку Добавить**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-190">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
5. <span data-ttu-id="a2dfe-191">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-191">Click **Close**.</span></span>
<span data-ttu-id="a2dfe-192">Обратите внимание, что нажмите кнопку **Закрыть** только в том случае, если вы не владелец группы, и в результате не разрешается добавлять гостя в группу.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-192">Note that you need to click **Close** only if you are not the owner of the group and as a result, you are not allowed to add the guest into the group.</span></span> <span data-ttu-id="a2dfe-193">В таких случаях запрос на добавление гостя в группу передается владельцу группы для утверждения.</span><span class="sxs-lookup"><span data-stu-id="a2dfe-193">In such cases, the request to add the guest into the group is transferred to the group owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="a2dfe-194">См. также</span><span class="sxs-lookup"><span data-stu-id="a2dfe-194">See also</span></span>

[<span data-ttu-id="a2dfe-195">Рекомендации по предоставлению общего доступа к файлам и папкам непроверенным пользователям</span><span class="sxs-lookup"><span data-stu-id="a2dfe-195">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="a2dfe-196">Ограничение возможности случайного раскрытия файлов при предоставлении доступа гостям</span><span class="sxs-lookup"><span data-stu-id="a2dfe-196">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="a2dfe-197">Создание безопасной среды гостевого общего доступа</span><span class="sxs-lookup"><span data-stu-id="a2dfe-197">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="a2dfe-198">Создание экстрасети B2B с управляемыми гостями</span><span class="sxs-lookup"><span data-stu-id="a2dfe-198">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="a2dfe-199">Интеграция SharePoint и OneDrive с Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="a2dfe-199">SharePoint and OneDrive integration with Azure AD B2B</span></span>](/sharepoint/sharepoint-azureb2b-integration-preview)