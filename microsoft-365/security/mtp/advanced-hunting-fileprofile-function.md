---
title: Функция FileProfile() в advanced hunting for Microsoft 365 Defender
description: Узнайте, как использовать FileProfile() для получения дополнительных сведений о файлах в результатах запроса на расширенный поиск
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, FileProfile, file profile, function, enrichment
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
ms.openlocfilehash: 68196f126ac470088d7ba5e2923accc492d8764c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929554"
---
# <a name="fileprofile"></a><span data-ttu-id="e49cc-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="e49cc-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e49cc-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e49cc-105">**Applies to:**</span></span>
- <span data-ttu-id="e49cc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e49cc-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e49cc-107">Функция является функцией обогащения в расширенных охотах, которая добавляет следующие данные в файлы, `FileProfile()` найденные в [](advanced-hunting-overview.md) запросе.</span><span class="sxs-lookup"><span data-stu-id="e49cc-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="e49cc-108">Столбец</span><span class="sxs-lookup"><span data-stu-id="e49cc-108">Column</span></span> | <span data-ttu-id="e49cc-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="e49cc-109">Data type</span></span> | <span data-ttu-id="e49cc-110">Описание</span><span class="sxs-lookup"><span data-stu-id="e49cc-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="e49cc-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="e49cc-111">SHA1</span></span> | <span data-ttu-id="e49cc-112">string</span><span class="sxs-lookup"><span data-stu-id="e49cc-112">string</span></span> | <span data-ttu-id="e49cc-113">SHA-1 файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="e49cc-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="e49cc-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="e49cc-114">SHA256</span></span> | <span data-ttu-id="e49cc-115">string</span><span class="sxs-lookup"><span data-stu-id="e49cc-115">string</span></span> | <span data-ttu-id="e49cc-116">SHA-256 файла, к который было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="e49cc-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="e49cc-117">MD5</span><span class="sxs-lookup"><span data-stu-id="e49cc-117">MD5</span></span> | <span data-ttu-id="e49cc-118">string</span><span class="sxs-lookup"><span data-stu-id="e49cc-118">string</span></span> | <span data-ttu-id="e49cc-119">Hash MD5 файла, к который было применено записано действие</span><span class="sxs-lookup"><span data-stu-id="e49cc-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="e49cc-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="e49cc-120">FileSize</span></span> | <span data-ttu-id="e49cc-121">int</span><span class="sxs-lookup"><span data-stu-id="e49cc-121">int</span></span> | <span data-ttu-id="e49cc-122">Размер файла в ветвях</span><span class="sxs-lookup"><span data-stu-id="e49cc-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="e49cc-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="e49cc-123">GlobalPrevalence</span></span> | <span data-ttu-id="e49cc-124">int</span><span class="sxs-lookup"><span data-stu-id="e49cc-124">int</span></span> | <span data-ttu-id="e49cc-125">Количество экземпляров сущности, наблюдаемой корпорацией Майкрософт на глобальном уровне</span><span class="sxs-lookup"><span data-stu-id="e49cc-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="e49cc-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="e49cc-126">GlobalFirstSeen</span></span> | <span data-ttu-id="e49cc-127">datetime</span><span class="sxs-lookup"><span data-stu-id="e49cc-127">datetime</span></span> | <span data-ttu-id="e49cc-128">Дата и время первого глобального наблюдения сущности корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e49cc-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="e49cc-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="e49cc-129">GlobalLastSeen</span></span> | <span data-ttu-id="e49cc-130">datetime</span><span class="sxs-lookup"><span data-stu-id="e49cc-130">datetime</span></span> | <span data-ttu-id="e49cc-131">Дата и время последнего наблюдения сущности корпорацией Майкрософт на глобальном уровне</span><span class="sxs-lookup"><span data-stu-id="e49cc-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="e49cc-132">Подписыватель</span><span class="sxs-lookup"><span data-stu-id="e49cc-132">Signer</span></span> | <span data-ttu-id="e49cc-133">string</span><span class="sxs-lookup"><span data-stu-id="e49cc-133">string</span></span> | <span data-ttu-id="e49cc-134">Сведения о подписании файла</span><span class="sxs-lookup"><span data-stu-id="e49cc-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="e49cc-135">Издатель</span><span class="sxs-lookup"><span data-stu-id="e49cc-135">Issuer</span></span> | <span data-ttu-id="e49cc-136">string</span><span class="sxs-lookup"><span data-stu-id="e49cc-136">string</span></span> | <span data-ttu-id="e49cc-137">Сведения о выдавливом ЦС</span><span class="sxs-lookup"><span data-stu-id="e49cc-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="e49cc-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="e49cc-138">SignerHash</span></span> | <span data-ttu-id="e49cc-139">string</span><span class="sxs-lookup"><span data-stu-id="e49cc-139">string</span></span> | <span data-ttu-id="e49cc-140">Уникальное значение hash, определяющие подписывающий</span><span class="sxs-lookup"><span data-stu-id="e49cc-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="e49cc-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="e49cc-141">IsCertificateValid</span></span> | <span data-ttu-id="e49cc-142">boolean</span><span class="sxs-lookup"><span data-stu-id="e49cc-142">boolean</span></span> | <span data-ttu-id="e49cc-143">Является ли сертификат, используемый для подписи файла, допустимым</span><span class="sxs-lookup"><span data-stu-id="e49cc-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="e49cc-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="e49cc-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="e49cc-145">boolean</span><span class="sxs-lookup"><span data-stu-id="e49cc-145">boolean</span></span> | <span data-ttu-id="e49cc-146">Указывает, является ли подписыватель корневого сертификата корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e49cc-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="e49cc-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="e49cc-147">IsExecutable</span></span> | <span data-ttu-id="e49cc-148">boolean</span><span class="sxs-lookup"><span data-stu-id="e49cc-148">boolean</span></span> | <span data-ttu-id="e49cc-149">Является ли файл переносимым исполняемым файлом (PE)</span><span class="sxs-lookup"><span data-stu-id="e49cc-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="e49cc-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="e49cc-150">ThreatName</span></span> | <span data-ttu-id="e49cc-151">string</span><span class="sxs-lookup"><span data-stu-id="e49cc-151">string</span></span> | <span data-ttu-id="e49cc-152">Имя обнаружения вредоносных программ или других найденных угроз</span><span class="sxs-lookup"><span data-stu-id="e49cc-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="e49cc-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="e49cc-153">Publisher</span></span> | <span data-ttu-id="e49cc-154">string</span><span class="sxs-lookup"><span data-stu-id="e49cc-154">string</span></span> | <span data-ttu-id="e49cc-155">Название организации, которая опубликовала файл</span><span class="sxs-lookup"><span data-stu-id="e49cc-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="e49cc-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="e49cc-156">SoftwareName</span></span> | <span data-ttu-id="e49cc-157">string</span><span class="sxs-lookup"><span data-stu-id="e49cc-157">string</span></span> | <span data-ttu-id="e49cc-158">Название программного продукта</span><span class="sxs-lookup"><span data-stu-id="e49cc-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="e49cc-159">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e49cc-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="e49cc-160">Аргументы</span><span class="sxs-lookup"><span data-stu-id="e49cc-160">Arguments</span></span>

- <span data-ttu-id="e49cc-161">**x**— столбец ИД файла для использования: , , или ; функция `SHA1` `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` использует, если не засекречены</span><span class="sxs-lookup"><span data-stu-id="e49cc-161">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="e49cc-162">**y**— ограничение на количество записей для обогащения, 1–1000; функция использует 100, если не закален</span><span class="sxs-lookup"><span data-stu-id="e49cc-162">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="e49cc-163">Примеры</span><span class="sxs-lookup"><span data-stu-id="e49cc-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="e49cc-164">Проецируемый только столбец SHA1 и его обогащение</span><span class="sxs-lookup"><span data-stu-id="e49cc-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="e49cc-165">Обогащение первых 500 записей и списков файлов с низким уровнем преобладаний</span><span class="sxs-lookup"><span data-stu-id="e49cc-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="e49cc-166">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e49cc-166">Related topics</span></span>
- [<span data-ttu-id="e49cc-167">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="e49cc-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e49cc-168">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="e49cc-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e49cc-169">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="e49cc-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e49cc-170">Получить дополнительные примеры запросов</span><span class="sxs-lookup"><span data-stu-id="e49cc-170">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
