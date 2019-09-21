---
title: Заметки о выпуске Microsoft соответствие требованиям
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Диспетчер соответствия требованиям Майкрософт — бесплатное средство оценки рисков на основе рабочих процессов на портале доверия службы Майкрософт. Диспетчер соответствия требованиям позволяет отслеживать, назначать и проверять нормативные действия, связанные с облачными службами Майкрософт.
ms.openlocfilehash: 815862616e1bdbf4b3be1d77de2a541ad703149f
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37089829"
---
# <a name="release-notes-for-compliance-manager-preview"></a><span data-ttu-id="5ad86-104">Заметки о выпуске для диспетчера соответствия требованиям (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="5ad86-104">Release Notes for Compliance Manager (Preview)</span></span>

<span data-ttu-id="5ad86-105">Общедоступная Предварительная версия диспетчера соответствия требованиям обеспечивает ранний доступ к предстоящим функциям и обновлениям.</span><span class="sxs-lookup"><span data-stu-id="5ad86-105">The public preview of Compliance Manager provides you with early access to upcoming functionality and updates.</span></span>

<span data-ttu-id="5ad86-106">С помощью обновленного средства " [Диспетчер соответствия требованиям](https://servicetrust.microsoft.com/ComplianceManager) " на [портале доверия службы](https://servicetrust.microsoft.com) можно отслеживать, назначать и проверять нормативные действия, связанные с облачными службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5ad86-106">You can use the updated [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) tool on the [Service Trust Portal](https://servicetrust.microsoft.com) to track, assign, and verify regulatory compliance activities related to Microsoft cloud services.</span></span>

## <a name="whats-new-in-compliance-manager-preview"></a><span data-ttu-id="5ad86-107">Новые возможности в диспетчере соответствия требованиям (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="5ad86-107">What’s new in Compliance Manager (Preview)</span></span>

- <span data-ttu-id="5ad86-108">**Интеграция с показателем безопасности Майкрософт:** Диспетчер соответствия требованиям поддерживает интеграцию с [рейтингом безопасности Майкрософт](../security/mtp/microsoft-secure-score.md) путем сопоставления действий, управляемых клиентами, с более чем 50 действиями по безопасному рейтингу.</span><span class="sxs-lookup"><span data-stu-id="5ad86-108">**Integration with Microsoft Secure Score:** Compliance Manager supports integration with [Microsoft Secure Score](../security/mtp/microsoft-secure-score.md) by mapping customer-managed Actions to more than 50 Secure Score actions.</span></span> <span data-ttu-id="5ad86-109">После выполнения сопоставленного действия в показателе безопасности соответствующее действие диспетчера соответствия автоматически обновляется.</span><span class="sxs-lookup"><span data-stu-id="5ad86-109">When you complete a mapped action in Secure Score, the corresponding Compliance Manager Action automatically updates.</span></span>

- <span data-ttu-id="5ad86-110">**Импорт настраиваемых оценок:** Помимо встроенных оценок, диспетчер соответствия требованиям теперь поддерживает импорт пользовательских шаблонов.</span><span class="sxs-lookup"><span data-stu-id="5ad86-110">**Import custom Assessments:** In addition to built-in Assessments, Compliance Manager now supports importing custom Templates.</span></span> <span data-ttu-id="5ad86-111">Вы можете создавать собственные оценки для любого продукта или службы, а также любых стандартных или регулируемых.</span><span class="sxs-lookup"><span data-stu-id="5ad86-111">You can create custom Assessments for any product or service and any standard or regulation.</span></span>

- <span data-ttu-id="5ad86-112">**Элементы действий:** Элементы Action теперь являются отдельными элементами, и многие из них включают коллекцию телеметрии из API графа Microsoft Secure scores.</span><span class="sxs-lookup"><span data-stu-id="5ad86-112">**Actions Items:** Action Items are now individual items and many include telemetry collection from the Microsoft Secure Score Graph API.</span></span> <span data-ttu-id="5ad86-113">Там, где это возможно, в технических рекомендациях теперь есть ссылки на страницу "соответствующая конфигурация" в службе Office 365.</span><span class="sxs-lookup"><span data-stu-id="5ad86-113">Where possible, technical action recommendations now have links to the applicable configuration page in the Office 365 service.</span></span>

- <span data-ttu-id="5ad86-114">**Управление клиентами:** Новый интерфейс для управления новыми элементами данных в диспетчере соответствия требованиям (Предварительная версия):</span><span class="sxs-lookup"><span data-stu-id="5ad86-114">**Tenant Management:** New interface for managing new data elements in Compliance Manager (Preview):</span></span>
    - <span data-ttu-id="5ad86-115">**Измерения:** Просматривать, добавлять и настраивать метаданные для шаблонов, оценок и действий, которые позволяют создавать настраиваемые сводные элементы для фильтров.</span><span class="sxs-lookup"><span data-stu-id="5ad86-115">**Dimensions:** View, add and customize metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
    - <span data-ttu-id="5ad86-116">**Владельцы:** Укажите владельца для каждого элемента Action.</span><span class="sxs-lookup"><span data-stu-id="5ad86-116">**Owners:** Specify an owner for each Action Item.</span></span>
    - <span data-ttu-id="5ad86-117">**Действия клиента:** Управление полным списком элементов действий, включенных в Диспетчер соответствия требованиям (Предварительная версия), а также включение и отключение мониторинга безопасного индекса для действий, интегрированных с рейтингом безопасности.</span><span class="sxs-lookup"><span data-stu-id="5ad86-117">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Action Items integrated with Secure Score.</span></span>

- <span data-ttu-id="5ad86-118">**Обновленный показатель соответствия требованиям**: методология изменилась для поддержки синхронизации с показателем безопасности Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5ad86-118">**Updated Compliance Score**: The methodology has changed to support syncing with Microsoft Secure Score.</span></span> <span data-ttu-id="5ad86-119">Система оценки удаляет кредиты управления, управляемые Майкрософт, и фокусируется исключительно на выполнении элементов управления, управляемых заказчиком.</span><span class="sxs-lookup"><span data-stu-id="5ad86-119">The scoring system removes the Microsoft-managed control credits and focuses solely on the completion of customer-managed controls.</span></span>

## <a name="known-issues-in-compliance-manager-preview"></a><span data-ttu-id="5ad86-120">Известные проблемы в диспетчере соответствия требованиям (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="5ad86-120">Known issues in Compliance Manager (Preview)</span></span>

<span data-ttu-id="5ad86-121">В следующих разделах рассматриваются известные проблемы, которые необходимо устранить в будущих выпусках диспетчера соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="5ad86-121">The following sections cover known issues to be resolved in upcoming releases of Compliance Manager.</span></span>

### <a name="compliance-score"></a><span data-ttu-id="5ad86-122">Оценка соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="5ad86-122">Compliance Score</span></span>

- <span data-ttu-id="5ad86-123">Для элементов Action, помеченных как не включенные **в область**, баллы, назначенные элементу Action, не исключаются из вычисления оценки соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="5ad86-123">For Action Items marked as **Not in Scope**, the score assigned to the Action Item is not excluded from the Compliance Score calculation.</span></span> <span data-ttu-id="5ad86-124">Элементы действий, помеченные **не в области** , не увеличивают рейтинг соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="5ad86-124">Action Items marked **Not in Scope** do not increase your Compliance Score.</span></span>

### <a name="secure-score"></a><span data-ttu-id="5ad86-125">Оценка безопасности</span><span class="sxs-lookup"><span data-stu-id="5ad86-125">Secure Score</span></span>

- <span data-ttu-id="5ad86-126">Результаты безопасной оценки недоступны для некоторых элементов Action в некоторых подписках Microsoft 365 и Office 365.</span><span class="sxs-lookup"><span data-stu-id="5ad86-126">Secure Score results are not available for some Actions Items in certain Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="5ad86-127">В таких случаях результат безопасной оценки "не удалось обнаружить".</span><span class="sxs-lookup"><span data-stu-id="5ad86-127">The Secure Score result is 'Could not be detected' in these cases.</span></span>
- <span data-ttu-id="5ad86-128">Иногда результаты безопасности возвращаются для соответствующих политик и незавершенных элементов действий.</span><span class="sxs-lookup"><span data-stu-id="5ad86-128">Sometimes Secure Score results are returned for corresponding policies and Action Items not completed.</span></span>

### <a name="microsoft-managed-controls"></a><span data-ttu-id="5ad86-129">Элементы управления, управляемые корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5ad86-129">Microsoft-managed Controls</span></span>

- <span data-ttu-id="5ad86-130">Тестовая дата для элементов управления, управляемых Майкрософт, не отображается в пользовательском интерфейсе, даже если она включена в оценку.</span><span class="sxs-lookup"><span data-stu-id="5ad86-130">The test date for Microsoft-managed controls is not appearing in the UI, even when included in the Assessment.</span></span> <span data-ttu-id="5ad86-131">Чтобы просмотреть сведения о дате тестирования, необходимо экспортировать оценку.</span><span class="sxs-lookup"><span data-stu-id="5ad86-131">To see test date information, you must export the Assessment.</span></span>

### <a name="customization"></a><span data-ttu-id="5ad86-132">Настройка</span><span class="sxs-lookup"><span data-stu-id="5ad86-132">Customization</span></span>

- <span data-ttu-id="5ad86-133">Добавление пользовательских элементов управления позволяет добавить новый элемент управления к существующему семейству элементов управления, но не позволяет добавить новое семейство элементов управления.</span><span class="sxs-lookup"><span data-stu-id="5ad86-133">Adding custom Controls enables adding a new control to an existing control family, but it does not allow you to add a new Control Family.</span></span>
- <span data-ttu-id="5ad86-134">Этот выпуск не поддерживает связывание элементов действий и добавление действий или элементов управления для оценки.</span><span class="sxs-lookup"><span data-stu-id="5ad86-134">This release does not support linking Action Items or adding Actions Items or Controls to an Assessment.</span></span>
- <span data-ttu-id="5ad86-135">Если вы создаете дополнительное действие, его невозможно изменить или удалить.</span><span class="sxs-lookup"><span data-stu-id="5ad86-135">If you create a custom Action, you cannot edit or delete it.</span></span>

### <a name="control-families-not-shown-in-assessments"></a><span data-ttu-id="5ad86-136">Семейства элементов управления, не показанные в ходе оценки</span><span class="sxs-lookup"><span data-stu-id="5ad86-136">Control Families Not Shown in Assessments</span></span>

- <span data-ttu-id="5ad86-137">При импорте шаблона все оценки, основанные на этом шаблоне, отражают все семейства элементов управления, которые входят в шаблон.</span><span class="sxs-lookup"><span data-stu-id="5ad86-137">When you import a Template, all Assessments based on that Template reflect all Control Families that are part of the Template.</span></span> <span data-ttu-id="5ad86-138">Но если вы добавите в шаблон новые элементы управления, все существующие оценки не отразятся на изменениях.</span><span class="sxs-lookup"><span data-stu-id="5ad86-138">But if you add new Control Families to the Template, any existing Assessments will not reflect the changes.</span></span> <span data-ttu-id="5ad86-139">Изменения отражают только новые оценки, созданные в обновленном шаблоне.</span><span class="sxs-lookup"><span data-stu-id="5ad86-139">Only new Assessments created off the updated Template reflect the changes.</span></span>

### <a name="filters"></a><span data-ttu-id="5ad86-140">Фильтры</span><span class="sxs-lookup"><span data-stu-id="5ad86-140">Filters</span></span>

- <span data-ttu-id="5ad86-141">Фильтрация по элементам действий или элементам управления не приводит к согласованию правильных результатов.</span><span class="sxs-lookup"><span data-stu-id="5ad86-141">Filtering on Action Items or Controls does not consistently produce correct results.</span></span>

### <a name="templates"></a><span data-ttu-id="5ad86-142">Шаблоны</span><span class="sxs-lookup"><span data-stu-id="5ad86-142">Templates</span></span>

- <span data-ttu-id="5ad86-143">Архивные шаблоны доступны для редактирования, и их нельзя редактировать.</span><span class="sxs-lookup"><span data-stu-id="5ad86-143">Archived templates are editable and they should not be editable.</span></span>
- <span data-ttu-id="5ad86-144">Заблокированные шаблоны допускают создание оценки, если это не так.</span><span class="sxs-lookup"><span data-stu-id="5ad86-144">Locked templates allow for Assessment creation when they should not.</span></span> <span data-ttu-id="5ad86-145">Блокировка шаблона заключается в том, чтобы он не использовался для создания оценок.</span><span class="sxs-lookup"><span data-stu-id="5ad86-145">Locking a Template is meant to prevent it from being used to create Assessments.</span></span>

### <a name="export"></a><span data-ttu-id="5ad86-146">Экспорт</span><span class="sxs-lookup"><span data-stu-id="5ad86-146">Export</span></span>

- <span data-ttu-id="5ad86-147">Экспорт шаблона в JSON завершается с ошибкой, если состояние шаблона — " **импортировано** " или " **ожидающее утверждение**".</span><span class="sxs-lookup"><span data-stu-id="5ad86-147">Template export to JSON fails when the template status is set to **Imported** or **Pending Approval**.</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="5ad86-148">Поддерживаемые браузеры</span><span class="sxs-lookup"><span data-stu-id="5ad86-148">Supported browsers</span></span>

- <span data-ttu-id="5ad86-149">Поддерживаются последние версии Microsoft EDGE, Chrome и Safari.</span><span class="sxs-lookup"><span data-stu-id="5ad86-149">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="5ad86-150">В некоторых случаях обновленные данные не отображаются, пока браузер не обновится.</span><span class="sxs-lookup"><span data-stu-id="5ad86-150">There may be instances where updated data does not appear until your browser is refreshed.</span></span>
- <span data-ttu-id="5ad86-151">Предварительная версия Microsoft EDGE не поддерживается, но не имеет известных проблем.</span><span class="sxs-lookup"><span data-stu-id="5ad86-151">The preview version of Microsoft Edge is not supported but has no known issues.</span></span>
- <span data-ttu-id="5ad86-152">Internet Explorer не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5ad86-152">Internet Explorer is not supported.</span></span>

### <a name="session-timeout"></a><span data-ttu-id="5ad86-153">Время ожидания сеанса</span><span class="sxs-lookup"><span data-stu-id="5ad86-153">Session timeout</span></span>

- <span data-ttu-id="5ad86-154">При истечении времени ожидания сеанса может появиться сообщение об ошибке "что-то пошло не так".</span><span class="sxs-lookup"><span data-stu-id="5ad86-154">When a session times out, a “Something went wrong” error may appear.</span></span> <span data-ttu-id="5ad86-155">Чтобы устранить проблему, перейдите к [диспетчеру соответствия требованиям](https://servicetrust.microsoft.com/ComplianceManager) и снова войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="5ad86-155">To resolve, go to [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) and log in again.</span></span>
 
### <a name="language-support"></a><span data-ttu-id="5ad86-156">Поддержка языка</span><span class="sxs-lookup"><span data-stu-id="5ad86-156">Language support</span></span>

- <span data-ttu-id="5ad86-157">Все языки не поддерживаются для всех веб-страниц.</span><span class="sxs-lookup"><span data-stu-id="5ad86-157">All languages are not supported for all webpages.</span></span> <span data-ttu-id="5ad86-158">Если ваш локальный язык не поддерживается, просмотрите его на английском языке (США).</span><span class="sxs-lookup"><span data-stu-id="5ad86-158">If your local language is unsupported, view in US English.</span></span>