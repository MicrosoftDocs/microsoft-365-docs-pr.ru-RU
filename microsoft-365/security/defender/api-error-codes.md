---
title: Общие коды ошибок API API Defender REST 365 Defender
description: Узнайте об общих кодах ошибок API API Rest Защитника Майкрософт 365
keywords: api, error, codes, common errors, mtp, api error codes
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
ms.openlocfilehash: ab564ddb0263b501b6aca979f2148dfb5cf92758
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076694"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="db2eb-104">Общие коды ошибок API API Defender REST 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db2eb-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="db2eb-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="db2eb-105">**Applies to:**</span></span>

- <span data-ttu-id="db2eb-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="db2eb-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="db2eb-107">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="db2eb-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="db2eb-108">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="db2eb-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="db2eb-109">Коды ошибок могут быть возвращены операцией на любом из API Защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="db2eb-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="db2eb-110">В каждом ответе на ошибку будет содержаться сообщение об ошибке, которое поможет устранить проблему.</span><span class="sxs-lookup"><span data-stu-id="db2eb-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="db2eb-111">Столбец сообщения об ошибке в разделе таблицы содержит некоторые примеры сообщений.</span><span class="sxs-lookup"><span data-stu-id="db2eb-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="db2eb-112">Содержимое фактических сообщений зависит от факторов, которые вызвали отклик.</span><span class="sxs-lookup"><span data-stu-id="db2eb-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="db2eb-113">Переменное содержимое указывается в таблице угловым скобками.</span><span class="sxs-lookup"><span data-stu-id="db2eb-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="db2eb-114">Коды ошибок</span><span class="sxs-lookup"><span data-stu-id="db2eb-114">Error codes</span></span>

