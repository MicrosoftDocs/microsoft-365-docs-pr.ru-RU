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
description: Узнайте о действиях по настройке Microsoft 365, необходимых для настройки команды для совместной работы с гостями в Teams для работы с задачами, беседами и документацией.
ms.openlocfilehash: cc962e22bde70220e07f805b0a7a83c111886369
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659610"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="4ca49-103">Совместная работа с гостями в команде</span><span class="sxs-lookup"><span data-stu-id="4ca49-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="4ca49-104">Если вам нужно совместно работать с гостями в документах, задачах и беседах, рекомендуем использовать Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4ca49-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="4ca49-105">Teams предоставляет все функции совместной работы, доступные в Office и SharePoint, сохраняемый чат и настраиваемый и постоянный набор средств совместной работы в едином интерфейсе пользователя.</span><span class="sxs-lookup"><span data-stu-id="4ca49-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="4ca49-106">В этой статье мы разберем действия по настройке Microsoft 365, необходимые для настройки команды для совместной работы с гостями.</span><span class="sxs-lookup"><span data-stu-id="4ca49-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="4ca49-107">Видеодемонстрация</span><span class="sxs-lookup"><span data-stu-id="4ca49-107">Video demonstration</span></span>

<span data-ttu-id="4ca49-108">В этом видео показаны действия по настройке, описанные в этом документе.</span><span class="sxs-lookup"><span data-stu-id="4ca49-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="4ca49-109">Параметры внешней совместной работы Azure</span><span class="sxs-lookup"><span data-stu-id="4ca49-109">Azure External collaboration settings</span></span>

<span data-ttu-id="4ca49-110">Общий доступ в Microsoft 365 управляется на самом высоком уровне с помощью параметров внешней совместной работы [B2B в Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)</span><span class="sxs-lookup"><span data-stu-id="4ca49-110">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="4ca49-111">Если в Azure AD отключен или запрещен гостевой общий доступ, этот параметр переопределит все параметры общего доступа, настроенные в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4ca49-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="4ca49-112">Проверьте параметры внешних параметров совместной работы B2B, чтобы убедиться, что общий доступ гостям не заблокирован.</span><span class="sxs-lookup"><span data-stu-id="4ca49-112">Check the B2B external collaboration settings settings to ensure that sharing with guests is not blocked.</span></span>

