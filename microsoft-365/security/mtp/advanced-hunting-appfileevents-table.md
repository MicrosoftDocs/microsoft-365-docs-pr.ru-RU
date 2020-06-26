---
title: Таблица аппфиливентс в схеме расширенного поискового окна
description: Сведения о событиях, связанных с файлами, связанными с облачными приложениями и службами, в таблице Аппфиливентс расширенной схемы Поиск
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справка по схеме, Кусто, таблица, столбец, тип данных, описание, Аппфиливентс, безопасность облачных приложений, МКАС
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: da3b331d4f607aa0961e275db9444aadbec4fcf2
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899343"
---
# <a name="appfileevents"></a><span data-ttu-id="8ad8b-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="8ad8b-104">AppFileEvents</span></span>

<span data-ttu-id="8ad8b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="8ad8b-105">**Applies to:**</span></span>
- <span data-ttu-id="8ad8b-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="8ad8b-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="8ad8b-107">`AppFileEvents`Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит сведения о действиях, связанных с файлами, в облачных приложениях и службах, отслеживаемых Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="8ad8b-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="8ad8b-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="8ad8b-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="8ad8b-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="8ad8b-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="8ad8b-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="8ad8b-110">Column name</span></span> | <span data-ttu-id="8ad8b-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="8ad8b-111">Data type</span></span> | <span data-ttu-id="8ad8b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="8ad8b-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="8ad8b-113">datetime</span><span class="sxs-lookup"><span data-stu-id="8ad8b-113">datetime</span></span> | <span data-ttu-id="8ad8b-114">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="8ad8b-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="8ad8b-115">string</span><span class="sxs-lookup"><span data-stu-id="8ad8b-115">string</span></span> | <span data-ttu-id="8ad8b-116">Тип действия, вызвавшего событие</span><span class="sxs-lookup"><span data-stu-id="8ad8b-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="8ad8b-117">string</span><span class="sxs-lookup"><span data-stu-id="8ad8b-117">string</span></span> | <span data-ttu-id="8ad8b-118">Приложение, которое выполнило записанное действие</span><span class="sxs-lookup"><span data-stu-id="8ad8b-118">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="8ad8b-119">string</span><span class="sxs-lookup"><span data-stu-id="8ad8b-119">string</span></span> | <span data-ttu-id="8ad8b-120">Имя файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="8ad8b-120">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="8ad8b-121">string</span><span class="sxs-lookup"><span data-stu-id="8ad8b-121">string</span></span> | <span data-ttu-id="8ad8b-122">Папка, содержащая файл, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="8ad8b-122">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="8ad8b-123">string</span><span class="sxs-lookup"><span data-stu-id="8ad8b-123">string</span></span> | <span data-ttu-id="8ad8b-124">Исходное имя файла, переименованного в результате действия</span><span class="sxs-lookup"><span data-stu-id="8ad8b-124">Original name of the file that was renamed as a result of the action</span></span> |
| `AccountName` | <span data-ttu-id="8ad8b-125">string</span><span class="sxs-lookup"><span data-stu-id="8ad8b-125">string</span></span> | <span data-ttu-id="8ad8b-126">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="8ad8b-126">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="8ad8b-127">string</span><span class="sxs-lookup"><span data-stu-id="8ad8b-127">string</span></span> | <span data-ttu-id="8ad8b-128">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="8ad8b-128">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="8ad8b-129">string</span><span class="sxs-lookup"><span data-stu-id="8ad8b-129">string</span></span> | <span data-ttu-id="8ad8b-130">Имя участника-пользователя (UPN) учетной записи</span><span class="sxs-lookup"><span data-stu-id="8ad8b-130">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="8ad8b-131">string</span><span class="sxs-lookup"><span data-stu-id="8ad8b-131">string</span></span> | <span data-ttu-id="8ad8b-132">Уникальный идентификатор учетной записи в Azure AD</span><span class="sxs-lookup"><span data-stu-id="8ad8b-132">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="8ad8b-133">string</span><span class="sxs-lookup"><span data-stu-id="8ad8b-133">string</span></span> | <span data-ttu-id="8ad8b-134">Имя пользователя учетной записи, отображаемое в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="8ad8b-134">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="8ad8b-135">Как правило, это сочетание определенного или имени, посрединное инициирование, фамилия или фамилия.</span><span class="sxs-lookup"><span data-stu-id="8ad8b-135">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IPAddress` | <span data-ttu-id="8ad8b-136">string</span><span class="sxs-lookup"><span data-stu-id="8ad8b-136">string</span></span> | <span data-ttu-id="8ad8b-137">IP-адрес, назначенный конечной точке и используемый во время связанных сетевых коммуникаций</span><span class="sxs-lookup"><span data-stu-id="8ad8b-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="8ad8b-138">string</span><span class="sxs-lookup"><span data-stu-id="8ad8b-138">string</span></span> | <span data-ttu-id="8ad8b-139">Город, страна или другое географическое расположение, связанное с событием</span><span class="sxs-lookup"><span data-stu-id="8ad8b-139">City, country, or other geographic location associated with the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="8ad8b-140">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="8ad8b-140">Related topics</span></span>
- [<span data-ttu-id="8ad8b-141">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="8ad8b-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8ad8b-142">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="8ad8b-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8ad8b-143">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="8ad8b-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8ad8b-144">Поиск угроз на устройствах и в сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="8ad8b-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="8ad8b-145">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="8ad8b-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8ad8b-146">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="8ad8b-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
