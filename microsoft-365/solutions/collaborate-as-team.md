---
title: Совместная работа с гостями в команде
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
description: Сведения о действиях по настройке Microsoft 365, необходимых для настройки группы для сотрудничества задач, обсуждений и документации с гостями в Teams.
ms.openlocfilehash: 7f00acb7b7b58169d6a66bfa4cabdc5a3035f67f
ms.sourcegitcommit: 8a726ed7ec19a8728c079780fa4d343a5f759fbb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030033"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="2e586-103">Совместная работа с гостями в команде</span><span class="sxs-lookup"><span data-stu-id="2e586-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="2e586-104">Если вам требуется совместно работать с гостями в документах, задачах и беседах, рекомендуется использовать Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2e586-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="2e586-105">Teams предоставляет все функции совместной работы, доступные в Office и SharePoint с сохраняемым чат и настраиваемым и расширяемым набором средств совместной работы в едином пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="2e586-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="2e586-106">В этой статье мы рассмотрим действия по настройке Microsoft 365, необходимые для настройки группы для совместной работы с гостями.</span><span class="sxs-lookup"><span data-stu-id="2e586-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="2e586-107">Видеодемонстрация</span><span class="sxs-lookup"><span data-stu-id="2e586-107">Video demonstration</span></span>

<span data-ttu-id="2e586-108">В этом видеоролике показаны действия по настройке, описанные в этом документе.</span><span class="sxs-lookup"><span data-stu-id="2e586-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="2e586-109">Параметры связей в Организации Azure</span><span class="sxs-lookup"><span data-stu-id="2e586-109">Azure Organizational relationships settings</span></span>

