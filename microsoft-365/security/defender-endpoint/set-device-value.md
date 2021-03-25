---
title: Набор API значения устройства
description: Узнайте, как указать значение устройства с помощью API Microsoft Defender для конечной точки.
keywords: apis, graph api, supported apis, tags, machine tags
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 33692ddf62153c0a6aa8f84568d69803af113bc6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185567"
---
# <a name="set-device-value-api"></a><span data-ttu-id="bc299-104">Набор API значения устройства</span><span class="sxs-lookup"><span data-stu-id="bc299-104">Set device value API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bc299-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="bc299-105">**Applies to:**</span></span>
- [<span data-ttu-id="bc299-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="bc299-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bc299-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bc299-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="bc299-108">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="bc299-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="bc299-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="bc299-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bc299-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="bc299-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="bc299-111">Описание API</span><span class="sxs-lookup"><span data-stu-id="bc299-111">API description</span></span>

<span data-ttu-id="bc299-112">Установите значение устройства определенной [машины.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="bc299-112">Set the device value of a specific [Machine](machine.md).</span></span><br>
<span data-ttu-id="bc299-113">Дополнительные [сведения см. в](tvm-assign-device-value.md) добавлении значений устройства.</span><span class="sxs-lookup"><span data-stu-id="bc299-113">See [assign device values](tvm-assign-device-value.md) for more information.</span></span>

## <a name="limitations"></a><span data-ttu-id="bc299-114">Ограничения</span><span class="sxs-lookup"><span data-stu-id="bc299-114">Limitations</span></span>

1. <span data-ttu-id="bc299-115">Вы можете размещать на устройствах последний раз в соответствии с настроенным периодом хранения.</span><span class="sxs-lookup"><span data-stu-id="bc299-115">You can post on devices last seen according to your configured retention period.</span></span>

2. <span data-ttu-id="bc299-116">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="bc299-116">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="bc299-117">Разрешения</span><span class="sxs-lookup"><span data-stu-id="bc299-117">Permissions</span></span>

<span data-ttu-id="bc299-118">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="bc299-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="bc299-119">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="bc299-119">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="bc299-120">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="bc299-120">Permission type</span></span> |    <span data-ttu-id="bc299-121">Разрешение</span><span class="sxs-lookup"><span data-stu-id="bc299-121">Permission</span></span>    |    <span data-ttu-id="bc299-122">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="bc299-122">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="bc299-123">Приложение</span><span class="sxs-lookup"><span data-stu-id="bc299-123">Application</span></span> |    <span data-ttu-id="bc299-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="bc299-124">Machine.ReadWrite.All</span></span> |    <span data-ttu-id="bc299-125">'Read and write all machine information'</span><span class="sxs-lookup"><span data-stu-id="bc299-125">'Read and write all machine information'</span></span>
<span data-ttu-id="bc299-126">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="bc299-126">Delegated (work or school account)</span></span> | <span data-ttu-id="bc299-127">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="bc299-127">Machine.ReadWrite</span></span> | <span data-ttu-id="bc299-128">'Read and write machine information'</span><span class="sxs-lookup"><span data-stu-id="bc299-128">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="bc299-129">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="bc299-129">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="bc299-130">У пользователя должно быть по крайней мере следующее разрешение на роль: "Управление параметром безопасности".</span><span class="sxs-lookup"><span data-stu-id="bc299-130">The user needs to have at least the following role permission: 'Manage security setting'.</span></span> <span data-ttu-id="bc299-131">Дополнительные сведения (см. [дополнительные сведения](user-roles.md) о создании ролей и управлении ими)</span><span class="sxs-lookup"><span data-stu-id="bc299-131">For more  (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="bc299-132">Пользователь должен иметь доступ к машине на основе параметров группы машин (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) машин).</span><span class="sxs-lookup"><span data-stu-id="bc299-132">User needs to have access to the machine, based on machine group settings (See [Create and manage machine groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="bc299-133">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="bc299-133">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{machineId}/setDeviceValue
```

## <a name="request-headers"></a><span data-ttu-id="bc299-134">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="bc299-134">Request headers</span></span>

<span data-ttu-id="bc299-135">Имя</span><span class="sxs-lookup"><span data-stu-id="bc299-135">Name</span></span> | <span data-ttu-id="bc299-136">Тип</span><span class="sxs-lookup"><span data-stu-id="bc299-136">Type</span></span> | <span data-ttu-id="bc299-137">Описание</span><span class="sxs-lookup"><span data-stu-id="bc299-137">Description</span></span>
:---|:---|:---
<span data-ttu-id="bc299-138">Авторизация</span><span class="sxs-lookup"><span data-stu-id="bc299-138">Authorization</span></span> | <span data-ttu-id="bc299-139">Строка</span><span class="sxs-lookup"><span data-stu-id="bc299-139">String</span></span> | <span data-ttu-id="bc299-140">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="bc299-140">Bearer {token}.</span></span> <span data-ttu-id="bc299-141">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="bc299-141">**Required**.</span></span>
<span data-ttu-id="bc299-142">Content-Type</span><span class="sxs-lookup"><span data-stu-id="bc299-142">Content-Type</span></span> | <span data-ttu-id="bc299-143">string</span><span class="sxs-lookup"><span data-stu-id="bc299-143">string</span></span> | <span data-ttu-id="bc299-144">application/json.</span><span class="sxs-lookup"><span data-stu-id="bc299-144">application/json.</span></span> <span data-ttu-id="bc299-145">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="bc299-145">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="bc299-146">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="bc299-146">Request body</span></span>

<span data-ttu-id="bc299-147">В теле запроса поставляем объект JSON со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="bc299-147">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="bc299-148">Параметр</span><span class="sxs-lookup"><span data-stu-id="bc299-148">Parameter</span></span> |    <span data-ttu-id="bc299-149">Тип</span><span class="sxs-lookup"><span data-stu-id="bc299-149">Type</span></span>    | <span data-ttu-id="bc299-150">Описание</span><span class="sxs-lookup"><span data-stu-id="bc299-150">Description</span></span>
:---|:---|:---
<span data-ttu-id="bc299-151">DeviceValue</span><span class="sxs-lookup"><span data-stu-id="bc299-151">DeviceValue</span></span> |    <span data-ttu-id="bc299-152">Перечисление</span><span class="sxs-lookup"><span data-stu-id="bc299-152">Enum</span></span> |    <span data-ttu-id="bc299-153">Значение устройства.</span><span class="sxs-lookup"><span data-stu-id="bc299-153">Device value.</span></span> <span data-ttu-id="bc299-154">Допустимые значения: "Нормальный", "Низкий" и "Высокий".</span><span class="sxs-lookup"><span data-stu-id="bc299-154">Allowed values are: 'Normal', 'Low' and 'High'.</span></span> <span data-ttu-id="bc299-155">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="bc299-155">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="bc299-156">Отклик</span><span class="sxs-lookup"><span data-stu-id="bc299-156">Response</span></span>

<span data-ttu-id="bc299-157">В случае успешной работы этот метод возвращает код ответа 200 — Ok и обновленный компьютер в тексте отклика.</span><span class="sxs-lookup"><span data-stu-id="bc299-157">If successful, this method returns 200 - Ok response code and the updated Machine in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="bc299-158">Пример</span><span class="sxs-lookup"><span data-stu-id="bc299-158">Example</span></span>

<span data-ttu-id="bc299-159">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="bc299-159">**Request**</span></span>

<span data-ttu-id="bc299-160">Вот пример запроса, который добавляет тег машины.</span><span class="sxs-lookup"><span data-stu-id="bc299-160">Here is an example of a request that adds machine tag.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/setDeviceValue
```

```json
{
  "DeviceValue" : "High"
}
```