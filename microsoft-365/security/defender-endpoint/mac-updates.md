---
title: Развертывание обновлений для Microsoft Defender для конечной точки на Mac
description: Управление обновлениями для Microsoft Defender для конечной точки на Mac в корпоративных средах.
keywords: Microsoft, defender, Microsoft Defender for Endpoint, mac, updates, deploy
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
ms.openlocfilehash: 6447aa4182846020312e9be870c5548d9415ac71
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842834"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="d2204-104">Развертывание обновлений для Microsoft Defender для конечной точки на macOS</span><span class="sxs-lookup"><span data-stu-id="d2204-104">Deploy updates for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d2204-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d2204-105">**Applies to:**</span></span>

- [<span data-ttu-id="d2204-106">Microsoft Defender для конечной точки в macOS</span><span class="sxs-lookup"><span data-stu-id="d2204-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="d2204-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d2204-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d2204-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d2204-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d2204-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="d2204-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d2204-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="d2204-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="d2204-111">Корпорация Майкрософт регулярно публикует обновления программного обеспечения для повышения производительности, безопасности и предоставления новых функций.</span><span class="sxs-lookup"><span data-stu-id="d2204-111">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

<span data-ttu-id="d2204-112">Для обновления Microsoft Defender для конечной точки на macOS используется программа с именем Microsoft AutoUpdate (MAU).</span><span class="sxs-lookup"><span data-stu-id="d2204-112">To update Microsoft Defender for Endpoint on macOS, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="d2204-113">По умолчанию MAU автоматически проверяет обновления ежедневно, но их можно изменить на еженедельные, ежемесячные или вручную.</span><span class="sxs-lookup"><span data-stu-id="d2204-113">By default, MAU automatically checks for updates daily, but you can change that to weekly, monthly, or manually.</span></span>

![Снимок экрана MAU](images/MDATP-34-MAU.png)

<span data-ttu-id="d2204-115">Если вы решите развернуть обновления с помощью средств распространения программного обеспечения, необходимо настроить MAU, чтобы вручную проверять обновления программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="d2204-115">If you decide to deploy updates by using your software distribution tools, you should configure MAU to manually check for software updates.</span></span> <span data-ttu-id="d2204-116">Вы можете развернуть настройки, чтобы настроить, как и когда MAU проверяет обновления для macs в организации.</span><span class="sxs-lookup"><span data-stu-id="d2204-116">You can deploy preferences to configure how and when MAU checks for updates for the Macs in your organization.</span></span>

## <a name="use-msupdate"></a><span data-ttu-id="d2204-117">Использование msupdate</span><span class="sxs-lookup"><span data-stu-id="d2204-117">Use msupdate</span></span>

<span data-ttu-id="d2204-118">MAU включает средство командной строки, называемое *msupdate,* которое предназначено для ИТ-администраторов, чтобы они могли более точно контролировать при применении обновлений.</span><span class="sxs-lookup"><span data-stu-id="d2204-118">MAU includes a command-line tool, called *msupdate*, that is designed for IT administrators so that they have more precise control over when updates are applied.</span></span> <span data-ttu-id="d2204-119">Инструкции по использованию этого средства можно найти в [update Office для Mac с помощью msupdate.](/deployoffice/mac/update-office-for-mac-using-msupdate)</span><span class="sxs-lookup"><span data-stu-id="d2204-119">Instructions for how to use this tool can be found in [Update Office for Mac by using msupdate](/deployoffice/mac/update-office-for-mac-using-msupdate).</span></span>

<span data-ttu-id="d2204-120">В MAU идентификатор приложения для Microsoft Defender для конечной точки на macOS *— WDAV00.*</span><span class="sxs-lookup"><span data-stu-id="d2204-120">In MAU, the application identifier for Microsoft Defender for Endpoint on macOS is *WDAV00*.</span></span> <span data-ttu-id="d2204-121">Чтобы скачать и установить последние обновления для Microsoft Defender для конечной точки на macOS, выполните следующую команду из окна терминала:</span><span class="sxs-lookup"><span data-stu-id="d2204-121">To download and install the latest updates for Microsoft Defender for Endpoint on macOS, execute the following command from a Terminal window:</span></span>

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a><span data-ttu-id="d2204-122">Настройка предпочтений для Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="d2204-122">Set preferences for Microsoft AutoUpdate</span></span>

<span data-ttu-id="d2204-123">В этом разделе описываются наиболее распространенные предпочтения, которые можно использовать для настройки MAU.</span><span class="sxs-lookup"><span data-stu-id="d2204-123">This section describes the most common preferences that can be used to configure MAU.</span></span> <span data-ttu-id="d2204-124">Эти параметры можно развернуть в качестве профиля конфигурации через консоль управления, которую использует ваше предприятие.</span><span class="sxs-lookup"><span data-stu-id="d2204-124">These settings can be deployed as a configuration profile through the management console that your enterprise is using.</span></span> <span data-ttu-id="d2204-125">Пример профиля конфигурации показан в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="d2204-125">An example of a configuration profile is shown in the following sections.</span></span>

### <a name="set-the-channel-name"></a><span data-ttu-id="d2204-126">Настройка имени канала</span><span class="sxs-lookup"><span data-stu-id="d2204-126">Set the channel name</span></span>

<span data-ttu-id="d2204-127">Канал определяет тип и частоту обновлений, предлагаемых через MAU.</span><span class="sxs-lookup"><span data-stu-id="d2204-127">The channel determines the type and frequency of updates that are offered through MAU.</span></span> <span data-ttu-id="d2204-128">Устройства в `Beta` может попробовать новые функции перед устройствами `Preview` в и `Current` .</span><span class="sxs-lookup"><span data-stu-id="d2204-128">Devices in `Beta` can try out new features before devices in `Preview` and `Current`.</span></span> 

<span data-ttu-id="d2204-129">Канал `Current` содержит наиболее стабильную версию продукта.</span><span class="sxs-lookup"><span data-stu-id="d2204-129">The `Current` channel contains the most stable version of the product.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="d2204-130">До версии Microsoft AutoUpdate 4.29 каналы имели разные имена:</span><span class="sxs-lookup"><span data-stu-id="d2204-130">Prior to Microsoft AutoUpdate version 4.29, channels had different names:</span></span> 
> 
> - <span data-ttu-id="d2204-131">`Beta` был назван `InsiderFast` (Insider Fast)</span><span class="sxs-lookup"><span data-stu-id="d2204-131">`Beta` was named `InsiderFast` (Insider Fast)</span></span>
> - <span data-ttu-id="d2204-132">`Preview` был назван `External` (Insider Slow)</span><span class="sxs-lookup"><span data-stu-id="d2204-132">`Preview` was named `External` (Insider Slow)</span></span>
> - <span data-ttu-id="d2204-133">`Current` был назван `Production`</span><span class="sxs-lookup"><span data-stu-id="d2204-133">`Current` was named `Production`</span></span>

>[!TIP]
><span data-ttu-id="d2204-134">Чтобы просмотреть новые функции и предоставить ранние отзывы, рекомендуется настроить некоторые устройства в вашем предприятии на `Beta` или `Preview` .</span><span class="sxs-lookup"><span data-stu-id="d2204-134">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to `Beta` or `Preview`.</span></span>

|<span data-ttu-id="d2204-135">Section</span><span class="sxs-lookup"><span data-stu-id="d2204-135">Section</span></span>|<span data-ttu-id="d2204-136">Значение</span><span class="sxs-lookup"><span data-stu-id="d2204-136">Value</span></span>|
|:--|:--|
| <span data-ttu-id="d2204-137">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d2204-137">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="d2204-138">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="d2204-138">**Key**</span></span> | <span data-ttu-id="d2204-139">ChannelName</span><span class="sxs-lookup"><span data-stu-id="d2204-139">ChannelName</span></span> |
| <span data-ttu-id="d2204-140">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d2204-140">**Data type**</span></span> | <span data-ttu-id="d2204-141">String</span><span class="sxs-lookup"><span data-stu-id="d2204-141">String</span></span> |
| <span data-ttu-id="d2204-142">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="d2204-142">**Possible values**</span></span> | <span data-ttu-id="d2204-143">Бета-версия</span><span class="sxs-lookup"><span data-stu-id="d2204-143">Beta</span></span> <br/> <span data-ttu-id="d2204-144">Предварительный просмотр</span><span class="sxs-lookup"><span data-stu-id="d2204-144">Preview</span></span> <br/> <span data-ttu-id="d2204-145">Current</span><span class="sxs-lookup"><span data-stu-id="d2204-145">Current</span></span> |
|||

>[!WARNING]
><span data-ttu-id="d2204-146">Этот параметр изменяет канал для всех приложений, которые обновляются с помощью Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="d2204-146">This setting changes the channel for all applications that are updated through Microsoft AutoUpdate.</span></span> <span data-ttu-id="d2204-147">Чтобы изменить канал только для Microsoft Defender для конечной точки на macOS, выполните следующую команду после замены `[channel-name]` на нужный канал:</span><span class="sxs-lookup"><span data-stu-id="d2204-147">To change the channel only for Microsoft Defender for Endpoint on macOS, execute the following command after replacing `[channel-name]` with the desired channel:</span></span>
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a><span data-ttu-id="d2204-148">Установите частоту проверки обновления</span><span class="sxs-lookup"><span data-stu-id="d2204-148">Set update check frequency</span></span>

<span data-ttu-id="d2204-149">Измените, как часто MAU выполняет поиск обновлений.</span><span class="sxs-lookup"><span data-stu-id="d2204-149">Change how often MAU searches for updates.</span></span>

|<span data-ttu-id="d2204-150">Section</span><span class="sxs-lookup"><span data-stu-id="d2204-150">Section</span></span>|<span data-ttu-id="d2204-151">Значение</span><span class="sxs-lookup"><span data-stu-id="d2204-151">Value</span></span>|
|:--|:--|
| <span data-ttu-id="d2204-152">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d2204-152">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="d2204-153">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="d2204-153">**Key**</span></span> | <span data-ttu-id="d2204-154">UpdateCheckFrequency</span><span class="sxs-lookup"><span data-stu-id="d2204-154">UpdateCheckFrequency</span></span> |
| <span data-ttu-id="d2204-155">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d2204-155">**Data type**</span></span> | <span data-ttu-id="d2204-156">Целое число</span><span class="sxs-lookup"><span data-stu-id="d2204-156">Integer</span></span> |
| <span data-ttu-id="d2204-157">**Значение, используемое по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="d2204-157">**Default value**</span></span> | <span data-ttu-id="d2204-158">720 (минут)</span><span class="sxs-lookup"><span data-stu-id="d2204-158">720 (minutes)</span></span> |
| <span data-ttu-id="d2204-159">**Comment**</span><span class="sxs-lookup"><span data-stu-id="d2204-159">**Comment**</span></span> | <span data-ttu-id="d2204-160">Это значение устанавливается в минутах.</span><span class="sxs-lookup"><span data-stu-id="d2204-160">This value is set in minutes.</span></span> |


### <a name="change-how-mau-interacts-with-updates"></a><span data-ttu-id="d2204-161">Изменение взаимодействия MAU с обновлениями</span><span class="sxs-lookup"><span data-stu-id="d2204-161">Change how MAU interacts with updates</span></span>

<span data-ttu-id="d2204-162">Измените, как MAU ищет обновления.</span><span class="sxs-lookup"><span data-stu-id="d2204-162">Change how MAU searches for updates.</span></span>

|<span data-ttu-id="d2204-163">Section</span><span class="sxs-lookup"><span data-stu-id="d2204-163">Section</span></span>|<span data-ttu-id="d2204-164">Значение</span><span class="sxs-lookup"><span data-stu-id="d2204-164">Value</span></span>|
|:--|:--|
| <span data-ttu-id="d2204-165">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d2204-165">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="d2204-166">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="d2204-166">**Key**</span></span> | <span data-ttu-id="d2204-167">HowToCheck</span><span class="sxs-lookup"><span data-stu-id="d2204-167">HowToCheck</span></span> |
| <span data-ttu-id="d2204-168">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d2204-168">**Data type**</span></span> | <span data-ttu-id="d2204-169">String</span><span class="sxs-lookup"><span data-stu-id="d2204-169">String</span></span> |
| <span data-ttu-id="d2204-170">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="d2204-170">**Possible values**</span></span> | <span data-ttu-id="d2204-171">Вручную</span><span class="sxs-lookup"><span data-stu-id="d2204-171">Manual</span></span> <br/> <span data-ttu-id="d2204-172">AutomaticCheck</span><span class="sxs-lookup"><span data-stu-id="d2204-172">AutomaticCheck</span></span> <br/> <span data-ttu-id="d2204-173">AutomaticDownload</span><span class="sxs-lookup"><span data-stu-id="d2204-173">AutomaticDownload</span></span> |
| <span data-ttu-id="d2204-174">**Comment**</span><span class="sxs-lookup"><span data-stu-id="d2204-174">**Comment**</span></span> |  <span data-ttu-id="d2204-175">Обратите внимание, что AutomaticDownload будет скачивать и устанавливать безмолвно, если это возможно.</span><span class="sxs-lookup"><span data-stu-id="d2204-175">Note that AutomaticDownload will do a download and install silently if possible.</span></span> |


### <a name="change-whether-the-check-for-updates-button-is-enabled"></a><span data-ttu-id="d2204-176">Измените, включена ли кнопка "Проверка обновлений"</span><span class="sxs-lookup"><span data-stu-id="d2204-176">Change whether the "Check for Updates" button is enabled</span></span>

<span data-ttu-id="d2204-177">Измените, смогут ли местные пользователи щелкнуть параметр "Проверка обновлений" в пользовательском интерфейсе Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="d2204-177">Change whether local users will be able to click the "Check for Updates" option in the Microsoft AutoUpdate user interface.</span></span>

|<span data-ttu-id="d2204-178">Section</span><span class="sxs-lookup"><span data-stu-id="d2204-178">Section</span></span>|<span data-ttu-id="d2204-179">Значение</span><span class="sxs-lookup"><span data-stu-id="d2204-179">Value</span></span>|
|:--|:--|
| <span data-ttu-id="d2204-180">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d2204-180">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="d2204-181">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="d2204-181">**Key**</span></span> | <span data-ttu-id="d2204-182">EnableCheckForUpdatesButton</span><span class="sxs-lookup"><span data-stu-id="d2204-182">EnableCheckForUpdatesButton</span></span> |
| <span data-ttu-id="d2204-183">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d2204-183">**Data type**</span></span> | <span data-ttu-id="d2204-184">Логический</span><span class="sxs-lookup"><span data-stu-id="d2204-184">Boolean</span></span> |
| <span data-ttu-id="d2204-185">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="d2204-185">**Possible values**</span></span> | <span data-ttu-id="d2204-186">True (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d2204-186">True (default)</span></span> <br/> <span data-ttu-id="d2204-187">False (Ложь)</span><span class="sxs-lookup"><span data-stu-id="d2204-187">False</span></span> |


### <a name="disable-insider-checkbox"></a><span data-ttu-id="d2204-188">Отключение почтового ящика Insider</span><span class="sxs-lookup"><span data-stu-id="d2204-188">Disable Insider checkbox</span></span>

<span data-ttu-id="d2204-189">Установите для true, чтобы сделать "Присоединиться к программе Office инсайдерской ..." checkbox недоступный или серый для пользователей.</span><span class="sxs-lookup"><span data-stu-id="d2204-189">Set to true to make the "Join the Office Insider Program..." checkbox unavailable / greyed out to users.</span></span>

|<span data-ttu-id="d2204-190">Section</span><span class="sxs-lookup"><span data-stu-id="d2204-190">Section</span></span>|<span data-ttu-id="d2204-191">Значение</span><span class="sxs-lookup"><span data-stu-id="d2204-191">Value</span></span>|
|:--|:--|
| <span data-ttu-id="d2204-192">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d2204-192">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="d2204-193">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="d2204-193">**Key**</span></span> | <span data-ttu-id="d2204-194">DisableInsiderCheckbox</span><span class="sxs-lookup"><span data-stu-id="d2204-194">DisableInsiderCheckbox</span></span> |
| <span data-ttu-id="d2204-195">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d2204-195">**Data type**</span></span> | <span data-ttu-id="d2204-196">Логический</span><span class="sxs-lookup"><span data-stu-id="d2204-196">Boolean</span></span> |
| <span data-ttu-id="d2204-197">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="d2204-197">**Possible values**</span></span> | <span data-ttu-id="d2204-198">False (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d2204-198">False (default)</span></span> <br/> <span data-ttu-id="d2204-199">True (Истина)</span><span class="sxs-lookup"><span data-stu-id="d2204-199">True</span></span> |


### <a name="limit-the-telemetry-that-is-sent-from-mau"></a><span data-ttu-id="d2204-200">Ограничение телеметрии, отправленной из MAU</span><span class="sxs-lookup"><span data-stu-id="d2204-200">Limit the telemetry that is sent from MAU</span></span>

<span data-ttu-id="d2204-201">Установите для отправки минимальные данные о сердцебиении, отсутствие использования приложений и отсутствие сведений об среде.</span><span class="sxs-lookup"><span data-stu-id="d2204-201">Set to false to send minimal heartbeat data, no application usage, and no environment details.</span></span>

|<span data-ttu-id="d2204-202">Section</span><span class="sxs-lookup"><span data-stu-id="d2204-202">Section</span></span>|<span data-ttu-id="d2204-203">Значение</span><span class="sxs-lookup"><span data-stu-id="d2204-203">Value</span></span>|
|:--|:--|
| <span data-ttu-id="d2204-204">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d2204-204">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="d2204-205">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="d2204-205">**Key**</span></span> | <span data-ttu-id="d2204-206">SendAllTelemetryEnabled</span><span class="sxs-lookup"><span data-stu-id="d2204-206">SendAllTelemetryEnabled</span></span> |
| <span data-ttu-id="d2204-207">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d2204-207">**Data type**</span></span> | <span data-ttu-id="d2204-208">Логический</span><span class="sxs-lookup"><span data-stu-id="d2204-208">Boolean</span></span> |
| <span data-ttu-id="d2204-209">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="d2204-209">**Possible values**</span></span> | <span data-ttu-id="d2204-210">True (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d2204-210">True (default)</span></span> <br/> <span data-ttu-id="d2204-211">False (Ложь)</span><span class="sxs-lookup"><span data-stu-id="d2204-211">False</span></span> |


## <a name="example-configuration-profile"></a><span data-ttu-id="d2204-212">Пример профиля конфигурации</span><span class="sxs-lookup"><span data-stu-id="d2204-212">Example configuration profile</span></span>

<span data-ttu-id="d2204-213">Следующий профиль конфигурации используется для:</span><span class="sxs-lookup"><span data-stu-id="d2204-213">The following configuration profile is used to:</span></span>
- <span data-ttu-id="d2204-214">Поместите устройство в канал Production</span><span class="sxs-lookup"><span data-stu-id="d2204-214">Place the device in the Production channel</span></span>
- <span data-ttu-id="d2204-215">Автоматическое скачивание и установка обновлений</span><span class="sxs-lookup"><span data-stu-id="d2204-215">Automatically download and install updates</span></span>
- <span data-ttu-id="d2204-216">Включить кнопку "Проверка обновлений" в пользовательском интерфейсе</span><span class="sxs-lookup"><span data-stu-id="d2204-216">Enable the "Check for updates" button in the user interface</span></span>
- <span data-ttu-id="d2204-217">Разрешить пользователям на устройстве зарегистрироваться в каналах Insider</span><span class="sxs-lookup"><span data-stu-id="d2204-217">Allow users on the device to enroll into the Insider channels</span></span>


>[!WARNING]
><span data-ttu-id="d2204-218">Приведенная ниже конфигурация — это пример конфигурации, которая не должна использоваться в производстве без надлежащего анализа параметров и настройки конфигураций.</span><span class="sxs-lookup"><span data-stu-id="d2204-218">The below configuration is an example configuration and should not be used in production without proper review of settings and tailor of configurations.</span></span>

>[!TIP]
><span data-ttu-id="d2204-219">Чтобы просмотреть новые функции и предоставить ранние отзывы, рекомендуется настроить некоторые устройства в вашем предприятии на `Beta` или `Preview` .</span><span class="sxs-lookup"><span data-stu-id="d2204-219">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to `Beta` or `Preview`.</span></span>

### <a name="jamf"></a><span data-ttu-id="d2204-220">JAMF</span><span class="sxs-lookup"><span data-stu-id="d2204-220">JAMF</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>ChannelName</key>
    <string>Production</string>
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

### <a name="intune"></a><span data-ttu-id="d2204-221">Intune</span><span class="sxs-lookup"><span data-stu-id="d2204-221">Intune</span></span>

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
            <string>Production</string>
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

<span data-ttu-id="d2204-222">Чтобы настроить MAU, вы можете развернуть этот профиль конфигурации из средства управления, которое использует ваше предприятие:</span><span class="sxs-lookup"><span data-stu-id="d2204-222">To configure MAU, you can deploy this configuration profile from the management tool that your enterprise is using:</span></span>
- <span data-ttu-id="d2204-223">Из JAMF загрузите этот профиль конфигурации и установите домен preference *на com.microsoft.autoupdate2.*</span><span class="sxs-lookup"><span data-stu-id="d2204-223">From JAMF, upload this configuration profile and set the Preference Domain to *com.microsoft.autoupdate2*.</span></span>
- <span data-ttu-id="d2204-224">В Intune загрузите этот профиль конфигурации и установите имя профиля настраиваемой конфигурации *на com.microsoft.autoupdate2.*</span><span class="sxs-lookup"><span data-stu-id="d2204-224">From Intune, upload this configuration profile and set the custom configuration profile name to *com.microsoft.autoupdate2*.</span></span>

## <a name="resources"></a><span data-ttu-id="d2204-225">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="d2204-225">Resources</span></span>

- [<span data-ttu-id="d2204-226">msupdate reference</span><span class="sxs-lookup"><span data-stu-id="d2204-226">msupdate reference</span></span>](/deployoffice/mac/update-office-for-mac-using-msupdate)
