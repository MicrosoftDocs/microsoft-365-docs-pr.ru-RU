---
title: Функция Филепрофиле () в расширенном поиске для защиты от угроз Майкрософт
description: Узнайте, как использовать Филепрофиле (), чтобы получить сведения о файлах в расширенных запросах поиска.
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справочник по схемам, Кусто, Филепрофиле, профиле файла, функция, обогащение
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
ms.openlocfilehash: 6d627dcf3d6ec8ca1d2aa76eab484361c25b529e
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338421"
---
# <a name="fileprofile"></a><span data-ttu-id="155d7-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="155d7-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="155d7-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="155d7-105">**Applies to:**</span></span>
- <span data-ttu-id="155d7-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="155d7-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="155d7-107">`FileProfile()`Функция — это функция обогащения в [расширенном поиске](advanced-hunting-overview.md) , которая добавляет следующие данные в файлы, найденные в запросе.</span><span class="sxs-lookup"><span data-stu-id="155d7-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="155d7-108">Столбец</span><span class="sxs-lookup"><span data-stu-id="155d7-108">Column</span></span> | <span data-ttu-id="155d7-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="155d7-109">Data type</span></span> | <span data-ttu-id="155d7-110">Описание</span><span class="sxs-lookup"><span data-stu-id="155d7-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="155d7-111">ХЭШЕМ</span><span class="sxs-lookup"><span data-stu-id="155d7-111">SHA1</span></span> | <span data-ttu-id="155d7-112">string</span><span class="sxs-lookup"><span data-stu-id="155d7-112">string</span></span> | <span data-ttu-id="155d7-113">SHA-1 файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="155d7-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="155d7-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="155d7-114">SHA256</span></span> | <span data-ttu-id="155d7-115">string</span><span class="sxs-lookup"><span data-stu-id="155d7-115">string</span></span> | <span data-ttu-id="155d7-116">SHA – 256 файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="155d7-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="155d7-117">MD5</span><span class="sxs-lookup"><span data-stu-id="155d7-117">MD5</span></span> | <span data-ttu-id="155d7-118">string</span><span class="sxs-lookup"><span data-stu-id="155d7-118">string</span></span> | <span data-ttu-id="155d7-119">Хэш MD5 файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="155d7-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="155d7-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="155d7-120">FileSize</span></span> | <span data-ttu-id="155d7-121">int</span><span class="sxs-lookup"><span data-stu-id="155d7-121">int</span></span> | <span data-ttu-id="155d7-122">Размер файла в байтах</span><span class="sxs-lookup"><span data-stu-id="155d7-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="155d7-123">глобалпреваленце</span><span class="sxs-lookup"><span data-stu-id="155d7-123">GlobalPrevalence</span></span> | <span data-ttu-id="155d7-124">int</span><span class="sxs-lookup"><span data-stu-id="155d7-124">int</span></span> | <span data-ttu-id="155d7-125">Количество экземпляров сущности, которые корпорация Майкрософт соблюдает глобально</span><span class="sxs-lookup"><span data-stu-id="155d7-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="155d7-126">глобалфирстсин</span><span class="sxs-lookup"><span data-stu-id="155d7-126">GlobalFirstSeen</span></span> | <span data-ttu-id="155d7-127">datetime</span><span class="sxs-lookup"><span data-stu-id="155d7-127">datetime</span></span> | <span data-ttu-id="155d7-128">Дата и время, когда объект впервые наблюдался корпорацией Майкрософт глобально</span><span class="sxs-lookup"><span data-stu-id="155d7-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="155d7-129">глобалластсин</span><span class="sxs-lookup"><span data-stu-id="155d7-129">GlobalLastSeen</span></span> | <span data-ttu-id="155d7-130">datetime</span><span class="sxs-lookup"><span data-stu-id="155d7-130">datetime</span></span> | <span data-ttu-id="155d7-131">Дата и время последней первоначальной отстановки объекта корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="155d7-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="155d7-132">Подписывающего лица</span><span class="sxs-lookup"><span data-stu-id="155d7-132">Signer</span></span> | <span data-ttu-id="155d7-133">string</span><span class="sxs-lookup"><span data-stu-id="155d7-133">string</span></span> | <span data-ttu-id="155d7-134">Сведения о подписавшем файла</span><span class="sxs-lookup"><span data-stu-id="155d7-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="155d7-135">Издатель</span><span class="sxs-lookup"><span data-stu-id="155d7-135">Issuer</span></span> | <span data-ttu-id="155d7-136">string</span><span class="sxs-lookup"><span data-stu-id="155d7-136">string</span></span> | <span data-ttu-id="155d7-137">Сведения о выдающем центре сертификации (ЦС)</span><span class="sxs-lookup"><span data-stu-id="155d7-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="155d7-138">сигнерхаш</span><span class="sxs-lookup"><span data-stu-id="155d7-138">SignerHash</span></span> | <span data-ttu-id="155d7-139">string</span><span class="sxs-lookup"><span data-stu-id="155d7-139">string</span></span> | <span data-ttu-id="155d7-140">Уникальное значение хэша, идентифицирующее подписывающий</span><span class="sxs-lookup"><span data-stu-id="155d7-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="155d7-141">исцертификатевалид</span><span class="sxs-lookup"><span data-stu-id="155d7-141">IsCertificateValid</span></span> | <span data-ttu-id="155d7-142">boolean</span><span class="sxs-lookup"><span data-stu-id="155d7-142">boolean</span></span> | <span data-ttu-id="155d7-143">Является ли сертификат, используемый для подписи файла, допустимым</span><span class="sxs-lookup"><span data-stu-id="155d7-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="155d7-144">исрутсигнермикрософт</span><span class="sxs-lookup"><span data-stu-id="155d7-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="155d7-145">boolean</span><span class="sxs-lookup"><span data-stu-id="155d7-145">boolean</span></span> | <span data-ttu-id="155d7-146">Указывает, является ли подписывающий корневой сертификат корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="155d7-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="155d7-147">Исполняемый файл</span><span class="sxs-lookup"><span data-stu-id="155d7-147">IsExecutable</span></span> | <span data-ttu-id="155d7-148">boolean</span><span class="sxs-lookup"><span data-stu-id="155d7-148">boolean</span></span> | <span data-ttu-id="155d7-149">Является ли файл переносимым исполняемым файлом (PE)</span><span class="sxs-lookup"><span data-stu-id="155d7-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="155d7-150">среатнаме</span><span class="sxs-lookup"><span data-stu-id="155d7-150">ThreatName</span></span> | <span data-ttu-id="155d7-151">string</span><span class="sxs-lookup"><span data-stu-id="155d7-151">string</span></span> | <span data-ttu-id="155d7-152">Имя для обнаружения вредоносных программ или других обнаруженных угроз</span><span class="sxs-lookup"><span data-stu-id="155d7-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="155d7-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="155d7-153">Publisher</span></span> | <span data-ttu-id="155d7-154">string</span><span class="sxs-lookup"><span data-stu-id="155d7-154">string</span></span> | <span data-ttu-id="155d7-155">Имя Организации, опубликовавшего файл</span><span class="sxs-lookup"><span data-stu-id="155d7-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="155d7-156">софтваренаме</span><span class="sxs-lookup"><span data-stu-id="155d7-156">SoftwareName</span></span> | <span data-ttu-id="155d7-157">string</span><span class="sxs-lookup"><span data-stu-id="155d7-157">string</span></span> | <span data-ttu-id="155d7-158">Название программного продукта</span><span class="sxs-lookup"><span data-stu-id="155d7-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="155d7-159">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="155d7-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="155d7-160">Аргументы</span><span class="sxs-lookup"><span data-stu-id="155d7-160">Arguments</span></span>

- <span data-ttu-id="155d7-161">**x**— столбец идентификатора файла, который будет использоваться: `SHA1` , `SHA256` , `InitiatingProcessSHA1` , или `InitiatingProcessSHA256` ; использует функцию, если она не `SHA1` указана</span><span class="sxs-lookup"><span data-stu-id="155d7-161">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="155d7-162">**y**— ограничено числом записей до обогащения, 1-1000; функция использует 100, если она не указана</span><span class="sxs-lookup"><span data-stu-id="155d7-162">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="155d7-163">Примеры</span><span class="sxs-lookup"><span data-stu-id="155d7-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="155d7-164">Project только для столбца SHA1 и обогащения</span><span class="sxs-lookup"><span data-stu-id="155d7-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="155d7-165">Улучшение первых 500 записей и списков файлов с минимальным дообладанием</span><span class="sxs-lookup"><span data-stu-id="155d7-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="155d7-166">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="155d7-166">Related topics</span></span>
- [<span data-ttu-id="155d7-167">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="155d7-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="155d7-168">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="155d7-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="155d7-169">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="155d7-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="155d7-170">Получение дополнительных примеров запросов</span><span class="sxs-lookup"><span data-stu-id="155d7-170">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
