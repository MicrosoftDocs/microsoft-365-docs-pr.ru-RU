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
description: В этой статье вы узнаете, как совместно работать с гостями над документом в SharePoint и OneDrive.
ms.openlocfilehash: 1b2fe003902b69e4c0c58852af67862ce6f2eb34
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663515"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="a93cb-103">Совместная работа с гостями над документом</span><span class="sxs-lookup"><span data-stu-id="a93cb-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="a93cb-104">Если вам нужно сотрудничать с людьми за пределами вашей организации над документами в SharePoint или OneDrive, вы можете отправить им ссылку для общего доступа к документу.</span><span class="sxs-lookup"><span data-stu-id="a93cb-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing-link to the document.</span></span> <span data-ttu-id="a93cb-105">В этой статье мы разберем действия по настройке Microsoft 365, необходимые для настройки ссылок общего доступа для SharePoint и OneDrive в соответствии с потребностями вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a93cb-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing-links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="a93cb-106">Видеодемонстрация</span><span class="sxs-lookup"><span data-stu-id="a93cb-106">Video demonstration</span></span>

<span data-ttu-id="a93cb-107">В этом видео показаны действия по настройке, описанные в этом документе.</span><span class="sxs-lookup"><span data-stu-id="a93cb-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="a93cb-108">Параметры внешней совместной работы Azure</span><span class="sxs-lookup"><span data-stu-id="a93cb-108">Azure external collaboration settings</span></span>

<span data-ttu-id="a93cb-109">Общий доступ в Microsoft 365 управляется на самом высоком уровне с помощью параметров внешней совместной работы [B2B в Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)</span><span class="sxs-lookup"><span data-stu-id="a93cb-109">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="a93cb-110">Если в Azure AD отключен или запрещен общий доступ для гостей, этот параметр переопределяет все параметры общего доступа, настроенные в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a93cb-110">If guest-sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="a93cb-111">Проверьте параметры внешней совместной работы B2B, чтобы убедиться, что общий доступ гостям не заблокирован.</span><span class="sxs-lookup"><span data-stu-id="a93cb-111">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Снимок экрана: страница параметров организационных связей Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="a93cb-113">Настройка параметров внешней совместной работы</span><span class="sxs-lookup"><span data-stu-id="a93cb-113">To set external collaboration settings</span></span>

