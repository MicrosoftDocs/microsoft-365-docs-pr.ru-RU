---
title: Отправка или обновление API индикатора
description: Узнайте, как использовать API отправки или обновления индикатора для отправки или обновления нового объекта индикатора в Microsoft Defender для конечной точки.
keywords: apis, graph api, supported apis, submit, ti, indicator, update
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
ms.openlocfilehash: 42bab0a9d20d5e1ef78b98b3538cef209240d890
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187360"
---
# <a name="submit-or-update-indicator-api"></a><span data-ttu-id="13442-104">Отправка или обновление API индикатора</span><span class="sxs-lookup"><span data-stu-id="13442-104">Submit or Update Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="13442-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="13442-105">**Applies to:**</span></span>
- [<span data-ttu-id="13442-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="13442-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="13442-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="13442-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="13442-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="13442-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="13442-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="13442-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="13442-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="13442-110">API description</span></span>
<span data-ttu-id="13442-111">Отправка или обновление новой сущности [индикатора.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="13442-111">Submits or Updates new [Indicator](ti-indicator.md) entity.</span></span>
<br><span data-ttu-id="13442-112">Нотация CIDR для ИП не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="13442-112">CIDR notation for IPs is not supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="13442-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="13442-113">Limitations</span></span>
1. <span data-ttu-id="13442-114">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="13442-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="13442-115">Существует ограничение в 15 000 активных индикаторов на одного клиента.</span><span class="sxs-lookup"><span data-stu-id="13442-115">There is a limit of 15,000 active indicators per tenant.</span></span> 


## <a name="permissions"></a><span data-ttu-id="13442-116">Разрешения</span><span class="sxs-lookup"><span data-stu-id="13442-116">Permissions</span></span>
<span data-ttu-id="13442-117">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="13442-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="13442-118">Дополнительные новости, в том числе выбор разрешений, см. в [руб. Начало работы](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="13442-118">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="13442-119">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="13442-119">Permission type</span></span> |   <span data-ttu-id="13442-120">Разрешение</span><span class="sxs-lookup"><span data-stu-id="13442-120">Permission</span></span>  |   <span data-ttu-id="13442-121">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="13442-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="13442-122">Приложение</span><span class="sxs-lookup"><span data-stu-id="13442-122">Application</span></span> |   <span data-ttu-id="13442-123">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="13442-123">Ti.ReadWrite</span></span> |  <span data-ttu-id="13442-124">'Read and write Indicators'</span><span class="sxs-lookup"><span data-stu-id="13442-124">'Read and write Indicators'</span></span>
<span data-ttu-id="13442-125">Приложение</span><span class="sxs-lookup"><span data-stu-id="13442-125">Application</span></span> |   <span data-ttu-id="13442-126">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="13442-126">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="13442-127">'Read and write All Indicators'</span><span class="sxs-lookup"><span data-stu-id="13442-127">'Read and write All Indicators'</span></span>
<span data-ttu-id="13442-128">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="13442-128">Delegated (work or school account)</span></span> |    <span data-ttu-id="13442-129">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="13442-129">Ti.ReadWrite</span></span> |  <span data-ttu-id="13442-130">'Read and write Indicators'</span><span class="sxs-lookup"><span data-stu-id="13442-130">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="13442-131">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="13442-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="13442-132">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="13442-132">Request headers</span></span>

<span data-ttu-id="13442-133">Имя</span><span class="sxs-lookup"><span data-stu-id="13442-133">Name</span></span> | <span data-ttu-id="13442-134">Тип</span><span class="sxs-lookup"><span data-stu-id="13442-134">Type</span></span> | <span data-ttu-id="13442-135">Описание</span><span class="sxs-lookup"><span data-stu-id="13442-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="13442-136">Авторизация</span><span class="sxs-lookup"><span data-stu-id="13442-136">Authorization</span></span> | <span data-ttu-id="13442-137">Строка</span><span class="sxs-lookup"><span data-stu-id="13442-137">String</span></span> | <span data-ttu-id="13442-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="13442-138">Bearer {token}.</span></span> <span data-ttu-id="13442-139">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="13442-139">**Required**.</span></span>
<span data-ttu-id="13442-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="13442-140">Content-Type</span></span> | <span data-ttu-id="13442-141">string</span><span class="sxs-lookup"><span data-stu-id="13442-141">string</span></span> | <span data-ttu-id="13442-142">application/json.</span><span class="sxs-lookup"><span data-stu-id="13442-142">application/json.</span></span> <span data-ttu-id="13442-143">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="13442-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="13442-144">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="13442-144">Request body</span></span>
<span data-ttu-id="13442-145">В теле запроса поставляем объект JSON со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="13442-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="13442-146">Параметр</span><span class="sxs-lookup"><span data-stu-id="13442-146">Parameter</span></span> | <span data-ttu-id="13442-147">Тип</span><span class="sxs-lookup"><span data-stu-id="13442-147">Type</span></span>    | <span data-ttu-id="13442-148">Описание</span><span class="sxs-lookup"><span data-stu-id="13442-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="13442-149">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="13442-149">indicatorValue</span></span> | <span data-ttu-id="13442-150">Строка</span><span class="sxs-lookup"><span data-stu-id="13442-150">String</span></span> | <span data-ttu-id="13442-151">Удостоверение сущности [индикатора.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="13442-151">Identity of the [Indicator](ti-indicator.md) entity.</span></span> <span data-ttu-id="13442-152">**Required**</span><span class="sxs-lookup"><span data-stu-id="13442-152">**Required**</span></span>
<span data-ttu-id="13442-153">indicatorType</span><span class="sxs-lookup"><span data-stu-id="13442-153">indicatorType</span></span> | <span data-ttu-id="13442-154">Перечисление</span><span class="sxs-lookup"><span data-stu-id="13442-154">Enum</span></span> | <span data-ttu-id="13442-155">Тип индикатора.</span><span class="sxs-lookup"><span data-stu-id="13442-155">Type of the indicator.</span></span> <span data-ttu-id="13442-156">Возможные значения: "FileSha1", "FileSha256", "IpAddress", "DomainName" и "URL".</span><span class="sxs-lookup"><span data-stu-id="13442-156">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span> <span data-ttu-id="13442-157">**Required**</span><span class="sxs-lookup"><span data-stu-id="13442-157">**Required**</span></span>
<span data-ttu-id="13442-158">action</span><span class="sxs-lookup"><span data-stu-id="13442-158">action</span></span> | <span data-ttu-id="13442-159">Перечисление</span><span class="sxs-lookup"><span data-stu-id="13442-159">Enum</span></span> | <span data-ttu-id="13442-160">Действие, которое будет принято, если индикатор будет обнаружен в организации.</span><span class="sxs-lookup"><span data-stu-id="13442-160">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="13442-161">Возможные значения: "Alert", "AlertAndBlock" и "Allowed".</span><span class="sxs-lookup"><span data-stu-id="13442-161">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span> <span data-ttu-id="13442-162">**Required**</span><span class="sxs-lookup"><span data-stu-id="13442-162">**Required**</span></span>
<span data-ttu-id="13442-163">приложение</span><span class="sxs-lookup"><span data-stu-id="13442-163">application</span></span> | <span data-ttu-id="13442-164">Строка</span><span class="sxs-lookup"><span data-stu-id="13442-164">String</span></span> | <span data-ttu-id="13442-165">Приложение, связанное с индикатором.</span><span class="sxs-lookup"><span data-stu-id="13442-165">The application associated with the indicator.</span></span> <span data-ttu-id="13442-166">**Необязательное**</span><span class="sxs-lookup"><span data-stu-id="13442-166">**Optional**</span></span>
<span data-ttu-id="13442-167">title</span><span class="sxs-lookup"><span data-stu-id="13442-167">title</span></span> | <span data-ttu-id="13442-168">Строка</span><span class="sxs-lookup"><span data-stu-id="13442-168">String</span></span> | <span data-ttu-id="13442-169">Название оповещений индикатора.</span><span class="sxs-lookup"><span data-stu-id="13442-169">Indicator alert title.</span></span> <span data-ttu-id="13442-170">**Required**</span><span class="sxs-lookup"><span data-stu-id="13442-170">**Required**</span></span>
<span data-ttu-id="13442-171">description</span><span class="sxs-lookup"><span data-stu-id="13442-171">description</span></span> | <span data-ttu-id="13442-172">Строка</span><span class="sxs-lookup"><span data-stu-id="13442-172">String</span></span> | <span data-ttu-id="13442-173">Описание индикатора.</span><span class="sxs-lookup"><span data-stu-id="13442-173">Description of the indicator.</span></span> <span data-ttu-id="13442-174">**Required**</span><span class="sxs-lookup"><span data-stu-id="13442-174">**Required**</span></span>
<span data-ttu-id="13442-175">expirationTime</span><span class="sxs-lookup"><span data-stu-id="13442-175">expirationTime</span></span> | <span data-ttu-id="13442-176">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="13442-176">DateTimeOffset</span></span> | <span data-ttu-id="13442-177">Срок действия индикатора.</span><span class="sxs-lookup"><span data-stu-id="13442-177">The expiration time of the indicator.</span></span> <span data-ttu-id="13442-178">**Необязательное**</span><span class="sxs-lookup"><span data-stu-id="13442-178">**Optional**</span></span>
<span data-ttu-id="13442-179">severity</span><span class="sxs-lookup"><span data-stu-id="13442-179">severity</span></span> | <span data-ttu-id="13442-180">Перечисление</span><span class="sxs-lookup"><span data-stu-id="13442-180">Enum</span></span> | <span data-ttu-id="13442-181">Серьезность индикатора.</span><span class="sxs-lookup"><span data-stu-id="13442-181">The severity of the indicator.</span></span> <span data-ttu-id="13442-182">Возможные значения: "Информационная", "Низкая", "Средняя" и "Высокая".</span><span class="sxs-lookup"><span data-stu-id="13442-182">possible values are: "Informational", "Low", "Medium" and "High".</span></span> <span data-ttu-id="13442-183">**Необязательное**</span><span class="sxs-lookup"><span data-stu-id="13442-183">**Optional**</span></span>
<span data-ttu-id="13442-184">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="13442-184">recommendedActions</span></span> | <span data-ttu-id="13442-185">Строка</span><span class="sxs-lookup"><span data-stu-id="13442-185">String</span></span> | <span data-ttu-id="13442-186">Предупреждение индикатора TI рекомендуемые действия.</span><span class="sxs-lookup"><span data-stu-id="13442-186">TI indicator alert recommended actions.</span></span> <span data-ttu-id="13442-187">**Необязательное**</span><span class="sxs-lookup"><span data-stu-id="13442-187">**Optional**</span></span>
<span data-ttu-id="13442-188">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="13442-188">rbacGroupNames</span></span> | <span data-ttu-id="13442-189">Строка</span><span class="sxs-lookup"><span data-stu-id="13442-189">String</span></span> | <span data-ttu-id="13442-190">Разделенный запятой список имен групп RBAC, к который будет применен индикатор.</span><span class="sxs-lookup"><span data-stu-id="13442-190">Comma-separated list of RBAC group names the indicator would be applied to.</span></span> <span data-ttu-id="13442-191">**Необязательное**</span><span class="sxs-lookup"><span data-stu-id="13442-191">**Optional**</span></span>


## <a name="response"></a><span data-ttu-id="13442-192">Отклик</span><span class="sxs-lookup"><span data-stu-id="13442-192">Response</span></span>
- <span data-ttu-id="13442-193">В случае успешной работы этот метод возвращает 200 — код ответа OK и созданную /обновленную сущность [Индикатора](ti-indicator.md) в тексте ответа.</span><span class="sxs-lookup"><span data-stu-id="13442-193">If successful, this method returns 200 - OK response code and the created / updated [Indicator](ti-indicator.md) entity in the response body.</span></span>
- <span data-ttu-id="13442-194">Если не удалось: этот метод возвращает 400 — Bad Request.</span><span class="sxs-lookup"><span data-stu-id="13442-194">If not successful: this method return 400 - Bad Request.</span></span> <span data-ttu-id="13442-195">Плохой запрос обычно указывает неправильное тело.</span><span class="sxs-lookup"><span data-stu-id="13442-195">Bad request usually indicates incorrect body.</span></span>

## <a name="example"></a><span data-ttu-id="13442-196">Пример</span><span class="sxs-lookup"><span data-stu-id="13442-196">Example</span></span>

<span data-ttu-id="13442-197">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="13442-197">**Request**</span></span>

<span data-ttu-id="13442-198">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="13442-198">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

```json
{
    "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
    "indicatorType": "FileSha1",
    "title": "test",
    "application": "demo-test",
    "expirationTime": "2020-12-12T00:00:00Z",
    "action": "AlertAndBlock",
    "severity": "Informational",
    "description": "test",
    "recommendedActions": "nothing",
    "rbacGroupNames": ["group1", "group2"]
}
```

## <a name="related-topic"></a><span data-ttu-id="13442-199">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="13442-199">Related topic</span></span>
- [<span data-ttu-id="13442-200">Управление индикаторами</span><span class="sxs-lookup"><span data-stu-id="13442-200">Manage indicators</span></span>](manage-indicators.md)
