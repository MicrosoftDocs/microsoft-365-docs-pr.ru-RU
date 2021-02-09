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
ms.openlocfilehash: 7457084d49c5a9fef4ef79abc7702c6b473efcd2
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145305"
---
# <a name="alertevidence"></a><span data-ttu-id="e24d4-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="e24d4-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e24d4-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e24d4-105">**Applies to:**</span></span>
- <span data-ttu-id="e24d4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e24d4-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e24d4-107">Таблица в схеме повышенной охоты содержит сведения о различных сущностями — файлах, IP-адресах, URL-адресах, пользователях или устройствах, связанных с оповещениями из `AlertEvidence` Microsoft Defender для конечной точки, Microsoft Defender для Office 365, Microsoft Cloud App Security и Microsoft Defender для удостоверений. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e24d4-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="e24d4-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="e24d4-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="e24d4-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="e24d4-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="e24d4-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="e24d4-110">Column name</span></span> | <span data-ttu-id="e24d4-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="e24d4-111">Data type</span></span> | <span data-ttu-id="e24d4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e24d4-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="e24d4-113">datetime</span><span class="sxs-lookup"><span data-stu-id="e24d4-113">datetime</span></span> | <span data-ttu-id="e24d4-114">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="e24d4-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="e24d4-115">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-115">string</span></span> | <span data-ttu-id="e24d4-116">Уникальный идентификатор оповещения</span><span class="sxs-lookup"><span data-stu-id="e24d4-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="e24d4-117">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-117">string</span></span> | <span data-ttu-id="e24d4-118">Продукт или служба, которые предоставили сведения об оповещении</span><span class="sxs-lookup"><span data-stu-id="e24d4-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="e24d4-119">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-119">string</span></span> | <span data-ttu-id="e24d4-120">Тип объекта, например файл, процесс, устройство или пользователь</span><span class="sxs-lookup"><span data-stu-id="e24d4-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="e24d4-121">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-121">string</span></span> | <span data-ttu-id="e24d4-122">Как сущность участвует в оповещении, указывающее, влияет ли он или просто связан</span><span class="sxs-lookup"><span data-stu-id="e24d4-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="e24d4-123">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-123">string</span></span> | <span data-ttu-id="e24d4-124">Указывает, является ли сущность источником или местом назначения сетевого подключения</span><span class="sxs-lookup"><span data-stu-id="e24d4-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="e24d4-125">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-125">string</span></span> | <span data-ttu-id="e24d4-126">Имя файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="e24d4-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="e24d4-127">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-127">string</span></span> | <span data-ttu-id="e24d4-128">Папка, содержащая файл, к которой было применено записано действие</span><span class="sxs-lookup"><span data-stu-id="e24d4-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="e24d4-129">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-129">string</span></span> | <span data-ttu-id="e24d4-130">SHA-1 файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="e24d4-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="e24d4-131">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-131">string</span></span> | <span data-ttu-id="e24d4-132">SHA-256 файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="e24d4-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="e24d4-133">Это поле обычно не заполняется — используйте столбец SHA1, если он доступен.</span><span class="sxs-lookup"><span data-stu-id="e24d4-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="e24d4-134">int</span><span class="sxs-lookup"><span data-stu-id="e24d4-134">int</span></span> | <span data-ttu-id="e24d4-135">Размер файла в ветвях</span><span class="sxs-lookup"><span data-stu-id="e24d4-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="e24d4-136">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-136">string</span></span> | <span data-ttu-id="e24d4-137">Семейство вредоносных программ, под которые был классифицирован подозрительный или вредоносный файл или процесс</span><span class="sxs-lookup"><span data-stu-id="e24d4-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="e24d4-138">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-138">string</span></span> | <span data-ttu-id="e24d4-139">IP-адрес, к которому выполнено подключение</span><span class="sxs-lookup"><span data-stu-id="e24d4-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="e24d4-140">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-140">string</span></span> | <span data-ttu-id="e24d4-141">URL-адрес или полное доменное имя, к которому выполнено подключение</span><span class="sxs-lookup"><span data-stu-id="e24d4-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="e24d4-142">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-142">string</span></span> | <span data-ttu-id="e24d4-143">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="e24d4-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="e24d4-144">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-144">string</span></span> | <span data-ttu-id="e24d4-145">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="e24d4-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="e24d4-146">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-146">string</span></span> | <span data-ttu-id="e24d4-147">Идентификатор безопасности (SID) учетной записи</span><span class="sxs-lookup"><span data-stu-id="e24d4-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="e24d4-148">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-148">string</span></span> | <span data-ttu-id="e24d4-149">Уникальный идентификатор учетной записи в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e24d4-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountUpn` | <span data-ttu-id="e24d4-150">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-150">string</span></span> | <span data-ttu-id="e24d4-151">Имя пользователя-пользователя (UPN) учетной записи</span><span class="sxs-lookup"><span data-stu-id="e24d4-151">User principal name (UPN) of the account</span></span> |
| `DeviceId` | <span data-ttu-id="e24d4-152">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-152">string</span></span> | <span data-ttu-id="e24d4-153">Уникальный идентификатор устройства в службе</span><span class="sxs-lookup"><span data-stu-id="e24d4-153">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="e24d4-154">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-154">string</span></span> | <span data-ttu-id="e24d4-155">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="e24d4-155">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="e24d4-156">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-156">string</span></span> | <span data-ttu-id="e24d4-157">IP-адрес, присвоенный локальному устройству, используемму во время связи</span><span class="sxs-lookup"><span data-stu-id="e24d4-157">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="e24d4-158">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-158">string</span></span> | <span data-ttu-id="e24d4-159">Уникальный идентификатор сообщения электронной почты, сформированный в Office 365</span><span class="sxs-lookup"><span data-stu-id="e24d4-159">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="e24d4-160">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-160">string</span></span> | <span data-ttu-id="e24d4-161">Тема письма</span><span class="sxs-lookup"><span data-stu-id="e24d4-161">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="e24d4-162">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-162">string</span></span> | <span data-ttu-id="e24d4-163">Уникальный идентификатор приложения</span><span class="sxs-lookup"><span data-stu-id="e24d4-163">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="e24d4-164">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-164">string</span></span> | <span data-ttu-id="e24d4-165">Приложение, которое выполнило записанную действие</span><span class="sxs-lookup"><span data-stu-id="e24d4-165">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="e24d4-166">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-166">string</span></span> | <span data-ttu-id="e24d4-167">Командная строка, используемая для создания нового процесса</span><span class="sxs-lookup"><span data-stu-id="e24d4-167">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="e24d4-168">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-168">string</span></span> | <span data-ttu-id="e24d4-169">Дополнительные сведения о событии в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="e24d4-169">Additional information about the event in JSON array format</span></span> |
| `RegistryKey` |<span data-ttu-id="e24d4-170">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-170">string</span></span> | <span data-ttu-id="e24d4-171">Ключ реестра, к который было применено записано действие</span><span class="sxs-lookup"><span data-stu-id="e24d4-171">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueName` |<span data-ttu-id="e24d4-172">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-172">string</span></span> | <span data-ttu-id="e24d4-173">Имя значения реестра, к которое было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="e24d4-173">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` |<span data-ttu-id="e24d4-174">string</span><span class="sxs-lookup"><span data-stu-id="e24d4-174">string</span></span> | <span data-ttu-id="e24d4-175">Данные значения реестра, к которое было применено записано действие</span><span class="sxs-lookup"><span data-stu-id="e24d4-175">Data of the registry value that the recorded action was applied to</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e24d4-176">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="e24d4-176">Related topics</span></span>
- [<span data-ttu-id="e24d4-177">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="e24d4-177">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e24d4-178">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="e24d4-178">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e24d4-179">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="e24d4-179">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e24d4-180">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="e24d4-180">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e24d4-181">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="e24d4-181">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e24d4-182">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="e24d4-182">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
