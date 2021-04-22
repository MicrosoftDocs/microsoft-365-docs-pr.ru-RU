---
title: Функция FileProfile() в продвинутой охоте для Microsoft 365 Defender
description: Узнайте, как использовать FileProfile() для обогащения сведений о файлах в результатах запроса на расширенные запросы на охоту
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, Microsoft 365, m365, search, query, telemetry, schema reference, kusto, FileProfile, file Profile, function, enrichment
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
ms.openlocfilehash: 67295529cdb7b8a3e93e663f2a8a28d27a8f6737
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935849"
---
# <a name="fileprofile"></a><span data-ttu-id="bba4b-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="bba4b-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bba4b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="bba4b-105">**Applies to:**</span></span>
- <span data-ttu-id="bba4b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bba4b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="bba4b-107">Функция является функцией обогащения в продвинутой охоте, которая добавляет следующие данные в `FileProfile()` файлы, найденные в [](advanced-hunting-overview.md) запросе.</span><span class="sxs-lookup"><span data-stu-id="bba4b-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="bba4b-108">Column</span><span class="sxs-lookup"><span data-stu-id="bba4b-108">Column</span></span> | <span data-ttu-id="bba4b-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="bba4b-109">Data type</span></span> | <span data-ttu-id="bba4b-110">Описание</span><span class="sxs-lookup"><span data-stu-id="bba4b-110">Description</span></span> |
|------------|---------------|-------------|
| `SHA1` | <span data-ttu-id="bba4b-111">string</span><span class="sxs-lookup"><span data-stu-id="bba4b-111">string</span></span> | <span data-ttu-id="bba4b-112">SHA-1 файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="bba4b-112">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="bba4b-113">string</span><span class="sxs-lookup"><span data-stu-id="bba4b-113">string</span></span> | <span data-ttu-id="bba4b-114">SHA-256 файла, к который было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="bba4b-114">SHA-256 of the file that the recorded action was applied to</span></span> |
| `MD5` | <span data-ttu-id="bba4b-115">Строка</span><span class="sxs-lookup"><span data-stu-id="bba4b-115">string</span></span> | <span data-ttu-id="bba4b-116">Hash MD5 файла, к который было применено записано действие</span><span class="sxs-lookup"><span data-stu-id="bba4b-116">MD5 hash of the file that the recorded action was applied to</span></span> |
| `FileSize` | <span data-ttu-id="bba4b-117">int</span><span class="sxs-lookup"><span data-stu-id="bba4b-117">int</span></span> | <span data-ttu-id="bba4b-118">Размер файла в bytes</span><span class="sxs-lookup"><span data-stu-id="bba4b-118">Size of the file in bytes</span></span> |
| `GlobalPrevalence` | <span data-ttu-id="bba4b-119">int</span><span class="sxs-lookup"><span data-stu-id="bba4b-119">int</span></span> | <span data-ttu-id="bba4b-120">Количество экземпляров объекта, наблюдаемого Корпорацией Майкрософт во всем мире</span><span class="sxs-lookup"><span data-stu-id="bba4b-120">Number of instances of the entity observed by Microsoft globally</span></span> |
| `GlobalFirstSeen` | <span data-ttu-id="bba4b-121">datetime</span><span class="sxs-lookup"><span data-stu-id="bba4b-121">datetime</span></span> | <span data-ttu-id="bba4b-122">Дата и время, когда сущность впервые была замечена Корпорацией Майкрософт во всем мире</span><span class="sxs-lookup"><span data-stu-id="bba4b-122">Date and time when the entity was first observed by Microsoft globally</span></span> |
| `GlobalLastSeen` | <span data-ttu-id="bba4b-123">datetime</span><span class="sxs-lookup"><span data-stu-id="bba4b-123">datetime</span></span> | <span data-ttu-id="bba4b-124">Дата и время, когда объект в последний раз наблюдался Корпорацией Майкрософт во всем мире</span><span class="sxs-lookup"><span data-stu-id="bba4b-124">Date and time when the entity was last observed by Microsoft globally</span></span> |
| `Signer` | <span data-ttu-id="bba4b-125">Строка</span><span class="sxs-lookup"><span data-stu-id="bba4b-125">string</span></span> | <span data-ttu-id="bba4b-126">Сведения о подписывщике файла</span><span class="sxs-lookup"><span data-stu-id="bba4b-126">Information about the signer of the file</span></span> |
| `Issuer` | <span data-ttu-id="bba4b-127">Строка</span><span class="sxs-lookup"><span data-stu-id="bba4b-127">string</span></span> | <span data-ttu-id="bba4b-128">Сведения о полномочиях по выдаче сертификатов (CA)</span><span class="sxs-lookup"><span data-stu-id="bba4b-128">Information about the issuing certificate authority (CA)</span></span> |
| `SignerHash` | <span data-ttu-id="bba4b-129">Строка</span><span class="sxs-lookup"><span data-stu-id="bba4b-129">string</span></span> | <span data-ttu-id="bba4b-130">Уникальное значение hash, определяющие подписавщика</span><span class="sxs-lookup"><span data-stu-id="bba4b-130">Unique hash value identifying the signer</span></span> |
| `IsCertificateValid` | <span data-ttu-id="bba4b-131">boolean</span><span class="sxs-lookup"><span data-stu-id="bba4b-131">boolean</span></span> | <span data-ttu-id="bba4b-132">Допустим ли сертификат, используемый для подписи файла</span><span class="sxs-lookup"><span data-stu-id="bba4b-132">Whether the certificate used to sign the file is valid</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="bba4b-133">boolean</span><span class="sxs-lookup"><span data-stu-id="bba4b-133">boolean</span></span> | <span data-ttu-id="bba4b-134">Указывает, является ли подписатель корневого сертификата Корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="bba4b-134">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `SignatureState` | <span data-ttu-id="bba4b-135">Строка</span><span class="sxs-lookup"><span data-stu-id="bba4b-135">string</span></span> | <span data-ttu-id="bba4b-136">Состояние подписи файла: SignedValid — файл подписывался с действительной подписью, SignedInvalid — файл подписывался, но сертификат недействителен, Неподписанное — файл не подписан, Неизвестный — сведения о файле не могут быть извлечены.</span><span class="sxs-lookup"><span data-stu-id="bba4b-136">State of the file signature: SignedValid - the file is signed with a valid signature, SignedInvalid - the file is signed but the certificate is invalid, Unsigned - the file is not signed, Unknown - information about the file cannot be retrieved</span></span>
| `IsExecutable` | <span data-ttu-id="bba4b-137">boolean</span><span class="sxs-lookup"><span data-stu-id="bba4b-137">boolean</span></span> | <span data-ttu-id="bba4b-138">Является ли файл портативным исполняемым (PE) файлом</span><span class="sxs-lookup"><span data-stu-id="bba4b-138">Whether the file is a Portable Executable (PE) file</span></span> |
| `ThreatName` | <span data-ttu-id="bba4b-139">Строка</span><span class="sxs-lookup"><span data-stu-id="bba4b-139">string</span></span> | <span data-ttu-id="bba4b-140">Имя обнаружения любых найденных вредоносных программ или других угроз</span><span class="sxs-lookup"><span data-stu-id="bba4b-140">Detection name for any malware or other threats found</span></span> |
| `Publisher` | <span data-ttu-id="bba4b-141">Строка</span><span class="sxs-lookup"><span data-stu-id="bba4b-141">string</span></span> | <span data-ttu-id="bba4b-142">Имя организации, которая опубликовала файл</span><span class="sxs-lookup"><span data-stu-id="bba4b-142">Name of the organization that published the file</span></span> |
| `SoftwareName` | <span data-ttu-id="bba4b-143">string</span><span class="sxs-lookup"><span data-stu-id="bba4b-143">string</span></span> | <span data-ttu-id="bba4b-144">Название программного продукта</span><span class="sxs-lookup"><span data-stu-id="bba4b-144">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="bba4b-145">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bba4b-145">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="bba4b-146">Аргументы</span><span class="sxs-lookup"><span data-stu-id="bba4b-146">Arguments</span></span>

