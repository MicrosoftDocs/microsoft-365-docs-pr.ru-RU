---
title: Microsoft 365 Apps for enterprise
description: Развертывание Приложения Microsoft 365, их обновление и управление настройками
keywords: журнал изменений
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 7b1178312178865face58748a37228f60643d5fc
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287979"
---
# <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="a881b-104">Приложения Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="a881b-104">Microsoft 365 Apps for enterprise</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="a881b-105">Начальное развертывание</span><span class="sxs-lookup"><span data-stu-id="a881b-105">Initial deployment</span></span>

<span data-ttu-id="a881b-106">компьютеры, управляемые Майкрософт обеспечивает установку Приложения Microsoft 365 для предприятий (64-bit) в составе изображения на всех [устройствах программы.](../service-description/device-list.md)</span><span class="sxs-lookup"><span data-stu-id="a881b-106">Microsoft Managed Desktop ensures that Microsoft 365 Apps for enterprise (64-bit) are installed as a part of the image on all [program devices](../service-description/device-list.md).</span></span> <span data-ttu-id="a881b-107">Все следующие приложения должны присутствовать на устройстве при доставке:</span><span class="sxs-lookup"><span data-stu-id="a881b-107">All of the following applications should be present on the device when it's delivered:</span></span>

- <span data-ttu-id="a881b-108">Word</span><span class="sxs-lookup"><span data-stu-id="a881b-108">Word</span></span>
- <span data-ttu-id="a881b-109">Excel</span><span class="sxs-lookup"><span data-stu-id="a881b-109">Excel</span></span>
- <span data-ttu-id="a881b-110">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="a881b-110">PowerPoint</span></span>
- <span data-ttu-id="a881b-111">Outlook</span><span class="sxs-lookup"><span data-stu-id="a881b-111">Outlook</span></span>
- <span data-ttu-id="a881b-112">Publisher</span><span class="sxs-lookup"><span data-stu-id="a881b-112">Publisher</span></span>
- <span data-ttu-id="a881b-113">Доступ</span><span class="sxs-lookup"><span data-stu-id="a881b-113">Access</span></span>
- <span data-ttu-id="a881b-114">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a881b-114">Skype for Business</span></span>
- <span data-ttu-id="a881b-115">OneNote</span><span class="sxs-lookup"><span data-stu-id="a881b-115">OneNote</span></span>

<span data-ttu-id="a881b-116">Этот подход минимизирует влияние сети и гарантирует, что пользователи смогут работать продуктивно сразу после получения устройства.</span><span class="sxs-lookup"><span data-stu-id="a881b-116">This approach minimizes network impact and ensures that users can be productive as soon as they receive their device.</span></span> <span data-ttu-id="a881b-117">Затем мы развертываем дополнительные политики на управляемых устройствах, чтобы настроить приложения для использования.</span><span class="sxs-lookup"><span data-stu-id="a881b-117">We then deploy more policies to managed devices to set up the applications for use.</span></span>

> [!NOTE]
> <span data-ttu-id="a881b-118">Microsoft Teams развертывается отдельно от Приложения Microsoft 365 для предприятий и не входит в базовое изображение.</span><span class="sxs-lookup"><span data-stu-id="a881b-118">Microsoft Teams is deployed separately from Microsoft 365 Apps for enterprise and is not included in the base image.</span></span> 

### <a name="available-deployment-to-users"></a><span data-ttu-id="a881b-119">Доступное развертывание для пользователей</span><span class="sxs-lookup"><span data-stu-id="a881b-119">Available deployment to users</span></span>

<span data-ttu-id="a881b-120">Если у пользователя нет Приложения Microsoft 365 по какой-либо причине, вы можете использовать пакет, чтобы вернуть устройство в ожидаемое состояние.</span><span class="sxs-lookup"><span data-stu-id="a881b-120">If a user does not have Microsoft 365 Apps on their device for any reason, you can use a package to return the device to its expected state.</span></span> <span data-ttu-id="a881b-121">Добавьте пользователя в группу **Modern Workplace-Office-Office365_Install** и приложения станут доступны для них в Корпоративный портал.</span><span class="sxs-lookup"><span data-stu-id="a881b-121">Add the user to the **Modern Workplace-Office-Office365_Install** group and the apps will become available to them in the Company Portal.</span></span>

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a><span data-ttu-id="a881b-122">Приложения Microsoft 365 для предприятий (32-битный)</span><span class="sxs-lookup"><span data-stu-id="a881b-122">Microsoft 365 Apps for enterprise (32-bit)</span></span>

