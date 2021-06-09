---
title: Получить API сведений о файлах
description: Узнайте, как использовать API сведений о файле Get для получения файла с помощью идентификаторов Sha1, Sha256 или MD5 в Microsoft Defender для конечной точки.
keywords: apis, graph api, supported apis, get, file, information, sha1, sha256, md5
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: b7877fb2d9b616b487d23befd0f0af35ce2c0753
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770299"
---
# <a name="get-file-information-api"></a><span data-ttu-id="a8f53-104">Получить API сведений о файлах</span><span class="sxs-lookup"><span data-stu-id="a8f53-104">Get file information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a8f53-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a8f53-105">**Applies to:**</span></span>
- [<span data-ttu-id="a8f53-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a8f53-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a8f53-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a8f53-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a8f53-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="a8f53-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a8f53-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="a8f53-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="a8f53-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="a8f53-110">API description</span></span>
<span data-ttu-id="a8f53-111">Извлечение [файла по](files.md) идентификатору Sha1 или Sha256</span><span class="sxs-lookup"><span data-stu-id="a8f53-111">Retrieves a [File](files.md) by identifier Sha1, or Sha256</span></span>


## <a name="limitations"></a><span data-ttu-id="a8f53-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="a8f53-112">Limitations</span></span>
1. <span data-ttu-id="a8f53-113">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="a8f53-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="a8f53-114">Разрешения</span><span class="sxs-lookup"><span data-stu-id="a8f53-114">Permissions</span></span>
<span data-ttu-id="a8f53-115">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="a8f53-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a8f53-116">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a8f53-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="a8f53-117">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="a8f53-117">Permission type</span></span> |   <span data-ttu-id="a8f53-118">Разрешение</span><span class="sxs-lookup"><span data-stu-id="a8f53-118">Permission</span></span>  |   <span data-ttu-id="a8f53-119">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="a8f53-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a8f53-120">Приложение</span><span class="sxs-lookup"><span data-stu-id="a8f53-120">Application</span></span> |   <span data-ttu-id="a8f53-121">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="a8f53-121">File.Read.All</span></span> | <span data-ttu-id="a8f53-122">'Read all file profiles'</span><span class="sxs-lookup"><span data-stu-id="a8f53-122">'Read all file profiles'</span></span>
<span data-ttu-id="a8f53-123">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="a8f53-123">Delegated (work or school account)</span></span> | <span data-ttu-id="a8f53-124">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="a8f53-124">File.Read.All</span></span> |    <span data-ttu-id="a8f53-125">'Read all file profiles'</span><span class="sxs-lookup"><span data-stu-id="a8f53-125">'Read all file profiles'</span></span>

>[!Note]
> <span data-ttu-id="a8f53-126">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="a8f53-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="a8f53-127">Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="a8f53-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="a8f53-128">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="a8f53-128">HTTP request</span></span>
```
GET /api/files/{id}
```

## <a name="request-headers"></a><span data-ttu-id="a8f53-129">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="a8f53-129">Request headers</span></span>

<span data-ttu-id="a8f53-130">Имя</span><span class="sxs-lookup"><span data-stu-id="a8f53-130">Name</span></span> | <span data-ttu-id="a8f53-131">Тип</span><span class="sxs-lookup"><span data-stu-id="a8f53-131">Type</span></span> | <span data-ttu-id="a8f53-132">Описание</span><span class="sxs-lookup"><span data-stu-id="a8f53-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="a8f53-133">Авторизация</span><span class="sxs-lookup"><span data-stu-id="a8f53-133">Authorization</span></span> | <span data-ttu-id="a8f53-134">String</span><span class="sxs-lookup"><span data-stu-id="a8f53-134">String</span></span> | <span data-ttu-id="a8f53-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="a8f53-135">Bearer {token}.</span></span> <span data-ttu-id="a8f53-136">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="a8f53-136">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="a8f53-137">Тело запроса</span><span class="sxs-lookup"><span data-stu-id="a8f53-137">Request body</span></span>
<span data-ttu-id="a8f53-138">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="a8f53-138">Empty</span></span>

## <a name="response"></a><span data-ttu-id="a8f53-139">Отклик</span><span class="sxs-lookup"><span data-stu-id="a8f53-139">Response</span></span>
<span data-ttu-id="a8f53-140">При успешном и файле существует — 200 ОК с [объектом файла](files.md) в теле.</span><span class="sxs-lookup"><span data-stu-id="a8f53-140">If successful and file exists - 200 OK with the [file](files.md) entity in the body.</span></span> <span data-ttu-id="a8f53-141">Если файл не существует - 404 Не найден.</span><span class="sxs-lookup"><span data-stu-id="a8f53-141">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="a8f53-142">Пример</span><span class="sxs-lookup"><span data-stu-id="a8f53-142">Example</span></span>

<span data-ttu-id="a8f53-143">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="a8f53-143">**Request**</span></span>

<span data-ttu-id="a8f53-144">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="a8f53-144">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/4388963aaa83afe2042a46a3c017ad50bdcdafb3
```

<span data-ttu-id="a8f53-145">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="a8f53-145">**Response**</span></span>

<span data-ttu-id="a8f53-146">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="a8f53-146">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Files/$entity",
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
