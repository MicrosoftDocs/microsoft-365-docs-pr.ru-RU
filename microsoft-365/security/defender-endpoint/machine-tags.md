---
title: Создание тегов устройств и управление ими
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
ms.openlocfilehash: 83dd2483b93b2f4fe520973ce05346f59baf2f28
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453581"
---
# <a name="create-and-manage-device-tags"></a><span data-ttu-id="4143d-104">Создание тегов устройств и управление ими</span><span class="sxs-lookup"><span data-stu-id="4143d-104">Create and manage device tags</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4143d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="4143d-105">**Applies to:**</span></span>
- [<span data-ttu-id="4143d-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="4143d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4143d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4143d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4143d-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="4143d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4143d-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="4143d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="4143d-110">Добавьте теги на устройства, чтобы создать логическую группу.</span><span class="sxs-lookup"><span data-stu-id="4143d-110">Add tags on devices to create a logical group affiliation.</span></span> <span data-ttu-id="4143d-111">Теги устройств поддерживают правильное сопоставление сети, позволяя вам присоединять различные теги для захвата контекста и включения динамического создания списков в рамках инцидента.</span><span class="sxs-lookup"><span data-stu-id="4143d-111">Device tags support proper mapping of the network, enabling you to attach different tags to capture context and to enable dynamic list creation as part of an incident.</span></span> <span data-ttu-id="4143d-112">Теги можно использовать в качестве фильтра в представлении списка **Устройств** или для групповых устройств.</span><span class="sxs-lookup"><span data-stu-id="4143d-112">Tags can be used as a filter in **Devices list** view, or to group devices.</span></span> <span data-ttu-id="4143d-113">Дополнительные сведения о группировке устройств см. в дополнительных сведениях [о создании и управлении группами устройств.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="4143d-113">For more information on device grouping, see [Create and manage device groups](machine-groups.md).</span></span>

<span data-ttu-id="4143d-114">Теги на устройствах можно добавлять следующими способами:</span><span class="sxs-lookup"><span data-stu-id="4143d-114">You can add tags on devices using the following ways:</span></span>

- <span data-ttu-id="4143d-115">Использование портала</span><span class="sxs-lookup"><span data-stu-id="4143d-115">Using the portal</span></span>
- <span data-ttu-id="4143d-116">Настройка значения раздела реестра</span><span class="sxs-lookup"><span data-stu-id="4143d-116">Setting a registry key value</span></span>

> [!NOTE]
> <span data-ttu-id="4143d-117">Может возникнуть задержка между временем, когда тег добавляется на устройство, и его доступностью в списке устройств и на странице устройства.</span><span class="sxs-lookup"><span data-stu-id="4143d-117">There may be some latency between the time a tag is added to a device and its availability in the devices list and device page.</span></span>  

<span data-ttu-id="4143d-118">Чтобы добавить теги устройств с помощью API, см. [API добавления и удаления тегов устройств](add-or-remove-machine-tags.md).</span><span class="sxs-lookup"><span data-stu-id="4143d-118">To add device tags using API, see [Add or remove device tags API](add-or-remove-machine-tags.md).</span></span>

## <a name="add-and-manage-device-tags-using-the-portal"></a><span data-ttu-id="4143d-119">Добавление тегов устройств и управление ими с помощью портала</span><span class="sxs-lookup"><span data-stu-id="4143d-119">Add and manage device tags using the portal</span></span>

1. <span data-ttu-id="4143d-120">Выберите устройство, для которого вы хотите настроить теги.</span><span class="sxs-lookup"><span data-stu-id="4143d-120">Select the device that you want to manage tags on.</span></span> <span data-ttu-id="4143d-121">Можно выбрать устройство или найти его в любом из следующих представлений:</span><span class="sxs-lookup"><span data-stu-id="4143d-121">You can select or search for a device from any of the following views:</span></span>

   - <span data-ttu-id="4143d-122">**Панель мониторинга операций безопасности** — выберите имя устройства из верхнего устройства с разделом активных оповещений.</span><span class="sxs-lookup"><span data-stu-id="4143d-122">**Security operations dashboard** - Select the device name from the Top devices with active alerts section.</span></span>
   - <span data-ttu-id="4143d-123">**Очередь оповещений** – Выберите имя устройства рядом со значком устройства из очереди оповещений.</span><span class="sxs-lookup"><span data-stu-id="4143d-123">**Alerts queue** - Select the device name beside the device icon from the alerts queue.</span></span>
   - <span data-ttu-id="4143d-124">**Список устройств** – Выберите имя устройства из списка устройств.</span><span class="sxs-lookup"><span data-stu-id="4143d-124">**Devices list** - Select the device name from the list of devices.</span></span>
   - <span data-ttu-id="4143d-125">**Поле поиска** – Выберите устройство из раскрывающегося меню и введите имя устройства.</span><span class="sxs-lookup"><span data-stu-id="4143d-125">**Search box** - Select Device from the drop-down menu and enter the device name.</span></span>

     <span data-ttu-id="4143d-126">Вы также можете попасть на страницу оповещений с помощью представления файлов и IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="4143d-126">You can also get to the alert page through the file and IP views.</span></span>

2. <span data-ttu-id="4143d-127">Выберите **Управление тегами** в строке действий ответа.</span><span class="sxs-lookup"><span data-stu-id="4143d-127">Select **Manage Tags** from the row of Response actions.</span></span>

    :::image type="content" alt-text="Изображение кнопки управления тегами." source="images/manage-tags-option.png":::

3. <span data-ttu-id="4143d-129">Введите, чтобы найти или создать теги</span><span class="sxs-lookup"><span data-stu-id="4143d-129">Type to find or create tags</span></span>

    :::image type="content" alt-text="Изображение добавления тегов на устройстве1." source="images/create-new-tag.png":::

<span data-ttu-id="4143d-131">Теги добавляются в представление устройства и будут также отражены в представлении **списка Устройств.**</span><span class="sxs-lookup"><span data-stu-id="4143d-131">Tags are added to the device view and will also be reflected on the **Devices list** view.</span></span> <span data-ttu-id="4143d-132">Затем можно использовать фильтр **Теги,** чтобы увидеть соответствующий список устройств.</span><span class="sxs-lookup"><span data-stu-id="4143d-132">You can then use the **Tags** filter to see the relevant list of devices.</span></span>

>[!NOTE]
> <span data-ttu-id="4143d-133">Фильтрация может не работать с именами тегов, которые содержат скобки.</span><span class="sxs-lookup"><span data-stu-id="4143d-133">Filtering might not work on tag names that contain parenthesis.</span></span><br>
> <span data-ttu-id="4143d-134">При создании нового тега отображается список существующих тегов.</span><span class="sxs-lookup"><span data-stu-id="4143d-134">When you create a new tag, a list of existing tags are displayed.</span></span> <span data-ttu-id="4143d-135">В списке показаны только теги, созданные через портал.</span><span class="sxs-lookup"><span data-stu-id="4143d-135">The list only shows tags created through the portal.</span></span> <span data-ttu-id="4143d-136">Существующие теги, созданные с клиентских устройств, не будут отображаться.</span><span class="sxs-lookup"><span data-stu-id="4143d-136">Existing tags created from client devices will not be displayed.</span></span>

<span data-ttu-id="4143d-137">Вы также можете удалить теги из этого представления.</span><span class="sxs-lookup"><span data-stu-id="4143d-137">You can also delete tags from this view.</span></span>

:::image type="content" alt-text="Изображение добавления тегов на устройстве2." source="images/new-tag-label-display.png":::

## <a name="add-device-tags-by-setting-a-registry-key-value"></a><span data-ttu-id="4143d-139">Добавление тегов устройств, установив ключевое значение реестра</span><span class="sxs-lookup"><span data-stu-id="4143d-139">Add device tags by setting a registry key value</span></span>

>[!NOTE]
> <span data-ttu-id="4143d-140">Применимо только на следующих устройствах:</span><span class="sxs-lookup"><span data-stu-id="4143d-140">Applicable only on the following devices:</span></span>
>- <span data-ttu-id="4143d-141">Windows 10 версии 1709 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="4143d-141">Windows 10, version 1709 or later</span></span>
>- <span data-ttu-id="4143d-142">Windows Сервер, версия 1803 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="4143d-142">Windows Server, version 1803 or later</span></span>
>- <span data-ttu-id="4143d-143">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="4143d-143">Windows Server 2016</span></span>
>- <span data-ttu-id="4143d-144">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="4143d-144">Windows Server 2012 R2</span></span>
>- <span data-ttu-id="4143d-145">Windows Server 2008 R2 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="4143d-145">Windows Server 2008 R2 SP1</span></span>
>- <span data-ttu-id="4143d-146">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="4143d-146">Windows 8.1</span></span>
>- <span data-ttu-id="4143d-147">Windows 7 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="4143d-147">Windows 7 SP1</span></span>

> [!NOTE] 
> <span data-ttu-id="4143d-148">Максимальное количество символов, которые можно установить в теге, — 200.</span><span class="sxs-lookup"><span data-stu-id="4143d-148">The maximum number of characters that can be set in a tag is 200.</span></span>

<span data-ttu-id="4143d-149">Устройства с похожими тегами могут быть удобными, если необходимо применить контекстное действие к определенному списку устройств.</span><span class="sxs-lookup"><span data-stu-id="4143d-149">Devices with similar tags can be handy when you need to apply contextual action on a specific list of devices.</span></span>

<span data-ttu-id="4143d-150">Используйте следующую запись ключа реестра, чтобы добавить тег на устройстве:</span><span class="sxs-lookup"><span data-stu-id="4143d-150">Use the following registry key entry to add a tag on a device:</span></span>

- <span data-ttu-id="4143d-151">Ключ реестра: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span><span class="sxs-lookup"><span data-stu-id="4143d-151">Registry key: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span></span>
- <span data-ttu-id="4143d-152">Ключевое значение реестра (REG_SZ): `Group`</span><span class="sxs-lookup"><span data-stu-id="4143d-152">Registry key value (REG_SZ): `Group`</span></span>
- <span data-ttu-id="4143d-153">Данные ключей реестра: `Name of the tag you want to set`</span><span class="sxs-lookup"><span data-stu-id="4143d-153">Registry key data: `Name of the tag you want to set`</span></span>

>[!NOTE]
><span data-ttu-id="4143d-154">Тег устройства является частью отчета об информации об устройстве, который создается один раз в день.</span><span class="sxs-lookup"><span data-stu-id="4143d-154">The device tag is part of the device information report that's generated once a day.</span></span> <span data-ttu-id="4143d-155">В качестве альтернативы можно перезапустить конечную точку, которая будет передавать новый отчет о устройстве.</span><span class="sxs-lookup"><span data-stu-id="4143d-155">As an alternative, you may choose to restart the endpoint that would transfer a new device information report.</span></span>
> 
> <span data-ttu-id="4143d-156">Если необходимо удалить тег, который был добавлен с помощью вышеуказанного ключа Реестра, удалите содержимое данных ключа реестра вместо удаления ключа "Group".</span><span class="sxs-lookup"><span data-stu-id="4143d-156">If you need to remove a tag that was added using the above Registry key, clear the contents of the Registry key data instead of removing the 'Group' key.</span></span>