<span data-ttu-id="a881b-123">компьютеры, управляемые Майкрософт не поддерживает развертывание 32-битной версии M365 Apps для предприятия.</span><span class="sxs-lookup"><span data-stu-id="a881b-123">Microsoft Managed Desktop doesn't support the deployment of the 32-bit version of M365 Apps for enterprise.</span></span>

## <a name="updates-to-microsoft-365-apps"></a><span data-ttu-id="a881b-124">Обновления для Приложения Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a881b-124">Updates to Microsoft 365 Apps</span></span>

<span data-ttu-id="a881b-125">Приложения Microsoft 365 для обновления на канале [Monthly Enterprise.](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)</span><span class="sxs-lookup"><span data-stu-id="a881b-125">Microsoft 365 Apps are set to update on the [Monthly Enterprise Channel](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview).</span></span> <span data-ttu-id="a881b-126">Эта практика предоставляет пользователям новые Office каждый месяц, но они будут получать только одно обновление в месяц в предсказуемом графике выпуска.</span><span class="sxs-lookup"><span data-stu-id="a881b-126">This practice provides your users with new Office features each month, but they'll receive just one update per month on a predictable release schedule.</span></span> <span data-ttu-id="a881b-127">Обновления выпускаются во второй вторник месяца; эти обновления могут включать обновления функций, безопасности и качества.</span><span class="sxs-lookup"><span data-stu-id="a881b-127">Updates are released on the second Tuesday of the month; these updates can include feature, security, and quality updates.</span></span> <span data-ttu-id="a881b-128">Эти обновления происходят автоматически и извлекаются непосредственно из Office CDN для этого конкретного канала.</span><span class="sxs-lookup"><span data-stu-id="a881b-128">These updates occur automatically and are pulled directly from the Office CDN for that specific channel.</span></span>

<span data-ttu-id="a881b-129">компьютеры, управляемые Майкрософт каждый выпуск определяет потенциальные проблемы в среде.</span><span class="sxs-lookup"><span data-stu-id="a881b-129">Microsoft Managed Desktop staggers each release to identify any potential issues in your environment.</span></span> <span data-ttu-id="a881b-130">Мы завершаем выкатку через 28 дней после выпуска из группы Microsoft 365 приложений.</span><span class="sxs-lookup"><span data-stu-id="a881b-130">We complete the rollout 28 days after the release from the Microsoft 365 App product group.</span></span> <span data-ttu-id="a881b-131">компьютеры, управляемые Майкрософт выпуски обновлений для разных групп, чтобы дать время для проверки и тестирования следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a881b-131">Microsoft Managed Desktop schedules update releases to different groups to allow time for validation and testing as follows:</span></span> 

- <span data-ttu-id="a881b-132">Тест: ноль дней</span><span class="sxs-lookup"><span data-stu-id="a881b-132">Test: zero days</span></span>
- <span data-ttu-id="a881b-133">Первый: ноль дней</span><span class="sxs-lookup"><span data-stu-id="a881b-133">First: zero days</span></span>
- <span data-ttu-id="a881b-134">Быстрый: 3 дня</span><span class="sxs-lookup"><span data-stu-id="a881b-134">Fast: 3 days</span></span>
- <span data-ttu-id="a881b-135">Broad: 7 дней</span><span class="sxs-lookup"><span data-stu-id="a881b-135">Broad: 7 days</span></span>

