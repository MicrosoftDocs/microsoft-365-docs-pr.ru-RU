---
title: Создание и управление тегами устройств
description: Использование тегов устройств для групповых устройств для захвата контекста и создания динамического списка в рамках инцидента
keywords: теги, теги устройств, группы устройств, группы, исправление, уровень, правила, группа aad, роль, назначение, ранж
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
ms.openlocfilehash: ffe7d13ca0943e8927d0d9ce663527fedf880e48
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187593"
---
# <a name="create-and-manage-device-tags"></a><span data-ttu-id="bb264-104">Создание и управление тегами устройств</span><span class="sxs-lookup"><span data-stu-id="bb264-104">Create and manage device tags</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bb264-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="bb264-105">**Applies to:**</span></span>
- [<span data-ttu-id="bb264-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="bb264-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bb264-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bb264-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bb264-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="bb264-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bb264-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="bb264-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="bb264-110">Добавьте теги на устройствах, чтобы создать логическую групповую принадлежность.</span><span class="sxs-lookup"><span data-stu-id="bb264-110">Add tags on devices to create a logical group affiliation.</span></span> <span data-ttu-id="bb264-111">Теги устройств поддерживают правильное сопоставление сети, позволяя прикреплять различные теги для захвата контекста и включения динамического создания списка в рамках инцидента.</span><span class="sxs-lookup"><span data-stu-id="bb264-111">Device tags support proper mapping of the network, enabling you to attach different tags to capture context and to enable dynamic list creation as part of an incident.</span></span> <span data-ttu-id="bb264-112">Теги можно использовать в качестве фильтра в представлении списка **Устройств** или для групповых устройств.</span><span class="sxs-lookup"><span data-stu-id="bb264-112">Tags can be used as a filter in **Devices list** view, or to group devices.</span></span> <span data-ttu-id="bb264-113">Дополнительные сведения о группировке устройств см. в дополнительных сведениях [о создании и управлении группами устройств.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="bb264-113">For more information on device grouping, see [Create and manage device groups](machine-groups.md).</span></span>

<span data-ttu-id="bb264-114">Теги на устройствах можно добавлять следующими способами:</span><span class="sxs-lookup"><span data-stu-id="bb264-114">You can add tags on devices using the following ways:</span></span>

- <span data-ttu-id="bb264-115">Использование портала</span><span class="sxs-lookup"><span data-stu-id="bb264-115">Using the portal</span></span>
- <span data-ttu-id="bb264-116">Настройка ключевого значения реестра</span><span class="sxs-lookup"><span data-stu-id="bb264-116">Setting a registry key value</span></span>

> [!NOTE]
> <span data-ttu-id="bb264-117">Может возникнуть задержка между временем, когда тег добавляется на устройство, и его доступностью в списке устройств и на странице устройства.</span><span class="sxs-lookup"><span data-stu-id="bb264-117">There may be some latency between the time a tag is added to a device and its availability in the devices list and device page.</span></span>  

<span data-ttu-id="bb264-118">Чтобы добавить теги устройств с помощью API, см. [aPI add or remove device tags.](add-or-remove-machine-tags.md)</span><span class="sxs-lookup"><span data-stu-id="bb264-118">To add device tags using API, see [Add or remove device tags API](add-or-remove-machine-tags.md).</span></span>

## <a name="add-and-manage-device-tags-using-the-portal"></a><span data-ttu-id="bb264-119">Добавление тегов устройств и управление ими с помощью портала</span><span class="sxs-lookup"><span data-stu-id="bb264-119">Add and manage device tags using the portal</span></span>

1. <span data-ttu-id="bb264-120">Выберите устройство, на которое нужно управлять тегами.</span><span class="sxs-lookup"><span data-stu-id="bb264-120">Select the device that you want to manage tags on.</span></span> <span data-ttu-id="bb264-121">Вы можете выбрать или найти устройство из любого из следующих представлений:</span><span class="sxs-lookup"><span data-stu-id="bb264-121">You can select or search for a device from any of the following views:</span></span>

   - <span data-ttu-id="bb264-122">**Панель мониторинга операций безопасности** — выберите имя устройства из верхнего устройства с разделом активных оповещений.</span><span class="sxs-lookup"><span data-stu-id="bb264-122">**Security operations dashboard** - Select the device name from the Top devices with active alerts section.</span></span>
   - <span data-ttu-id="bb264-123">**Очередь оповещений** . Выберите имя устройства рядом с значком устройства из очереди оповещений.</span><span class="sxs-lookup"><span data-stu-id="bb264-123">**Alerts queue** - Select the device name beside the device icon from the alerts queue.</span></span>
   - <span data-ttu-id="bb264-124">**Список устройств** . Выберите имя устройства из списка устройств.</span><span class="sxs-lookup"><span data-stu-id="bb264-124">**Devices list** - Select the device name from the list of devices.</span></span>
   - <span data-ttu-id="bb264-125">**Поле поиска** — выберите устройство из выпадающее меню и введите имя устройства.</span><span class="sxs-lookup"><span data-stu-id="bb264-125">**Search box** - Select Device from the drop-down menu and enter the device name.</span></span>

     <span data-ttu-id="bb264-126">Вы также можете получить на страницу оповещения через файл и IP-представления.</span><span class="sxs-lookup"><span data-stu-id="bb264-126">You can also get to the alert page through the file and IP views.</span></span>

2. <span data-ttu-id="bb264-127">Выберите **Управление тегами** из ряда действий ответа.</span><span class="sxs-lookup"><span data-stu-id="bb264-127">Select **Manage Tags** from the row of Response actions.</span></span>

    ![Изображение кнопки управления тегами](images/manage-tags.png)

3. <span data-ttu-id="bb264-129">Введите, чтобы найти или создать теги</span><span class="sxs-lookup"><span data-stu-id="bb264-129">Type to find or create tags</span></span>

    ![Изображение добавления тегов на устройстве1](images/new-tags.png)

<span data-ttu-id="bb264-131">Теги добавляются в представление устройства и будут также отражены в представлении **списка Устройств.**</span><span class="sxs-lookup"><span data-stu-id="bb264-131">Tags are added to the device view and will also be reflected on the **Devices list** view.</span></span> <span data-ttu-id="bb264-132">Затем можно использовать фильтр **Теги,** чтобы увидеть соответствующий список устройств.</span><span class="sxs-lookup"><span data-stu-id="bb264-132">You can then use the **Tags** filter to see the relevant list of devices.</span></span>

>[!NOTE]
> <span data-ttu-id="bb264-133">Фильтрация может не работать с именами тегов, которые содержат скобки.</span><span class="sxs-lookup"><span data-stu-id="bb264-133">Filtering might not work on tag names that contain parenthesis.</span></span><br>
> <span data-ttu-id="bb264-134">При создании нового тега отображается список существующих тегов.</span><span class="sxs-lookup"><span data-stu-id="bb264-134">When you create a new tag, a list of existing tags are displayed.</span></span> <span data-ttu-id="bb264-135">В списке показаны только теги, созданные через портал.</span><span class="sxs-lookup"><span data-stu-id="bb264-135">The list only shows tags created through the portal.</span></span> <span data-ttu-id="bb264-136">Существующие теги, созданные с клиентских устройств, не будут отображаться.</span><span class="sxs-lookup"><span data-stu-id="bb264-136">Existing tags created from client devices will not be displayed.</span></span>

<span data-ttu-id="bb264-137">Вы также можете удалить теги из этого представления.</span><span class="sxs-lookup"><span data-stu-id="bb264-137">You can also delete tags from this view.</span></span>

![Изображение добавления тегов на устройстве2](images/more-manage-tags.png)

## <a name="add-device-tags-by-setting-a-registry-key-value"></a><span data-ttu-id="bb264-139">Добавление тегов устройств, установив ключевое значение реестра</span><span class="sxs-lookup"><span data-stu-id="bb264-139">Add device tags by setting a registry key value</span></span>

>[!NOTE]
> <span data-ttu-id="bb264-140">Применимо только на следующих устройствах:</span><span class="sxs-lookup"><span data-stu-id="bb264-140">Applicable only on the following devices:</span></span>
>- <span data-ttu-id="bb264-141">Windows 10, версия 1709 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="bb264-141">Windows 10, version 1709 or later</span></span>
>- <span data-ttu-id="bb264-142">Windows Server, версия 1803 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="bb264-142">Windows Server, version 1803 or later</span></span>
>- <span data-ttu-id="bb264-143">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="bb264-143">Windows Server 2016</span></span>
>- <span data-ttu-id="bb264-144">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="bb264-144">Windows Server 2012 R2</span></span>
>- <span data-ttu-id="bb264-145">Windows Server 2008 R2 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="bb264-145">Windows Server 2008 R2 SP1</span></span>
>- <span data-ttu-id="bb264-146">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="bb264-146">Windows 8.1</span></span>
>- <span data-ttu-id="bb264-147">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="bb264-147">Windows 7 SP1</span></span>

> [!NOTE] 
> <span data-ttu-id="bb264-148">Максимальное количество символов, которые можно установить в теге, — 200.</span><span class="sxs-lookup"><span data-stu-id="bb264-148">The maximum number of characters that can be set in a tag is 200.</span></span>

<span data-ttu-id="bb264-149">Устройства с похожими тегами могут быть удобными, если необходимо применить контекстное действие к определенному списку устройств.</span><span class="sxs-lookup"><span data-stu-id="bb264-149">Devices with similar tags can be handy when you need to apply contextual action on a specific list of devices.</span></span>

<span data-ttu-id="bb264-150">Используйте следующую запись ключа реестра, чтобы добавить тег на устройстве:</span><span class="sxs-lookup"><span data-stu-id="bb264-150">Use the following registry key entry to add a tag on a device:</span></span>

- <span data-ttu-id="bb264-151">Ключ реестра: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span><span class="sxs-lookup"><span data-stu-id="bb264-151">Registry key: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span></span>
- <span data-ttu-id="bb264-152">Ключевое значение реестра (REG_SZ): `Group`</span><span class="sxs-lookup"><span data-stu-id="bb264-152">Registry key value (REG_SZ): `Group`</span></span>
- <span data-ttu-id="bb264-153">Данные ключей реестра: `Name of the tag you want to set`</span><span class="sxs-lookup"><span data-stu-id="bb264-153">Registry key data: `Name of the tag you want to set`</span></span>

>[!NOTE]
><span data-ttu-id="bb264-154">Тег устройства является частью отчета об информации об устройстве, который создается один раз в день.</span><span class="sxs-lookup"><span data-stu-id="bb264-154">The device tag is part of the device information report that's generated once a day.</span></span> <span data-ttu-id="bb264-155">В качестве альтернативы можно перезапустить конечную точку, которая будет передавать новый отчет о устройстве.</span><span class="sxs-lookup"><span data-stu-id="bb264-155">As an alternative, you may choose to restart the endpoint that would transfer a new device information report.</span></span>
> 
> <span data-ttu-id="bb264-156">Если необходимо удалить тег, который был добавлен с помощью вышеуказанного ключа Реестра, удалите содержимое данных ключа реестра вместо удаления ключа "Group".</span><span class="sxs-lookup"><span data-stu-id="bb264-156">If you need to remove a tag that was added using the above Registry key, clear the contents of the Registry key data instead of removing the 'Group' key.</span></span>
