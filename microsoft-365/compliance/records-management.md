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
ms.openlocfilehash: 48705ac6d0c271ca2646de7c058a340ee3f736ae
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818959"
---
# <a name="records-management-in-microsoft-365"></a><span data-ttu-id="4cb87-103">Управление записями в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4cb87-103">Records management in Microsoft 365</span></span>

><span data-ttu-id="4cb87-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="4cb87-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="4cb87-105">Организациям всех типов требуется решение по управлению нормативными, юридическими и критически важными для бизнеса записями в корпоративных данных.</span><span class="sxs-lookup"><span data-stu-id="4cb87-105">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="4cb87-106">Управление записями в Microsoft 365 помогает организации управлять юридическими обязательствами, дает возможность продемонстрировать соответствие нормативным требованиям и повышает эффективность работы с помощью регулярной ликвидации элементов, которые больше не требуется хранить, не представляют ценность или не нужны для предприятия.</span><span class="sxs-lookup"><span data-stu-id="4cb87-106">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="4cb87-107">Управление записями в Microsoft 365 обеспечивает перечисленные ниже возможности.</span><span class="sxs-lookup"><span data-stu-id="4cb87-107">Records management in Microsoft 365 provides the following capabilities:</span></span>

- <span data-ttu-id="4cb87-108">**Пометка содержимого как записи**.</span><span class="sxs-lookup"><span data-stu-id="4cb87-108">**Label content as a record**.</span></span> <span data-ttu-id="4cb87-109">Создавайте и публикуйте метки хранения, которые помечают содержимое как [запись](records.md) и затем могут быть применены пользователями или [применены автоматически](labels.md#applying-a-retention-label-automatically-based-on-conditions) путем определения конфиденциальной информации, ключевых слов или типов содержимого.</span><span class="sxs-lookup"><span data-stu-id="4cb87-109">Create and publish retention labels that mark content as a [record](records.md) that can then be applied by end users or [auto-applied](labels.md#applying-a-retention-label-automatically-based-on-conditions) by identifying sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="4cb87-110">**Перенос требований к хранению и управление ими с помощью плана хранения**.</span><span class="sxs-lookup"><span data-stu-id="4cb87-110">**Migrate and manage your retention requirements with file plan**.</span></span> <span data-ttu-id="4cb87-111">Вы можете перенести существующий [план хранения](file-plan-manager.md) в Microsoft 365 или создать новый план для расширенных функций управления.</span><span class="sxs-lookup"><span data-stu-id="4cb87-111">By using a [file plan](file-plan-manager.md), you can bring in an existing retention plan to Microsoft 365, or build a new one for enhanced management capabilities.</span></span>

- <span data-ttu-id="4cb87-112">**Создание политик хранения и удаления в метке записи**.</span><span class="sxs-lookup"><span data-stu-id="4cb87-112">**Establish retention and deletion policies within the record label**.</span></span> <span data-ttu-id="4cb87-113">Определение сроков [хранения](create-retention-policies.md#retaining-content-for-a-specific-period-of-time) и [ликвидации](create-retention-policies.md#deleting-content-thats-older-than-a-specific-age) на основе различных факторов, в том числе даты последнего изменения или создания.</span><span class="sxs-lookup"><span data-stu-id="4cb87-113">Define [retention](create-retention-policies.md#retaining-content-for-a-specific-period-of-time) and [disposition](create-retention-policies.md#deleting-content-thats-older-than-a-specific-age) periods based on various factors that include the date last modified or created.</span></span>

- <span data-ttu-id="4cb87-114">**Запуск хранения на основе события** с [хранением на основе событий](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="4cb87-114">**Trigger event-based retention** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="4cb87-115">**Проверка и подтверждение ликвидации** с помощью [проверки перед ликвидацией](disposition.md#disposition-reviews) и подтверждения [удаления записей](disposition.md#disposition-of-records).</span><span class="sxs-lookup"><span data-stu-id="4cb87-115">**Review and validate disposition** with [disposition reviews](disposition.md#disposition-reviews) and proof of [records deletion](disposition.md#disposition-of-records).</span></span>

- <span data-ttu-id="4cb87-116">**Экспорт информации обо всех ликвидированных элементах** с помощью [функции экспорта](disposition.md#filter-and-export-the-views).</span><span class="sxs-lookup"><span data-stu-id="4cb87-116">**Export information about all disposed items** with the [export option](disposition.md#filter-and-export-the-views).</span></span>

- <span data-ttu-id="4cb87-117">**Настройка определенных разрешений** для [предоставления правильного доступа](../security/office-365-security/permissions-in-the-security-and-compliance-center.md) функциям диспетчера записей в организации.</span><span class="sxs-lookup"><span data-stu-id="4cb87-117">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="4cb87-118">С помощью решения для управления записями в Microsoft 365 можно внедрять графики хранения, принятые вашей организации, в план хранения. Это даст возможность управлять хранением, объявлением записей и ликвидацией для поддержки полного жизненного цикла содержимого.</span><span class="sxs-lookup"><span data-stu-id="4cb87-118">With the records-management solution in Microsoft 365, you can incorporate your organization’s retention schedules into the file plan to manage retention, records declaration, and disposition to support the full lifecycle of your content.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4cb87-119">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="4cb87-119">Next steps</span></span>

<span data-ttu-id="4cb87-120">Если вы готовы приступить к управлению записями в Microsoft 365, см. статью [Сведения о записях](records.md).</span><span class="sxs-lookup"><span data-stu-id="4cb87-120">If you are ready to get started with records management in Microsoft 365, see [Learn about records](records.md).</span></span>
