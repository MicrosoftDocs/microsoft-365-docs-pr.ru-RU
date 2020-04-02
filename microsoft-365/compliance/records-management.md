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
ms.openlocfilehash: e74c7d9e5f01b49805fccdfac2c719835354b97a
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106085"
---
# <a name="records-management-in-microsoft-365"></a><span data-ttu-id="829aa-103">Управление записями в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="829aa-103">Records management in Microsoft 365</span></span>

><span data-ttu-id="829aa-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="829aa-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="829aa-105">Организациям всех типов требуется решение по управлению нормативными, юридическими и критически важными для бизнеса записями в корпоративных данных.</span><span class="sxs-lookup"><span data-stu-id="829aa-105">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="829aa-106">Управление записями в Microsoft 365 помогает организации управлять юридическими обязательствами, дает возможность продемонстрировать соответствие нормативным требованиям и повышает эффективность работы с помощью регулярной ликвидации элементов, которые больше не требуется хранить, не представляют ценность или не нужны для предприятия.</span><span class="sxs-lookup"><span data-stu-id="829aa-106">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="829aa-107">Решение для управления записями поддерживает следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="829aa-107">The records-management solution supports the following elements:</span></span>

- <span data-ttu-id="829aa-108">**Пометка содержимого как записи**.</span><span class="sxs-lookup"><span data-stu-id="829aa-108">**Label content as a record**.</span></span> <span data-ttu-id="829aa-109">Опубликуйте [метки записи](records.md), применяемые конечными пользователями, или [автоматически применяемые метки записи](labels.md#applying-a-retention-label-automatically-based-on-conditions) для элементов, содержащих определенную конфиденциальную информацию, ключевые слова или типы контента.</span><span class="sxs-lookup"><span data-stu-id="829aa-109">Publish [record labels](records.md) to be applied by end users or [auto-apply](labels.md#applying-a-retention-label-automatically-based-on-conditions) record labels to items containing specific sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="829aa-110">**Миграция плана хранения и управление им с помощью плана хранения** и использование [диспетчера плана хранения](file-plan-manager.md) для переноса существующего плана хранения или создания нового при помощи дескрипторов файлов и разворачивающихся иерархий.</span><span class="sxs-lookup"><span data-stu-id="829aa-110">**Migrate and manage your retention plan with file plan** and use [file plan manager](file-plan-manager.md) to bring in your existing retention plan, or build new with file descriptors and expanding hierarchies.</span></span>

- <span data-ttu-id="829aa-111">**Создание политик хранения и удаления в метке записи**.</span><span class="sxs-lookup"><span data-stu-id="829aa-111">**Establish retention and deletion policies within the record label**.</span></span> <span data-ttu-id="829aa-112">Определите сроки [хранения](retention-policies.md#retaining-content-for-a-specific-period-of-time) и [ликвидации](retention-policies.md#deleting-content-thats-older-than-a-specific-age) на основе различных факторов, в том числе даты последнего изменения или создания.</span><span class="sxs-lookup"><span data-stu-id="829aa-112">Define [retention](retention-policies.md#retaining-content-for-a-specific-period-of-time) and [disposition](retention-policies.md#deleting-content-thats-older-than-a-specific-age) periods based on various factors including the date last modified or created.</span></span>

- <span data-ttu-id="829aa-113">**Запуск хранения на основе события** с [хранением на основе событий](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="829aa-113">**Trigger event-based retention** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="829aa-114">**Проверка и подтверждение ликвидации** с помощью [проверки перед ликвидацией](disposition-reviews.md).</span><span class="sxs-lookup"><span data-stu-id="829aa-114">**Review and validate disposition** with [disposition review](disposition-reviews.md).</span></span>

- <span data-ttu-id="829aa-115">**Просмотр ликвидированных элементов с помощью проверки перед ликвидацией** и [экспорт отчета о ликвидации](disposition-reviews.md#export-the-disposition-items) для дальнейшей проверки и создания отчетов.</span><span class="sxs-lookup"><span data-stu-id="829aa-115">**Review disposed items with disposition review** and [export a disposition report](disposition-reviews.md#export-the-disposition-items) for further validation and reporting.</span></span>

- <span data-ttu-id="829aa-116">**Настройка определенных разрешений** для [предоставления правильного доступа](../security/office-365-security/permissions-in-the-security-and-compliance-center.md) функциям диспетчера записей в организации.</span><span class="sxs-lookup"><span data-stu-id="829aa-116">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="829aa-117">С помощью решения для управления записями в Microsoft 365 вы можете внедрять графики хранения вашей организации в план файлов, чтобы управлять хранением, объявлением записей и ликвидацией для поддержки полного жизненного цикла контента.</span><span class="sxs-lookup"><span data-stu-id="829aa-117">With the records-management solution in Microsoft 365, you can incorporate your organization’s retention schedules into the file plan to manage retention, records declaration, and disposition in support of the full content lifecycle.</span></span>
