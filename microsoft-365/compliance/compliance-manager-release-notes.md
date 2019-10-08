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
ms.openlocfilehash: 3646d86cd9edac95975958458eb52a44fe30d2f5
ms.sourcegitcommit: 15173ab87325b7d79bab683702b35d77a355cd6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2019
ms.locfileid: "37417508"
---
# <a name="release-notes-for-compliance-manager-preview"></a><span data-ttu-id="f8184-104">Заметки о выпуске для диспетчера соответствия требованиям (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="f8184-104">Release Notes for Compliance Manager (Preview)</span></span>

<span data-ttu-id="f8184-105">Общедоступная Предварительная версия диспетчера соответствия требованиям обеспечивает ранний доступ к предстоящим функциям и обновлениям.</span><span class="sxs-lookup"><span data-stu-id="f8184-105">The public preview of Compliance Manager provides you with early access to upcoming functionality and updates.</span></span>

<span data-ttu-id="f8184-106">С помощью обновленного средства " [Диспетчер соответствия требованиям](https://servicetrust.microsoft.com/ComplianceManager) " на [портале доверия службы](https://servicetrust.microsoft.com) можно отслеживать, назначать и проверять нормативные действия, связанные с облачными службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f8184-106">You can use the updated [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) tool on the [Service Trust Portal](https://servicetrust.microsoft.com) to track, assign, and verify regulatory compliance activities related to Microsoft cloud services.</span></span>

## <a name="whats-new-in-compliance-manager-preview"></a><span data-ttu-id="f8184-107">Новые возможности в диспетчере соответствия требованиям (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="f8184-107">What’s new in Compliance Manager (Preview)</span></span>

- <span data-ttu-id="f8184-108">**Доступ к диспетчеру соответствия на основе ролей:** Роль **доступа к** предназначению по умолчанию удалена.</span><span class="sxs-lookup"><span data-stu-id="f8184-108">**Role-based access to Compliance Manager:** The default **Guess access** role has been removed.</span></span> <span data-ttu-id="f8184-109">Чтобы пользователь мог получить доступ к диспетчеру соответствия требованиям, глобальный администратор должен [назначить каждому пользователю разрешение](compliance-manager-overview#permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f8184-109">In order for a user to access Compliance Manager, the global admin must [assign each user a permission](compliance-manager-overview#permissions.md).</span></span>

- <span data-ttu-id="f8184-110">**Интеграция с показателем безопасности Майкрософт:** Диспетчер соответствия требованиям поддерживает интеграцию с [рейтингом безопасности Майкрософт](../security/mtp/microsoft-secure-score.md) путем сопоставления действий, управляемых клиентами, с более чем 50 действиями по безопасному рейтингу.</span><span class="sxs-lookup"><span data-stu-id="f8184-110">**Integration with Microsoft Secure Score:** Compliance Manager supports integration with [Microsoft Secure Score](../security/mtp/microsoft-secure-score.md) by mapping customer-managed Actions to more than 50 Secure Score actions.</span></span> <span data-ttu-id="f8184-111">После выполнения сопоставленного действия в показателе безопасности соответствующее действие диспетчера соответствия автоматически обновляется.</span><span class="sxs-lookup"><span data-stu-id="f8184-111">When you complete a mapped action in Secure Score, the corresponding Compliance Manager Action automatically updates.</span></span>

- <span data-ttu-id="f8184-112">**Импорт настраиваемых оценок:** Помимо встроенных оценок, диспетчер соответствия требованиям теперь поддерживает импорт пользовательских шаблонов.</span><span class="sxs-lookup"><span data-stu-id="f8184-112">**Import custom Assessments:** In addition to built-in Assessments, Compliance Manager now supports importing custom Templates.</span></span> <span data-ttu-id="f8184-113">Вы можете создавать собственные оценки для любого продукта или службы, а также любых стандартных или регулируемых.</span><span class="sxs-lookup"><span data-stu-id="f8184-113">You can create custom Assessments for any product or service and any standard or regulation.</span></span>

- <span data-ttu-id="f8184-114">**Элементы действий:** Элементы Action теперь являются отдельными элементами, и многие из них включают коллекцию телеметрии из API графа Microsoft Secure scores.</span><span class="sxs-lookup"><span data-stu-id="f8184-114">**Actions Items:** Action Items are now individual items and many include telemetry collection from the Microsoft Secure Score Graph API.</span></span> <span data-ttu-id="f8184-115">Там, где это возможно, в технических рекомендациях теперь есть ссылки на страницу "соответствующая конфигурация" в службе Office 365.</span><span class="sxs-lookup"><span data-stu-id="f8184-115">Where possible, technical action recommendations now have links to the applicable configuration page in the Office 365 service.</span></span>

- <span data-ttu-id="f8184-116">**Управление клиентами:** Новый интерфейс для управления новыми элементами данных в диспетчере соответствия требованиям (Предварительная версия):</span><span class="sxs-lookup"><span data-stu-id="f8184-116">**Tenant Management:** New interface for managing new data elements in Compliance Manager (Preview):</span></span>
    - <span data-ttu-id="f8184-117">**Измерения:** Просматривать, добавлять и настраивать метаданные для шаблонов, оценок и действий, которые позволяют создавать настраиваемые сводные элементы для фильтров.</span><span class="sxs-lookup"><span data-stu-id="f8184-117">**Dimensions:** View, add and customize metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
    - <span data-ttu-id="f8184-118">**Владельцы:** Укажите владельца для каждого элемента Action.</span><span class="sxs-lookup"><span data-stu-id="f8184-118">**Owners:** Specify an owner for each Action Item.</span></span>
    - <span data-ttu-id="f8184-119">**Действия клиента:** Управление полным списком элементов действий, включенных в Диспетчер соответствия требованиям (Предварительная версия), а также включение и отключение мониторинга безопасного индекса для действий, интегрированных с рейтингом безопасности.</span><span class="sxs-lookup"><span data-stu-id="f8184-119">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Action Items integrated with Secure Score.</span></span>

- <span data-ttu-id="f8184-120">**Обновленный показатель соответствия требованиям**: методология изменилась для поддержки синхронизации с показателем безопасности Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f8184-120">**Updated Compliance Score**: The methodology has changed to support syncing with Microsoft Secure Score.</span></span> <span data-ttu-id="f8184-121">Оценка рассчитывается на основе оценок действий, управляемых корпорацией Майкрософт, и показателей действий, управляемых клиентами.</span><span class="sxs-lookup"><span data-stu-id="f8184-121">The score is calculated based on Microsoft-managed action scores and customer-managed action scores.</span></span>

## <a name="known-issues-in-compliance-manager-preview"></a><span data-ttu-id="f8184-122">Известные проблемы в диспетчере соответствия требованиям (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="f8184-122">Known issues in Compliance Manager (Preview)</span></span>

<span data-ttu-id="f8184-123">В следующих разделах рассматриваются известные проблемы, которые необходимо устранить в будущих выпусках диспетчера соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="f8184-123">The following sections cover known issues to be resolved in upcoming releases of Compliance Manager.</span></span>

### <a name="compliance-score"></a><span data-ttu-id="f8184-124">Оценка соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="f8184-124">Compliance Score</span></span>

- <span data-ttu-id="f8184-125">Для элементов Action, помеченных как не включенные **в область**, баллы, назначенные элементу Action, не исключаются из вычисления оценки соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="f8184-125">For Action Items marked as **Not in Scope**, the score assigned to the Action Item is not excluded from the Compliance Score calculation.</span></span> <span data-ttu-id="f8184-126">Элементы действий, помеченные **не в области** , не увеличивают рейтинг соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="f8184-126">Action Items marked **Not in Scope** do not increase your Compliance Score.</span></span>

### <a name="secure-score"></a><span data-ttu-id="f8184-127">Оценка безопасности</span><span class="sxs-lookup"><span data-stu-id="f8184-127">Secure Score</span></span>

- <span data-ttu-id="f8184-128">Результаты безопасной оценки недоступны для некоторых элементов Action в некоторых подписках Microsoft 365 и Office 365.</span><span class="sxs-lookup"><span data-stu-id="f8184-128">Secure Score results are not available for some Actions Items in certain Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="f8184-129">В таких случаях результат безопасной оценки "не удалось обнаружить".</span><span class="sxs-lookup"><span data-stu-id="f8184-129">The Secure Score result is 'Could not be detected' in these cases.</span></span>
- <span data-ttu-id="f8184-130">Иногда результаты безопасности возвращаются для соответствующих политик и незавершенных элементов действий.</span><span class="sxs-lookup"><span data-stu-id="f8184-130">Sometimes Secure Score results are returned for corresponding policies and Action Items not completed.</span></span>

### <a name="microsoft-managed-controls"></a><span data-ttu-id="f8184-131">Элементы управления, управляемые корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="f8184-131">Microsoft-managed Controls</span></span>

- <span data-ttu-id="f8184-132">Тестовая дата для элементов управления, управляемых Майкрософт, не отображается в пользовательском интерфейсе, даже если она включена в оценку.</span><span class="sxs-lookup"><span data-stu-id="f8184-132">The test date for Microsoft-managed controls is not appearing in the UI, even when included in the Assessment.</span></span> <span data-ttu-id="f8184-133">Чтобы просмотреть сведения о дате тестирования, необходимо экспортировать оценку.</span><span class="sxs-lookup"><span data-stu-id="f8184-133">To see test date information, you must export the Assessment.</span></span>

### <a name="customization"></a><span data-ttu-id="f8184-134">Настройка</span><span class="sxs-lookup"><span data-stu-id="f8184-134">Customization</span></span>

- <span data-ttu-id="f8184-135">Добавление пользовательских элементов управления позволяет добавить новый элемент управления к существующему семейству элементов управления, но не позволяет добавить новое семейство элементов управления.</span><span class="sxs-lookup"><span data-stu-id="f8184-135">Adding custom Controls enables adding a new control to an existing control family, but it does not allow you to add a new Control Family.</span></span>
- <span data-ttu-id="f8184-136">Этот выпуск не поддерживает связывание элементов действий и добавление действий или элементов управления для оценки.</span><span class="sxs-lookup"><span data-stu-id="f8184-136">This release does not support linking Action Items or adding Actions Items or Controls to an Assessment.</span></span>
- <span data-ttu-id="f8184-137">Если вы создаете дополнительное действие, его невозможно изменить или удалить.</span><span class="sxs-lookup"><span data-stu-id="f8184-137">If you create a custom Action, you cannot edit or delete it.</span></span>

### <a name="control-families-not-shown-in-assessments"></a><span data-ttu-id="f8184-138">Семейства элементов управления, не показанные в ходе оценки</span><span class="sxs-lookup"><span data-stu-id="f8184-138">Control Families Not Shown in Assessments</span></span>

- <span data-ttu-id="f8184-139">При импорте шаблона все оценки, основанные на этом шаблоне, отражают все семейства элементов управления, которые входят в шаблон.</span><span class="sxs-lookup"><span data-stu-id="f8184-139">When you import a Template, all Assessments based on that Template reflect all Control Families that are part of the Template.</span></span> <span data-ttu-id="f8184-140">Но если вы добавите в шаблон новые элементы управления, все существующие оценки не отразятся на изменениях.</span><span class="sxs-lookup"><span data-stu-id="f8184-140">But if you add new Control Families to the Template, any existing Assessments will not reflect the changes.</span></span> <span data-ttu-id="f8184-141">Изменения отражают только новые оценки, созданные в обновленном шаблоне.</span><span class="sxs-lookup"><span data-stu-id="f8184-141">Only new Assessments created off the updated Template reflect the changes.</span></span>

### <a name="filters"></a><span data-ttu-id="f8184-142">Фильтры</span><span class="sxs-lookup"><span data-stu-id="f8184-142">Filters</span></span>

- <span data-ttu-id="f8184-143">Фильтрация по элементам действий или элементам управления не приводит к согласованию правильных результатов.</span><span class="sxs-lookup"><span data-stu-id="f8184-143">Filtering on Action Items or Controls does not consistently produce correct results.</span></span>

### <a name="templates"></a><span data-ttu-id="f8184-144">Шаблоны</span><span class="sxs-lookup"><span data-stu-id="f8184-144">Templates</span></span>

- <span data-ttu-id="f8184-145">Архивные шаблоны доступны для редактирования, и их нельзя редактировать.</span><span class="sxs-lookup"><span data-stu-id="f8184-145">Archived templates are editable and they should not be editable.</span></span>
- <span data-ttu-id="f8184-146">Заблокированные шаблоны допускают создание оценки, если это не так.</span><span class="sxs-lookup"><span data-stu-id="f8184-146">Locked templates allow for Assessment creation when they should not.</span></span> <span data-ttu-id="f8184-147">Блокировка шаблона заключается в том, чтобы он не использовался для создания оценок.</span><span class="sxs-lookup"><span data-stu-id="f8184-147">Locking a Template is meant to prevent it from being used to create Assessments.</span></span>

### <a name="export"></a><span data-ttu-id="f8184-148">Экспорт</span><span class="sxs-lookup"><span data-stu-id="f8184-148">Export</span></span>

- <span data-ttu-id="f8184-149">Экспорт шаблона в JSON завершается с ошибкой, если состояние шаблона — " **импортировано** " или " **ожидающее утверждение**".</span><span class="sxs-lookup"><span data-stu-id="f8184-149">Template export to JSON fails when the template status is set to **Imported** or **Pending Approval**.</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="f8184-150">Поддерживаемые браузеры</span><span class="sxs-lookup"><span data-stu-id="f8184-150">Supported browsers</span></span>

- <span data-ttu-id="f8184-151">Поддерживаются последние версии Microsoft EDGE, Chrome и Safari.</span><span class="sxs-lookup"><span data-stu-id="f8184-151">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="f8184-152">В некоторых случаях обновленные данные не отображаются, пока браузер не обновится.</span><span class="sxs-lookup"><span data-stu-id="f8184-152">There may be instances where updated data does not appear until your browser is refreshed.</span></span>
- <span data-ttu-id="f8184-153">Предварительная версия Microsoft EDGE не поддерживается, но не имеет известных проблем.</span><span class="sxs-lookup"><span data-stu-id="f8184-153">The preview version of Microsoft Edge is not supported but has no known issues.</span></span>
- <span data-ttu-id="f8184-154">Internet Explorer не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f8184-154">Internet Explorer is not supported.</span></span>

### <a name="session-timeout"></a><span data-ttu-id="f8184-155">Время ожидания сеанса</span><span class="sxs-lookup"><span data-stu-id="f8184-155">Session timeout</span></span>

- <span data-ttu-id="f8184-156">При истечении времени ожидания сеанса может появиться сообщение об ошибке "что-то пошло не так".</span><span class="sxs-lookup"><span data-stu-id="f8184-156">When a session times out, a “Something went wrong” error may appear.</span></span> <span data-ttu-id="f8184-157">Чтобы устранить проблему, перейдите к [диспетчеру соответствия требованиям](https://servicetrust.microsoft.com/ComplianceManager) и снова войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="f8184-157">To resolve, go to [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) and log in again.</span></span>
 
### <a name="language-support"></a><span data-ttu-id="f8184-158">Поддержка языка</span><span class="sxs-lookup"><span data-stu-id="f8184-158">Language support</span></span>

- <span data-ttu-id="f8184-159">Все языки не поддерживаются для всех веб-страниц.</span><span class="sxs-lookup"><span data-stu-id="f8184-159">All languages are not supported for all webpages.</span></span> <span data-ttu-id="f8184-160">Если ваш локальный язык не поддерживается, просмотрите его на английском языке (США).</span><span class="sxs-lookup"><span data-stu-id="f8184-160">If your local language is unsupported, view in US English.</span></span>