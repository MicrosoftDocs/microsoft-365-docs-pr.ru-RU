---
title: Тип ресурса file
description: Извлечение последних оповещений Microsoft Defender для конечных точек, связанных с файлами.
keywords: apis, graph api, supported apis, get, alerts, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9079a47dcc078b582586370b322502b74ce3838c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199985"
---
# <a name="file-resource-type"></a><span data-ttu-id="a43cb-104">Тип ресурса file</span><span class="sxs-lookup"><span data-stu-id="a43cb-104">File resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a43cb-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="a43cb-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="a43cb-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="a43cb-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a43cb-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="a43cb-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="a43cb-108">Представляет объект файла в Защитнике для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a43cb-108">Represent a file entity in Defender for Endpoint.</span></span>

## <a name="methods"></a><span data-ttu-id="a43cb-109">Методы</span><span class="sxs-lookup"><span data-stu-id="a43cb-109">Methods</span></span>
<span data-ttu-id="a43cb-110">Метод</span><span class="sxs-lookup"><span data-stu-id="a43cb-110">Method</span></span>|<span data-ttu-id="a43cb-111">Возвращаемый тип</span><span class="sxs-lookup"><span data-stu-id="a43cb-111">Return Type</span></span> |<span data-ttu-id="a43cb-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a43cb-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="a43cb-113">Получить файл</span><span class="sxs-lookup"><span data-stu-id="a43cb-113">Get file</span></span>](get-file-information.md) | [<span data-ttu-id="a43cb-114">file</span><span class="sxs-lookup"><span data-stu-id="a43cb-114">file</span></span>](files.md) | <span data-ttu-id="a43cb-115">Получить один файл</span><span class="sxs-lookup"><span data-stu-id="a43cb-115">Get a single file</span></span> 
[<span data-ttu-id="a43cb-116">Оповещений, связанных с файлами списка</span><span class="sxs-lookup"><span data-stu-id="a43cb-116">List file related alerts</span></span>](get-file-related-alerts.md) | <span data-ttu-id="a43cb-117">Коллекция [alert](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="a43cb-117">[alert](alerts.md) collection</span></span> | <span data-ttu-id="a43cb-118">Получите [объекты](alerts.md) оповещений, связанные с файлом.</span><span class="sxs-lookup"><span data-stu-id="a43cb-118">Get the [alert](alerts.md) entities that are associated with the file.</span></span>
[<span data-ttu-id="a43cb-119">Машины, связанные с файлами списка</span><span class="sxs-lookup"><span data-stu-id="a43cb-119">List file related machines</span></span>](get-file-related-machines.md) | <span data-ttu-id="a43cb-120">[коллекция](machine.md) машин</span><span class="sxs-lookup"><span data-stu-id="a43cb-120">[machine](machine.md) collection</span></span> | <span data-ttu-id="a43cb-121">Получите [объекты](machine.md) машины, связанные с оповещением.</span><span class="sxs-lookup"><span data-stu-id="a43cb-121">Get the [machine](machine.md) entities associated with the alert.</span></span>
[<span data-ttu-id="a43cb-122">статистика файлов</span><span class="sxs-lookup"><span data-stu-id="a43cb-122">file statistics</span></span>](get-file-statistics.md) | <span data-ttu-id="a43cb-123">Сводка статистики</span><span class="sxs-lookup"><span data-stu-id="a43cb-123">Statistics summary</span></span> | <span data-ttu-id="a43cb-124">Извлекает распространенность для данного файла.</span><span class="sxs-lookup"><span data-stu-id="a43cb-124">Retrieves the prevalence for the given file.</span></span>


## <a name="properties"></a><span data-ttu-id="a43cb-125">Свойства</span><span class="sxs-lookup"><span data-stu-id="a43cb-125">Properties</span></span>
|<span data-ttu-id="a43cb-126">Свойство</span><span class="sxs-lookup"><span data-stu-id="a43cb-126">Property</span></span> | <span data-ttu-id="a43cb-127">Тип</span><span class="sxs-lookup"><span data-stu-id="a43cb-127">Type</span></span>    |   <span data-ttu-id="a43cb-128">Описание</span><span class="sxs-lookup"><span data-stu-id="a43cb-128">Description</span></span> |
|:---|:---|:---|
|<span data-ttu-id="a43cb-129">sha1</span><span class="sxs-lookup"><span data-stu-id="a43cb-129">sha1</span></span> | <span data-ttu-id="a43cb-130">Строка</span><span class="sxs-lookup"><span data-stu-id="a43cb-130">String</span></span> | <span data-ttu-id="a43cb-131">Sha1 hash of the file content</span><span class="sxs-lookup"><span data-stu-id="a43cb-131">Sha1 hash of the file content</span></span> |
|<span data-ttu-id="a43cb-132">sha256</span><span class="sxs-lookup"><span data-stu-id="a43cb-132">sha256</span></span> | <span data-ttu-id="a43cb-133">Строка</span><span class="sxs-lookup"><span data-stu-id="a43cb-133">String</span></span> | <span data-ttu-id="a43cb-134">Sha256 hash of the file content</span><span class="sxs-lookup"><span data-stu-id="a43cb-134">Sha256 hash of the file content</span></span> |
|<span data-ttu-id="a43cb-135">globalPrevalence</span><span class="sxs-lookup"><span data-stu-id="a43cb-135">globalPrevalence</span></span> | <span data-ttu-id="a43cb-136">Nullable long</span><span class="sxs-lookup"><span data-stu-id="a43cb-136">Nullable long</span></span> | <span data-ttu-id="a43cb-137">Распространенность файлов в организации</span><span class="sxs-lookup"><span data-stu-id="a43cb-137">File prevalence across organization</span></span> |
|<span data-ttu-id="a43cb-138">globalFirstObserved</span><span class="sxs-lookup"><span data-stu-id="a43cb-138">globalFirstObserved</span></span> | <span data-ttu-id="a43cb-139">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="a43cb-139">DateTimeOffset</span></span> | <span data-ttu-id="a43cb-140">При первом наблюдении файла</span><span class="sxs-lookup"><span data-stu-id="a43cb-140">First time the file was observed</span></span> |
|<span data-ttu-id="a43cb-141">globalLastObserved</span><span class="sxs-lookup"><span data-stu-id="a43cb-141">globalLastObserved</span></span> | <span data-ttu-id="a43cb-142">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="a43cb-142">DateTimeOffset</span></span> | <span data-ttu-id="a43cb-143">Последний раз, когда файл был замечен</span><span class="sxs-lookup"><span data-stu-id="a43cb-143">Last time the file was observed</span></span> |
|<span data-ttu-id="a43cb-144">size</span><span class="sxs-lookup"><span data-stu-id="a43cb-144">size</span></span> | <span data-ttu-id="a43cb-145">Nullable long</span><span class="sxs-lookup"><span data-stu-id="a43cb-145">Nullable long</span></span> | <span data-ttu-id="a43cb-146">Размер файла</span><span class="sxs-lookup"><span data-stu-id="a43cb-146">Size of the file</span></span> |
|<span data-ttu-id="a43cb-147">fileType</span><span class="sxs-lookup"><span data-stu-id="a43cb-147">fileType</span></span> | <span data-ttu-id="a43cb-148">Строка</span><span class="sxs-lookup"><span data-stu-id="a43cb-148">String</span></span> | <span data-ttu-id="a43cb-149">Тип файла</span><span class="sxs-lookup"><span data-stu-id="a43cb-149">Type of the file</span></span> |
|<span data-ttu-id="a43cb-150">isPeFile</span><span class="sxs-lookup"><span data-stu-id="a43cb-150">isPeFile</span></span> | <span data-ttu-id="a43cb-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="a43cb-151">Boolean</span></span> | <span data-ttu-id="a43cb-152">верно, если файл является переносным для выполнения (например, "DLL", "EXE" и т.д.)</span><span class="sxs-lookup"><span data-stu-id="a43cb-152">true if the file is portable executable (e.g. "DLL", "EXE", etc.)</span></span> |
|<span data-ttu-id="a43cb-153">filePublisher</span><span class="sxs-lookup"><span data-stu-id="a43cb-153">filePublisher</span></span> | <span data-ttu-id="a43cb-154">Строка</span><span class="sxs-lookup"><span data-stu-id="a43cb-154">String</span></span> | <span data-ttu-id="a43cb-155">Издатель файлов</span><span class="sxs-lookup"><span data-stu-id="a43cb-155">File publisher</span></span> |
|<span data-ttu-id="a43cb-156">fileProductName</span><span class="sxs-lookup"><span data-stu-id="a43cb-156">fileProductName</span></span> | <span data-ttu-id="a43cb-157">Строка</span><span class="sxs-lookup"><span data-stu-id="a43cb-157">String</span></span> | <span data-ttu-id="a43cb-158">Название продукта</span><span class="sxs-lookup"><span data-stu-id="a43cb-158">Product name</span></span> |
|<span data-ttu-id="a43cb-159">подписывка</span><span class="sxs-lookup"><span data-stu-id="a43cb-159">signer</span></span> | <span data-ttu-id="a43cb-160">Строка</span><span class="sxs-lookup"><span data-stu-id="a43cb-160">String</span></span> | <span data-ttu-id="a43cb-161">Подписатель файлов</span><span class="sxs-lookup"><span data-stu-id="a43cb-161">File signer</span></span> |
|<span data-ttu-id="a43cb-162">эмитент</span><span class="sxs-lookup"><span data-stu-id="a43cb-162">issuer</span></span> | <span data-ttu-id="a43cb-163">Строка</span><span class="sxs-lookup"><span data-stu-id="a43cb-163">String</span></span> | <span data-ttu-id="a43cb-164">Эмитент файлов</span><span class="sxs-lookup"><span data-stu-id="a43cb-164">File issuer</span></span> |
|<span data-ttu-id="a43cb-165">signerHash</span><span class="sxs-lookup"><span data-stu-id="a43cb-165">signerHash</span></span> | <span data-ttu-id="a43cb-166">Строка</span><span class="sxs-lookup"><span data-stu-id="a43cb-166">String</span></span> | <span data-ttu-id="a43cb-167">Hash of the signing certificate</span><span class="sxs-lookup"><span data-stu-id="a43cb-167">Hash of the signing certificate</span></span> |
|<span data-ttu-id="a43cb-168">isValidCertificate</span><span class="sxs-lookup"><span data-stu-id="a43cb-168">isValidCertificate</span></span> | <span data-ttu-id="a43cb-169">Boolean</span><span class="sxs-lookup"><span data-stu-id="a43cb-169">Boolean</span></span> | <span data-ttu-id="a43cb-170">Был успешно проверен сертификат подписи агентом Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="a43cb-170">Was signing certificate successfully verified by Microsoft Defender for Endpoint agent</span></span> |
|<span data-ttu-id="a43cb-171">determinationType</span><span class="sxs-lookup"><span data-stu-id="a43cb-171">determinationType</span></span> | <span data-ttu-id="a43cb-172">Строка</span><span class="sxs-lookup"><span data-stu-id="a43cb-172">String</span></span> | <span data-ttu-id="a43cb-173">Тип определения файла</span><span class="sxs-lookup"><span data-stu-id="a43cb-173">The determination type of the file</span></span> |
|<span data-ttu-id="a43cb-174">determinationValue</span><span class="sxs-lookup"><span data-stu-id="a43cb-174">determinationValue</span></span> | <span data-ttu-id="a43cb-175">Строка</span><span class="sxs-lookup"><span data-stu-id="a43cb-175">String</span></span> | <span data-ttu-id="a43cb-176">Значение определения</span><span class="sxs-lookup"><span data-stu-id="a43cb-176">Determination value</span></span> |


## <a name="json-representation"></a><span data-ttu-id="a43cb-177">Представление Json</span><span class="sxs-lookup"><span data-stu-id="a43cb-177">Json representation</span></span>

```json
{
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
