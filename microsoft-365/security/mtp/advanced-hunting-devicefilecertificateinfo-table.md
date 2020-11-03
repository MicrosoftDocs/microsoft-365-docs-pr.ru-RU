---
title: Таблица девицефилецертификатеинфо в схеме расширенного поискового окна
description: Сведения о подписывании файлов в таблице Девицефилецертификатеинфо расширенной схемы поискового подсистемы
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справка по схеме, Кусто, таблица, столбец, тип данных, цифровая подпись, сертификат, подписывание файлов, Девицефилецертификатеинфо
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
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 9291d9f113fdc1c082b38d92399c1dee646b523d
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846174"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="1e791-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="1e791-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1e791-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1e791-105">**Applies to:**</span></span>
- <span data-ttu-id="1e791-106">Защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1e791-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="1e791-107">`DeviceFileCertificateInfo`Таблица в схеме [Advanced поиске](advanced-hunting-overview.md) содержит сведения о сертификатах подписи файлов.</span><span class="sxs-lookup"><span data-stu-id="1e791-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="1e791-108">В этой таблице используются данные, полученные из действий по проверке сертификатов, которые регулярно выполняются для файлов в конечных точках.</span><span class="sxs-lookup"><span data-stu-id="1e791-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="1e791-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="1e791-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="1e791-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="1e791-110">Column name</span></span> | <span data-ttu-id="1e791-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="1e791-111">Data type</span></span> | <span data-ttu-id="1e791-112">Описание</span><span class="sxs-lookup"><span data-stu-id="1e791-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="1e791-113">datetime</span><span class="sxs-lookup"><span data-stu-id="1e791-113">datetime</span></span> | <span data-ttu-id="1e791-114">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="1e791-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="1e791-115">string</span><span class="sxs-lookup"><span data-stu-id="1e791-115">string</span></span> | <span data-ttu-id="1e791-116">Уникальный идентификатор для обслуживаемого компьютера</span><span class="sxs-lookup"><span data-stu-id="1e791-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="1e791-117">string</span><span class="sxs-lookup"><span data-stu-id="1e791-117">string</span></span> | <span data-ttu-id="1e791-118">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="1e791-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="1e791-119">string</span><span class="sxs-lookup"><span data-stu-id="1e791-119">string</span></span> | <span data-ttu-id="1e791-120">SHA-1 файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="1e791-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="1e791-121">boolean</span><span class="sxs-lookup"><span data-stu-id="1e791-121">boolean</span></span> | <span data-ttu-id="1e791-122">Указывает, подписан ли файл</span><span class="sxs-lookup"><span data-stu-id="1e791-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="1e791-123">string</span><span class="sxs-lookup"><span data-stu-id="1e791-123">string</span></span> | <span data-ttu-id="1e791-124">Указывает, были ли сведения о подписи прочитаны как внедренный контент в самом файле или прочитаны из внешнего файла каталога</span><span class="sxs-lookup"><span data-stu-id="1e791-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="1e791-125">string</span><span class="sxs-lookup"><span data-stu-id="1e791-125">string</span></span> | <span data-ttu-id="1e791-126">Сведения о подписавшем файла</span><span class="sxs-lookup"><span data-stu-id="1e791-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="1e791-127">string</span><span class="sxs-lookup"><span data-stu-id="1e791-127">string</span></span> | <span data-ttu-id="1e791-128">Уникальное значение хэша, идентифицирующее подписывающий</span><span class="sxs-lookup"><span data-stu-id="1e791-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="1e791-129">string</span><span class="sxs-lookup"><span data-stu-id="1e791-129">string</span></span> | <span data-ttu-id="1e791-130">Сведения о выдающем центре сертификации (ЦС)</span><span class="sxs-lookup"><span data-stu-id="1e791-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="1e791-131">string</span><span class="sxs-lookup"><span data-stu-id="1e791-131">string</span></span> | <span data-ttu-id="1e791-132">Уникальное хэш-значение, идентифицирующее выставляющий центр сертификации (CA)</span><span class="sxs-lookup"><span data-stu-id="1e791-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="1e791-133">string</span><span class="sxs-lookup"><span data-stu-id="1e791-133">string</span></span> | <span data-ttu-id="1e791-134">Идентификатор сертификата, который является уникальным для выдающего центра сертификации (CA).</span><span class="sxs-lookup"><span data-stu-id="1e791-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="1e791-135">string</span><span class="sxs-lookup"><span data-stu-id="1e791-135">string</span></span> |  <span data-ttu-id="1e791-136">Массив JSON список URL-адресов сетевых ресурсов, содержащих сертификаты и списки отзыва сертификатов (CRL)</span><span class="sxs-lookup"><span data-stu-id="1e791-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="1e791-137">datetime</span><span class="sxs-lookup"><span data-stu-id="1e791-137">datetime</span></span> | <span data-ttu-id="1e791-138">Дата и время создания сертификата</span><span class="sxs-lookup"><span data-stu-id="1e791-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="1e791-139">datetime</span><span class="sxs-lookup"><span data-stu-id="1e791-139">datetime</span></span> | <span data-ttu-id="1e791-140">Дата и время истечения срока действия сертификата</span><span class="sxs-lookup"><span data-stu-id="1e791-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="1e791-141">datetime</span><span class="sxs-lookup"><span data-stu-id="1e791-141">datetime</span></span> | <span data-ttu-id="1e791-142">Дата и время, когда сертификат был каунтерсигнед</span><span class="sxs-lookup"><span data-stu-id="1e791-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="1e791-143">boolean</span><span class="sxs-lookup"><span data-stu-id="1e791-143">boolean</span></span> | <span data-ttu-id="1e791-144">Указывает, является ли файл доверенным на основе результатов функции Винверифитруст, который проверяет наличие неизвестных сведений о корневых сертификатах, недопустимые подписи, отозванные сертификаты и другие сомнительные атрибуты</span><span class="sxs-lookup"><span data-stu-id="1e791-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="1e791-145">boolean</span><span class="sxs-lookup"><span data-stu-id="1e791-145">boolean</span></span> | <span data-ttu-id="1e791-146">Указывает, является ли подписывающий корневой сертификат корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="1e791-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="1e791-147">long</span><span class="sxs-lookup"><span data-stu-id="1e791-147">long</span></span> | <span data-ttu-id="1e791-148">Идентификатор события на основе повторяющегося счетчика.</span><span class="sxs-lookup"><span data-stu-id="1e791-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="1e791-149">Чтобы определить уникальные события, этот столбец должен использоваться вместе со столбцами DeviceName и timestamp.</span><span class="sxs-lookup"><span data-stu-id="1e791-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="1e791-150">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="1e791-150">Related topics</span></span>
- [<span data-ttu-id="1e791-151">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="1e791-151">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1e791-152">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="1e791-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="1e791-153">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="1e791-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="1e791-154">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="1e791-154">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="1e791-155">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="1e791-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="1e791-156">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="1e791-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
