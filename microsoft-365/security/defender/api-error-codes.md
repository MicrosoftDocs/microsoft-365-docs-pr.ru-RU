---
title: Общие Microsoft 365 API API Defender REST
description: Узнайте об общих кодах ошибок Microsoft 365 API Defender REST
keywords: api, error, codes, common errors, Microsoft 365 Defender, api error codes
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e621b79d37a2c3a22394bd51e0493334eff461c7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932885"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="c5737-104">Общие Microsoft 365 API API Defender REST</span><span class="sxs-lookup"><span data-stu-id="c5737-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c5737-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c5737-105">**Applies to:**</span></span>

- <span data-ttu-id="c5737-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c5737-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5737-107">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="c5737-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c5737-108">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="c5737-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="c5737-109">Коды ошибок могут быть возвращены операцией на любом Microsoft 365 API Defender.</span><span class="sxs-lookup"><span data-stu-id="c5737-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="c5737-110">В каждом ответе на ошибку будет содержаться сообщение об ошибке, которое поможет устранить проблему.</span><span class="sxs-lookup"><span data-stu-id="c5737-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="c5737-111">Столбец сообщения об ошибке в разделе таблицы содержит некоторые примеры сообщений.</span><span class="sxs-lookup"><span data-stu-id="c5737-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="c5737-112">Содержимое фактических сообщений зависит от факторов, которые вызвали отклик.</span><span class="sxs-lookup"><span data-stu-id="c5737-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="c5737-113">Переменное содержимое указывается в таблице угловым скобками.</span><span class="sxs-lookup"><span data-stu-id="c5737-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="c5737-114">Коды ошибок</span><span class="sxs-lookup"><span data-stu-id="c5737-114">Error codes</span></span>

