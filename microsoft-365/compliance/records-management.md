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
description: С помощью управления записями в Microsoft 365 вы можете применять определенные графики хранения вашей организации к плану файлов, чтобы управлять хранением, объявлением записей и ликвидацией для поддержки полного жизненного цикла контента.
ms.openlocfilehash: e4454ba5940d9a67d9f160d90d0a9db14563bcf7
ms.sourcegitcommit: f5cecd77e63ae8b47743d4f6dc3135f5decaf28b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2020
ms.locfileid: "43949252"
---
# <a name="records-management-in-microsoft-365"></a><span data-ttu-id="53c63-103">Управление записями в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="53c63-103">Records management in Microsoft 365</span></span>

><span data-ttu-id="53c63-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="53c63-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="53c63-105">Организациям всех типов требуется решение по управлению нормативными, юридическими и критически важными для бизнеса записями в корпоративных данных.</span><span class="sxs-lookup"><span data-stu-id="53c63-105">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="53c63-106">Управление записями в Microsoft 365 помогает организации управлять юридическими обязательствами, дает возможность продемонстрировать соответствие нормативным требованиям и повышает эффективность работы с помощью регулярной ликвидации элементов, которые больше не требуется хранить, не представляют ценность или не нужны для предприятия.</span><span class="sxs-lookup"><span data-stu-id="53c63-106">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="53c63-107">Решение для управления записями поддерживает следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="53c63-107">The records-management solution supports the following elements:</span></span>

- <span data-ttu-id="53c63-108">**Пометка содержимого как записи**.</span><span class="sxs-lookup"><span data-stu-id="53c63-108">**Label content as a record**.</span></span> <span data-ttu-id="53c63-109">Можно создавать и публиковать метки хранения, объявляющие содержимое [записями](records.md). После этого конечные пользователи смогут применять такие метки (а также их можно будет [применять автоматически](labels.md#applying-a-retention-label-automatically-based-on-conditions)) путем определения конфиденциальной информации, ключевых слов или типов содержимого.</span><span class="sxs-lookup"><span data-stu-id="53c63-109">Create and publish retention labels that declare content as a [record](records.md) that can then be applied by end users or [auto-applied](labels.md#applying-a-retention-label-automatically-based-on-conditions) by identifying sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="53c63-110">**Миграция плана хранения и управление им с помощью плана хранения** и использование [диспетчера плана хранения](file-plan-manager.md) для переноса существующего плана хранения или создания нового при помощи дескрипторов файлов и разворачивающихся иерархий.</span><span class="sxs-lookup"><span data-stu-id="53c63-110">**Migrate and manage your retention plan with file plan** and use [file plan manager](file-plan-manager.md) to bring in your existing retention plan, or build new with file descriptors and expanding hierarchies.</span></span>

- <span data-ttu-id="53c63-111">**Создание политик хранения и удаления**.</span><span class="sxs-lookup"><span data-stu-id="53c63-111">**Establish retention and deletion policies**.</span></span> <span data-ttu-id="53c63-112">Определение сроков [хранения](retention-policies.md#retaining-content-for-a-specific-period-of-time) и [ликвидации](retention-policies.md#deleting-content-thats-older-than-a-specific-age) на основе различных факторов, в том числе даты последнего изменения или создания.</span><span class="sxs-lookup"><span data-stu-id="53c63-112">Define [retention](retention-policies.md#retaining-content-for-a-specific-period-of-time) and [disposition](retention-policies.md#deleting-content-thats-older-than-a-specific-age) periods based on various factors that include the date last modified or created.</span></span>

- <span data-ttu-id="53c63-113">**Запуск хранения на основе события** с [хранением на основе событий](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="53c63-113">**Trigger event-based retention** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="53c63-114">**Проверка и подтверждение ликвидации** с помощью [проверки перед ликвидацией](disposition.md#disposition-reviews) и подтверждения [удаления записей](disposition.md#disposition-of-records).</span><span class="sxs-lookup"><span data-stu-id="53c63-114">**Review and validate disposition** with [disposition reviews](disposition.md#disposition-reviews) and proof of [records deletion](disposition.md#disposition-of-records).</span></span>

- <span data-ttu-id="53c63-115">**Экспорт информации обо всех ликвидированных элементах** с помощью [функции экспорта](disposition.md#filter-and-export-the-views).</span><span class="sxs-lookup"><span data-stu-id="53c63-115">**Export information about all disposed items** with the [export option](disposition.md#filter-and-export-the-views).</span></span>

- <span data-ttu-id="53c63-116">**Настройка определенных разрешений** для [предоставления правильного доступа](../security/office-365-security/permissions-in-the-security-and-compliance-center.md) функциям диспетчера записей в организации.</span><span class="sxs-lookup"><span data-stu-id="53c63-116">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="53c63-117">С помощью решения для управления записями в Microsoft 365 можно внедрять графики хранения, принятые вашей организации, в план хранения. Это даст возможность управлять хранением, объявлением записей и ликвидацией для поддержки полного жизненного цикла содержимого.</span><span class="sxs-lookup"><span data-stu-id="53c63-117">With the records-management solution in Microsoft 365, you can incorporate your organization’s retention schedules into the file plan to manage retention, records declaration, and disposition to support the full lifecycle of your content.</span></span>
