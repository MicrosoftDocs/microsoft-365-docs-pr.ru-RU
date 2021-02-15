---
title: Запуск портала с помощью планивщика запуска портала
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
description: В этой статье описывается, как можно запустить портал с помощью планивщика запуска портала
ms.openlocfilehash: 66912f5730c580bd75282a64124fefcdf262d738
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2021
ms.locfileid: "49864880"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="168bf-103">Запуск портала с помощью планивщика запуска портала</span><span class="sxs-lookup"><span data-stu-id="168bf-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="168bf-104">Портал — это сайт SharePoint в вашей интрасети, у которого есть большое количество посетителей сайта, использующих его содержимое.</span><span class="sxs-lookup"><span data-stu-id="168bf-104">A portal is a SharePoint site on your intranet that has a large number of site viewers who consume content on the site.</span></span> <span data-ttu-id="168bf-105">Запуск портала волнами является важной частью обеспечения у пользователей плавного и емких способов доступа к новому порталу SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="168bf-105">Launching your portal in waves is an important part of ensuring users have a smooth and performant experience accessing a new SharePoint Online portal.</span></span> 

<span data-ttu-id="168bf-106">Запуск в волны — это ключевой способ выкатить портал, как описано в планировании плана запуска портала в [SharePoint Online.](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="168bf-106">Launching in waves is a key way to roll-out your portal, as detailed in [Planning your portal launch roll-out plan in SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span></span> <span data-ttu-id="168bf-107">Планер запуска портала предназначен для того, чтобы помочь вам следовать подходу к поэтапному или волновому выпуску, управляя перенаправлениями для нового портала.</span><span class="sxs-lookup"><span data-stu-id="168bf-107">The Portal Launch Scheduler is designed to help you follow a wave / phased roll-out approach by managing the redirects for the new portal.</span></span> <span data-ttu-id="168bf-108">Во время каждой волны можно собирать отзывы пользователей и отслеживать производительность во время каждой волны развертывания.</span><span class="sxs-lookup"><span data-stu-id="168bf-108">During each of the waves, you can gather user feedback and monitor performance during each wave of deployment.</span></span> <span data-ttu-id="168bf-109">Преимущество этого заключается в том, что вы постепенно вводите портал, даете возможность приостановить и устранить проблемы перед тем, как двигаться к следующей волне, и в конечном итоге обеспечить положительное впечатление для пользователей.</span><span class="sxs-lookup"><span data-stu-id="168bf-109">This has the advantage of slowly introducing the portal, giving you the option to pause and resolve issues before proceeding with the next wave, and ultimately ensuring a positive experience for your users.</span></span> 

<span data-ttu-id="168bf-110">Существует два типа перенаправления:</span><span class="sxs-lookup"><span data-stu-id="168bf-110">There are two types of redirection:</span></span> 
- <span data-ttu-id="168bf-111">двухнаправленный запуск нового современного портала SharePoint Online для замены существующего классического или современного портала SharePoint</span><span class="sxs-lookup"><span data-stu-id="168bf-111">bidirectional: launch a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal</span></span> 
- <span data-ttu-id="168bf-112">перенаправление временных страниц: запуск нового современного портала SharePoint Online без существующего портала SharePoint</span><span class="sxs-lookup"><span data-stu-id="168bf-112">temporary page redirection: launch a new modern SharePoint Online portal with no existing SharePoint portal</span></span>

<span data-ttu-id="168bf-113">Планировать запуск портала можно только для запуска современных порталов SharePoint Online (то есть информационных сайтов).</span><span class="sxs-lookup"><span data-stu-id="168bf-113">The portal launch scheduler is only available to launch modern SharePoint Online portals (i.e. communication sites).</span></span> <span data-ttu-id="168bf-114">Запуски должны быть запланированы по крайней мере за 7 дней до этого.</span><span class="sxs-lookup"><span data-stu-id="168bf-114">Launches must be scheduled at least 7 days in advance.</span></span> <span data-ttu-id="168bf-115">Требуемая частота волн определяется ожидаемым количеством пользователей.</span><span class="sxs-lookup"><span data-stu-id="168bf-115">The number of waves required is determined by the expected number of users.</span></span> <span data-ttu-id="168bf-116">Перед планированием запуска портала необходимо запустить средство диагностики страниц [Для SharePoint,](https://aka.ms/perftool) чтобы убедиться, что домашняя страница на портале работает.</span><span class="sxs-lookup"><span data-stu-id="168bf-116">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) must be run to verify that the home page on the portal is healthy.</span></span> <span data-ttu-id="168bf-117">После запуска портала все пользователи с разрешениями на доступ к сайту смогут получить доступ к новому сайту.</span><span class="sxs-lookup"><span data-stu-id="168bf-117">At the end of the portal launch, all users with permissions to the site will be able to access the new site.</span></span> 

<span data-ttu-id="168bf-118">Для получения дополнительных сведений об успешном запуске портала следуйте базовым принципам, рекомендациям и рекомендациям, подробно описанным в этой теме. [](https://docs.microsoft.com/sharepoint/portal-health)</span><span class="sxs-lookup"><span data-stu-id="168bf-118">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in [Creating, launching and maintaining a healthy portal](https://docs.microsoft.com/sharepoint/portal-health).</span></span> 

> [!NOTE]
> <span data-ttu-id="168bf-119">Эта функция недоступна для планов Office 365 Germany, Office 365 под управлением 21Vianet (Китай) или Microsoft 365 для государственных органов США.</span><span class="sxs-lookup"><span data-stu-id="168bf-119">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans.</span></span>

## <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="168bf-120">Настройка приложения и подключение к SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="168bf-120">App setup and connecting to SharePoint Online</span></span>
1. <span data-ttu-id="168bf-121">[Скачайте последнюю версию командной консоли SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="168bf-121">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="168bf-p104">Если вы установили предыдущую версию командной консоли SharePoint Online, перейдите к разделу "Установка и удаление программ" и удалите компонент "Командная консоль SharePoint Online".</span><span class="sxs-lookup"><span data-stu-id="168bf-p104">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell." </span></span><br><span data-ttu-id="168bf-123">На странице Центра загрузки выберите нужный язык и нажмите кнопку "Скачать".</span><span class="sxs-lookup"><span data-stu-id="168bf-123">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="168bf-124">Вам будет предложено скачать версию x64 или x86 файла MSI.</span><span class="sxs-lookup"><span data-stu-id="168bf-124">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="168bf-125">Для 64-разрядной версии Windows скачайте файл x64, а для 32-разрядной — файл x86.</span><span class="sxs-lookup"><span data-stu-id="168bf-125">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="168bf-126">Если вы не знаете свою разрядность, см. статью [Какая у меня версия операционной системы Windows?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span><span class="sxs-lookup"><span data-stu-id="168bf-126">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="168bf-127">После скачивания файла запустите его и следуйте инструкциям мастера настройки.</span><span class="sxs-lookup"><span data-stu-id="168bf-127">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="168bf-128">Подключите SharePoint, используя [права глобального администратора или администратора SharePoint](/sharepoint/sharepoint-admin-role) в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="168bf-128">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="168bf-129">Сведения о том, как это сделать, см. в статье [Начало работы с командной консолью SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="168bf-129">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>


## <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="168bf-130">Просмотр существующих настроек запуска портала</span><span class="sxs-lookup"><span data-stu-id="168bf-130">View any existing portal launch setups</span></span>

<span data-ttu-id="168bf-131">Чтобы узнать, существуют ли конфигурации запуска портала:</span><span class="sxs-lookup"><span data-stu-id="168bf-131">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="168bf-132">Запланировать запуск портала на сайте</span><span class="sxs-lookup"><span data-stu-id="168bf-132">Schedule a portal launch on the site</span></span>

<span data-ttu-id="168bf-133">Необходимое количество волн зависит от ожидаемого размера запуска.</span><span class="sxs-lookup"><span data-stu-id="168bf-133">The number of waves required depends on your expected launch size.</span></span> 
- <span data-ttu-id="168bf-134">Менее 10 000 пользователей: 1 волна</span><span class="sxs-lookup"><span data-stu-id="168bf-134">Less than 10k users: 1 wave</span></span>
- <span data-ttu-id="168bf-135">От 10 до 30 000 пользователей: 3 волны</span><span class="sxs-lookup"><span data-stu-id="168bf-135">10k to 30k users: 3 waves</span></span> 
- <span data-ttu-id="168bf-136">От 30 000 до 100 000 пользователей: 5 волн</span><span class="sxs-lookup"><span data-stu-id="168bf-136">30k+ to 100k users: 5 waves</span></span>
- <span data-ttu-id="168bf-137">Более 100 000 пользователей: 5 волн и свяжитесь со своей командой учетных записей Майкрософт</span><span class="sxs-lookup"><span data-stu-id="168bf-137">More than 100k users: 5 waves and contact your Microsoft account team</span></span>

### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="168bf-138">Действия по перенаправлению междунаправлениями</span><span class="sxs-lookup"><span data-stu-id="168bf-138">Steps for bidirectional redirection</span></span>

<span data-ttu-id="168bf-139">Двухнаправленное перенаправление включает запуск нового современного портала SharePoint Online для замены существующего классического или современного портала SharePoint.</span><span class="sxs-lookup"><span data-stu-id="168bf-139">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="168bf-140">Пользователи в активных волнах будут перенаправлены на новый сайт независимо от того, переходят ли они на старый или новый сайт.</span><span class="sxs-lookup"><span data-stu-id="168bf-140">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="168bf-141">Пользователи в не запускаемой волне, которые пытаются получить доступ к новому сайту, будут перенаправлены обратно на старый сайт, пока их волны не будут запущены.</span><span class="sxs-lookup"><span data-stu-id="168bf-141">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span> 

<span data-ttu-id="168bf-142">Мы поддерживаем только перенаправление между домашней страницей по умолчанию на старом сайте и домашней страницей по умолчанию на новом сайте.</span><span class="sxs-lookup"><span data-stu-id="168bf-142">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="168bf-143">Если у вас есть администраторы или владельцы, которые нуждаются в доступе к старым и новым сайтам без перенаправления, убедитесь, что они указаны с помощью `WaveOverrideUsers` параметра.</span><span class="sxs-lookup"><span data-stu-id="168bf-143">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span>

<span data-ttu-id="168bf-144">Поэтапное перенос пользователей с существующего сайта SharePoint на новый сайт SharePoint:</span><span class="sxs-lookup"><span data-stu-id="168bf-144">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="168bf-145">Чтобы назначить волны запуска портала, запустите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="168bf-145">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="168bf-146">Пример.</span><span class="sxs-lookup"><span data-stu-id="168bf-146">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="168bf-147">Полная проверка.</span><span class="sxs-lookup"><span data-stu-id="168bf-147">Complete validation.</span></span> <span data-ttu-id="168bf-148">Настройка перенаправления в службе может занять от 5 до 10 минут.</span><span class="sxs-lookup"><span data-stu-id="168bf-148">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="168bf-149">Действия для перенаправления на временную страницу</span><span class="sxs-lookup"><span data-stu-id="168bf-149">Steps for redirection to temporary page</span></span>

<span data-ttu-id="168bf-150">Если портал SharePoint не существует, следует использовать временное перенаправление страниц.</span><span class="sxs-lookup"><span data-stu-id="168bf-150">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="168bf-151">Пользователи поэтапно направляются на новый современный портал SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="168bf-151">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="168bf-152">Если пользователь находится в волне, которая не была запущена, он будет перенаправлен на временную страницу (любой URL-адрес).</span><span class="sxs-lookup"><span data-stu-id="168bf-152">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span> 

1. <span data-ttu-id="168bf-153">Чтобы назначить волны запуска портала, запустите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="168bf-153">Run the following command to designate portal launch waves.</span></span>
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="168bf-154">Пример.</span><span class="sxs-lookup"><span data-stu-id="168bf-154">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="168bf-155">Полная проверка.</span><span class="sxs-lookup"><span data-stu-id="168bf-155">Complete validation.</span></span> <span data-ttu-id="168bf-156">Настройка перенаправления в службе может занять от 5 до 10 минут.</span><span class="sxs-lookup"><span data-stu-id="168bf-156">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="168bf-157">Приостановка или перезапуск запуска портала на сайте</span><span class="sxs-lookup"><span data-stu-id="168bf-157">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="168bf-158">Чтобы приостановить запуск портала и временно запретить переходы на новую волну, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="168bf-158">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. <span data-ttu-id="168bf-159">Проверьте перенаправление всех пользователей на старый сайт.</span><span class="sxs-lookup"><span data-stu-id="168bf-159">Validate that all users are redirected to the old site.</span></span> 

3. <span data-ttu-id="168bf-160">Чтобы перезапустить приостановленный запуск портала, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="168bf-160">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. <span data-ttu-id="168bf-161">Проверьте, восстановлено ли перенаправление.</span><span class="sxs-lookup"><span data-stu-id="168bf-161">Validate that the redirection is now restored.</span></span> 

## <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="168bf-162">Удаление запуска портала на сайте</span><span class="sxs-lookup"><span data-stu-id="168bf-162">Delete a portal launch on the site</span></span>

1. <span data-ttu-id="168bf-163">Чтобы удалить запланированный или запущенный портал для сайта, запустите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="168bf-163">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="168bf-164">Проверьте, не происходит ли перенаправление для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="168bf-164">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="168bf-165">Подробнее</span><span class="sxs-lookup"><span data-stu-id="168bf-165">Learn more</span></span>
[<span data-ttu-id="168bf-166">Планирование плана запуска портала в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="168bf-166">Planning your portal launch roll-out plan in SharePoint Online</span></span>](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