<span data-ttu-id="c5737-115">Код ошибки</span><span class="sxs-lookup"><span data-stu-id="c5737-115">Error code</span></span> | <span data-ttu-id="c5737-116">Код состояния HTTP</span><span class="sxs-lookup"><span data-stu-id="c5737-116">HTTP status code</span></span> | <span data-ttu-id="c5737-117">Сообщение</span><span class="sxs-lookup"><span data-stu-id="c5737-117">Message</span></span>
-|-|-
<span data-ttu-id="c5737-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="c5737-118">BadRequest</span></span> | <span data-ttu-id="c5737-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c5737-119">BadRequest (400)</span></span> | <span data-ttu-id="c5737-120">Общее сообщение об ошибке "Плохой запрос".</span><span class="sxs-lookup"><span data-stu-id="c5737-120">General Bad Request error message.</span></span>
<span data-ttu-id="c5737-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="c5737-121">ODataError</span></span> | <span data-ttu-id="c5737-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c5737-122">BadRequest (400)</span></span> | <span data-ttu-id="c5737-123">Недействительный запрос URI OData \<the specific error is specified\> .</span><span class="sxs-lookup"><span data-stu-id="c5737-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="c5737-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="c5737-124">InvalidInput</span></span> | <span data-ttu-id="c5737-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c5737-125">BadRequest (400)</span></span> | <span data-ttu-id="c5737-126">Недействительный \<the invalid input\> вход.</span><span class="sxs-lookup"><span data-stu-id="c5737-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="c5737-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="c5737-127">InvalidRequestBody</span></span> | <span data-ttu-id="c5737-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c5737-128">BadRequest (400)</span></span> | <span data-ttu-id="c5737-129">Недействительное тело запроса.</span><span class="sxs-lookup"><span data-stu-id="c5737-129">Invalid request body.</span></span>
<span data-ttu-id="c5737-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="c5737-130">InvalidHashValue</span></span> | <span data-ttu-id="c5737-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c5737-131">BadRequest (400)</span></span> | <span data-ttu-id="c5737-132">Значение hash \<the invalid hash\> является недействительным.</span><span class="sxs-lookup"><span data-stu-id="c5737-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="c5737-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="c5737-133">InvalidDomainName</span></span> | <span data-ttu-id="c5737-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c5737-134">BadRequest (400)</span></span> | <span data-ttu-id="c5737-135">Доменное \<the invalid domain\> имя является недействительным.</span><span class="sxs-lookup"><span data-stu-id="c5737-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="c5737-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="c5737-136">InvalidIpAddress</span></span> | <span data-ttu-id="c5737-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c5737-137">BadRequest (400)</span></span> | <span data-ttu-id="c5737-138">\<the invalid IP\>IP-адрес недействителен.</span><span class="sxs-lookup"><span data-stu-id="c5737-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="c5737-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="c5737-139">InvalidUrl</span></span> | <span data-ttu-id="c5737-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c5737-140">BadRequest (400)</span></span> | <span data-ttu-id="c5737-141">\<the invalid URL\>URL-адрес недействителен.</span><span class="sxs-lookup"><span data-stu-id="c5737-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="c5737-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="c5737-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="c5737-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c5737-143">BadRequest (400)</span></span> | <span data-ttu-id="c5737-144">Максимальный размер пакета превышен.</span><span class="sxs-lookup"><span data-stu-id="c5737-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="c5737-145">Получено: \<batch size received\> , разрешено: {размер пакета разрешен}.</span><span class="sxs-lookup"><span data-stu-id="c5737-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="c5737-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="c5737-146">MissingRequiredParameter</span></span> | <span data-ttu-id="c5737-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c5737-147">BadRequest (400)</span></span> | <span data-ttu-id="c5737-148">Параметр \<the missing parameter\> отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c5737-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="c5737-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="c5737-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="c5737-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c5737-150">BadRequest (400)</span></span> | <span data-ttu-id="c5737-151">Платформа ОС \<the client OS Platform\> не поддерживается для этого действия.</span><span class="sxs-lookup"><span data-stu-id="c5737-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="c5737-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="c5737-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="c5737-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c5737-153">BadRequest (400)</span></span> | <span data-ttu-id="c5737-154">\<The requested action\> поддерживается в клиентской версии \<supported client version\> и выше.</span><span class="sxs-lookup"><span data-stu-id="c5737-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="c5737-155">Не авторизован (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="c5737-155">Unauthorized</span></span> | <span data-ttu-id="c5737-156">Несанкционированный (401)</span><span class="sxs-lookup"><span data-stu-id="c5737-156">Unauthorized (401)</span></span> | <span data-ttu-id="c5737-157">Не авторизован (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="c5737-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="c5737-158">*Примечание. Обычно это вызвано недействительным или просроченным загонщиком авторизации.*</span><span class="sxs-lookup"><span data-stu-id="c5737-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="c5737-159">Запрещено</span><span class="sxs-lookup"><span data-stu-id="c5737-159">Forbidden</span></span> | <span data-ttu-id="c5737-160">Запрет (403)</span><span class="sxs-lookup"><span data-stu-id="c5737-160">Forbidden (403)</span></span> | <span data-ttu-id="c5737-161">Запрещено</span><span class="sxs-lookup"><span data-stu-id="c5737-161">Forbidden</span></span> <br /><br /><span data-ttu-id="c5737-162">*Примечание. Допустимый маркер, но недостаточное разрешение для действия*.</span><span class="sxs-lookup"><span data-stu-id="c5737-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="c5737-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="c5737-163">DisabledFeature</span></span> | <span data-ttu-id="c5737-164">Запрет (403)</span><span class="sxs-lookup"><span data-stu-id="c5737-164">Forbidden (403)</span></span> | <span data-ttu-id="c5737-165">Функция tenant не включена.</span><span class="sxs-lookup"><span data-stu-id="c5737-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="c5737-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="c5737-166">DisallowedOperation</span></span> | <span data-ttu-id="c5737-167">Запрет (403)</span><span class="sxs-lookup"><span data-stu-id="c5737-167">Forbidden (403)</span></span> | <span data-ttu-id="c5737-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="c5737-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="c5737-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="c5737-169">NotFound</span></span> | <span data-ttu-id="c5737-170">Не найден (404)</span><span class="sxs-lookup"><span data-stu-id="c5737-170">Not Found (404)</span></span> | <span data-ttu-id="c5737-171">Сообщение об ошибке General Not Found.</span><span class="sxs-lookup"><span data-stu-id="c5737-171">General Not Found error message.</span></span>
<span data-ttu-id="c5737-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="c5737-172">ResourceNotFound</span></span> | <span data-ttu-id="c5737-173">Не найден (404)</span><span class="sxs-lookup"><span data-stu-id="c5737-173">Not Found (404)</span></span> | <span data-ttu-id="c5737-174">Ресурс \<the requested resource\> не найден.</span><span class="sxs-lookup"><span data-stu-id="c5737-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="c5737-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="c5737-175">InternalServerError</span></span> | <span data-ttu-id="c5737-176">Ошибка внутреннего сервера (500)</span><span class="sxs-lookup"><span data-stu-id="c5737-176">Internal Server Error (500)</span></span> | <span data-ttu-id="c5737-177">*Примечание. Отсутствие сообщения об ошибке, повторное повторить операцию или связаться с Microsoft, если она не будет решена*</span><span class="sxs-lookup"><span data-stu-id="c5737-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="c5737-178">Примеры</span><span class="sxs-lookup"><span data-stu-id="c5737-178">Examples</span></span>

