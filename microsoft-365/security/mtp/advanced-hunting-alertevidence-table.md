---
title: Таблица AlertEvidence в схеме повышенной охоты
description: Сведения о сведениях, связанных с оповещениями, в таблице AlertEvidence схемы повышенной охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, evidence, file, IP address, device, machine, user, account
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c01b0aae1eff3d9b4add632aff0f13cb56941a30
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932314"
---
# <a name="alertevidence"></a><span data-ttu-id="30738-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="30738-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="30738-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="30738-105">**Applies to:**</span></span>
- <span data-ttu-id="30738-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="30738-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="30738-107">Таблица в схеме повышенной охоты содержит сведения о различных сущностями — файлах, IP-адресах, URL-адресах, пользователях или устройствах, связанных с оповещениями из `AlertEvidence` Microsoft Defender для конечной точки, Microsoft Defender для Office 365, Microsoft Cloud App Security и Microsoft Defender для удостоверений. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="30738-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="30738-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="30738-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="30738-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="30738-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="30738-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="30738-110">Column name</span></span> | <span data-ttu-id="30738-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="30738-111">Data type</span></span> | <span data-ttu-id="30738-112">Описание</span><span class="sxs-lookup"><span data-stu-id="30738-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="30738-113">datetime</span><span class="sxs-lookup"><span data-stu-id="30738-113">datetime</span></span> | <span data-ttu-id="30738-114">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="30738-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="30738-115">string</span><span class="sxs-lookup"><span data-stu-id="30738-115">string</span></span> | <span data-ttu-id="30738-116">Уникальный идентификатор оповещения</span><span class="sxs-lookup"><span data-stu-id="30738-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="30738-117">string</span><span class="sxs-lookup"><span data-stu-id="30738-117">string</span></span> | <span data-ttu-id="30738-118">Продукт или служба, которые предоставили сведения об оповещении</span><span class="sxs-lookup"><span data-stu-id="30738-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="30738-119">string</span><span class="sxs-lookup"><span data-stu-id="30738-119">string</span></span> | <span data-ttu-id="30738-120">Тип объекта, например файл, процесс, устройство или пользователь</span><span class="sxs-lookup"><span data-stu-id="30738-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="30738-121">string</span><span class="sxs-lookup"><span data-stu-id="30738-121">string</span></span> | <span data-ttu-id="30738-122">Как сущность участвует в оповещении, указывающее, влияет ли он или просто связан</span><span class="sxs-lookup"><span data-stu-id="30738-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="30738-123">string</span><span class="sxs-lookup"><span data-stu-id="30738-123">string</span></span> | <span data-ttu-id="30738-124">Указывает, является ли сущность источником или местом назначения сетевого подключения</span><span class="sxs-lookup"><span data-stu-id="30738-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="30738-125">string</span><span class="sxs-lookup"><span data-stu-id="30738-125">string</span></span> | <span data-ttu-id="30738-126">Имя файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="30738-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="30738-127">string</span><span class="sxs-lookup"><span data-stu-id="30738-127">string</span></span> | <span data-ttu-id="30738-128">Папка, содержащая файл, к которой было применено записано действие</span><span class="sxs-lookup"><span data-stu-id="30738-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="30738-129">string</span><span class="sxs-lookup"><span data-stu-id="30738-129">string</span></span> | <span data-ttu-id="30738-130">SHA-1 файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="30738-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="30738-131">string</span><span class="sxs-lookup"><span data-stu-id="30738-131">string</span></span> | <span data-ttu-id="30738-132">SHA-256 файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="30738-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="30738-133">Это поле обычно не заполняется — используйте столбец SHA1, если он доступен.</span><span class="sxs-lookup"><span data-stu-id="30738-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="30738-134">int</span><span class="sxs-lookup"><span data-stu-id="30738-134">int</span></span> | <span data-ttu-id="30738-135">Размер файла в ветвях</span><span class="sxs-lookup"><span data-stu-id="30738-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="30738-136">string</span><span class="sxs-lookup"><span data-stu-id="30738-136">string</span></span> | <span data-ttu-id="30738-137">Семейство вредоносных программ, под которые был классифицирован подозрительный или вредоносный файл или процесс</span><span class="sxs-lookup"><span data-stu-id="30738-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="30738-138">string</span><span class="sxs-lookup"><span data-stu-id="30738-138">string</span></span> | <span data-ttu-id="30738-139">IP-адрес, к которому выполнено подключение</span><span class="sxs-lookup"><span data-stu-id="30738-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="30738-140">string</span><span class="sxs-lookup"><span data-stu-id="30738-140">string</span></span> | <span data-ttu-id="30738-141">URL-адрес или полное доменное имя, к которому выполнено подключение</span><span class="sxs-lookup"><span data-stu-id="30738-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="30738-142">string</span><span class="sxs-lookup"><span data-stu-id="30738-142">string</span></span> | <span data-ttu-id="30738-143">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="30738-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="30738-144">string</span><span class="sxs-lookup"><span data-stu-id="30738-144">string</span></span> | <span data-ttu-id="30738-145">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="30738-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="30738-146">string</span><span class="sxs-lookup"><span data-stu-id="30738-146">string</span></span> | <span data-ttu-id="30738-147">Идентификатор безопасности (SID) учетной записи</span><span class="sxs-lookup"><span data-stu-id="30738-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="30738-148">string</span><span class="sxs-lookup"><span data-stu-id="30738-148">string</span></span> | <span data-ttu-id="30738-149">Уникальный идентификатор учетной записи в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="30738-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `DeviceId` | <span data-ttu-id="30738-150">string</span><span class="sxs-lookup"><span data-stu-id="30738-150">string</span></span> | <span data-ttu-id="30738-151">Уникальный идентификатор устройства в службе</span><span class="sxs-lookup"><span data-stu-id="30738-151">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="30738-152">string</span><span class="sxs-lookup"><span data-stu-id="30738-152">string</span></span> | <span data-ttu-id="30738-153">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="30738-153">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="30738-154">string</span><span class="sxs-lookup"><span data-stu-id="30738-154">string</span></span> | <span data-ttu-id="30738-155">IP-адрес, присвоенный локальному устройству, используемму во время связи</span><span class="sxs-lookup"><span data-stu-id="30738-155">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="30738-156">string</span><span class="sxs-lookup"><span data-stu-id="30738-156">string</span></span> | <span data-ttu-id="30738-157">Уникальный идентификатор сообщения электронной почты, сформированный в Office 365</span><span class="sxs-lookup"><span data-stu-id="30738-157">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="30738-158">string</span><span class="sxs-lookup"><span data-stu-id="30738-158">string</span></span> | <span data-ttu-id="30738-159">Тема письма</span><span class="sxs-lookup"><span data-stu-id="30738-159">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="30738-160">string</span><span class="sxs-lookup"><span data-stu-id="30738-160">string</span></span> | <span data-ttu-id="30738-161">Уникальный идентификатор приложения</span><span class="sxs-lookup"><span data-stu-id="30738-161">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="30738-162">string</span><span class="sxs-lookup"><span data-stu-id="30738-162">string</span></span> | <span data-ttu-id="30738-163">Приложение, которое выполнило записанную действие</span><span class="sxs-lookup"><span data-stu-id="30738-163">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="30738-164">string</span><span class="sxs-lookup"><span data-stu-id="30738-164">string</span></span> | <span data-ttu-id="30738-165">Командная строка, используемая для создания нового процесса</span><span class="sxs-lookup"><span data-stu-id="30738-165">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="30738-166">string</span><span class="sxs-lookup"><span data-stu-id="30738-166">string</span></span> | <span data-ttu-id="30738-167">Дополнительные сведения о событии в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="30738-167">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="30738-168">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="30738-168">Related topics</span></span>
- [<span data-ttu-id="30738-169">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="30738-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="30738-170">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="30738-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="30738-171">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="30738-171">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="30738-172">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="30738-172">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="30738-173">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="30738-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="30738-174">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="30738-174">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
