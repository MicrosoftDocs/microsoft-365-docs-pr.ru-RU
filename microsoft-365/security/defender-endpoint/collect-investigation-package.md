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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 4cf60ea73ea907be9c10b2dd9562a0ea60127f2d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289899"
---
# <a name="collect-investigation-package-api"></a><span data-ttu-id="1f39a-104">Сбор API пакета расследований</span><span class="sxs-lookup"><span data-stu-id="1f39a-104">Collect investigation package API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1f39a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1f39a-105">**Applies to:**</span></span>
- [<span data-ttu-id="1f39a-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1f39a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1f39a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1f39a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="1f39a-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="1f39a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1f39a-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="1f39a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="1f39a-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="1f39a-110">API description</span></span>

<span data-ttu-id="1f39a-111">Сбор пакета исследований с устройства.</span><span class="sxs-lookup"><span data-stu-id="1f39a-111">Collect investigation package from a device.</span></span>

## <a name="limitations"></a><span data-ttu-id="1f39a-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="1f39a-112">Limitations</span></span>

1. <span data-ttu-id="1f39a-113">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="1f39a-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="1f39a-114">Разрешения</span><span class="sxs-lookup"><span data-stu-id="1f39a-114">Permissions</span></span>

<span data-ttu-id="1f39a-115">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="1f39a-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1f39a-116">Дополнительные новости, в том числе выбор разрешений, см. в этой [ссылке: Use Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="1f39a-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="1f39a-117">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="1f39a-117">Permission type</span></span> | <span data-ttu-id="1f39a-118">Разрешение</span><span class="sxs-lookup"><span data-stu-id="1f39a-118">Permission</span></span> | <span data-ttu-id="1f39a-119">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="1f39a-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1f39a-120">Application</span><span class="sxs-lookup"><span data-stu-id="1f39a-120">Application</span></span> | <span data-ttu-id="1f39a-121">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="1f39a-121">Machine.CollectForensics</span></span> | <span data-ttu-id="1f39a-122">'Collect forensics'</span><span class="sxs-lookup"><span data-stu-id="1f39a-122">'Collect forensics'</span></span>
<span data-ttu-id="1f39a-123">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="1f39a-123">Delegated (work or school account)</span></span> | <span data-ttu-id="1f39a-124">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="1f39a-124">Machine.CollectForensics</span></span> | <span data-ttu-id="1f39a-125">'Collect forensics'</span><span class="sxs-lookup"><span data-stu-id="1f39a-125">'Collect forensics'</span></span>

> [!NOTE]
> <span data-ttu-id="1f39a-126">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="1f39a-126">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="1f39a-127">Пользователю необходимо иметь по крайней мере следующее разрешение на роль: 'Alerts Investigation' (См. [создание](user-roles.md) ролей и управление ими для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="1f39a-127">The user needs to have at least the following role permission: 'Alerts Investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="1f39a-128">Пользователь должен иметь доступ к устройству на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="1f39a-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="1f39a-129">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="1f39a-129">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/collectInvestigationPackage
```

## <a name="request-headers"></a><span data-ttu-id="1f39a-130">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="1f39a-130">Request headers</span></span>

<span data-ttu-id="1f39a-131">Имя</span><span class="sxs-lookup"><span data-stu-id="1f39a-131">Name</span></span> | <span data-ttu-id="1f39a-132">Тип</span><span class="sxs-lookup"><span data-stu-id="1f39a-132">Type</span></span> | <span data-ttu-id="1f39a-133">Описание</span><span class="sxs-lookup"><span data-stu-id="1f39a-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="1f39a-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="1f39a-134">Authorization</span></span> | <span data-ttu-id="1f39a-135">Строка</span><span class="sxs-lookup"><span data-stu-id="1f39a-135">String</span></span> | <span data-ttu-id="1f39a-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="1f39a-136">Bearer {token}.</span></span> <span data-ttu-id="1f39a-137">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="1f39a-137">**Required**.</span></span>
<span data-ttu-id="1f39a-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="1f39a-138">Content-Type</span></span> | <span data-ttu-id="1f39a-139">string</span><span class="sxs-lookup"><span data-stu-id="1f39a-139">string</span></span> | <span data-ttu-id="1f39a-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="1f39a-140">application/json.</span></span> <span data-ttu-id="1f39a-141">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="1f39a-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="1f39a-142">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="1f39a-142">Request body</span></span>

<span data-ttu-id="1f39a-143">В теле запроса поставляем объект JSON со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="1f39a-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="1f39a-144">Параметр</span><span class="sxs-lookup"><span data-stu-id="1f39a-144">Parameter</span></span> | <span data-ttu-id="1f39a-145">Тип</span><span class="sxs-lookup"><span data-stu-id="1f39a-145">Type</span></span> | <span data-ttu-id="1f39a-146">Описание</span><span class="sxs-lookup"><span data-stu-id="1f39a-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="1f39a-147">Comment</span><span class="sxs-lookup"><span data-stu-id="1f39a-147">Comment</span></span> | <span data-ttu-id="1f39a-148">String</span><span class="sxs-lookup"><span data-stu-id="1f39a-148">String</span></span> | <span data-ttu-id="1f39a-149">Комментарий для связи с действием.</span><span class="sxs-lookup"><span data-stu-id="1f39a-149">Comment to associate with the action.</span></span> <span data-ttu-id="1f39a-150">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="1f39a-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="1f39a-151">Отклик</span><span class="sxs-lookup"><span data-stu-id="1f39a-151">Response</span></span>

<span data-ttu-id="1f39a-152">В случае успешной работы этот метод возвращает 201 — созданный код ответа и действие машины [в](machineaction.md) тексте отклика.</span><span class="sxs-lookup"><span data-stu-id="1f39a-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="1f39a-153">Пример</span><span class="sxs-lookup"><span data-stu-id="1f39a-153">Example</span></span>

### <a name="request"></a><span data-ttu-id="1f39a-154">Запрос</span><span class="sxs-lookup"><span data-stu-id="1f39a-154">Request</span></span>

<span data-ttu-id="1f39a-155">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="1f39a-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/fb9ab6be3965095a09c057be7c90f0a2/collectInvestigationPackage
```

```json
{
  "Comment": "Collect forensics due to alert 1234"
}
```
