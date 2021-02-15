---
title: Microsoft 365 Apps for enterprise
description: Развертывание приложений Microsoft 365, их обновление и управление настройками
keywords: журнал изменений
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 98995084fb7de9ecb434b70b5d38793a20675f19
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840353"
---
# <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="b89b5-104">Приложения Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="b89b5-104">Microsoft 365 Apps for enterprise</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="b89b5-105">Начальное развертывание</span><span class="sxs-lookup"><span data-stu-id="b89b5-105">Initial deployment</span></span>

<span data-ttu-id="b89b5-106">Компьютеры, управляемые Майкрософт, обеспечивают установку приложений Microsoft 365 для предприятий (64-битных версий) в составе образа на всех [программных устройствах.](../service-description/device-list.md)</span><span class="sxs-lookup"><span data-stu-id="b89b5-106">Microsoft Managed Desktop ensures that Microsoft 365 Apps for enterprise (64-bit) are installed as a part of the image on all [program devices](../service-description/device-list.md).</span></span> <span data-ttu-id="b89b5-107">Все следующие приложения должны присутствовать на устройстве при его доставке:</span><span class="sxs-lookup"><span data-stu-id="b89b5-107">All of the following applications should be present on the device when it's delivered:</span></span>

- <span data-ttu-id="b89b5-108">Word</span><span class="sxs-lookup"><span data-stu-id="b89b5-108">Word</span></span>
- <span data-ttu-id="b89b5-109">Excel</span><span class="sxs-lookup"><span data-stu-id="b89b5-109">Excel</span></span>
- <span data-ttu-id="b89b5-110">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="b89b5-110">PowerPoint</span></span>
- <span data-ttu-id="b89b5-111">Outlook</span><span class="sxs-lookup"><span data-stu-id="b89b5-111">Outlook</span></span>
- <span data-ttu-id="b89b5-112">Publisher</span><span class="sxs-lookup"><span data-stu-id="b89b5-112">Publisher</span></span>
- <span data-ttu-id="b89b5-113">Access</span><span class="sxs-lookup"><span data-stu-id="b89b5-113">Access</span></span>
- <span data-ttu-id="b89b5-114">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="b89b5-114">Skype for Business</span></span>
- <span data-ttu-id="b89b5-115">OneNote</span><span class="sxs-lookup"><span data-stu-id="b89b5-115">OneNote</span></span>

<span data-ttu-id="b89b5-116">Этот подход сводит к минимуму влияние на сеть и гарантирует, что пользователи смогут работать эффективно сразу после получения устройства.</span><span class="sxs-lookup"><span data-stu-id="b89b5-116">This approach minimizes network impact and ensures that users can be productive as soon as they receive their device.</span></span> <span data-ttu-id="b89b5-117">Затем мы развертываем дополнительные политики на управляемых устройствах, чтобы настроить приложения для использования.</span><span class="sxs-lookup"><span data-stu-id="b89b5-117">We then deploy more policies to managed devices to set up the applications for use.</span></span>

> [!NOTE]
> <span data-ttu-id="b89b5-118">Microsoft Teams развертывается отдельно от приложений Microsoft 365 для предприятий и не включается в базовый образ.</span><span class="sxs-lookup"><span data-stu-id="b89b5-118">Microsoft Teams is deployed separately from Microsoft 365 Apps for enterprise and is not included in the base image.</span></span> 

### <a name="available-deployment-to-users"></a><span data-ttu-id="b89b5-119">Доступное развертывание для пользователей</span><span class="sxs-lookup"><span data-stu-id="b89b5-119">Available deployment to users</span></span>

<span data-ttu-id="b89b5-120">Если у пользователя нет приложений Microsoft 365 на своем устройстве по какой-либо причине, вы можете использовать пакет, чтобы вернуть устройство в ожидаемое состояние.</span><span class="sxs-lookup"><span data-stu-id="b89b5-120">If a user does not have Microsoft 365 Apps on their device for any reason, you can use a package to return the device to its expected state.</span></span> <span data-ttu-id="b89b5-121">Добавьте пользователя в группу **Modern Workplace-Office-Office365_Install,** и приложения станут доступны для них на портале компании.</span><span class="sxs-lookup"><span data-stu-id="b89b5-121">Add the user to the **Modern Workplace-Office-Office365_Install** group and the apps will become available to them in the Company Portal.</span></span>

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a><span data-ttu-id="b89b5-122">Приложения Microsoft 365 для предприятий (32-битные)</span><span class="sxs-lookup"><span data-stu-id="b89b5-122">Microsoft 365 Apps for enterprise (32-bit)</span></span>

