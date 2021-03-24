---
title: Методы в временной шкале устройства
description: Понимание временной шкалы устройства в Microsoft Defender для конечной точки
keywords: Хронология устройства, конечная точка, MITRE, MITRE ATT&CK, методы, тактика
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d6e2c18bd3710e659b5f9887844bc92528da4607
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070141"
---
# <a name="techniques-in-the-device-timeline"></a><span data-ttu-id="99bed-104">Методы в временной шкале устройства</span><span class="sxs-lookup"><span data-stu-id="99bed-104">Techniques in the device timeline</span></span>


<span data-ttu-id="99bed-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="99bed-105">**Applies to:**</span></span>
- [<span data-ttu-id="99bed-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="99bed-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)


<span data-ttu-id="99bed-107">Вы можете получить больше информации в ходе расследования, проанализировав события, которые произошли на определенном устройстве.</span><span class="sxs-lookup"><span data-stu-id="99bed-107">You can gain more insight in an investigation by analyzing the events that happened on a specific device.</span></span> <span data-ttu-id="99bed-108">Сначала выберите интересующее устройство из списка [Устройств.](machines-view-overview.md)</span><span class="sxs-lookup"><span data-stu-id="99bed-108">First, select the device of interest from the [Devices list](machines-view-overview.md).</span></span> <span data-ttu-id="99bed-109">На странице устройства можно выбрать вкладку **Timeline** для просмотра всех событий, произошедших на устройстве.</span><span class="sxs-lookup"><span data-stu-id="99bed-109">On the device page, you can select the **Timeline** tab to view all the events that occurred on the device.</span></span>

## <a name="understand-techniques-in-the-timeline"></a><span data-ttu-id="99bed-110">Понимание методов в временной шкале</span><span class="sxs-lookup"><span data-stu-id="99bed-110">Understand techniques in the timeline</span></span>

