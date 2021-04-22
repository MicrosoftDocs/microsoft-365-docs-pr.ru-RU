---
title: Исследование IP-адреса, связанного с оповещением
description: Используйте параметры исследования для изучения возможной связи между устройствами и внешними IP-адресами.
keywords: исследование, исследование, IP-адрес, оповещение, Microsoft Defender для конечной точки, внешний IP
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
ms.openlocfilehash: cb95deb890b52f0f5fde26a3a193181713b8ae5f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933833"
---
# <a name="investigate-an-ip-address-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="fc7c2-104">Исследование IP-адреса, связанного с оповещением Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fc7c2-104">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="fc7c2-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="fc7c2-105">**Applies to:**</span></span>
- [<span data-ttu-id="fc7c2-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="fc7c2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fc7c2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fc7c2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="fc7c2-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="fc7c2-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fc7c2-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="fc7c2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="fc7c2-110">Изучите возможную связь между устройствами и внешними IP-адресами протокола Интернета.</span><span class="sxs-lookup"><span data-stu-id="fc7c2-110">Examine possible communication between your devices and external internet protocol (IP) addresses.</span></span>

<span data-ttu-id="fc7c2-111">Определение всех устройств в организации, которые связывались с подозрительным или известным вредоносным IP-адресом, например серверами Command and Control (C2), помогает определить потенциальные области нарушения, связанные файлы и зараженные устройства.</span><span class="sxs-lookup"><span data-stu-id="fc7c2-111">Identifying all devices in the organization that communicated with a suspected or known malicious IP address, such as Command and Control (C2) servers, helps determine the potential scope of breach, associated files, and infected devices.</span></span>

<span data-ttu-id="fc7c2-112">Сведения из следующих разделов можно найти в представлении IP-адресов:</span><span class="sxs-lookup"><span data-stu-id="fc7c2-112">You can find information from the following sections in the IP address view:</span></span>

- <span data-ttu-id="fc7c2-113">IP во всем мире</span><span class="sxs-lookup"><span data-stu-id="fc7c2-113">IP worldwide</span></span>
- <span data-ttu-id="fc7c2-114">Обратные имена DNS</span><span class="sxs-lookup"><span data-stu-id="fc7c2-114">Reverse DNS names</span></span>
- <span data-ttu-id="fc7c2-115">Оповещений, связанных с этим IP</span><span class="sxs-lookup"><span data-stu-id="fc7c2-115">Alerts related to this IP</span></span>
- <span data-ttu-id="fc7c2-116">IP в организации</span><span class="sxs-lookup"><span data-stu-id="fc7c2-116">IP in organization</span></span>
- <span data-ttu-id="fc7c2-117">Распространенность</span><span class="sxs-lookup"><span data-stu-id="fc7c2-117">Prevalence</span></span>

## <a name="ip-worldwide-and-reverse-dns-names"></a><span data-ttu-id="fc7c2-118">Ip Worldwide и обратные имена DNS</span><span class="sxs-lookup"><span data-stu-id="fc7c2-118">IP Worldwide and Reverse DNS names</span></span>

<span data-ttu-id="fc7c2-119">В разделе сведения об IP-адресе показаны атрибуты IP-адреса, такие как ASN и имена обратных DNS.</span><span class="sxs-lookup"><span data-stu-id="fc7c2-119">The IP address details section shows attributes of the IP address such as its ASN and its Reverse DNS names.</span></span>

## <a name="alerts-related-to-this-ip"></a><span data-ttu-id="fc7c2-120">Оповещений, связанных с этим IP</span><span class="sxs-lookup"><span data-stu-id="fc7c2-120">Alerts related to this IP</span></span>

<span data-ttu-id="fc7c2-121">**Оповещений, связанных с этим** ip-разделом, содержится список оповещений, связанных с IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="fc7c2-121">The **Alerts related to this IP** section provides a list of alerts that are associated with the IP.</span></span>

## <a name="ip-in-organization"></a><span data-ttu-id="fc7c2-122">IP в организации</span><span class="sxs-lookup"><span data-stu-id="fc7c2-122">IP in organization</span></span>

<span data-ttu-id="fc7c2-123">В **разделе IP в организации** приводится подробная информация о распространенности IP-адреса в организации.</span><span class="sxs-lookup"><span data-stu-id="fc7c2-123">The **IP in organization** section provides details on the prevalence of the IP address in the organization.</span></span>

## <a name="prevalence"></a><span data-ttu-id="fc7c2-124">Распространенность</span><span class="sxs-lookup"><span data-stu-id="fc7c2-124">Prevalence</span></span>

<span data-ttu-id="fc7c2-125">В **разделе "Распространенность"** отображается количество устройств, подключенных к этому IP-адресу, а также время первого и последнего отображения IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="fc7c2-125">The **Prevalence** section displays how many devices have connected to this IP address, and when the IP was first and last seen.</span></span> <span data-ttu-id="fc7c2-126">Результаты этого раздела можно отфильтровать по времени; по умолчанию — 30 дней.</span><span class="sxs-lookup"><span data-stu-id="fc7c2-126">You can filter the results of this section by time period; the default period is 30 days.</span></span>

## <a name="most-recent-observed-devices-with-ip"></a><span data-ttu-id="fc7c2-127">Самые последние наблюдаемые устройства с IP</span><span class="sxs-lookup"><span data-stu-id="fc7c2-127">Most recent observed devices with IP</span></span>

<span data-ttu-id="fc7c2-128">Последние **наблюдаемые устройства** с разделом IP предоставляют хронологическое представление о событиях и связанных оповещениях, которые наблюдались на IP-адресе.</span><span class="sxs-lookup"><span data-stu-id="fc7c2-128">The **Most recent observed devices** with IP section provides a chronological view on the events and associated alerts that were observed on the IP address.</span></span>

<span data-ttu-id="fc7c2-129">**Исследование внешнего IP-адреса:**</span><span class="sxs-lookup"><span data-stu-id="fc7c2-129">**Investigate an external IP:**</span></span>

1. <span data-ttu-id="fc7c2-130">Выберите **IP-адрес** **из** выпадаемого меню панели поиска.</span><span class="sxs-lookup"><span data-stu-id="fc7c2-130">Select **IP** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="fc7c2-131">Введите IP-адрес в **поле Поиска.**</span><span class="sxs-lookup"><span data-stu-id="fc7c2-131">Enter the IP address in the **Search** field.</span></span>
3. <span data-ttu-id="fc7c2-132">Щелкните значок поиска или нажмите **кнопку Ввод**.</span><span class="sxs-lookup"><span data-stu-id="fc7c2-132">Click the search icon or press **Enter**.</span></span>

<span data-ttu-id="fc7c2-133">Отображаются сведения об IP-адресе, в том числе: сведения о регистрации (при наличии), обратные IP-адреса (например, домены), распространенность устройств в организации, связывающихся с этим IP-адресом (в течение определенного периода времени), а также устройства в организации, наблюдаемые при общении с этим IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="fc7c2-133">Details about the IP address are displayed, including: registration details (if available), reverse IPs (for example, domains), prevalence of devices in the organization that communicated with this IP Address (during selectable time period), and the devices in the organization that were observed communicating with this IP address.</span></span>

> [!NOTE]
> <span data-ttu-id="fc7c2-134">Результаты поиска будут возвращены только для IP-адресов, наблюдаемых при общении с устройствами в организации.</span><span class="sxs-lookup"><span data-stu-id="fc7c2-134">Search results will only be returned for IP addresses observed in communication with devices in the organization.</span></span>

<span data-ttu-id="fc7c2-135">Для определения критериев поиска используйте фильтры поиска.</span><span class="sxs-lookup"><span data-stu-id="fc7c2-135">Use the search filters to define the search criteria.</span></span> <span data-ttu-id="fc7c2-136">Вы также можете использовать поле поиска по временной шкале, чтобы отфильтровать отображаемые результаты всех устройств в организации, наблюдающих связь с IP-адресом, файлом, связанным с сообщением, и последней датой.</span><span class="sxs-lookup"><span data-stu-id="fc7c2-136">You can also use the timeline search box to filter the displayed results of all devices in the organization observed communicating with the IP address, the file associated with the communication and the last date observed.</span></span>

<span data-ttu-id="fc7c2-137">Щелкнув любое из имен устройств, вы сможете просмотреть представление этого устройства, где можно продолжить изучение сообщений о оповещениях, поведении и событиях.</span><span class="sxs-lookup"><span data-stu-id="fc7c2-137">Clicking any of the device names will take you to that device's view, where you can continue investigate reported alerts, behaviors, and events.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fc7c2-138">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="fc7c2-138">Related topics</span></span>

- [<span data-ttu-id="fc7c2-139">Просмотр и организация очереди оповещений Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="fc7c2-139">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="fc7c2-140">Управление оповещениями Защитника Майкрософт для конечных точек</span><span class="sxs-lookup"><span data-stu-id="fc7c2-140">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="fc7c2-141">Исследование оповещений Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="fc7c2-141">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="fc7c2-142">Исследование файла, связанного с оповещением Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="fc7c2-142">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="fc7c2-143">Исследование устройств в списке Устройств конечных точек Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="fc7c2-143">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="fc7c2-144">Исследование домена, связанного с оповещением Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fc7c2-144">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="fc7c2-145">Исследование учетной записи пользователя в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="fc7c2-145">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
