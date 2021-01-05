---
title: Маршрутка сети с учетом информации Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/22/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Маршрутка сети с учетом информации Microsoft 365
ms.openlocfilehash: 367f83684a4a200e3ddd630e1412c756d7093da1
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749555"
---
# <a name="microsoft-365-informed-network-routing-preview"></a><span data-ttu-id="7e7b6-103">Маршрутная сеть с учетом информации Microsoft 365 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="7e7b6-103">Microsoft 365 informed network routing (preview)</span></span>

<span data-ttu-id="7e7b6-104">Проинформируемая маршрутизируемая сеть — это функция, которая интегрирует различные приложения Microsoft 365 со сторонними решениями для программно-определяемой сети (SD-WAN), чтобы оптимизировать и улучшить сетевое подключение к конечным точкам служб Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-104">Informed network routing is a feature that integrates various Microsoft 365 applications with third party software defined network (SD-WAN) solutions in order to optimize and improve your network connectivity to Microsoft service endpoints.</span></span> <span data-ttu-id="7e7b6-105">Оптимизированная связь SD-WAN может улучшить взаимодействие с пользователем и повысить производительность.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-105">Optimized SD-WAN connectivity may result in improved user experiences and performance.</span></span>

>[!IMPORTANT]
><span data-ttu-id="7e7b6-106">В настоящее время маршрутия сети с предварительной версией Microsoft 365 находится в состоянии предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-106">Microsoft 365 informed network routing is currently in preview status.</span></span> <span data-ttu-id="7e7b6-107">Дополнительные сведения об этой предварительной версии, включая рекомендации по получении помощи, см. в руководстве по маршрутиации сети с открытой предварительной версией [Microsoft 365.](https://go.microsoft.com/fwlink/?linkid=2151565)</span><span class="sxs-lookup"><span data-stu-id="7e7b6-107">For more information on this preview including guidance for receiving assistance, see [Microsoft 365 informed network routing Public Preview](https://go.microsoft.com/fwlink/?linkid=2151565).</span></span>

## <a name="overview"></a><span data-ttu-id="7e7b6-108">Обзор</span><span class="sxs-lookup"><span data-stu-id="7e7b6-108">Overview</span></span>

<span data-ttu-id="7e7b6-109">Маршрутная маршрутка по сети обеспечивает двунаправленный канал общего доступа к данным между корпорацией Майкрософт и вашим решением SD-WAN.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-109">Informed network routing provides a bi-directional data sharing channel between Microsoft and your SD-WAN solution.</span></span> <span data-ttu-id="7e7b6-110">Майкрософт периодически делится с решением SD-WAN отзывами о качестве выбранных приложений Microsoft 365 для сетевого трафика, связанного с каждой конкретной интернет-каналом.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-110">For every office location and Internet circuit that you configure, Microsoft periodically shares feedback with the SD-WAN solution on the quality of selected Microsoft 365 application experiences for network traffic associated with each specific Internet circuit.</span></span> <span data-ttu-id="7e7b6-111">Используя эту обратную связь, решение SD-WAN может затем принять интеллектуальные действия по восстановлению, перенанося трафик приложений Microsoft 365 по альтернативным доступным ссылкам.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-111">Using this feedback, the SD-WAN solution may then take smart recovery actions by routing Microsoft 365 application traffic through alternate available links.</span></span> 

<span data-ttu-id="7e7b6-112">Снижение качества обслуживания на пути к определенной сети Интернета, например увеличение задержки или высокая потеря пакетов, трудно определить на постоянной основе.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-112">Quality of service degradations in the path of a particular Internet circuit such as increased latency or high packet loss are difficult to detect on a continuous basis.</span></span> <span data-ttu-id="7e7b6-113">Это может отрицательно сказаться на пользовательском интерфейсе таких приложений, как Exchange Online, SharePoint, OneDrive и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-113">These degradations may be detrimental to user experiences for applications such as Exchange Online, SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="7e7b6-114">К распространенным симптомам относятся медленный поиск контента Exchange, высокое время передачи при взаимодействии с библиотеками документов SharePoint или OneDrive, а также неудовлетворительные вызовы или качество собраний в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-114">Common symptoms include slow search of Exchange content, high transfer times when interacting with SharePoint or OneDrive document libraries, or poor call or meeting quality in Microsoft Teams.</span></span>

