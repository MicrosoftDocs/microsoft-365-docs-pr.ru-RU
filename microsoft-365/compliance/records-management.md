---
title: Управление записями
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: С помощью управления записями в Microsoft 365 вы можете применять графики хранения к плану файлов, чтобы управлять хранением, объявлением записей и ликвидацией.
ms.openlocfilehash: 08b028bbd28c06684245321e09f8ef3252098956
ms.sourcegitcommit: a53af7a228bb1f58cb8128a69a19da49f9e28700
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "45372492"
---
# <a name="records-management-in-microsoft-365"></a><span data-ttu-id="37256-103">Управление записями в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="37256-103">Records management in Microsoft 365</span></span>

><span data-ttu-id="37256-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="37256-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="37256-105">Организациям всех типов требуется решение по управлению нормативными, юридическими и критически важными для бизнеса записями в корпоративных данных.</span><span class="sxs-lookup"><span data-stu-id="37256-105">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="37256-106">Управление записями в Microsoft 365 помогает организации управлять юридическими обязательствами, дает возможность продемонстрировать соответствие нормативным требованиям и повышает эффективность работы с помощью регулярной ликвидации элементов, которые больше не требуется хранить, не представляют ценность или не нужны для предприятия.</span><span class="sxs-lookup"><span data-stu-id="37256-106">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="37256-107">Управление записями в Microsoft 365 обеспечивает перечисленные ниже возможности.</span><span class="sxs-lookup"><span data-stu-id="37256-107">Records management in Microsoft 365 provides the following capabilities:</span></span>

- <span data-ttu-id="37256-108">**Пометка содержимого как записи**.</span><span class="sxs-lookup"><span data-stu-id="37256-108">**Label content as a record**.</span></span> <span data-ttu-id="37256-109">Создавайте и настраивайте метки хранения, чтобы помечать содержимое как [запись](records.md). Их затем можно применять вручную или [автоматически](apply-retention-labels-automatically.md) путем определения конфиденциальной информации, ключевых слов или типов содержимого.</span><span class="sxs-lookup"><span data-stu-id="37256-109">Create and configure retention labels to mark content as a [record](records.md) that can then be applied by users or [auto-applied](apply-retention-labels-automatically.md) by identifying sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="37256-110">**Перенос требований к хранению и управление ими с помощью плана хранения**.</span><span class="sxs-lookup"><span data-stu-id="37256-110">**Migrate and manage your retention requirements with file plan**.</span></span> <span data-ttu-id="37256-111">Вы можете перенести существующий [план хранения](file-plan-manager.md) в Microsoft 365 или создать новый план для расширенных функций управления.</span><span class="sxs-lookup"><span data-stu-id="37256-111">By using a [file plan](file-plan-manager.md), you can bring in an existing retention plan to Microsoft 365, or build a new one for enhanced management capabilities.</span></span>

- <span data-ttu-id="37256-112">**Настройка параметров хранения и удаления с помощью метки хранения**.</span><span class="sxs-lookup"><span data-stu-id="37256-112">**Configure retention and deletion settings with the retention label**.</span></span> <span data-ttu-id="37256-113">Определение сроков и действий хранения на основе различных факторов, в том числе даты последнего изменения или создания.</span><span class="sxs-lookup"><span data-stu-id="37256-113">Define retention periods and actions based on various factors that include the date last modified or created.</span></span>

- <span data-ttu-id="37256-114">**Запуск различных периодов хранения** с помощью [функции хранения на основе событий](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="37256-114">**Start different retention periods when an event occurs** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="37256-115">**Проверка и подтверждение ликвидации** с помощью [проверки перед ликвидацией](disposition.md#disposition-reviews) и подтверждения [удаления записей](disposition.md#disposition-of-records).</span><span class="sxs-lookup"><span data-stu-id="37256-115">**Review and validate disposition** with [disposition reviews](disposition.md#disposition-reviews) and proof of [records deletion](disposition.md#disposition-of-records).</span></span>

- <span data-ttu-id="37256-116">**Экспорт информации обо всех ликвидированных элементах** с помощью [функции экспорта](disposition.md#filter-and-export-the-views).</span><span class="sxs-lookup"><span data-stu-id="37256-116">**Export information about all disposed items** with the [export option](disposition.md#filter-and-export-the-views).</span></span>

- <span data-ttu-id="37256-117">**Настройка определенных разрешений** для [предоставления правильного доступа](../security/office-365-security/permissions-in-the-security-and-compliance-center.md) функциям диспетчера записей в организации.</span><span class="sxs-lookup"><span data-stu-id="37256-117">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="37256-118">С помощью решения для управления записями в Microsoft 365 можно внедрять графики и требования организации в план, который управляет хранением, объявлением записей и ликвидацией для поддержки полного жизненного цикла содержимого.</span><span class="sxs-lookup"><span data-stu-id="37256-118">With the records-management solution in Microsoft 365, you can incorporate your organization's retention schedules and requirements into a file plan that manages retention, records declaration, and disposition to support the full lifecycle of your content.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="37256-119">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="37256-119">Additional resources</span></span>

<span data-ttu-id="37256-120">Сведения об управлении записями представлены [в записи вебинара](https://aka.ms/MIPC/Video-RecordsManagementWebinar) и [презентации с вопросами и ответами](https://aka.ms/MIPC/Blog-RecordsManagementWebinar).</span><span class="sxs-lookup"><span data-stu-id="37256-120">See the [webinar recording](https://aka.ms/MIPC/Video-RecordsManagementWebinar) and [deck with FAQs](https://aka.ms/MIPC/Blog-RecordsManagementWebinar) for records management.</span></span>

## <a name="next-steps"></a><span data-ttu-id="37256-121">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="37256-121">Next steps</span></span>

<span data-ttu-id="37256-122">Если вы готовы приступить к управлению записями в Microsoft 365, см. статью [Сведения о записях](records.md).</span><span class="sxs-lookup"><span data-stu-id="37256-122">If you are ready to get started with records management in Microsoft 365, see [Learn about records](records.md).</span></span>
