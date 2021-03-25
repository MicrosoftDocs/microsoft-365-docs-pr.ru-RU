---
title: Получать сведения о связанных доменах оповещений
description: Извлечение всех доменов, связанных с определенным оповещением с помощью Microsoft Defender для конечной точки.
keywords: apis, graph api, supported apis, get alert information, alert information, related domain
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
ms.openlocfilehash: 0cb09b23df8243d970069d087976ddc79394b67d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200417"
---
# <a name="get-alert-related-domain-information-api"></a><span data-ttu-id="b408a-104">Получить API сведений о домене, связанных с оповещением</span><span class="sxs-lookup"><span data-stu-id="b408a-104">Get alert related domain information API</span></span>

<span data-ttu-id="b408a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b408a-105">**Applies to:**</span></span> 
- [<span data-ttu-id="b408a-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b408a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- <span data-ttu-id="b408a-107">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="b408a-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b408a-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="b408a-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="b408a-109">Описание API</span><span class="sxs-lookup"><span data-stu-id="b408a-109">API description</span></span>
<span data-ttu-id="b408a-110">Извлекает все домены, связанные с определенным оповещением.</span><span class="sxs-lookup"><span data-stu-id="b408a-110">Retrieves all domains related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="b408a-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="b408a-111">Limitations</span></span>
1. <span data-ttu-id="b408a-112">Вы можете запрашивать последние обновления оповещений в соответствии с настроенным периодом хранения.</span><span class="sxs-lookup"><span data-stu-id="b408a-112">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="b408a-113">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="b408a-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="b408a-114">Разрешения</span><span class="sxs-lookup"><span data-stu-id="b408a-114">Permissions</span></span>
<span data-ttu-id="b408a-115">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="b408a-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b408a-116">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b408a-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="b408a-117">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="b408a-117">Permission type</span></span> | <span data-ttu-id="b408a-118">Разрешение</span><span class="sxs-lookup"><span data-stu-id="b408a-118">Permission</span></span> | <span data-ttu-id="b408a-119">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="b408a-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b408a-120">Application</span><span class="sxs-lookup"><span data-stu-id="b408a-120">Application</span></span> | <span data-ttu-id="b408a-121">URL-адрес. Read.All</span><span class="sxs-lookup"><span data-stu-id="b408a-121">URL.Read.All</span></span> | <span data-ttu-id="b408a-122">"Чтение URL-адресов"</span><span class="sxs-lookup"><span data-stu-id="b408a-122">'Read URLs'</span></span>
<span data-ttu-id="b408a-123">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="b408a-123">Delegated (work or school account)</span></span> | <span data-ttu-id="b408a-124">URL-адрес. Read.All</span><span class="sxs-lookup"><span data-stu-id="b408a-124">URL.Read.All</span></span> | <span data-ttu-id="b408a-125">"Чтение URL-адресов"</span><span class="sxs-lookup"><span data-stu-id="b408a-125">'Read URLs'</span></span>

>[!Note]
> <span data-ttu-id="b408a-126">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="b408a-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="b408a-127">Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="b408a-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="b408a-128">Пользователь должен иметь доступ к устройству, связанному с оповещением, на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="b408a-128">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="b408a-129">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="b408a-129">HTTP request</span></span>
```
GET /api/alerts/{id}/domains
```

## <a name="request-headers"></a><span data-ttu-id="b408a-130">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="b408a-130">Request headers</span></span>

<span data-ttu-id="b408a-131">Имя</span><span class="sxs-lookup"><span data-stu-id="b408a-131">Name</span></span> | <span data-ttu-id="b408a-132">Тип</span><span class="sxs-lookup"><span data-stu-id="b408a-132">Type</span></span> | <span data-ttu-id="b408a-133">Описание</span><span class="sxs-lookup"><span data-stu-id="b408a-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="b408a-134">Авторизация</span><span class="sxs-lookup"><span data-stu-id="b408a-134">Authorization</span></span> | <span data-ttu-id="b408a-135">Строка</span><span class="sxs-lookup"><span data-stu-id="b408a-135">String</span></span> | <span data-ttu-id="b408a-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="b408a-136">Bearer {token}.</span></span> <span data-ttu-id="b408a-137">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="b408a-137">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="b408a-138">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="b408a-138">Request body</span></span>
<span data-ttu-id="b408a-139">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="b408a-139">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b408a-140">Отклик</span><span class="sxs-lookup"><span data-stu-id="b408a-140">Response</span></span>
<span data-ttu-id="b408a-141">При успешном и оповещении и существовании домена — 200 ОК.</span><span class="sxs-lookup"><span data-stu-id="b408a-141">If successful and alert and domain exist - 200 OK.</span></span> <span data-ttu-id="b408a-142">Если оповещение не найдено - 404 Не найдено.</span><span class="sxs-lookup"><span data-stu-id="b408a-142">If alert not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="b408a-143">Пример</span><span class="sxs-lookup"><span data-stu-id="b408a-143">Example</span></span>

<span data-ttu-id="b408a-144">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="b408a-144">**Request**</span></span>

<span data-ttu-id="b408a-145">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="b408a-145">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/alerts/636688558380765161_2136280442/domains
```

<span data-ttu-id="b408a-146">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="b408a-146">**Response**</span></span>

<span data-ttu-id="b408a-147">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="b408a-147">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/$metadata#Domains",
    "value": [
        {
            "host": "www.example.com"
        },
        {
            "host": "www.example2.com"
        }
        ...
    ]
}

```
