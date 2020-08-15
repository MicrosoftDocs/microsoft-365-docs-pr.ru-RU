---
title: Узнайте о записях
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Узнайте о записях, которые помогут вам внедрить решение для управления записями в Microsoft 365.
ms.openlocfilehash: e64e91aeef307d05f23c47987a84baaf386324df
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685445"
---
# <a name="learn-about-records"></a><span data-ttu-id="5b1e6-103">Узнайте о записях</span><span class="sxs-lookup"><span data-stu-id="5b1e6-103">Learn about records</span></span>

><span data-ttu-id="5b1e6-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="5b1e6-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="5b1e6-105">Управление записями в Microsoft 365 помогает организации соблюдать корпоративные политики, правовые и нормативные положения, а также уменьшить риски и правовые последствия.</span><span class="sxs-lookup"><span data-stu-id="5b1e6-105">Managing records in Microsoft 365 helps your organization comply with corporate policies and legal or regulatory obligations, while also reducing risk and legal liability.</span></span>

<span data-ttu-id="5b1e6-106">Когда содержимое помечается как запись:</span><span class="sxs-lookup"><span data-stu-id="5b1e6-106">When content is marked as a record:</span></span>

- <span data-ttu-id="5b1e6-107">На элементы накладываются ограничения в отношении того, какие[действия разрешены или запрещены](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span><span class="sxs-lookup"><span data-stu-id="5b1e6-107">Restrictions are placed on the items in terms of what [actions are allowed or blocked](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

- <span data-ttu-id="5b1e6-108">дополнительные действия, связанные с элементом, фиксируются в журнале;</span><span class="sxs-lookup"><span data-stu-id="5b1e6-108">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="5b1e6-109">Когда элементы удаляются по истечении периода хранения, вы должны подтвердить их ликвидацию.</span><span class="sxs-lookup"><span data-stu-id="5b1e6-109">You have proof of disposition when the items are deleted at the end of their retention period.</span></span>

<span data-ttu-id="5b1e6-110">Чтобы пометить содержимое как запись, используются [метки хранения](retention.md#retention-labels).</span><span class="sxs-lookup"><span data-stu-id="5b1e6-110">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="5b1e6-111">Вы можете либо опубликовать эти метки, чтобы пользователи и администраторы могли вручную применить их к содержимому, либо автоматически применить эти метки к содержимому, которое вы хотите пометить как запись.</span><span class="sxs-lookup"><span data-stu-id="5b1e6-111">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

<span data-ttu-id="5b1e6-112">Используя метки хранения для того, чтобы помечать содержимое как записи, вы можете реализовать единую и последовательную стратегию управления записями в своей среде Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5b1e6-112">By using retention labels to mark content as records, you can implement a single and consistent strategy for managing records across your Microsoft 365 environment.</span></span>

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a><span data-ttu-id="5b1e6-113">Сравните ограничения на то, какие действия разрешены или запрещены</span><span class="sxs-lookup"><span data-stu-id="5b1e6-113">Compare restrictions for what actions are allowed or blocked</span></span>

<span data-ttu-id="5b1e6-114">Используйте приведенную ниже таблицу, чтобы определить, какие ограничения накладываются на контент в результате применения стандартной метки хранения, а также меток хранения, помечающих содержимое как запись.</span><span class="sxs-lookup"><span data-stu-id="5b1e6-114">Use the following table to identify what restrictions are placed on content as a result of applying a standard retention label, and retention labels that mark content as a record.</span></span> 

<span data-ttu-id="5b1e6-115">Конфигурация стандартной метки хранения позволяет сохранять данные, не помечая содержимое как запись.</span><span class="sxs-lookup"><span data-stu-id="5b1e6-115">A standard retention label has the configuration to retain data without marking content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="5b1e6-116">Таблица также содержит столбцы для заблокированной и разблокированной записи, которая применима к содержимому в SharePoint и OneDrive, но не в Exchange.</span><span class="sxs-lookup"><span data-stu-id="5b1e6-116">For completeness, the table includes columns for a locked and unlocked record, which is applicable to SharePoint and OneDrive, but not Exchange.</span></span> <span data-ttu-id="5b1e6-117">Для блокировки и разблокировки записи используется [Управление версиями записи](record-versioning.md), которое не поддерживается для элементов Exchange.</span><span class="sxs-lookup"><span data-stu-id="5b1e6-117">The ability to lock and unlock a record uses [record versioning](record-versioning.md) that isn't supported for Exchange items.</span></span> <span data-ttu-id="5b1e6-118">Таким образом, для всех элементов Exchange, которые помечены как записи, действие сопоставляется со столбцом **Запись заблокирована**, а столбец **Запись разблокирована** не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="5b1e6-118">So for all Exchange items that are marked as a record, the behavior maps to the **Record - locked** column, and the **Record - unlocked column** is not relevant.</span></span>


|<span data-ttu-id="5b1e6-119">Действие</span><span class="sxs-lookup"><span data-stu-id="5b1e6-119">Action</span></span>| <span data-ttu-id="5b1e6-120">Метка хранения</span><span class="sxs-lookup"><span data-stu-id="5b1e6-120">Retention label</span></span> |<span data-ttu-id="5b1e6-121">Запись заблокирована</span><span class="sxs-lookup"><span data-stu-id="5b1e6-121">Record - locked</span></span>| <span data-ttu-id="5b1e6-122">Запись разблокирована</span><span class="sxs-lookup"><span data-stu-id="5b1e6-122">Record - unlocked</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5b1e6-123">Изменение содержаний</span><span class="sxs-lookup"><span data-stu-id="5b1e6-123">Edit contents</span></span>|<span data-ttu-id="5b1e6-124">Разрешено</span><span class="sxs-lookup"><span data-stu-id="5b1e6-124">Allowed</span></span> | <span data-ttu-id="5b1e6-125">**Заблокировано**</span><span class="sxs-lookup"><span data-stu-id="5b1e6-125">**Blocked**</span></span> | <span data-ttu-id="5b1e6-126">Разрешено</span><span class="sxs-lookup"><span data-stu-id="5b1e6-126">Allowed</span></span>|
|<span data-ttu-id="5b1e6-127">Изменение свойств, включая переименование</span><span class="sxs-lookup"><span data-stu-id="5b1e6-127">Edit properties, including rename</span></span>|<span data-ttu-id="5b1e6-128">Разрешено</span><span class="sxs-lookup"><span data-stu-id="5b1e6-128">Allowed</span></span> |<span data-ttu-id="5b1e6-129">Разрешено</span><span class="sxs-lookup"><span data-stu-id="5b1e6-129">Allowed</span></span> | <span data-ttu-id="5b1e6-130">Разрешено</span><span class="sxs-lookup"><span data-stu-id="5b1e6-130">Allowed</span></span>|
|<span data-ttu-id="5b1e6-131">Удалить</span><span class="sxs-lookup"><span data-stu-id="5b1e6-131">Delete</span></span>|<span data-ttu-id="5b1e6-132">Разрешено <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5b1e6-132">Allowed <sup>1</sup></span></span> |<span data-ttu-id="5b1e6-133">**Заблокировано**</span><span class="sxs-lookup"><span data-stu-id="5b1e6-133">**Blocked**</span></span> | <span data-ttu-id="5b1e6-134">**Заблокировано**</span><span class="sxs-lookup"><span data-stu-id="5b1e6-134">**Blocked**</span></span>|
|<span data-ttu-id="5b1e6-135">Копировать</span><span class="sxs-lookup"><span data-stu-id="5b1e6-135">Copy</span></span>|<span data-ttu-id="5b1e6-136">Разрешено</span><span class="sxs-lookup"><span data-stu-id="5b1e6-136">Allowed</span></span> |<span data-ttu-id="5b1e6-137">Разрешено</span><span class="sxs-lookup"><span data-stu-id="5b1e6-137">Allowed</span></span> | <span data-ttu-id="5b1e6-138">Разрешено</span><span class="sxs-lookup"><span data-stu-id="5b1e6-138">Allowed</span></span>|
|<span data-ttu-id="5b1e6-139">Перемещение в контейнере <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="5b1e6-139">Move within container <sup>2</sup></span></span>|<span data-ttu-id="5b1e6-140">Разрешено</span><span class="sxs-lookup"><span data-stu-id="5b1e6-140">Allowed</span></span> |<span data-ttu-id="5b1e6-141">Разрешено</span><span class="sxs-lookup"><span data-stu-id="5b1e6-141">Allowed</span></span> | <span data-ttu-id="5b1e6-142">Разрешено</span><span class="sxs-lookup"><span data-stu-id="5b1e6-142">Allowed</span></span>|
|<span data-ttu-id="5b1e6-143">Перемещение между контейнерами <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="5b1e6-143">Move across containers <sup>2</sup></span></span>|<span data-ttu-id="5b1e6-144">Разрешено</span><span class="sxs-lookup"><span data-stu-id="5b1e6-144">Allowed</span></span> |<span data-ttu-id="5b1e6-145">Разрешено, если никогда не будет разблокировано</span><span class="sxs-lookup"><span data-stu-id="5b1e6-145">Allowed if never unlocked</span></span> | <span data-ttu-id="5b1e6-146">Разрешено</span><span class="sxs-lookup"><span data-stu-id="5b1e6-146">Allowed</span></span>|
|<span data-ttu-id="5b1e6-147">Открыть/читать</span><span class="sxs-lookup"><span data-stu-id="5b1e6-147">Open/Read</span></span>|<span data-ttu-id="5b1e6-148">Разрешено</span><span class="sxs-lookup"><span data-stu-id="5b1e6-148">Allowed</span></span> |<span data-ttu-id="5b1e6-149">Разрешено</span><span class="sxs-lookup"><span data-stu-id="5b1e6-149">Allowed</span></span> | <span data-ttu-id="5b1e6-150">Разрешено</span><span class="sxs-lookup"><span data-stu-id="5b1e6-150">Allowed</span></span>|
|<span data-ttu-id="5b1e6-151">Изменить метку</span><span class="sxs-lookup"><span data-stu-id="5b1e6-151">Change label</span></span>|<span data-ttu-id="5b1e6-152">Разрешено</span><span class="sxs-lookup"><span data-stu-id="5b1e6-152">Allowed</span></span> |<span data-ttu-id="5b1e6-153">Разрешено только для администраторов контейнера</span><span class="sxs-lookup"><span data-stu-id="5b1e6-153">Allowed - container admin only</span></span> | <span data-ttu-id="5b1e6-154">Разрешено только для администраторов контейнера</span><span class="sxs-lookup"><span data-stu-id="5b1e6-154">Allowed - container admin only</span></span>|
|<span data-ttu-id="5b1e6-155">Удалить метку</span><span class="sxs-lookup"><span data-stu-id="5b1e6-155">Remove label</span></span>|<span data-ttu-id="5b1e6-156">Разрешено</span><span class="sxs-lookup"><span data-stu-id="5b1e6-156">Allowed</span></span> |<span data-ttu-id="5b1e6-157">Разрешено только для администраторов контейнера</span><span class="sxs-lookup"><span data-stu-id="5b1e6-157">Allowed - container admin only</span></span> | <span data-ttu-id="5b1e6-158">Разрешено только для администраторов контейнера</span><span class="sxs-lookup"><span data-stu-id="5b1e6-158">Allowed - container admin only</span></span>|

<span data-ttu-id="5b1e6-159">Сноски:</span><span class="sxs-lookup"><span data-stu-id="5b1e6-159">Footnotes:</span></span>

<span data-ttu-id="5b1e6-160"><sup>1</sup> Поддерживается OneDrive и Exchange путем сохранения копии в защищенном месте, но заблокировано в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5b1e6-160"><sup>1</sup> Supported by OneDrive and Exchange by retaining a copy in a secured location, but blocked by SharePoint.</span></span>

<span data-ttu-id="5b1e6-161">Сообщение, которое видит пользователь, когда пытается удалить помеченный документ в SharePoint:</span><span class="sxs-lookup"><span data-stu-id="5b1e6-161">Message a user sees if they try to delete a labeled document in SharePoint:</span></span>

![Сообщение о том, что элемент не был удален из SharePoint](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<span data-ttu-id="5b1e6-163"><sup>2</sup> Контейнеры включают библиотеки документов SharePoint и почтовые ящики Exhange.</span><span class="sxs-lookup"><span data-stu-id="5b1e6-163"><sup>2</sup> Containers include SharePoint document libraries and Exchange mailboxes.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5b1e6-164">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="5b1e6-164">Next steps</span></span>

<span data-ttu-id="5b1e6-165">Если у вас еще нет меток хранения для управления записями, см. статью [Начало работы с политиками хранения и метками хранения](get-started-with-retention.md).</span><span class="sxs-lookup"><span data-stu-id="5b1e6-165">If you don't yet have retention labels to use for records management, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="5b1e6-166">Чтобы пометить содержимое как запись, см. статью [Объявление записей с помощью меток хранения](declare-records.md).</span><span class="sxs-lookup"><span data-stu-id="5b1e6-166">To mark content as a record, see [Declare records by using retention labels](declare-records.md).</span></span>
