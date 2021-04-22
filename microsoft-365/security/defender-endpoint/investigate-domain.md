---
title: Исследование доменов Microsoft Defender для доменов конечных точек
description: Используйте параметры исследования, чтобы узнать, связывались ли устройства и серверы с вредоносными доменами.
keywords: исследование домена, домена, вредоносного домена, Microsoft Defender для конечной точки, оповещения, URL-адреса
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
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 7826229ba67384137c033745a5b85e557fc9c4a7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933473"
---
# <a name="investigate-a-domain-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="8390d-104">Исследование домена, связанного с оповещением Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8390d-104">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8390d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="8390d-105">**Applies to:**</span></span>
- [<span data-ttu-id="8390d-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="8390d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8390d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8390d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="8390d-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="8390d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8390d-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="8390d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatedomain-abovefoldlink) 

<span data-ttu-id="8390d-110">Изучите домен, чтобы узнать, связывались ли устройства и серверы в корпоративной сети с известным вредоносным доменом.</span><span class="sxs-lookup"><span data-stu-id="8390d-110">Investigate a domain to see if devices and servers in your enterprise network have been communicating with a known malicious domain.</span></span>

<span data-ttu-id="8390d-111">Вы можете исследовать домен с помощью функции поиска или нажав на доменную ссылку из временной шкалы **Устройства.**</span><span class="sxs-lookup"><span data-stu-id="8390d-111">You can investigate a domain by using the search feature or by clicking on a domain link from the **Device timeline**.</span></span>

<span data-ttu-id="8390d-112">В представлении URL-адреса можно увидеть сведения из следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="8390d-112">You can see information from the following sections in the URL view:</span></span>

- <span data-ttu-id="8390d-113">Url-адрес, контакты, nameservers</span><span class="sxs-lookup"><span data-stu-id="8390d-113">URL details, Contacts, Nameservers</span></span>
- <span data-ttu-id="8390d-114">Оповещений, связанных с этим URL-адресом</span><span class="sxs-lookup"><span data-stu-id="8390d-114">Alerts related to this URL</span></span> 
- <span data-ttu-id="8390d-115">URL-адрес в организации</span><span class="sxs-lookup"><span data-stu-id="8390d-115">URL in organization</span></span>
- <span data-ttu-id="8390d-116">Самые последние наблюдаемые устройства с URL-адресом</span><span class="sxs-lookup"><span data-stu-id="8390d-116">Most recent observed devices with URL</span></span>

## <a name="url-worldwide"></a><span data-ttu-id="8390d-117">URL-адрес по всему миру</span><span class="sxs-lookup"><span data-stu-id="8390d-117">URL worldwide</span></span>

<span data-ttu-id="8390d-118">В **разделе URL-адрес Worldwide** перечислены URL-адрес, ссылка на дополнительные сведения в Whois, количество связанных открытых инцидентов и количество активных оповещений.</span><span class="sxs-lookup"><span data-stu-id="8390d-118">The **URL Worldwide** section lists the URL, a link to further details at Whois, the number of related open incidents, and the number of active alerts.</span></span>

## <a name="incident"></a><span data-ttu-id="8390d-119">Инцидент</span><span class="sxs-lookup"><span data-stu-id="8390d-119">Incident</span></span>

<span data-ttu-id="8390d-120">Карта **Incident** отображает планку всех активных оповещений в инцидентах за последние 180 дней.</span><span class="sxs-lookup"><span data-stu-id="8390d-120">The **Incident** card displays a bar chart of all active alerts in incidents over the past 180 days.</span></span>

## <a name="prevalence"></a><span data-ttu-id="8390d-121">Распространенность</span><span class="sxs-lookup"><span data-stu-id="8390d-121">Prevalence</span></span>

<span data-ttu-id="8390d-122">Карта **"Распространенность"** содержит сведения о распространенности URL-адреса в организации в течение определенного периода времени.</span><span class="sxs-lookup"><span data-stu-id="8390d-122">The **Prevalence** card provides details on the prevalence of the URL within the organization, over a specified period of time.</span></span>

<span data-ttu-id="8390d-123">Хотя по умолчанию период времени составляет последние 30 дней, вы можете настроить диапазон, выбрав стрелку вниз в углу карты.</span><span class="sxs-lookup"><span data-stu-id="8390d-123">Although the default time period is the past 30 days, you can customize the range by selecting the downward-pointing arrow in the corner of the card.</span></span> <span data-ttu-id="8390d-124">Самый короткий диапазон, доступный для распространения за прошедший день, в то время как самый длинный диапазон за последние 6 месяцев.</span><span class="sxs-lookup"><span data-stu-id="8390d-124">The shortest range available is for prevalence over the past day, while the longest range is over the past 6 months.</span></span>

## <a name="alerts"></a><span data-ttu-id="8390d-125">Оповещения</span><span class="sxs-lookup"><span data-stu-id="8390d-125">Alerts</span></span>

<span data-ttu-id="8390d-126">Вкладка **Alerts** содержит список оповещений, связанных с URL-адресом.</span><span class="sxs-lookup"><span data-stu-id="8390d-126">The **Alerts** tab provides a list of alerts that are associated with the URL.</span></span> <span data-ttu-id="8390d-127">Показанная здесь таблица — это отфильтровываемая версия оповещений, видимых на экране очереди оповещения, в которой отображаются только оповещения, связанные с доменом, их серьезность, состояние, связанный инцидент, классификация, состояние расследования и другие.</span><span class="sxs-lookup"><span data-stu-id="8390d-127">The table shown here is a filtered version of the alerts visible on the Alert queue screen, showing only alerts associated with the domain, their severity, status, the associated incident, classification, investigation state, and more.</span></span>

<span data-ttu-id="8390d-128">Вкладка Оповещений может быть скорректирована для показа более или менее сведений путем выбора столбцов настройки из меню действий над загонами столбцов. </span><span class="sxs-lookup"><span data-stu-id="8390d-128">The Alerts tab can be adjusted to show more or less information, by selecting **Customize columns** from the action menu above the column headers.</span></span> <span data-ttu-id="8390d-129">Количество отображаемого пунктов также можно откорректировать, выбрав элементы на одну страницу **в** том же меню.</span><span class="sxs-lookup"><span data-stu-id="8390d-129">The number of items displayed can also be adjusted, by selecting **items per page** on the same menu.</span></span>

## <a name="observed-in-organization"></a><span data-ttu-id="8390d-130">Наблюдается в организации</span><span class="sxs-lookup"><span data-stu-id="8390d-130">Observed in organization</span></span>

<span data-ttu-id="8390d-131">Вкладка **Observed в организации** предоставляет хронологическое представление событий и связанных оповещений, которые наблюдались на URL-адресе.</span><span class="sxs-lookup"><span data-stu-id="8390d-131">The **Observed in organization** tab provides a chronological view on the events and associated alerts that were observed on the URL.</span></span> <span data-ttu-id="8390d-132">Эта вкладка включает в себя хронологию и настраиваемую таблицу сведений о событиях, таких как время, устройство и краткое описание произошедшего.</span><span class="sxs-lookup"><span data-stu-id="8390d-132">This tab includes a timeline and a customizable table listing event details, such as the time, device, and a brief description of what happened.</span></span> 

<span data-ttu-id="8390d-133">Вы можете просмотреть события из разных периодов времени, введя даты в текстовые поля над заглавами таблицы.</span><span class="sxs-lookup"><span data-stu-id="8390d-133">You can view events from different periods of time by entering the dates into the text fields above the table headers.</span></span> <span data-ttu-id="8390d-134">Вы также можете настроить диапазон времени, выбрав различные области временной шкалы.</span><span class="sxs-lookup"><span data-stu-id="8390d-134">You can also customize the time range by selecting different areas of the timeline.</span></span>

<span data-ttu-id="8390d-135">**Исследование домена:**</span><span class="sxs-lookup"><span data-stu-id="8390d-135">**Investigate a domain:**</span></span>

1. <span data-ttu-id="8390d-136">Выберите **URL-адрес** **из** выпадаемого меню панели поиска.</span><span class="sxs-lookup"><span data-stu-id="8390d-136">Select **URL** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="8390d-137">Введите URL-адрес в **поле Поиска.**</span><span class="sxs-lookup"><span data-stu-id="8390d-137">Enter the URL in the **Search** field.</span></span>
3. <span data-ttu-id="8390d-138">Щелкните значок поиска или нажмите **кнопку Ввод**.</span><span class="sxs-lookup"><span data-stu-id="8390d-138">Click the search icon   or press **Enter**.</span></span> <span data-ttu-id="8390d-139">Отображаются сведения о URL-адресе.</span><span class="sxs-lookup"><span data-stu-id="8390d-139">Details about the URL are displayed.</span></span> <span data-ttu-id="8390d-140">Примечание. Результаты поиска будут возвращены только для URL-адресов, наблюдаемых в сообщениях с устройств в организации.</span><span class="sxs-lookup"><span data-stu-id="8390d-140">Note: search results will only be returned for URLs observed in communications from devices in the organization.</span></span>
4. <span data-ttu-id="8390d-141">Для определения критериев поиска используйте фильтры поиска.</span><span class="sxs-lookup"><span data-stu-id="8390d-141">Use the search filters to define the search criteria.</span></span> <span data-ttu-id="8390d-142">Вы также можете использовать поле поиска по временной шкале, чтобы отфильтровать отображаемые результаты всех устройств в организации, наблюдающих связь с URL-адресом, файлом, связанным с сообщением, и последней датой.</span><span class="sxs-lookup"><span data-stu-id="8390d-142">You can also use the timeline search box to filter the displayed results of all devices in the organization observed communicating with the URL, the file associated with the communication and the last date observed.</span></span>
5. <span data-ttu-id="8390d-143">Щелкнув любое из имен устройств, вы сможете просмотреть представление этого устройства, где можно продолжить изучение сообщений о оповещениях, поведении и событиях.</span><span class="sxs-lookup"><span data-stu-id="8390d-143">Clicking any of the device names will take you to that device's view, where you can continue investigate reported alerts, behaviors, and events.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8390d-144">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="8390d-144">Related topics</span></span>
- [<span data-ttu-id="8390d-145">Просмотр и организация очереди оповещений Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="8390d-145">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="8390d-146">Управление оповещениями Защитника Майкрософт для конечных точек</span><span class="sxs-lookup"><span data-stu-id="8390d-146">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="8390d-147">Исследование оповещений Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="8390d-147">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="8390d-148">Исследование файла, связанного с оповещением Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="8390d-148">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="8390d-149">Исследование устройств в списке Устройств конечных точек Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="8390d-149">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="8390d-150">Исследование IP-адреса, связанного с оповещением Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8390d-150">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="8390d-151">Исследование учетной записи пользователя в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="8390d-151">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
