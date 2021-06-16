---
title: Запуск портала с помощью план-графика запуска портала
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: В этой статье описывается, как можно запустить портал с помощью планера запуска Портала
ms.openlocfilehash: fb092ea2500aaa139a34e511d224ec4419e04cb5
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930263"
---
# <a name="launch-your-portal-using-the-sharepoint-portal-launch-scheduler"></a><span data-ttu-id="7eedb-103">Запуск портала с помощью SharePoint календаря запуска портала</span><span class="sxs-lookup"><span data-stu-id="7eedb-103">Launch your portal using the SharePoint Portal launch scheduler</span></span>

<span data-ttu-id="7eedb-104">Портал — это сайт SharePoint на вашем интрасети с высоким трафиком — сайт с количеством от 10 000 до 100 000 зрителей в течение нескольких недель.</span><span class="sxs-lookup"><span data-stu-id="7eedb-104">A portal is a SharePoint communication site on your intranet that is high-traffic – a site that has anywhere from 10,000 to over 100,000 viewers over the course of several weeks.</span></span> <span data-ttu-id="7eedb-105">Используйте план-график запуска портала для запуска портала, чтобы обеспечить пользователям возможность плавного просмотра при доступе к вашему SharePoint порталу.</span><span class="sxs-lookup"><span data-stu-id="7eedb-105">Use the Portal launch scheduler to launch your portal to ensure users have a smooth viewing experience when accessing your new SharePoint portal.</span></span>
<br>
<br>
<span data-ttu-id="7eedb-106">План-график запуска Портала предназначен для того, чтобы помочь вам следовать поэтапному подходу к выкатыву, пакетив просмотры в волнах и управляя URL-адресами для нового портала.</span><span class="sxs-lookup"><span data-stu-id="7eedb-106">The Portal launch scheduler is designed to help you follow a phased roll-out approach by batching viewers in waves and managing the URL redirects for the new portal.</span></span> <span data-ttu-id="7eedb-107">Во время запуска каждой волны можно собирать отзывы пользователей, отслеживать производительность портала и приостанавлить запуск, чтобы устранить проблемы перед началом следующей волны.</span><span class="sxs-lookup"><span data-stu-id="7eedb-107">During the launch of each wave, you can gather user feedback, monitor portal performance, and pause the launch to resolve issues before proceeding with the next wave.</span></span> <span data-ttu-id="7eedb-108">Узнайте больше о планировании [запуска портала](/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide)в SharePoint .</span><span class="sxs-lookup"><span data-stu-id="7eedb-108">Learn more about how to [plan a portal launch in SharePoint](/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span></span>

<span data-ttu-id="7eedb-109">**Существует два типа перенаправления:**</span><span class="sxs-lookup"><span data-stu-id="7eedb-109">**There are two types of redirections:**</span></span>

- <span data-ttu-id="7eedb-110">**Bidirectional**: запустите новый современный SharePoint, чтобы заменить существующий SharePoint или современный портал</span><span class="sxs-lookup"><span data-stu-id="7eedb-110">**Bidirectional**: launch a new modern SharePoint portal to replace an existing SharePoint classic or modern portal</span></span>
- <span data-ttu-id="7eedb-111">**Перенаправление** на временную страницу: запустите новый современный портал SharePoint без существующего SharePoint портала</span><span class="sxs-lookup"><span data-stu-id="7eedb-111">**Redirect to a temporary page**: launch a new modern SharePoint portal with no existing SharePoint portal</span></span>

<span data-ttu-id="7eedb-112">Разрешения сайта должны быть настроены отдельно от волн в рамках запуска.</span><span class="sxs-lookup"><span data-stu-id="7eedb-112">Site permissions must be set up separately from waves as part of the launch.</span></span> <span data-ttu-id="7eedb-113">Например, при выпуске портала для всей организации можно установить разрешения на "Все, кроме внешних пользователей", а затем разделить пользователей на волны с помощью групп безопасности.</span><span class="sxs-lookup"><span data-stu-id="7eedb-113">For example, if you are releasing an organization-wide portal, you can set permissions to “Everyone except external users,” then separate your users into waves using security groups.</span></span> <span data-ttu-id="7eedb-114">Добавление группы безопасности к волне не дает этой группе безопасности доступ к сайту.</span><span class="sxs-lookup"><span data-stu-id="7eedb-114">Adding a security group to a wave does not give that security group access to the site.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="7eedb-115">Эта функция будет доступна с панели **Параметры** на домашней странице сайтов SharePoint связи для целевых клиентов выпуска начиная с мая 2021 г. и станет доступной для всех клиентов к июлю 2021 г.</span><span class="sxs-lookup"><span data-stu-id="7eedb-115">This feature will be accessible from the **Settings** panel on the home page of SharePoint communication sites for Targeted release customers starting in May 2021 and will become available to all customers by July 2021</span></span>
> - <span data-ttu-id="7eedb-116">Версия PowerShell этого средства доступна сегодня</span><span class="sxs-lookup"><span data-stu-id="7eedb-116">The PowerShell version of this tool is available today</span></span>
> - <span data-ttu-id="7eedb-117">Эту функцию можно использовать только на современных сайтах SharePoint связи</span><span class="sxs-lookup"><span data-stu-id="7eedb-117">This feature can only be used on modern SharePoint communication sites</span></span>
> - <span data-ttu-id="7eedb-118">Чтобы настроить и запланировать запуск портала, необходимо иметь разрешения владельца сайта.</span><span class="sxs-lookup"><span data-stu-id="7eedb-118">You must have site owner permissions for the site to customize and schedule the launch of a portal</span></span>
> - <span data-ttu-id="7eedb-119">Запуски должны быть запланированы не менее чем за семь дней до начала, и каждая волна может длиться от одного до семи дней</span><span class="sxs-lookup"><span data-stu-id="7eedb-119">Launches must be scheduled at least seven days in advance and each wave can last one to seven days</span></span>
> - <span data-ttu-id="7eedb-120">Количество требуемого количества волн автоматически определяется ожидаемым числом пользователей</span><span class="sxs-lookup"><span data-stu-id="7eedb-120">The number of waves required is automatically determined by the expected number of users</span></span>
> - <span data-ttu-id="7eedb-121">Перед планированием запуска портала необходимо запустить SharePoint page [Diagnostics for SharePoint,](https://aka.ms/perftool) чтобы убедиться, что домашняя страница сайта здорова</span><span class="sxs-lookup"><span data-stu-id="7eedb-121">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) must be run to verify that the home page of the site is healthy</span></span>
> - <span data-ttu-id="7eedb-122">По завершении запуска все пользователи с разрешениями на сайт смогут получить доступ к новому сайту</span><span class="sxs-lookup"><span data-stu-id="7eedb-122">At the end of the launch, all users with permissions to the site will be able to access the new site</span></span>
> - <span data-ttu-id="7eedb-123">Если ваша организация использует [Viva Connections,](/SharePoint/viva-connections)пользователи могут видеть значок вашей организации в панели приложений Microsoft Teams, однако при выборе значка пользователи не смогут получить доступ к порталу до запуска волны.</span><span class="sxs-lookup"><span data-stu-id="7eedb-123">If your organization is using [Viva Connections](/SharePoint/viva-connections), users may see your organization's icon in the Microsoft Teams app bar, however when the icon is selected users will not be able to access the portal until their wave has launched</span></span>
> - <span data-ttu-id="7eedb-124">Эта функция недоступна для Office 365, Office 365 21Vianet (Китай) или Microsoft 365 планов правительства США</span><span class="sxs-lookup"><span data-stu-id="7eedb-124">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans</span></span>

## <a name="understand-the-differences-between-portal-launch-scheduler-options"></a><span data-ttu-id="7eedb-125">Понимание различий между вариантами расписания запуска портала:</span><span class="sxs-lookup"><span data-stu-id="7eedb-125">Understand the differences between Portal launch scheduler options:</span></span>

<span data-ttu-id="7eedb-126">Ранее запуски портала могли быть запланированы только через SharePoint PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7eedb-126">Formerly, portal launches could only be scheduled through SharePoint PowerShell.</span></span> <span data-ttu-id="7eedb-127">Теперь у вас есть два варианта, которые помогут вам планировать запуск портала и управлять им.</span><span class="sxs-lookup"><span data-stu-id="7eedb-127">Now, you have two options to help you schedule and manage your portal's launch.</span></span> <span data-ttu-id="7eedb-128">Узнайте о ключевых различиях между обоими средствами:</span><span class="sxs-lookup"><span data-stu-id="7eedb-128">Learn about the key differences between both tools:</span></span>

<span data-ttu-id="7eedb-129">**SharePoint Версия PowerShell:**</span><span class="sxs-lookup"><span data-stu-id="7eedb-129">**SharePoint PowerShell version:**</span></span>

- <span data-ttu-id="7eedb-130">Учетные данные администратора необходимы для [SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell)</span><span class="sxs-lookup"><span data-stu-id="7eedb-130">Admin credentials are required to use [SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell)</span></span>
- <span data-ttu-id="7eedb-131">Минимальное требование одной волны</span><span class="sxs-lookup"><span data-stu-id="7eedb-131">Minimum requirement of one wave</span></span>
- <span data-ttu-id="7eedb-132">Запланировать запуск на основе согласованного часовой пояса универсального времени (UTC)</span><span class="sxs-lookup"><span data-stu-id="7eedb-132">Schedule your launch based on Coordinated Universal Time (UTC) time zone</span></span>

<span data-ttu-id="7eedb-133">**In-product version:**</span><span class="sxs-lookup"><span data-stu-id="7eedb-133">**In-product version:**</span></span>

- <span data-ttu-id="7eedb-134">Необходимы учетные данные владельца сайта</span><span class="sxs-lookup"><span data-stu-id="7eedb-134">Site owner credentials are required</span></span>
- <span data-ttu-id="7eedb-135">Минимальное требование в две волны</span><span class="sxs-lookup"><span data-stu-id="7eedb-135">Minimum requirement of two waves</span></span>
- <span data-ttu-id="7eedb-136">Запланировать запуск на основе локального часовой пояса портала, как указано в региональных параметрах</span><span class="sxs-lookup"><span data-stu-id="7eedb-136">Schedule your launch based on the portal's local time zone as indicated in regional settings</span></span>

## <a name="get-started-using-the-portal-launch-scheduler"></a><span data-ttu-id="7eedb-137">Начало работы с помощью планера запуска портала</span><span class="sxs-lookup"><span data-stu-id="7eedb-137">Get started using the Portal launch scheduler</span></span>

1. <span data-ttu-id="7eedb-138">Прежде чем использовать средство расписания запуска [Портала,](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) добавьте всех  пользователей, которым потребуется доступ к этому сайту, с помощью разрешений сайта в качестве владельца сайта, члена сайта или посетителя.</span><span class="sxs-lookup"><span data-stu-id="7eedb-138">Before using the Portal launch scheduler tool, [add all users who will need access to this site](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) through **Site permissions** as a Site owner, Site member, or Visitor.</span></span>

2. <span data-ttu-id="7eedb-139">Затем приступить к планированию запуска портала с помощью доступа к планировщику запуска портала одним из двух способов:</span><span class="sxs-lookup"><span data-stu-id="7eedb-139">Then, start scheduling your portal’s launch by accessing the Portal launch scheduler in one of two ways:</span></span>

   <span data-ttu-id="7eedb-140">**Вариант 1.** Первые несколько раз, когда вы редактируете и переопубликовывайте изменения на домашней странице или вплоть до домашней страницы версии 3.0, вам будет предложено использовать средство расписания запуска портала.</span><span class="sxs-lookup"><span data-stu-id="7eedb-140">**Option 1**: The first few times you edit and republish changes to your home page - or up until home page version 3.0 - you will be prompted to use the Portal launch scheduler tool.</span></span> <span data-ttu-id="7eedb-141">Выберите **запуск Schedule,** чтобы двигаться вперед с планированием.</span><span class="sxs-lookup"><span data-stu-id="7eedb-141">Select **Schedule launch** to move forward with scheduling.</span></span> <span data-ttu-id="7eedb-142">Или выберите **Republish,** чтобы переиздать изменения страницы без планирования запуска.</span><span class="sxs-lookup"><span data-stu-id="7eedb-142">Or select **Republish** to republish your page edits without scheduling the launch.</span></span>

   ![Изображение запроса на использование планера запуска портала при переопубликовании домашней страницы](../media/portal-launch-republish-2.png)

   <span data-ttu-id="7eedb-144">**Вариант 2.** В любое время можно перейти на домашную  страницу SharePoint  связи, выбрать Параметры, а затем запланировать запуск сайта, чтобы запланировать запуск портала.</span><span class="sxs-lookup"><span data-stu-id="7eedb-144">**Option 2**: At any time, you can navigate to the SharePoint communication site home page, select **Settings** and then **Schedule site launch** to schedule your portal’s launch.</span></span>

   ![Изображение области Параметры с расписанием запуска сайта выделено](../media/portal-launch-settings-2.png)

3. <span data-ttu-id="7eedb-146">Далее подтвердите оценку состояния здоровья портала и в случае необходимости с помощью средства Page [Diagnostics для](https://aka.ms/perftool) SharePoint, пока портал не получит **полезный** результат.</span><span class="sxs-lookup"><span data-stu-id="7eedb-146">Next, confirm the portal’s health score and make improvements to the portal if needed using the [Page Diagnostics for SharePoint](https://aka.ms/perftool) tool until your portal receives a **Healthy** score.</span></span> <span data-ttu-id="7eedb-147">Затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7eedb-147">Then, select **Next**.</span></span>

   ![Изображение средства расписания запуска портала](../media/portal-launch-panel-2.png)

   > [!NOTE]
   > <span data-ttu-id="7eedb-149">Имя и описание сайта не могут быть изменены из расписания запуска портала, а вместо  этого можно изменить, выбрав Параметры, а затем сведения о сайте на домашней странице. </span><span class="sxs-lookup"><span data-stu-id="7eedb-149">The site name and description can’t be edited from the Portal launch scheduler and instead can be changed by selecting **Settings** and then **Site information** from the home page.</span></span>

4. <span data-ttu-id="7eedb-150">Выберите **число ожидаемых пользователей** из отсевной части.</span><span class="sxs-lookup"><span data-stu-id="7eedb-150">Select the **Number of expected users** from the drop-down.</span></span> <span data-ttu-id="7eedb-151">Этот показатель представляет число пользователей, которым, скорее всего, потребуется доступ к сайту.</span><span class="sxs-lookup"><span data-stu-id="7eedb-151">This figure represents the number of users who will most likely need access to the site.</span></span> <span data-ttu-id="7eedb-152">План-график запуска портала автоматически определяет идеальное количество волн в зависимости от ожидаемых пользователей, таких как:</span><span class="sxs-lookup"><span data-stu-id="7eedb-152">The Portal launch scheduler will automatically determine the ideal number of waves depending on the expected users like this:</span></span>

   - <span data-ttu-id="7eedb-153">Менее 10k пользователей: две волны</span><span class="sxs-lookup"><span data-stu-id="7eedb-153">Less than 10k users: Two waves</span></span>
   - <span data-ttu-id="7eedb-154">От 10k до 30k пользователей: три волны</span><span class="sxs-lookup"><span data-stu-id="7eedb-154">10k to 30k users: Three waves</span></span>
   - <span data-ttu-id="7eedb-155">30k+ до 100k пользователей: пять волн</span><span class="sxs-lookup"><span data-stu-id="7eedb-155">30k+ to 100k users: Five waves</span></span>
   - <span data-ttu-id="7eedb-156">Более 100k пользователей: пять волн и свяжитесь с Microsoft по шагам, перечисленным на портале Запуск с более чем 100k пользователей раздела.</span><span class="sxs-lookup"><span data-stu-id="7eedb-156">More than 100k users: Five waves and contact your Microsoft via the steps listed in Launch portal with over 100k users section.</span></span>

5. <span data-ttu-id="7eedb-157">Затем определите **необходимый тип перенаправления:**</span><span class="sxs-lookup"><span data-stu-id="7eedb-157">Then, determine the **Type of redirect** needed:</span></span>

   <span data-ttu-id="7eedb-158">**Вариант 1.** Отправка пользователей на существующую страницу SharePoint (бидайрекционная) — Используйте этот параметр при запуске нового современного портала SharePoint, чтобы заменить существующий портал SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7eedb-158">**Option 1: Send users to an existing SharePoint page (bidirectional)** – Use this option when launching a new modern SharePoint portal to replace an existing SharePoint portal.</span></span> <span data-ttu-id="7eedb-159">Пользователи в активных волнах будут перенаправлены на новый сайт независимо от того, переходят ли они на старый или новый сайт.</span><span class="sxs-lookup"><span data-stu-id="7eedb-159">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="7eedb-160">Пользователи не запущенной волны, которые пытаются получить доступ к новому сайту, будут перенаправлены обратно на старый сайт до запуска волны.</span><span class="sxs-lookup"><span data-stu-id="7eedb-160">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7eedb-161">При использовании параметра bidirectional у лица, запланив запуск, также должны быть разрешения владельца сайта на другой SharePoint портале.</span><span class="sxs-lookup"><span data-stu-id="7eedb-161">When using the bidirectional option, the person scheduling the launch must also have site owner permissions to the other SharePoint portal.</span></span>

   <span data-ttu-id="7eedb-162">**Вариант 2.** Отправка пользователей на автогенерированную временную страницу (временное перенаправление страницы) — Использование временной перенаправления страниц следует использовать, если не существует существующего SharePoint портала.</span><span class="sxs-lookup"><span data-stu-id="7eedb-162">**Option 2: Send users to an autogenerated temporary page (temporary page redirection)** – Use a temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="7eedb-163">Пользователи направляются на новый современный портал SharePoint, и если пользователь находится в волне, которая не запущена, они будут перенаправлены на временную страницу.</span><span class="sxs-lookup"><span data-stu-id="7eedb-163">Users are directed to a new modern SharePoint portal and if a user is in a wave that has not been launched, they will be redirected to a temporary page.</span></span>

   <span data-ttu-id="7eedb-164">**Вариант 3. Отправка** пользователей на внешнюю страницу — предоставление внешнего URL-адреса на временную пусковую страницу до запуска волны пользователя.</span><span class="sxs-lookup"><span data-stu-id="7eedb-164">**Option 3: Send users to an external page** – Provide an external URL to a temporary landing page experience until the user’s wave is launched.</span></span>

6. <span data-ttu-id="7eedb-165">Разгон аудитории на волны.</span><span class="sxs-lookup"><span data-stu-id="7eedb-165">Break up your audience into waves.</span></span> <span data-ttu-id="7eedb-166">Добавьте до 20 групп безопасности на одну волну.</span><span class="sxs-lookup"><span data-stu-id="7eedb-166">Add up to 20 security groups per wave.</span></span> <span data-ttu-id="7eedb-167">Сведения о волне можно изменить до запуска каждой волны.</span><span class="sxs-lookup"><span data-stu-id="7eedb-167">Wave details can be edited up until the launch of each wave.</span></span> <span data-ttu-id="7eedb-168">Каждая волна может длиться как минимум один день (24 часа) и не более семи дней.</span><span class="sxs-lookup"><span data-stu-id="7eedb-168">Each wave can last at minimum one day (24 hours) and at most seven days.</span></span> <span data-ttu-id="7eedb-169">Это позволяет SharePoint и вашей технической среде возможность акклиматить и масштабироваться до большого объема пользователей сайта.</span><span class="sxs-lookup"><span data-stu-id="7eedb-169">This allows SharePoint and your technical environment an opportunity to acclimate and scale to the large volume of site users.</span></span> <span data-ttu-id="7eedb-170">При планировании запуска через пользовательский интерфейс часовой пояс основан на региональных параметрах сайта.</span><span class="sxs-lookup"><span data-stu-id="7eedb-170">When scheduling a launch through the UI, the time zone is based on the site’s regional settings.</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="7eedb-171">План-график запуска портала автоматически по умолчанию будет не менее 2 волн.</span><span class="sxs-lookup"><span data-stu-id="7eedb-171">The Portal launch scheduler will automatically default to a minimum of 2 waves.</span></span> <span data-ttu-id="7eedb-172">Однако версия PowerShell этого средства позволяет использовать 1 волну.</span><span class="sxs-lookup"><span data-stu-id="7eedb-172">However, the PowerShell version of this tool will allow for 1 wave.</span></span>
   > - <span data-ttu-id="7eedb-173">Microsoft 365 группы не поддерживаются этой версией план-графика запуска Портала.</span><span class="sxs-lookup"><span data-stu-id="7eedb-173">Microsoft 365 groups are not supported by this version of the Portal launch scheduler.</span></span>

7. <span data-ttu-id="7eedb-174">Определите, кому нужно сразу просмотреть сайт и ввести их сведения в **поле Пользователи, освобожденные от полей волн.**</span><span class="sxs-lookup"><span data-stu-id="7eedb-174">Determine who needs to view the site right away and enter their information into the **Users exempt from waves** field.</span></span> <span data-ttu-id="7eedb-175">Эти пользователи исключены из волн и не будут перенаправлены до, во время или после запуска.</span><span class="sxs-lookup"><span data-stu-id="7eedb-175">These users are excluded from waves and will not be redirected before, during, or after the launch.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7eedb-176">Для всего запуска можно использовать до 50 различных пользователей или групп безопасности.</span><span class="sxs-lookup"><span data-stu-id="7eedb-176">Up to 50 distinct users or security groups max can be used for the entire launch.</span></span> <span data-ttu-id="7eedb-177">Каждый запуск не зависит друг от друга, поэтому если вы запланировать запуск на другом портале, для этого запуска можно использовать до 50 групп пользователей и безопасности.</span><span class="sxs-lookup"><span data-stu-id="7eedb-177">Each launch is independent of each other, so if you schedule a launch on another portal, then you could use up to 50 users/security groups for that launch.</span></span> <span data-ttu-id="7eedb-178">Кроме того, на одной волне можно использовать до 20 различных пользователей или групп безопасности.</span><span class="sxs-lookup"><span data-stu-id="7eedb-178">Additionally, you can use up to 20 distinct users or security groups per wave.</span></span> 

><span data-ttu-id="7eedb-179">План-график запуска портала поддерживает группы безопасности и группы безопасности с включенной почтой.</span><span class="sxs-lookup"><span data-stu-id="7eedb-179">The portal launch scheduler supports security groups and mail enabled security groups.</span></span> 


8. <span data-ttu-id="7eedb-180">Подтверждение сведений о запуске портала и выберите **Расписание.**</span><span class="sxs-lookup"><span data-stu-id="7eedb-180">Confirm portal launch details and select **Schedule**.</span></span> <span data-ttu-id="7eedb-181">После запланированного запуска все изменения на домашней странице SharePoint портала должны получить здоровый диагностический результат до возобновления запуска портала.</span><span class="sxs-lookup"><span data-stu-id="7eedb-181">Once the launch has been scheduled, any changes to the SharePoint portal home page will need to receive a healthy diagnostic result before the portal launch will resume.</span></span>

### <a name="launch-a-portal-with-over-100k-users"></a><span data-ttu-id="7eedb-182">Запуск портала с более чем 100k пользователями</span><span class="sxs-lookup"><span data-stu-id="7eedb-182">Launch a portal with over 100k users</span></span>

<span data-ttu-id="7eedb-183">Если планируется запустить портал с более чем 100 000 пользователей, отправьте запрос на поддержку после перечисленных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="7eedb-183">If you are planning to launch a portal with over 100,000 users, submit a support request following the steps listed below.</span></span> <span data-ttu-id="7eedb-184">Обязательно включай всю запрашиваемую информацию.</span><span class="sxs-lookup"><span data-stu-id="7eedb-184">Make sure to include all the requested information.</span></span>

<span data-ttu-id="7eedb-185">**Выполните следующие действия.**</span><span class="sxs-lookup"><span data-stu-id="7eedb-185">**Follow these steps:**</span></span>

1. <span data-ttu-id="7eedb-186">Перейдите на сайт <https://admin.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="7eedb-186">Go to <https://admin.microsoft.com>.</span></span>
2. <span data-ttu-id="7eedb-187">Убедитесь, что вы используете новый центр предварительного просмотра центра администрирования</span><span class="sxs-lookup"><span data-stu-id="7eedb-187">Ensure you are using the new admin center preview</span></span>
3. <span data-ttu-id="7eedb-188">На левой области навигации выберите **поддержку** и выберите **новый запрос на службу**</span><span class="sxs-lookup"><span data-stu-id="7eedb-188">On the left navigational pane, select **Support**, and then select **New Service Request**</span></span>

   <span data-ttu-id="7eedb-189">Откроется область **Нужна помощь?** в правой части экрана.</span><span class="sxs-lookup"><span data-stu-id="7eedb-189">This will activate the **Need Help?** pane on the right-hand side of your screen.</span></span>

4. <span data-ttu-id="7eedb-190">Для **краткого описания проблемы** введите "Запуск SharePoint с 100k пользователями"</span><span class="sxs-lookup"><span data-stu-id="7eedb-190">For **Briefly describe your issue**, enter "Launch SharePoint Portal with 100k users"</span></span></br>
5. <span data-ttu-id="7eedb-191">Затем выберите **службу поддержки контактов**</span><span class="sxs-lookup"><span data-stu-id="7eedb-191">Then, select **Contact Support**</span></span>
6. <span data-ttu-id="7eedb-192">В **статье Описание** введите "Запуск SharePoint с 100k пользователями"</span><span class="sxs-lookup"><span data-stu-id="7eedb-192">Under **Description**, enter "Launch SharePoint Portal with 100k users"</span></span>
7. <span data-ttu-id="7eedb-193">Заполните оставшиеся сведения и выберите **Контакт**</span><span class="sxs-lookup"><span data-stu-id="7eedb-193">Fill out the remaining information, and then select **Contact me**</span></span>
8. <span data-ttu-id="7eedb-194">После создания запроса предоставьте агенту поддержки следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="7eedb-194">After the ticket has been created, ensure you provide the support agent with the following information:</span></span>
   - <span data-ttu-id="7eedb-195">URL-адрес портала</span><span class="sxs-lookup"><span data-stu-id="7eedb-195">Portal URL's</span></span>
   - <span data-ttu-id="7eedb-196">Число пользователей</span><span class="sxs-lookup"><span data-stu-id="7eedb-196">Number of users expected</span></span>
   - <span data-ttu-id="7eedb-197">Предполагаемое расписание запуска</span><span class="sxs-lookup"><span data-stu-id="7eedb-197">Estimated launch schedule</span></span>

## <a name="make-changes-to-a-scheduled-portal-launch"></a><span data-ttu-id="7eedb-198">Внесение изменений в запланированный запуск портала</span><span class="sxs-lookup"><span data-stu-id="7eedb-198">Make changes to a scheduled portal launch</span></span>

<span data-ttu-id="7eedb-199">Сведения о запуске можно изменить для каждой волны до даты запуска волны.</span><span class="sxs-lookup"><span data-stu-id="7eedb-199">Launch details can be edited for each wave up until the date of the wave’s launch.</span></span>

1. <span data-ttu-id="7eedb-200">Чтобы изменить сведения о запуске портала, перейдите **Параметры** и выберите **расписание запуска сайта.**</span><span class="sxs-lookup"><span data-stu-id="7eedb-200">To edit portal launch details, navigate to **Settings** and select **Schedule site launch**.</span></span>
2. <span data-ttu-id="7eedb-201">Затем выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="7eedb-201">Then, select **Edit**.</span></span>
3. <span data-ttu-id="7eedb-202">Когда вы закончите делать изменения, выберите **Обновление**.</span><span class="sxs-lookup"><span data-stu-id="7eedb-202">When you are finished making your edits, select **Update**.</span></span>

## <a name="delete-a-scheduled-portal-launch"></a><span data-ttu-id="7eedb-203">Удаление запланированного запуска портала</span><span class="sxs-lookup"><span data-stu-id="7eedb-203">Delete a scheduled portal launch</span></span>

<span data-ttu-id="7eedb-204">Запуски, запланированные с помощью средства расписания запуска Портала, могут быть отменены или удалены в любое время, даже если некоторые волны уже запущены.</span><span class="sxs-lookup"><span data-stu-id="7eedb-204">Launches scheduled using the Portal launch scheduler tool can be canceled, or deleted, at any time even if some waves have already been launched.</span></span>

1. <span data-ttu-id="7eedb-205">Чтобы отменить запуск портала, перейдите **на Параметры** и **запланировать запуск сайта.**</span><span class="sxs-lookup"><span data-stu-id="7eedb-205">To cancel your portal’s launch, navigate to **Settings** and **Schedule site launch**.</span></span>

2. <span data-ttu-id="7eedb-206">Затем выберите **Удаление,** а затем, когда вы увидите сообщение ниже, выберите **Удалить** еще раз.</span><span class="sxs-lookup"><span data-stu-id="7eedb-206">Then, select **Delete** and then when you see the message below select **Delete** again.</span></span>

   ![Изображение средства расписания запуска портала](../media/portal-launch-delete-2.png)

## <a name="use-the-powershell-portal-launch-scheduler"></a><span data-ttu-id="7eedb-208">Использование план-графика запуска портала PowerShell</span><span class="sxs-lookup"><span data-stu-id="7eedb-208">Use the PowerShell Portal launch scheduler</span></span>

<span data-ttu-id="7eedb-209">Изначально средство SharePoint портала было доступно только через [SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell) и будет по-прежнему поддерживаться с помощью PowerShell для клиентов, предпочитающих этот метод.</span><span class="sxs-lookup"><span data-stu-id="7eedb-209">The SharePoint Portal launch scheduler tool was originally only available via [SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell) and will continue to be supported through PowerShell for customers who prefer this method.</span></span> <span data-ttu-id="7eedb-210">Эти же заметки в начале этой статьи применяются к обеим версиям планера запуска Портала.</span><span class="sxs-lookup"><span data-stu-id="7eedb-210">The same notes at the beginning of this article apply to both versions of the Portal launch scheduler.</span></span>

> [!NOTE]
> <span data-ttu-id="7eedb-211">Для использования SharePoint PowerShell нужны разрешения администратора.</span><span class="sxs-lookup"><span data-stu-id="7eedb-211">You need administrator permissions to use SharePoint PowerShell.</span></span>
> <span data-ttu-id="7eedb-212">Сведения о запуске портала для запусков, созданных в PowerShell, будут отображаться и управляться в новом средстве расписания запуска портала в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7eedb-212">Portal launch details for launches created in PowerShell will appear and can be managed in the new Portal launch scheduler tool in SharePoint.</span></span>

### <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="7eedb-213">Настройка приложения и подключение к SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7eedb-213">App setup and connecting to SharePoint Online</span></span>

1. <span data-ttu-id="7eedb-214">[Скачайте последнюю версию командной консоли SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="7eedb-214">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="7eedb-p118">Если вы установили предыдущую версию командной консоли SharePoint Online, перейдите к разделу "Установка и удаление программ" и удалите компонент "Командная консоль SharePoint Online".</span><span class="sxs-lookup"><span data-stu-id="7eedb-p118">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell." </span></span><br><span data-ttu-id="7eedb-216">На странице Центра загрузки выберите нужный язык и нажмите кнопку "Скачать".</span><span class="sxs-lookup"><span data-stu-id="7eedb-216">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="7eedb-217">Вам будет предложено скачать версию x64 или x86 файла MSI.</span><span class="sxs-lookup"><span data-stu-id="7eedb-217">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="7eedb-218">Для 64-разрядной версии Windows скачайте файл x64, а для 32-разрядной — файл x86.</span><span class="sxs-lookup"><span data-stu-id="7eedb-218">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="7eedb-219">Если вы не знаете свою разрядность, см. статью [Какая у меня версия операционной системы Windows?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span><span class="sxs-lookup"><span data-stu-id="7eedb-219">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="7eedb-220">После скачивания файла запустите его и следуйте инструкциям мастера настройки.</span><span class="sxs-lookup"><span data-stu-id="7eedb-220">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="7eedb-221">Подключите SharePoint, используя [права глобального администратора или администратора SharePoint](/sharepoint/sharepoint-admin-role) в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7eedb-221">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="7eedb-222">Сведения о том, как это сделать, см. в статье [Начало работы с командной консолью SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="7eedb-222">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

### <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="7eedb-223">Просмотр всех существующих установок запуска портала</span><span class="sxs-lookup"><span data-stu-id="7eedb-223">View any existing portal launch setups</span></span>

<span data-ttu-id="7eedb-224">Чтобы узнать, существуют ли существующие конфигурации запуска портала:</span><span class="sxs-lookup"><span data-stu-id="7eedb-224">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

### <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="7eedb-225">Расписание запуска портала на сайте</span><span class="sxs-lookup"><span data-stu-id="7eedb-225">Schedule a portal launch on the site</span></span>

<span data-ttu-id="7eedb-226">Количество требуемого количества волн зависит от ожидаемого размера запуска.</span><span class="sxs-lookup"><span data-stu-id="7eedb-226">The number of waves required depends on your expected launch size.</span></span>

- <span data-ttu-id="7eedb-227">Менее 10k пользователей: одна волна</span><span class="sxs-lookup"><span data-stu-id="7eedb-227">Less than 10k users: One wave</span></span>
- <span data-ttu-id="7eedb-228">От 10k до 30k пользователей: три волны</span><span class="sxs-lookup"><span data-stu-id="7eedb-228">10k to 30k users: Three waves</span></span> 
- <span data-ttu-id="7eedb-229">30k+ до 100k пользователей: пять волн</span><span class="sxs-lookup"><span data-stu-id="7eedb-229">30k+ to 100k users: Five waves</span></span>
- <span data-ttu-id="7eedb-230">Более 100k пользователей: пять волн и свяжитесь с командой учетных записей Майкрософт</span><span class="sxs-lookup"><span data-stu-id="7eedb-230">More than 100k users: Five waves and contact your Microsoft account team</span></span>

#### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="7eedb-231">Действия по перенаправлению бидеректов</span><span class="sxs-lookup"><span data-stu-id="7eedb-231">Steps for bidirectional redirection</span></span>

<span data-ttu-id="7eedb-232">Перенаправление бидеректов включает запуск нового современного портала SharePoint Online, который заменит существующий SharePoint или современный портал.</span><span class="sxs-lookup"><span data-stu-id="7eedb-232">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="7eedb-233">Пользователи в активных волнах будут перенаправлены на новый сайт независимо от того, переходят ли они на старый или новый сайт.</span><span class="sxs-lookup"><span data-stu-id="7eedb-233">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="7eedb-234">Пользователи не запущенной волны, которые пытаются получить доступ к новому сайту, будут перенаправлены обратно на старый сайт до запуска волны.</span><span class="sxs-lookup"><span data-stu-id="7eedb-234">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span>

<span data-ttu-id="7eedb-235">Мы поддерживаем только перенаправление между домашней страницей по умолчанию на старом сайте и домашней страницей по умолчанию на новом сайте.</span><span class="sxs-lookup"><span data-stu-id="7eedb-235">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="7eedb-236">Если у вас есть администраторы или владельцы, которые нуждаются в доступе к старым и новым сайтам без перенаправления, убедитесь, что они указаны с помощью `WaveOverrideUsers` параметра.</span><span class="sxs-lookup"><span data-stu-id="7eedb-236">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span>

<span data-ttu-id="7eedb-237">Поэтапное перенос пользователей с существующего SharePoint сайта на новый SharePoint сайта:</span><span class="sxs-lookup"><span data-stu-id="7eedb-237">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="7eedb-238">Запустите следующую команду, чтобы назначить волны запуска портала.</span><span class="sxs-lookup"><span data-stu-id="7eedb-238">Run the following command to designate portal launch waves.</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="7eedb-239">Пример.</span><span class="sxs-lookup"><span data-stu-id="7eedb-239">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"},
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="7eedb-240">Полная проверка.</span><span class="sxs-lookup"><span data-stu-id="7eedb-240">Complete validation.</span></span> <span data-ttu-id="7eedb-241">Перенаправление может занять 5-10 минут, чтобы завершить конфигурацию по службе.</span><span class="sxs-lookup"><span data-stu-id="7eedb-241">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span>

#### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="7eedb-242">Действия по перенаправлению на временную страницу</span><span class="sxs-lookup"><span data-stu-id="7eedb-242">Steps for redirection to temporary page</span></span>

<span data-ttu-id="7eedb-243">Временное перенаправление страниц следует использовать, если не существует SharePoint портала.</span><span class="sxs-lookup"><span data-stu-id="7eedb-243">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="7eedb-244">Пользователи направляются на новый современный портал SharePoint Online поэтапно.</span><span class="sxs-lookup"><span data-stu-id="7eedb-244">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="7eedb-245">Если пользователь находится в волне, которая не была запущена, он будет перенаправлен на временную страницу (любой URL-адрес).</span><span class="sxs-lookup"><span data-stu-id="7eedb-245">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span>

1. <span data-ttu-id="7eedb-246">Запустите следующую команду, чтобы назначить волны запуска портала.</span><span class="sxs-lookup"><span data-stu-id="7eedb-246">Run the following command to designate portal launch waves.</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="7eedb-247">Пример.</span><span class="sxs-lookup"><span data-stu-id="7eedb-247">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"},
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="7eedb-248">Полная проверка.</span><span class="sxs-lookup"><span data-stu-id="7eedb-248">Complete validation.</span></span> <span data-ttu-id="7eedb-249">Перенаправление может занять 5-10 минут, чтобы завершить конфигурацию по службе.</span><span class="sxs-lookup"><span data-stu-id="7eedb-249">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span>

### <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="7eedb-250">Приостановка или перезапуск запуска портала на сайте</span><span class="sxs-lookup"><span data-stu-id="7eedb-250">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="7eedb-251">Чтобы приостановить запуск портала и временно предотвратить предстоящие прогрессии волн, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7eedb-251">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="7eedb-252">Проверка перенаправления всех пользователей на старый сайт.</span><span class="sxs-lookup"><span data-stu-id="7eedb-252">Validate that all users are redirected to the old site.</span></span>

3. <span data-ttu-id="7eedb-253">Чтобы перезапустить приостановленный запуск портала, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7eedb-253">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```

4. <span data-ttu-id="7eedb-254">Проверка восстановления перенаправления.</span><span class="sxs-lookup"><span data-stu-id="7eedb-254">Validate that the redirection is now restored.</span></span>

### <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="7eedb-255">Удаление запуска портала на сайте</span><span class="sxs-lookup"><span data-stu-id="7eedb-255">Delete a portal launch on the site</span></span>

1. <span data-ttu-id="7eedb-256">Запустите следующую команду, чтобы удалить запланированный или запущенный запуск портала для сайта.</span><span class="sxs-lookup"><span data-stu-id="7eedb-256">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="7eedb-257">Проверка того, что перенаправление не происходит для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="7eedb-257">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="7eedb-258">Подробнее</span><span class="sxs-lookup"><span data-stu-id="7eedb-258">Learn more</span></span>

[<span data-ttu-id="7eedb-259">Планирование плана запуска портала в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7eedb-259">Planning your portal launch roll-out plan in SharePoint Online</span></span>](./planportallaunchroll-out.md)

[<span data-ttu-id="7eedb-260">Планирование сайта связи</span><span class="sxs-lookup"><span data-stu-id="7eedb-260">Plan your communication site</span></span>](https://support.microsoft.com/office/plan-your-sharepoint-communication-site-35d9adfe-d5cc-462f-a63a-bae7f2529182)