<span data-ttu-id="a881b-136">компьютеры, управляемые Майкрософт устанавливает семидневный срок [обновления](/deployoffice/configure-update-settings-microsoft-365-apps) для устройств.</span><span class="sxs-lookup"><span data-stu-id="a881b-136">Microsoft Managed Desktop sets a seven-day [update deadline](/deployoffice/configure-update-settings-microsoft-365-apps) for devices.</span></span> <span data-ttu-id="a881b-137">После того как обновление доступно, оно должно быть установлено в течение семи дней.</span><span class="sxs-lookup"><span data-stu-id="a881b-137">Once the update is available, it must be installed within seven days.</span></span> <span data-ttu-id="a881b-138">Пользователи получают [уведомления](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) о том, что обновления требуются в нескольких расположениях: приложении в подносе системы за 12 часов до крайнего срока, и они получают предупреждение за 15 минут до крайнего срока.</span><span class="sxs-lookup"><span data-stu-id="a881b-138">Users are [notified](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) that updates are required in several locations: the application, in the system tray 12 hours prior to the deadline, and they receive a 15-minute warning prior to the deadline.</span></span> <span data-ttu-id="a881b-139">Все Приложения Microsoft 365 должны быть закрыты для завершения обновления.</span><span class="sxs-lookup"><span data-stu-id="a881b-139">All Microsoft 365 Apps must be closed for the update to complete.</span></span>

### <a name="pausing-or-rolling-back-an-update"></a><span data-ttu-id="a881b-140">Прио пауза или откат обновления</span><span class="sxs-lookup"><span data-stu-id="a881b-140">Pausing or rolling back an update</span></span>

<span data-ttu-id="a881b-141">Если по какой-либо причине необходимо приостановить или откат [](../working-with-managed-desktop/admin-support.md) Microsoft 365 обновления приложения, задай запрос на поддержку администратора на компьютеры, управляемые Майкрософт портале.</span><span class="sxs-lookup"><span data-stu-id="a881b-141">If you need to pause or roll back Microsoft 365 App update for any reason, file an [admin support request](../working-with-managed-desktop/admin-support.md) through the Microsoft Managed Desktop portal.</span></span>

<span data-ttu-id="a881b-142">Во время выпуска компьютеры, управляемые Майкрософт отслеживает показатели ошибок всех Приложения Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a881b-142">During a release, Microsoft Managed Desktop monitors the error rates of all Microsoft 365 Apps.</span></span> <span data-ttu-id="a881b-143">Если мы заметим существенную разницу в качестве между новым выпуском и его предшественником, мы можем связаться с вами через портал администрирования компьютеры, управляемые Майкрософт администратора.</span><span class="sxs-lookup"><span data-stu-id="a881b-143">If we note a significant difference in quality between the new release and its predecessor, we might contact you through the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="a881b-144">В зависимости от серьезности, мы будем спрашивать, хотите ли вы приостановить выпуск или сообщить вам, что мы приняли меры для смягчения проблемы.</span><span class="sxs-lookup"><span data-stu-id="a881b-144">Depending on the severity, we will either ask if you want to pause the release or inform you that we have taken action to mitigate an issue.</span></span> 

### <a name="delivery-optimization"></a><span data-ttu-id="a881b-145">Оптимизация доставки</span><span class="sxs-lookup"><span data-stu-id="a881b-145">Delivery optimization</span></span>

<span data-ttu-id="a881b-146">Оптимизация доставки — это одноранговая технология распространения, доступная в Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a881b-146">Delivery Optimization is a peer-to-peer distribution technology available in Windows 10.</span></span> <span data-ttu-id="a881b-147">Это позволяет устройствам обмениваться контентом, например обновлениями, которые устройства скачали из Microsoft через Интернет.</span><span class="sxs-lookup"><span data-stu-id="a881b-147">It allows devices to share content, such as updates, that the devices have downloaded from Microsoft over the internet.</span></span> <span data-ttu-id="a881b-148">С его помощью можно уменьшить пропускную способность сети, так как устройство может получать части обновления с другого устройства в локальной сети вместо того, чтобы полностью скачать обновление из Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a881b-148">Using it can help reduce network bandwidth because a device can get portions of the update from another device on its local network instead of having to download the update completely from Microsoft.</span></span>

<span data-ttu-id="a881b-149">[Оптимизация доставки](/deployoffice/delivery-optimization) включена по умолчанию на устройствах с Windows 10 Корпоративная или Windows 10 для образовательных учреждений выпусками.</span><span class="sxs-lookup"><span data-stu-id="a881b-149">[Delivery Optimization](/deployoffice/delivery-optimization) is enabled by default on devices running the Windows 10 Enterprise or Windows 10 Education editions.</span></span> 

## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="a881b-150">Параметры управляется компьютеры, управляемые Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a881b-150">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="a881b-151">Корпорация Майкрософт управляет некоторыми настройками в рамках службы.</span><span class="sxs-lookup"><span data-stu-id="a881b-151">Microsoft manages some settings as a part of the service.</span></span> <span data-ttu-id="a881b-152">компьютеры, управляемые Майкрософт не управляет базовым Office безопасности, но вы можете установить его самостоятельно, следуя указаниям в разделе Параметры [управления.](#settings-you-manage)</span><span class="sxs-lookup"><span data-stu-id="a881b-152">Microsoft Managed Desktop doesn't manage an Office Security baseline but you can set one yourself by following the guidance in the [Settings you manage](#settings-you-manage) section.</span></span>

### <a name="update-settings"></a><span data-ttu-id="a881b-153">Обновление параметров</span><span class="sxs-lookup"><span data-stu-id="a881b-153">Update settings</span></span>

<span data-ttu-id="a881b-154">компьютеры, управляемые Майкрософт поддерживает все параметры [обновления](/deployoffice/configure-update-settings-microsoft-365-apps) для управляемых устройств, и эти параметры следует изменить.</span><span class="sxs-lookup"><span data-stu-id="a881b-154">Microsoft Managed Desktop maintains all [update settings](/deployoffice/configure-update-settings-microsoft-365-apps) for managed devices and you should modify these settings.</span></span>

### <a name="set-updates-to-occur-automatically"></a><span data-ttu-id="a881b-155">Настроить автоматические обновления</span><span class="sxs-lookup"><span data-stu-id="a881b-155">Set updates to occur automatically</span></span>

<span data-ttu-id="a881b-156">**Значение по умолчанию:** включено</span><span class="sxs-lookup"><span data-stu-id="a881b-156">**Default value**: Enabled</span></span>

<span data-ttu-id="a881b-157">Эта политика настроена для обеспечения того, чтобы все Office устройства могли быть в курсе облачных технологий.</span><span class="sxs-lookup"><span data-stu-id="a881b-157">This policy is configured in order to ensure that all Office devices can be kept up to date from the cloud.</span></span> 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a><span data-ttu-id="a881b-158">Установите крайний срок, когда необходимо применять обновления</span><span class="sxs-lookup"><span data-stu-id="a881b-158">Set a deadline when updates have to be applied</span></span>

<span data-ttu-id="a881b-159">**Значение по умолчанию:** 7 дней</span><span class="sxs-lookup"><span data-stu-id="a881b-159">**Default value**: 7 days</span></span>

<span data-ttu-id="a881b-160">Политика **UpdateDeadline** используется для настройки льготного периода, который пользователи имеют до принудительного обновления на устройстве.</span><span class="sxs-lookup"><span data-stu-id="a881b-160">The **UpdateDeadline** policy is used to configure the grace period which users have before an update is enforced on the device.</span></span> <span data-ttu-id="a881b-161">Эта политика крайних сроков также вызывает [уведомления](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) для пользователя, чтобы сообщить им об изменениях, необходимых на их устройстве.</span><span class="sxs-lookup"><span data-stu-id="a881b-161">This deadline policy also triggers [notifications](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) to the user to inform them of the changes required on their device.</span></span>  

### <a name="defer-updates-on-a-device-for-a-period"></a><span data-ttu-id="a881b-162">Отсрочка обновлений на устройстве на период</span><span class="sxs-lookup"><span data-stu-id="a881b-162">Defer updates on a device for a period</span></span>

<span data-ttu-id="a881b-163">Эта политика настраивается по-разному для каждой группы устройств управления обновлениями и требуется для компьютеры, управляемые Майкрософт для удовлетворения целей обновления:</span><span class="sxs-lookup"><span data-stu-id="a881b-163">This policy is configured differently for each update management device group and is required for Microsoft Managed Desktop to meet its update targets:</span></span>  