<span data-ttu-id="b89b5-123">Компьютеры, управляемые Майкрософт, не поддерживают развертывание 32-битной версии приложений M365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="b89b5-123">Microsoft Managed Desktop doesn't support the deployment of the 32-bit version of M365 Apps for enterprise.</span></span>

## <a name="updates-to-microsoft-365-apps"></a><span data-ttu-id="b89b5-124">Обновления приложений Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b89b5-124">Updates to Microsoft 365 Apps</span></span>

<span data-ttu-id="b89b5-125">Приложения Microsoft 365 обновляются в [monthly Enterprise Channel.](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)</span><span class="sxs-lookup"><span data-stu-id="b89b5-125">Microsoft 365 Apps are set to update on the [Monthly Enterprise Channel](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview).</span></span> <span data-ttu-id="b89b5-126">Эта практика предоставляет пользователям новые функции Office каждый месяц, но они будут получать только одно обновление в месяц при прогнозируемом расписании выпусков.</span><span class="sxs-lookup"><span data-stu-id="b89b5-126">This practice provides your users with new Office features each month, but they'll receive just one update per month on a predictable release schedule.</span></span> <span data-ttu-id="b89b5-127">Обновления выпускаются во второй вторник месяца; эти обновления могут включать обновления функций, безопасности и качества.</span><span class="sxs-lookup"><span data-stu-id="b89b5-127">Updates are released on the second Tuesday of the month; these updates can include feature, security, and quality updates.</span></span> <span data-ttu-id="b89b5-128">Эти обновления происходят автоматически и извлекаются непосредственно из CDN Office для этого канала.</span><span class="sxs-lookup"><span data-stu-id="b89b5-128">These updates occur automatically and are pulled directly from the Office CDN for that specific channel.</span></span>

<span data-ttu-id="b89b5-129">На компьютерах, управляемых Майкрософт, каждый выпуск определяет потенциальные проблемы в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="b89b5-129">Microsoft Managed Desktop staggers each release to identify any potential issues in your environment.</span></span> <span data-ttu-id="b89b5-130">Мы завершаем выпуск через 28 дней после выпуска из группы продуктов приложения Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b89b5-130">We complete the rollout 28 days after the release from the Microsoft 365 App product group.</span></span> <span data-ttu-id="b89b5-131">Компьютеры, управляемые Майкрософт, запланируют выпуски обновлений для разных групп, чтобы дать время на проверку и тестирование следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b89b5-131">Microsoft Managed Desktop schedules update releases to different groups to allow time for validation and testing as follows:</span></span> 

- <span data-ttu-id="b89b5-132">Тест: ноль дней</span><span class="sxs-lookup"><span data-stu-id="b89b5-132">Test: zero days</span></span>
- <span data-ttu-id="b89b5-133">Первый: ноль дней</span><span class="sxs-lookup"><span data-stu-id="b89b5-133">First: zero days</span></span>
- <span data-ttu-id="b89b5-134">Быстрое: 7 дней</span><span class="sxs-lookup"><span data-stu-id="b89b5-134">Fast: 7 days</span></span>
- <span data-ttu-id="b89b5-135">Широкая: 21 день</span><span class="sxs-lookup"><span data-stu-id="b89b5-135">Broad: 21 days</span></span>

