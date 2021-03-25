---
title: Запуск API антивирусного сканирования
description: Используйте этот API для создания вызовов, связанных с запуском антивирусного сканирования на устройстве.
keywords: apis, api графа, поддерживаемые apis, удаление устройства из изоляции
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
ms.openlocfilehash: d0db45daa786c1a44272e4d02153af3fe658e781
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200213"
---
# <a name="run-antivirus-scan-api"></a><span data-ttu-id="04037-104">Запуск API антивирусного сканирования</span><span class="sxs-lookup"><span data-stu-id="04037-104">Run antivirus scan API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="04037-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="04037-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="04037-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="04037-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="04037-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="04037-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="04037-108">Описание API</span><span class="sxs-lookup"><span data-stu-id="04037-108">API description</span></span>
<span data-ttu-id="04037-109">Инициируйте проверку антивируса Microsoft Defender на устройстве.</span><span class="sxs-lookup"><span data-stu-id="04037-109">Initiate Microsoft Defender Antivirus scan on a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="04037-110">Ограничения</span><span class="sxs-lookup"><span data-stu-id="04037-110">Limitations</span></span>
1. <span data-ttu-id="04037-111">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="04037-111">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="04037-112">Разрешения</span><span class="sxs-lookup"><span data-stu-id="04037-112">Permissions</span></span>
<span data-ttu-id="04037-113">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="04037-113">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="04037-114">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="04037-114">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="04037-115">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="04037-115">Permission type</span></span> |   <span data-ttu-id="04037-116">Разрешение</span><span class="sxs-lookup"><span data-stu-id="04037-116">Permission</span></span>  |   <span data-ttu-id="04037-117">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="04037-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="04037-118">Application</span><span class="sxs-lookup"><span data-stu-id="04037-118">Application</span></span> |   <span data-ttu-id="04037-119">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="04037-119">Machine.Scan</span></span> |  <span data-ttu-id="04037-120">'Scan machine'</span><span class="sxs-lookup"><span data-stu-id="04037-120">'Scan machine'</span></span>
<span data-ttu-id="04037-121">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="04037-121">Delegated (work or school account)</span></span> |    <span data-ttu-id="04037-122">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="04037-122">Machine.Scan</span></span> |  <span data-ttu-id="04037-123">'Scan machine'</span><span class="sxs-lookup"><span data-stu-id="04037-123">'Scan machine'</span></span>

>[!Note]
> <span data-ttu-id="04037-124">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="04037-124">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="04037-125">У пользователя должно быть по крайней мере следующее разрешение на роль: "Активные действия по исправлению" (см. дополнительные сведения о создании и управлении ролями) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="04037-125">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="04037-126">Пользователь должен иметь доступ к устройству на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="04037-126">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="04037-127">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="04037-127">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/runAntiVirusScan
```

## <a name="request-headers"></a><span data-ttu-id="04037-128">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="04037-128">Request headers</span></span>

<span data-ttu-id="04037-129">Имя</span><span class="sxs-lookup"><span data-stu-id="04037-129">Name</span></span> | <span data-ttu-id="04037-130">Тип</span><span class="sxs-lookup"><span data-stu-id="04037-130">Type</span></span> | <span data-ttu-id="04037-131">Описание</span><span class="sxs-lookup"><span data-stu-id="04037-131">Description</span></span>
:---|:---|:---
<span data-ttu-id="04037-132">Авторизация</span><span class="sxs-lookup"><span data-stu-id="04037-132">Authorization</span></span> | <span data-ttu-id="04037-133">Строка</span><span class="sxs-lookup"><span data-stu-id="04037-133">String</span></span> | <span data-ttu-id="04037-134">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="04037-134">Bearer {token}.</span></span> <span data-ttu-id="04037-135">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="04037-135">**Required**.</span></span>
<span data-ttu-id="04037-136">Content-Type</span><span class="sxs-lookup"><span data-stu-id="04037-136">Content-Type</span></span> | <span data-ttu-id="04037-137">string</span><span class="sxs-lookup"><span data-stu-id="04037-137">string</span></span> | <span data-ttu-id="04037-138">application/json</span><span class="sxs-lookup"><span data-stu-id="04037-138">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="04037-139">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="04037-139">Request body</span></span>
<span data-ttu-id="04037-140">В теле запроса поставляем объект JSON со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="04037-140">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="04037-141">Параметр</span><span class="sxs-lookup"><span data-stu-id="04037-141">Parameter</span></span> | <span data-ttu-id="04037-142">Тип</span><span class="sxs-lookup"><span data-stu-id="04037-142">Type</span></span>    | <span data-ttu-id="04037-143">Описание</span><span class="sxs-lookup"><span data-stu-id="04037-143">Description</span></span>
:---|:---|:---
<span data-ttu-id="04037-144">Comment</span><span class="sxs-lookup"><span data-stu-id="04037-144">Comment</span></span> |   <span data-ttu-id="04037-145">String</span><span class="sxs-lookup"><span data-stu-id="04037-145">String</span></span> | <span data-ttu-id="04037-146">Комментарий для связи с действием.</span><span class="sxs-lookup"><span data-stu-id="04037-146">Comment to associate with the action.</span></span> <span data-ttu-id="04037-147">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="04037-147">**Required**.</span></span>
<span data-ttu-id="04037-148">ScanType</span><span class="sxs-lookup"><span data-stu-id="04037-148">ScanType</span></span>|   <span data-ttu-id="04037-149">Строка</span><span class="sxs-lookup"><span data-stu-id="04037-149">String</span></span>  | <span data-ttu-id="04037-150">Определяет тип сканирования.</span><span class="sxs-lookup"><span data-stu-id="04037-150">Defines the type of the Scan.</span></span> <span data-ttu-id="04037-151">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="04037-151">**Required**.</span></span>

<span data-ttu-id="04037-152">**ScanType** управляет типом сканирования для выполнения и может быть одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="04037-152">**ScanType** controls the type of scan to perform and can be one of the following:</span></span>

- <span data-ttu-id="04037-153">**Quick** — выполните быстрое сканирование на устройстве</span><span class="sxs-lookup"><span data-stu-id="04037-153">**Quick** – Perform quick scan on the device</span></span>
- <span data-ttu-id="04037-154">**Full** — выполните полное сканирование на устройстве</span><span class="sxs-lookup"><span data-stu-id="04037-154">**Full** – Perform full scan on the device</span></span>



## <a name="response"></a><span data-ttu-id="04037-155">Отклик</span><span class="sxs-lookup"><span data-stu-id="04037-155">Response</span></span>
<span data-ttu-id="04037-156">В случае успешной работы этот метод возвращает 201, созданный код ответа и _объект MachineAction_ в тексте ответа.</span><span class="sxs-lookup"><span data-stu-id="04037-156">If successful, this method returns 201, Created response code and _MachineAction_ object in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="04037-157">Пример</span><span class="sxs-lookup"><span data-stu-id="04037-157">Example</span></span>

<span data-ttu-id="04037-158">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="04037-158">**Request**</span></span>

<span data-ttu-id="04037-159">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="04037-159">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runAntiVirusScan 
```

```json
{
  "Comment": "Check machine for viruses due to alert 3212",
  "ScanType": "Full"
}
```

