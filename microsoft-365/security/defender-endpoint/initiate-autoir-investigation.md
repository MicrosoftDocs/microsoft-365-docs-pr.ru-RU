---
title: Запуск API исследования
description: Используйте этот API, чтобы начать исследование на устройстве.
keywords: apis, graph api, supported apis, investigation
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
ms.openlocfilehash: b7a6a3e7f6f705f322ee3eb1c1b561bc01c55d29
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770893"
---
# <a name="start-investigation-api"></a><span data-ttu-id="03833-104">Запуск API исследования</span><span class="sxs-lookup"><span data-stu-id="03833-104">Start Investigation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="03833-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="03833-105">**Applies to:**</span></span>
- [<span data-ttu-id="03833-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="03833-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="03833-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="03833-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="03833-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="03833-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="03833-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="03833-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="03833-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="03833-110">API description</span></span>
<span data-ttu-id="03833-111">Запустите автоматическое исследование на устройстве.</span><span class="sxs-lookup"><span data-stu-id="03833-111">Start automated investigation on a device.</span></span>
<br><span data-ttu-id="03833-112">Дополнительные [сведения см.](automated-investigations.md) в обзоре автоматизированных расследований.</span><span class="sxs-lookup"><span data-stu-id="03833-112">See [Overview of automated investigations](automated-investigations.md) for more information.</span></span>


## <a name="limitations"></a><span data-ttu-id="03833-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="03833-113">Limitations</span></span>
1. <span data-ttu-id="03833-114">Ограничения скорости для этого API — 50 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="03833-114">Rate limitations for this API are 50 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="03833-115">Разрешения</span><span class="sxs-lookup"><span data-stu-id="03833-115">Permissions</span></span>
<span data-ttu-id="03833-116">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="03833-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="03833-117">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="03833-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="03833-118">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="03833-118">Permission type</span></span> |   <span data-ttu-id="03833-119">Разрешение</span><span class="sxs-lookup"><span data-stu-id="03833-119">Permission</span></span>  |   <span data-ttu-id="03833-120">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="03833-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="03833-121">Приложение</span><span class="sxs-lookup"><span data-stu-id="03833-121">Application</span></span> |   <span data-ttu-id="03833-122">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="03833-122">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="03833-123">'Read and write all alerts'</span><span class="sxs-lookup"><span data-stu-id="03833-123">'Read and write all alerts'</span></span>
<span data-ttu-id="03833-124">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="03833-124">Delegated (work or school account)</span></span> | <span data-ttu-id="03833-125">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="03833-125">Alert.ReadWrite</span></span> | <span data-ttu-id="03833-126">'Read and write alerts'</span><span class="sxs-lookup"><span data-stu-id="03833-126">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="03833-127">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="03833-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="03833-128">У пользователя должно быть по крайней мере следующее разрешение на роль: "Активные действия по исправлению" (см. дополнительные сведения о создании и управлении ролями) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="03833-128">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="03833-129">Пользователь должен иметь доступ к устройству на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="03833-129">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="03833-130">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="03833-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/startInvestigation
```

## <a name="request-headers"></a><span data-ttu-id="03833-131">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="03833-131">Request headers</span></span>

<span data-ttu-id="03833-132">Имя</span><span class="sxs-lookup"><span data-stu-id="03833-132">Name</span></span> | <span data-ttu-id="03833-133">Тип</span><span class="sxs-lookup"><span data-stu-id="03833-133">Type</span></span> | <span data-ttu-id="03833-134">Описание</span><span class="sxs-lookup"><span data-stu-id="03833-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="03833-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="03833-135">Authorization</span></span> | <span data-ttu-id="03833-136">String</span><span class="sxs-lookup"><span data-stu-id="03833-136">String</span></span> | <span data-ttu-id="03833-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="03833-137">Bearer {token}.</span></span> <span data-ttu-id="03833-138">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="03833-138">**Required**.</span></span>
<span data-ttu-id="03833-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="03833-139">Content-Type</span></span> | <span data-ttu-id="03833-140">string</span><span class="sxs-lookup"><span data-stu-id="03833-140">string</span></span> | <span data-ttu-id="03833-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="03833-141">application/json.</span></span> <span data-ttu-id="03833-142">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="03833-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="03833-143">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="03833-143">Request body</span></span>
<span data-ttu-id="03833-144">В теле запроса поставляем объект JSON со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="03833-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="03833-145">Параметр</span><span class="sxs-lookup"><span data-stu-id="03833-145">Parameter</span></span> | <span data-ttu-id="03833-146">Тип</span><span class="sxs-lookup"><span data-stu-id="03833-146">Type</span></span>    | <span data-ttu-id="03833-147">Описание</span><span class="sxs-lookup"><span data-stu-id="03833-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="03833-148">Comment</span><span class="sxs-lookup"><span data-stu-id="03833-148">Comment</span></span> |   <span data-ttu-id="03833-149">String</span><span class="sxs-lookup"><span data-stu-id="03833-149">String</span></span> |    <span data-ttu-id="03833-150">Комментарий для связи с действием.</span><span class="sxs-lookup"><span data-stu-id="03833-150">Comment to associate with the action.</span></span> <span data-ttu-id="03833-151">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="03833-151">**Required**.</span></span>


## <a name="response"></a><span data-ttu-id="03833-152">Отклик</span><span class="sxs-lookup"><span data-stu-id="03833-152">Response</span></span>
<span data-ttu-id="03833-153">В случае успеха этот метод возвращает 201 — созданный код ответа и [исследование](investigation.md) в тексте ответа.</span><span class="sxs-lookup"><span data-stu-id="03833-153">If successful, this method returns 201 - Created response code and [Investigation](investigation.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="03833-154">Пример</span><span class="sxs-lookup"><span data-stu-id="03833-154">Example</span></span>

<span data-ttu-id="03833-155">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="03833-155">**Request**</span></span>

<span data-ttu-id="03833-156">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="03833-156">Here is an example of the request.</span></span>

```https
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/startInvestigation
```

```json
{
  "Comment": "Test investigation"
}
```
