---
title: DeviceFileCertificateInfo table in the advanced hunting schema
description: Сведения о подписании файлов в таблице DeviceFileCertificateInfo в продвинутой схеме охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, digital signature, certificate, file signing, DeviceFileCertificateInfo
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
ms.openlocfilehash: 1f894f3fc8cff2113004ff9c9e34ec2ca0144799
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023217"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="01ad6-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="01ad6-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="01ad6-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="01ad6-105">**Applies to:**</span></span>
- <span data-ttu-id="01ad6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01ad6-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="01ad6-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="01ad6-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="01ad6-108">Таблица `DeviceFileCertificateInfo` в [продвинутой схеме охоты](advanced-hunting-overview.md) содержит сведения о сертификатах подписи файлов.</span><span class="sxs-lookup"><span data-stu-id="01ad6-108">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="01ad6-109">В этой таблице используются данные, полученные в ходе регулярной проверки сертификатов в файлах конечных точек.</span><span class="sxs-lookup"><span data-stu-id="01ad6-109">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="01ad6-110">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="01ad6-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="01ad6-111">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="01ad6-111">Column name</span></span> | <span data-ttu-id="01ad6-112">Тип данных</span><span class="sxs-lookup"><span data-stu-id="01ad6-112">Data type</span></span> | <span data-ttu-id="01ad6-113">Описание</span><span class="sxs-lookup"><span data-stu-id="01ad6-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="01ad6-114">datetime</span><span class="sxs-lookup"><span data-stu-id="01ad6-114">datetime</span></span> | <span data-ttu-id="01ad6-115">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="01ad6-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="01ad6-116">string</span><span class="sxs-lookup"><span data-stu-id="01ad6-116">string</span></span> | <span data-ttu-id="01ad6-117">Уникальный идентификатор для обслуживаемого компьютера</span><span class="sxs-lookup"><span data-stu-id="01ad6-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="01ad6-118">string</span><span class="sxs-lookup"><span data-stu-id="01ad6-118">string</span></span> | <span data-ttu-id="01ad6-119">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="01ad6-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="01ad6-120">string</span><span class="sxs-lookup"><span data-stu-id="01ad6-120">string</span></span> | <span data-ttu-id="01ad6-121">SHA-1 файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="01ad6-121">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="01ad6-122">boolean</span><span class="sxs-lookup"><span data-stu-id="01ad6-122">boolean</span></span> | <span data-ttu-id="01ad6-123">Указывает, подписан ли файл</span><span class="sxs-lookup"><span data-stu-id="01ad6-123">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="01ad6-124">Строка</span><span class="sxs-lookup"><span data-stu-id="01ad6-124">string</span></span> | <span data-ttu-id="01ad6-125">Указывает, была ли информация подписи прочитана как встроенное содержимое в самом файле или считывается из внешнего файла каталога.</span><span class="sxs-lookup"><span data-stu-id="01ad6-125">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="01ad6-126">Строка</span><span class="sxs-lookup"><span data-stu-id="01ad6-126">string</span></span> | <span data-ttu-id="01ad6-127">Сведения о подписывщике файла</span><span class="sxs-lookup"><span data-stu-id="01ad6-127">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="01ad6-128">Строка</span><span class="sxs-lookup"><span data-stu-id="01ad6-128">string</span></span> | <span data-ttu-id="01ad6-129">Уникальное значение hash, определяющие подписавщика</span><span class="sxs-lookup"><span data-stu-id="01ad6-129">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="01ad6-130">Строка</span><span class="sxs-lookup"><span data-stu-id="01ad6-130">string</span></span> | <span data-ttu-id="01ad6-131">Сведения о полномочиях по выдаче сертификатов (CA)</span><span class="sxs-lookup"><span data-stu-id="01ad6-131">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="01ad6-132">Строка</span><span class="sxs-lookup"><span data-stu-id="01ad6-132">string</span></span> | <span data-ttu-id="01ad6-133">Уникальное значение hash identifying issuing certificate authority (CA)</span><span class="sxs-lookup"><span data-stu-id="01ad6-133">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="01ad6-134">Строка</span><span class="sxs-lookup"><span data-stu-id="01ad6-134">string</span></span> | <span data-ttu-id="01ad6-135">Идентификатор сертификата, который является уникальным для органа по выдаче сертификатов (CA)</span><span class="sxs-lookup"><span data-stu-id="01ad6-135">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="01ad6-136">Строка</span><span class="sxs-lookup"><span data-stu-id="01ad6-136">string</span></span> |  <span data-ttu-id="01ad6-137">Массив JSON с перечислением URL-адресов сетевых акций, содержащих сертификаты и списки отзывов сертификатов (CRLs)</span><span class="sxs-lookup"><span data-stu-id="01ad6-137">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="01ad6-138">datetime</span><span class="sxs-lookup"><span data-stu-id="01ad6-138">datetime</span></span> | <span data-ttu-id="01ad6-139">Дата и время создания сертификата</span><span class="sxs-lookup"><span data-stu-id="01ad6-139">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="01ad6-140">datetime</span><span class="sxs-lookup"><span data-stu-id="01ad6-140">datetime</span></span> | <span data-ttu-id="01ad6-141">Дата и время истечения срока действия сертификата</span><span class="sxs-lookup"><span data-stu-id="01ad6-141">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="01ad6-142">datetime</span><span class="sxs-lookup"><span data-stu-id="01ad6-142">datetime</span></span> | <span data-ttu-id="01ad6-143">Дата и время, когда сертификат был подписан</span><span class="sxs-lookup"><span data-stu-id="01ad6-143">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="01ad6-144">boolean</span><span class="sxs-lookup"><span data-stu-id="01ad6-144">boolean</span></span> | <span data-ttu-id="01ad6-145">Указывает, доверяют ли файлу результаты функции WinVerifyTrust, которая проверяет неизвестные сведения корневого сертификата, недействительные подписи, отозванные сертификаты и другие сомнительные атрибуты.</span><span class="sxs-lookup"><span data-stu-id="01ad6-145">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="01ad6-146">boolean</span><span class="sxs-lookup"><span data-stu-id="01ad6-146">boolean</span></span> | <span data-ttu-id="01ad6-147">Указывает, является ли подписатель корневого сертификата Корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="01ad6-147">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="01ad6-148">long</span><span class="sxs-lookup"><span data-stu-id="01ad6-148">long</span></span> | <span data-ttu-id="01ad6-149">Идентификатор события на основе повторяющегося счетчика.</span><span class="sxs-lookup"><span data-stu-id="01ad6-149">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="01ad6-150">Для определения уникальных событий этот столбец должен использоваться в сочетании со столбцами DeviceName и Timestamp.</span><span class="sxs-lookup"><span data-stu-id="01ad6-150">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="01ad6-151">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="01ad6-151">Related topics</span></span>
- [<span data-ttu-id="01ad6-152">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="01ad6-152">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="01ad6-153">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="01ad6-153">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="01ad6-154">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="01ad6-154">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="01ad6-155">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="01ad6-155">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="01ad6-156">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="01ad6-156">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="01ad6-157">Применение рекомендаций по использованию запросов</span><span class="sxs-lookup"><span data-stu-id="01ad6-157">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
