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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: a7e2eca147bb956606380b9ac97a91b898830dd0
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197273"
---
# <a name="alertevidence"></a><span data-ttu-id="ddffc-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="ddffc-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ddffc-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ddffc-105">**Applies to:**</span></span>
- <span data-ttu-id="ddffc-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="ddffc-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="ddffc-107">`AlertEvidence`Таблица в схеме [расширенного](advanced-hunting-overview.md) поискового заданных содержит сведения о различных сущностях — файлах, IP-адресах, URL-адресах, пользователях или устройствах, связанных с оповещениями из пакета ATP (Майкрософт) atp, Office 365 ATP, Microsoft Cloud App Security и Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="ddffc-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="ddffc-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="ddffc-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="ddffc-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="ddffc-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ddffc-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="ddffc-110">Column name</span></span> | <span data-ttu-id="ddffc-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="ddffc-111">Data type</span></span> | <span data-ttu-id="ddffc-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ddffc-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="ddffc-113">datetime</span><span class="sxs-lookup"><span data-stu-id="ddffc-113">datetime</span></span> | <span data-ttu-id="ddffc-114">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="ddffc-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="ddffc-115">string</span><span class="sxs-lookup"><span data-stu-id="ddffc-115">string</span></span> | <span data-ttu-id="ddffc-116">Уникальный идентификатор оповещения</span><span class="sxs-lookup"><span data-stu-id="ddffc-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="ddffc-117">string</span><span class="sxs-lookup"><span data-stu-id="ddffc-117">string</span></span> | <span data-ttu-id="ddffc-118">Продукт или услуга, которые предоставили информацию оповещений</span><span class="sxs-lookup"><span data-stu-id="ddffc-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="ddffc-119">string</span><span class="sxs-lookup"><span data-stu-id="ddffc-119">string</span></span> | <span data-ttu-id="ddffc-120">Тип объекта, например файл, процесс, устройство или пользователь</span><span class="sxs-lookup"><span data-stu-id="ddffc-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="ddffc-121">string</span><span class="sxs-lookup"><span data-stu-id="ddffc-121">string</span></span> | <span data-ttu-id="ddffc-122">Способ участия объекта в оповещении, указывающий на то, что он повлиял или является просто связанным</span><span class="sxs-lookup"><span data-stu-id="ddffc-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="ddffc-123">string</span><span class="sxs-lookup"><span data-stu-id="ddffc-123">string</span></span> | <span data-ttu-id="ddffc-124">Указывает, является ли объект источником или местом назначения сетевого подключения.</span><span class="sxs-lookup"><span data-stu-id="ddffc-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="ddffc-125">string</span><span class="sxs-lookup"><span data-stu-id="ddffc-125">string</span></span> | <span data-ttu-id="ddffc-126">Имя файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="ddffc-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="ddffc-127">string</span><span class="sxs-lookup"><span data-stu-id="ddffc-127">string</span></span> | <span data-ttu-id="ddffc-128">Папка, содержащая файл, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="ddffc-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="ddffc-129">string</span><span class="sxs-lookup"><span data-stu-id="ddffc-129">string</span></span> | <span data-ttu-id="ddffc-130">SHA-1 файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="ddffc-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="ddffc-131">string</span><span class="sxs-lookup"><span data-stu-id="ddffc-131">string</span></span> | <span data-ttu-id="ddffc-132">SHA-256 файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="ddffc-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="ddffc-133">Это поле обычно не заполняется — используйте столбец SHA1, если он доступен.</span><span class="sxs-lookup"><span data-stu-id="ddffc-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="ddffc-134">int</span><span class="sxs-lookup"><span data-stu-id="ddffc-134">int</span></span> | <span data-ttu-id="ddffc-135">Размер файла в байтах</span><span class="sxs-lookup"><span data-stu-id="ddffc-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="ddffc-136">string</span><span class="sxs-lookup"><span data-stu-id="ddffc-136">string</span></span> | <span data-ttu-id="ddffc-137">Семейство вредоносных программ, которые были классифицированы подозрительным или вредоносным файлом или процессом</span><span class="sxs-lookup"><span data-stu-id="ddffc-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="ddffc-138">string</span><span class="sxs-lookup"><span data-stu-id="ddffc-138">string</span></span> | <span data-ttu-id="ddffc-139">IP-адрес, к которому выполнено подключение</span><span class="sxs-lookup"><span data-stu-id="ddffc-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="ddffc-140">string</span><span class="sxs-lookup"><span data-stu-id="ddffc-140">string</span></span> | <span data-ttu-id="ddffc-141">URL-адрес или полное доменное имя, к которому выполнено подключение</span><span class="sxs-lookup"><span data-stu-id="ddffc-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="ddffc-142">string</span><span class="sxs-lookup"><span data-stu-id="ddffc-142">string</span></span> | <span data-ttu-id="ddffc-143">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="ddffc-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="ddffc-144">string</span><span class="sxs-lookup"><span data-stu-id="ddffc-144">string</span></span> | <span data-ttu-id="ddffc-145">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="ddffc-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="ddffc-146">string</span><span class="sxs-lookup"><span data-stu-id="ddffc-146">string</span></span> | <span data-ttu-id="ddffc-147">Идентификатор безопасности (SID) учетной записи</span><span class="sxs-lookup"><span data-stu-id="ddffc-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="ddffc-148">string</span><span class="sxs-lookup"><span data-stu-id="ddffc-148">string</span></span> | <span data-ttu-id="ddffc-149">Уникальный идентификатор учетной записи в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ddffc-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `DeviceId` | <span data-ttu-id="ddffc-150">string</span><span class="sxs-lookup"><span data-stu-id="ddffc-150">string</span></span> | <span data-ttu-id="ddffc-151">Уникальный идентификатор устройства в службе</span><span class="sxs-lookup"><span data-stu-id="ddffc-151">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="ddffc-152">string</span><span class="sxs-lookup"><span data-stu-id="ddffc-152">string</span></span> | <span data-ttu-id="ddffc-153">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="ddffc-153">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="ddffc-154">string</span><span class="sxs-lookup"><span data-stu-id="ddffc-154">string</span></span> | <span data-ttu-id="ddffc-155">IP-адрес, назначенный локальному устройству, используемому при обмене данными</span><span class="sxs-lookup"><span data-stu-id="ddffc-155">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="ddffc-156">string</span><span class="sxs-lookup"><span data-stu-id="ddffc-156">string</span></span> | <span data-ttu-id="ddffc-157">Уникальный идентификатор сообщения электронной почты, сформированный в Office 365</span><span class="sxs-lookup"><span data-stu-id="ddffc-157">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="ddffc-158">string</span><span class="sxs-lookup"><span data-stu-id="ddffc-158">string</span></span> | <span data-ttu-id="ddffc-159">Тема письма</span><span class="sxs-lookup"><span data-stu-id="ddffc-159">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="ddffc-160">string</span><span class="sxs-lookup"><span data-stu-id="ddffc-160">string</span></span> | <span data-ttu-id="ddffc-161">Уникальный идентификатор приложения</span><span class="sxs-lookup"><span data-stu-id="ddffc-161">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="ddffc-162">string</span><span class="sxs-lookup"><span data-stu-id="ddffc-162">string</span></span> | <span data-ttu-id="ddffc-163">Приложение, которое выполнило записанное действие</span><span class="sxs-lookup"><span data-stu-id="ddffc-163">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="ddffc-164">string</span><span class="sxs-lookup"><span data-stu-id="ddffc-164">string</span></span> | <span data-ttu-id="ddffc-165">Командная строка, используемая для создания нового процесса</span><span class="sxs-lookup"><span data-stu-id="ddffc-165">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="ddffc-166">string</span><span class="sxs-lookup"><span data-stu-id="ddffc-166">string</span></span> | <span data-ttu-id="ddffc-167">Дополнительные сведения о событии в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="ddffc-167">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="ddffc-168">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="ddffc-168">Related topics</span></span>
- [<span data-ttu-id="ddffc-169">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="ddffc-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ddffc-170">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="ddffc-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ddffc-171">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="ddffc-171">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ddffc-172">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="ddffc-172">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ddffc-173">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="ddffc-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ddffc-174">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="ddffc-174">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
