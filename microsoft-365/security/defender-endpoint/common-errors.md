---
title: Распространенные ошибки API защитника Майкрософт
description: Список распространенных ошибок API Защитника Майкрософт с описаниями.
keywords: apis, api mdatp, ошибки, устранение неполадок
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
ms.openlocfilehash: ddbbe07bc477ae3a5016feb795b5bad5ed82a30a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072414"
---
# <a name="common-rest-api-error-codes"></a><span data-ttu-id="d2092-104">Коды распространенных ошибок REST API</span><span class="sxs-lookup"><span data-stu-id="d2092-104">Common REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* <span data-ttu-id="d2092-105">Коды ошибок, перечисленные в следующей таблице, могут быть возвращены операцией на любом из API Конечных точек Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="d2092-105">The error codes listed in the following table may be returned by an operation on any of Microsoft Defender for Endpoint APIs.</span></span>
* <span data-ttu-id="d2092-106">В дополнение к коду ошибки каждый ответ на ошибку содержит сообщение об ошибке, которое может помочь устранить проблему.</span><span class="sxs-lookup"><span data-stu-id="d2092-106">In addition to the error code, every error response contains an error message, which can help resolve the problem.</span></span>
* <span data-ttu-id="d2092-107">Сообщение — это бесплатный текст, который можно изменить.</span><span class="sxs-lookup"><span data-stu-id="d2092-107">The message is a free text that can be changed.</span></span>
* <span data-ttu-id="d2092-108">В нижней части страницы можно найти примеры ответов.</span><span class="sxs-lookup"><span data-stu-id="d2092-108">At the bottom of the page, you can find response examples.</span></span>