1. <span data-ttu-id="a93cb-114">Войдите в Azure Active Directory [https://aad.portal.azure.com](https://aad.portal.azure.com) по</span><span class="sxs-lookup"><span data-stu-id="a93cb-114">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="a93cb-115">В левой области навигации щелкните **Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="a93cb-115">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="a93cb-116">Щелкните **"Внешние удостоверения".**</span><span class="sxs-lookup"><span data-stu-id="a93cb-116">Click **External identities**.</span></span>
4. <span data-ttu-id="a93cb-117">На экране **"Начало работы"** в левой области навигации щелкните параметры **внешней совместной работы.**</span><span class="sxs-lookup"><span data-stu-id="a93cb-117">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="a93cb-118">**Убедитесь, что администраторы** и пользователи в  роли приглашенного гостя могут приглашать гостей, а для участников установлено значение **"Да".**</span><span class="sxs-lookup"><span data-stu-id="a93cb-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="a93cb-119">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a93cb-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="a93cb-120">Обратите внимание на параметры в разделе **"Ограничения для совместной работы".**</span><span class="sxs-lookup"><span data-stu-id="a93cb-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="a93cb-121">Убедитесь, что домены гостей, с которых вы хотите сотрудничать, не блокируются.</span><span class="sxs-lookup"><span data-stu-id="a93cb-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="a93cb-122">Если вы работаете с гостями из нескольких организаций, вы можете ограничить их возможность доступа к данным каталога.</span><span class="sxs-lookup"><span data-stu-id="a93cb-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="a93cb-123">Это не позволит им увидеть, кто еще является гостем в каталоге.</span><span class="sxs-lookup"><span data-stu-id="a93cb-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="a93cb-124">Для этого в соответствии с ограничениями  доступа гостевых пользователей доступ к гостевых пользователей ограничен доступом к свойствам и членством в параметрах объектов каталога или доступ гостевых пользователей ограничен свойствами и членством в их собственных объектах **каталогов.**</span><span class="sxs-lookup"><span data-stu-id="a93cb-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="a93cb-125">Параметры общего доступа на уровне организации SharePoint</span><span class="sxs-lookup"><span data-stu-id="a93cb-125">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="a93cb-126">Чтобы у людей за пределами организации был доступ к документу в SharePoint или OneDrive, параметры общего доступа на уровне организации SharePoint и OneDrive должны разрешать общий доступ пользователям за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="a93cb-126">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="a93cb-127">Параметры на уровне организации для SharePoint определяют параметры, которые будут доступны для отдельных сайтов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a93cb-127">The organization-level settings for SharePoint determine the settings that will be available for individual SharePoint sites.</span></span> <span data-ttu-id="a93cb-128">Параметры сайта не могут быть более нео разрешательными, чем параметры на уровне организации.</span><span class="sxs-lookup"><span data-stu-id="a93cb-128">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="a93cb-129">Параметр на уровне организации для OneDrive определяет уровень общего доступа, который будет доступен в библиотеках OneDrive пользователей.</span><span class="sxs-lookup"><span data-stu-id="a93cb-129">The organization-level setting for OneDrive determines the level of sharing that will be available in users' OneDrive libraries.</span></span>

<span data-ttu-id="a93cb-130">Если вы хотите разрешить общий доступ к файлам и папам, неавтоматическим данным, в SharePoint и OneDrive, выберите **"Все".**</span><span class="sxs-lookup"><span data-stu-id="a93cb-130">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="a93cb-131">Если вы хотите убедиться, что людям за пределами вашей организации необходимо проверить подлинность, выберите **"Новые" и "Существующие гости".**</span><span class="sxs-lookup"><span data-stu-id="a93cb-131">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="a93cb-132">*Ссылки* для всех — самый простой способ поделиться: люди за пределами организации могут открывать ссылку без проверки подлинности и могут передавать ее другим.</span><span class="sxs-lookup"><span data-stu-id="a93cb-132">*Anyone* links is the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="a93cb-133">Для SharePoint выберите наиболее ненадобную настройку, которая потребуется любому сайту в организации.</span><span class="sxs-lookup"><span data-stu-id="a93cb-133">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Снимок экрана: параметры общего доступа в SharePoint на уровне организации](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="a93cb-135">Настройка параметров общего доступа на уровне организации SharePoint</span><span class="sxs-lookup"><span data-stu-id="a93cb-135">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="a93cb-136">В Центре администрирования Microsoft 365 в левой области навигации в центре администрирования **щелкните** **SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="a93cb-136">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="a93cb-137">В Центре администрирования SharePoint в области навигации слева в разделе **"Политики"** щелкните **"Общий доступ".**</span><span class="sxs-lookup"><span data-stu-id="a93cb-137">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="a93cb-138">Убедитесь, что для внешнего общего доступа для SharePoint или OneDrive установлено имя **"Любой",** **"Новый" и "Существующие гости".**</span><span class="sxs-lookup"><span data-stu-id="a93cb-138">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="a93cb-139">(Обратите внимание, что параметр OneDrive не может быть более разрешительным, чем параметр SharePoint.)</span><span class="sxs-lookup"><span data-stu-id="a93cb-139">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="a93cb-140">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a93cb-140">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="a93cb-141">Параметры ссылок по умолчанию на уровне организации SharePoint</span><span class="sxs-lookup"><span data-stu-id="a93cb-141">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="a93cb-142">Параметры ссылки на файл и папку по умолчанию определяют параметр ссылки, который будет по умолчанию показываться пользователям при совместном доступе к файлу или папке.</span><span class="sxs-lookup"><span data-stu-id="a93cb-142">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="a93cb-143">При желании пользователи могут изменить тип ссылки на один из других вариантов перед совместным доступом.</span><span class="sxs-lookup"><span data-stu-id="a93cb-143">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="a93cb-144">Помните, что этот параметр влияет на сайты SharePoint в вашей организации, а также OneDrive.</span><span class="sxs-lookup"><span data-stu-id="a93cb-144">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="a93cb-145">Выберите ссылку любого из следующих типов, которые затем выбираются по умолчанию при совместном доступе пользователей к файлам и папок:</span><span class="sxs-lookup"><span data-stu-id="a93cb-145">Choose a link from any of the following types which is then selected by default when users share files and folders:</span></span>

- <span data-ttu-id="a93cb-146">**Любой, у кого есть** ссылка— выберите этот параметр, если вы хотите сделать много общего доступа к файлам и папам, которые не были проавентированы.</span><span class="sxs-lookup"><span data-stu-id="a93cb-146">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="a93cb-147">Если вы хотите  разрешить ссылки "Любой", но вас беспокоит случайное неавтоматическое совместное использование, рассмотрите один из других вариантов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a93cb-147">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="a93cb-148">Этот тип ссылки доступен, только если вы включили общий **доступ для всех.**</span><span class="sxs-lookup"><span data-stu-id="a93cb-148">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="a93cb-149">**Только для людей в вашей** организации. Выберите этот вариант, если вы ожидаете, что большая часть общего доступа к файлам и папок будет делаться с людьми из вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a93cb-149">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="a93cb-150">**Конкретные люди—** рассмотрите этот вариант, если вы хотите сделать много файлов и папок, чтобы поделиться с гостями.</span><span class="sxs-lookup"><span data-stu-id="a93cb-150">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="a93cb-151">Этот тип ссылки работает с гостями и требует от них проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="a93cb-151">This type of link works with guests and requires them to authenticate.</span></span>
 
![Снимок экрана: параметры общего доступа к файлам и папкам в SharePoint на уровне организации](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="a93cb-153">Установка параметров ссылок по умолчанию для SharePoint и OneDrive на уровне организации</span><span class="sxs-lookup"><span data-stu-id="a93cb-153">To set the SharePoint and OneDrive organization-level default link settings</span></span>

1. <span data-ttu-id="a93cb-154">Перейдите на страницу "Общий доступ" в Центре администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a93cb-154">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="a93cb-155">В **разделе "Ссылки на файлы и папки"** выберите ссылку для общего доступа по умолчанию, которую вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="a93cb-155">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="a93cb-156">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a93cb-156">If you made changes, click **Save**.</span></span>

<span data-ttu-id="a93cb-157">Чтобы установить разрешение для ссылки для общего доступа, в разделе "Выберите разрешение, выбранное по умолчанию для **ссылок для общего доступа".**</span><span class="sxs-lookup"><span data-stu-id="a93cb-157">To set the permission for the sharing link, under **Choose the permission that's selected by default for sharing links.**</span></span>

1. <span data-ttu-id="a93cb-158">Выберите **"Вид",** если не хотите, чтобы неавтерицированные пользователи внося изменения в файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="a93cb-158">Select **View** if you do not want unauthenticated users to make changes to the files and folders.</span></span>
2. <span data-ttu-id="a93cb-159">Выберите  "Изменить", если вы хотите разрешить пользователям, неавтиентенным пользователям, вносить изменения в файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="a93cb-159">Select **Edit** if you want to allow unauthenticated users to make changes to the files and folders.</span></span>

<span data-ttu-id="a93cb-160">Обратите внимание, что два вышеперечисленных параметра предварительной передачи могут применяться не только для гостей и внешних пользователей, но и для внутренних пользователей.</span><span class="sxs-lookup"><span data-stu-id="a93cb-160">Note that the above two premission-options can be applied not only for guests/external users but also for internal users.</span></span> <span data-ttu-id="a93cb-161">Выбираемый параметр разрешений определяется по собственному усмотрению.</span><span class="sxs-lookup"><span data-stu-id="a93cb-161">The permission-option you choose is determined by self-discretion.</span></span>

<span data-ttu-id="a93cb-162">Настройка разрешений для ссылок, позволяющих обмениваться данными с любыми пользователями</span><span class="sxs-lookup"><span data-stu-id="a93cb-162">To set permissions for links that allow sharing with anyone</span></span>

1. <span data-ttu-id="a93cb-163">По этим **ссылкам можно предоставить такие разрешения:** в подмайке,</span><span class="sxs-lookup"><span data-stu-id="a93cb-163">Under the **These links can give these permissions:** sub-pane,</span></span> 
    1. <span data-ttu-id="a93cb-164">В **выпадаемом** списке "Файлы"</span><span class="sxs-lookup"><span data-stu-id="a93cb-164">From the **Files** drop-down list,</span></span> 
        - <span data-ttu-id="a93cb-165">Выберите **"Просмотреть" и** "Изменить", если вы хотите разрешить пользователям, неавтиентическим пользователям, вносить изменения в файлы.</span><span class="sxs-lookup"><span data-stu-id="a93cb-165">Select **View and edit** if you want to allow unauthenticated users to make changes to the files.</span></span>
        - <span data-ttu-id="a93cb-166">Выберите **"Вид",** если не хотите, чтобы неавтерицированные пользователи внося изменения в файлы.</span><span class="sxs-lookup"><span data-stu-id="a93cb-166">Select **View** if you do not want unauthenticated users to make changes to the files.</span></span>
    2. <span data-ttu-id="a93cb-167">В **выпадаемом списке** "Папки"</span><span class="sxs-lookup"><span data-stu-id="a93cb-167">From the **Folders** drop-down list,</span></span>
        - <span data-ttu-id="a93cb-168">Выберите **"Просмотр", "Изменить" и "Отправить",** если вы хотите разрешить пользователям, не непроверяющих, вносить изменения в папки.</span><span class="sxs-lookup"><span data-stu-id="a93cb-168">Select **View, edit, and upload** if you want to allow unauthenticated users to make changes to the folders.</span></span>
        - <span data-ttu-id="a93cb-169">Выберите **"Вид",** если не хотите, чтобы неавтерицированные пользователи могли вносить изменения в папки.</span><span class="sxs-lookup"><span data-stu-id="a93cb-169">Select **View** if you do not want unauthenticated users to make changes to the folders.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="a93cb-170">Параметры общего доступа на уровне сайта SharePoint</span><span class="sxs-lookup"><span data-stu-id="a93cb-170">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="a93cb-171">При совместном использовании файлов и папок, которые находятся на сайте SharePoint, необходимо также проверить параметры общего доступа на уровне сайта для этого сайта.</span><span class="sxs-lookup"><span data-stu-id="a93cb-171">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![Снимок экрана: параметры внешнего общего доступа к сайту SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="a93cb-173">Настройка параметров общего доступа на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="a93cb-173">To set site-level sharing settings</span></span>

1. <span data-ttu-id="a93cb-174">В Центре администрирования SharePoint в области навигации слева разйдите раздел **"Сайты"** и щелкните **"Активные сайты".**</span><span class="sxs-lookup"><span data-stu-id="a93cb-174">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="a93cb-175">Выберите сайт, на котором вы хотите поделиться файлами и папками с гостями.</span><span class="sxs-lookup"><span data-stu-id="a93cb-175">Select the site on which you want to share files and folders with guests.</span></span>
3. <span data-ttu-id="a93cb-176">Прокрутите вниз по строке (в которой присутствует выбранный сайт) и щелкните в любом месте столбца "Внешний **общий доступ".**</span><span class="sxs-lookup"><span data-stu-id="a93cb-176">Scroll right across the row (in which the selected site is present) and click anywhere in the **External sharing** column.</span></span>
4. <span data-ttu-id="a93cb-177">На всплываемой странице щелкните вкладку **"Политики".**</span><span class="sxs-lookup"><span data-stu-id="a93cb-177">From the page that pops up, click **Policies** tab.</span></span>
5. <span data-ttu-id="a93cb-178">В области **внешнего общего** доступа нажмите кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="a93cb-178">Under the **External sharing** pane, click **Edit**.</span></span>
6. <span data-ttu-id="a93cb-179">Убедитесь, что для общего доступа установлено **"Любой"** **или "Новый" и "Существующие гости".**</span><span class="sxs-lookup"><span data-stu-id="a93cb-179">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
7. <span data-ttu-id="a93cb-180">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a93cb-180">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="a93cb-181">Приглашение пользователей</span><span class="sxs-lookup"><span data-stu-id="a93cb-181">Invite users</span></span>

<span data-ttu-id="a93cb-182">Теперь настроены параметры общего доступа для гостей; теперь пользователи могут делиться файлами и папками с пользователями за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a93cb-182">Guest-sharing settings are now configured; so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="a93cb-183">Дополнительные [сведения см.](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) в файлах и папках SharePoint, а также в файлах и папках [SharePoint.](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c)</span><span class="sxs-lookup"><span data-stu-id="a93cb-183">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="a93cb-184">См. также</span><span class="sxs-lookup"><span data-stu-id="a93cb-184">See also</span></span>

[<span data-ttu-id="a93cb-185">Рекомендации по предоставлению общего доступа к файлам и папкам непроверенным пользователям</span><span class="sxs-lookup"><span data-stu-id="a93cb-185">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="a93cb-186">Ограничение возможности случайного раскрытия файлов при предоставлении доступа гостям</span><span class="sxs-lookup"><span data-stu-id="a93cb-186">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="a93cb-187">Интеграция SharePoint и OneDrive с Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="a93cb-187">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
