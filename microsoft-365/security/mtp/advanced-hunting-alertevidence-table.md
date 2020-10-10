---
title: Таблица алертевиденце в схеме расширенного поискового окна
description: Сведения, связанные с оповещениями в таблице Алертевиденце расширенной схемы поискового подсистемы
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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: ec6fe3d080efb396ce0ecacadd3d5d9a8fa9f8d1
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413202"
---
# <a name="alertevidence"></a><span data-ttu-id="69313-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="69313-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="69313-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="69313-105">**Applies to:**</span></span>
- <span data-ttu-id="69313-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="69313-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="69313-107">`AlertEvidence`Таблица в схеме [расширенного](advanced-hunting-overview.md) поискового заданных содержит сведения о различных сущностях — файлах, IP-адресах, URL-адресах, пользователях или устройствах, связанных с оповещениями из пакета ATP (Майкрософт) atp, Office 365 ATP, Microsoft Cloud App Security и Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="69313-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="69313-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="69313-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="69313-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="69313-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="69313-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="69313-110">Column name</span></span> | <span data-ttu-id="69313-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="69313-111">Data type</span></span> | <span data-ttu-id="69313-112">Описание</span><span class="sxs-lookup"><span data-stu-id="69313-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="69313-113">datetime</span><span class="sxs-lookup"><span data-stu-id="69313-113">datetime</span></span> | <span data-ttu-id="69313-114">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="69313-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="69313-115">string</span><span class="sxs-lookup"><span data-stu-id="69313-115">string</span></span> | <span data-ttu-id="69313-116">Уникальный идентификатор оповещения</span><span class="sxs-lookup"><span data-stu-id="69313-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="69313-117">string</span><span class="sxs-lookup"><span data-stu-id="69313-117">string</span></span> | <span data-ttu-id="69313-118">Продукт или услуга, которые предоставили информацию оповещений</span><span class="sxs-lookup"><span data-stu-id="69313-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="69313-119">string</span><span class="sxs-lookup"><span data-stu-id="69313-119">string</span></span> | <span data-ttu-id="69313-120">Тип объекта, например файл, процесс, устройство или пользователь</span><span class="sxs-lookup"><span data-stu-id="69313-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="69313-121">string</span><span class="sxs-lookup"><span data-stu-id="69313-121">string</span></span> | <span data-ttu-id="69313-122">Способ участия объекта в оповещении, указывающий на то, что он повлиял или является просто связанным</span><span class="sxs-lookup"><span data-stu-id="69313-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="69313-123">string</span><span class="sxs-lookup"><span data-stu-id="69313-123">string</span></span> | <span data-ttu-id="69313-124">Указывает, является ли объект источником или местом назначения сетевого подключения.</span><span class="sxs-lookup"><span data-stu-id="69313-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="69313-125">string</span><span class="sxs-lookup"><span data-stu-id="69313-125">string</span></span> | <span data-ttu-id="69313-126">Имя файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="69313-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="69313-127">string</span><span class="sxs-lookup"><span data-stu-id="69313-127">string</span></span> | <span data-ttu-id="69313-128">Папка, содержащая файл, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="69313-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="69313-129">string</span><span class="sxs-lookup"><span data-stu-id="69313-129">string</span></span> | <span data-ttu-id="69313-130">SHA-1 файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="69313-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="69313-131">string</span><span class="sxs-lookup"><span data-stu-id="69313-131">string</span></span> | <span data-ttu-id="69313-132">SHA-256 файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="69313-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="69313-133">Это поле обычно не заполняется — используйте столбец SHA1, если он доступен.</span><span class="sxs-lookup"><span data-stu-id="69313-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="69313-134">int</span><span class="sxs-lookup"><span data-stu-id="69313-134">int</span></span> | <span data-ttu-id="69313-135">Размер файла в байтах</span><span class="sxs-lookup"><span data-stu-id="69313-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="69313-136">string</span><span class="sxs-lookup"><span data-stu-id="69313-136">string</span></span> | <span data-ttu-id="69313-137">Семейство вредоносных программ, которые были классифицированы подозрительным или вредоносным файлом или процессом</span><span class="sxs-lookup"><span data-stu-id="69313-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="69313-138">string</span><span class="sxs-lookup"><span data-stu-id="69313-138">string</span></span> | <span data-ttu-id="69313-139">IP-адрес, к которому выполнено подключение</span><span class="sxs-lookup"><span data-stu-id="69313-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="69313-140">string</span><span class="sxs-lookup"><span data-stu-id="69313-140">string</span></span> | <span data-ttu-id="69313-141">URL-адрес или полное доменное имя, к которому выполнено подключение</span><span class="sxs-lookup"><span data-stu-id="69313-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="69313-142">string</span><span class="sxs-lookup"><span data-stu-id="69313-142">string</span></span> | <span data-ttu-id="69313-143">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="69313-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="69313-144">string</span><span class="sxs-lookup"><span data-stu-id="69313-144">string</span></span> | <span data-ttu-id="69313-145">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="69313-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="69313-146">string</span><span class="sxs-lookup"><span data-stu-id="69313-146">string</span></span> | <span data-ttu-id="69313-147">Идентификатор безопасности (SID) учетной записи</span><span class="sxs-lookup"><span data-stu-id="69313-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="69313-148">string</span><span class="sxs-lookup"><span data-stu-id="69313-148">string</span></span> | <span data-ttu-id="69313-149">Уникальный идентификатор учетной записи в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="69313-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `DeviceId` | <span data-ttu-id="69313-150">string</span><span class="sxs-lookup"><span data-stu-id="69313-150">string</span></span> | <span data-ttu-id="69313-151">Уникальный идентификатор устройства в службе</span><span class="sxs-lookup"><span data-stu-id="69313-151">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="69313-152">string</span><span class="sxs-lookup"><span data-stu-id="69313-152">string</span></span> | <span data-ttu-id="69313-153">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="69313-153">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="69313-154">string</span><span class="sxs-lookup"><span data-stu-id="69313-154">string</span></span> | <span data-ttu-id="69313-155">IP-адрес, назначенный локальному устройству, используемому при обмене данными</span><span class="sxs-lookup"><span data-stu-id="69313-155">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="69313-156">string</span><span class="sxs-lookup"><span data-stu-id="69313-156">string</span></span> | <span data-ttu-id="69313-157">Уникальный идентификатор сообщения электронной почты, сформированный в Office 365</span><span class="sxs-lookup"><span data-stu-id="69313-157">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="69313-158">string</span><span class="sxs-lookup"><span data-stu-id="69313-158">string</span></span> | <span data-ttu-id="69313-159">Тема письма</span><span class="sxs-lookup"><span data-stu-id="69313-159">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="69313-160">string</span><span class="sxs-lookup"><span data-stu-id="69313-160">string</span></span> | <span data-ttu-id="69313-161">Уникальный идентификатор приложения</span><span class="sxs-lookup"><span data-stu-id="69313-161">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="69313-162">string</span><span class="sxs-lookup"><span data-stu-id="69313-162">string</span></span> | <span data-ttu-id="69313-163">Приложение, которое выполнило записанное действие</span><span class="sxs-lookup"><span data-stu-id="69313-163">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="69313-164">string</span><span class="sxs-lookup"><span data-stu-id="69313-164">string</span></span> | <span data-ttu-id="69313-165">Командная строка, используемая для создания нового процесса</span><span class="sxs-lookup"><span data-stu-id="69313-165">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="69313-166">string</span><span class="sxs-lookup"><span data-stu-id="69313-166">string</span></span> | <span data-ttu-id="69313-167">Дополнительные сведения о событии в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="69313-167">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="69313-168">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="69313-168">Related topics</span></span>
- [<span data-ttu-id="69313-169">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="69313-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="69313-170">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="69313-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="69313-171">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="69313-171">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="69313-172">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="69313-172">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="69313-173">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="69313-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="69313-174">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="69313-174">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
