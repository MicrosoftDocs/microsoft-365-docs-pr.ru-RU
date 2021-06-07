---
title: API стоп-файла и карантина
description: Узнайте, как остановить запуск файла на устройстве и удалить его в Microsoft Defender для конечной точки. См. пример.
keywords: apis, graph api, supported apis, stop and quarantine file
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
ms.openlocfilehash: ac14f1ecda2b6256dc19223869b8878e6e725b96
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771415"
---
# <a name="stop-and-quarantine-file-api"></a><span data-ttu-id="473ea-105">API стоп-файла и карантина</span><span class="sxs-lookup"><span data-stu-id="473ea-105">Stop and quarantine file API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="473ea-106">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="473ea-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="473ea-107">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="473ea-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="473ea-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="473ea-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="473ea-109">Описание API</span><span class="sxs-lookup"><span data-stu-id="473ea-109">API description</span></span>
<span data-ttu-id="473ea-110">Остановите выполнение файла на устройстве и удалите его.</span><span class="sxs-lookup"><span data-stu-id="473ea-110">Stop execution of a file on a device and delete it.</span></span>


## <a name="limitations"></a><span data-ttu-id="473ea-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="473ea-111">Limitations</span></span>
1. <span data-ttu-id="473ea-112">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="473ea-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="473ea-113">Разрешения</span><span class="sxs-lookup"><span data-stu-id="473ea-113">Permissions</span></span>
<span data-ttu-id="473ea-114">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="473ea-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="473ea-115">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="473ea-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="473ea-116">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="473ea-116">Permission type</span></span> |   <span data-ttu-id="473ea-117">Разрешение</span><span class="sxs-lookup"><span data-stu-id="473ea-117">Permission</span></span>  |   <span data-ttu-id="473ea-118">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="473ea-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="473ea-119">Приложение</span><span class="sxs-lookup"><span data-stu-id="473ea-119">Application</span></span> |   <span data-ttu-id="473ea-120">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="473ea-120">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="473ea-121">'Stop and Quarantine'</span><span class="sxs-lookup"><span data-stu-id="473ea-121">'Stop And Quarantine'</span></span>
<span data-ttu-id="473ea-122">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="473ea-122">Delegated (work or school account)</span></span> | <span data-ttu-id="473ea-123">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="473ea-123">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="473ea-124">'Stop and Quarantine'</span><span class="sxs-lookup"><span data-stu-id="473ea-124">'Stop And Quarantine'</span></span>

>[!Note]
> <span data-ttu-id="473ea-125">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="473ea-125">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="473ea-126">У пользователя должно быть по крайней мере следующее разрешение на роль: "Активные действия по исправлению" (см. дополнительные сведения о создании и управлении ролями) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="473ea-126">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="473ea-127">Пользователь должен иметь доступ к устройству на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="473ea-127">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="473ea-128">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="473ea-128">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/StopAndQuarantineFile
```

## <a name="request-headers"></a><span data-ttu-id="473ea-129">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="473ea-129">Request headers</span></span>

<span data-ttu-id="473ea-130">Имя</span><span class="sxs-lookup"><span data-stu-id="473ea-130">Name</span></span> | <span data-ttu-id="473ea-131">Тип</span><span class="sxs-lookup"><span data-stu-id="473ea-131">Type</span></span> | <span data-ttu-id="473ea-132">Описание</span><span class="sxs-lookup"><span data-stu-id="473ea-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="473ea-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="473ea-133">Authorization</span></span> | <span data-ttu-id="473ea-134">String</span><span class="sxs-lookup"><span data-stu-id="473ea-134">String</span></span> | <span data-ttu-id="473ea-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="473ea-135">Bearer {token}.</span></span> <span data-ttu-id="473ea-136">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="473ea-136">**Required**.</span></span>
<span data-ttu-id="473ea-137">Content-Type</span><span class="sxs-lookup"><span data-stu-id="473ea-137">Content-Type</span></span> | <span data-ttu-id="473ea-138">string</span><span class="sxs-lookup"><span data-stu-id="473ea-138">string</span></span> | <span data-ttu-id="473ea-139">application/json.</span><span class="sxs-lookup"><span data-stu-id="473ea-139">application/json.</span></span> <span data-ttu-id="473ea-140">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="473ea-140">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="473ea-141">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="473ea-141">Request body</span></span>
<span data-ttu-id="473ea-142">В теле запроса поставляем объект JSON со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="473ea-142">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="473ea-143">Параметр</span><span class="sxs-lookup"><span data-stu-id="473ea-143">Parameter</span></span> | <span data-ttu-id="473ea-144">Тип</span><span class="sxs-lookup"><span data-stu-id="473ea-144">Type</span></span>    | <span data-ttu-id="473ea-145">Описание</span><span class="sxs-lookup"><span data-stu-id="473ea-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="473ea-146">Comment</span><span class="sxs-lookup"><span data-stu-id="473ea-146">Comment</span></span> |   <span data-ttu-id="473ea-147">String</span><span class="sxs-lookup"><span data-stu-id="473ea-147">String</span></span> |    <span data-ttu-id="473ea-148">Комментарий для связи с действием.</span><span class="sxs-lookup"><span data-stu-id="473ea-148">Comment to associate with the action.</span></span> <span data-ttu-id="473ea-149">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="473ea-149">**Required**.</span></span>
<span data-ttu-id="473ea-150">Sha1</span><span class="sxs-lookup"><span data-stu-id="473ea-150">Sha1</span></span> |  <span data-ttu-id="473ea-151">String</span><span class="sxs-lookup"><span data-stu-id="473ea-151">String</span></span>   | <span data-ttu-id="473ea-152">Sha1 файла для остановки и карантина на устройстве.</span><span class="sxs-lookup"><span data-stu-id="473ea-152">Sha1 of the file to stop and quarantine on the device.</span></span> <span data-ttu-id="473ea-153">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="473ea-153">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="473ea-154">Отклик</span><span class="sxs-lookup"><span data-stu-id="473ea-154">Response</span></span>
<span data-ttu-id="473ea-155">В случае успешной работы этот метод возвращает 201 — созданный код ответа и действие машины [в](machineaction.md) тексте отклика.</span><span class="sxs-lookup"><span data-stu-id="473ea-155">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="473ea-156">Пример</span><span class="sxs-lookup"><span data-stu-id="473ea-156">Example</span></span>

<span data-ttu-id="473ea-157">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="473ea-157">**Request**</span></span>

<span data-ttu-id="473ea-158">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="473ea-158">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/StopAndQuarantineFile 
```

```json
{
  "Comment": "Stop and quarantine file on machine due to alert 441688558380765161_2136280442",
  "Sha1": "87662bc3d60e4200ceaf7aae249d1c343f4b83c9"
}

```