<span data-ttu-id="b89b5-136">На компьютерах, управляемых Майкрософт, устанавливается семидневный крайний срок обновления [для](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) устройств.</span><span class="sxs-lookup"><span data-stu-id="b89b5-136">Microsoft Managed Desktop sets a seven-day [update deadline](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) for devices.</span></span> <span data-ttu-id="b89b5-137">После того как обновление станет доступным, оно должно быть установлено в течение семи дней.</span><span class="sxs-lookup"><span data-stu-id="b89b5-137">Once the update is available, it must be installed within seven days.</span></span> <span data-ttu-id="b89b5-138">Пользователи [](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) получают уведомления о том, что обновления требуются в нескольких местах: приложение в системной области за 12 часов до крайнего срока и получает 15-минутное предупреждение перед крайним сроком.</span><span class="sxs-lookup"><span data-stu-id="b89b5-138">Users are [notified](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) that updates are required in several locations: the application, in the system tray 12 hours prior to the deadline, and they receive a 15-minute warning prior to the deadline.</span></span> <span data-ttu-id="b89b5-139">Для завершения обновления все приложения Microsoft 365 должны быть закрыты.</span><span class="sxs-lookup"><span data-stu-id="b89b5-139">All Microsoft 365 Apps must be closed for the update to complete.</span></span>

### <a name="pausing-or-rolling-back-an-update"></a><span data-ttu-id="b89b5-140">Приоренка или откат обновления</span><span class="sxs-lookup"><span data-stu-id="b89b5-140">Pausing or rolling back an update</span></span>

<span data-ttu-id="b89b5-141">Если по какой-либо причине вам нужно приостановить или откатить обновление приложения Microsoft 365, поделайте запрос в службу поддержки администратора на портале Microsoft Managed Desktop. [](../working-with-managed-desktop/admin-support.md)</span><span class="sxs-lookup"><span data-stu-id="b89b5-141">If you need to pause or roll back Microsoft 365 App update for any reason, file an [admin support request](../working-with-managed-desktop/admin-support.md) through the Microsoft Managed Desktop portal.</span></span>

<span data-ttu-id="b89b5-142">Во время выпуска компьютеры, управляемые Майкрософт, отслеживают количество ошибок во всех приложениях Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b89b5-142">During a release, Microsoft Managed Desktop monitors the error rates of all Microsoft 365 Apps.</span></span> <span data-ttu-id="b89b5-143">Если мы отметим существенное различие в качестве между новым выпуском и его предшественником, мы можем связаться с вами на портале администрирования управляемых компьютеров Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b89b5-143">If we note a significant difference in quality between the new release and its predecessor, we might contact you through the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="b89b5-144">В зависимости от серьезности мы запросим, хотите ли вы приостановить выпуск, или проинформировать вас о том, что мы приняли меры для решения проблемы.</span><span class="sxs-lookup"><span data-stu-id="b89b5-144">Depending on the severity, we will either ask if you want to pause the release or inform you that we have taken action to mitigate an issue.</span></span> 

### <a name="delivery-optimization"></a><span data-ttu-id="b89b5-145">Оптимизация доставки</span><span class="sxs-lookup"><span data-stu-id="b89b5-145">Delivery optimization</span></span>

<span data-ttu-id="b89b5-146">Оптимизация доставки — это технология одноранговой рассылки, доступная в Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b89b5-146">Delivery Optimization is a peer-to-peer distribution technology available in Windows 10.</span></span> <span data-ttu-id="b89b5-147">Это позволяет устройствам обмениваться содержимым, например обновлениями, которые устройства скачали из Майкрософт через Интернет.</span><span class="sxs-lookup"><span data-stu-id="b89b5-147">It allows devices to share content, such as updates, that the devices have downloaded from Microsoft over the internet.</span></span> <span data-ttu-id="b89b5-148">Использование этого решения может помочь уменьшить пропускную способность сети, так как устройство может получать части обновления с другого устройства в локальной сети вместо того, чтобы полностью загружать обновление от Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b89b5-148">Using it can help reduce network bandwidth because a device can get portions of the update from another device on its local network instead of having to download the update completely from Microsoft.</span></span>