<span data-ttu-id="db2eb-115">Код ошибки</span><span class="sxs-lookup"><span data-stu-id="db2eb-115">Error code</span></span> | <span data-ttu-id="db2eb-116">Код состояния HTTP</span><span class="sxs-lookup"><span data-stu-id="db2eb-116">HTTP status code</span></span> | <span data-ttu-id="db2eb-117">Сообщение</span><span class="sxs-lookup"><span data-stu-id="db2eb-117">Message</span></span>
-|-|-
<span data-ttu-id="db2eb-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="db2eb-118">BadRequest</span></span> | <span data-ttu-id="db2eb-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="db2eb-119">BadRequest (400)</span></span> | <span data-ttu-id="db2eb-120">Общее сообщение об ошибке "Плохой запрос".</span><span class="sxs-lookup"><span data-stu-id="db2eb-120">General Bad Request error message.</span></span>
<span data-ttu-id="db2eb-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="db2eb-121">ODataError</span></span> | <span data-ttu-id="db2eb-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="db2eb-122">BadRequest (400)</span></span> | <span data-ttu-id="db2eb-123">Недействительный запрос URI OData \<the specific error is specified\> .</span><span class="sxs-lookup"><span data-stu-id="db2eb-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="db2eb-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="db2eb-124">InvalidInput</span></span> | <span data-ttu-id="db2eb-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="db2eb-125">BadRequest (400)</span></span> | <span data-ttu-id="db2eb-126">Недействительный \<the invalid input\> вход.</span><span class="sxs-lookup"><span data-stu-id="db2eb-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="db2eb-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="db2eb-127">InvalidRequestBody</span></span> | <span data-ttu-id="db2eb-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="db2eb-128">BadRequest (400)</span></span> | <span data-ttu-id="db2eb-129">Недействительное тело запроса.</span><span class="sxs-lookup"><span data-stu-id="db2eb-129">Invalid request body.</span></span>
<span data-ttu-id="db2eb-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="db2eb-130">InvalidHashValue</span></span> | <span data-ttu-id="db2eb-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="db2eb-131">BadRequest (400)</span></span> | <span data-ttu-id="db2eb-132">Значение hash \<the invalid hash\> является недействительным.</span><span class="sxs-lookup"><span data-stu-id="db2eb-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="db2eb-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="db2eb-133">InvalidDomainName</span></span> | <span data-ttu-id="db2eb-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="db2eb-134">BadRequest (400)</span></span> | <span data-ttu-id="db2eb-135">Доменное \<the invalid domain\> имя является недействительным.</span><span class="sxs-lookup"><span data-stu-id="db2eb-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="db2eb-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="db2eb-136">InvalidIpAddress</span></span> | <span data-ttu-id="db2eb-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="db2eb-137">BadRequest (400)</span></span> | <span data-ttu-id="db2eb-138">\<the invalid IP\>IP-адрес недействителен.</span><span class="sxs-lookup"><span data-stu-id="db2eb-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="db2eb-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="db2eb-139">InvalidUrl</span></span> | <span data-ttu-id="db2eb-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="db2eb-140">BadRequest (400)</span></span> | <span data-ttu-id="db2eb-141">\<the invalid URL\>URL-адрес недействителен.</span><span class="sxs-lookup"><span data-stu-id="db2eb-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="db2eb-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="db2eb-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="db2eb-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="db2eb-143">BadRequest (400)</span></span> | <span data-ttu-id="db2eb-144">Максимальный размер пакета превышен.</span><span class="sxs-lookup"><span data-stu-id="db2eb-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="db2eb-145">Получено: \<batch size received\> , разрешено: {размер пакета разрешен}.</span><span class="sxs-lookup"><span data-stu-id="db2eb-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="db2eb-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="db2eb-146">MissingRequiredParameter</span></span> | <span data-ttu-id="db2eb-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="db2eb-147">BadRequest (400)</span></span> | <span data-ttu-id="db2eb-148">Параметр \<the missing parameter\> отсутствует.</span><span class="sxs-lookup"><span data-stu-id="db2eb-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="db2eb-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="db2eb-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="db2eb-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="db2eb-150">BadRequest (400)</span></span> | <span data-ttu-id="db2eb-151">Платформа ОС \<the client OS Platform\> не поддерживается для этого действия.</span><span class="sxs-lookup"><span data-stu-id="db2eb-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="db2eb-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="db2eb-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="db2eb-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="db2eb-153">BadRequest (400)</span></span> | <span data-ttu-id="db2eb-154">\<The requested action\> поддерживается в клиентской версии \<supported client version\> и выше.</span><span class="sxs-lookup"><span data-stu-id="db2eb-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="db2eb-155">Не авторизован (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="db2eb-155">Unauthorized</span></span> | <span data-ttu-id="db2eb-156">Несанкционированный (401)</span><span class="sxs-lookup"><span data-stu-id="db2eb-156">Unauthorized (401)</span></span> | <span data-ttu-id="db2eb-157">Не авторизован (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="db2eb-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="db2eb-158">*Примечание. Обычно это вызвано недействительным или просроченным загонщиком авторизации.*</span><span class="sxs-lookup"><span data-stu-id="db2eb-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="db2eb-159">Запрещено</span><span class="sxs-lookup"><span data-stu-id="db2eb-159">Forbidden</span></span> | <span data-ttu-id="db2eb-160">Запрет (403)</span><span class="sxs-lookup"><span data-stu-id="db2eb-160">Forbidden (403)</span></span> | <span data-ttu-id="db2eb-161">Запрещено</span><span class="sxs-lookup"><span data-stu-id="db2eb-161">Forbidden</span></span> <br /><br /><span data-ttu-id="db2eb-162">*Примечание. Допустимый маркер, но недостаточное разрешение для действия*.</span><span class="sxs-lookup"><span data-stu-id="db2eb-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="db2eb-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="db2eb-163">DisabledFeature</span></span> | <span data-ttu-id="db2eb-164">Запрет (403)</span><span class="sxs-lookup"><span data-stu-id="db2eb-164">Forbidden (403)</span></span> | <span data-ttu-id="db2eb-165">Функция tenant не включена.</span><span class="sxs-lookup"><span data-stu-id="db2eb-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="db2eb-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="db2eb-166">DisallowedOperation</span></span> | <span data-ttu-id="db2eb-167">Запрет (403)</span><span class="sxs-lookup"><span data-stu-id="db2eb-167">Forbidden (403)</span></span> | <span data-ttu-id="db2eb-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="db2eb-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="db2eb-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="db2eb-169">NotFound</span></span> | <span data-ttu-id="db2eb-170">Не найден (404)</span><span class="sxs-lookup"><span data-stu-id="db2eb-170">Not Found (404)</span></span> | <span data-ttu-id="db2eb-171">Сообщение об ошибке General Not Found.</span><span class="sxs-lookup"><span data-stu-id="db2eb-171">General Not Found error message.</span></span>
<span data-ttu-id="db2eb-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="db2eb-172">ResourceNotFound</span></span> | <span data-ttu-id="db2eb-173">Не найден (404)</span><span class="sxs-lookup"><span data-stu-id="db2eb-173">Not Found (404)</span></span> | <span data-ttu-id="db2eb-174">Ресурс \<the requested resource\> не найден.</span><span class="sxs-lookup"><span data-stu-id="db2eb-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="db2eb-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="db2eb-175">InternalServerError</span></span> | <span data-ttu-id="db2eb-176">Ошибка внутреннего сервера (500)</span><span class="sxs-lookup"><span data-stu-id="db2eb-176">Internal Server Error (500)</span></span> | <span data-ttu-id="db2eb-177">*Примечание. Отсутствие сообщения об ошибке, повторное повторить операцию или связаться с Microsoft, если она не будет решена*</span><span class="sxs-lookup"><span data-stu-id="db2eb-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="db2eb-178">Примеры</span><span class="sxs-lookup"><span data-stu-id="db2eb-178">Examples</span></span>

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

## <a name="body-parameters"></a><span data-ttu-id="db2eb-179">Параметры тела</span><span class="sxs-lookup"><span data-stu-id="db2eb-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="db2eb-180">Параметры тела являются чувствительными к делу.</span><span class="sxs-lookup"><span data-stu-id="db2eb-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="db2eb-181">Если вы испытываете *ошибку InvalidRequestBody* или *MissingRequiredParameter,* она может быть вызвана опечатка.</span><span class="sxs-lookup"><span data-stu-id="db2eb-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="db2eb-182">Просмотрите документацию по API и убедитесь, что представленные параметры соответствуют соответствующему примеру.</span><span class="sxs-lookup"><span data-stu-id="db2eb-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="db2eb-183">Отслеживание ID</span><span class="sxs-lookup"><span data-stu-id="db2eb-183">Tracking ID</span></span>

<span data-ttu-id="db2eb-184">Каждый ответ на ошибку содержит уникальный параметр ID для отслеживания.</span><span class="sxs-lookup"><span data-stu-id="db2eb-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="db2eb-185">Имя свойства этого параметра является *целевым.*</span><span class="sxs-lookup"><span data-stu-id="db2eb-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="db2eb-186">При контакте с нами об ошибке, присоединение этого ID поможет нам найти корневую причину проблемы.</span><span class="sxs-lookup"><span data-stu-id="db2eb-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="db2eb-187">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="db2eb-187">Related articles</span></span>

- [<span data-ttu-id="db2eb-188">Обзор API защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="db2eb-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="db2eb-189">Поддерживаемые API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db2eb-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="db2eb-190">Доступ к API защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="db2eb-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="db2eb-191">Узнайте о ограничениях API и лицензировании</span><span class="sxs-lookup"><span data-stu-id="db2eb-191">Learn about API limits and licensing</span></span>](api-terms.md)