<span data-ttu-id="7e7b6-115">Механизм обратной связи и восстановления в сетевой маршрутике с информированием направлен на динамическое обнаружение таких проблем почти в режиме реального времени и информирует развернутое решение SD-WAN о том, что необходимо принять меры по автоматическому восстановлению.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-115">The feedback and recovery mechanism within network informed routing seeks to dynamically detect such issues in near real time and informs the deployed SD-WAN solution to take automatic recovery actions.</span></span>

<span data-ttu-id="7e7b6-116">Канал общего доступа к данным также используется для периодического получения данных оптики на уровне сети из решения SD-WAN, включая сведения о конфигурации и статистику использования, связанную с устройством и подключенными каналами.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-116">The data sharing channel is also used to periodically receive network-level optics data from the SD-WAN solution, including configuration information and usage statistics associated with the device and attached circuits.</span></span> <span data-ttu-id="7e7b6-117">Персональные данные не собираются и не хранятся.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-117">No personal information is collected or stored.</span></span> <span data-ttu-id="7e7b6-118">Вся собранная информация агрегируется по расположениям офисов и подключенным интернет-схемам.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-118">All collected information is aggregated to office locations and connected Internet circuits.</span></span> <span data-ttu-id="7e7b6-119">Эти сведения могут помочь корпорации Майкрософт более эффективно и эффективно устранять проблемы, о чем сообщается, при использовании служб и приложений Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-119">This information can help Microsoft more efficiently and effectively resolve reported issues with your use of Microsoft 365 services and applications.</span></span>

>[!NOTE]
><span data-ttu-id="7e7b6-120">Маршрутизации сети Microsoft 365 с поддержкой клиентов в коммерческом облаке WW, но не в облаке GCC Moderate, GCC High, DoD, Germany или Китае.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-120">Microsoft 365 informed network routing supports tenants in WW Commercial cloud but not the GCC Moderate, GCC High, DoD, Germany, or China clouds.</span></span>

## <a name="requirements"></a><span data-ttu-id="7e7b6-121">Требования</span><span class="sxs-lookup"><span data-stu-id="7e7b6-121">Requirements</span></span>

### <a name="integrated-sd-wan-solutions"></a><span data-ttu-id="7e7b6-122">Интегрированные решения SD-WAN</span><span class="sxs-lookup"><span data-stu-id="7e7b6-122">Integrated SD-WAN solutions</span></span>

<span data-ttu-id="7e7b6-123">Корпорация Майкрософт совместно с различными партнерами обеспечивает интеграцию с маршрутией сети с учетом информации о Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-123">Microsoft is working with various partners to enable integration with Microsoft 365 informed network routing.</span></span> <span data-ttu-id="7e7b6-124">В настоящее время включены следующие решения:</span><span class="sxs-lookup"><span data-stu-id="7e7b6-124">Currently enabled solutions include the following:</span></span>