<span data-ttu-id="2e586-110">Общий доступ в Microsoft 365 регулируется на самом высоком уровне [параметрами организационных отношений в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="2e586-110">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="2e586-111">Если общий доступ к гостям отключен или ограничен в Azure AD, этот параметр переопределяет все параметры общего доступа, настроенные в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2e586-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="2e586-112">Проверьте параметры организационных отношений, чтобы предотвратить блокировку общего доступа с гостями.</span><span class="sxs-lookup"><span data-stu-id="2e586-112">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Снимок экрана: страница параметров организационных связей Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="2e586-114">Настройка параметров организационных отношений</span><span class="sxs-lookup"><span data-stu-id="2e586-114">To set organizational relationship settings</span></span>

1. <span data-ttu-id="2e586-115">Выполните вход в Azure Active Directory по адресу [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="2e586-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="2e586-116">В области навигации слева выберите **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="2e586-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="2e586-117">Щелкните **Внешние удостоверения**.</span><span class="sxs-lookup"><span data-stu-id="2e586-117">Click **External identities**.</span></span>
4. <span data-ttu-id="2e586-118">На экране "начало **работы** " в левой области навигации щелкните элемент **внешние параметры совместной работы**.</span><span class="sxs-lookup"><span data-stu-id="2e586-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="2e586-119">Убедитесь, что у **администраторов и пользователей в роли гостя может быть приглашение** , а **Участники** — значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="2e586-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="2e586-120">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2e586-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="2e586-121">Обратите внимание на параметры в разделе **ограничения совместной работы** .</span><span class="sxs-lookup"><span data-stu-id="2e586-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="2e586-122">Убедитесь, что домены гостей, с которыми вы хотите работать совместно, не заблокированы.</span><span class="sxs-lookup"><span data-stu-id="2e586-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="2e586-123">Если вы работаете с гостями в нескольких организациях, вам может потребоваться ограничить их возможности доступа к данным каталога.</span><span class="sxs-lookup"><span data-stu-id="2e586-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="2e586-124">Это не позволит им увидеть, кто еще является гостем в каталоге.</span><span class="sxs-lookup"><span data-stu-id="2e586-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="2e586-125">Для этого в разделе **ограничения доступа пользователей гостей** выберите пункт **гости-пользователи имеют ограниченный доступ к свойствам и членству в параметрах объектов каталогов** или **доступ гостей к свойствам и членству собственных объектов каталога**.</span><span class="sxs-lookup"><span data-stu-id="2e586-125">To do this, under **Guest user access restrictions** , select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="2e586-126">Параметры гостевого доступа Teams</span><span class="sxs-lookup"><span data-stu-id="2e586-126">Teams guest access settings</span></span>

<span data-ttu-id="2e586-127">У Teams есть главный переключатель включения/выключения для гостевого доступа, а также различные параметры, позволяющие контролировать, какие гости могут выполнять в команде.</span><span class="sxs-lookup"><span data-stu-id="2e586-127">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="2e586-128">Главный коммутатор, **разрешающий гостевой доступ в Teams** , должен быть **включен** для работы в Teams.</span><span class="sxs-lookup"><span data-stu-id="2e586-128">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="2e586-129">Убедитесь, что гостевой доступ включен в Teams, и внесите любую корректировку параметров гостя в соответствии с бизнес-потребностями.</span><span class="sxs-lookup"><span data-stu-id="2e586-129">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="2e586-130">Помните, что эти параметры влияют на все команды.</span><span class="sxs-lookup"><span data-stu-id="2e586-130">Keep in mind that these settings affect all teams.</span></span>

![Снимок экрана: переключатель гостевого доступа в Teams](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="2e586-132">Настройка параметров гостевого доступа в Teams</span><span class="sxs-lookup"><span data-stu-id="2e586-132">To set Teams guest access settings</span></span>

1. <span data-ttu-id="2e586-133">Войдите в Центр администрирования Microsoft 365 на сайте [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="2e586-133">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="2e586-134">В области навигации слева щелкните **Показать все**.</span><span class="sxs-lookup"><span data-stu-id="2e586-134">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="2e586-135">В разделе **Центры администрирования** щелкните **Teams**.</span><span class="sxs-lookup"><span data-stu-id="2e586-135">Under **Admin centers** , click **Teams**.</span></span>
4. <span data-ttu-id="2e586-136">В центре администрирования Teams в левой области навигации разверните узел **Параметры всей Организации** и выберите **гостевой доступ**.</span><span class="sxs-lookup"><span data-stu-id="2e586-136">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="2e586-137">Убедитесь, что для параметра **Разрешить гостевой доступ в Teams** задано значение **Вкл.**.</span><span class="sxs-lookup"><span data-stu-id="2e586-137">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="2e586-138">Внесите необходимые изменения в дополнительные параметры гостей и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2e586-138">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="2e586-139">После включения гостевых параметров Teams может потребоваться до двадцати четырех часов.</span><span class="sxs-lookup"><span data-stu-id="2e586-139">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="2e586-140">Параметры гостей для групп Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2e586-140">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="2e586-141">Teams использует группы Microsoft 365 для членства в группах.</span><span class="sxs-lookup"><span data-stu-id="2e586-141">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="2e586-142">Чтобы гостевой доступ в Teams работали в Teams, необходимо включить параметры гостей для группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2e586-142">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Снимок экрана: гостевые параметры для групп Microsoft 365 в Центре администрирования Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="2e586-144">Настройка параметров гостя для групп Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2e586-144">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="2e586-145">В центре администрирования Microsoft 365 в левой области навигации разверните узел **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="2e586-145">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="2e586-146">Щелкните **Параметры организации**.</span><span class="sxs-lookup"><span data-stu-id="2e586-146">Click **Org settings**.</span></span>
3. <span data-ttu-id="2e586-147">В списке выберите пункт **Microsoft 365 группы**.</span><span class="sxs-lookup"><span data-stu-id="2e586-147">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="2e586-148">Убедитесь, что **владельцы групп Let добавляют пользователей за пределом "гости" в Microsoft 365 группы как гости** и получают флажки **доступ к группе "участники гостевой группы** ".</span><span class="sxs-lookup"><span data-stu-id="2e586-148">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="2e586-149">Если вы внесли изменения, нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="2e586-149">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="2e586-150">Параметры общего доступа на уровне Организации SharePoint</span><span class="sxs-lookup"><span data-stu-id="2e586-150">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="2e586-151">Содержимое Teams, например файлы, папки и списки, хранятся в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2e586-151">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="2e586-152">Чтобы гости могли иметь доступ к этим элементам в Teams, параметры общего доступа на уровне Организации SharePoint должны разрешить совместное использование с гостями.</span><span class="sxs-lookup"><span data-stu-id="2e586-152">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="2e586-153">Параметры на уровне Организации определяют, какие параметры доступны для отдельных сайтов, включая сайты, связанные с Teams.</span><span class="sxs-lookup"><span data-stu-id="2e586-153">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="2e586-154">Параметры сайта не могут быть более разрешительнои, чем параметры на уровне Организации.</span><span class="sxs-lookup"><span data-stu-id="2e586-154">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="2e586-155">Если вы хотите разрешить общий доступ к файлам и папкам для людей, не прошедших проверку подлинности, выберите пункт **все**.</span><span class="sxs-lookup"><span data-stu-id="2e586-155">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="2e586-156">Если необходимо обеспечить проверку подлинности для всех гостей, выберите **новые и существующие гости**.</span><span class="sxs-lookup"><span data-stu-id="2e586-156">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="2e586-157">Выберите наиболее разрешительное значение, которое потребуется всем сайтам в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="2e586-157">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Снимок экрана: параметры общего доступа в SharePoint на уровне организации](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="2e586-159">Настройка параметров общего доступа на уровне Организации для SharePoint</span><span class="sxs-lookup"><span data-stu-id="2e586-159">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="2e586-160">В центре администрирования Microsoft 365 в левой области навигации в разделе **центры администрирования** щелкните **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="2e586-160">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers** , click **SharePoint**.</span></span>
2. <span data-ttu-id="2e586-161">В центре администрирования SharePoint в левой области навигации разверните узел **политики** и выберите **общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="2e586-161">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="2e586-162">Убедитесь, что для внешнего общего доступа для SharePoint задано значение " **любой пользователь** " или " **новые и существующие гости** ".</span><span class="sxs-lookup"><span data-stu-id="2e586-162">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="2e586-163">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2e586-163">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="2e586-164">Параметры ссылок по умолчанию на уровне Организации SharePoint</span><span class="sxs-lookup"><span data-stu-id="2e586-164">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="2e586-165">Параметры ссылок, которые будут отображаться для пользователей по умолчанию при предоставлении общего доступа к файлам или папкам, определяются параметрами по умолчанию для файлов и ссылок на папки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2e586-165">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="2e586-166">При необходимости пользователи могут изменить тип ссылки на один из других вариантов перед предоставлением общего доступа.</span><span class="sxs-lookup"><span data-stu-id="2e586-166">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="2e586-167">Помните, что этот параметр влияет на все команды и сайты SharePoint в Организации.</span><span class="sxs-lookup"><span data-stu-id="2e586-167">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="2e586-168">Выберите один из следующих типов ссылки — типы, которые будут выбраны по умолчанию при общем доступе к файлам и папкам:</span><span class="sxs-lookup"><span data-stu-id="2e586-168">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="2e586-169">Если вы ожидаете совместное использование файлов и папок, не прошедших проверку подлинности **, выберите** этот параметр.</span><span class="sxs-lookup"><span data-stu-id="2e586-169">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="2e586-170">Если вы хотите разрешить ссылки для *всех пользователей* , но беспокоитесь о случайном совместном доступе без проверки подлинности, рассмотрите один из других параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2e586-170">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="2e586-171">Этот тип ссылки доступен только в том случае, если вы включили **общий доступ** .</span><span class="sxs-lookup"><span data-stu-id="2e586-171">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="2e586-172">**Только люди из вашей организации** — выберите этот вариант, если вы хотите, чтобы большая часть общего доступа к файлам и папкам была доступна пользователям в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="2e586-172">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="2e586-173">**Specific people** Если вы собираетесь делать большой объем общего доступа к файлам и папкам для гостей, используйте этот вариант.</span><span class="sxs-lookup"><span data-stu-id="2e586-173">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="2e586-174">Этот тип ссылки работает с гостями и требует проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="2e586-174">This type of link works with guests and requires them to authenticate.</span></span>
 
![Снимок экрана: параметры общего доступа к файлам и папкам в SharePoint на уровне организации](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="2e586-176">Настройка параметров по умолчанию для ссылок на уровне Организации в SharePoint</span><span class="sxs-lookup"><span data-stu-id="2e586-176">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="2e586-177">Перейдите на страницу "общий доступ" в центре администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2e586-177">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="2e586-178">В разделе **ссылки на файлы и папки** выберите ссылку для совместного доступа по умолчанию, которую нужно использовать.</span><span class="sxs-lookup"><span data-stu-id="2e586-178">Under **File and folder links** , select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="2e586-179">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2e586-179">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="2e586-180">Создание команды</span><span class="sxs-lookup"><span data-stu-id="2e586-180">Create a team</span></span>

<span data-ttu-id="2e586-181">Следующий шаг — создание команды, которую планируется использовать для совместной работы с гостями.</span><span class="sxs-lookup"><span data-stu-id="2e586-181">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="2e586-182">Создание команды</span><span class="sxs-lookup"><span data-stu-id="2e586-182">To create a team</span></span>
1. <span data-ttu-id="2e586-183">В Teams на вкладке **группы** выберите команду **присоединиться или создайте** команду в нижней части левой области.</span><span class="sxs-lookup"><span data-stu-id="2e586-183">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="2e586-184">Нажмите **создать группу**.</span><span class="sxs-lookup"><span data-stu-id="2e586-184">Click **Create a team**.</span></span>
3. <span data-ttu-id="2e586-185">Нажмите **"создать группу"**.</span><span class="sxs-lookup"><span data-stu-id="2e586-185">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="2e586-186">Выберите **частный** или **общедоступный**.</span><span class="sxs-lookup"><span data-stu-id="2e586-186">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="2e586-187">Введите имя и описание команды, а затем нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="2e586-187">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="2e586-188">Нажмите кнопку **пропустить**.</span><span class="sxs-lookup"><span data-stu-id="2e586-188">Click **Skip**.</span></span>

<span data-ttu-id="2e586-189">Мы будем приглашать пользователей позже.</span><span class="sxs-lookup"><span data-stu-id="2e586-189">We'll invite users later.</span></span> <span data-ttu-id="2e586-190">Затем важно проверить параметры общего доступа на уровне сайта для сайта SharePoint, связанного с командой.</span><span class="sxs-lookup"><span data-stu-id="2e586-190">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="2e586-191">Параметры общего доступа на уровне сайта SharePoint</span><span class="sxs-lookup"><span data-stu-id="2e586-191">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="2e586-192">Проверьте параметры общего доступа на уровне сайта, чтобы убедиться, что они допускают тип доступа, который вы хотите использовать для этой команды.</span><span class="sxs-lookup"><span data-stu-id="2e586-192">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="2e586-193">Например, если вы настроили параметры на уровне Организации для всех **пользователей** , но хотите, чтобы все гости подлинны для этой команды, убедитесь, что для параметров общего доступа на уровне сайта задано значение " **новые и существующие гости** ".</span><span class="sxs-lookup"><span data-stu-id="2e586-193">For example, if you set the organization-level settings to **Anyone** , but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![Снимок экрана: параметры внешнего общего доступа к сайту SharePoint](../media/sharepoint-site-external-sharing-settings.png)


<span data-ttu-id="2e586-195">Установка параметров общего доступа на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="2e586-195">To set site-level sharing settings</span></span>
1. <span data-ttu-id="2e586-196">В центре администрирования SharePoint в левой области навигации разверните узел **сайты** и выберите пункт **активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="2e586-196">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="2e586-197">Выберите сайт для команды, которую вы только что создали.</span><span class="sxs-lookup"><span data-stu-id="2e586-197">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="2e586-198">Нажмите кнопку... и выберите **общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="2e586-198">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="2e586-199">Убедитесь, что для общего доступа задано значение " **любой пользователь** " или " **новые и существующие гости** ".</span><span class="sxs-lookup"><span data-stu-id="2e586-199">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="2e586-200">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2e586-200">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="2e586-201">Приглашение пользователей</span><span class="sxs-lookup"><span data-stu-id="2e586-201">Invite users</span></span>

<span data-ttu-id="2e586-202">Параметры общего доступа к гостевой сети настроены, поэтому вы можете добавить в команду внутренних пользователей и гостей.</span><span class="sxs-lookup"><span data-stu-id="2e586-202">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="2e586-203">Приглашение внутренних пользователей в команду</span><span class="sxs-lookup"><span data-stu-id="2e586-203">To invite internal users to a team</span></span>
1. <span data-ttu-id="2e586-204">В группе выберите **Дополнительные параметры** ( **\*\*\*** ), а затем нажмите кнопку **Добавить участника**.</span><span class="sxs-lookup"><span data-stu-id="2e586-204">In the team, click **More options** ( **\*\*\*** ), and then click **Add member**.</span></span>
2. <span data-ttu-id="2e586-205">Введите имя человека, которого хотите пригласить.</span><span class="sxs-lookup"><span data-stu-id="2e586-205">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="2e586-206">Нажмите **Добавить** , а затем **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="2e586-206">Click **Add** , and then click **Close**.</span></span>

<span data-ttu-id="2e586-207">Приглашение гостей в команду</span><span class="sxs-lookup"><span data-stu-id="2e586-207">To invite guests to a team</span></span>
1. <span data-ttu-id="2e586-208">В группе выберите **Дополнительные параметры** ( **\*\*\*** ), а затем нажмите кнопку **Добавить участника**.</span><span class="sxs-lookup"><span data-stu-id="2e586-208">In the team, click **More options** ( **\*\*\*** ), and then click **Add member**.</span></span>
2. <span data-ttu-id="2e586-209">Введите адрес электронной почты гостя, которого вы хотите пригласить.</span><span class="sxs-lookup"><span data-stu-id="2e586-209">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="2e586-210">Щелкните ссылку **изменить сведения о гостевой** системе.</span><span class="sxs-lookup"><span data-stu-id="2e586-210">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="2e586-211">Введите полное имя гостя и щелкните галочку.</span><span class="sxs-lookup"><span data-stu-id="2e586-211">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="2e586-212">Нажмите **Добавить** , а затем **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="2e586-212">Click **Add** , and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e586-213">См. также</span><span class="sxs-lookup"><span data-stu-id="2e586-213">See also</span></span>

[<span data-ttu-id="2e586-214">Рекомендации по предоставлению общего доступа к файлам и папкам непроверенным пользователям</span><span class="sxs-lookup"><span data-stu-id="2e586-214">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="2e586-215">Ограничение возможности случайного раскрытия файлов при предоставлении доступа гостям</span><span class="sxs-lookup"><span data-stu-id="2e586-215">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="2e586-216">Создание безопасной среды гостевого общего доступа</span><span class="sxs-lookup"><span data-stu-id="2e586-216">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="2e586-217">Создание экстрасети B2B с управляемыми гостями</span><span class="sxs-lookup"><span data-stu-id="2e586-217">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="2e586-218">Интеграция SharePoint и OneDrive с помощью Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="2e586-218">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
