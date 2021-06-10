---
title: Таблица AlertEvidence в продвинутой схеме охоты
description: Сведения о сведениях, связанных с оповещениями в таблице AlertEvidence в продвинутой схеме охоты
keywords: передовая охота, охота на угрозы, охота на киберугрозы, Microsoft 365 Defender, Microsoft 365, m365, поиск, запрос, телеметрия, ссылка схемы, кусто, таблица, столбец, тип данных, описание, AlertInfo, оповещения, сущности, доказательства, файл, IP-адрес, устройство, машина, пользователь, учетная запись
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 5ecab217a6181096e4689d78fa2bdddc0a767d0d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932587"
---
# <a name="alertevidence"></a><span data-ttu-id="ddd0a-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="ddd0a-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ddd0a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ddd0a-105">**Applies to:**</span></span>
- <span data-ttu-id="ddd0a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ddd0a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ddd0a-107">Таблица в продвинутой схеме охоты содержит сведения о различных сущностями— `AlertEvidence` файлах, IP-адресах, URL-адресах, пользователях или устройствах, связанных с оповещениями из Microsoft Defender for [](advanced-hunting-overview.md) Endpoint, Microsoft Defender для Office 365, Microsoft Cloud App Security и Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="ddd0a-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="ddd0a-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="ddd0a-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="ddd0a-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="ddd0a-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ddd0a-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="ddd0a-110">Column name</span></span> | <span data-ttu-id="ddd0a-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="ddd0a-111">Data type</span></span> | <span data-ttu-id="ddd0a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ddd0a-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="ddd0a-113">datetime</span><span class="sxs-lookup"><span data-stu-id="ddd0a-113">datetime</span></span> | <span data-ttu-id="ddd0a-114">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="ddd0a-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="ddd0a-115">string</span><span class="sxs-lookup"><span data-stu-id="ddd0a-115">string</span></span> | <span data-ttu-id="ddd0a-116">Уникальный идентификатор оповещения</span><span class="sxs-lookup"><span data-stu-id="ddd0a-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="ddd0a-117">Строка</span><span class="sxs-lookup"><span data-stu-id="ddd0a-117">string</span></span> | <span data-ttu-id="ddd0a-118">Продукт или служба, которые предоставили сведения об оповещении</span><span class="sxs-lookup"><span data-stu-id="ddd0a-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="ddd0a-119">Строка</span><span class="sxs-lookup"><span data-stu-id="ddd0a-119">string</span></span> | <span data-ttu-id="ddd0a-120">Тип объекта, например файл, процесс, устройство или пользователь</span><span class="sxs-lookup"><span data-stu-id="ddd0a-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="ddd0a-121">Строка</span><span class="sxs-lookup"><span data-stu-id="ddd0a-121">string</span></span> | <span data-ttu-id="ddd0a-122">Участие объекта в оповещении, указывающее, влияет ли оно на него или связано только с ним</span><span class="sxs-lookup"><span data-stu-id="ddd0a-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="ddd0a-123">Строка</span><span class="sxs-lookup"><span data-stu-id="ddd0a-123">string</span></span> | <span data-ttu-id="ddd0a-124">Указывает, является ли объект источником или предназначением сетевого подключения</span><span class="sxs-lookup"><span data-stu-id="ddd0a-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="ddd0a-125">string</span><span class="sxs-lookup"><span data-stu-id="ddd0a-125">string</span></span> | <span data-ttu-id="ddd0a-126">Имя файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="ddd0a-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="ddd0a-127">string</span><span class="sxs-lookup"><span data-stu-id="ddd0a-127">string</span></span> | <span data-ttu-id="ddd0a-128">Папка, содержащая файл, к котором было применено записано действие</span><span class="sxs-lookup"><span data-stu-id="ddd0a-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="ddd0a-129">string</span><span class="sxs-lookup"><span data-stu-id="ddd0a-129">string</span></span> | <span data-ttu-id="ddd0a-130">SHA-1 файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="ddd0a-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="ddd0a-131">string</span><span class="sxs-lookup"><span data-stu-id="ddd0a-131">string</span></span> | <span data-ttu-id="ddd0a-132">SHA-256 файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="ddd0a-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="ddd0a-133">Это поле обычно не заполнено— используйте столбец SHA1 при наличии.</span><span class="sxs-lookup"><span data-stu-id="ddd0a-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="ddd0a-134">int</span><span class="sxs-lookup"><span data-stu-id="ddd0a-134">int</span></span> | <span data-ttu-id="ddd0a-135">Размер файла в bytes</span><span class="sxs-lookup"><span data-stu-id="ddd0a-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="ddd0a-136">Строка</span><span class="sxs-lookup"><span data-stu-id="ddd0a-136">string</span></span> | <span data-ttu-id="ddd0a-137">Семейство вредоносных программ, засекреченное под подозрительным или вредоносным файлом или процессом</span><span class="sxs-lookup"><span data-stu-id="ddd0a-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="ddd0a-138">string</span><span class="sxs-lookup"><span data-stu-id="ddd0a-138">string</span></span> | <span data-ttu-id="ddd0a-139">IP-адрес, к которому выполнено подключение</span><span class="sxs-lookup"><span data-stu-id="ddd0a-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="ddd0a-140">string</span><span class="sxs-lookup"><span data-stu-id="ddd0a-140">string</span></span> | <span data-ttu-id="ddd0a-141">URL-адрес или полное доменное имя, к которому выполнено подключение</span><span class="sxs-lookup"><span data-stu-id="ddd0a-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="ddd0a-142">string</span><span class="sxs-lookup"><span data-stu-id="ddd0a-142">string</span></span> | <span data-ttu-id="ddd0a-143">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="ddd0a-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="ddd0a-144">Строка</span><span class="sxs-lookup"><span data-stu-id="ddd0a-144">string</span></span> | <span data-ttu-id="ddd0a-145">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="ddd0a-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="ddd0a-146">Строка</span><span class="sxs-lookup"><span data-stu-id="ddd0a-146">string</span></span> | <span data-ttu-id="ddd0a-147">Идентификатор безопасности (SID) учетной записи</span><span class="sxs-lookup"><span data-stu-id="ddd0a-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="ddd0a-148">Строка</span><span class="sxs-lookup"><span data-stu-id="ddd0a-148">string</span></span> | <span data-ttu-id="ddd0a-149">Уникальный идентификатор учетной записи в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ddd0a-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountUpn` | <span data-ttu-id="ddd0a-150">Строка</span><span class="sxs-lookup"><span data-stu-id="ddd0a-150">string</span></span> | <span data-ttu-id="ddd0a-151">Основное имя пользователя (UPN) учетной записи</span><span class="sxs-lookup"><span data-stu-id="ddd0a-151">User principal name (UPN) of the account</span></span> |
| `DeviceId` | <span data-ttu-id="ddd0a-152">Строка</span><span class="sxs-lookup"><span data-stu-id="ddd0a-152">string</span></span> | <span data-ttu-id="ddd0a-153">Уникальный идентификатор устройства в службе</span><span class="sxs-lookup"><span data-stu-id="ddd0a-153">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="ddd0a-154">string</span><span class="sxs-lookup"><span data-stu-id="ddd0a-154">string</span></span> | <span data-ttu-id="ddd0a-155">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="ddd0a-155">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="ddd0a-156">string</span><span class="sxs-lookup"><span data-stu-id="ddd0a-156">string</span></span> | <span data-ttu-id="ddd0a-157">IP-адрес, присвоенный локальному устройству, используемму во время связи</span><span class="sxs-lookup"><span data-stu-id="ddd0a-157">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="ddd0a-158">string</span><span class="sxs-lookup"><span data-stu-id="ddd0a-158">string</span></span> | <span data-ttu-id="ddd0a-159">Уникальный идентификатор сообщения электронной почты, сформированный в Office 365</span><span class="sxs-lookup"><span data-stu-id="ddd0a-159">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="ddd0a-160">string</span><span class="sxs-lookup"><span data-stu-id="ddd0a-160">string</span></span> | <span data-ttu-id="ddd0a-161">Тема письма</span><span class="sxs-lookup"><span data-stu-id="ddd0a-161">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="ddd0a-162">string</span><span class="sxs-lookup"><span data-stu-id="ddd0a-162">string</span></span> | <span data-ttu-id="ddd0a-163">Уникальный идентификатор для приложения</span><span class="sxs-lookup"><span data-stu-id="ddd0a-163">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="ddd0a-164">Строка</span><span class="sxs-lookup"><span data-stu-id="ddd0a-164">string</span></span> | <span data-ttu-id="ddd0a-165">Приложение, которое выполнило записанную акцию</span><span class="sxs-lookup"><span data-stu-id="ddd0a-165">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="ddd0a-166">Строка</span><span class="sxs-lookup"><span data-stu-id="ddd0a-166">string</span></span> | <span data-ttu-id="ddd0a-167">Командная строка, используемая для создания нового процесса</span><span class="sxs-lookup"><span data-stu-id="ddd0a-167">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="ddd0a-168">Строка</span><span class="sxs-lookup"><span data-stu-id="ddd0a-168">string</span></span> | <span data-ttu-id="ddd0a-169">Дополнительные сведения о событии в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="ddd0a-169">Additional information about the event in JSON array format</span></span> |
| `RegistryKey` |<span data-ttu-id="ddd0a-170">Строка</span><span class="sxs-lookup"><span data-stu-id="ddd0a-170">string</span></span> | <span data-ttu-id="ddd0a-171">Ключ реестра, к который было применено записано действие</span><span class="sxs-lookup"><span data-stu-id="ddd0a-171">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueName` |<span data-ttu-id="ddd0a-172">Строка</span><span class="sxs-lookup"><span data-stu-id="ddd0a-172">string</span></span> | <span data-ttu-id="ddd0a-173">Имя значения реестра, к которое было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="ddd0a-173">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` |<span data-ttu-id="ddd0a-174">Строка</span><span class="sxs-lookup"><span data-stu-id="ddd0a-174">string</span></span> | <span data-ttu-id="ddd0a-175">Данные о значении реестра, которое было применено к зарегистрированным действиям</span><span class="sxs-lookup"><span data-stu-id="ddd0a-175">Data of the registry value that the recorded action was applied to</span></span> |

## <a name="related-topics"></a><span data-ttu-id="ddd0a-176">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ddd0a-176">Related topics</span></span>
- [<span data-ttu-id="ddd0a-177">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="ddd0a-177">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ddd0a-178">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="ddd0a-178">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ddd0a-179">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="ddd0a-179">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ddd0a-180">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="ddd0a-180">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ddd0a-181">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="ddd0a-181">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ddd0a-182">Применение рекомендаций по использованию запросов</span><span class="sxs-lookup"><span data-stu-id="ddd0a-182">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
