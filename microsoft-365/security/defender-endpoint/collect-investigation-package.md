---
title: Сбор API пакета расследований
description: Используйте этот API для создания вызовов, связанных с сбором пакета исследований с устройства.
keywords: apis, graph api, supported apis, collect investigation package
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
ms.openlocfilehash: 1e24236aae1922705c1711042f0426251a979ede
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167083"
---
# <a name="collect-investigation-package-api"></a><span data-ttu-id="22d6d-104">Сбор API пакета расследований</span><span class="sxs-lookup"><span data-stu-id="22d6d-104">Collect investigation package API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="22d6d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="22d6d-105">**Applies to:**</span></span>
- [<span data-ttu-id="22d6d-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="22d6d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="22d6d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="22d6d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="22d6d-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="22d6d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="22d6d-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="22d6d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="22d6d-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="22d6d-110">API description</span></span>
<span data-ttu-id="22d6d-111">Сбор пакета исследований с устройства.</span><span class="sxs-lookup"><span data-stu-id="22d6d-111">Collect investigation package from a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="22d6d-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="22d6d-112">Limitations</span></span>
1. <span data-ttu-id="22d6d-113">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="22d6d-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="22d6d-114">Разрешения</span><span class="sxs-lookup"><span data-stu-id="22d6d-114">Permissions</span></span>
<span data-ttu-id="22d6d-115">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="22d6d-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="22d6d-116">Дополнительные новости, в том числе выбор разрешений, см. в этой [ссылке: Use Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="22d6d-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="22d6d-117">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="22d6d-117">Permission type</span></span> |   <span data-ttu-id="22d6d-118">Разрешение</span><span class="sxs-lookup"><span data-stu-id="22d6d-118">Permission</span></span>  |   <span data-ttu-id="22d6d-119">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="22d6d-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="22d6d-120">Приложение</span><span class="sxs-lookup"><span data-stu-id="22d6d-120">Application</span></span> |   <span data-ttu-id="22d6d-121">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="22d6d-121">Machine.CollectForensics</span></span> |  <span data-ttu-id="22d6d-122">'Collect forensics'</span><span class="sxs-lookup"><span data-stu-id="22d6d-122">'Collect forensics'</span></span>
<span data-ttu-id="22d6d-123">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="22d6d-123">Delegated (work or school account)</span></span> |    <span data-ttu-id="22d6d-124">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="22d6d-124">Machine.CollectForensics</span></span> |  <span data-ttu-id="22d6d-125">'Collect forensics'</span><span class="sxs-lookup"><span data-stu-id="22d6d-125">'Collect forensics'</span></span>

>[!Note]
> <span data-ttu-id="22d6d-126">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="22d6d-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="22d6d-127">Пользователю необходимо иметь по крайней мере следующее разрешение на роль: 'Alerts Investigation' (См. [создание](user-roles.md) ролей и управление ими для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="22d6d-127">The user needs to have at least the following role permission: 'Alerts Investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="22d6d-128">Пользователь должен иметь доступ к устройству на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="22d6d-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="22d6d-129">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="22d6d-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/collectInvestigationPackage
```

## <a name="request-headers"></a><span data-ttu-id="22d6d-130">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="22d6d-130">Request headers</span></span>

<span data-ttu-id="22d6d-131">Имя</span><span class="sxs-lookup"><span data-stu-id="22d6d-131">Name</span></span> | <span data-ttu-id="22d6d-132">Тип</span><span class="sxs-lookup"><span data-stu-id="22d6d-132">Type</span></span> | <span data-ttu-id="22d6d-133">Описание</span><span class="sxs-lookup"><span data-stu-id="22d6d-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="22d6d-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="22d6d-134">Authorization</span></span> | <span data-ttu-id="22d6d-135">Строка</span><span class="sxs-lookup"><span data-stu-id="22d6d-135">String</span></span> | <span data-ttu-id="22d6d-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="22d6d-136">Bearer {token}.</span></span> <span data-ttu-id="22d6d-137">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="22d6d-137">**Required**.</span></span>
<span data-ttu-id="22d6d-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="22d6d-138">Content-Type</span></span> | <span data-ttu-id="22d6d-139">string</span><span class="sxs-lookup"><span data-stu-id="22d6d-139">string</span></span> | <span data-ttu-id="22d6d-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="22d6d-140">application/json.</span></span> <span data-ttu-id="22d6d-141">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="22d6d-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="22d6d-142">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="22d6d-142">Request body</span></span>
<span data-ttu-id="22d6d-143">В теле запроса поставляем объект JSON со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="22d6d-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="22d6d-144">Параметр</span><span class="sxs-lookup"><span data-stu-id="22d6d-144">Parameter</span></span> | <span data-ttu-id="22d6d-145">Тип</span><span class="sxs-lookup"><span data-stu-id="22d6d-145">Type</span></span>    | <span data-ttu-id="22d6d-146">Описание</span><span class="sxs-lookup"><span data-stu-id="22d6d-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="22d6d-147">Comment</span><span class="sxs-lookup"><span data-stu-id="22d6d-147">Comment</span></span> |   <span data-ttu-id="22d6d-148">String</span><span class="sxs-lookup"><span data-stu-id="22d6d-148">String</span></span> |    <span data-ttu-id="22d6d-149">Комментарий для связи с действием.</span><span class="sxs-lookup"><span data-stu-id="22d6d-149">Comment to associate with the action.</span></span> <span data-ttu-id="22d6d-150">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="22d6d-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="22d6d-151">Отклик</span><span class="sxs-lookup"><span data-stu-id="22d6d-151">Response</span></span>
<span data-ttu-id="22d6d-152">В случае успешной работы этот метод возвращает 201 — созданный код ответа и действие машины [в](machineaction.md) тексте отклика.</span><span class="sxs-lookup"><span data-stu-id="22d6d-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="22d6d-153">Пример</span><span class="sxs-lookup"><span data-stu-id="22d6d-153">Example</span></span>

<span data-ttu-id="22d6d-154">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="22d6d-154">**Request**</span></span>

<span data-ttu-id="22d6d-155">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="22d6d-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/fb9ab6be3965095a09c057be7c90f0a2/collectInvestigationPackage
```

```json
{
  "Comment": "Collect forensics due to alert 1234"
}
```