- <span data-ttu-id="a881b-164">Тест: ноль дней</span><span class="sxs-lookup"><span data-stu-id="a881b-164">Test: zero days</span></span>
- <span data-ttu-id="a881b-165">Первый: ноль дней</span><span class="sxs-lookup"><span data-stu-id="a881b-165">First: zero days</span></span>
- <span data-ttu-id="a881b-166">Быстрый 7 дней</span><span class="sxs-lookup"><span data-stu-id="a881b-166">Fast 7 days</span></span>
- <span data-ttu-id="a881b-167">Broad: 21 дней</span><span class="sxs-lookup"><span data-stu-id="a881b-167">Broad: 21 days</span></span>

### <a name="update-notifications-settings"></a><span data-ttu-id="a881b-168">Обновление параметров уведомлений</span><span class="sxs-lookup"><span data-stu-id="a881b-168">Update notifications settings</span></span>

<span data-ttu-id="a881b-169">**Значение по умолчанию:** False</span><span class="sxs-lookup"><span data-stu-id="a881b-169">**Default value**: False</span></span>

<span data-ttu-id="a881b-170">Параметр "скрыть уведомления об обновлении" задается **параметру False** на компьютеры, управляемые Майкрософт устройствах, чтобы предоставить пользователям наилучшие сведения об обновлении, уведомив их о необходимости обновления. [](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps)</span><span class="sxs-lookup"><span data-stu-id="a881b-170">The "hide update notifications" setting is set to **False** on Microsoft Managed Desktop devices to provide the best update experience for users by [notifying](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) them when updates are required.</span></span>

### <a name="specify-a-location-to-look-for-updates"></a><span data-ttu-id="a881b-171">Указать расположение для поиска обновлений</span><span class="sxs-lookup"><span data-stu-id="a881b-171">Specify a location to look for updates</span></span>

<span data-ttu-id="a881b-172">**Значение по умолчанию:** ежемесячный Enterprise канал</span><span class="sxs-lookup"><span data-stu-id="a881b-172">**Default value**: Monthly Enterprise Channel</span></span>

<span data-ttu-id="a881b-173">Сочетание политик **UpdatePath** и **UpdateChannel** используется по мере необходимости для достижения расписания обновлений.</span><span class="sxs-lookup"><span data-stu-id="a881b-173">A combination of the **UpdatePath** and **UpdateChannel** policies is used as needed to achieve the update schedule.</span></span> <span data-ttu-id="a881b-174">Эти политики должны гарантировать, что все Office устройства получают обновления непосредственно из CDN для ежемесячного Enterprise Channel.</span><span class="sxs-lookup"><span data-stu-id="a881b-174">These policies are set to ensure that all Office devices receive updates directly from the CDN for the Monthly Enterprise Channel.</span></span>

### <a name="specify-the-target-version-of-microsoft-365-apps"></a><span data-ttu-id="a881b-175">Укажите целевую версию Приложения Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a881b-175">Specify the Target Version of Microsoft 365 Apps</span></span>

<span data-ttu-id="a881b-176">Политика target Version иногда используется компьютеры, управляемые Майкрософт для отката или закрепления определенной версии Office.</span><span class="sxs-lookup"><span data-stu-id="a881b-176">The Target Version policy is sometimes used by Microsoft Managed Desktop in order to roll back or pin a specific version of Office.</span></span> 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a><span data-ttu-id="a881b-177">Скрыть параметр, чтобы включить или отключить Office автоматические обновления</span><span class="sxs-lookup"><span data-stu-id="a881b-177">Hide the option to enable or disable Office automatic updates</span></span>

<span data-ttu-id="a881b-178">**Значение по умолчанию:** включено</span><span class="sxs-lookup"><span data-stu-id="a881b-178">**Default value**: Enabled</span></span>

<span data-ttu-id="a881b-179">Этот параметр необходим для компьютеры, управляемые Майкрософт для удовлетворения целей обновления для Microsoft 365 приложений.</span><span class="sxs-lookup"><span data-stu-id="a881b-179">This setting is required for Microsoft Managed Desktop to meet its update targets for Microsoft 365 Applications.</span></span> 

### <a name="first-run-settings"></a><span data-ttu-id="a881b-180">Параметры первого запуска</span><span class="sxs-lookup"><span data-stu-id="a881b-180">First run settings</span></span> 

