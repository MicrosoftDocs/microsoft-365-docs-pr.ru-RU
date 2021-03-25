---
title: Развертывание обновлений для ATP Защитника Майкрософт для Mac
description: Управление обновлениями для ATP Microsoft Defender для Mac в корпоративных средах.
keywords: Microsoft, defender, atp, mac, updates, deploy
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 99f507ad381ee21ba91753716439180fafe37c24
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074342"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="1adfe-104">Развертывание обновлений для Microsoft Defender для конечной точки для Mac</span><span class="sxs-lookup"><span data-stu-id="1adfe-104">Deploy updates for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1adfe-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1adfe-105">**Applies to:**</span></span>

- [<span data-ttu-id="1adfe-106">Microsoft Defender для конечной точки для Mac</span><span class="sxs-lookup"><span data-stu-id="1adfe-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="1adfe-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1adfe-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1adfe-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1adfe-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1adfe-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="1adfe-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1adfe-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="1adfe-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="1adfe-111">Корпорация Майкрософт регулярно публикует обновления программного обеспечения для повышения производительности, безопасности и предоставления новых функций.</span><span class="sxs-lookup"><span data-stu-id="1adfe-111">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

<span data-ttu-id="1adfe-112">Для обновления Microsoft Defender для конечной точки для Mac используется программа с именем Microsoft AutoUpdate (MAU).</span><span class="sxs-lookup"><span data-stu-id="1adfe-112">To update Microsoft Defender for Endpoint for Mac, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="1adfe-113">По умолчанию MAU автоматически проверяет обновления ежедневно, но их можно изменить на еженедельные, ежемесячные или вручную.</span><span class="sxs-lookup"><span data-stu-id="1adfe-113">By default, MAU automatically checks for updates daily, but you can change that to weekly, monthly, or manually.</span></span>

![Снимок экрана MAU](images/MDATP-34-MAU.png)

<span data-ttu-id="1adfe-115">Если вы решите развернуть обновления с помощью средств распространения программного обеспечения, необходимо настроить MAU, чтобы вручную проверять обновления программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="1adfe-115">If you decide to deploy updates by using your software distribution tools, you should configure MAU to manually check for software updates.</span></span> <span data-ttu-id="1adfe-116">Вы можете развернуть настройки, чтобы настроить, как и когда MAU проверяет обновления для macs в организации.</span><span class="sxs-lookup"><span data-stu-id="1adfe-116">You can deploy preferences to configure how and when MAU checks for updates for the Macs in your organization.</span></span>

## <a name="use-msupdate"></a><span data-ttu-id="1adfe-117">Использование msupdate</span><span class="sxs-lookup"><span data-stu-id="1adfe-117">Use msupdate</span></span>

<span data-ttu-id="1adfe-118">MAU включает средство командной строки, называемое *msupdate,* которое предназначено для ИТ-администраторов, чтобы они могли более точно контролировать при применении обновлений.</span><span class="sxs-lookup"><span data-stu-id="1adfe-118">MAU includes a command-line tool, called *msupdate*, that is designed for IT administrators so that they have more precise control over when updates are applied.</span></span> <span data-ttu-id="1adfe-119">Инструкции по использованию этого средства можно найти в [обновлении Office для Mac с помощью msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).</span><span class="sxs-lookup"><span data-stu-id="1adfe-119">Instructions for how to use this tool can be found in [Update Office for Mac by using msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).</span></span>

<span data-ttu-id="1adfe-120">В MAU идентификатор приложения для Microsoft Defender для конечной точки для Mac *— WDAV00.*</span><span class="sxs-lookup"><span data-stu-id="1adfe-120">In MAU, the application identifier for Microsoft Defender for Endpoint for Mac is *WDAV00*.</span></span> <span data-ttu-id="1adfe-121">Чтобы скачать и установить последние обновления для Microsoft Defender для конечной точки для Mac, выполните следующую команду из окна терминала:</span><span class="sxs-lookup"><span data-stu-id="1adfe-121">To download and install the latest updates for Microsoft Defender for Endpoint for Mac, execute the following command from a Terminal window:</span></span>

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a><span data-ttu-id="1adfe-122">Настройка предпочтений для Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="1adfe-122">Set preferences for Microsoft AutoUpdate</span></span>

<span data-ttu-id="1adfe-123">В этом разделе описываются наиболее распространенные предпочтения, которые можно использовать для настройки MAU.</span><span class="sxs-lookup"><span data-stu-id="1adfe-123">This section describes the most common preferences that can be used to configure MAU.</span></span> <span data-ttu-id="1adfe-124">Эти параметры можно развернуть в качестве профиля конфигурации через консоль управления, которую использует ваше предприятие.</span><span class="sxs-lookup"><span data-stu-id="1adfe-124">These settings can be deployed as a configuration profile through the management console that your enterprise is using.</span></span> <span data-ttu-id="1adfe-125">Пример профиля конфигурации показан в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="1adfe-125">An example of a configuration profile is shown in the following sections.</span></span>

### <a name="set-the-channel-name"></a><span data-ttu-id="1adfe-126">Настройка имени канала</span><span class="sxs-lookup"><span data-stu-id="1adfe-126">Set the channel name</span></span>

<span data-ttu-id="1adfe-127">Канал определяет тип и частоту обновлений, предлагаемых через MAU.</span><span class="sxs-lookup"><span data-stu-id="1adfe-127">The channel determines the type and frequency of updates that are offered through MAU.</span></span> <span data-ttu-id="1adfe-128">Устройства в `Beta` может попробовать новые функции перед устройствами `Preview` в и `Current` .</span><span class="sxs-lookup"><span data-stu-id="1adfe-128">Devices in `Beta` can try out new features before devices in `Preview` and `Current`.</span></span> 

<span data-ttu-id="1adfe-129">Канал `Current` содержит наиболее стабильную версию продукта.</span><span class="sxs-lookup"><span data-stu-id="1adfe-129">The `Current` channel contains the most stable version of the product.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="1adfe-130">До версии Microsoft AutoUpdate 4.29 каналы имели разные имена:</span><span class="sxs-lookup"><span data-stu-id="1adfe-130">Prior to Microsoft AutoUpdate version 4.29, channels had different names:</span></span> 
> 
> - <span data-ttu-id="1adfe-131">`Beta` был назван `InsiderFast` (Insider Fast)</span><span class="sxs-lookup"><span data-stu-id="1adfe-131">`Beta` was named `InsiderFast` (Insider Fast)</span></span>
> - <span data-ttu-id="1adfe-132">`Preview` был назван `External` (Insider Slow)</span><span class="sxs-lookup"><span data-stu-id="1adfe-132">`Preview` was named `External` (Insider Slow)</span></span>
> - <span data-ttu-id="1adfe-133">`Current` был назван `Production`</span><span class="sxs-lookup"><span data-stu-id="1adfe-133">`Current` was named `Production`</span></span>

>[!TIP]
><span data-ttu-id="1adfe-134">Чтобы просмотреть новые функции и предоставить ранние отзывы, рекомендуется настроить некоторые устройства в вашем предприятии на `Beta` или `Preview` .</span><span class="sxs-lookup"><span data-stu-id="1adfe-134">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to `Beta` or `Preview`.</span></span>

|||
|:--|:--|
| <span data-ttu-id="1adfe-135">**Домен**</span><span class="sxs-lookup"><span data-stu-id="1adfe-135">**Domain**</span></span> | <span data-ttu-id="1adfe-136">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="1adfe-136">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="1adfe-137">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="1adfe-137">**Key**</span></span> | <span data-ttu-id="1adfe-138">ChannelName</span><span class="sxs-lookup"><span data-stu-id="1adfe-138">ChannelName</span></span> |
| <span data-ttu-id="1adfe-139">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="1adfe-139">**Data type**</span></span> | <span data-ttu-id="1adfe-140">String</span><span class="sxs-lookup"><span data-stu-id="1adfe-140">String</span></span> |
| <span data-ttu-id="1adfe-141">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="1adfe-141">**Possible values**</span></span> | <span data-ttu-id="1adfe-142">Бета-версия</span><span class="sxs-lookup"><span data-stu-id="1adfe-142">Beta</span></span> <br/> <span data-ttu-id="1adfe-143">Предварительная версия</span><span class="sxs-lookup"><span data-stu-id="1adfe-143">Preview</span></span> <br/> <span data-ttu-id="1adfe-144">Current</span><span class="sxs-lookup"><span data-stu-id="1adfe-144">Current</span></span> |
|||

>[!WARNING]
><span data-ttu-id="1adfe-145">Этот параметр изменяет канал для всех приложений, которые обновляются с помощью Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="1adfe-145">This setting changes the channel for all applications that are updated through Microsoft AutoUpdate.</span></span> <span data-ttu-id="1adfe-146">Чтобы изменить канал только для Microsoft Defender для конечной точки для Mac, выполните следующую команду после замены `[channel-name]` на нужный канал:</span><span class="sxs-lookup"><span data-stu-id="1adfe-146">To change the channel only for Microsoft Defender for Endpoint for Mac, execute the following command after replacing `[channel-name]` with the desired channel:</span></span>
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a><span data-ttu-id="1adfe-147">Установите частоту проверки обновления</span><span class="sxs-lookup"><span data-stu-id="1adfe-147">Set update check frequency</span></span>

<span data-ttu-id="1adfe-148">Измените, как часто MAU выполняет поиск обновлений.</span><span class="sxs-lookup"><span data-stu-id="1adfe-148">Change how often MAU searches for updates.</span></span>

|||
|:--|:--|
| <span data-ttu-id="1adfe-149">**Домен**</span><span class="sxs-lookup"><span data-stu-id="1adfe-149">**Domain**</span></span> | <span data-ttu-id="1adfe-150">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="1adfe-150">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="1adfe-151">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="1adfe-151">**Key**</span></span> | <span data-ttu-id="1adfe-152">UpdateCheckFrequency</span><span class="sxs-lookup"><span data-stu-id="1adfe-152">UpdateCheckFrequency</span></span> |
| <span data-ttu-id="1adfe-153">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="1adfe-153">**Data type**</span></span> | <span data-ttu-id="1adfe-154">Целое число</span><span class="sxs-lookup"><span data-stu-id="1adfe-154">Integer</span></span> |
| <span data-ttu-id="1adfe-155">**Значение, используемое по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="1adfe-155">**Default value**</span></span> | <span data-ttu-id="1adfe-156">720 (минут)</span><span class="sxs-lookup"><span data-stu-id="1adfe-156">720 (minutes)</span></span> |
| <span data-ttu-id="1adfe-157">**Comment**</span><span class="sxs-lookup"><span data-stu-id="1adfe-157">**Comment**</span></span> | <span data-ttu-id="1adfe-158">Это значение устанавливается в минутах.</span><span class="sxs-lookup"><span data-stu-id="1adfe-158">This value is set in minutes.</span></span> |
|||

### <a name="change-how-mau-interacts-with-updates"></a><span data-ttu-id="1adfe-159">Изменение взаимодействия MAU с обновлениями</span><span class="sxs-lookup"><span data-stu-id="1adfe-159">Change how MAU interacts with updates</span></span>

<span data-ttu-id="1adfe-160">Измените, как MAU ищет обновления.</span><span class="sxs-lookup"><span data-stu-id="1adfe-160">Change how MAU searches for updates.</span></span>

|||
|:--|:--|
| <span data-ttu-id="1adfe-161">**Домен**</span><span class="sxs-lookup"><span data-stu-id="1adfe-161">**Domain**</span></span> | <span data-ttu-id="1adfe-162">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="1adfe-162">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="1adfe-163">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="1adfe-163">**Key**</span></span> | <span data-ttu-id="1adfe-164">HowToCheck</span><span class="sxs-lookup"><span data-stu-id="1adfe-164">HowToCheck</span></span> |
| <span data-ttu-id="1adfe-165">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="1adfe-165">**Data type**</span></span> | <span data-ttu-id="1adfe-166">String</span><span class="sxs-lookup"><span data-stu-id="1adfe-166">String</span></span> |
| <span data-ttu-id="1adfe-167">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="1adfe-167">**Possible values**</span></span> | <span data-ttu-id="1adfe-168">Вручную</span><span class="sxs-lookup"><span data-stu-id="1adfe-168">Manual</span></span> <br/> <span data-ttu-id="1adfe-169">AutomaticCheck</span><span class="sxs-lookup"><span data-stu-id="1adfe-169">AutomaticCheck</span></span> <br/> <span data-ttu-id="1adfe-170">AutomaticDownload</span><span class="sxs-lookup"><span data-stu-id="1adfe-170">AutomaticDownload</span></span> |
| <span data-ttu-id="1adfe-171">**Comment**</span><span class="sxs-lookup"><span data-stu-id="1adfe-171">**Comment**</span></span> |  <span data-ttu-id="1adfe-172">Обратите внимание, что AutomaticDownload будет скачивать и устанавливать безмолвно, если это возможно.</span><span class="sxs-lookup"><span data-stu-id="1adfe-172">Note that AutomaticDownload will do a download and install silently if possible.</span></span> |
|||

### <a name="change-whether-the-check-for-updates-button-is-enabled"></a><span data-ttu-id="1adfe-173">Измените, включена ли кнопка "Проверка обновлений"</span><span class="sxs-lookup"><span data-stu-id="1adfe-173">Change whether the "Check for Updates" button is enabled</span></span>

<span data-ttu-id="1adfe-174">Измените, смогут ли местные пользователи щелкнуть параметр "Проверка обновлений" в пользовательском интерфейсе Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="1adfe-174">Change whether local users will be able to click the "Check for Updates" option in the Microsoft AutoUpdate user interface.</span></span>

|||
|:--|:--|
| <span data-ttu-id="1adfe-175">**Домен**</span><span class="sxs-lookup"><span data-stu-id="1adfe-175">**Domain**</span></span> | <span data-ttu-id="1adfe-176">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="1adfe-176">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="1adfe-177">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="1adfe-177">**Key**</span></span> | <span data-ttu-id="1adfe-178">EnableCheckForUpdatesButton</span><span class="sxs-lookup"><span data-stu-id="1adfe-178">EnableCheckForUpdatesButton</span></span> |
| <span data-ttu-id="1adfe-179">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="1adfe-179">**Data type**</span></span> | <span data-ttu-id="1adfe-180">Логический</span><span class="sxs-lookup"><span data-stu-id="1adfe-180">Boolean</span></span> |
| <span data-ttu-id="1adfe-181">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="1adfe-181">**Possible values**</span></span> | <span data-ttu-id="1adfe-182">True (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="1adfe-182">True (default)</span></span> <br/> <span data-ttu-id="1adfe-183">False</span><span class="sxs-lookup"><span data-stu-id="1adfe-183">False</span></span> |
|||

### <a name="disable-insider-checkbox"></a><span data-ttu-id="1adfe-184">Отключение почтового ящика Insider</span><span class="sxs-lookup"><span data-stu-id="1adfe-184">Disable Insider checkbox</span></span>

<span data-ttu-id="1adfe-185">Установите для true, чтобы сделать "Присоединиться к программе инсайдерской службы Office..." checkbox недоступный или серый для пользователей.</span><span class="sxs-lookup"><span data-stu-id="1adfe-185">Set to true to make the "Join the Office Insider Program..." checkbox unavailable / greyed out to users.</span></span>

|||
|:--|:--|
| <span data-ttu-id="1adfe-186">**Домен**</span><span class="sxs-lookup"><span data-stu-id="1adfe-186">**Domain**</span></span> | <span data-ttu-id="1adfe-187">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="1adfe-187">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="1adfe-188">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="1adfe-188">**Key**</span></span> | <span data-ttu-id="1adfe-189">DisableInsiderCheckbox</span><span class="sxs-lookup"><span data-stu-id="1adfe-189">DisableInsiderCheckbox</span></span> |
| <span data-ttu-id="1adfe-190">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="1adfe-190">**Data type**</span></span> | <span data-ttu-id="1adfe-191">Логический</span><span class="sxs-lookup"><span data-stu-id="1adfe-191">Boolean</span></span> |
| <span data-ttu-id="1adfe-192">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="1adfe-192">**Possible values**</span></span> | <span data-ttu-id="1adfe-193">False (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="1adfe-193">False (default)</span></span> <br/> <span data-ttu-id="1adfe-194">Верно</span><span class="sxs-lookup"><span data-stu-id="1adfe-194">True</span></span> |
|||

### <a name="limit-the-telemetry-that-is-sent-from-mau"></a><span data-ttu-id="1adfe-195">Ограничение телеметрии, отправленной из MAU</span><span class="sxs-lookup"><span data-stu-id="1adfe-195">Limit the telemetry that is sent from MAU</span></span>

<span data-ttu-id="1adfe-196">Установите для отправки минимальные данные о сердцебиении, отсутствие использования приложений и отсутствие сведений об среде.</span><span class="sxs-lookup"><span data-stu-id="1adfe-196">Set to false to send minimal heartbeat data, no application usage, and no environment details.</span></span>

|||
|:--|:--|
| <span data-ttu-id="1adfe-197">**Домен**</span><span class="sxs-lookup"><span data-stu-id="1adfe-197">**Domain**</span></span> | <span data-ttu-id="1adfe-198">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="1adfe-198">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="1adfe-199">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="1adfe-199">**Key**</span></span> | <span data-ttu-id="1adfe-200">SendAllTelemetryEnabled</span><span class="sxs-lookup"><span data-stu-id="1adfe-200">SendAllTelemetryEnabled</span></span> |
| <span data-ttu-id="1adfe-201">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="1adfe-201">**Data type**</span></span> | <span data-ttu-id="1adfe-202">Логический</span><span class="sxs-lookup"><span data-stu-id="1adfe-202">Boolean</span></span> |
| <span data-ttu-id="1adfe-203">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="1adfe-203">**Possible values**</span></span> | <span data-ttu-id="1adfe-204">True (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="1adfe-204">True (default)</span></span> <br/> <span data-ttu-id="1adfe-205">False</span><span class="sxs-lookup"><span data-stu-id="1adfe-205">False</span></span> |
|||

## <a name="example-configuration-profile"></a><span data-ttu-id="1adfe-206">Пример профиля конфигурации</span><span class="sxs-lookup"><span data-stu-id="1adfe-206">Example configuration profile</span></span>

<span data-ttu-id="1adfe-207">Следующий профиль конфигурации используется для:</span><span class="sxs-lookup"><span data-stu-id="1adfe-207">The following configuration profile is used to:</span></span>
- <span data-ttu-id="1adfe-208">Поместите устройство в бета-канал</span><span class="sxs-lookup"><span data-stu-id="1adfe-208">Place the device in the Beta channel</span></span>
- <span data-ttu-id="1adfe-209">Автоматическое скачивание и установка обновлений</span><span class="sxs-lookup"><span data-stu-id="1adfe-209">Automatically download and install updates</span></span>
- <span data-ttu-id="1adfe-210">Включить кнопку "Проверка обновлений" в пользовательском интерфейсе</span><span class="sxs-lookup"><span data-stu-id="1adfe-210">Enable the "Check for updates" button in the user interface</span></span>
- <span data-ttu-id="1adfe-211">Разрешить пользователям на устройстве зарегистрироваться в каналах Insider</span><span class="sxs-lookup"><span data-stu-id="1adfe-211">Allow users on the device to enroll into the Insider channels</span></span>

### <a name="jamf"></a><span data-ttu-id="1adfe-212">JAMF</span><span class="sxs-lookup"><span data-stu-id="1adfe-212">JAMF</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>ChannelName</key>
    <string>Beta</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
</dict>
</plist>
```

### <a name="intune"></a><span data-ttu-id="1adfe-213">Intune</span><span class="sxs-lookup"><span data-stu-id="1adfe-213">Intune</span></span>

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>B762FF60-6ACB-4A72-9E72-459D00C936F3</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.autoupdate2</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft AutoUpdate settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft AutoUpdate configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
            <key>PayloadUUID</key>
            <string>5A6F350A-CC2C-440B-A074-68E3F34EBAE9</string>
            <key>PayloadType</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadOrganization</key>
            <string>Microsoft</string>
            <key>PayloadIdentifier</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft AutoUpdate configuration settings</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>ChannelName</key>
            <string>Beta</string>
            <key>HowToCheck</key>
            <string>AutomaticDownload</string>
            <key>EnableCheckForUpdatesButton</key>
            <true/>
            <key>DisableInsiderCheckbox</key>
            <false/>
            <key>SendAllTelemetryEnabled</key>
            <true/>
            </dict>
        </array>
    </dict>
</plist>
```

<span data-ttu-id="1adfe-214">Чтобы настроить MAU, вы можете развернуть этот профиль конфигурации из средства управления, которое использует ваше предприятие:</span><span class="sxs-lookup"><span data-stu-id="1adfe-214">To configure MAU, you can deploy this configuration profile from the management tool that your enterprise is using:</span></span>
- <span data-ttu-id="1adfe-215">Из JAMF загрузите этот профиль конфигурации и установите домен preference *на com.microsoft.autoupdate2.*</span><span class="sxs-lookup"><span data-stu-id="1adfe-215">From JAMF, upload this configuration profile and set the Preference Domain to *com.microsoft.autoupdate2*.</span></span>
- <span data-ttu-id="1adfe-216">В Intune загрузите этот профиль конфигурации и установите имя профиля настраиваемой конфигурации *на com.microsoft.autoupdate2.*</span><span class="sxs-lookup"><span data-stu-id="1adfe-216">From Intune, upload this configuration profile and set the custom configuration profile name to *com.microsoft.autoupdate2*.</span></span>

## <a name="resources"></a><span data-ttu-id="1adfe-217">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="1adfe-217">Resources</span></span>

- [<span data-ttu-id="1adfe-218">msupdate reference</span><span class="sxs-lookup"><span data-stu-id="1adfe-218">msupdate reference</span></span>](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)
