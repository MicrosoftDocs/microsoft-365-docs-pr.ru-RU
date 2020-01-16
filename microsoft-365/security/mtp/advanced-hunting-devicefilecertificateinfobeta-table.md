---
title: Таблица девицефилецертификатеинфобета в схеме расширенного поискового окна
description: Сведения о подписывании файлов в таблице Девицефилецертификатеинфобета расширенной схемы поискового подсистемы
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справка по схеме, Кусто, таблица, столбец, тип данных, цифровая подпись, сертификат, подписывание файлов девицефилецертификатеинфобета
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: d51fc812ffb82d9af1f706e513498da7611a1a6b
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210471"
---
# <a name="devicefilecertificateinfobeta"></a><span data-ttu-id="bbf46-104">девицефилецертификатеинфобета</span><span class="sxs-lookup"><span data-stu-id="bbf46-104">DeviceFileCertificateInfoBeta</span></span>

<span data-ttu-id="bbf46-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="bbf46-105">**Applies to:**</span></span>
- <span data-ttu-id="bbf46-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="bbf46-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="bbf46-107">`DeviceFileCertificateInfoBeta` Таблица в схеме [Advanced поиске](advanced-hunting-overview.md) содержит сведения о сертификатах подписи файлов.</span><span class="sxs-lookup"><span data-stu-id="bbf46-107">The `DeviceFileCertificateInfoBeta` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="bbf46-108">В этой таблице используются данные, полученные из действий по проверке сертификатов, которые регулярно выполняются для файлов в конечных точках.</span><span class="sxs-lookup"><span data-stu-id="bbf46-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="bbf46-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="bbf46-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="bbf46-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="bbf46-110">Column name</span></span> | <span data-ttu-id="bbf46-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="bbf46-111">Data type</span></span> | <span data-ttu-id="bbf46-112">Описание</span><span class="sxs-lookup"><span data-stu-id="bbf46-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="bbf46-113">datetime</span><span class="sxs-lookup"><span data-stu-id="bbf46-113">datetime</span></span> | <span data-ttu-id="bbf46-114">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="bbf46-114">Date and time when the event was recorded</span></span>
| `DeviceId` | <span data-ttu-id="bbf46-115">string</span><span class="sxs-lookup"><span data-stu-id="bbf46-115">string</span></span> | <span data-ttu-id="bbf46-116">Уникальный идентификатор для обслуживаемого компьютера</span><span class="sxs-lookup"><span data-stu-id="bbf46-116">Unique identifier for the machine in the service</span></span>
| `DeviceName` | <span data-ttu-id="bbf46-117">string</span><span class="sxs-lookup"><span data-stu-id="bbf46-117">string</span></span> | <span data-ttu-id="bbf46-118">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="bbf46-118">Fully qualified domain name (FQDN) of the machine</span></span>
| `SHA1` | <span data-ttu-id="bbf46-119">string</span><span class="sxs-lookup"><span data-stu-id="bbf46-119">string</span></span> | <span data-ttu-id="bbf46-120">SHA-1 файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="bbf46-120">SHA-1 of the file that the recorded action was applied to</span></span>
| `IsSigned` | <span data-ttu-id="bbf46-121">boolean</span><span class="sxs-lookup"><span data-stu-id="bbf46-121">boolean</span></span> | <span data-ttu-id="bbf46-122">Указывает, подписан ли файл</span><span class="sxs-lookup"><span data-stu-id="bbf46-122">Indicates whether the file is signed</span></span>
| `SignatureType` | <span data-ttu-id="bbf46-123">string</span><span class="sxs-lookup"><span data-stu-id="bbf46-123">string</span></span> | <span data-ttu-id="bbf46-124">Указывает, были ли сведения о подписи прочитаны как внедренный контент в самом файле или прочитаны из внешнего файла каталога</span><span class="sxs-lookup"><span data-stu-id="bbf46-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span>
| `Signer` | <span data-ttu-id="bbf46-125">string</span><span class="sxs-lookup"><span data-stu-id="bbf46-125">string</span></span> | <span data-ttu-id="bbf46-126">Сведения о подписавшем файла</span><span class="sxs-lookup"><span data-stu-id="bbf46-126">Information about the signer of the file</span></span>
| `SignerHash` | <span data-ttu-id="bbf46-127">string</span><span class="sxs-lookup"><span data-stu-id="bbf46-127">string</span></span> | <span data-ttu-id="bbf46-128">Уникальное значение хэша, идентифицирующее подписывающий</span><span class="sxs-lookup"><span data-stu-id="bbf46-128">Unique hash value identifying the signer</span></span>
| `Issuer` | <span data-ttu-id="bbf46-129">string</span><span class="sxs-lookup"><span data-stu-id="bbf46-129">string</span></span> | <span data-ttu-id="bbf46-130">Сведения о выдающем центре сертификации (ЦС)</span><span class="sxs-lookup"><span data-stu-id="bbf46-130">Information about the issuing certificate authority (CA)</span></span>
| `IssuerHash` | <span data-ttu-id="bbf46-131">string</span><span class="sxs-lookup"><span data-stu-id="bbf46-131">string</span></span> | <span data-ttu-id="bbf46-132">Уникальное хэш-значение, идентифицирующее выставляющий центр сертификации (CA)</span><span class="sxs-lookup"><span data-stu-id="bbf46-132">Unique hash value identifying issuing certificate authority (CA)</span></span>
| `CrlDistributionPointUrls` | <span data-ttu-id="bbf46-133">string</span><span class="sxs-lookup"><span data-stu-id="bbf46-133">string</span></span> |  <span data-ttu-id="bbf46-134">URL-адрес сетевой папки, содержащей сертификаты, и список отзыва сертификатов (CRL).</span><span class="sxs-lookup"><span data-stu-id="bbf46-134">URL of the network share that contains certificates and the certificate revocation list (CRL)</span></span>
| `CertificateCreationTime` | <span data-ttu-id="bbf46-135">datetime</span><span class="sxs-lookup"><span data-stu-id="bbf46-135">datetime</span></span> | <span data-ttu-id="bbf46-136">Дата и время создания сертификата</span><span class="sxs-lookup"><span data-stu-id="bbf46-136">Date and time the certificate was created</span></span>
| `CertificateExpirationTime` | <span data-ttu-id="bbf46-137">datetime</span><span class="sxs-lookup"><span data-stu-id="bbf46-137">datetime</span></span> | <span data-ttu-id="bbf46-138">Дата и время истечения срока действия сертификата</span><span class="sxs-lookup"><span data-stu-id="bbf46-138">Date and time the certificate is set to expire</span></span>
| `CertificateCountersignatureTime` | <span data-ttu-id="bbf46-139">datetime</span><span class="sxs-lookup"><span data-stu-id="bbf46-139">datetime</span></span> | <span data-ttu-id="bbf46-140">Дата и время, когда сертификат был каунтерсигнед</span><span class="sxs-lookup"><span data-stu-id="bbf46-140">Date and time the certificate was countersigned</span></span>
| `IsTrusted` | <span data-ttu-id="bbf46-141">boolean</span><span class="sxs-lookup"><span data-stu-id="bbf46-141">boolean</span></span> | <span data-ttu-id="bbf46-142">Указывает, является ли файл доверенным на основе результатов функции Винверифитруст, который проверяет наличие неизвестных сведений о корневых сертификатах, недопустимые подписи, отозванные сертификаты и другие сомнительные атрибуты</span><span class="sxs-lookup"><span data-stu-id="bbf46-142">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span>
| `IsRootSignerMicrosoft` | <span data-ttu-id="bbf46-143">boolean</span><span class="sxs-lookup"><span data-stu-id="bbf46-143">boolean</span></span> | <span data-ttu-id="bbf46-144">Указывает, является ли подписывающий корневой сертификат корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="bbf46-144">Indicates whether the signer of the root certificate is Microsoft</span></span>
| `ReportId` | <span data-ttu-id="bbf46-145">long</span><span class="sxs-lookup"><span data-stu-id="bbf46-145">long</span></span> | <span data-ttu-id="bbf46-146">Идентификатор события на основе повторяющегося счетчика.</span><span class="sxs-lookup"><span data-stu-id="bbf46-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="bbf46-147">Чтобы определить уникальные события, этот столбец должен использоваться вместе со столбцами DeviceName и timestamp.</span><span class="sxs-lookup"><span data-stu-id="bbf46-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bbf46-148">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="bbf46-148">Related topics</span></span>
- [<span data-ttu-id="bbf46-149">Заблаговременный поиск угроз</span><span class="sxs-lookup"><span data-stu-id="bbf46-149">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="bbf46-150">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="bbf46-150">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="bbf46-151">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="bbf46-151">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="bbf46-152">Поиск угроз на устройствах и в сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="bbf46-152">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="bbf46-153">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="bbf46-153">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="bbf46-154">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="bbf46-154">Apply query best practices</span></span>](advanced-hunting-best-practices.md)