- <span data-ttu-id="bba4b-147">**x**— столбец ID файла для использования: , , , или ; использование `SHA1` `SHA256` функции, если `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` неустановлено</span><span class="sxs-lookup"><span data-stu-id="bba4b-147">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="bba4b-148">**y**— ограничение количества записей для обогащения, 1-1000; функция использует 100, если неустановлено</span><span class="sxs-lookup"><span data-stu-id="bba4b-148">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>


>[!TIP]
> <span data-ttu-id="bba4b-149">Функции обогащения будут показывать дополнительные сведения только в том случае, если они доступны.</span><span class="sxs-lookup"><span data-stu-id="bba4b-149">Enrichment functions will show supplemental information only when they are available.</span></span> <span data-ttu-id="bba4b-150">Доступность информации разнообразна и зависит от многих факторов.</span><span class="sxs-lookup"><span data-stu-id="bba4b-150">Availability of information is varied and depends on a lot of factors.</span></span> <span data-ttu-id="bba4b-151">Убедитесь, что это следует учитывать при использовании FileProfile() в запросах или при создании настраиваемой диагностики.</span><span class="sxs-lookup"><span data-stu-id="bba4b-151">Make sure to consider this when using FileProfile() in your queries or in creating custom detections.</span></span> <span data-ttu-id="bba4b-152">Для наилучших результатов рекомендуется использовать функцию FileProfile() с SHA1.</span><span class="sxs-lookup"><span data-stu-id="bba4b-152">For best results, we recommend using the FileProfile() function with SHA1.</span></span>

## <a name="examples"></a><span data-ttu-id="bba4b-153">Примеры</span><span class="sxs-lookup"><span data-stu-id="bba4b-153">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="bba4b-154">Проект только столбца SHA1 и его обогащение</span><span class="sxs-lookup"><span data-stu-id="bba4b-154">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="bba4b-155">Обогащение первых 500 записей и списков файлов с низкой распространенностью</span><span class="sxs-lookup"><span data-stu-id="bba4b-155">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="bba4b-156">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="bba4b-156">Related topics</span></span>
- [<span data-ttu-id="bba4b-157">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="bba4b-157">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="bba4b-158">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="bba4b-158">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="bba4b-159">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="bba4b-159">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="bba4b-160">Дополнительные примеры запросов</span><span class="sxs-lookup"><span data-stu-id="bba4b-160">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