><span data-ttu-id="d2092-109">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="d2092-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d2092-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="d2092-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="d2092-111">Код ошибки</span><span class="sxs-lookup"><span data-stu-id="d2092-111">Error code</span></span> |<span data-ttu-id="d2092-112">Код состояния HTTP</span><span class="sxs-lookup"><span data-stu-id="d2092-112">HTTP status code</span></span> |<span data-ttu-id="d2092-113">Сообщение</span><span class="sxs-lookup"><span data-stu-id="d2092-113">Message</span></span> 
:---|:---|:---
<span data-ttu-id="d2092-114">BadRequest</span><span class="sxs-lookup"><span data-stu-id="d2092-114">BadRequest</span></span> | <span data-ttu-id="d2092-115">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d2092-115">BadRequest (400)</span></span> | <span data-ttu-id="d2092-116">Общее сообщение об ошибке "Плохой запрос".</span><span class="sxs-lookup"><span data-stu-id="d2092-116">General Bad Request error message.</span></span>
<span data-ttu-id="d2092-117">ODataError</span><span class="sxs-lookup"><span data-stu-id="d2092-117">ODataError</span></span> | <span data-ttu-id="d2092-118">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d2092-118">BadRequest (400)</span></span> | <span data-ttu-id="d2092-119">Недействительный запрос OData URI (указана конкретная ошибка).</span><span class="sxs-lookup"><span data-stu-id="d2092-119">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="d2092-120">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="d2092-120">InvalidInput</span></span> | <span data-ttu-id="d2092-121">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d2092-121">BadRequest (400)</span></span> | <span data-ttu-id="d2092-122">Недействительный вход {недопустимый ввод}.</span><span class="sxs-lookup"><span data-stu-id="d2092-122">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="d2092-123">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="d2092-123">InvalidRequestBody</span></span> | <span data-ttu-id="d2092-124">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d2092-124">BadRequest (400)</span></span> | <span data-ttu-id="d2092-125">Недействительное тело запроса.</span><span class="sxs-lookup"><span data-stu-id="d2092-125">Invalid request body.</span></span>
<span data-ttu-id="d2092-126">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="d2092-126">InvalidHashValue</span></span> | <span data-ttu-id="d2092-127">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d2092-127">BadRequest (400)</span></span> | <span data-ttu-id="d2092-128">Значение Hash {недействительный hash} является недействительным.</span><span class="sxs-lookup"><span data-stu-id="d2092-128">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="d2092-129">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="d2092-129">InvalidDomainName</span></span> | <span data-ttu-id="d2092-130">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d2092-130">BadRequest (400)</span></span> | <span data-ttu-id="d2092-131">Доменное имя {недействительный домен} является недействительным.</span><span class="sxs-lookup"><span data-stu-id="d2092-131">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="d2092-132">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="d2092-132">InvalidIpAddress</span></span> | <span data-ttu-id="d2092-133">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d2092-133">BadRequest (400)</span></span> | <span data-ttu-id="d2092-134">IP-адрес {недействительный IP} является недействительным.</span><span class="sxs-lookup"><span data-stu-id="d2092-134">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="d2092-135">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="d2092-135">InvalidUrl</span></span> | <span data-ttu-id="d2092-136">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d2092-136">BadRequest (400)</span></span> | <span data-ttu-id="d2092-137">URL-адрес {недопустимый URL-адрес} является недействительным.</span><span class="sxs-lookup"><span data-stu-id="d2092-137">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="d2092-138">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="d2092-138">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="d2092-139">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d2092-139">BadRequest (400)</span></span> | <span data-ttu-id="d2092-140">Максимальный размер пакета превышен.</span><span class="sxs-lookup"><span data-stu-id="d2092-140">Maximum batch size exceeded.</span></span> <span data-ttu-id="d2092-141">Получено: {размер пакета получен}, разрешено: {размер пакета разрешен}.</span><span class="sxs-lookup"><span data-stu-id="d2092-141">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="d2092-142">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="d2092-142">MissingRequiredParameter</span></span> | <span data-ttu-id="d2092-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d2092-143">BadRequest (400)</span></span> | <span data-ttu-id="d2092-144">Параметр {отсутствующий параметр} отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d2092-144">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="d2092-145">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="d2092-145">OsPlatformNotSupported</span></span> | <span data-ttu-id="d2092-146">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d2092-146">BadRequest (400)</span></span> | <span data-ttu-id="d2092-147">Платформа OS {клиентская платформа ОС} не поддерживается для этого действия.</span><span class="sxs-lookup"><span data-stu-id="d2092-147">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="d2092-148">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="d2092-148">ClientVersionNotSupported</span></span> | <span data-ttu-id="d2092-149">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d2092-149">BadRequest (400)</span></span> | <span data-ttu-id="d2092-150">{Запрашиваемая мера} поддерживается в клиентской версии {поддерживаемой клиентской версии} и выше.</span><span class="sxs-lookup"><span data-stu-id="d2092-150">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="d2092-151">Не авторизован (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="d2092-151">Unauthorized</span></span> | <span data-ttu-id="d2092-152">Несанкционированный (401)</span><span class="sxs-lookup"><span data-stu-id="d2092-152">Unauthorized (401)</span></span> | <span data-ttu-id="d2092-153">Несанкционированный (недействительный или просроченный загон авторизации).</span><span class="sxs-lookup"><span data-stu-id="d2092-153">Unauthorized (invalid or expired authorization header).</span></span>
<span data-ttu-id="d2092-154">Запрещено</span><span class="sxs-lookup"><span data-stu-id="d2092-154">Forbidden</span></span> | <span data-ttu-id="d2092-155">Запрет (403)</span><span class="sxs-lookup"><span data-stu-id="d2092-155">Forbidden (403)</span></span> | <span data-ttu-id="d2092-156">Запрет (допустимый маркер, но недостаточное разрешение для действия).</span><span class="sxs-lookup"><span data-stu-id="d2092-156">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="d2092-157">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="d2092-157">DisabledFeature</span></span> | <span data-ttu-id="d2092-158">Запрет (403)</span><span class="sxs-lookup"><span data-stu-id="d2092-158">Forbidden (403)</span></span> | <span data-ttu-id="d2092-159">Функция tenant не включена.</span><span class="sxs-lookup"><span data-stu-id="d2092-159">Tenant feature is not enabled.</span></span>
<span data-ttu-id="d2092-160">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="d2092-160">DisallowedOperation</span></span> | <span data-ttu-id="d2092-161">Запрет (403)</span><span class="sxs-lookup"><span data-stu-id="d2092-161">Forbidden (403)</span></span> | <span data-ttu-id="d2092-162">{отложенная операция и причина}.</span><span class="sxs-lookup"><span data-stu-id="d2092-162">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="d2092-163">NotFound</span><span class="sxs-lookup"><span data-stu-id="d2092-163">NotFound</span></span> | <span data-ttu-id="d2092-164">Не найден (404)</span><span class="sxs-lookup"><span data-stu-id="d2092-164">Not Found (404)</span></span> | <span data-ttu-id="d2092-165">Сообщение об ошибке General Not Found.</span><span class="sxs-lookup"><span data-stu-id="d2092-165">General Not Found error message.</span></span>
<span data-ttu-id="d2092-166">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="d2092-166">ResourceNotFound</span></span> | <span data-ttu-id="d2092-167">Не найден (404)</span><span class="sxs-lookup"><span data-stu-id="d2092-167">Not Found (404)</span></span> | <span data-ttu-id="d2092-168">Ресурс {запрашиваемом ресурсе} не найден.</span><span class="sxs-lookup"><span data-stu-id="d2092-168">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="d2092-169">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="d2092-169">InternalServerError</span></span> | <span data-ttu-id="d2092-170">Ошибка внутреннего сервера (500)</span><span class="sxs-lookup"><span data-stu-id="d2092-170">Internal Server Error (500)</span></span> | <span data-ttu-id="d2092-171">(Нет сообщения об ошибке, повторить операцию)</span><span class="sxs-lookup"><span data-stu-id="d2092-171">(No error message, retry the operation)</span></span>
<span data-ttu-id="d2092-172">TooManyRequests</span><span class="sxs-lookup"><span data-stu-id="d2092-172">TooManyRequests</span></span> | <span data-ttu-id="d2092-173">Слишком много запросов (429)</span><span class="sxs-lookup"><span data-stu-id="d2092-173">Too Many Requests (429)</span></span> | <span data-ttu-id="d2092-174">Ответ будет представлять достижение ограничения квоты либо по количеству запросов, либо по ЦП.</span><span class="sxs-lookup"><span data-stu-id="d2092-174">Response will represent reaching quota limit either by number of requests or by CPU.</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="d2092-175">Параметры тела являются чувствительными к делу</span><span class="sxs-lookup"><span data-stu-id="d2092-175">Body parameters are case-sensitive</span></span>

<span data-ttu-id="d2092-176">Представленные параметры тела в настоящее время чувствительны к делу.</span><span class="sxs-lookup"><span data-stu-id="d2092-176">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="d2092-177">Если вы испытываете **ошибки InvalidRequestBody** или **MissingRequiredParameter,** это может быть вызвано неправильным капиталом параметров или письмом нижнего уровня.</span><span class="sxs-lookup"><span data-stu-id="d2092-177">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="d2092-178">Просмотрите страницу документации API и убедитесь, что представленные параметры соответствуют соответствующему примеру.</span><span class="sxs-lookup"><span data-stu-id="d2092-178">Review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="d2092-179">ID запроса корреляции</span><span class="sxs-lookup"><span data-stu-id="d2092-179">Correlation request ID</span></span>

<span data-ttu-id="d2092-180">Каждый ответ на ошибку содержит уникальный параметр ID для отслеживания.</span><span class="sxs-lookup"><span data-stu-id="d2092-180">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="d2092-181">Имя свойства этого параметра — "target".</span><span class="sxs-lookup"><span data-stu-id="d2092-181">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="d2092-182">При контакте с нами об ошибке, присоединение этого ID поможет найти корневую причину проблемы.</span><span class="sxs-lookup"><span data-stu-id="d2092-182">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="d2092-183">Примеры</span><span class="sxs-lookup"><span data-stu-id="d2092-183">Examples</span></span>

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