```json
{
    "error": {
        "code": "ResourceNotFound",
        "message": "Machine 123123123 was not found",
        "target": "43f4cb08-8fac-4b65-9db1-745c2ae65f3a"
    }
}
```

```json
{
    "error": {
        "code": "InvalidRequestBody",
        "message": "Request body is incorrect",
        "target": "1fa66c0f-18bd-4133-b378-36d76f3a2ba0"
    }
}
```

## <a name="body-parameters"></a><span data-ttu-id="c5737-179">Параметры тела</span><span class="sxs-lookup"><span data-stu-id="c5737-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5737-180">Параметры тела являются чувствительными к делу.</span><span class="sxs-lookup"><span data-stu-id="c5737-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="c5737-181">Если вы испытываете *ошибку InvalidRequestBody* или *MissingRequiredParameter,* она может быть вызвана опечатка.</span><span class="sxs-lookup"><span data-stu-id="c5737-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="c5737-182">Просмотрите документацию по API и убедитесь, что представленные параметры соответствуют соответствующему примеру.</span><span class="sxs-lookup"><span data-stu-id="c5737-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="c5737-183">Отслеживание ID</span><span class="sxs-lookup"><span data-stu-id="c5737-183">Tracking ID</span></span>

<span data-ttu-id="c5737-184">Каждый ответ на ошибку содержит уникальный параметр ID для отслеживания.</span><span class="sxs-lookup"><span data-stu-id="c5737-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="c5737-185">Имя свойства этого параметра является *целевым.*</span><span class="sxs-lookup"><span data-stu-id="c5737-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="c5737-186">При контакте с нами об ошибке, присоединение этого ID поможет нам найти корневую причину проблемы.</span><span class="sxs-lookup"><span data-stu-id="c5737-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="c5737-187">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="c5737-187">Related articles</span></span>

- [<span data-ttu-id="c5737-188">Microsoft 365 Обзор API defender</span><span class="sxs-lookup"><span data-stu-id="c5737-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="c5737-189">Поддерживаемые API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c5737-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="c5737-190">Доступ к API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c5737-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="c5737-191">Узнайте о ограничениях API и лицензировании</span><span class="sxs-lookup"><span data-stu-id="c5737-191">Learn about API limits and licensing</span></span>](api-terms.md)