| <span data-ttu-id="7e7b6-125">Device Maker</span><span class="sxs-lookup"><span data-stu-id="7e7b6-125">Device Maker</span></span> | <span data-ttu-id="7e7b6-126">Имя решения</span><span class="sxs-lookup"><span data-stu-id="7e7b6-126">Solution Name</span></span> | <span data-ttu-id="7e7b6-127">Минимальная версия</span><span class="sxs-lookup"><span data-stu-id="7e7b6-127">Minimum Version</span></span> |
| --- | --- | --- |
| <span data-ttu-id="7e7b6-128">Cisco</span><span class="sxs-lookup"><span data-stu-id="7e7b6-128">Cisco</span></span> | [<span data-ttu-id="7e7b6-129">IOS XE SD-WAN</span><span class="sxs-lookup"><span data-stu-id="7e7b6-129">IOS XE SD-WAN</span></span>](https://go.microsoft.com/fwlink/?linkid=2151460) | <span data-ttu-id="7e7b6-130">20.4/17.4</span><span class="sxs-lookup"><span data-stu-id="7e7b6-130">20.4/17.4</span></span> |

### <a name="network-topology"></a><span data-ttu-id="7e7b6-131">топологию сети; </span><span class="sxs-lookup"><span data-stu-id="7e7b6-131">Network topology</span></span>

<span data-ttu-id="7e7b6-132">В настоящее время в маршруте по сети в сети определяется трафик, связанный с определенным расположением офиса и интернет-каналом, на основе общего IP-адреса, используемого для отправки сетевого трафика в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-132">Informed network routing currently identifies traffic associated with a specific office location and Internet circuit based on the public IP address used to send network traffic to Microsoft.</span></span> 

<span data-ttu-id="7e7b6-133">Если в филиале нет по крайней мере одной сетевой схемы, предоставляющая прямой доступ к Интернету, маршрутная маршрутная маршрутка с данными по сети может не иметь значительного значения.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-133">In the case where there is not at least one network circuit providing direct Internet access at a branch location, network informed routing may not provide significant value.</span></span>

### <a name="application-usage"></a><span data-ttu-id="7e7b6-134">Использование приложений</span><span class="sxs-lookup"><span data-stu-id="7e7b6-134">Application usage</span></span>

<span data-ttu-id="7e7b6-135">Данные о работе с приложениями (отражаются с помощью метрик качества сети) собираются с помощью Microsoft Outlook на устройствах под управлением Windows, Teams, SharePoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-135">Application experience data (reflected through network quality metrics) is collected through usage of Microsoft Outlook on devices running Windows, Teams, SharePoint, and OneDrive.</span></span> <span data-ttu-id="7e7b6-136">При оценке состояния сетевой сети другой трафик приложений не рассматривается.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-136">Other application traffic is not considered when evaluating the health of a network circuit.</span></span>

## <a name="enabling-informed-network-routing"></a><span data-ttu-id="7e7b6-137">Включение маршрутов в сети с использованием информации</span><span class="sxs-lookup"><span data-stu-id="7e7b6-137">Enabling informed network routing</span></span>

<span data-ttu-id="7e7b6-138">Для включения маршрутов в сети с учетом информации требуется выполнить несколько действий, некоторые из которых необходимо выполнить в интерфейсе конфигурации решения SD-WAN.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-138">Enabling informed network routing requires multiple steps, some of which will need to be performed within the configuration interface of your SD-WAN solution.</span></span> <span data-ttu-id="7e7b6-139">Обратитесь к поставщику решения SD-WAN, чтобы получить инструкции по инициации процесса включения сетевой маршрутизации в решении SD-WAN, прежде чем приступить к настройке в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-139">Consult your SD-WAN solution vendor for guidance on how to initiate the process of enabling network informed routing within the SD-WAN solution before proceeding with configuration in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="7e7b6-140">После того как вы будете готовы включить маршрутику по сети в Центре администрирования Microsoft 365, убедитесь, что у вас есть необходимые разрешения глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-140">Once you are ready to enable informed network routing in the Microsoft 365 admin center, ensure you have the necessary global administrator permissions.</span></span>

>[!IMPORTANT]
><span data-ttu-id="7e7b6-141">Чтобы предоставить приложению на уровне клиента необходимые разрешения для выбранного решения SD-WAN на доступ к каналу общего доступа к данным маршрутной маршрутки в сети, необходимо выполнить следующие действия в качестве глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-141">In order to provide the necessary tenant-level applications permissions consent for the selected SD-WAN solution to access the informed network routing data sharing channel, you must perform the following steps as a global administrator.</span></span>


### <a name="step-1-open-sd-wan-solution-configuration-options"></a><span data-ttu-id="7e7b6-142">Шаг 1. Открытие параметров конфигурации решения SD-WAN</span><span class="sxs-lookup"><span data-stu-id="7e7b6-142">Step 1: Open SD-WAN solution configuration options</span></span>

<span data-ttu-id="7e7b6-143">В Центре [администрирования Microsoft 365](https://admin.microsoft.com/)выберите "Health **> Network connectivity" (Подключение** к сети) в области навигации слева.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-143">In the [Microsoft 365 admin center](https://admin.microsoft.com/), select **Health > Network connectivity** in the left-hand navigation pane.</span></span>

<span data-ttu-id="7e7b6-144">В этом разделе Центра администрирования приводится сводная метрика сетевого подключения для вашей организации и рекомендации по улучшению подключения.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-144">This section of the admin center provides aggregated network connectivity metrics for your organization and guidance on how to improve your connectivity.</span></span> <span data-ttu-id="7e7b6-145">Дополнительные сведения об этих функциях, доступных в Центре администрирования [Microsoft 365,](office-365-network-mac-perf-overview.md) см. в центре администрирования Microsoft 365 (предварительная версия).</span><span class="sxs-lookup"><span data-stu-id="7e7b6-145">See [Network connectivity in the Microsoft 365 Admin Center (preview)](office-365-network-mac-perf-overview.md) for additional information on these features available within the admin center.</span></span>

<span data-ttu-id="7e7b6-146">Выберите **параметры > SD-WAN,** чтобы открыть области конфигурации маршрутов сети.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-146">Select **Settings > SD-WAN solution** to open the informed network routing configuration pane.</span></span> <span data-ttu-id="7e7b6-147">Другие параметры,  которые отображаются в параметрах, применимы к общему руководству по сетевому подключению в Центре администрирования и не требуются для обеспечения маршрутации по сети.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-147">The other options that appear under **Settings** are applicable to the general network connectivity guidance in the admin center and are not required to enable informed network routing.</span></span>

<span data-ttu-id="7e7b6-148">В области конфигурации выберите "Добавить **решение SD-WAN (предварительная версия)".**</span><span class="sxs-lookup"><span data-stu-id="7e7b6-148">In the configuration pane, select **Add your SD-WAN solution (Preview)**.</span></span>

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a><span data-ttu-id="7e7b6-149">Шаг 2. Выбор решения SD-WAN и расположения для хранения данных</span><span class="sxs-lookup"><span data-stu-id="7e7b6-149">Step 2: Select your SD-WAN solution and data storage location</span></span>

<span data-ttu-id="7e7b6-150">В выпадающих полях выберите развернутые решения SD-WAN и расположение, в котором будут храниться данные, связанные с маршрутирой с данными о сети.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-150">In the drop-down boxes, select the SD-WAN solution you have deployed and the location where you wish to have the data associated with network informed routing stored.</span></span> <span data-ttu-id="7e7b6-151">Дополнительные [сведения см.](#data-storage) в разделе хранилища данных.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-151">See the [data storage](#data-storage) section for additional information.</span></span>

<span data-ttu-id="7e7b6-152">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-152">Select **Next**.</span></span>

### <a name="step-3-accept-terms-for-sharing-of-data"></a><span data-ttu-id="7e7b6-153">Шаг 3. Принятие условий для общего доступа к данным</span><span class="sxs-lookup"><span data-stu-id="7e7b6-153">Step 3: Accept terms for sharing of data</span></span>

<span data-ttu-id="7e7b6-154">Внимательно прочитайте и подтвердите предоставленные условия, связанные с обменом данными между Корпорацией Майкрософт и выбранным решением SD-WAN, а затем выберите указанный контрольный ящик.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-154">Carefully read and acknowledge the provided terms associated with sharing data between Microsoft and your selected SD-WAN solution, and then select the indicated checkbox.</span></span>

<span data-ttu-id="7e7b6-155">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-155">Select **Next**.</span></span>

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a><span data-ttu-id="7e7b6-156">Шаг 4. Предоставление разрешений для решения SD-WAN</span><span class="sxs-lookup"><span data-stu-id="7e7b6-156">Step 4: Grant permissions to the SD-WAN solution</span></span>

<span data-ttu-id="7e7b6-157">На этом этапе будет инициирован запрос на предоставление разрешений в Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="7e7b6-157">This step will initiate a permissions grant request with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="7e7b6-158">Вам будет запросят предоставить разрешения на уровне клиента, которые позволяют выбранному решению SD-WAN получать доступ к хранилищу данных маршрутной маршрутки в сети, а также сведения о состоянии службы, связанные с клиентом.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-158">You will be requested to grant tenant-level permissions that allow your selected SD-WAN solution access to the informed network routing data storage and the service health information associated with your tenant.</span></span> <span data-ttu-id="7e7b6-159">Для этого действия требуются разрешения роли глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-159">This action requires global administrator role permissions.</span></span>

<span data-ttu-id="7e7b6-160">Выберите **ссылку "Предоставить разрешение для этого** приложения" и следуйте запросам Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-160">Select the **Give permission to this application** link and follow the Azure AD requests.</span></span>

<span data-ttu-id="7e7b6-161">После предоставления разрешений выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="7e7b6-161">Once you have completed the permissions grant, select **Next**.</span></span>

### <a name="step-5-confirm-your-configuration-settings"></a><span data-ttu-id="7e7b6-162">Шаг 5. Подтверждение параметров конфигурации</span><span class="sxs-lookup"><span data-stu-id="7e7b6-162">Step 5: Confirm your configuration settings</span></span>

<span data-ttu-id="7e7b6-163">Последний шаг в включите маршрутику с использованием сетевой информации для клиента — это страница подтверждения, на которую будут отображаться предоставленные параметры.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-163">The final step in enabling network informed routing for your tenant is a confirmation page that displays the settings you've provided.</span></span> 

<span data-ttu-id="7e7b6-164">Теперь для клиента включена маршрутная маршрутка по сети.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-164">Informed network routing is now enabled for your tenant.</span></span>

<span data-ttu-id="7e7b6-165">Выберите **"Готово",** а затем закроем области конфигурации решения SD-WAN.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-165">Select **Done** and then close the SD-WAN solution configuration pane.</span></span>

## <a name="configuring-network-informed-routing"></a><span data-ttu-id="7e7b6-166">Настройка сетевой маршрутной маршрутки</span><span class="sxs-lookup"><span data-stu-id="7e7b6-166">Configuring network informed routing</span></span>

<span data-ttu-id="7e7b6-167">В решении SD-WAN будет выполняться большая часть конфигурации маршрутов сети, например настройка маршрутов трафика в обычных условиях и альтернативные пути, которые следует использовать при обнаружении проблем.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-167">You will perform much of the configuration for informed network routing within your SD-WAN solution, such as configuring how your traffic should be routed under normal circumstances and the alternate paths that should be used if issues are detected.</span></span> <span data-ttu-id="7e7b6-168">Подробные сведения об этих действиях по настройке можно получить у поставщика решений SD-WAN.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-168">Consult your SD-WAN solution provider for details on these configuration steps.</span></span>

<span data-ttu-id="7e7b6-169">Каждое расположение офиса должно быть настроено в Центре администрирования Microsoft 365, чтобы маршруты в сети могли правильно определять трафик, связанный с сетевыми каналами, обеспечивающими подключение к этим расположениям.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-169">Each office location must be configured in the Microsoft 365 admin center so that informed network routing can properly identify traffic associated with the network circuits providing connectivity to these locations.</span></span>

<span data-ttu-id="7e7b6-170">Расположения Office могут быть автоматически обнаружены как часть текущей коллекции телеметрии сети корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-170">Office locations may be auto-detected as part of Microsoft's ongoing collection of network telemetry.</span></span> <span data-ttu-id="7e7b6-171">В результате некоторые расположения могут быть предварительно заполнены в Центре администрирования вашего клиента.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-171">As a result, some locations may be pre-populated in the admin center for your tenant.</span></span> 

<span data-ttu-id="7e7b6-172">Если эти расположения точны, необходимо просто включить функцию маршрутации сети для каждого нужного расположения и настроить интернет-цепи и их общедоступные IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-172">If these locations are accurate, you will simply need to enable the informed network routing feature for each desired location and configure the Internet circuits and their public IP addresses.</span></span> 

<span data-ttu-id="7e7b6-173">Если автоматически обнаруженные расположения не точны или в клиенте нет предварительно заполненных местоположений, вам придется добавить или изменить расположения вручную, чтобы отразить точную топологию организации.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-173">If the auto-detected locations are not accurate, or there are no locations pre-populated in your tenant, you will have to add or edit locations manually to reflect an accurate topology of your organization.</span></span>

### <a name="updating-locations"></a><span data-ttu-id="7e7b6-174">Обновление местоположений</span><span class="sxs-lookup"><span data-stu-id="7e7b6-174">Updating locations</span></span>

<span data-ttu-id="7e7b6-175">Расположения клиента можно найти на вкладке **"Расположения".** Расположения могут изменяться непосредственно в списке или обновляться с помощью CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-175">Locations for your tenant can be found under the **Locations** tab. Locations may be edited directly in the list or updated using a CSV file.</span></span>

<span data-ttu-id="7e7b6-176">Убедитесь, что в этом списке присутствует каждое расположение офиса, в котором вы хотите включить маршрутику в сети.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-176">Ensure that each office location where you wish to enable informed network routing is present in this list.</span></span>

>[!NOTE]
><span data-ttu-id="7e7b6-177">Столбцы в списке **"Расположения"** для собранных примеров и других сведений, связанных с оценкой, не связаны с функцией маршрутации в сети.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-177">The columns in the **Locations** list for samples collected and other assessment-related information are not related to the informed network routing feature.</span></span>

### <a name="enabling-a-location-for-informed-network-routing"></a><span data-ttu-id="7e7b6-178">Включение расположения для маршрутки в сети с использованием информации</span><span class="sxs-lookup"><span data-stu-id="7e7b6-178">Enabling a location for informed network routing</span></span>

1. <span data-ttu-id="7e7b6-179">В **списке "Расположения"** выберите **"Изменить"** в меню быстрых действий, чтобы открыть области конфигурации расположения.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-179">In the **Locations** list, select **Edit** from the quick actions menu to open the location configuration pane.</span></span>

2. <span data-ttu-id="7e7b6-180">Выберите "Использовать маршрутику сети с учетом **информации Microsoft 365" в этом расположении.**</span><span class="sxs-lookup"><span data-stu-id="7e7b6-180">Select **Use Microsoft 365 informed network routing at this location**.</span></span>

3. <span data-ttu-id="7e7b6-181">Добавьте все сетевые сети, обеспечивающие подключение к Интернету, в это расположение офиса в диапазонах IP-адресов **egress** в этом разделе расположения офиса.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-181">Add all network circuits providing Internet connectivity to this office location in the **Egress IP Address ranges at this office location** section.</span></span> <span data-ttu-id="7e7b6-182">Убедитесь, что каждая схема связана с уникальными подсетями общедоступных IP-адресов, представляющими сетевой трафик.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-182">Ensure that each circuit is associated with the unique public IP address subnets representing your network traffic.</span></span>

4. <span data-ttu-id="7e7b6-183">Нажмите кнопку **Сохранить**, чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-183">Select **Save** to save your changes.</span></span>

## <a name="disabling-network-informed-routing"></a><span data-ttu-id="7e7b6-184">Отключение сетевой маршрутной маршрутки</span><span class="sxs-lookup"><span data-stu-id="7e7b6-184">Disabling network informed routing</span></span>

<span data-ttu-id="7e7b6-185">Функция маршрутки в сети может быть отключена для всего клиента путем сброса параметров решения SD-WAN.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-185">The informed network routing feature may be disabled for the entire tenant by resetting your SD-WAN solution settings.</span></span> <span data-ttu-id="7e7b6-186">Хотя это остановит всю обработку данных в Microsoft 365, вы также должны отключить маршрутику с учетом сетевых данных в Центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-186">While this will stop all processing of data within Microsoft 365, you should also disable network informed routing within the admin center.</span></span>

### <a name="step-1-open-sd-wan-solution-configuration-options"></a><span data-ttu-id="7e7b6-187">Шаг 1. Открытие параметров конфигурации решения SD-WAN</span><span class="sxs-lookup"><span data-stu-id="7e7b6-187">Step 1: Open SD-WAN solution configuration options</span></span>

<span data-ttu-id="7e7b6-188">В Центре [администрирования Microsoft 365](https://admin.microsoft.com/) выберите **"Health > Network connectivity" (Подключение** к сети) в области навигации слева.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-188">In the [Microsoft 365 admin center](https://admin.microsoft.com/) select **Health > Network connectivity** in the left-hand navigation pane.</span></span>

<span data-ttu-id="7e7b6-189">Выберите **параметры > SD-WAN,** чтобы открыть области конфигурации маршрутов сети.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-189">Select **Settings > SD-WAN solution** to open the informed network routing configuration pane.</span></span>

<span data-ttu-id="7e7b6-190">В области конфигурации показана сводка настроенного в настоящее время решения SD-WAN.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-190">The configuration pane shows a summary of your currently configured SD-WAN solution.</span></span>

### <a name="step-2-reset-your-configuration"></a><span data-ttu-id="7e7b6-191">Шаг 2. Сброс конфигурации</span><span class="sxs-lookup"><span data-stu-id="7e7b6-191">Step 2: Reset your configuration</span></span>

<span data-ttu-id="7e7b6-192">В области конфигурации выберите **"Сброс параметров решения SD-WAN".**</span><span class="sxs-lookup"><span data-stu-id="7e7b6-192">In the configuration pane, select **Reset your SD-WAN solution settings**.</span></span>

<span data-ttu-id="7e7b6-193">Теперь параметры были сброшены, а маршрутная маршрутка по сети отключена.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-193">Your settings have now been reset and informed network routing has been disabled.</span></span> <span data-ttu-id="7e7b6-194">Вы можете повторно включить его в любое время, вы следуя шагам, которые необходимо включить в маршруте [по](#enabling-informed-network-routing)сети.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-194">You can re-enable it at any time by following the steps in [Enabling informed network routing](#enabling-informed-network-routing).</span></span>

## <a name="data-storage"></a><span data-ttu-id="7e7b6-195">Хранилище данных</span><span class="sxs-lookup"><span data-stu-id="7e7b6-195">Data storage</span></span>

<span data-ttu-id="7e7b6-196">Данные, обмениваются данными между корпорацией Майкрософт и поставщиком решений SD-WAN, хранятся в расположении хранения данных, выбранном во время первоначальной реализации сетевой маршрутной маршрутации.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-196">Data exchanged between Microsoft and the SD-WAN solution provider is stored in the data storage location selected during the initial enablement of network informed routing.</span></span> <span data-ttu-id="7e7b6-197">Параметры расположения для хранения данных представляют географические области, содержащие регионы Microsoft Azure, в которых хранятся данные.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-197">The data storage location options represent geographical areas containing Microsoft Azure regions where the data is stored.</span></span>

>[!NOTE]
><span data-ttu-id="7e7b6-198">На этапе предварительного просмотра единственным доступным местом хранения данных является **Северная Америка.**</span><span class="sxs-lookup"><span data-stu-id="7e7b6-198">During the Preview phase, the only available data storage location is **North America**.</span></span> <span data-ttu-id="7e7b6-199">Дополнительные места хранения данных станут доступны до общедоступной маршрутиации по сети.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-199">Additional data storage locations will become available prior to the general availability of informed network routing.</span></span>

<span data-ttu-id="7e7b6-200">Данные сохраняются в этом расположении в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-200">Data is retained in this location for up to 30 days.</span></span> <span data-ttu-id="7e7b6-201">Если этот срок отключен, все оставшиеся данные удаляются в течение 30-дневного времени хранения.</span><span class="sxs-lookup"><span data-stu-id="7e7b6-201">When disabled, all remaining data is removed within this 30-day retention window.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7e7b6-202">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="7e7b6-202">Related topics</span></span>

[<span data-ttu-id="7e7b6-203">Сетевое подключение в Центре администрирования Microsoft 365 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="7e7b6-203">Network connectivity in the Microsoft 365 admin center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="7e7b6-204">Microsoft 365 Network Connectivity Location Services (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="7e7b6-204">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