<span data-ttu-id="b89b5-149">[Оптимизация доставки](https://docs.microsoft.com/deployoffice/delivery-optimization) включена по умолчанию на устройствах под управлением выпусков Windows 10 Корпоративная или Windows 10 для образовательных сфере.</span><span class="sxs-lookup"><span data-stu-id="b89b5-149">[Delivery Optimization](https://docs.microsoft.com/deployoffice/delivery-optimization) is enabled by default on devices running the Windows 10 Enterprise or Windows 10 Education editions.</span></span> 

## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="b89b5-150">Параметры, управляемые компьютером, управляемым Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b89b5-150">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="b89b5-151">Корпорация Майкрософт управляет некоторыми настройками в рамках службы.</span><span class="sxs-lookup"><span data-stu-id="b89b5-151">Microsoft manages some settings as a part of the service.</span></span> <span data-ttu-id="b89b5-152">Компьютеры, управляемые Майкрософт, не управляют базовыми показателями безопасности Office, но вы можете настроить их самостоятельно, следуя указаниям в разделе ["Параметры", которым вы управляете.](#settings-you-manage)</span><span class="sxs-lookup"><span data-stu-id="b89b5-152">Microsoft Managed Desktop doesn't manage an Office Security baseline but you can set one yourself by following the guidance in the [Settings you manage](#settings-you-manage) section.</span></span>

### <a name="update-settings"></a><span data-ttu-id="b89b5-153">Обновление параметров</span><span class="sxs-lookup"><span data-stu-id="b89b5-153">Update settings</span></span>

<span data-ttu-id="b89b5-154">На компьютере, управляемом Майкрософт, поддерживаются все параметры [обновления](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) для управляемых устройств, и эти параметры следует изменить.</span><span class="sxs-lookup"><span data-stu-id="b89b5-154">Microsoft Managed Desktop maintains all [update settings](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) for managed devices and you should modify these settings.</span></span>

### <a name="set-updates-to-occur-automatically"></a><span data-ttu-id="b89b5-155">Настроить автоматические обновления</span><span class="sxs-lookup"><span data-stu-id="b89b5-155">Set updates to occur automatically</span></span>

<span data-ttu-id="b89b5-156">**Значение по умолчанию:** включено</span><span class="sxs-lookup"><span data-stu-id="b89b5-156">**Default value**: Enabled</span></span>

<span data-ttu-id="b89b5-157">Эта политика настроена для обеспечения того, чтобы все устройства Office могли быть в курсе всех облачных служб.</span><span class="sxs-lookup"><span data-stu-id="b89b5-157">This policy is configured in order to ensure that all Office devices can be kept up to date from the cloud.</span></span> 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a><span data-ttu-id="b89b5-158">Установите крайний срок, когда необходимо применить обновления</span><span class="sxs-lookup"><span data-stu-id="b89b5-158">Set a deadline when updates have to be applied</span></span>

<span data-ttu-id="b89b5-159">**Значение по умолчанию:** 7 дней</span><span class="sxs-lookup"><span data-stu-id="b89b5-159">**Default value**: 7 days</span></span>

<span data-ttu-id="b89b5-160">Политика **UpdateDeadline** используется для настройки льготного периода, который пользователи имеют до принудительного обновления на устройстве.</span><span class="sxs-lookup"><span data-stu-id="b89b5-160">The **UpdateDeadline** policy is used to configure the grace period which users have before an update is enforced on the device.</span></span> <span data-ttu-id="b89b5-161">Эта политика крайнего [](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) срока также инициирует уведомления пользователя об изменениях, необходимых для его устройства.</span><span class="sxs-lookup"><span data-stu-id="b89b5-161">This deadline policy also triggers [notifications](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) to the user to inform them of the changes required on their device.</span></span>  

### <a name="defer-updates-on-a-device-for-a-period"></a><span data-ttu-id="b89b5-162">Отсрочка обновлений на устройстве на период</span><span class="sxs-lookup"><span data-stu-id="b89b5-162">Defer updates on a device for a period</span></span>

<span data-ttu-id="b89b5-163">Эта политика настраивается по-разному для каждой группы устройств управления обновлениями и необходима для того, чтобы компьютеры, управляемые Майкрософт, отвечали целевым объектам обновления:</span><span class="sxs-lookup"><span data-stu-id="b89b5-163">This policy is configured differently for each update management device group and is required for Microsoft Managed Desktop to meet its update targets:</span></span>  

- <span data-ttu-id="b89b5-164">Тест: ноль дней</span><span class="sxs-lookup"><span data-stu-id="b89b5-164">Test: zero days</span></span>
- <span data-ttu-id="b89b5-165">Первый: ноль дней</span><span class="sxs-lookup"><span data-stu-id="b89b5-165">First: zero days</span></span>
- <span data-ttu-id="b89b5-166">Быстрое 7 дней</span><span class="sxs-lookup"><span data-stu-id="b89b5-166">Fast 7 days</span></span>
- <span data-ttu-id="b89b5-167">Широкая: 21 день</span><span class="sxs-lookup"><span data-stu-id="b89b5-167">Broad: 21 days</span></span>

### <a name="update-notifications-settings"></a><span data-ttu-id="b89b5-168">Обновление параметров уведомлений</span><span class="sxs-lookup"><span data-stu-id="b89b5-168">Update notifications settings</span></span>

<span data-ttu-id="b89b5-169">**Значение по умолчанию:** False</span><span class="sxs-lookup"><span data-stu-id="b89b5-169">**Default value**: False</span></span>

<span data-ttu-id="b89b5-170">Для параметра "скрыть уведомления об обновлениях" на настольных устройствах, управляемых Майкрософт, задайте для них параметр **False,** чтобы обеспечить наилучшее обновление для пользователей, уведомляя их о необходимости обновления. [](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps)</span><span class="sxs-lookup"><span data-stu-id="b89b5-170">The "hide update notifications" setting is set to **False** on Microsoft Managed Desktop devices to provide the best update experience for users by [notifying](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) them when updates are required.</span></span>

### <a name="specify-a-location-to-look-for-updates"></a><span data-ttu-id="b89b5-171">Указать расположение для поиска обновлений</span><span class="sxs-lookup"><span data-stu-id="b89b5-171">Specify a location to look for updates</span></span>

<span data-ttu-id="b89b5-172">**Значение по умолчанию:** Monthly Enterprise Channel</span><span class="sxs-lookup"><span data-stu-id="b89b5-172">**Default value**: Monthly Enterprise Channel</span></span>

<span data-ttu-id="b89b5-173">Для достижения расписания обновления используется сочетание политик **UpdatePath** и **UpdateChannel.**</span><span class="sxs-lookup"><span data-stu-id="b89b5-173">A combination of the **UpdatePath** and **UpdateChannel** policies is used as needed to achieve the update schedule.</span></span> <span data-ttu-id="b89b5-174">Эти политики гарантируют, что все устройства Office будут получать обновления непосредственно из CDN для Monthly Enterprise Channel.</span><span class="sxs-lookup"><span data-stu-id="b89b5-174">These policies are set to ensure that all Office devices receive updates directly from the CDN for the Monthly Enterprise Channel.</span></span>

### <a name="specify-the-target-version-of-microsoft-365-apps"></a><span data-ttu-id="b89b5-175">Указание целевой версии приложений Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b89b5-175">Specify the Target Version of Microsoft 365 Apps</span></span>

<span data-ttu-id="b89b5-176">Политика целевой версии иногда используется компьютером, управляемым Майкрософт, для отката или закрепления определенной версии Office.</span><span class="sxs-lookup"><span data-stu-id="b89b5-176">The Target Version policy is sometimes used by Microsoft Managed Desktop in order to roll back or pin a specific version of Office.</span></span> 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a><span data-ttu-id="b89b5-177">Скрытие параметра для включаемого или отключения автоматических обновлений Office</span><span class="sxs-lookup"><span data-stu-id="b89b5-177">Hide the option to enable or disable Office automatic updates</span></span>

<span data-ttu-id="b89b5-178">**Значение по умолчанию:** включено</span><span class="sxs-lookup"><span data-stu-id="b89b5-178">**Default value**: Enabled</span></span>

<span data-ttu-id="b89b5-179">Этот параметр необходим для того, чтобы компьютеры, управляемые Майкрософт, соответствуют целям обновления для приложений Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b89b5-179">This setting is required for Microsoft Managed Desktop to meet its update targets for Microsoft 365 Applications.</span></span> 

### <a name="first-run-settings"></a><span data-ttu-id="b89b5-180">Параметры первого запуска</span><span class="sxs-lookup"><span data-stu-id="b89b5-180">First run settings</span></span> 

<span data-ttu-id="b89b5-181">Существует несколько параметров, влияющих на поведение при первом запуске Office.</span><span class="sxs-lookup"><span data-stu-id="b89b5-181">There are several settings that affect the behavior the first time Office is run.</span></span>

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a><span data-ttu-id="b89b5-182">Принятие условий лицензии от имени конечного пользователя</span><span class="sxs-lookup"><span data-stu-id="b89b5-182">Accept the license terms on behalf of the end user</span></span>

<span data-ttu-id="b89b5-183">**Значение по умолчанию:** Отключено</span><span class="sxs-lookup"><span data-stu-id="b89b5-183">**Default value**: Disabled</span></span>

<span data-ttu-id="b89b5-184">Когда пользователь впервые открывает приложение Microsoft 365, пользователю будет предложено принять условия лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="b89b5-184">The first time a user opens a Microsoft 365 App, they are prompted to accept the license terms.</span></span> <span data-ttu-id="b89b5-185">Если вы хотите принять условия лицензионного соглашения от имени пользователей, подайте запрос на обслуживание в команду Microsoft Managed Desktop Operations с запросом включения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="b89b5-185">If you want to accept the license terms on behalf of your users, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

### <a name="suppress-outlook-mobile-check-box"></a><span data-ttu-id="b89b5-186">Подавление мобильного outlook</span><span class="sxs-lookup"><span data-stu-id="b89b5-186">Suppress Outlook mobile check box</span></span>

<span data-ttu-id="b89b5-187">**Значение по умолчанию:** Отключено</span><span class="sxs-lookup"><span data-stu-id="b89b5-187">**Default value**: Disabled</span></span>

<span data-ttu-id="b89b5-188">Когда пользователь впервые открывает Outlook, пользователю будет предложено установить Outlook Mobile.</span><span class="sxs-lookup"><span data-stu-id="b89b5-188">The first time a user opens Outlook they are prompted to install Outlook Mobile.</span></span> <span data-ttu-id="b89b5-189">Если вы не хотите, чтобы пользователи видели этот параметр, подайте запрос на обслуживание в команду Microsoft Managed Desktop Operations, включив этот параметр для ваших устройств.</span><span class="sxs-lookup"><span data-stu-id="b89b5-189">If you don’t want your users to see that check box, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled for your devices.</span></span> 

## <a name="other-settings"></a><span data-ttu-id="b89b5-190">Другие параметры</span><span class="sxs-lookup"><span data-stu-id="b89b5-190">Other settings</span></span>

<span data-ttu-id="b89b5-191">Существуют другие параметры приложения Microsoft 365, которые можно дополнительно настроить от вашего имени.</span><span class="sxs-lookup"><span data-stu-id="b89b5-191">There are other Microsoft 365 App settings which Microsoft Managed Desktop can optionally configure on your behalf.</span></span> 

### <a name="disable-personal-onedrive"></a><span data-ttu-id="b89b5-192">Отключение личного OneDrive</span><span class="sxs-lookup"><span data-stu-id="b89b5-192">Disable Personal OneDrive</span></span>

<span data-ttu-id="b89b5-193">**Значение по умолчанию:** Отключено</span><span class="sxs-lookup"><span data-stu-id="b89b5-193">**Default value**: Disabled</span></span>

<span data-ttu-id="b89b5-194">В некоторых организациях пользователи имеют доступ как к корпоративным, так и к личным файлам на своих устройствах.</span><span class="sxs-lookup"><span data-stu-id="b89b5-194">Some organizations are concerned about users having access to both corporate and personal files on their devices.</span></span> <span data-ttu-id="b89b5-195">Вы можете подать запрос на обслуживание в команду Microsoft Managed Desktop Operations с запросом включения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="b89b5-195">You can file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

## <a name="settings-you-manage"></a><span data-ttu-id="b89b5-196">Параметры, которые вы управляете</span><span class="sxs-lookup"><span data-stu-id="b89b5-196">Settings you manage</span></span>

<span data-ttu-id="b89b5-197">Существует множество других политик, которые компьютеры, управляемые Майкрософт, еще не настроены как часть нашей службы.</span><span class="sxs-lookup"><span data-stu-id="b89b5-197">There are many other policies which Microsoft Managed Desktop does not yet set as a part of our service.</span></span> <span data-ttu-id="b89b5-198">Вы можете настроить эти политики с помощью Microsoft Intune, который использует службу [облачной политики Office.](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied)</span><span class="sxs-lookup"><span data-stu-id="b89b5-198">You can configure these policies by using Microsoft Intune, which uses the [Office Cloud Policy](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) service.</span></span> <span data-ttu-id="b89b5-199">Чтобы настроить эти политики, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b89b5-199">To set these policies, follow these steps:</span></span>

1.  <span data-ttu-id="b89b5-200">Во входе в Центр администрирования Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="b89b5-200">Sign in to the Microsoft Endpoint Manager admin center.</span></span>
2.  <span data-ttu-id="b89b5-201">Select **Apps > Policies for Office apps > Create**</span><span class="sxs-lookup"><span data-stu-id="b89b5-201">Select **Apps > Policies for Office apps > Create**</span></span>
3.  <span data-ttu-id="b89b5-202">На странице **"Создание конфигурации** политики" сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="b89b5-202">On the **Create policy** configuration page, do the following:</span></span>
    - <span data-ttu-id="b89b5-203">Введите имя.</span><span class="sxs-lookup"><span data-stu-id="b89b5-203">Enter a name.</span></span>
    - <span data-ttu-id="b89b5-204">В качестве описания (необязательно).</span><span class="sxs-lookup"><span data-stu-id="b89b5-204">Provide a description (optional).</span></span>
    - <span data-ttu-id="b89b5-205">В **заданиях** выберите, применяется ли эта политика ко всем пользователям приложений Microsoft 365 для предприятий или только к пользователям, которые анонимно используют Office для Интернета.</span><span class="sxs-lookup"><span data-stu-id="b89b5-205">In **assignments**, choose whether this policy applies to all users of Microsoft 365 Apps for enterprise, or just to users who anonymously access documents using Office for the web.</span></span>
    - <span data-ttu-id="b89b5-206">Выберите группу безопасности на основе AAD, назначенную конфигурации политики.</span><span class="sxs-lookup"><span data-stu-id="b89b5-206">Select the AAD-based security group that is assigned to the policy configuration.</span></span> <span data-ttu-id="b89b5-207">Каждая конфигурация политики может быть назначена только одной группе, а каждой группе может быть назначена только одна конфигурация политики.</span><span class="sxs-lookup"><span data-stu-id="b89b5-207">Each policy configuration can only be assigned to one group, and each group can only be assigned one policy configuration.</span></span>
    - <span data-ttu-id="b89b5-208">Настройте параметры политики, которые необходимо включить в конфигурацию политики.</span><span class="sxs-lookup"><span data-stu-id="b89b5-208">Configure the policy settings to be included in the policy configuration.</span></span> <span data-ttu-id="b89b5-209">Вы можете найти имя параметра политики, чтобы найти параметр политики, который необходимо настроить.</span><span class="sxs-lookup"><span data-stu-id="b89b5-209">You can search on the policy setting name to find the policy setting that you want to configure.</span></span> <span data-ttu-id="b89b5-210">Вы также можете отфильтровать приложение, определить, является ли политика рекомендуемой базой безопасности и настроена ли политика.</span><span class="sxs-lookup"><span data-stu-id="b89b5-210">You can also filter on the application, on whether the policy is a recommended security baseline, and on whether the policy has been configured.</span></span> <span data-ttu-id="b89b5-211">В столбце платформы указывается, применяется ли политика к приложениям Microsoft 365 для предприятий для устройств с Windows, Office в Интернете или всем.</span><span class="sxs-lookup"><span data-stu-id="b89b5-211">The platform column indicates whether the policy is applied to Microsoft 365 Apps for enterprise for Windows devices, Office for the web, or all.</span></span>
4.  <span data-ttu-id="b89b5-212">После выбора выберите **"Создать".**</span><span class="sxs-lookup"><span data-stu-id="b89b5-212">After you have made your selections, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="b89b5-213">Политики конфигурации Office поддерживают развертывание только на основе пользователей</span><span class="sxs-lookup"><span data-stu-id="b89b5-213">Office Configuration Policies only support user-based deployment</span></span>
