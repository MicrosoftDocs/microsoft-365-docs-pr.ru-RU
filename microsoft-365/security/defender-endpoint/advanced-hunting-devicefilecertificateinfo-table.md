---
title: DeviceFileCertificateInfo table in the advanced hunting schema
description: Сведения о подписании файлов в таблице DeviceFileCertificateInfo в продвинутой схеме охоты
keywords: передовая охота, охота на угрозы, охота на киберугрозы, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, digital signature, certificate, file signing, DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: b3b5af8093107925c6c12c901e8138960c5eeaf6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072421"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="9c56e-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="9c56e-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9c56e-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="9c56e-105">**Applies to:**</span></span>
- [<span data-ttu-id="9c56e-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9c56e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="9c56e-107">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="9c56e-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9c56e-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="9c56e-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="9c56e-109">Таблица `DeviceFileCertificateInfo` в [продвинутой схеме охоты](advanced-hunting-overview.md) содержит сведения о сертификатах подписи файлов.</span><span class="sxs-lookup"><span data-stu-id="9c56e-109">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="9c56e-110">В этой таблице используются данные, полученные в ходе регулярной проверки сертификатов в файлах конечных точек.</span><span class="sxs-lookup"><span data-stu-id="9c56e-110">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="9c56e-111">Сведения о других таблицах в продвинутой схеме охоты см. в справке [о схеме охоты.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="9c56e-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="9c56e-112">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="9c56e-112">Column name</span></span> | <span data-ttu-id="9c56e-113">Тип данных</span><span class="sxs-lookup"><span data-stu-id="9c56e-113">Data type</span></span> | <span data-ttu-id="9c56e-114">Описание</span><span class="sxs-lookup"><span data-stu-id="9c56e-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="9c56e-115">datetime</span><span class="sxs-lookup"><span data-stu-id="9c56e-115">datetime</span></span> | <span data-ttu-id="9c56e-116">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="9c56e-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="9c56e-117">string</span><span class="sxs-lookup"><span data-stu-id="9c56e-117">string</span></span> | <span data-ttu-id="9c56e-118">Уникальный идентификатор устройства в службе</span><span class="sxs-lookup"><span data-stu-id="9c56e-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="9c56e-119">строка</span><span class="sxs-lookup"><span data-stu-id="9c56e-119">string</span></span> | <span data-ttu-id="9c56e-120">Полное доменное имя (FQDN) устройства</span><span class="sxs-lookup"><span data-stu-id="9c56e-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `SHA1` | <span data-ttu-id="9c56e-121">string</span><span class="sxs-lookup"><span data-stu-id="9c56e-121">string</span></span> | <span data-ttu-id="9c56e-122">SHA-1 файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="9c56e-122">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="9c56e-123">boolean</span><span class="sxs-lookup"><span data-stu-id="9c56e-123">boolean</span></span> | <span data-ttu-id="9c56e-124">Указывает, подписан ли файл</span><span class="sxs-lookup"><span data-stu-id="9c56e-124">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="9c56e-125">строка</span><span class="sxs-lookup"><span data-stu-id="9c56e-125">string</span></span> | <span data-ttu-id="9c56e-126">Указывает, была ли информация подписи прочитана как встроенное содержимое в самом файле или считывается из внешнего файла каталога.</span><span class="sxs-lookup"><span data-stu-id="9c56e-126">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="9c56e-127">строка</span><span class="sxs-lookup"><span data-stu-id="9c56e-127">string</span></span> | <span data-ttu-id="9c56e-128">Сведения о подписывщике файла</span><span class="sxs-lookup"><span data-stu-id="9c56e-128">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="9c56e-129">строка</span><span class="sxs-lookup"><span data-stu-id="9c56e-129">string</span></span> | <span data-ttu-id="9c56e-130">Уникальное значение hash, определяющие подписавщика</span><span class="sxs-lookup"><span data-stu-id="9c56e-130">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="9c56e-131">строка</span><span class="sxs-lookup"><span data-stu-id="9c56e-131">string</span></span> | <span data-ttu-id="9c56e-132">Сведения о полномочиях по выдаче сертификатов (CA)</span><span class="sxs-lookup"><span data-stu-id="9c56e-132">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="9c56e-133">строка</span><span class="sxs-lookup"><span data-stu-id="9c56e-133">string</span></span> | <span data-ttu-id="9c56e-134">Уникальное значение hash identifying issuing certificate authority (CA)</span><span class="sxs-lookup"><span data-stu-id="9c56e-134">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="9c56e-135">строка</span><span class="sxs-lookup"><span data-stu-id="9c56e-135">string</span></span> | <span data-ttu-id="9c56e-136">Идентификатор сертификата, который является уникальным для органа по выдаче сертификатов (CA)</span><span class="sxs-lookup"><span data-stu-id="9c56e-136">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="9c56e-137">строка</span><span class="sxs-lookup"><span data-stu-id="9c56e-137">string</span></span> |  <span data-ttu-id="9c56e-138">Массив JSON с перечислением URL-адресов сетевых акций, содержащих сертификаты и списки отзывов сертификатов (CRLs)</span><span class="sxs-lookup"><span data-stu-id="9c56e-138">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="9c56e-139">datetime</span><span class="sxs-lookup"><span data-stu-id="9c56e-139">datetime</span></span> | <span data-ttu-id="9c56e-140">Дата и время создания сертификата</span><span class="sxs-lookup"><span data-stu-id="9c56e-140">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="9c56e-141">datetime</span><span class="sxs-lookup"><span data-stu-id="9c56e-141">datetime</span></span> | <span data-ttu-id="9c56e-142">Дата и время истечения срока действия сертификата</span><span class="sxs-lookup"><span data-stu-id="9c56e-142">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="9c56e-143">datetime</span><span class="sxs-lookup"><span data-stu-id="9c56e-143">datetime</span></span> | <span data-ttu-id="9c56e-144">Дата и время, когда сертификат был подписан</span><span class="sxs-lookup"><span data-stu-id="9c56e-144">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="9c56e-145">boolean</span><span class="sxs-lookup"><span data-stu-id="9c56e-145">boolean</span></span> | <span data-ttu-id="9c56e-146">Указывает, доверяют ли файлу результаты функции WinVerifyTrust, которая проверяет неизвестные сведения корневого сертификата, недействительные подписи, отозванные сертификаты и другие сомнительные атрибуты.</span><span class="sxs-lookup"><span data-stu-id="9c56e-146">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="9c56e-147">boolean</span><span class="sxs-lookup"><span data-stu-id="9c56e-147">boolean</span></span> | <span data-ttu-id="9c56e-148">Указывает, является ли подписатель корневого сертификата Корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="9c56e-148">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="9c56e-149">long</span><span class="sxs-lookup"><span data-stu-id="9c56e-149">long</span></span> | <span data-ttu-id="9c56e-150">Идентификатор события на основе повторяющегося счетчика.</span><span class="sxs-lookup"><span data-stu-id="9c56e-150">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="9c56e-151">Для определения уникальных событий этот столбец должен использоваться в сочетании со столбцами DeviceName и Timestamp.</span><span class="sxs-lookup"><span data-stu-id="9c56e-151">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> |


## <a name="related-topics"></a><span data-ttu-id="9c56e-152">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="9c56e-152">Related topics</span></span>
- [<span data-ttu-id="9c56e-153">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="9c56e-153">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9c56e-154">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="9c56e-154">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9c56e-155">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="9c56e-155">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
