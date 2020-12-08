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
ms.openlocfilehash: 7e488caba5e4df47bb3f51f195e093891565d95c
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367205"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="35128-103">Запуск портала с помощью планировщика запуска портала</span><span class="sxs-lookup"><span data-stu-id="35128-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="35128-104">Портал — это сайт SharePoint в вашей интрасети, у которого есть большое количество посетителей сайта, использующих его содержимое.</span><span class="sxs-lookup"><span data-stu-id="35128-104">A portal is a SharePoint site on your intranet that has a large number of site viewers who consume content on the site.</span></span> <span data-ttu-id="35128-105">Запуск портала в волне является важной частью обеспечения гладкого и производительного взаимодействия пользователей с доступом к новому порталу SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="35128-105">Launching your portal in waves is an important part of ensuring users have a smooth and performant experience accessing a new SharePoint Online portal.</span></span> 

<span data-ttu-id="35128-106">Запуск в волнах — это ключевой способ развертывания портала, как описано в разделе [Планирование развертывания портала для запуска в SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="35128-106">Launching in waves is a key way to roll-out your portal, as detailed in [Planning your portal launch roll-out plan in SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span></span> <span data-ttu-id="35128-107">Планировщик запуска портала предназначен для выполнения поэтапного и поэтапного развертывания с помощью управления перенаправлениями для нового портала.</span><span class="sxs-lookup"><span data-stu-id="35128-107">The Portal Launch Scheduler is designed to help you follow a wave / phased roll-out approach by managing the redirects for the new portal.</span></span> <span data-ttu-id="35128-108">Во время каждой волны вы можете собирать отзывы пользователей и мониторинг производительности во время каждой волны развертывания.</span><span class="sxs-lookup"><span data-stu-id="35128-108">During each of the waves, you can gather user feedback and monitor performance during each wave of deployment.</span></span> <span data-ttu-id="35128-109">Благодаря этому вы можете приостановить и устранить проблемы, прежде чем переходить к следующему волнам, и в конечном счете обеспечить положительную работу пользователей.</span><span class="sxs-lookup"><span data-stu-id="35128-109">This has the advantage of slowly introducing the portal, giving you the option to pause and resolve issues before proceeding with the next wave, and ultimately ensuring a positive experience for your users.</span></span> 

<span data-ttu-id="35128-110">Существует два типа перенаправления:</span><span class="sxs-lookup"><span data-stu-id="35128-110">There are two types of redirection:</span></span> 
- <span data-ttu-id="35128-111">Двунаправленная: запуск нового современного портала SharePoint Online для замены существующего классического или современного портала SharePoint</span><span class="sxs-lookup"><span data-stu-id="35128-111">bidirectional: launch a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal</span></span> 
- <span data-ttu-id="35128-112">временное перенаправление страниц: запуск нового современного портала SharePoint Online без существующего портала SharePoint</span><span class="sxs-lookup"><span data-stu-id="35128-112">temporary page redirection: launch a new modern SharePoint Online portal with no existing SharePoint portal</span></span>

<span data-ttu-id="35128-113">Планировщик запуска портала доступен только для запуска современных порталов SharePoint Online, например сайтов для общения и современных сайтов групп.</span><span class="sxs-lookup"><span data-stu-id="35128-113">The portal launch scheduler is only available to launch modern SharePoint Online portals, i.e. communication sites and modern team sites.</span></span> <span data-ttu-id="35128-114">Запуск должен быть запланирован по крайней мере на 7 дней заранее.</span><span class="sxs-lookup"><span data-stu-id="35128-114">Launches must be scheduled at least 7 days in advance.</span></span> <span data-ttu-id="35128-115">Количество требуемых волн определяется ожидаемым количеством пользователей.</span><span class="sxs-lookup"><span data-stu-id="35128-115">The number of waves required is determined by the expected number of users.</span></span> <span data-ttu-id="35128-116">Перед планированием запуска портала необходимо запустить [средство диагностики страниц для SharePoint](https://aka.ms/perftool) , чтобы убедиться, что домашняя страница на портале работоспособна.</span><span class="sxs-lookup"><span data-stu-id="35128-116">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) must be run to verify that the home page on the portal is healthy.</span></span> <span data-ttu-id="35128-117">После запуска портала все пользователи с разрешениями на сайт смогут получить доступ к новому сайту.</span><span class="sxs-lookup"><span data-stu-id="35128-117">At the end of the portal launch, all users with permissions to the site will be able to access the new site.</span></span> 

<span data-ttu-id="35128-118">Для получения дополнительных сведений о запуске успешного портала следуйте основным принципам, рекомендациям и рекомендациям, описанным в разделе [Создание, запуск и обслуживание работоспособного портала](https://docs.microsoft.com/sharepoint/portal-health).</span><span class="sxs-lookup"><span data-stu-id="35128-118">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in [Creating, launching and maintaining a healthy portal](https://docs.microsoft.com/sharepoint/portal-health).</span></span> 

> [!NOTE]
> <span data-ttu-id="35128-119">Эта функция недоступна для Office 365 Германия, Office 365 под управлением 21Vianet (Китай) или Microsoft 365 для государственных организаций США.</span><span class="sxs-lookup"><span data-stu-id="35128-119">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans.</span></span>

## <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="35128-120">Установка приложений и подключение к SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="35128-120">App setup and connecting to SharePoint Online</span></span>
1. <span data-ttu-id="35128-121">[Скачайте последнюю версию командной консоли SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="35128-121">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="35128-p104">Если вы установили предыдущую версию командной консоли SharePoint Online, перейдите к разделу "Установка и удаление программ" и удалите компонент "Командная консоль SharePoint Online". </span><span class="sxs-lookup"><span data-stu-id="35128-p104">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell." </span></span><br><span data-ttu-id="35128-123">На странице Центра загрузки выберите нужный язык и нажмите кнопку "Скачать".</span><span class="sxs-lookup"><span data-stu-id="35128-123">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="35128-124">Вам будет предложено скачать версию x64 или x86 файла MSI.</span><span class="sxs-lookup"><span data-stu-id="35128-124">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="35128-125">Для 64-разрядной версии Windows скачайте файл x64, а для 32-разрядной — файл x86.</span><span class="sxs-lookup"><span data-stu-id="35128-125">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="35128-126">Если вы не знаете свою разрядность, см. статью [Какая у меня версия операционной системы Windows?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span><span class="sxs-lookup"><span data-stu-id="35128-126">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="35128-127">После скачивания файла запустите его и следуйте инструкциям мастера настройки.</span><span class="sxs-lookup"><span data-stu-id="35128-127">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="35128-128">Подключите SharePoint, используя [права глобального администратора или администратора SharePoint](/sharepoint/sharepoint-admin-role) в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="35128-128">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="35128-129">Сведения о том, как это сделать, см. в статье [Начало работы с командной консолью SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="35128-129">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>


## <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="35128-130">Просмотр всех существующих настроек запуска портала</span><span class="sxs-lookup"><span data-stu-id="35128-130">View any existing portal launch setups</span></span>

<span data-ttu-id="35128-131">Чтобы проверить наличие существующих конфигураций запуска портала:</span><span class="sxs-lookup"><span data-stu-id="35128-131">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="35128-132">Планирование запуска портала на сайте</span><span class="sxs-lookup"><span data-stu-id="35128-132">Schedule a portal launch on the site</span></span>

<span data-ttu-id="35128-133">Количество требуемых волн зависит от предполагаемого размера запуска.</span><span class="sxs-lookup"><span data-stu-id="35128-133">The number of waves required depends on your expected launch size.</span></span> 
- <span data-ttu-id="35128-134">Менее 10 000 пользователей: 1 волна</span><span class="sxs-lookup"><span data-stu-id="35128-134">Less than 10k users: 1 wave</span></span>
- <span data-ttu-id="35128-135">10 000 к пользователям 30k: 3 волны</span><span class="sxs-lookup"><span data-stu-id="35128-135">10k to 30k users: 3 waves</span></span> 
- <span data-ttu-id="35128-136">30k + до 100 000 пользователей: 5 волн</span><span class="sxs-lookup"><span data-stu-id="35128-136">30k+ to 100k users: 5 waves</span></span>
- <span data-ttu-id="35128-137">Более 100 КБ пользователей: 5 волнах и обращение к группе учетных записей Майкрософт</span><span class="sxs-lookup"><span data-stu-id="35128-137">More than 100k users: 5 waves and contact your Microsoft account team</span></span>

### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="35128-138">Действия для перенаправления с двунаправленным письмом</span><span class="sxs-lookup"><span data-stu-id="35128-138">Steps for bidirectional redirection</span></span>

<span data-ttu-id="35128-139">Двунаправленное перенаправление включает в себя запуск нового современного портала SharePoint Online для замены существующего классического или современного портала SharePoint.</span><span class="sxs-lookup"><span data-stu-id="35128-139">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="35128-140">Пользователи в активных волнах будут перенаправляться на новый сайт независимо от того, переходить на старый или новый сайт.</span><span class="sxs-lookup"><span data-stu-id="35128-140">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="35128-141">Пользователи в незапущенной волне, который пытается получить доступ к новому сайту, будут перенаправлены на старый сайт, пока не будет запущена звуковая волна.</span><span class="sxs-lookup"><span data-stu-id="35128-141">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span> 

<span data-ttu-id="35128-142">Поддерживается перенаправление только между домашней страницей по умолчанию на старом сайте и домашней страницей по умолчанию на новом сайте.</span><span class="sxs-lookup"><span data-stu-id="35128-142">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="35128-143">Если у вас есть администраторы или владельцы, которым необходим доступ к старым и новым сайтам без перенаправления, убедитесь, что они указаны с помощью `WaveOverrideUsers` параметра.</span><span class="sxs-lookup"><span data-stu-id="35128-143">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span> <span data-ttu-id="35128-144">Если у вас есть администраторы или владельцы, которым необходим доступ к старым и новым сайтам без перенаправления, убедитесь, что они указаны с помощью `WaveOverrideUsers` параметра.</span><span class="sxs-lookup"><span data-stu-id="35128-144">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span> <span data-ttu-id="35128-145">Поддерживается перенаправление только между домашней страницей по умолчанию на старом сайте и домашней страницей по умолчанию на новом сайте.</span><span class="sxs-lookup"><span data-stu-id="35128-145">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span>

<span data-ttu-id="35128-146">Для поэтапной миграции пользователей с существующего сайта SharePoint на новый сайт SharePoint выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="35128-146">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="35128-147">Выполните следующую команду, чтобы назначить запускаемые волны портала.</span><span class="sxs-lookup"><span data-stu-id="35128-147">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="35128-148">Пример.</span><span class="sxs-lookup"><span data-stu-id="35128-148">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="35128-149">Выполнение проверки.</span><span class="sxs-lookup"><span data-stu-id="35128-149">Complete validation.</span></span> <span data-ttu-id="35128-150">Перенаправление для завершения настройки в службе может занять 5-10 минут.</span><span class="sxs-lookup"><span data-stu-id="35128-150">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="35128-151">Действия для перенаправления на временную страницу</span><span class="sxs-lookup"><span data-stu-id="35128-151">Steps for redirection to temporary page</span></span>

<span data-ttu-id="35128-152">Временное перенаправление страницы следует использовать, если существующий портал SharePoint не существует.</span><span class="sxs-lookup"><span data-stu-id="35128-152">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="35128-153">В поэтапной манере пользователи направлены на новый современный портал SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="35128-153">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="35128-154">Если пользователь находится в волне, который еще не запущен, он будет перенаправлен на временную страницу (любой URL-адрес).</span><span class="sxs-lookup"><span data-stu-id="35128-154">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span> 

1. <span data-ttu-id="35128-155">Выполните следующую команду, чтобы назначить запускаемые волны портала.</span><span class="sxs-lookup"><span data-stu-id="35128-155">Run the following command to designate portal launch waves.</span></span>
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="35128-156">Пример.</span><span class="sxs-lookup"><span data-stu-id="35128-156">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="35128-157">Выполнение проверки.</span><span class="sxs-lookup"><span data-stu-id="35128-157">Complete validation.</span></span> <span data-ttu-id="35128-158">Перенаправление для завершения настройки в службе может занять 5-10 минут.</span><span class="sxs-lookup"><span data-stu-id="35128-158">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="35128-159">Приостановка и перезапуск запуска портала на сайте</span><span class="sxs-lookup"><span data-stu-id="35128-159">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="35128-160">Чтобы приостановить запуск портала в ходе выполнения и временно предотвратить появление будущих поступающих в нее действий, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="35128-160">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. <span data-ttu-id="35128-161">Проверка того, что все пользователи перенаправляются на старый сайт.</span><span class="sxs-lookup"><span data-stu-id="35128-161">Validate that all users are redirected to the old site.</span></span> 

3. <span data-ttu-id="35128-162">Чтобы перезапустить приостановленный запуск портала, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="35128-162">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. <span data-ttu-id="35128-163">Проверка того, что перенаправление восстановлено.</span><span class="sxs-lookup"><span data-stu-id="35128-163">Validate that the redirection is now restored.</span></span> 

## <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="35128-164">Удаление запуска портала на сайте</span><span class="sxs-lookup"><span data-stu-id="35128-164">Delete a portal launch on the site</span></span>
1. <span data-ttu-id="35128-165">Создайте Звукозапись для запуска портала.</span><span class="sxs-lookup"><span data-stu-id="35128-165">Create a Portal launch Wave.</span></span>
  - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="35128-166">Выполните приведенную ниже команду, чтобы удалить запланированное или выполняемое для сайта время запуска портала.</span><span class="sxs-lookup"><span data-stu-id="35128-166">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

3. <span data-ttu-id="35128-167">Проверка того, что перенаправление не выполняется для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="35128-167">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="35128-168">Подробнее</span><span class="sxs-lookup"><span data-stu-id="35128-168">Learn more</span></span>
[<span data-ttu-id="35128-169">Планирование развертывания портала для запуска в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="35128-169">Planning your portal launch roll-out plan in SharePoint Online</span></span>](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)