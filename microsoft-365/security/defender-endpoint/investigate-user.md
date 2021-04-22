---
title: Исследование учетной записи пользователя в Microsoft Defender для конечной точки
description: Во время расследования изучите учетную запись пользователя на возможные скомпрометированные учетные данные или поворот на связанной учетной записи пользователя.
keywords: исследование, учетная запись, пользователь, сущность пользователя, оповещение, Microsoft Defender для конечной точки
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: e98142e4076c5e695f16eb06c062bc69d3d7dd55
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935069"
---
# <a name="investigate-a-user-account-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="7d698-104">Исследование учетной записи пользователя в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="7d698-104">Investigate a user account in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7d698-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="7d698-105">**Applies to:**</span></span>
- [<span data-ttu-id="7d698-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="7d698-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7d698-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7d698-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="7d698-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="7d698-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7d698-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="7d698-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatgeuser-abovefoldlink)

## <a name="investigate-user-account-entities"></a><span data-ttu-id="7d698-110">Изучение сущностями учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="7d698-110">Investigate user account entities</span></span>

<span data-ttu-id="7d698-111">Определите учетные записи пользователей с наиболее активными оповещениями (отображаемой на панели мониторинга как "Пользователи в опасности") и изучите случаи потенциального взлома учетных данных или сводки на связанной учетной записи пользователя при расследовании оповещения или устройства для определения возможного более позднего перемещения между устройствами с этой учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="7d698-111">Identify user accounts with the most active alerts (displayed on dashboard as "Users at risk") and investigate cases of potential compromised credentials, or pivot on the associated user account when investigating an alert or device to identify possible lateral movement between devices with that user account.</span></span>

<span data-ttu-id="7d698-112">Сведения о учетной записи пользователей можно найти в следующих представлениях:</span><span class="sxs-lookup"><span data-stu-id="7d698-112">You can find user account information in the following views:</span></span>

- <span data-ttu-id="7d698-113">Информационная панель</span><span class="sxs-lookup"><span data-stu-id="7d698-113">Dashboard</span></span>
- <span data-ttu-id="7d698-114">Очередь оповещений</span><span class="sxs-lookup"><span data-stu-id="7d698-114">Alert queue</span></span>
- <span data-ttu-id="7d698-115">Страница сведения об устройстве</span><span class="sxs-lookup"><span data-stu-id="7d698-115">Device details page</span></span>

<span data-ttu-id="7d698-116">В этих представлениях доступна щелкаемая ссылка учетной записи пользователя, которая будет отбирать вас на страницу сведений о учетной записи пользователя, где показано больше сведений о учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="7d698-116">A clickable user account link is available in these views, that will take you to the user account details page where more details about the user account are shown.</span></span>

<span data-ttu-id="7d698-117">При расследовании объекта учетной записи пользователя вы увидите:</span><span class="sxs-lookup"><span data-stu-id="7d698-117">When you investigate a user account entity, you'll see:</span></span>

- <span data-ttu-id="7d698-118">Сведения о учетной записи пользователя, оповещений Microsoft Defender для удостоверений и в журнале на устройствах, роли, типе логотипа и другие сведения</span><span class="sxs-lookup"><span data-stu-id="7d698-118">User account details, Microsoft Defender for Identity alerts, and logged on devices, role, logon type, and other details</span></span>
- <span data-ttu-id="7d698-119">Обзор инцидентов и устройств пользователя</span><span class="sxs-lookup"><span data-stu-id="7d698-119">Overview of the incidents and user's devices</span></span>
- <span data-ttu-id="7d698-120">Оповещений, связанных с этим пользователем</span><span class="sxs-lookup"><span data-stu-id="7d698-120">Alerts related to this user</span></span>
- <span data-ttu-id="7d698-121">Наблюдается в организации (устройства, входив в систему)</span><span class="sxs-lookup"><span data-stu-id="7d698-121">Observed in organization (devices logged on to)</span></span>

![Изображение страницы сведений об объекте учетной записи пользователя](images/atp-user-details-view.png)

### <a name="user-details"></a><span data-ttu-id="7d698-123">Сведения о пользователях</span><span class="sxs-lookup"><span data-stu-id="7d698-123">User details</span></span>

<span data-ttu-id="7d698-124">В  области сведений пользователя слева содержится информация о пользователе, например связанных открытых инцидентах, активных оповещений, имя SAM, SID, Microsoft Defender для удостоверений оповещений, количество устройств, на которые пользователь вошел, когда пользователь был первым и последним видел, роли и типы логотипов.</span><span class="sxs-lookup"><span data-stu-id="7d698-124">The **User details** pane on left provides information about the user, such as related open incidents, active alerts, SAM name, SID, Microsoft Defender for Identity alerts, number of devices the user is logged on to, when the user was first and last seen, role, and logon types.</span></span> <span data-ttu-id="7d698-125">В зависимости от функций интеграции, которые вы включили, вы увидите другие сведения.</span><span class="sxs-lookup"><span data-stu-id="7d698-125">Depending on the integration features you've enabled, you'll see other details.</span></span> <span data-ttu-id="7d698-126">Например, если вы включаете Skype для бизнес-интеграции, вы сможете связаться с пользователем с портала.</span><span class="sxs-lookup"><span data-stu-id="7d698-126">For example, if you enable the Skype for business integration, you'll be able to contact the user from the portal.</span></span> <span data-ttu-id="7d698-127">Раздел оповещений **ATP** Azure содержит ссылку на страницу Защитник Майкрософт для удостоверений, если включена функция Microsoft Defender для удостоверений, и есть оповещения, связанные с пользователем.</span><span class="sxs-lookup"><span data-stu-id="7d698-127">The **Azure ATP alerts** section contains a link that will take you to the Microsoft Defender for Identity page, if you have enabled the Microsoft Defender for Identity feature, and there are alerts related to the user.</span></span> <span data-ttu-id="7d698-128">На странице Защитник Майкрософт для удостоверений будут предоставляться дополнительные сведения о оповещениях.</span><span class="sxs-lookup"><span data-stu-id="7d698-128">The Microsoft Defender for Identity page will provide more information about the alerts.</span></span>

>[!NOTE]
><span data-ttu-id="7d698-129">Для использования этой функции необходимо включить интеграцию в Microsoft Defender for Identity и Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="7d698-129">You'll need to enable the integration on both Microsoft Defender for Identity and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="7d698-130">В Defender for Endpoint вы можете включить эту функцию в расширенных функциях.</span><span class="sxs-lookup"><span data-stu-id="7d698-130">In Defender for Endpoint, you can enable this feature in advanced features.</span></span> <span data-ttu-id="7d698-131">Дополнительные сведения о том, как включить расширенные функции, см. в дополнительных [сведениях.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="7d698-131">For more information on how to enable advanced features, see [Turn on advanced features](advanced-features.md).</span></span>

<span data-ttu-id="7d698-132">Обзор, оповещений и наблюдаемые в организации — это разные вкладки, на которые отображаются различные атрибуты учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="7d698-132">The Overview, Alerts, and Observed in organization are different tabs that display various attributes about the user account.</span></span>

### <a name="overview"></a><span data-ttu-id="7d698-133">Обзор</span><span class="sxs-lookup"><span data-stu-id="7d698-133">Overview</span></span>

<span data-ttu-id="7d698-134">На **вкладке Обзор** показаны сведения об инцидентах и список устройств, на которые входил пользователь.</span><span class="sxs-lookup"><span data-stu-id="7d698-134">The **Overview** tab shows the incidents details and a list of the devices that the user has logged on to.</span></span> <span data-ttu-id="7d698-135">Вы можете расширить их, чтобы увидеть сведения о событиях входа для каждого устройства.</span><span class="sxs-lookup"><span data-stu-id="7d698-135">You can expand these to see details of the log-on events for each device.</span></span>

### <a name="alerts"></a><span data-ttu-id="7d698-136">Оповещения</span><span class="sxs-lookup"><span data-stu-id="7d698-136">Alerts</span></span>

<span data-ttu-id="7d698-137">Вкладка **Alerts** содержит список оповещений, связанных с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="7d698-137">The **Alerts** tab provides a list of alerts that are associated with the user account.</span></span> <span data-ttu-id="7d698-138">Этот список представляет фильтрованное представление очереди Оповещения [и](alerts-queue.md)показывает оповещения, в которых контекст пользователя — это выбранная учетная запись пользователя, дата обнаружения последнего действия, краткое описание оповещений, устройство, связанное с оповещением, серьезность оповещений, состояние оповещений в очереди и назначенное оповещение.</span><span class="sxs-lookup"><span data-stu-id="7d698-138">This list is a filtered view of the [Alert queue](alerts-queue.md), and shows alerts where the user context is the selected user account, the date when the last activity was detected, a short description of the alert, the device associated with the alert, the alert's severity, the alert's status in the queue, and who is assigned the alert.</span></span>

### <a name="observed-in-organization"></a><span data-ttu-id="7d698-139">Наблюдается в организации</span><span class="sxs-lookup"><span data-stu-id="7d698-139">Observed in organization</span></span>

<span data-ttu-id="7d698-140">Вкладка **Observed** в организации позволяет указать диапазон дат, чтобы увидеть список устройств, на которых был зарегистрирован этот пользователь, наиболее частые и наименее часто регистрируются в учетной записи пользователя для каждого из этих устройств, а также общее число наблюдаемых пользователей на каждом устройстве.</span><span class="sxs-lookup"><span data-stu-id="7d698-140">The **Observed in organization** tab allows you to specify a date range to see a list of devices where this user was observed logged on to, the most frequent and least frequent logged on user account for each of these devices, and total observed users on each device.</span></span>

<span data-ttu-id="7d698-141">Выбор элемента в таблице "Наблюдаемые" расширит элемент, раскроет дополнительные сведения об устройстве.</span><span class="sxs-lookup"><span data-stu-id="7d698-141">Selecting an item on the Observed in organization table will expand the item, revealing more details about the device.</span></span> <span data-ttu-id="7d698-142">Непосредственно выбрав ссылку в элементе, вышлет вас на соответствующую страницу.</span><span class="sxs-lookup"><span data-stu-id="7d698-142">Directly selecting a link within an item will send you to the corresponding page.</span></span>

## <a name="search-for-specific-user-accounts"></a><span data-ttu-id="7d698-143">Поиск определенных учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="7d698-143">Search for specific user accounts</span></span>

1. <span data-ttu-id="7d698-144">Выберите **пользователя** из **выпадаемого** меню панели поиска.</span><span class="sxs-lookup"><span data-stu-id="7d698-144">Select **User** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="7d698-145">Введите учетную запись пользователя в **поле Поиска.**</span><span class="sxs-lookup"><span data-stu-id="7d698-145">Enter the user account in the **Search** field.</span></span>
3. <span data-ttu-id="7d698-146">Щелкните значок поиска или нажмите **кнопку Ввод**.</span><span class="sxs-lookup"><span data-stu-id="7d698-146">Click the search icon or press **Enter**.</span></span>

<span data-ttu-id="7d698-147">Отображается список пользователей, совпадающих с текстом запроса.</span><span class="sxs-lookup"><span data-stu-id="7d698-147">A list of users matching the query text is displayed.</span></span> <span data-ttu-id="7d698-148">Вы увидите домен и имя учетной записи пользователя, когда учетная запись пользователя была в последний раз замечена, и общее число устройств, на которые она была зарегистрирована, за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="7d698-148">You'll see the user account's domain and name, when the user account was last seen, and the total number of devices it was observed logged on to in the last 30 days.</span></span>

<span data-ttu-id="7d698-149">Результаты можно фильтровать по следующим периодам времени:</span><span class="sxs-lookup"><span data-stu-id="7d698-149">You can filter the results by the following time periods:</span></span>

- <span data-ttu-id="7d698-150">1 день</span><span class="sxs-lookup"><span data-stu-id="7d698-150">1 day</span></span>
- <span data-ttu-id="7d698-151">за 3 дня;</span><span class="sxs-lookup"><span data-stu-id="7d698-151">3 days</span></span>
- <span data-ttu-id="7d698-152">7 дней</span><span class="sxs-lookup"><span data-stu-id="7d698-152">7 days</span></span>
- <span data-ttu-id="7d698-153">30 дней</span><span class="sxs-lookup"><span data-stu-id="7d698-153">30 days</span></span>
- <span data-ttu-id="7d698-154">6 месяцев</span><span class="sxs-lookup"><span data-stu-id="7d698-154">6 months</span></span>

## <a name="related-topics"></a><span data-ttu-id="7d698-155">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="7d698-155">Related topics</span></span>

- [<span data-ttu-id="7d698-156">Просмотр и организация очереди оповещений Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="7d698-156">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="7d698-157">Управление оповещениями Защитника Майкрософт для конечных точек</span><span class="sxs-lookup"><span data-stu-id="7d698-157">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="7d698-158">Исследование оповещений Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="7d698-158">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="7d698-159">Исследование файла, связанного с предупреждением Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7d698-159">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="7d698-160">Исследование устройств в списке устройств Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="7d698-160">Investigate devices in the Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="7d698-161">Исследование IP-адреса, связанного с оповещением Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7d698-161">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="7d698-162">Исследование домена, связанного с предупреждением Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7d698-162">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
