---
title: Совместная работа с гостями над документом
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
description: В этой статье вы узнаете, как сотрудничать с гостями в документе в SharePoint и OneDrive.
ms.openlocfilehash: 9158ec7692ef90eb2e270242472fceb10d0e60b7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920232"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="cf6d2-103">Совместная работа с гостями над документом</span><span class="sxs-lookup"><span data-stu-id="cf6d2-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="cf6d2-104">Если вам необходимо сотрудничать с людьми за пределами организации в документах в SharePoint или OneDrive, вы можете отправить им ссылку на общий доступ к документу.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing-link to the document.</span></span> <span data-ttu-id="cf6d2-105">В этой статье мы проявим действия по настройке Microsoft 365, необходимые для настройки ссылок общего доступа для SharePoint и OneDrive для нужд вашей организации.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing-links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="cf6d2-106">Видеодемонстрация</span><span class="sxs-lookup"><span data-stu-id="cf6d2-106">Video demonstration</span></span>

<span data-ttu-id="cf6d2-107">В этом видео показаны действия по настройке, описанные в этом документе.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="cf6d2-108">Параметры внешней совместной работы Azure</span><span class="sxs-lookup"><span data-stu-id="cf6d2-108">Azure external collaboration settings</span></span>

<span data-ttu-id="cf6d2-109">Общий доступ в Microsoft 365 настраивается на самом высоком уровне с помощью [параметров внешней совместной работы B2B в Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="cf6d2-109">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="cf6d2-110">Если общий доступ к гостю отключен или ограничен в Azure AD, этот параметр переопределяет все параметры общего доступа, настроенные в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-110">If guest-sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="cf6d2-111">Проверьте параметры внешней совместной работы B2B, чтобы обеспечить, чтобы общий доступ к гостям не был заблокирован.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-111">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Снимок экрана: страница параметров организационных связей Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="cf6d2-113">Чтобы настроить параметры внешней совместной работы, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-113">To set external collaboration settings</span></span>

1. <span data-ttu-id="cf6d2-114">Войдите в Azure Active Directory на сайте [https://aad.portal.azure.com](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="cf6d2-114">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="cf6d2-115">В области навигации слева щелкните **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-115">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="cf6d2-116">Нажмите **Внешние удостоверения**.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-116">Click **External identities**.</span></span>
4. <span data-ttu-id="cf6d2-117">На экране **Начало работы** в области навигации слева щелкните **Параметры внешней совместной работы**.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-117">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="cf6d2-118">Убедитесь, что для параметров **Администраторы и пользователи с ролью "Приглашающий гостей" могут приглашать** и **Участники могут приглашать** установлено значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="cf6d2-119">Если вы внесли изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="cf6d2-120">Обратите внимание на параметры в разделе **Ограничения совместной работы**.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="cf6d2-121">Убедитесь, что домены гостей, с которыми вы хотите сотрудничать, не заблокированы.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="cf6d2-122">Если вы работаете с гостями из нескольких организаций, вы можете ограничить их доступ к данным каталога.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="cf6d2-123">Это не позволит им видеть других гостей в каталоге.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="cf6d2-124">Для этого в разделе **Ограничения доступа гостевых пользователей** выберите **Гостевые пользователи имеют ограниченный доступ к свойствам и членству в параметрах объектов каталога** или **Доступ гостевых пользователей ограничен свойствами и членством в их собственных объектах каталога**.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="cf6d2-125">Параметры общего доступа на уровне организации SharePoint</span><span class="sxs-lookup"><span data-stu-id="cf6d2-125">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="cf6d2-126">Чтобы у людей за пределами организации был доступ к документу в SharePoint или OneDrive, параметры общего доступа на уровне организации SharePoint и OneDrive должны разрешить совместное использование с пользователями, не входя в организацию.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-126">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="cf6d2-127">Параметры на уровне организации для SharePoint определяют параметры, доступные для отдельных сайтов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-127">The organization-level settings for SharePoint determine the settings that will be available for individual SharePoint sites.</span></span> <span data-ttu-id="cf6d2-128">Параметры сайта не могут разрешать больше, чем параметры на уровне организации.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-128">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="cf6d2-129">Параметр на уровне организации Для OneDrive определяет уровень общего доступа, который будет доступен в библиотеках OneDrive пользователей.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-129">The organization-level setting for OneDrive determines the level of sharing that will be available in users' OneDrive libraries.</span></span>

<span data-ttu-id="cf6d2-130">Для SharePoint и OneDrive, если вы хотите разрешить неавентированное совместное использование файлов и папок, выберите **Anyone**.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-130">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="cf6d2-131">Если вы хотите убедиться, что люди за пределами организации должны проверить подлинность, выберите **новые и существующие гости.**</span><span class="sxs-lookup"><span data-stu-id="cf6d2-131">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="cf6d2-132">*Все* ссылки — это самый простой способ обмена данными: люди за пределами организации могут открыть ссылку без проверки подлинности и могут бесплатно передавать ее другим.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-132">*Anyone* links is the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="cf6d2-133">Для SharePoint выберите наиболее разрешительный параметр, который будет необходим любому сайту в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-133">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Снимок экрана: настройка параметров общего доступа для SharePoint на уровне организации](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="cf6d2-135">Чтобы настроить общий доступ для SharePoint на уровне организации, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-135">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="cf6d2-136">В Центре администрирования Microsoft 365 в области навигации слева в разделе **Центры администрирования** выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-136">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="cf6d2-137">В центре администрирования SharePoint в левой области навигации в **разделе Политики** нажмите **кнопку Совместное использование**.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-137">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="cf6d2-138">Убедитесь, что внешний общий доступ для SharePoint или OneDrive установлен для **всех** или **новых и существующих гостей.**</span><span class="sxs-lookup"><span data-stu-id="cf6d2-138">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="cf6d2-139">(Обратите внимание, что параметр OneDrive не может быть более допустимым, чем параметр SharePoint.)</span><span class="sxs-lookup"><span data-stu-id="cf6d2-139">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="cf6d2-140">Если вы внесли изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-140">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="cf6d2-141">Настройка ссылок по умолчанию для SharePoint на уровне организации</span><span class="sxs-lookup"><span data-stu-id="cf6d2-141">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="cf6d2-142">Параметры ссылок на файлы или папки по умолчанию определяют тип ссылок, которые будет отображаться пользователям по умолчанию при совместном использовании файлов или папок.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-142">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="cf6d2-143">При желании пользователи могут изменить тип ссылки на один из доступных вариантов перед совместным использованием.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-143">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="cf6d2-144">Имейте в виду, что этот параметр влияет на сайты SharePoint в вашей организации, а также OneDrive.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-144">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="cf6d2-145">Выберите ссылку из любого из следующих типов, которые затем выбираются по умолчанию при совместном доступе пользователей к файлам и папок:</span><span class="sxs-lookup"><span data-stu-id="cf6d2-145">Choose a link from any of the following types which is then selected by default when users share files and folders:</span></span>

- <span data-ttu-id="cf6d2-146">**Любой человек со ссылкой** — выберите этот параметр, если вы ожидаете сделать много неавентированных файлов и общего доступа к папкам.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-146">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="cf6d2-147">Если вы хотите разрешить тип ссылок *Все*, но беспокоитесь о случайном общем доступе без проверки подлинности, рассмотрите один из следующих вариантов в качестве варианта по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-147">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="cf6d2-148">Этот тип ссылки доступен, только если включен общий доступ для **всех**.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-148">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="cf6d2-149">**Только люди в вашей организации**. Выберите этот вариант, если ожидается, что совместное использование большей части файлов и папок будет осуществляться пользователями внутри вашей организации.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-149">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="cf6d2-150">**Конкретные люди**. Рассмотрите этот вариант, если ожидается совместное использование большого количества файлов и папок гостями.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-150">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="cf6d2-151">Этот тип ссылки работает с гостями и требует от них прохождения проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-151">This type of link works with guests and requires them to authenticate.</span></span>
 
![Снимок экрана: настройка параметров общего доступа к файлам и папкам в SharePoint на уровне организации](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="cf6d2-153">Настройка параметров ссылок по умолчанию на уровне организации SharePoint и OneDrive</span><span class="sxs-lookup"><span data-stu-id="cf6d2-153">To set the SharePoint and OneDrive organization-level default link settings</span></span>

1. <span data-ttu-id="cf6d2-154">Перейдите на страницу общего доступа в Центре администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-154">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="cf6d2-155">В разделе **Ссылки на файлы и папки** выберите ссылку для общего доступа, которая будет использоваться по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-155">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="cf6d2-156">Если вы внесли изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-156">If you made changes, click **Save**.</span></span>

<span data-ttu-id="cf6d2-157">Чтобы установить разрешение для ссылки общего доступа, выберите разрешение, выбранное по умолчанию **для обмена ссылками.**</span><span class="sxs-lookup"><span data-stu-id="cf6d2-157">To set the permission for the sharing link, under **Choose the permission that's selected by default for sharing links.**</span></span>

1. <span data-ttu-id="cf6d2-158">Выберите **View,** если не хотите, чтобы неавентированные пользователи внося изменения в файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-158">Select **View** if you do not want unauthenticated users to make changes to the files and folders.</span></span>
2. <span data-ttu-id="cf6d2-159">Выберите **Изменить,** если вы хотите разрешить неавентическим пользователям вносить изменения в файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-159">Select **Edit** if you want to allow unauthenticated users to make changes to the files and folders.</span></span>

<span data-ttu-id="cf6d2-160">Обратите внимание, что эти два параметра предварительной миссии могут применяться не только для гостей и внешних пользователей, но и для внутренних пользователей.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-160">Note that the above two premission-options can be applied not only for guests/external users but also for internal users.</span></span> <span data-ttu-id="cf6d2-161">Выбор разрешения определяется по собственному усмотрению.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-161">The permission-option you choose is determined by self-discretion.</span></span>

<span data-ttu-id="cf6d2-162">Настройка разрешений для ссылок, позволяющих делиться с кем-либо</span><span class="sxs-lookup"><span data-stu-id="cf6d2-162">To set permissions for links that allow sharing with anyone</span></span>

1. <span data-ttu-id="cf6d2-163">В соответствии **с этими ссылками можно предоставить такие разрешения:**</span><span class="sxs-lookup"><span data-stu-id="cf6d2-163">Under the **These links can give these permissions:** sub-pane,</span></span> 
    1. <span data-ttu-id="cf6d2-164">Из **выпадаемого** списка Files</span><span class="sxs-lookup"><span data-stu-id="cf6d2-164">From the **Files** drop-down list,</span></span> 
        - <span data-ttu-id="cf6d2-165">Выберите **Просмотр и изменение,** если вы хотите разрешить неавентическим пользователям вносить изменения в файлы.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-165">Select **View and edit** if you want to allow unauthenticated users to make changes to the files.</span></span>
        - <span data-ttu-id="cf6d2-166">Выберите **View,** если не хотите, чтобы неавентированные пользователи внося изменения в файлы.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-166">Select **View** if you do not want unauthenticated users to make changes to the files.</span></span>
    2. <span data-ttu-id="cf6d2-167">Из **выпадаемого** списка папок</span><span class="sxs-lookup"><span data-stu-id="cf6d2-167">From the **Folders** drop-down list,</span></span>
        - <span data-ttu-id="cf6d2-168">Выберите **Просмотр, редактирование** и отправку, если вы хотите разрешить неавентическим пользователям вносить изменения в папки.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-168">Select **View, edit, and upload** if you want to allow unauthenticated users to make changes to the folders.</span></span>
        - <span data-ttu-id="cf6d2-169">Выберите **Просмотр,** если вы не хотите, чтобы неавентированные пользователи внося изменения в папки.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-169">Select **View** if you do not want unauthenticated users to make changes to the folders.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="cf6d2-170">Настройка параметров общего доступа на уровне сайта SharePoint</span><span class="sxs-lookup"><span data-stu-id="cf6d2-170">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="cf6d2-171">Если вы делитесь файлами и папками, которые находятся на сайте SharePoint, вам также необходимо проверить параметры общего доступа на уровне сайта для этого сайта.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-171">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![Снимок экрана: настройка параметров внешнего общего доступа для сайта SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="cf6d2-173">Чтобы настроить параметры общего доступа на уровне сайта, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-173">To set site-level sharing settings</span></span>

1. <span data-ttu-id="cf6d2-174">В Центре администрирования SharePoint в области навигации слева разверните раздел **Сайты** и нажмите **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-174">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="cf6d2-175">Выберите сайт, на котором необходимо обмениваться файлами и папками с гостями.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-175">Select the site on which you want to share files and folders with guests.</span></span>
3. <span data-ttu-id="cf6d2-176">Прокрутите правую строку (в которой присутствует выбранный сайт) и нажмите кнопку в любом месте в столбце **Внешний общий** доступ.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-176">Scroll right across the row (in which the selected site is present) and click anywhere in the **External sharing** column.</span></span>
4. <span data-ttu-id="cf6d2-177">На всплываемой странице нажмите вкладку **Политики.**</span><span class="sxs-lookup"><span data-stu-id="cf6d2-177">From the page that pops up, click **Policies** tab.</span></span>
5. <span data-ttu-id="cf6d2-178">В области **внешнего общего** доступа нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-178">Under the **External sharing** pane, click **Edit**.</span></span>
6. <span data-ttu-id="cf6d2-179">Убедитесь, что для параметра общего доступа установлено значение **Все** или **Новые и существующие гости**.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-179">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
7. <span data-ttu-id="cf6d2-180">Если вы внесли изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-180">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="cf6d2-181">Приглашение пользователей</span><span class="sxs-lookup"><span data-stu-id="cf6d2-181">Invite users</span></span>

<span data-ttu-id="cf6d2-182">Параметры обмена гостями теперь настроены; чтобы теперь пользователи могли обмениваться файлами и папками с людьми за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-182">Guest-sharing settings are now configured; so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="cf6d2-183">Дополнительные сведения см. в разделе Share [OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders.](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c)</span><span class="sxs-lookup"><span data-stu-id="cf6d2-183">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf6d2-184">См. также</span><span class="sxs-lookup"><span data-stu-id="cf6d2-184">See also</span></span>

[<span data-ttu-id="cf6d2-185">Рекомендации по предоставлению общего доступа к файлам и папкам непроверенным пользователям</span><span class="sxs-lookup"><span data-stu-id="cf6d2-185">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="cf6d2-186">Ограничение возможности случайного раскрытия файлов при предоставлении доступа гостям</span><span class="sxs-lookup"><span data-stu-id="cf6d2-186">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="cf6d2-187">Интеграция SharePoint и OneDrive с Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="cf6d2-187">SharePoint and OneDrive integration with Azure AD B2B</span></span>](/sharepoint/sharepoint-azureb2b-integration-preview)