<span data-ttu-id="a881b-181">Существует несколько параметров, влияющих на поведение при первом Office запуска.</span><span class="sxs-lookup"><span data-stu-id="a881b-181">There are several settings that affect the behavior the first time Office is run.</span></span>

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a><span data-ttu-id="a881b-182">Принятие условий лицензии от имени конечного пользователя</span><span class="sxs-lookup"><span data-stu-id="a881b-182">Accept the license terms on behalf of the end user</span></span>

<span data-ttu-id="a881b-183">**Значение по умолчанию:** отключено</span><span class="sxs-lookup"><span data-stu-id="a881b-183">**Default value**: Disabled</span></span>

<span data-ttu-id="a881b-184">При первом открываемом приложении Microsoft 365 пользователю будет предложено принять условия лицензии.</span><span class="sxs-lookup"><span data-stu-id="a881b-184">The first time a user opens a Microsoft 365 App, they are prompted to accept the license terms.</span></span> <span data-ttu-id="a881b-185">Если вы хотите принять условия лицензии от имени пользователей, подайте запрос на обслуживание в команду компьютеры, управляемые Майкрософт operations с просьбой включить этот параметр.</span><span class="sxs-lookup"><span data-stu-id="a881b-185">If you want to accept the license terms on behalf of your users, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

### <a name="suppress-outlook-mobile-check-box"></a><span data-ttu-id="a881b-186">Подавление Outlook мобильного окна</span><span class="sxs-lookup"><span data-stu-id="a881b-186">Suppress Outlook mobile check box</span></span>

<span data-ttu-id="a881b-187">**Значение по умолчанию:** отключено</span><span class="sxs-lookup"><span data-stu-id="a881b-187">**Default value**: Disabled</span></span>

<span data-ttu-id="a881b-188">При первом открываемом Outlook пользователю будет предложено установить Outlook Mobile.</span><span class="sxs-lookup"><span data-stu-id="a881b-188">The first time a user opens Outlook they are prompted to install Outlook Mobile.</span></span> <span data-ttu-id="a881b-189">Если вы не хотите, чтобы пользователи видели этот контрольный ящик, отдайте запрос на обслуживание группе компьютеры, управляемые Майкрософт операций с просьбой включить этот параметр для устройств.</span><span class="sxs-lookup"><span data-stu-id="a881b-189">If you don’t want your users to see that check box, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled for your devices.</span></span> 

## <a name="other-settings"></a><span data-ttu-id="a881b-190">Другие параметры</span><span class="sxs-lookup"><span data-stu-id="a881b-190">Other settings</span></span>

<span data-ttu-id="a881b-191">Есть другие параметры Microsoft 365, которые компьютеры, управляемые Майкрософт можно дополнительно настроить от вашего имени.</span><span class="sxs-lookup"><span data-stu-id="a881b-191">There are other Microsoft 365 App settings which Microsoft Managed Desktop can optionally configure on your behalf.</span></span> 

### <a name="disable-personal-onedrive"></a><span data-ttu-id="a881b-192">Отключение персональных OneDrive</span><span class="sxs-lookup"><span data-stu-id="a881b-192">Disable Personal OneDrive</span></span>

<span data-ttu-id="a881b-193">**Значение по умолчанию:** отключено</span><span class="sxs-lookup"><span data-stu-id="a881b-193">**Default value**: Disabled</span></span>

<span data-ttu-id="a881b-194">Некоторые организации обеспокоены тем, что пользователи имеют доступ как к корпоративным, так и к личным файлам на своих устройствах.</span><span class="sxs-lookup"><span data-stu-id="a881b-194">Some organizations are concerned about users having access to both corporate and personal files on their devices.</span></span> <span data-ttu-id="a881b-195">Вы можете подать запрос на службу в компьютеры, управляемые Майкрософт operations с просьбой включить этот параметр.</span><span class="sxs-lookup"><span data-stu-id="a881b-195">You can file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

## <a name="settings-you-manage"></a><span data-ttu-id="a881b-196">Параметры управлять</span><span class="sxs-lookup"><span data-stu-id="a881b-196">Settings you manage</span></span>

