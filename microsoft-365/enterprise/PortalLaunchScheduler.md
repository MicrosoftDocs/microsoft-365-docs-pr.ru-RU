---
title: Запуск портала с помощью планировщика запуска портала
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
description: В этой статье описывается, как можно запустить портал с помощью планировщика запуска портала.
ms.openlocfilehash: 929492742fd140654bd13be8165093ee10647c6d
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999595"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="ce3b4-103">Запуск портала с помощью планировщика запуска портала</span><span class="sxs-lookup"><span data-stu-id="ce3b4-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="ce3b4-104">Вы можете запустить портал с помощью планировщика запуска портала, сначала проверив возможность настройки волн для нового портала администратором клиента.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-104">You can launch your portal using the Portal Launch Scheduler by first validating the tenant admin's ability to setup a waves for a new portal.</span></span> <span data-ttu-id="ce3b4-105">Затем администратор может проверить перенаправление запросов на основании существования пользователя в активных волнах.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-105">Then the admin can validate a redirection of requests, based on the existence of a user in the active waves.</span></span>

<span data-ttu-id="ce3b4-106">Для получения дополнительных сведений о запуске успешного портала следуйте основным принципам, рекомендациям и рекомендациям, описанным в разделе [Создание, запуск и обслуживание работоспособного портала](https://go.microsoft.com/fwlink/?linkid=2105838).</span><span class="sxs-lookup"><span data-stu-id="ce3b4-106">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in the [Creating, launching and maintaining a healthy portal](https://go.microsoft.com/fwlink/?linkid=2105838).</span></span> 

## <a name="app-setup"></a><span data-ttu-id="ce3b4-107">Установка приложения</span><span class="sxs-lookup"><span data-stu-id="ce3b4-107">App setup</span></span>
1. <span data-ttu-id="ce3b4-108">Удалить, если вы уже наступили `Microsoft.Online.SharePoint.PowerShell` с компьютера с помощью панели управления.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-108">Uninstall if there an existing `Microsoft.Online.SharePoint.PowerShell` from your machine through the control panel.</span></span>
2. <span data-ttu-id="ce3b4-109">На этапе PowerShell `Install-Module -Name Microsoft.Online.SharePoint.PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="ce3b4-109">On PowerShell pass `Install-Module -Name Microsoft.Online.SharePoint.PowerShell`.</span></span>

## <a name="connect-to-sharepoint-online"></a><span data-ttu-id="ce3b4-110">Подключение к SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ce3b4-110">Connect to SharePoint Online</span></span>
1. <span data-ttu-id="ce3b4-111">Откройте [командную консоль SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) в Windows.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-111">Open the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) in Windows.</span></span>
2. <span data-ttu-id="ce3b4-112">Подключитесь к клиенту от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-112">Connect to your tenant as an admin.</span></span>
   - `Connect-SPOService -Url "https://*-admin.sharepoint.com" -Credential "username”`
3.  <span data-ttu-id="ce3b4-113">При появлении соответствующего запроса введите пароль.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-113">Supply your password when prompted.</span></span>

## <a name="command-to-get-an-existing-setup"></a><span data-ttu-id="ce3b4-114">Команда для получения существующей программы установки</span><span class="sxs-lookup"><span data-stu-id="ce3b4-114">Command to get an existing setup</span></span>

<span data-ttu-id="ce3b4-115">Чтобы просмотреть существующие конфигурации запуска портала, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-115">To view existing portal launch configurations:</span></span>

1. <span data-ttu-id="ce3b4-116">Pass `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite` .</span><span class="sxs-lookup"><span data-stu-id="ce3b4-116">Pass `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite`.</span></span>
2. <span data-ttu-id="ce3b4-117">Передайте дополнительный параметр, `-DisplayFormat Raw` Если вы хотите просмотреть коллекцию волн, отформатированную как необработанный входной формат.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-117">Pass the additional parameter `-DisplayFormat Raw` if you wish to see the wave collection formatted as a raw input format.</span></span>

## <a name="commands-for-bi-directional-redirection"></a><span data-ttu-id="ce3b4-118">Команды для перенаправления с двунаправленным письмом</span><span class="sxs-lookup"><span data-stu-id="ce3b4-118">Commands for bi-directional redirection</span></span>

<span data-ttu-id="ce3b4-119">Для поэтапной миграции старых пользователей сайта на новый сайт:</span><span class="sxs-lookup"><span data-stu-id="ce3b4-119">To migrate old site users to the new site in a staged manner:</span></span>

1. <span data-ttu-id="ce3b4-120">Создание волновых спусков.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-120">Create Portal launch waves.</span></span>
   - <span data-ttu-id="ce3b4-121">Это относится только к этапам проверки раннего выпуска.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-121">This is only applicable in the early release test phase.</span></span>
   - <span data-ttu-id="ce3b4-122">Чтобы протестировать влияние изменения немедленно, убедитесь, что для первой волновой записи `LaunchDateUtc` задана текущая дата.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-122">To test the impact of the change immediately, make sure the first wave `LaunchDateUtc` is set to the current date.</span></span> <span data-ttu-id="ce3b4-123">Если этот флаг не указан, будет выведено сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-123">If you do not supply this flag, you get an error message.</span></span> <span data-ttu-id="ce3b4-124">Эта ошибка возникает, так как запуск в рабочей среде должен быть запланирован по крайней мере на 7 дней заранее.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-124">This error happens because launches in production must be scheduled at least 7 days in advance.</span></span>

  `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="ce3b4-125">Выполнение проверки.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-125">Complete validation.</span></span>
  - <span data-ttu-id="ce3b4-126">Перенаправление для завершения настройки в службе может занять до 5 минут, поэтому необходимо подождать, прежде чем продолжить.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-126">It can take up to 5 minutes for the redirection to complete its configuration across the service, so please wait before continuing.</span></span>
  - <span data-ttu-id="ce3b4-127">Если вы выполняете вход с указанным пользователем `WaveOverrideUsers` , ничего не изменится.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-127">If you login with the user specified as `WaveOverrideUsers`, then nothing changes.</span></span> <span data-ttu-id="ce3b4-128">Вы должны находиться на сайте, на который вы перемещаетесь.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-128">You should be staying at the site you navigated to.</span></span>
  - <span data-ttu-id="ce3b4-129">Войдите в систему, используя пользователя, который входит в число *посетителей SG1*.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-129">Login with a user who is part of *Viewers SG1*.</span></span>
    - <span data-ttu-id="ce3b4-130">Перейдите на старый сайт, и вы должны быть перенаправлены на новый сайт.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-130">Navigate to the old site and you should be redirected to the new site.</span></span>
    - <span data-ttu-id="ce3b4-131">Перейдите к новому сайту, и вы должны остаться на новом сайте.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-131">Navigate to the new site and you should be stay on the new site.</span></span>
    - <span data-ttu-id="ce3b4-132">Войдите в систему с помощью средства "Пользователи" *SG2* и перейдите к старому сайту и оставайтесь на старом сайте.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-132">Log with user in *Viewers SG2* and navigate to the old site and stay on the old site.</span></span>
    - <span data-ttu-id="ce3b4-133">Перейдите к новому сайту, и вы должны быть перенаправлены на старый сайт.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-133">Navigate to the new site and you should be redirected to the old site.</span></span>

3. <span data-ttu-id="ce3b4-134">Приостановка запуска портала.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-134">Pause Portal launch.</span></span>
  - <span data-ttu-id="ce3b4-135">Если необходимо приостановить номера выпуска, можно приостановить их для "x" дней.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-135">If you need to pause the launch waves, you can pause them for "x" number of days.</span></span> <span data-ttu-id="ce3b4-136">Установка `Status` флага приостановить предотвращает все будущие волновые прогрессии.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-136">Setting the `Status` flag to pause prevents all upcoming wave progressions.</span></span> 
  - <span data-ttu-id="ce3b4-137">`Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-137">`Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="ce3b4-138">При этом будут проверены, что все пользователи перенаправляются на старый сайт.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-138">This validates that all users are redirected to the old site.</span></span>

4. <span data-ttu-id="ce3b4-139">Перезапустите процесс запуска портала.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-139">Restart the portal launch progression.</span></span> 
  - <span data-ttu-id="ce3b4-140">`Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-140">`Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="ce3b4-141">Проверка того, что перенаправление восстановлено.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-141">Validate that the redirection is now restored.</span></span>

5. <span data-ttu-id="ce3b4-142">Удаление параметров запуска портала.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-142">Delete a portal launch setup.</span></span>
  - <span data-ttu-id="ce3b4-143">`Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-143">`Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="ce3b4-144">Проверка того, что перенаправление не выполняется для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-144">Validate that no redirection happens for all users.</span></span>

## <a name="commands-for-redirection-to-temporary-page"></a><span data-ttu-id="ce3b4-145">Команды для перенаправления на временную страницу</span><span class="sxs-lookup"><span data-stu-id="ce3b4-145">Commands for redirection to temporary page</span></span>

<span data-ttu-id="ce3b4-146">Выполните указанные ниже действия, если вы не используете предыдущий сайт и хотите опустить пользователей, не включенных в элемент "волна" на новой странице портала.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-146">Follow these steps if you have no previous site and you want to omit users not in the wave from landing on the new portal page.</span></span>

<span data-ttu-id="ce3b4-147">Чтобы создать временную страницу на любом из сайтов:</span><span class="sxs-lookup"><span data-stu-id="ce3b4-147">To create a temporary page in any of the sites:</span></span>

1. <span data-ttu-id="ce3b4-148">Создайте Звукозапись для запуска портала.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-148">Create a Portal launch Wave.</span></span>
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="ce3b4-149">Выполнение проверки.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-149">Complete validation.</span></span>

  - <span data-ttu-id="ce3b4-150">Подождите пять минут, прежде чем продолжить, так как выполнение действия может занять до пяти минут.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-150">Wait five minutes before continuing, as the action can take up to five minutes to complete.</span></span>
  - <span data-ttu-id="ce3b4-151">Войдите в систему пользователя, который входит в состав *посетителей SG1* и:</span><span class="sxs-lookup"><span data-stu-id="ce3b4-151">Log with the user who is part of *Viewers SG1* and:</span></span>
     - <span data-ttu-id="ce3b4-152">Перейдите к новому сайту, и вы должны остаться на новом сайте.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-152">Navigate to the new site, and you should be stay on the new site.</span></span>
     - <span data-ttu-id="ce3b4-153">Перейдите на страницу Temp, и вы должны остаться на странице Temp.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-153">Navigate to the temp page, and you should be stay on the temp page.</span></span>
  - <span data-ttu-id="ce3b4-154">Войдите в систему пользователя, который входит в состав *посетителей SG2* и:</span><span class="sxs-lookup"><span data-stu-id="ce3b4-154">Log with the user who is part of *Viewers SG2* and:</span></span>
     - <span data-ttu-id="ce3b4-155">Перейдите к новому сайту, и вы будете перенаправлены на страницу Temp.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-155">Navigate to the new site, and you should be redirected to the temp page.</span></span>
     - <span data-ttu-id="ce3b4-156">Перейдите на страницу Temp, и вы должны остаться на странице Temp.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-156">Navigate to the temp page, and you should stay on the temp page.</span></span>

3. <span data-ttu-id="ce3b4-157">Удаление параметров запуска портала.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-157">Delete a portal launch setup.</span></span>
  - <span data-ttu-id="ce3b4-158">`Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-158">`Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="ce3b4-159">Проверка того, что перенаправление не выполняется для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="ce3b4-159">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="ce3b4-160">Подробнее</span><span class="sxs-lookup"><span data-stu-id="ce3b4-160">Learn more</span></span>
[<span data-ttu-id="ce3b4-161">Планирование развертывания портала для запуска в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ce3b4-161">Planning your portal launch roll-out plan in SharePoint Online</span></span>](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)