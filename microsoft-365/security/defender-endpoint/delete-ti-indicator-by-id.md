---
title: Удаление API индикатора.
description: Узнайте, как использовать API delete Indicator для удаления объекта индикатора по ID в Microsoft Defender для конечной точки.
keywords: apis, public api, supported apis, delete, ti indicator, entity, id
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
ms.openlocfilehash: 1541e1d6e177416d77d768cef04d2524e6907ab5
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289923"
---
# <a name="delete-indicator-api"></a><span data-ttu-id="89a13-104">Удаление API индикатора</span><span class="sxs-lookup"><span data-stu-id="89a13-104">Delete Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="89a13-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="89a13-105">**Applies to:**</span></span>
- [<span data-ttu-id="89a13-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="89a13-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="89a13-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="89a13-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="89a13-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="89a13-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="89a13-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="89a13-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)  

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="89a13-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="89a13-110">API description</span></span>

<span data-ttu-id="89a13-111">Удаляет объект [индикатора](ti-indicator.md) по ID.</span><span class="sxs-lookup"><span data-stu-id="89a13-111">Deletes an [Indicator](ti-indicator.md) entity by ID.</span></span>

## <a name="limitations"></a><span data-ttu-id="89a13-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="89a13-112">Limitations</span></span>

<span data-ttu-id="89a13-113">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="89a13-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="89a13-114">Разрешения</span><span class="sxs-lookup"><span data-stu-id="89a13-114">Permissions</span></span>

<span data-ttu-id="89a13-115">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="89a13-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="89a13-116">Дополнительные новости, в том числе выбор разрешений, см. в [руб. Начало работы](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="89a13-116">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="89a13-117">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="89a13-117">Permission type</span></span> | <span data-ttu-id="89a13-118">Разрешение</span><span class="sxs-lookup"><span data-stu-id="89a13-118">Permission</span></span> | <span data-ttu-id="89a13-119">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="89a13-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="89a13-120">Application</span><span class="sxs-lookup"><span data-stu-id="89a13-120">Application</span></span> | <span data-ttu-id="89a13-121">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="89a13-121">Ti.ReadWrite</span></span> | <span data-ttu-id="89a13-122">"Чтение и написание индикаторов TI"</span><span class="sxs-lookup"><span data-stu-id="89a13-122">'Read and write TI Indicators'</span></span>
<span data-ttu-id="89a13-123">Application</span><span class="sxs-lookup"><span data-stu-id="89a13-123">Application</span></span> | <span data-ttu-id="89a13-124">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="89a13-124">Ti.ReadWrite.All</span></span> | <span data-ttu-id="89a13-125">'Read and write Indicators'</span><span class="sxs-lookup"><span data-stu-id="89a13-125">'Read and write Indicators'</span></span>

## <a name="http-request"></a><span data-ttu-id="89a13-126">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="89a13-126">HTTP request</span></span>

```http
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a><span data-ttu-id="89a13-127">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="89a13-127">Request headers</span></span>

<span data-ttu-id="89a13-128">Имя</span><span class="sxs-lookup"><span data-stu-id="89a13-128">Name</span></span> | <span data-ttu-id="89a13-129">Тип</span><span class="sxs-lookup"><span data-stu-id="89a13-129">Type</span></span> | <span data-ttu-id="89a13-130">Описание</span><span class="sxs-lookup"><span data-stu-id="89a13-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="89a13-131">Authorization</span><span class="sxs-lookup"><span data-stu-id="89a13-131">Authorization</span></span> | <span data-ttu-id="89a13-132">Строка</span><span class="sxs-lookup"><span data-stu-id="89a13-132">String</span></span> | <span data-ttu-id="89a13-133">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="89a13-133">Bearer {token}.</span></span> <span data-ttu-id="89a13-134">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="89a13-134">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="89a13-135">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="89a13-135">Request body</span></span>

<span data-ttu-id="89a13-136">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="89a13-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="89a13-137">Отклик</span><span class="sxs-lookup"><span data-stu-id="89a13-137">Response</span></span>

<span data-ttu-id="89a13-138">Если Индикатор существует и успешно удаляется — 204 ОК без контента.</span><span class="sxs-lookup"><span data-stu-id="89a13-138">If Indicator exist and deleted successfully - 204 OK without content.</span></span>

<span data-ttu-id="89a13-139">Если индикатор с указанным id не найден - 404 Не найден.</span><span class="sxs-lookup"><span data-stu-id="89a13-139">If Indicator with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="89a13-140">Пример</span><span class="sxs-lookup"><span data-stu-id="89a13-140">Example</span></span>

### <a name="request"></a><span data-ttu-id="89a13-141">Запрос</span><span class="sxs-lookup"><span data-stu-id="89a13-141">Request</span></span>

<span data-ttu-id="89a13-142">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="89a13-142">Here is an example of the request.</span></span>

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
