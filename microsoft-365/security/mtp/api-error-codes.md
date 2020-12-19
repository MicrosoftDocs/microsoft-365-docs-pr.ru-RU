---
title: Общие коды ошибок REST API в Microsoft 365 Defender
description: Узнайте о распространенных кодах ошибок REST API в Microsoft 365 Defender
keywords: API, ошибка, коды, распространенные ошибки, MTP, коды ошибок api
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 0df741efb7555d587a6033acc23716e93f542d5e
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719218"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="2f9ac-104">Общие коды ошибок REST API в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2f9ac-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="2f9ac-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="2f9ac-105">**Applies to:**</span></span>

- <span data-ttu-id="2f9ac-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="2f9ac-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2f9ac-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть существенно изменены до его коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="2f9ac-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="2f9ac-109">Коды ошибок могут возвращаться операцией с любыми API Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="2f9ac-110">Каждый ответ об ошибке будет содержать сообщение об ошибке, которое поможет устранить проблему.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="2f9ac-111">В столбце сообщения об ошибке в разделе таблицы есть примеры сообщений.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="2f9ac-112">Содержимое фактических сообщений зависит от факторов, которые вызвали отклик.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="2f9ac-113">Переменное содержимое указывается в таблице угловым скобками.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="2f9ac-114">Коды ошибок</span><span class="sxs-lookup"><span data-stu-id="2f9ac-114">Error codes</span></span>

<span data-ttu-id="2f9ac-115">Код ошибки</span><span class="sxs-lookup"><span data-stu-id="2f9ac-115">Error code</span></span> | <span data-ttu-id="2f9ac-116">Код состояния HTTP</span><span class="sxs-lookup"><span data-stu-id="2f9ac-116">HTTP status code</span></span> | <span data-ttu-id="2f9ac-117">Сообщение</span><span class="sxs-lookup"><span data-stu-id="2f9ac-117">Message</span></span>
-|-|-
<span data-ttu-id="2f9ac-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="2f9ac-118">BadRequest</span></span> | <span data-ttu-id="2f9ac-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2f9ac-119">BadRequest (400)</span></span> | <span data-ttu-id="2f9ac-120">Общее сообщение об ошибке "Bad Request".</span><span class="sxs-lookup"><span data-stu-id="2f9ac-120">General Bad Request error message.</span></span>
<span data-ttu-id="2f9ac-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="2f9ac-121">ODataError</span></span> | <span data-ttu-id="2f9ac-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2f9ac-122">BadRequest (400)</span></span> | <span data-ttu-id="2f9ac-123">Недопустимый запрос URI \<the specific error is specified\> OData.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="2f9ac-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="2f9ac-124">InvalidInput</span></span> | <span data-ttu-id="2f9ac-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2f9ac-125">BadRequest (400)</span></span> | <span data-ttu-id="2f9ac-126">Недопустимый \<the invalid input\> ввод.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="2f9ac-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="2f9ac-127">InvalidRequestBody</span></span> | <span data-ttu-id="2f9ac-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2f9ac-128">BadRequest (400)</span></span> | <span data-ttu-id="2f9ac-129">Недопустимый тело запроса.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-129">Invalid request body.</span></span>
<span data-ttu-id="2f9ac-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="2f9ac-130">InvalidHashValue</span></span> | <span data-ttu-id="2f9ac-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2f9ac-131">BadRequest (400)</span></span> | <span data-ttu-id="2f9ac-132">Недопустимое значение \<the invalid hash\> hash.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="2f9ac-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="2f9ac-133">InvalidDomainName</span></span> | <span data-ttu-id="2f9ac-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2f9ac-134">BadRequest (400)</span></span> | <span data-ttu-id="2f9ac-135">Недопустимое \<the invalid domain\> доменное имя.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="2f9ac-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="2f9ac-136">InvalidIpAddress</span></span> | <span data-ttu-id="2f9ac-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2f9ac-137">BadRequest (400)</span></span> | <span data-ttu-id="2f9ac-138">НЕДОПУСТИМЫЙ \<the invalid IP\> IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="2f9ac-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="2f9ac-139">InvalidUrl</span></span> | <span data-ttu-id="2f9ac-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2f9ac-140">BadRequest (400)</span></span> | <span data-ttu-id="2f9ac-141">Недопустимый \<the invalid URL\> URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="2f9ac-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="2f9ac-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="2f9ac-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2f9ac-143">BadRequest (400)</span></span> | <span data-ttu-id="2f9ac-144">Превышен максимальный размер пакета.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="2f9ac-145">Received: \<batch size received\> , allowed: {batch size allowed}.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="2f9ac-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="2f9ac-146">MissingRequiredParameter</span></span> | <span data-ttu-id="2f9ac-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2f9ac-147">BadRequest (400)</span></span> | <span data-ttu-id="2f9ac-148">Отсутствует \<the missing parameter\> параметр.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="2f9ac-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="2f9ac-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="2f9ac-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2f9ac-150">BadRequest (400)</span></span> | <span data-ttu-id="2f9ac-151">Платформа ОС \<the client OS Platform\> не поддерживается для этого действия.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="2f9ac-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="2f9ac-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="2f9ac-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2f9ac-153">BadRequest (400)</span></span> | <span data-ttu-id="2f9ac-154">\<The requested action\> поддерживается в версии клиента \<supported client version\> и выше.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="2f9ac-155">Не авторизован (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="2f9ac-155">Unauthorized</span></span> | <span data-ttu-id="2f9ac-156">Unauthorized (401)</span><span class="sxs-lookup"><span data-stu-id="2f9ac-156">Unauthorized (401)</span></span> | <span data-ttu-id="2f9ac-157">Не авторизован (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="2f9ac-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="2f9ac-158">*Примечание. Обычно это вызвано недопустимым или просроченным заголом авторизации.*</span><span class="sxs-lookup"><span data-stu-id="2f9ac-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="2f9ac-159">Запрещено</span><span class="sxs-lookup"><span data-stu-id="2f9ac-159">Forbidden</span></span> | <span data-ttu-id="2f9ac-160">Запрещено (403)</span><span class="sxs-lookup"><span data-stu-id="2f9ac-160">Forbidden (403)</span></span> | <span data-ttu-id="2f9ac-161">Запрещено</span><span class="sxs-lookup"><span data-stu-id="2f9ac-161">Forbidden</span></span> <br /><br /><span data-ttu-id="2f9ac-162">*Примечание. Допустимый маркер, но недостаточно разрешений для действия.*</span><span class="sxs-lookup"><span data-stu-id="2f9ac-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="2f9ac-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="2f9ac-163">DisabledFeature</span></span> | <span data-ttu-id="2f9ac-164">Запрещено (403)</span><span class="sxs-lookup"><span data-stu-id="2f9ac-164">Forbidden (403)</span></span> | <span data-ttu-id="2f9ac-165">Функция клиента не включена.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="2f9ac-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="2f9ac-166">DisallowedOperation</span></span> | <span data-ttu-id="2f9ac-167">Запрещено (403)</span><span class="sxs-lookup"><span data-stu-id="2f9ac-167">Forbidden (403)</span></span> | <span data-ttu-id="2f9ac-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="2f9ac-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="2f9ac-169">NotFound</span></span> | <span data-ttu-id="2f9ac-170">Не найдено (404)</span><span class="sxs-lookup"><span data-stu-id="2f9ac-170">Not Found (404)</span></span> | <span data-ttu-id="2f9ac-171">Сообщение об ошибке "Общие не найдено".</span><span class="sxs-lookup"><span data-stu-id="2f9ac-171">General Not Found error message.</span></span>
<span data-ttu-id="2f9ac-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="2f9ac-172">ResourceNotFound</span></span> | <span data-ttu-id="2f9ac-173">Не найдено (404)</span><span class="sxs-lookup"><span data-stu-id="2f9ac-173">Not Found (404)</span></span> | <span data-ttu-id="2f9ac-174">Ресурс \<the requested resource\> не найден.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="2f9ac-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="2f9ac-175">InternalServerError</span></span> | <span data-ttu-id="2f9ac-176">Внутренняя ошибка сервера (500)</span><span class="sxs-lookup"><span data-stu-id="2f9ac-176">Internal Server Error (500)</span></span> | <span data-ttu-id="2f9ac-177">*Примечание. Если сообщение об ошибке не устранено, повторно вы можете повторить операцию или обратиться в корпорацию Майкрософт.*</span><span class="sxs-lookup"><span data-stu-id="2f9ac-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="2f9ac-178">Примеры</span><span class="sxs-lookup"><span data-stu-id="2f9ac-178">Examples</span></span>

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

