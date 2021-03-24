---
title: Функция FileProfile() в продвинутой охоте для Microsoft 365 Defender
description: Узнайте, как использовать FileProfile() для обогащения сведений о файлах в результатах запроса на расширенные запросы на охоту
keywords: передовая охота, охота на угрозы, поиск киберугроз, защита от угроз Майкрософт, Microsoft 365, mtp, m365, поиск, запрос, телеметрия, ссылка схемы, kusto, FileProfile, профиль файла, функция, обогащение
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e511c12240512af772b3552f63ad9ed98ff105af
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070118"
---
# <a name="fileprofile"></a><span data-ttu-id="4f209-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="4f209-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4f209-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="4f209-105">**Applies to:**</span></span>
- <span data-ttu-id="4f209-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4f209-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="4f209-107">Функция является функцией обогащения в продвинутой охоте, которая добавляет следующие данные в `FileProfile()` файлы, найденные в [](advanced-hunting-overview.md) запросе.</span><span class="sxs-lookup"><span data-stu-id="4f209-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="4f209-108">Column</span><span class="sxs-lookup"><span data-stu-id="4f209-108">Column</span></span> | <span data-ttu-id="4f209-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="4f209-109">Data type</span></span> | <span data-ttu-id="4f209-110">Описание</span><span class="sxs-lookup"><span data-stu-id="4f209-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="4f209-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="4f209-111">SHA1</span></span> | <span data-ttu-id="4f209-112">string</span><span class="sxs-lookup"><span data-stu-id="4f209-112">string</span></span> | <span data-ttu-id="4f209-113">SHA-1 файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="4f209-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="4f209-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="4f209-114">SHA256</span></span> | <span data-ttu-id="4f209-115">строка</span><span class="sxs-lookup"><span data-stu-id="4f209-115">string</span></span> | <span data-ttu-id="4f209-116">SHA-256 файла, к который было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="4f209-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="4f209-117">MD5</span><span class="sxs-lookup"><span data-stu-id="4f209-117">MD5</span></span> | <span data-ttu-id="4f209-118">строка</span><span class="sxs-lookup"><span data-stu-id="4f209-118">string</span></span> | <span data-ttu-id="4f209-119">Hash MD5 файла, к который было применено записано действие</span><span class="sxs-lookup"><span data-stu-id="4f209-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="4f209-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="4f209-120">FileSize</span></span> | <span data-ttu-id="4f209-121">int</span><span class="sxs-lookup"><span data-stu-id="4f209-121">int</span></span> | <span data-ttu-id="4f209-122">Размер файла в bytes</span><span class="sxs-lookup"><span data-stu-id="4f209-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="4f209-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="4f209-123">GlobalPrevalence</span></span> | <span data-ttu-id="4f209-124">int</span><span class="sxs-lookup"><span data-stu-id="4f209-124">int</span></span> | <span data-ttu-id="4f209-125">Количество экземпляров объекта, наблюдаемого Корпорацией Майкрософт во всем мире</span><span class="sxs-lookup"><span data-stu-id="4f209-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="4f209-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="4f209-126">GlobalFirstSeen</span></span> | <span data-ttu-id="4f209-127">datetime</span><span class="sxs-lookup"><span data-stu-id="4f209-127">datetime</span></span> | <span data-ttu-id="4f209-128">Дата и время, когда сущность впервые была замечена Корпорацией Майкрософт во всем мире</span><span class="sxs-lookup"><span data-stu-id="4f209-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="4f209-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="4f209-129">GlobalLastSeen</span></span> | <span data-ttu-id="4f209-130">datetime</span><span class="sxs-lookup"><span data-stu-id="4f209-130">datetime</span></span> | <span data-ttu-id="4f209-131">Дата и время, когда объект в последний раз наблюдался Корпорацией Майкрософт во всем мире</span><span class="sxs-lookup"><span data-stu-id="4f209-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="4f209-132">Signer</span><span class="sxs-lookup"><span data-stu-id="4f209-132">Signer</span></span> | <span data-ttu-id="4f209-133">строка</span><span class="sxs-lookup"><span data-stu-id="4f209-133">string</span></span> | <span data-ttu-id="4f209-134">Сведения о подписывщике файла</span><span class="sxs-lookup"><span data-stu-id="4f209-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="4f209-135">Издатель</span><span class="sxs-lookup"><span data-stu-id="4f209-135">Issuer</span></span> | <span data-ttu-id="4f209-136">строка</span><span class="sxs-lookup"><span data-stu-id="4f209-136">string</span></span> | <span data-ttu-id="4f209-137">Сведения о полномочиях по выдаче сертификатов (CA)</span><span class="sxs-lookup"><span data-stu-id="4f209-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="4f209-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="4f209-138">SignerHash</span></span> | <span data-ttu-id="4f209-139">строка</span><span class="sxs-lookup"><span data-stu-id="4f209-139">string</span></span> | <span data-ttu-id="4f209-140">Уникальное значение hash, определяющие подписавщика</span><span class="sxs-lookup"><span data-stu-id="4f209-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="4f209-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="4f209-141">IsCertificateValid</span></span> | <span data-ttu-id="4f209-142">boolean</span><span class="sxs-lookup"><span data-stu-id="4f209-142">boolean</span></span> | <span data-ttu-id="4f209-143">Допустим ли сертификат, используемый для подписи файла</span><span class="sxs-lookup"><span data-stu-id="4f209-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="4f209-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="4f209-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="4f209-145">boolean</span><span class="sxs-lookup"><span data-stu-id="4f209-145">boolean</span></span> | <span data-ttu-id="4f209-146">Указывает, является ли подписатель корневого сертификата Корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="4f209-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="4f209-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="4f209-147">IsExecutable</span></span> | <span data-ttu-id="4f209-148">boolean</span><span class="sxs-lookup"><span data-stu-id="4f209-148">boolean</span></span> | <span data-ttu-id="4f209-149">Является ли файл портативным исполняемым (PE) файлом</span><span class="sxs-lookup"><span data-stu-id="4f209-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="4f209-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="4f209-150">ThreatName</span></span> | <span data-ttu-id="4f209-151">строка</span><span class="sxs-lookup"><span data-stu-id="4f209-151">string</span></span> | <span data-ttu-id="4f209-152">Имя обнаружения любых найденных вредоносных программ или других угроз</span><span class="sxs-lookup"><span data-stu-id="4f209-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="4f209-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="4f209-153">Publisher</span></span> | <span data-ttu-id="4f209-154">строка</span><span class="sxs-lookup"><span data-stu-id="4f209-154">string</span></span> | <span data-ttu-id="4f209-155">Имя организации, которая опубликовала файл</span><span class="sxs-lookup"><span data-stu-id="4f209-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="4f209-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="4f209-156">SoftwareName</span></span> | <span data-ttu-id="4f209-157">string</span><span class="sxs-lookup"><span data-stu-id="4f209-157">string</span></span> | <span data-ttu-id="4f209-158">Название программного продукта</span><span class="sxs-lookup"><span data-stu-id="4f209-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="4f209-159">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f209-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="4f209-160">Аргументы</span><span class="sxs-lookup"><span data-stu-id="4f209-160">Arguments</span></span>

