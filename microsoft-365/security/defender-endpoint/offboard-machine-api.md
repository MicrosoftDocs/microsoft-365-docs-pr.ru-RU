---
title: Offboard machine API
description: Узнайте, как использовать API для отключения устройства из Microsoft Defender для конечной точки.
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
ms.openlocfilehash: e2b1114cd091c9cd42aa8e4525416f9d73358a65
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771997"
---
# <a name="offboard-machine-api"></a><span data-ttu-id="c5729-104">Offboard machine API</span><span class="sxs-lookup"><span data-stu-id="c5729-104">Offboard machine API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c5729-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c5729-105">**Applies to:**</span></span>
- [<span data-ttu-id="c5729-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c5729-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c5729-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c5729-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c5729-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="c5729-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c5729-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="c5729-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="c5729-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="c5729-110">API description</span></span>
<span data-ttu-id="c5729-111">Offboard device from Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="c5729-111">Offboard device from Defender for Endpoint.</span></span>


## <a name="limitations"></a><span data-ttu-id="c5729-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="c5729-112">Limitations</span></span>
 - <span data-ttu-id="c5729-113">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="c5729-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Machine actions note](../../includes/machineactionsnote.md)]

>[!Note]
> <span data-ttu-id="c5729-114">Этот API поддерживается в Windows 10 версии 1703 и более поздней версии или Windows Server 2019 и более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="c5729-114">This API is supported on Windows 10, version 1703 and later, or Windows Server 2019 and later.</span></span> <span data-ttu-id="c5729-115">Этот API не поддерживается на устройствах MacOS или Linux.</span><span class="sxs-lookup"><span data-stu-id="c5729-115">This API is not supported on MacOS or Linux devices.</span></span>

## <a name="permissions"></a><span data-ttu-id="c5729-116">Разрешения</span><span class="sxs-lookup"><span data-stu-id="c5729-116">Permissions</span></span>
<span data-ttu-id="c5729-117">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="c5729-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c5729-118">Дополнительные новости, в том числе выбор разрешений, см. в этой [ссылке: Use Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c5729-118">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="c5729-119">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="c5729-119">Permission type</span></span> |   <span data-ttu-id="c5729-120">Разрешение</span><span class="sxs-lookup"><span data-stu-id="c5729-120">Permission</span></span>  |   <span data-ttu-id="c5729-121">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="c5729-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c5729-122">Приложение</span><span class="sxs-lookup"><span data-stu-id="c5729-122">Application</span></span> |   <span data-ttu-id="c5729-123">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="c5729-123">Machine.Offboard</span></span> |  <span data-ttu-id="c5729-124">'Offboard machine'</span><span class="sxs-lookup"><span data-stu-id="c5729-124">'Offboard machine'</span></span>
<span data-ttu-id="c5729-125">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="c5729-125">Delegated (work or school account)</span></span> |    <span data-ttu-id="c5729-126">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="c5729-126">Machine.Offboard</span></span> |  <span data-ttu-id="c5729-127">'Offboard machine'</span><span class="sxs-lookup"><span data-stu-id="c5729-127">'Offboard machine'</span></span>

>[!Note]
> <span data-ttu-id="c5729-128">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="c5729-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="c5729-129">Пользователю требуется роль AD глобального администратора</span><span class="sxs-lookup"><span data-stu-id="c5729-129">The user needs to 'Global Admin' AD role</span></span>
>- <span data-ttu-id="c5729-130">Пользователь должен иметь доступ к устройству на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="c5729-130">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="c5729-131">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="c5729-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/offboard
```

## <a name="request-headers"></a><span data-ttu-id="c5729-132">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="c5729-132">Request headers</span></span>

<span data-ttu-id="c5729-133">Имя</span><span class="sxs-lookup"><span data-stu-id="c5729-133">Name</span></span> | <span data-ttu-id="c5729-134">Тип</span><span class="sxs-lookup"><span data-stu-id="c5729-134">Type</span></span> | <span data-ttu-id="c5729-135">Описание</span><span class="sxs-lookup"><span data-stu-id="c5729-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="c5729-136">Authorization</span><span class="sxs-lookup"><span data-stu-id="c5729-136">Authorization</span></span> | <span data-ttu-id="c5729-137">String</span><span class="sxs-lookup"><span data-stu-id="c5729-137">String</span></span> | <span data-ttu-id="c5729-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="c5729-138">Bearer {token}.</span></span> <span data-ttu-id="c5729-139">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="c5729-139">**Required**.</span></span>
<span data-ttu-id="c5729-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="c5729-140">Content-Type</span></span> | <span data-ttu-id="c5729-141">string</span><span class="sxs-lookup"><span data-stu-id="c5729-141">string</span></span> | <span data-ttu-id="c5729-142">application/json.</span><span class="sxs-lookup"><span data-stu-id="c5729-142">application/json.</span></span> <span data-ttu-id="c5729-143">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="c5729-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="c5729-144">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="c5729-144">Request body</span></span>
<span data-ttu-id="c5729-145">В теле запроса поставляем объект JSON со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="c5729-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="c5729-146">Параметр</span><span class="sxs-lookup"><span data-stu-id="c5729-146">Parameter</span></span> | <span data-ttu-id="c5729-147">Тип</span><span class="sxs-lookup"><span data-stu-id="c5729-147">Type</span></span>    | <span data-ttu-id="c5729-148">Описание</span><span class="sxs-lookup"><span data-stu-id="c5729-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="c5729-149">Comment</span><span class="sxs-lookup"><span data-stu-id="c5729-149">Comment</span></span> |   <span data-ttu-id="c5729-150">String</span><span class="sxs-lookup"><span data-stu-id="c5729-150">String</span></span> |    <span data-ttu-id="c5729-151">Комментарий для связи с действием.</span><span class="sxs-lookup"><span data-stu-id="c5729-151">Comment to associate with the action.</span></span> <span data-ttu-id="c5729-152">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="c5729-152">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="c5729-153">Отклик</span><span class="sxs-lookup"><span data-stu-id="c5729-153">Response</span></span>
<span data-ttu-id="c5729-154">В случае успешной работы этот метод возвращает 201 — созданный код ответа и действие машины [в](machineaction.md) тексте отклика.</span><span class="sxs-lookup"><span data-stu-id="c5729-154">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="c5729-155">Пример</span><span class="sxs-lookup"><span data-stu-id="c5729-155">Example</span></span>

<span data-ttu-id="c5729-156">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="c5729-156">**Request**</span></span>

<span data-ttu-id="c5729-157">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="c5729-157">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/offboard
```

```json
{
  "Comment": "Offboard machine by automation"
}
```
