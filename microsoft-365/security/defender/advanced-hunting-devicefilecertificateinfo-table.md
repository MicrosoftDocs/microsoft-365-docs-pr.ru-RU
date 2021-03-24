---
title: DeviceFileCertificateInfo table in the advanced hunting schema
description: Сведения о подписании файлов в таблице DeviceFileCertificateInfo в продвинутой схеме охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft threat protection, Microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, digital signature, certificate, file signing, DeviceFileCertificateInfo
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
ms.openlocfilehash: 00e10c84c4bcb20f2e018bf05033b5b2235fd9ae
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071574"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="89399-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="89399-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="89399-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="89399-105">**Applies to:**</span></span>
- <span data-ttu-id="89399-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="89399-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="89399-107">Таблица `DeviceFileCertificateInfo` в [продвинутой схеме охоты](advanced-hunting-overview.md) содержит сведения о сертификатах подписи файлов.</span><span class="sxs-lookup"><span data-stu-id="89399-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="89399-108">В этой таблице используются данные, полученные в ходе регулярной проверки сертификатов в файлах конечных точек.</span><span class="sxs-lookup"><span data-stu-id="89399-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="89399-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="89399-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="89399-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="89399-110">Column name</span></span> | <span data-ttu-id="89399-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="89399-111">Data type</span></span> | <span data-ttu-id="89399-112">Описание</span><span class="sxs-lookup"><span data-stu-id="89399-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="89399-113">datetime</span><span class="sxs-lookup"><span data-stu-id="89399-113">datetime</span></span> | <span data-ttu-id="89399-114">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="89399-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="89399-115">string</span><span class="sxs-lookup"><span data-stu-id="89399-115">string</span></span> | <span data-ttu-id="89399-116">Уникальный идентификатор для обслуживаемого компьютера</span><span class="sxs-lookup"><span data-stu-id="89399-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="89399-117">string</span><span class="sxs-lookup"><span data-stu-id="89399-117">string</span></span> | <span data-ttu-id="89399-118">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="89399-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="89399-119">string</span><span class="sxs-lookup"><span data-stu-id="89399-119">string</span></span> | <span data-ttu-id="89399-120">SHA-1 файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="89399-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="89399-121">boolean</span><span class="sxs-lookup"><span data-stu-id="89399-121">boolean</span></span> | <span data-ttu-id="89399-122">Указывает, подписан ли файл</span><span class="sxs-lookup"><span data-stu-id="89399-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="89399-123">строка</span><span class="sxs-lookup"><span data-stu-id="89399-123">string</span></span> | <span data-ttu-id="89399-124">Указывает, была ли информация подписи прочитана как встроенное содержимое в самом файле или считывается из внешнего файла каталога.</span><span class="sxs-lookup"><span data-stu-id="89399-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="89399-125">строка</span><span class="sxs-lookup"><span data-stu-id="89399-125">string</span></span> | <span data-ttu-id="89399-126">Сведения о подписывщике файла</span><span class="sxs-lookup"><span data-stu-id="89399-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="89399-127">строка</span><span class="sxs-lookup"><span data-stu-id="89399-127">string</span></span> | <span data-ttu-id="89399-128">Уникальное значение hash, определяющие подписавщика</span><span class="sxs-lookup"><span data-stu-id="89399-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="89399-129">строка</span><span class="sxs-lookup"><span data-stu-id="89399-129">string</span></span> | <span data-ttu-id="89399-130">Сведения о полномочиях по выдаче сертификатов (CA)</span><span class="sxs-lookup"><span data-stu-id="89399-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="89399-131">строка</span><span class="sxs-lookup"><span data-stu-id="89399-131">string</span></span> | <span data-ttu-id="89399-132">Уникальное значение hash identifying issuing certificate authority (CA)</span><span class="sxs-lookup"><span data-stu-id="89399-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="89399-133">строка</span><span class="sxs-lookup"><span data-stu-id="89399-133">string</span></span> | <span data-ttu-id="89399-134">Идентификатор сертификата, который является уникальным для органа по выдаче сертификатов (CA)</span><span class="sxs-lookup"><span data-stu-id="89399-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="89399-135">строка</span><span class="sxs-lookup"><span data-stu-id="89399-135">string</span></span> |  <span data-ttu-id="89399-136">Массив JSON с перечислением URL-адресов сетевых акций, содержащих сертификаты и списки отзывов сертификатов (CRLs)</span><span class="sxs-lookup"><span data-stu-id="89399-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="89399-137">datetime</span><span class="sxs-lookup"><span data-stu-id="89399-137">datetime</span></span> | <span data-ttu-id="89399-138">Дата и время создания сертификата</span><span class="sxs-lookup"><span data-stu-id="89399-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="89399-139">datetime</span><span class="sxs-lookup"><span data-stu-id="89399-139">datetime</span></span> | <span data-ttu-id="89399-140">Дата и время истечения срока действия сертификата</span><span class="sxs-lookup"><span data-stu-id="89399-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="89399-141">datetime</span><span class="sxs-lookup"><span data-stu-id="89399-141">datetime</span></span> | <span data-ttu-id="89399-142">Дата и время, когда сертификат был подписан</span><span class="sxs-lookup"><span data-stu-id="89399-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="89399-143">boolean</span><span class="sxs-lookup"><span data-stu-id="89399-143">boolean</span></span> | <span data-ttu-id="89399-144">Указывает, доверяют ли файлу результаты функции WinVerifyTrust, которая проверяет неизвестные сведения корневого сертификата, недействительные подписи, отозванные сертификаты и другие сомнительные атрибуты.</span><span class="sxs-lookup"><span data-stu-id="89399-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="89399-145">boolean</span><span class="sxs-lookup"><span data-stu-id="89399-145">boolean</span></span> | <span data-ttu-id="89399-146">Указывает, является ли подписатель корневого сертификата Корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="89399-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="89399-147">long</span><span class="sxs-lookup"><span data-stu-id="89399-147">long</span></span> | <span data-ttu-id="89399-148">Идентификатор события на основе повторяющегося счетчика.</span><span class="sxs-lookup"><span data-stu-id="89399-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="89399-149">Для определения уникальных событий этот столбец должен использоваться в сочетании со столбцами DeviceName и Timestamp.</span><span class="sxs-lookup"><span data-stu-id="89399-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="89399-150">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="89399-150">Related topics</span></span>
- [<span data-ttu-id="89399-151">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="89399-151">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="89399-152">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="89399-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="89399-153">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="89399-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="89399-154">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="89399-154">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="89399-155">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="89399-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="89399-156">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="89399-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