- <span data-ttu-id="4f209-161">**x**— столбец ID файла для использования: , , , или ; использование `SHA1` `SHA256` функции, если `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` неустановлено</span><span class="sxs-lookup"><span data-stu-id="4f209-161">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="4f209-162">**y**— ограничение количества записей для обогащения, 1-1000; функция использует 100, если неустановлено</span><span class="sxs-lookup"><span data-stu-id="4f209-162">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>


>[!TIP]
> <span data-ttu-id="4f209-163">Функции обогащения будут показывать дополнительные сведения только в том случае, если они доступны.</span><span class="sxs-lookup"><span data-stu-id="4f209-163">Enrichment functions will show supplemental information only when they are available.</span></span> <span data-ttu-id="4f209-164">Доступность информации разнообразна и зависит от многих факторов.</span><span class="sxs-lookup"><span data-stu-id="4f209-164">Availability of information is varied and depends on a lot of factors.</span></span> <span data-ttu-id="4f209-165">Убедитесь, что это следует учитывать при использовании FileProfile() в запросах или при создании настраиваемой диагностики.</span><span class="sxs-lookup"><span data-stu-id="4f209-165">Make sure to consider this when using FileProfile() in your queries or in creating custom detections.</span></span> <span data-ttu-id="4f209-166">Для наилучших результатов рекомендуется использовать функцию FileProfile() с SHA1.</span><span class="sxs-lookup"><span data-stu-id="4f209-166">For best results, we recommend using the FileProfile() function with SHA1.</span></span>

## <a name="examples"></a><span data-ttu-id="4f209-167">Примеры</span><span class="sxs-lookup"><span data-stu-id="4f209-167">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="4f209-168">Проект только столбца SHA1 и его обогащение</span><span class="sxs-lookup"><span data-stu-id="4f209-168">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="4f209-169">Обогащение первых 500 записей и списков файлов с низкой распространенностью</span><span class="sxs-lookup"><span data-stu-id="4f209-169">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="4f209-170">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="4f209-170">Related topics</span></span>
- [<span data-ttu-id="4f209-171">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="4f209-171">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4f209-172">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="4f209-172">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4f209-173">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="4f209-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="4f209-174">Дополнительные примеры запросов</span><span class="sxs-lookup"><span data-stu-id="4f209-174">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