![Снимок экрана: страница параметров организационных связей Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="4ca49-114">Настройка параметров внешней совместной работы</span><span class="sxs-lookup"><span data-stu-id="4ca49-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="4ca49-115">Войдите в Azure Active Directory [https://aad.portal.azure.com](https://aad.portal.azure.com) по</span><span class="sxs-lookup"><span data-stu-id="4ca49-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="4ca49-116">В левой области навигации щелкните **Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="4ca49-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="4ca49-117">Щелкните **внешние удостоверения.**</span><span class="sxs-lookup"><span data-stu-id="4ca49-117">Click **External identities**.</span></span>
4. <span data-ttu-id="4ca49-118">На экране **"Начало работы"** в левой области навигации щелкните **параметры внешней совместной работы.**</span><span class="sxs-lookup"><span data-stu-id="4ca49-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="4ca49-119">**Убедитесь, что администраторы** и пользователи с  ролью приглашенного гостя могут приглашать гостей, а для участников установлено значение **"Да".**</span><span class="sxs-lookup"><span data-stu-id="4ca49-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="4ca49-120">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4ca49-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="4ca49-121">Обратите внимание на параметры в разделе **"Ограничения для совместной работы".**</span><span class="sxs-lookup"><span data-stu-id="4ca49-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="4ca49-122">Убедитесь, что домены гостей, с которых вы хотите сотрудничать, не блокируются.</span><span class="sxs-lookup"><span data-stu-id="4ca49-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="4ca49-123">Если вы работаете с гостями из нескольких организаций, вы можете ограничить их возможность доступа к данным каталога.</span><span class="sxs-lookup"><span data-stu-id="4ca49-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="4ca49-124">Это не позволит им увидеть, кто еще является гостем в каталоге.</span><span class="sxs-lookup"><span data-stu-id="4ca49-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="4ca49-125">Для этого в рамках ограничений доступа  гостевых пользователей выберите "Гостевых пользователей" ограниченный доступ к свойствам и членство в параметрах объектов каталога, а гостевой доступ пользователей ограничен свойствами и членством в собственных объектах каталогов. </span><span class="sxs-lookup"><span data-stu-id="4ca49-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="4ca49-126">Параметры гостевого доступа Teams</span><span class="sxs-lookup"><span data-stu-id="4ca49-126">Teams guest access settings</span></span>

<span data-ttu-id="4ca49-127">В Teams есть мастер включаемого и отключенного коммутатора для гостевого доступа и множество параметров, доступных для управления тем, что могут делать гости в команде.</span><span class="sxs-lookup"><span data-stu-id="4ca49-127">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="4ca49-128">Для работы в **Teams** должен быть  включен гостевой коммутатор "Разрешить гостевой доступ в Teams".</span><span class="sxs-lookup"><span data-stu-id="4ca49-128">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="4ca49-129">Убедитесь, что гостевой доступ включен в Teams, и внести любые изменения в параметры гостя в зависимости от потребностей вашей компании.</span><span class="sxs-lookup"><span data-stu-id="4ca49-129">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="4ca49-130">Помните, что эти параметры влияют на все команды.</span><span class="sxs-lookup"><span data-stu-id="4ca49-130">Keep in mind that these settings affect all teams.</span></span>

![Снимок экрана: переключатель гостевого доступа в Teams](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="4ca49-132">Настройка параметров гостевого доступа в Teams</span><span class="sxs-lookup"><span data-stu-id="4ca49-132">To set Teams guest access settings</span></span>

1. <span data-ttu-id="4ca49-133">Войдите в Центр администрирования Microsoft 365 на сайте [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="4ca49-133">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="4ca49-134">В левой области навигации щелкните **"Показать все".**</span><span class="sxs-lookup"><span data-stu-id="4ca49-134">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="4ca49-135">В разделе **Центры администрирования** щелкните **Teams**.</span><span class="sxs-lookup"><span data-stu-id="4ca49-135">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="4ca49-136">В Центре администрирования Teams в области навигации слева разйдите параметры для всей организации и щелкните "Гостевой **доступ".** </span><span class="sxs-lookup"><span data-stu-id="4ca49-136">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="4ca49-137">Убедитесь, что для параметра **Разрешить гостевой доступ в Teams** задано значение **Вкл.**.</span><span class="sxs-lookup"><span data-stu-id="4ca49-137">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="4ca49-138">Внесите необходимые изменения в дополнительные параметры гостей и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4ca49-138">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

<span data-ttu-id="4ca49-139">Если гостевой доступ Teams включен, вы можете дополнительно управлять гостевим доступом к отдельным командам и связанным с ними сайтам SharePoint с помощью меток конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="4ca49-139">Once Teams guest access is turned on, you can optionally control guest access to individual teams and their associated SharePoint sites using sensitivity labels.</span></span> <span data-ttu-id="4ca49-140">Дополнительные сведения см. в подписях конфиденциальности для защиты контента в Microsoft Teams, группах [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)и на сайтах SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4ca49-140">For more information, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

> [!NOTE]
> <span data-ttu-id="4ca49-141">После того как вы включите его, может потребоваться до 24 часов, чтобы параметры гостей Teams стали активными.</span><span class="sxs-lookup"><span data-stu-id="4ca49-141">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="4ca49-142">Гостевая настройка групп Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4ca49-142">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="4ca49-143">Teams использует группы Microsoft 365 для участия в группах.</span><span class="sxs-lookup"><span data-stu-id="4ca49-143">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="4ca49-144">Параметры гостей групп Microsoft 365 должны быть включены, чтобы гостевой доступ в Teams работал.</span><span class="sxs-lookup"><span data-stu-id="4ca49-144">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Снимок экрана: гостевые параметры для групп Microsoft 365 в Центре администрирования Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="4ca49-146">Настройка гостевых параметров групп Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4ca49-146">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="4ca49-147">В Центре администрирования Microsoft 365 в области навигации слева раз expand **Settings (Параметры).**</span><span class="sxs-lookup"><span data-stu-id="4ca49-147">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="4ca49-148">Щелкните **параметры организации.**</span><span class="sxs-lookup"><span data-stu-id="4ca49-148">Click **Org settings**.</span></span>
3. <span data-ttu-id="4ca49-149">В списке выберите **"Группы Microsoft 365".**</span><span class="sxs-lookup"><span data-stu-id="4ca49-149">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="4ca49-150">Убедитесь, что владельцы группы могут добавлять пользователей за пределами  вашей организации в группы **Microsoft 365** в качестве гостей, и чтобы участники группы гостей получили доступ к флажкам содержимого группы гостей.</span><span class="sxs-lookup"><span data-stu-id="4ca49-150">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="4ca49-151">Если вы влияли на изменения, нажмите **кнопку "Сохранить изменения".**</span><span class="sxs-lookup"><span data-stu-id="4ca49-151">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="4ca49-152">Параметры общего доступа на уровне организации SharePoint</span><span class="sxs-lookup"><span data-stu-id="4ca49-152">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="4ca49-153">Весь контент Teams, например файлы, папки и списки, хранится в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4ca49-153">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="4ca49-154">Чтобы у гостей был доступ к этим элементами в Teams, параметры общего доступа на уровне организации SharePoint должны разрешать общий доступ гостям.</span><span class="sxs-lookup"><span data-stu-id="4ca49-154">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="4ca49-155">Параметры на уровне организации определяют, какие параметры доступны для отдельных сайтов, включая сайты, связанные с группами.</span><span class="sxs-lookup"><span data-stu-id="4ca49-155">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="4ca49-156">Параметры сайта не могут быть более нео разрешательными, чем параметры на уровне организации.</span><span class="sxs-lookup"><span data-stu-id="4ca49-156">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="4ca49-157">Если вы хотите разрешить общий доступ к файлам и папам для непросвещенных людей, выберите **"Все".**</span><span class="sxs-lookup"><span data-stu-id="4ca49-157">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="4ca49-158">Если вы хотите убедиться, что все гости должны проверить подлинность, выберите **"Новые" и "Существующие гости".**</span><span class="sxs-lookup"><span data-stu-id="4ca49-158">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="4ca49-159">Выберите наиболее разрешительный параметр, который потребуется любому сайту в организации.</span><span class="sxs-lookup"><span data-stu-id="4ca49-159">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Снимок экрана: параметры общего доступа в SharePoint на уровне организации](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="4ca49-161">Настройка параметров общего доступа на уровне организации SharePoint</span><span class="sxs-lookup"><span data-stu-id="4ca49-161">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="4ca49-162">В Центре администрирования Microsoft 365 в левой области навигации в центре администрирования **щелкните** **SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="4ca49-162">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="4ca49-163">В Центре администрирования SharePoint в области навигации слева разйдите раздел **"Политики"** и щелкните **"Общий доступ".**</span><span class="sxs-lookup"><span data-stu-id="4ca49-163">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="4ca49-164">Убедитесь, что для внешнего общего доступа для SharePoint установлено **"Любой"** или **"Новый" и "Существующие гости".**</span><span class="sxs-lookup"><span data-stu-id="4ca49-164">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="4ca49-165">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4ca49-165">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="4ca49-166">Параметры ссылок по умолчанию на уровне организации SharePoint</span><span class="sxs-lookup"><span data-stu-id="4ca49-166">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="4ca49-167">Параметры ссылок на файлы и папки по умолчанию определяют параметр ссылки, который будет по умолчанию показываться пользователям при совместном доступе к файлу или папке.</span><span class="sxs-lookup"><span data-stu-id="4ca49-167">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="4ca49-168">При желании пользователи могут изменить тип ссылки на один из других вариантов перед совместным доступом.</span><span class="sxs-lookup"><span data-stu-id="4ca49-168">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="4ca49-169">Помните, что этот параметр влияет на все команды и сайты SharePoint в организации.</span><span class="sxs-lookup"><span data-stu-id="4ca49-169">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="4ca49-170">Выберите любой из следующих типов ссылок, которые будут выбраны по умолчанию при совместном доступе пользователей к файлам и папок:</span><span class="sxs-lookup"><span data-stu-id="4ca49-170">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="4ca49-171">**Любой, у кого есть** ссылка— выберите этот параметр, если вы хотите сделать много общего доступа к файлам и папок, не проавентированных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4ca49-171">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="4ca49-172">Если вы хотите  разрешить ссылки "Любой", но вас беспокоит случайное неавтоматическое совместное использование, рассмотрите один из других вариантов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4ca49-172">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="4ca49-173">Этот тип ссылки доступен, только если вы включили общий **доступ для всех.**</span><span class="sxs-lookup"><span data-stu-id="4ca49-173">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="4ca49-174">**Только для людей в вашей** организации. Выберите этот вариант, если вы ожидаете, что большая часть общего доступа к файлам и папок будет делаться с людьми из вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4ca49-174">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="4ca49-175">**Конкретные люди—** рассмотрите этот вариант, если вы хотите сделать много файлов и папок, чтобы поделиться с гостями.</span><span class="sxs-lookup"><span data-stu-id="4ca49-175">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="4ca49-176">Этот тип ссылки работает с гостями и требует от них проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="4ca49-176">This type of link works with guests and requires them to authenticate.</span></span>
 
![Снимок экрана: параметры общего доступа к файлам и папкам в SharePoint на уровне организации](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="4ca49-178">Установка параметров ссылок по умолчанию на уровне организации SharePoint</span><span class="sxs-lookup"><span data-stu-id="4ca49-178">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="4ca49-179">Перейдите на страницу "Общий доступ" в Центре администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4ca49-179">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="4ca49-180">В **разделе "Ссылки на файлы и папки"** выберите ссылку для общего доступа по умолчанию, которую вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="4ca49-180">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="4ca49-181">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4ca49-181">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="4ca49-182">Создание команды</span><span class="sxs-lookup"><span data-stu-id="4ca49-182">Create a team</span></span>

<span data-ttu-id="4ca49-183">Следующим шагом является создание команды, которую вы планируете использовать для совместной работы с гостями.</span><span class="sxs-lookup"><span data-stu-id="4ca49-183">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="4ca49-184">Создание команды</span><span class="sxs-lookup"><span data-stu-id="4ca49-184">To create a team</span></span>
1. <span data-ttu-id="4ca49-185">В Teams на вкладке **"Teams"** щелкните "Присоединиться" или **создайте** команду в нижней части левой области.</span><span class="sxs-lookup"><span data-stu-id="4ca49-185">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="4ca49-186">Нажмите **кнопку "Создать команду".**</span><span class="sxs-lookup"><span data-stu-id="4ca49-186">Click **Create a team**.</span></span>
3. <span data-ttu-id="4ca49-187">Щелкните **"Создать команду с нуля".**</span><span class="sxs-lookup"><span data-stu-id="4ca49-187">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="4ca49-188">Выберите **"Частный"** или **"Общедоступный"**.</span><span class="sxs-lookup"><span data-stu-id="4ca49-188">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="4ca49-189">Введите имя и описание команды и нажмите кнопку **"Создать".**</span><span class="sxs-lookup"><span data-stu-id="4ca49-189">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="4ca49-190">Нажмите **кнопку "Пропустить".**</span><span class="sxs-lookup"><span data-stu-id="4ca49-190">Click **Skip**.</span></span>

<span data-ttu-id="4ca49-191">Мы приглашаем пользователей позже.</span><span class="sxs-lookup"><span data-stu-id="4ca49-191">We'll invite users later.</span></span> <span data-ttu-id="4ca49-192">Затем важно проверить параметры общего доступа на уровне сайта для сайта SharePoint, связанного с командой.</span><span class="sxs-lookup"><span data-stu-id="4ca49-192">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="4ca49-193">Параметры общего доступа на уровне сайта SharePoint</span><span class="sxs-lookup"><span data-stu-id="4ca49-193">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="4ca49-194">Проверьте параметры общего доступа на уровне сайта, чтобы убедиться, что они позволяют использовать нужный тип доступа для этой команды.</span><span class="sxs-lookup"><span data-stu-id="4ca49-194">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="4ca49-195">Например, если для параметров на уровне организации установлено "Все", но вы хотите, чтобы все гости могли проверить подлинность этой команды, убедитесь, что для параметров общего доступа на уровне сайта установлено "Создать" и "Существующие гости". </span><span class="sxs-lookup"><span data-stu-id="4ca49-195">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![Снимок экрана: параметры внешнего общего доступа к сайту SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="4ca49-197">Настройка параметров общего доступа на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="4ca49-197">To set site-level sharing settings</span></span>
1. <span data-ttu-id="4ca49-198">В Центре администрирования SharePoint в области навигации слева разйдите раздел **"Сайты"** и щелкните **"Активные сайты".**</span><span class="sxs-lookup"><span data-stu-id="4ca49-198">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="4ca49-199">Выберите сайт для команды, которую вы только что создали.</span><span class="sxs-lookup"><span data-stu-id="4ca49-199">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="4ca49-200">Щелкните ... и выберите **"Общий доступ".**</span><span class="sxs-lookup"><span data-stu-id="4ca49-200">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="4ca49-201">Убедитесь, что для общего доступа установлено **"Все",** **"Создать" и "Существующие гости".**</span><span class="sxs-lookup"><span data-stu-id="4ca49-201">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="4ca49-202">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4ca49-202">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="4ca49-203">Приглашение пользователей</span><span class="sxs-lookup"><span data-stu-id="4ca49-203">Invite users</span></span>

<span data-ttu-id="4ca49-204">Теперь параметры гостевого общего доступа настроены, поэтому вы можете приступить к добавлению внутренних пользователей и гостей в команду.</span><span class="sxs-lookup"><span data-stu-id="4ca49-204">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="4ca49-205">Приглашение внутренних пользователей в команду</span><span class="sxs-lookup"><span data-stu-id="4ca49-205">To invite internal users to a team</span></span>
1. <span data-ttu-id="4ca49-206">В команде нажмите кнопку **"Дополнительные параметры"** **\*\*\*** (), а затем нажмите кнопку **"Добавить участника".**</span><span class="sxs-lookup"><span data-stu-id="4ca49-206">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="4ca49-207">Введите имя человека, которого вы хотите пригласить.</span><span class="sxs-lookup"><span data-stu-id="4ca49-207">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="4ca49-208">Нажмите **Добавить**, а затем **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="4ca49-208">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="4ca49-209">Приглашение гостей в команду</span><span class="sxs-lookup"><span data-stu-id="4ca49-209">To invite guests to a team</span></span>
1. <span data-ttu-id="4ca49-210">В команде нажмите кнопку **"Дополнительные параметры"** **\*\*\*** (), а затем нажмите кнопку **"Добавить участника".**</span><span class="sxs-lookup"><span data-stu-id="4ca49-210">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="4ca49-211">Введите адрес электронной почты гостя, которого вы хотите пригласить.</span><span class="sxs-lookup"><span data-stu-id="4ca49-211">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="4ca49-212">Нажмите **кнопку "Изменить гостевую информацию".**</span><span class="sxs-lookup"><span data-stu-id="4ca49-212">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="4ca49-213">Введите полное имя гостя и щелкните метку.</span><span class="sxs-lookup"><span data-stu-id="4ca49-213">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="4ca49-214">Нажмите **Добавить**, а затем **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="4ca49-214">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="4ca49-215">См. также</span><span class="sxs-lookup"><span data-stu-id="4ca49-215">See also</span></span>

[<span data-ttu-id="4ca49-216">Рекомендации по предоставлению общего доступа к файлам и папкам непроверенным пользователям</span><span class="sxs-lookup"><span data-stu-id="4ca49-216">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="4ca49-217">Ограничение возможности случайного раскрытия файлов при предоставлении доступа гостям</span><span class="sxs-lookup"><span data-stu-id="4ca49-217">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="4ca49-218">Создание безопасной среды гостевого общего доступа</span><span class="sxs-lookup"><span data-stu-id="4ca49-218">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="4ca49-219">Создание экстрасети B2B с управляемыми гостями</span><span class="sxs-lookup"><span data-stu-id="4ca49-219">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="4ca49-220">Интеграция SharePoint и OneDrive с Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="4ca49-220">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