<span data-ttu-id="a881b-197">Существует множество других политик, которые компьютеры, управляемые Майкрософт еще не установлены в качестве части нашей службы.</span><span class="sxs-lookup"><span data-stu-id="a881b-197">There are many other policies which Microsoft Managed Desktop does not yet set as a part of our service.</span></span> <span data-ttu-id="a881b-198">Эти политики можно настроить с помощью Microsoft Intune, которая использует [службу Office облачной](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) политики.</span><span class="sxs-lookup"><span data-stu-id="a881b-198">You can configure these policies by using Microsoft Intune, which uses the [Office Cloud Policy](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) service.</span></span> <span data-ttu-id="a881b-199">Чтобы установить эти политики, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a881b-199">To set these policies, follow these steps:</span></span>

1. <span data-ttu-id="a881b-200">Во входе в Microsoft Endpoint Manager центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="a881b-200">Sign in to the Microsoft Endpoint Manager admin center.</span></span>
2. <span data-ttu-id="a881b-201">Выбор **политик > приложений для Office приложений > Create**</span><span class="sxs-lookup"><span data-stu-id="a881b-201">Select **Apps > Policies for Office apps > Create**</span></span>
3. <span data-ttu-id="a881b-202">На странице **Создание конфигурации** политики сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="a881b-202">On the **Create policy** configuration page, do the following:</span></span>
    - <span data-ttu-id="a881b-203">Введите имя.</span><span class="sxs-lookup"><span data-stu-id="a881b-203">Enter a name.</span></span>
    - <span data-ttu-id="a881b-204">Предоставление описания (необязательно).</span><span class="sxs-lookup"><span data-stu-id="a881b-204">Provide a description (optional).</span></span>
    - <span data-ttu-id="a881b-205">В **заданиях** выберите, применима ли эта политика ко всем пользователям Приложения Microsoft 365 для предприятий или просто к пользователям, которые анонимно используют Office для Интернета.</span><span class="sxs-lookup"><span data-stu-id="a881b-205">In **assignments**, choose whether this policy applies to all users of Microsoft 365 Apps for enterprise, or just to users who anonymously access documents using Office for the web.</span></span>
    - <span data-ttu-id="a881b-206">Выберите группу безопасности на основе AAD, назначенную конфигурации политики.</span><span class="sxs-lookup"><span data-stu-id="a881b-206">Select the AAD-based security group that is assigned to the policy configuration.</span></span> <span data-ttu-id="a881b-207">Каждая конфигурация политик может быть назначена только одной группе, а каждой группе может быть назначена только одна конфигурация политики.</span><span class="sxs-lookup"><span data-stu-id="a881b-207">Each policy configuration can only be assigned to one group, and each group can only be assigned one policy configuration.</span></span>
    - <span data-ttu-id="a881b-208">Настройка параметров политики, которые будут включены в конфигурацию политики.</span><span class="sxs-lookup"><span data-stu-id="a881b-208">Configure the policy settings to be included in the policy configuration.</span></span> <span data-ttu-id="a881b-209">Вы можете найти имя параметра политики, чтобы найти параметр политики, который необходимо настроить.</span><span class="sxs-lookup"><span data-stu-id="a881b-209">You can search on the policy setting name to find the policy setting that you want to configure.</span></span> <span data-ttu-id="a881b-210">Вы также можете фильтровать приложение, является ли политика рекомендуемой базой безопасности и настроена ли политика.</span><span class="sxs-lookup"><span data-stu-id="a881b-210">You can also filter on the application, on whether the policy is a recommended security baseline, and on whether the policy has been configured.</span></span> <span data-ttu-id="a881b-211">Столбец платформы указывает, применяется ли политика к Приложения Microsoft 365 для предприятий для Windows, Office для Интернета или всех.</span><span class="sxs-lookup"><span data-stu-id="a881b-211">The platform column indicates whether the policy is applied to Microsoft 365 Apps for enterprise for Windows devices, Office for the web, or all.</span></span>
4. <span data-ttu-id="a881b-212">После выбора выберите **Create**.</span><span class="sxs-lookup"><span data-stu-id="a881b-212">After you have made your selections, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="a881b-213">Office Политики конфигурации поддерживают развертывание только на основе пользователя</span><span class="sxs-lookup"><span data-stu-id="a881b-213">Office Configuration Policies only support user-based deployment</span></span>