## <a name="body-parameters"></a><span data-ttu-id="2f9ac-179">Параметры тела</span><span class="sxs-lookup"><span data-stu-id="2f9ac-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2f9ac-180">Параметры тела чувствительны к делу.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="2f9ac-181">Ошибка *InvalidRequestBody* или *MissingRequiredParameter* может быть вызвана опечатку.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="2f9ac-182">Просмотрите документацию по API и убедитесь, что отправленные параметры соответствуют соответствующему примеру.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="2f9ac-183">ИД отслеживания</span><span class="sxs-lookup"><span data-stu-id="2f9ac-183">Tracking ID</span></span>

<span data-ttu-id="2f9ac-184">Каждый ответ об ошибке содержит уникальный параметр ID для отслеживания.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="2f9ac-185">Имя свойства этого параметра — *target*.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="2f9ac-186">Когда мы обращаемся к нам по поводу ошибки, прикрепление этого ИД поможет нам найти первопричину проблемы.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="2f9ac-187">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="2f9ac-187">Related articles</span></span>

- [<span data-ttu-id="2f9ac-188">Обзор API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2f9ac-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="2f9ac-189">Поддерживаемые API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2f9ac-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="2f9ac-190">Доступ к API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2f9ac-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="2f9ac-191">Узнайте об ограничениях API и лицензировании</span><span class="sxs-lookup"><span data-stu-id="2f9ac-191">Learn about API limits and licensing</span></span>](api-terms.md)
