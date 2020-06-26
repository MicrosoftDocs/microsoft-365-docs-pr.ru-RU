---
title: Таблица алертевиденце в схеме расширенного поискового окна
description: Сведения о файлах, сетевых адресах, пользователях или сведениях об устройствах, связанных с созданными оповещениями в таблице Алертевиденце расширенной схемы подсистемы Поиск
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справка по схеме, Кусто, таблица, столбец, тип данных, описание, Алертинфо, оповещения, сущности, пользователь, учетная запись
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
ms.openlocfilehash: a0f2ae36752a4415da7c1bc39ce35bd7f744a764
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899355"
---
# <a name="alertevidence"></a><span data-ttu-id="990b9-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="990b9-104">AlertEvidence</span></span>

<span data-ttu-id="990b9-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="990b9-105">**Applies to:**</span></span>
- <span data-ttu-id="990b9-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="990b9-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="990b9-107">`AlertEvidence`Таблица в схеме [расширенного](advanced-hunting-overview.md) поискового заданных содержит сведения о различных сущностях — файлах, IP-адресах, URL-адресах, пользователях или устройствах, связанных с оповещениями из пакета ATP (Майкрософт) atp, Office 365 ATP, Microsoft Cloud App Security и Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="990b9-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities — files, IP addresses, URLs, users, or devices — associated with alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="990b9-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="990b9-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="990b9-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="990b9-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="990b9-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="990b9-110">Column name</span></span> | <span data-ttu-id="990b9-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="990b9-111">Data type</span></span> | <span data-ttu-id="990b9-112">Описание</span><span class="sxs-lookup"><span data-stu-id="990b9-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="990b9-113">datetime</span><span class="sxs-lookup"><span data-stu-id="990b9-113">datetime</span></span> | <span data-ttu-id="990b9-114">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="990b9-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="990b9-115">string</span><span class="sxs-lookup"><span data-stu-id="990b9-115">string</span></span> | <span data-ttu-id="990b9-116">Уникальный идентификатор оповещения</span><span class="sxs-lookup"><span data-stu-id="990b9-116">Unique identifier for the alert</span></span> |
| `EntityType` | <span data-ttu-id="990b9-117">string</span><span class="sxs-lookup"><span data-stu-id="990b9-117">string</span></span> | <span data-ttu-id="990b9-118">Тип объекта, например файл, процесс, устройство или пользователь</span><span class="sxs-lookup"><span data-stu-id="990b9-118">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="990b9-119">string</span><span class="sxs-lookup"><span data-stu-id="990b9-119">string</span></span> | <span data-ttu-id="990b9-120">Способ участия объекта в оповещении, указывающий на то, что он повлиял или является просто связанным</span><span class="sxs-lookup"><span data-stu-id="990b9-120">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `SHA1` | <span data-ttu-id="990b9-121">string</span><span class="sxs-lookup"><span data-stu-id="990b9-121">string</span></span> | <span data-ttu-id="990b9-122">SHA-1 файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="990b9-122">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="990b9-123">string</span><span class="sxs-lookup"><span data-stu-id="990b9-123">string</span></span> | <span data-ttu-id="990b9-124">SHA-256 файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="990b9-124">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="990b9-125">Это поле обычно не заполняется. Используйте столбец SHA1, если он доступен.</span><span class="sxs-lookup"><span data-stu-id="990b9-125">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `RemoteIP` | <span data-ttu-id="990b9-126">string</span><span class="sxs-lookup"><span data-stu-id="990b9-126">string</span></span> | <span data-ttu-id="990b9-127">IP-адрес, к которому выполнено подключение</span><span class="sxs-lookup"><span data-stu-id="990b9-127">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="990b9-128">string</span><span class="sxs-lookup"><span data-stu-id="990b9-128">string</span></span> | <span data-ttu-id="990b9-129">URL-адрес или полное доменное имя, к которому выполнено подключение</span><span class="sxs-lookup"><span data-stu-id="990b9-129">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="990b9-130">string</span><span class="sxs-lookup"><span data-stu-id="990b9-130">string</span></span> | <span data-ttu-id="990b9-131">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="990b9-131">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="990b9-132">string</span><span class="sxs-lookup"><span data-stu-id="990b9-132">string</span></span> | <span data-ttu-id="990b9-133">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="990b9-133">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="990b9-134">string</span><span class="sxs-lookup"><span data-stu-id="990b9-134">string</span></span> | <span data-ttu-id="990b9-135">Идентификатор безопасности (SID) учетной записи</span><span class="sxs-lookup"><span data-stu-id="990b9-135">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="990b9-136">string</span><span class="sxs-lookup"><span data-stu-id="990b9-136">string</span></span> | <span data-ttu-id="990b9-137">Уникальный идентификатор учетной записи в Azure AD</span><span class="sxs-lookup"><span data-stu-id="990b9-137">Unique identifier for the account in Azure AD</span></span> |
| `DeviceId` | <span data-ttu-id="990b9-138">string</span><span class="sxs-lookup"><span data-stu-id="990b9-138">string</span></span> | <span data-ttu-id="990b9-139">Уникальный идентификатор для обслуживаемого компьютера</span><span class="sxs-lookup"><span data-stu-id="990b9-139">Unique identifier for the machine in the service</span></span> |
| `ThreatFamily` | <span data-ttu-id="990b9-140">string</span><span class="sxs-lookup"><span data-stu-id="990b9-140">string</span></span> | <span data-ttu-id="990b9-141">Семейство вредоносных программ, которые были классифицированы подозрительным или вредоносным файлом или процессом</span><span class="sxs-lookup"><span data-stu-id="990b9-141">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `EvidenceDirection` | <span data-ttu-id="990b9-142">string</span><span class="sxs-lookup"><span data-stu-id="990b9-142">string</span></span> | <span data-ttu-id="990b9-143">Указывает, является ли объект источником или местом назначения сетевого подключения.</span><span class="sxs-lookup"><span data-stu-id="990b9-143">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `AdditionalFields` | <span data-ttu-id="990b9-144">string</span><span class="sxs-lookup"><span data-stu-id="990b9-144">string</span></span> | <span data-ttu-id="990b9-145">Дополнительные сведения о событии в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="990b9-145">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="990b9-146">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="990b9-146">Related topics</span></span>
- [<span data-ttu-id="990b9-147">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="990b9-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="990b9-148">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="990b9-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="990b9-149">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="990b9-149">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="990b9-150">Поиск угроз на устройствах и в сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="990b9-150">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="990b9-151">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="990b9-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="990b9-152">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="990b9-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
