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
localization_priority: Priority
f1.keywords: NOCSH
recommendations: false
description: Сведения о действиях по настройке Microsoft 365, необходимых для настройки команды для совместной работы с гостями в задачах, беседах и документах в Teams.
ms.openlocfilehash: c17732705c1d88ff70e56f5d26d9e268e3ff7c19
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539267"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="58449-103">Совместная работа с гостями в команде</span><span class="sxs-lookup"><span data-stu-id="58449-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="58449-104">Если вам нужно совместно работать с гостями в документах, задачах и беседах, рекомендуем использовать Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="58449-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="58449-105">Teams предоставляет все функции совместной работы, доступные в Office и SharePoint, включая сохраняемый чат и настраиваемый и расширяемый набор средств совместной работы, в едином пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="58449-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="58449-106">В этой статье рассматриваются действия по настройке Microsoft 365, необходимые для настройки команды для совместной работы с гостями.</span><span class="sxs-lookup"><span data-stu-id="58449-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span> <span data-ttu-id="58449-107">После завершения настройки гостевого доступа вы сможете приглашать гостей в команды. Соответствующие инструкции см. в статье [Добавление гостей в команду в Teams](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f).</span><span class="sxs-lookup"><span data-stu-id="58449-107">Once you have configured guest access, you can invite guests to teams by following the steps in [Add guests to a team in Teams](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="58449-108">Видеодемонстрация</span><span class="sxs-lookup"><span data-stu-id="58449-108">Video demonstration</span></span>

<span data-ttu-id="58449-109">В этом видео показаны действия по настройке, описанные в этом документе.</span><span class="sxs-lookup"><span data-stu-id="58449-109">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="58449-110">Настройка параметров внешней совместной работы в Azure</span><span class="sxs-lookup"><span data-stu-id="58449-110">Azure External collaboration settings</span></span>

