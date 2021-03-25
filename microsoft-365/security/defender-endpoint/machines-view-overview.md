---
title: Просмотр и организация списка устройств ATP Защитника Майкрософт
description: Узнайте о доступных функций, которые можно использовать из списка Устройств, таких как сортировка, фильтрация и экспорт списка для расширения исследований.
keywords: сортировка, фильтрация, экспорт, csv, имя устройства, домен, последний увиденный, внутренний IP, состояние здоровья, активные оповещения, активные обнаружения вредоносных программ, категория угроз, оповещения о просмотре, сеть, подключение, вредоносные программы, тип, похититель паролей, вымогатель, эксплойт, угроза, общее вредоносное ПО, нежелательное программное обеспечение
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 01ad9f92299cd9d1b4a723bdec54f86f32ca8274
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076582"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-devices-list"></a><span data-ttu-id="8130b-104">Просмотр и организация списка конечных устройств Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="8130b-104">View and organize the Microsoft Defender for Endpoint Devices list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8130b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="8130b-105">**Applies to:**</span></span>
- [<span data-ttu-id="8130b-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="8130b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="8130b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8130b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8130b-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="8130b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8130b-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="8130b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-machinesview-abovefoldlink)


<span data-ttu-id="8130b-110">В **списке Устройств** показан список устройств в сети, на которых были созданы оповещения.</span><span class="sxs-lookup"><span data-stu-id="8130b-110">The **Devices list** shows a list of the devices in your network where alerts were generated.</span></span> <span data-ttu-id="8130b-111">По умолчанию в очереди отображаются устройства, замеченные за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="8130b-111">By default, the queue displays devices seen in the last 30 days.</span></span>  

<span data-ttu-id="8130b-112">С первого взгляда вы увидите такие сведения, как домен, уровень риска, платформа ОС и другие сведения для легкой идентификации устройств, наиболее опасных.</span><span class="sxs-lookup"><span data-stu-id="8130b-112">At a glance you'll see information such as domain, risk level, OS platform, and other details for easy identification of devices most at risk.</span></span>

<span data-ttu-id="8130b-113">Существует несколько вариантов настройки представления списка устройств.</span><span class="sxs-lookup"><span data-stu-id="8130b-113">There are several options you can choose from to customize the devices list view.</span></span> <span data-ttu-id="8130b-114">В верхней части навигации можно:</span><span class="sxs-lookup"><span data-stu-id="8130b-114">On the top navigation you can:</span></span>

- <span data-ttu-id="8130b-115">Добавление или удаление столбцов</span><span class="sxs-lookup"><span data-stu-id="8130b-115">Add or remove columns</span></span>
- <span data-ttu-id="8130b-116">Экспортировать весь список в формате CSV</span><span class="sxs-lookup"><span data-stu-id="8130b-116">Export the entire list in CSV format</span></span>
- <span data-ttu-id="8130b-117">Выберите количество элементов, которые будут показываться на странице</span><span class="sxs-lookup"><span data-stu-id="8130b-117">Select the number of items to show per page</span></span>
- <span data-ttu-id="8130b-118">Применение фильтров</span><span class="sxs-lookup"><span data-stu-id="8130b-118">Apply filters</span></span>

<span data-ttu-id="8130b-119">Во время процесса вмеяния список **Устройств** постепенно заполняется устройствами по мере того, как они начинают сообщать данные датчиков.</span><span class="sxs-lookup"><span data-stu-id="8130b-119">During the onboarding process, the **Devices list** is gradually populated with devices as they begin to report sensor data.</span></span> <span data-ttu-id="8130b-120">Используйте это представление для отслеживания бортовых конечных точек по мере их подключения к сети или скачивания полного списка конечных точек в качестве CSV-файла для автономного анализа.</span><span class="sxs-lookup"><span data-stu-id="8130b-120">Use this view to track your onboarded endpoints as they come online, or download the complete endpoint list as a CSV file for offline analysis.</span></span>

>[!NOTE]
> <span data-ttu-id="8130b-121">Если вы экспортируете список устройств, он будет содержать каждое устройство в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="8130b-121">If you export the device list, it will contain every device in your organization.</span></span> <span data-ttu-id="8130b-122">Загрузка может занять значительное количество времени в зависимости от размера организации.</span><span class="sxs-lookup"><span data-stu-id="8130b-122">It might take a significant amount of time to download, depending on how large your organization is.</span></span> <span data-ttu-id="8130b-123">Экспорт списка в формате CSV отображает данные в неотобраченном виде.</span><span class="sxs-lookup"><span data-stu-id="8130b-123">Exporting the list in CSV format displays the data in an unfiltered manner.</span></span> <span data-ttu-id="8130b-124">CSV-файл будет включать все устройства в организации, независимо от фильтрации, применяемой в представлении.</span><span class="sxs-lookup"><span data-stu-id="8130b-124">The CSV file will include all devices in the organization, regardless of any filtering applied in the view itself.</span></span>

![Изображение списка устройств со списком устройств](images/device-list.png)

## <a name="sort-and-filter-the-device-list"></a><span data-ttu-id="8130b-126">Сортировка и фильтрация списка устройств</span><span class="sxs-lookup"><span data-stu-id="8130b-126">Sort and filter the device list</span></span>

<span data-ttu-id="8130b-127">Вы можете применить следующие фильтры, чтобы ограничить список оповещений и получить более целенаправленное представление.</span><span class="sxs-lookup"><span data-stu-id="8130b-127">You can apply the following filters to limit the list of alerts and get a more focused view.</span></span>

### <a name="risk-level"></a><span data-ttu-id="8130b-128">Уровень риска</span><span class="sxs-lookup"><span data-stu-id="8130b-128">Risk level</span></span>

<span data-ttu-id="8130b-129">Уровень риска отражает общую оценку риска устройства на основе сочетания факторов, включая типы и серьезность активных оповещений на устройстве.</span><span class="sxs-lookup"><span data-stu-id="8130b-129">The risk level reflects the overall risk assessment of the device based on a combination of factors, including the types and severity of active alerts on the device.</span></span> <span data-ttu-id="8130b-130">Решение активных оповещений, одобрение действий по исправлению и подавление последующих оповещений могут снизить уровень риска.</span><span class="sxs-lookup"><span data-stu-id="8130b-130">Resolving active alerts, approving remediation activities, and suppressing subsequent alerts can lower the risk level.</span></span>

### <a name="exposure-level"></a><span data-ttu-id="8130b-131">Уровень экспозиции</span><span class="sxs-lookup"><span data-stu-id="8130b-131">Exposure level</span></span>

<span data-ttu-id="8130b-132">Уровень экспозиции отражает текущее воздействие устройства на основе совокупного воздействия ожидающих рекомендаций по безопасности.</span><span class="sxs-lookup"><span data-stu-id="8130b-132">The exposure level reflects the current exposure of the device based on the cumulative impact of its pending security recommendations.</span></span> <span data-ttu-id="8130b-133">Возможные уровни являются низкими, средними и высокими.</span><span class="sxs-lookup"><span data-stu-id="8130b-133">The possible levels are low, medium, and high.</span></span> <span data-ttu-id="8130b-134">Низкая экспозиция означает, что ваши устройства менее уязвимы от эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="8130b-134">Low exposure means your devices are less vulnerable from exploitation.</span></span>

<span data-ttu-id="8130b-135">Если на уровне экспозиции написано "Нет данных", существует несколько причин, по которым это может быть так:</span><span class="sxs-lookup"><span data-stu-id="8130b-135">If the exposure level says "No data available," there are a few reasons why this may be the case:</span></span>

- <span data-ttu-id="8130b-136">Устройство перестало отчитываться более чем на 30 дней — в этом случае оно считается неактивным, а экспозиция не вычисляется</span><span class="sxs-lookup"><span data-stu-id="8130b-136">Device stopped reporting for more than 30 days – in that case it is considered inactive, and the exposure isn't computed</span></span>
- <span data-ttu-id="8130b-137">Ос-устройства не поддерживается - см. [минимальные требования к Microsoft Defender для конечной точки](minimum-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="8130b-137">Device OS not supported - see [minimum requirements for Microsoft Defender for Endpoint](minimum-requirements.md)</span></span>
- <span data-ttu-id="8130b-138">Устройство со устаревшим агентом (очень маловероятно)</span><span class="sxs-lookup"><span data-stu-id="8130b-138">Device with stale agent (very unlikely)</span></span>

### <a name="os-platform"></a><span data-ttu-id="8130b-139">Платформа ОС</span><span class="sxs-lookup"><span data-stu-id="8130b-139">OS Platform</span></span>

<span data-ttu-id="8130b-140">Выберите только платформы ОС, которые вам интересны в расследовании.</span><span class="sxs-lookup"><span data-stu-id="8130b-140">Select only the OS platforms you're interested in investigating.</span></span>

### <a name="health-state"></a><span data-ttu-id="8130b-141">Состояние работоспособности</span><span class="sxs-lookup"><span data-stu-id="8130b-141">Health state</span></span>

<span data-ttu-id="8130b-142">Фильтр по следующим состояниям состояния здоровья устройства:</span><span class="sxs-lookup"><span data-stu-id="8130b-142">Filter by the following device health states:</span></span>

- <span data-ttu-id="8130b-143">**Active** — устройства, которые активно сообщают данные датчиков службе.</span><span class="sxs-lookup"><span data-stu-id="8130b-143">**Active** – Devices that are actively reporting sensor data to the service.</span></span>
- <span data-ttu-id="8130b-144">**Неактивные** — устройства, которые перестали отправлять сигналы более 7 дней.</span><span class="sxs-lookup"><span data-stu-id="8130b-144">**Inactive** – Devices that have completely stopped sending signals for more than 7 days.</span></span>
- <span data-ttu-id="8130b-145">**Неправильное устройство** — устройства с нарушениями связи со службой или не могут отправлять данные датчиков.</span><span class="sxs-lookup"><span data-stu-id="8130b-145">**Misconfigured** – Devices that have impaired communications with service or are unable to send sensor data.</span></span> <span data-ttu-id="8130b-146">Неправильное устройство можно далее классифицировать так:</span><span class="sxs-lookup"><span data-stu-id="8130b-146">Misconfigured devices can further be classified to:</span></span>
  - <span data-ttu-id="8130b-147">Нет данных датчика</span><span class="sxs-lookup"><span data-stu-id="8130b-147">No sensor data</span></span>
  - <span data-ttu-id="8130b-148">Нарушение связи</span><span class="sxs-lookup"><span data-stu-id="8130b-148">Impaired communications</span></span>

  <span data-ttu-id="8130b-149">Дополнительные сведения о том, как устранять проблемы на неправильном устройстве, см. в выпуске [Исправление нездоровых датчиков.](fix-unhealthy-sensors.md)</span><span class="sxs-lookup"><span data-stu-id="8130b-149">For more information on how to address issues on misconfigured devices see, [Fix unhealthy sensors](fix-unhealthy-sensors.md).</span></span>

### <a name="antivirus-status"></a><span data-ttu-id="8130b-150">Состояние антивируса</span><span class="sxs-lookup"><span data-stu-id="8130b-150">Antivirus status</span></span>

<span data-ttu-id="8130b-151">Фильтруем устройства по статусу антивируса.</span><span class="sxs-lookup"><span data-stu-id="8130b-151">Filter devices by antivirus status.</span></span> <span data-ttu-id="8130b-152">Применяется только к активным устройствам с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="8130b-152">Applies to active Windows 10 devices only.</span></span>

- <span data-ttu-id="8130b-153">**Отключено** — & отключается защита от угроз.</span><span class="sxs-lookup"><span data-stu-id="8130b-153">**Disabled** - Virus & threat protection is turned off.</span></span>
- <span data-ttu-id="8130b-154">**Не сообщается** . & защиты от угрозы не сообщается.</span><span class="sxs-lookup"><span data-stu-id="8130b-154">**Not reporting** - Virus & threat protection is not reporting.</span></span>
- <span data-ttu-id="8130b-155">**Не обновляется** . & защита от угроз не обновлена.</span><span class="sxs-lookup"><span data-stu-id="8130b-155">**Not updated** - Virus & threat protection is not up to date.</span></span>

<span data-ttu-id="8130b-156">Дополнительные сведения см. в странице Просмотр панели управления & [уязвимостей.](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="8130b-156">For more information, see [View the Threat & Vulnerability Management dashboard](tvm-dashboard-insights.md).</span></span>

### <a name="threat-mitigation-status"></a><span data-ttu-id="8130b-157">Состояние смягчения угроз</span><span class="sxs-lookup"><span data-stu-id="8130b-157">Threat mitigation status</span></span>

<span data-ttu-id="8130b-158">Чтобы просмотреть устройства, на которые может повлиять определенная угроза, выберите угрозу из меню отсев, а затем выберите аспект уязвимости, который необходимо смягчить.</span><span class="sxs-lookup"><span data-stu-id="8130b-158">To view devices that may be affected by a certain threat, select the threat from the dropdown menu, and then select what vulnerability aspect needs to be mitigated.</span></span>

<span data-ttu-id="8130b-159">Дополнительные данные об определенных угрозах см. в [обзоре Аналитика угроз.](threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="8130b-159">To learn more about certain threats, see [Threat analytics](threat-analytics.md).</span></span> <span data-ttu-id="8130b-160">Сведения о смягчении последствий см. в [& Threat & vulnerability Management.](next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="8130b-160">For mitigation information, see [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span>

### <a name="windows-10-version"></a><span data-ttu-id="8130b-161">Версия Windows 10</span><span class="sxs-lookup"><span data-stu-id="8130b-161">Windows 10 version</span></span>

<span data-ttu-id="8130b-162">Выберите только интересующие вас версии Windows 10.</span><span class="sxs-lookup"><span data-stu-id="8130b-162">Select only the Windows 10 versions you're interested in investigating.</span></span>

### <a name="tags--groups"></a><span data-ttu-id="8130b-163">Теги & группы</span><span class="sxs-lookup"><span data-stu-id="8130b-163">Tags & Groups</span></span>

<span data-ttu-id="8130b-164">Фильтрация списка на основе группировки и тегов, добавленных на отдельные устройства.</span><span class="sxs-lookup"><span data-stu-id="8130b-164">Filter the list based on the grouping and tagging that you've added to individual devices.</span></span> <span data-ttu-id="8130b-165">См. [в рубке Создание и управление тегами устройств,](machine-tags.md) [а также создание и управление группами устройств.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="8130b-165">See [Create and manage device tags](machine-tags.md) and [Create and manage device groups](machine-groups.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8130b-166">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8130b-166">Related topics</span></span>

- [<span data-ttu-id="8130b-167">Исследование устройств в списке Устройств конечных точек Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="8130b-167">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