>[!IMPORTANT]
><span data-ttu-id="99bed-111">Некоторые сведения относятся к предварительной версии продукта в общедоступных предварительных версиях, которые могут быть существенно изменены до его коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="99bed-111">Some information relates to a prereleased product feature in public preview which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="99bed-112">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="99bed-112">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="99bed-113">В Microsoft Defender для конечной точки **методы** являются дополнительным типом данных в временной шкале событий.</span><span class="sxs-lookup"><span data-stu-id="99bed-113">In Microsoft Defender for Endpoint, **Techniques** are an additional data type in the event timeline.</span></span> <span data-ttu-id="99bed-114">Методы предоставляют дополнительные сведения о действиях, связанных&[CK](https://attack.mitre.org/)&или под-методов.</span><span class="sxs-lookup"><span data-stu-id="99bed-114">Techniques provide more insight on activities associated with [MITRE ATT&CK](https://attack.mitre.org/) techniques or sub-techniques.</span></span> 

<span data-ttu-id="99bed-115">Эта функция упрощает опыт исследования, помогая аналитикам понять действия, наблюдаемые на устройстве.</span><span class="sxs-lookup"><span data-stu-id="99bed-115">This feature simplifies the investigation experience by helping analysts understand the activities that were observed on a device.</span></span> <span data-ttu-id="99bed-116">Затем аналитики могут принять решение о дальнейшем расследовании.</span><span class="sxs-lookup"><span data-stu-id="99bed-116">Analysts can then decide to investigate further.</span></span>

<span data-ttu-id="99bed-117">Для общего предварительного просмотра методы доступны по умолчанию и показаны вместе с событиями при просмотре временной шкалы устройства.</span><span class="sxs-lookup"><span data-stu-id="99bed-117">For public preview, Techniques are available by default and shown together with events when a device's timeline is viewed.</span></span> 

![Методы в скриншоте временной шкалы устройств](images/device-timeline-2.png)

<span data-ttu-id="99bed-119">Методы выделены жирным текстом и отображаются с синим значком слева.</span><span class="sxs-lookup"><span data-stu-id="99bed-119">Techniques are highlighted in bold text and appear with a blue icon on the left.</span></span> <span data-ttu-id="99bed-120">Соответствующее имя и имя&CK ATT также отображаются в качестве тегов в статье Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="99bed-120">The corresponding MITRE ATT&CK ID and technique name also appear as tags under Additional information.</span></span> 

<span data-ttu-id="99bed-121">Параметры поиска и экспорта также доступны для методов.</span><span class="sxs-lookup"><span data-stu-id="99bed-121">Search and Export options are also available for Techniques.</span></span>

## <a name="investigate-using-the-side-pane"></a><span data-ttu-id="99bed-122">Исследование с помощью боковой области</span><span class="sxs-lookup"><span data-stu-id="99bed-122">Investigate using the side pane</span></span>

<span data-ttu-id="99bed-123">Выберите метод для открытия соответствующей боковой области.</span><span class="sxs-lookup"><span data-stu-id="99bed-123">Select a Technique to open its corresponding side pane.</span></span> <span data-ttu-id="99bed-124">Здесь вы можете увидеть дополнительные сведения и сведения, такие как связанные методы&CK, тактика и описания.</span><span class="sxs-lookup"><span data-stu-id="99bed-124">Here you can see additional information and insights like related ATT&CK techniques, tactics, and descriptions.</span></span> 

<span data-ttu-id="99bed-125">Выберите определенную *методику атаки,* чтобы открыть связанную страницу&CK, на которой можно найти дополнительные сведения об этом.</span><span class="sxs-lookup"><span data-stu-id="99bed-125">Select the specific *Attack technique* to open the related ATT&CK technique page where you can find more information about it.</span></span>

<span data-ttu-id="99bed-126">Вы можете скопировать сведения об объекте при виде синего значка справа.</span><span class="sxs-lookup"><span data-stu-id="99bed-126">You can copy an entity's details when you see a blue icon on the right.</span></span> <span data-ttu-id="99bed-127">Например, чтобы скопировать sha1 связанного файла, выберите значок синей страницы.</span><span class="sxs-lookup"><span data-stu-id="99bed-127">For instance, to copy a related file's SHA1, select the blue page icon.</span></span>

![Копирование сведений об объекте](images/techniques-side-pane-clickable.png)

<span data-ttu-id="99bed-129">Вы можете сделать то же самое для командных строк.</span><span class="sxs-lookup"><span data-stu-id="99bed-129">You can do the same for command lines.</span></span>

![Копирование командной строки](images/techniques-side-pane-command.png)


## <a name="investigate-related-events"></a><span data-ttu-id="99bed-131">Исследование связанных событий</span><span class="sxs-lookup"><span data-stu-id="99bed-131">Investigate related events</span></span>

<span data-ttu-id="99bed-132">Чтобы найти [события,](advanced-hunting-overview.md) связанные с выбранным методом, выберите **Hunt для связанных событий.**</span><span class="sxs-lookup"><span data-stu-id="99bed-132">To use [advanced hunting](advanced-hunting-overview.md) to find events related to the selected Technique, select **Hunt for related events**.</span></span> <span data-ttu-id="99bed-133">Это приводит к продвинутой странице охоты с запросом на поиск событий, связанных с методом.</span><span class="sxs-lookup"><span data-stu-id="99bed-133">This leads to the advanced hunting page with a query to find events related to the Technique.</span></span>

![Охота за связанными событиями](images/techniques-hunt-for-related-events.png)

>[!NOTE]
><span data-ttu-id="99bed-135">Запрос с помощью кнопки **Hunt для** связанных событий с боковой области Technique отображает все события, связанные с идентифицированной техникой, но не включает сам метод в результаты запроса.</span><span class="sxs-lookup"><span data-stu-id="99bed-135">Querying using the **Hunt for related events** button from a Technique side pane displays all the events related to the identified technique but does not include the Technique itself in the query results.</span></span>


## <a name="customize-your-device-timeline"></a><span data-ttu-id="99bed-136">Настройка временной шкалы устройства</span><span class="sxs-lookup"><span data-stu-id="99bed-136">Customize your device timeline</span></span>

<span data-ttu-id="99bed-137">В правой правой части временной шкалы устройства можно выбрать диапазон дат, чтобы ограничить количество событий и методов в временной шкале.</span><span class="sxs-lookup"><span data-stu-id="99bed-137">On the upper right-hand side of the device timeline, you can choose a date range to limit the number of events and techniques in the timeline.</span></span> 

<span data-ttu-id="99bed-138">Вы можете настроить столбцы для разоблачения.</span><span class="sxs-lookup"><span data-stu-id="99bed-138">You can customize which columns to expose.</span></span> <span data-ttu-id="99bed-139">Вы также можете фильтровать для помеченных событий по типу данных или по группе событий.</span><span class="sxs-lookup"><span data-stu-id="99bed-139">You can also filter for flagged events by data type or by event group.</span></span>

### <a name="choose-columns-to-expose"></a><span data-ttu-id="99bed-140">Выбор столбцов для разоблачения</span><span class="sxs-lookup"><span data-stu-id="99bed-140">Choose columns to expose</span></span>
<span data-ttu-id="99bed-141">Вы можете выбрать, какие столбцы выставить в временной шкале, выбрав кнопку **Выберите столбцы.**</span><span class="sxs-lookup"><span data-stu-id="99bed-141">You can choose which columns to expose in the timeline by selecting the **Choose columns** button.</span></span>

![Настройка столбцов](images/filter-customize-columns.png)

<span data-ttu-id="99bed-143">Оттуда можно выбрать, какие сведения включить.</span><span class="sxs-lookup"><span data-stu-id="99bed-143">From there you can select which information set to include.</span></span>

### <a name="filter-to-view-techniques-or-events-only"></a><span data-ttu-id="99bed-144">Фильтр для просмотра только методов или событий</span><span class="sxs-lookup"><span data-stu-id="99bed-144">Filter to view techniques or events only</span></span>

<span data-ttu-id="99bed-145">Чтобы просмотреть только события или методы, выберите **фильтры** из временной шкалы устройства и выберите предпочтительный тип данных для просмотра.</span><span class="sxs-lookup"><span data-stu-id="99bed-145">To view only either events or techniques, select **Filters** from the device timeline and choose your preferred Data type to view.</span></span>

![Снимок экрана фильтров](images/device-timeline-filters.png)



## <a name="see-also"></a><span data-ttu-id="99bed-147">См. также</span><span class="sxs-lookup"><span data-stu-id="99bed-147">See also</span></span>
- [<span data-ttu-id="99bed-148">Просмотр и организация списка Устройств</span><span class="sxs-lookup"><span data-stu-id="99bed-148">View and organize the Devices list</span></span>](machines-view-overview.md)
- [<span data-ttu-id="99bed-149">Флаги событий событий Microsoft Defender для конечных устройств</span><span class="sxs-lookup"><span data-stu-id="99bed-149">Microsoft Defender for Endpoint device timeline event flags</span></span>](device-timeline-event-flag.md) 


 