<span data-ttu-id="58449-111">Общий доступ в Microsoft 365 настраивается на самом высоком уровне с помощью [параметров внешней совместной работы B2B в Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="58449-111">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="58449-112">Если гостевой общий доступ отключен или ограничен в Azure AD, этот параметр переопределит все параметры общего доступа, настроенные в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="58449-112">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="58449-113">Проверьте настройки параметров внешней совместной работы B2B, чтобы убедиться, что гостевой общий доступ не заблокирован.</span><span class="sxs-lookup"><span data-stu-id="58449-113">Check the B2B external collaboration settings settings to ensure that sharing with guests is not blocked.</span></span>

![Снимок экрана: страница параметров организационных связей Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="58449-115">Чтобы настроить параметры внешней совместной работы, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="58449-115">To set external collaboration settings</span></span>

1. <span data-ttu-id="58449-116">Войдите в Azure Active Directory на сайте [https://aad.portal.azure.com](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="58449-116">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="58449-117">В области навигации слева щелкните **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="58449-117">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="58449-118">Нажмите **Внешние удостоверения**.</span><span class="sxs-lookup"><span data-stu-id="58449-118">Click **External identities**.</span></span>
4. <span data-ttu-id="58449-119">На экране **Начало работы** в области навигации слева щелкните **Параметры внешней совместной работы**.</span><span class="sxs-lookup"><span data-stu-id="58449-119">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="58449-120">Убедитесь, что для параметров **Администраторы и пользователи с ролью "Приглашающий гостей" могут приглашать** и **Участники могут приглашать** установлено значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="58449-120">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="58449-121">Если вы внесли изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="58449-121">If you made changes, click **Save**.</span></span>

<span data-ttu-id="58449-122">Обратите внимание на параметры в разделе **Ограничения совместной работы**.</span><span class="sxs-lookup"><span data-stu-id="58449-122">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="58449-123">Убедитесь, что домены гостей, с которыми вы хотите сотрудничать, не заблокированы.</span><span class="sxs-lookup"><span data-stu-id="58449-123">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="58449-124">Если вы работаете с гостями из нескольких организаций, вы можете ограничить их доступ к данным каталога.</span><span class="sxs-lookup"><span data-stu-id="58449-124">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="58449-125">Это не позволит им видеть других гостей в каталоге.</span><span class="sxs-lookup"><span data-stu-id="58449-125">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="58449-126">Для этого в разделе **Ограничения доступа гостевых пользователей** выберите **Гостевые пользователи имеют ограниченный доступ к свойствам и членству в параметрах объектов каталога** или **Доступ гостевых пользователей ограничен свойствами и членством в их собственных объектах каталога**.</span><span class="sxs-lookup"><span data-stu-id="58449-126">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="58449-127">Настройка параметров гостевого доступа в Teams</span><span class="sxs-lookup"><span data-stu-id="58449-127">Teams guest access settings</span></span>

<span data-ttu-id="58449-128">В Teams есть главный переключатель, позволяющий включать или отключать гостевой доступ, и различные параметры, позволяющие настраивать действия гостей в команде.</span><span class="sxs-lookup"><span data-stu-id="58449-128">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="58449-129">Чтобы включить гостевой доступ в Teams, необходимо привести главный переключатель **Разрешить гостевой доступ в Teams** в положение **Вкл**.</span><span class="sxs-lookup"><span data-stu-id="58449-129">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="58449-p107">Включите гостевой доступ в Teams и внесите любые изменения в параметры гостей в зависимости от потребностей вашей организации. Помните, что эти параметры влияют на все команды.</span><span class="sxs-lookup"><span data-stu-id="58449-p107">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs. Keep in mind that these settings affect all teams.</span></span>

![Снимок экрана: переключатель гостевого доступа в Teams](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="58449-133">Настройка параметров гостевого доступа в Teams</span><span class="sxs-lookup"><span data-stu-id="58449-133">To set Teams guest access settings</span></span>

1. <span data-ttu-id="58449-134">Войдите в Центр администрирования Microsoft 365 на сайте [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="58449-134">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="58449-135">В области навигации слева щелкните **Показать все**.</span><span class="sxs-lookup"><span data-stu-id="58449-135">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="58449-136">В разделе **Центры администрирования** щелкните **Teams**.</span><span class="sxs-lookup"><span data-stu-id="58449-136">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="58449-137">В Центре администрирования Teams в области навигации слева разверните раздел **Параметры на уровне организации** и щелкните **Гостевой доступ**.</span><span class="sxs-lookup"><span data-stu-id="58449-137">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="58449-138">Убедитесь, что для параметра **Разрешить гостевой доступ в Teams** задано значение **Вкл.**.</span><span class="sxs-lookup"><span data-stu-id="58449-138">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="58449-139">Внесите необходимые изменения в дополнительные параметры гостей и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="58449-139">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

<span data-ttu-id="58449-140">После включения гостевого доступа в Teams вы можете дополнительно настроить гостевой доступ для отдельных команд и связанных с ними сайтов SharePoint с помощью меток конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="58449-140">Once Teams guest access is turned on, you can optionally control guest access to individual teams and their associated SharePoint sites using sensitivity labels.</span></span> <span data-ttu-id="58449-141">Дополнительные сведения см. в статье [Использование меток конфиденциальности для защиты контента в Microsoft Teams, в группах Microsoft 365 и на сайтах SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md).</span><span class="sxs-lookup"><span data-stu-id="58449-141">For more information, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

> [!NOTE]
> <span data-ttu-id="58449-142">Активация параметров гостей в Teams может занять до двадцати четырех часов с момента включения.</span><span class="sxs-lookup"><span data-stu-id="58449-142">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="58449-143">Настройка параметров гостей для групп Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="58449-143">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="58449-p109">Teams использует группы Microsoft 365 для участия в командах. Чтобы гостевой доступ в Teams работал, необходимо включить параметры гостей для групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="58449-p109">Teams uses Microsoft 365 Groups for team membership. The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Снимок экрана: настройка параметров гостей для групп Microsoft 365 в Центре администрирования Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="58449-147">Чтобы настроить параметры гостей для групп Microsoft 365, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="58449-147">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="58449-148">В Центре администрирования Microsoft 365 в области навигации слева разверните раздел **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="58449-148">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="58449-149">Нажмите **Параметры организации**.</span><span class="sxs-lookup"><span data-stu-id="58449-149">Click **Org settings**.</span></span>
3. <span data-ttu-id="58449-150">Выберите в списке **Группы Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="58449-150">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="58449-151">Убедитесь, что рядом с пунктами **Разрешить владельцам групп добавлять людей за пределами вашей организации в группы Microsoft 365 в качестве гостей** и **Разрешить гостевым участникам группы получать доступ к содержимому группы** установлены флажки.</span><span class="sxs-lookup"><span data-stu-id="58449-151">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="58449-152">Если вы внесли изменения, нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="58449-152">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="58449-153">Настройка параметров общего доступа для SharePoint на уровне организации</span><span class="sxs-lookup"><span data-stu-id="58449-153">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="58449-154">Все содержимое Teams, например файлы, папки и списки, хранится в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="58449-154">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="58449-155">Чтобы у гостей был доступ к этим элементам в Teams, параметры общего доступа SharePoint на уровне организации должны разрешать общий доступ гостям.</span><span class="sxs-lookup"><span data-stu-id="58449-155">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="58449-156">Параметры на уровне организации определяют доступность параметров для отдельных сайтов, включая сайты, связанные с командами.</span><span class="sxs-lookup"><span data-stu-id="58449-156">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="58449-157">Параметры сайта не могут разрешать больше, чем параметры на уровне организации.</span><span class="sxs-lookup"><span data-stu-id="58449-157">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="58449-158">Если вы хотите разрешить общий доступ к файлам и папкам непроверенным пользователям выберите **Все**.</span><span class="sxs-lookup"><span data-stu-id="58449-158">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="58449-159">Если вы хотите, чтобы все гости проходили проверку подлинности, выберите **Новые и существующие гости**.</span><span class="sxs-lookup"><span data-stu-id="58449-159">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="58449-160">Выберите наиболее разрешительный параметр, который будет необходим любому сайту в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="58449-160">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Снимок экрана: настройка параметров общего доступа для SharePoint на уровне организации](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="58449-162">Чтобы настроить общий доступ для SharePoint на уровне организации, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="58449-162">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="58449-163">В Центре администрирования Microsoft 365 в области навигации слева в разделе **Центры администрирования** выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="58449-163">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="58449-164">В Центре администрирования SharePoint в области навигации слева разверните раздел **Политики** и щелкните пункт **Общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="58449-164">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="58449-165">Убедитесь, что для параметра внешнего общего доступа SharePoint задано значение **Все** или **Новые и существующие гости**.</span><span class="sxs-lookup"><span data-stu-id="58449-165">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="58449-166">Если вы внесли изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="58449-166">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="58449-167">Настройка ссылок по умолчанию для SharePoint на уровне организации</span><span class="sxs-lookup"><span data-stu-id="58449-167">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="58449-168">Параметры ссылок на файлы или папки по умолчанию определяют тип ссылок, которые будет отображаться пользователям по умолчанию при совместном использовании файлов или папок.</span><span class="sxs-lookup"><span data-stu-id="58449-168">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="58449-169">При желании пользователи могут изменить тип ссылки на один из доступных вариантов перед совместным использованием.</span><span class="sxs-lookup"><span data-stu-id="58449-169">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="58449-170">Помните, что этот параметр влияет на все команды и сайты SharePoint в организации.</span><span class="sxs-lookup"><span data-stu-id="58449-170">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="58449-171">Выберите один из следующих типов ссылок, которые будут использоваться по умолчанию при общем доступе пользователей к файлам и папкам.</span><span class="sxs-lookup"><span data-stu-id="58449-171">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="58449-172">**Все, у кого есть ссылка**. Выберите этот вариант, если ожидается совместное использование большого количества файлов и папок без проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="58449-172">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="58449-173">Если вы хотите разрешить тип ссылок *Все*, но беспокоитесь о случайном общем доступе без проверки подлинности, рассмотрите один из следующих вариантов в качестве варианта по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="58449-173">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="58449-174">Этот тип ссылки доступен, только если включен общий доступ для **всех**.</span><span class="sxs-lookup"><span data-stu-id="58449-174">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="58449-175">**Только люди в вашей организации**. Выберите этот вариант, если ожидается, что совместное использование большей части файлов и папок будет осуществляться пользователями внутри вашей организации.</span><span class="sxs-lookup"><span data-stu-id="58449-175">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="58449-176">**Конкретные люди**. Рассмотрите этот вариант, если ожидается совместное использование большого количества файлов и папок гостями.</span><span class="sxs-lookup"><span data-stu-id="58449-176">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="58449-177">Этот тип ссылки работает с гостями и требует от них прохождения проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="58449-177">This type of link works with guests and requires them to authenticate.</span></span>
 
![Снимок экрана: настройка параметров общего доступа к файлам и папкам в SharePoint на уровне организации](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="58449-179">Чтобы настроить ссылки по умолчанию для SharePoint на уровне организации, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="58449-179">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="58449-180">Перейдите на страницу общего доступа в Центре администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="58449-180">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="58449-181">В разделе **Ссылки на файлы и папки** выберите ссылку для общего доступа, которая будет использоваться по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="58449-181">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="58449-182">Если вы внесли изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="58449-182">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="58449-183">Создание команды</span><span class="sxs-lookup"><span data-stu-id="58449-183">Create a team</span></span>

<span data-ttu-id="58449-184">Следующий этап — создание команды, которая будет использоваться для совместной работы с гостями.</span><span class="sxs-lookup"><span data-stu-id="58449-184">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="58449-185">Чтобы создать команду, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="58449-185">To create a team</span></span>
1. <span data-ttu-id="58449-186">В Teams на вкладке **Команды** щелкните **Присоединиться или создать команду** в левой области внизу.</span><span class="sxs-lookup"><span data-stu-id="58449-186">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="58449-187">Нажмите **Создать команду**.</span><span class="sxs-lookup"><span data-stu-id="58449-187">Click **Create a team**.</span></span>
3. <span data-ttu-id="58449-188">Щелкните **Создать команду с нуля**.</span><span class="sxs-lookup"><span data-stu-id="58449-188">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="58449-189">Выберите **Частная** или **Общедоступная**.</span><span class="sxs-lookup"><span data-stu-id="58449-189">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="58449-190">Введите имя и описание команды и нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="58449-190">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="58449-191">Щелкните **Пропустить**.</span><span class="sxs-lookup"><span data-stu-id="58449-191">Click **Skip**.</span></span>

<span data-ttu-id="58449-p116">Инструкции по приглашению пользователей приводятся далее. На следующем этапе важно проверить параметры общего доступа на уровне сайта SharePoint, связанного с командой.</span><span class="sxs-lookup"><span data-stu-id="58449-p116">We'll invite users later. Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="58449-194">Настройка параметров общего доступа на уровне сайта SharePoint</span><span class="sxs-lookup"><span data-stu-id="58449-194">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="58449-195">Проверьте параметры общего доступа на уровне сайта, чтобы убедиться, что они разрешают тип доступа, необходимый для этой команды.</span><span class="sxs-lookup"><span data-stu-id="58449-195">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="58449-196">Например, если для параметров на уровне организации установлено значение **Все**, но вы хотите, чтобы все гости в этой команде проходили проверку подлинности, установите для параметров общего доступа на уровне сайта значение **Новые и существующие гости**.</span><span class="sxs-lookup"><span data-stu-id="58449-196">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![Снимок экрана: настройка параметров внешнего общего доступа для сайта SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="58449-198">Чтобы настроить параметры общего доступа на уровне сайта, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="58449-198">To set site-level sharing settings</span></span>
1. <span data-ttu-id="58449-199">В Центре администрирования SharePoint в области навигации слева разверните раздел **Сайты** и нажмите **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="58449-199">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="58449-200">Выберите сайт для команды, которую вы только что создали.</span><span class="sxs-lookup"><span data-stu-id="58449-200">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="58449-201">Щелкните значок многоточия "..." и выберите **Общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="58449-201">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="58449-202">Убедитесь, что для параметра общего доступа установлено значение **Все** или **Новые и существующие гости**.</span><span class="sxs-lookup"><span data-stu-id="58449-202">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="58449-203">Если вы внесли изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="58449-203">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="58449-204">Приглашение пользователей</span><span class="sxs-lookup"><span data-stu-id="58449-204">Invite users</span></span>

<span data-ttu-id="58449-205">После настройки параметров гостевого общего доступа можно приступать к добавлению внутренних пользователей и гостей в свою команду.</span><span class="sxs-lookup"><span data-stu-id="58449-205">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="58449-206">Чтобы пригласить внутренних пользователей в команду, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="58449-206">To invite internal users to a team</span></span>
1. <span data-ttu-id="58449-207">В команде нажмите **Дополнительные параметры** (**\*\*\***) и выберите **Добавить участника**.</span><span class="sxs-lookup"><span data-stu-id="58449-207">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="58449-208">Введите имя пользователя, которого вы хотите пригласить.</span><span class="sxs-lookup"><span data-stu-id="58449-208">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="58449-209">Нажмите **Добавить**, а затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="58449-209">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="58449-210">Чтобы пригласить гостей в команду, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="58449-210">To invite guests to a team</span></span>
1. <span data-ttu-id="58449-211">В команде нажмите **Дополнительные параметры** (**\*\*\***) и выберите **Добавить участника**.</span><span class="sxs-lookup"><span data-stu-id="58449-211">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="58449-212">Введите адрес электронной почты пользователя, которого вы хотите пригласить.</span><span class="sxs-lookup"><span data-stu-id="58449-212">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="58449-213">Нажмите **Изменить сведения о госте**.</span><span class="sxs-lookup"><span data-stu-id="58449-213">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="58449-214">Введите полное имя гостя и установите флажок.</span><span class="sxs-lookup"><span data-stu-id="58449-214">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="58449-215">Нажмите **Добавить**, а затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="58449-215">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="58449-216">См. также</span><span class="sxs-lookup"><span data-stu-id="58449-216">See also</span></span>

[<span data-ttu-id="58449-217">Рекомендации по предоставлению общего доступа к файлам и папкам непроверенным пользователям</span><span class="sxs-lookup"><span data-stu-id="58449-217">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="58449-218">Ограничение возможности случайного раскрытия файлов при предоставлении доступа гостям</span><span class="sxs-lookup"><span data-stu-id="58449-218">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="58449-219">Создание безопасной среды гостевого общего доступа</span><span class="sxs-lookup"><span data-stu-id="58449-219">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="58449-220">Создание экстрасети B2B с управляемыми гостями</span><span class="sxs-lookup"><span data-stu-id="58449-220">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="58449-221">Интеграция SharePoint и OneDrive с Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="58449-221">SharePoint and OneDrive integration with Azure AD B2B</span></span>](/sharepoint/sharepoint-azureb2b-integration-preview)

[<span data-ttu-id="58449-222">При совместном использовании в SharePoint Online или OneDrive параметры общего доступа недоступны для выбора</span><span class="sxs-lookup"><span data-stu-id="58449-222">Sharing options are greyed out when sharing from SharePoint or OneDrive</span></span>](/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)