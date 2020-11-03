---
title: Общие коды ошибок REST API защитника Microsoft 365
description: Сведения о распространенных кодах ошибок REST API защитника Microsoft 365
keywords: API, ошибка, коды, распространенные ошибки, MTP, коды ошибок API
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
ms.openlocfilehash: aceb376662f2b27397aa2332f8929a57d5a3ee03
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846012"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="34794-104">Общие коды ошибок REST API защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="34794-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="34794-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="34794-105">**Applies to:**</span></span>
- <span data-ttu-id="34794-106">Защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="34794-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="34794-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть значительно изменены до выпуска.</span><span class="sxs-lookup"><span data-stu-id="34794-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="34794-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="34794-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="34794-109">Коды ошибок, перечисленные в следующей таблице, могут быть возвращены операцией для любого API-интерфейса защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34794-109">The error codes listed in the following table may be returned by an operation on any of Microsoft 365 Defender APIs.</span></span>

<span data-ttu-id="34794-110">Каждый ответ на сообщение об ошибке содержит сообщение об ошибке, которое поможет решить эту проблему.</span><span class="sxs-lookup"><span data-stu-id="34794-110">Every error response contains an error message, which can help resolving the problem.</span></span>

<span data-ttu-id="34794-111">Сообщение — это произвольный текст, который можно изменить.</span><span class="sxs-lookup"><span data-stu-id="34794-111">The message is a free text that can be changed.</span></span>

<span data-ttu-id="34794-112">В нижней части страницы можно найти примеры ответа.</span><span class="sxs-lookup"><span data-stu-id="34794-112">At the bottom of the page, you can find response examples.</span></span>

<span data-ttu-id="34794-113">Код ошибки</span><span class="sxs-lookup"><span data-stu-id="34794-113">Error code</span></span> |<span data-ttu-id="34794-114">Код состояния HTTP</span><span class="sxs-lookup"><span data-stu-id="34794-114">HTTP status code</span></span> |<span data-ttu-id="34794-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="34794-115">Message</span></span> 
:---|:---|:---
<span data-ttu-id="34794-116">бадрекуест</span><span class="sxs-lookup"><span data-stu-id="34794-116">BadRequest</span></span> | <span data-ttu-id="34794-117">Бадрекуест (400)</span><span class="sxs-lookup"><span data-stu-id="34794-117">BadRequest (400)</span></span> | <span data-ttu-id="34794-118">Общее сообщение об ошибке "ошибочный запрос".</span><span class="sxs-lookup"><span data-stu-id="34794-118">General Bad Request error message.</span></span>
<span data-ttu-id="34794-119">одатаеррор</span><span class="sxs-lookup"><span data-stu-id="34794-119">ODataError</span></span> | <span data-ttu-id="34794-120">Бадрекуест (400)</span><span class="sxs-lookup"><span data-stu-id="34794-120">BadRequest (400)</span></span> | <span data-ttu-id="34794-121">Недопустимый запрос URI OData (указана конкретная ошибка).</span><span class="sxs-lookup"><span data-stu-id="34794-121">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="34794-122">инвалидинпут</span><span class="sxs-lookup"><span data-stu-id="34794-122">InvalidInput</span></span> | <span data-ttu-id="34794-123">Бадрекуест (400)</span><span class="sxs-lookup"><span data-stu-id="34794-123">BadRequest (400)</span></span> | <span data-ttu-id="34794-124">Недопустимые входные данные {Недопустимый вход}.</span><span class="sxs-lookup"><span data-stu-id="34794-124">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="34794-125">инвалидрекуестбоди</span><span class="sxs-lookup"><span data-stu-id="34794-125">InvalidRequestBody</span></span> | <span data-ttu-id="34794-126">Бадрекуест (400)</span><span class="sxs-lookup"><span data-stu-id="34794-126">BadRequest (400)</span></span> | <span data-ttu-id="34794-127">Недопустимый текст запроса.</span><span class="sxs-lookup"><span data-stu-id="34794-127">Invalid request body.</span></span>
<span data-ttu-id="34794-128">инвалидхашвалуе</span><span class="sxs-lookup"><span data-stu-id="34794-128">InvalidHashValue</span></span> | <span data-ttu-id="34794-129">Бадрекуест (400)</span><span class="sxs-lookup"><span data-stu-id="34794-129">BadRequest (400)</span></span> | <span data-ttu-id="34794-130">Хэш-значение {недопустимый хэш} является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="34794-130">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="34794-131">инвалиддомаиннаме</span><span class="sxs-lookup"><span data-stu-id="34794-131">InvalidDomainName</span></span> | <span data-ttu-id="34794-132">Бадрекуест (400)</span><span class="sxs-lookup"><span data-stu-id="34794-132">BadRequest (400)</span></span> | <span data-ttu-id="34794-133">Доменное имя {недопустимый домен} является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="34794-133">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="34794-134">инвалидипаддресс</span><span class="sxs-lookup"><span data-stu-id="34794-134">InvalidIpAddress</span></span> | <span data-ttu-id="34794-135">Бадрекуест (400)</span><span class="sxs-lookup"><span data-stu-id="34794-135">BadRequest (400)</span></span> | <span data-ttu-id="34794-136">IP-адрес {недопустимый IP-адрес} является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="34794-136">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="34794-137">инвалидурл</span><span class="sxs-lookup"><span data-stu-id="34794-137">InvalidUrl</span></span> | <span data-ttu-id="34794-138">Бадрекуест (400)</span><span class="sxs-lookup"><span data-stu-id="34794-138">BadRequest (400)</span></span> | <span data-ttu-id="34794-139">URL {недопустимый URL-адрес} является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="34794-139">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="34794-140">максимумбатчсизиксцеедед</span><span class="sxs-lookup"><span data-stu-id="34794-140">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="34794-141">Бадрекуест (400)</span><span class="sxs-lookup"><span data-stu-id="34794-141">BadRequest (400)</span></span> | <span data-ttu-id="34794-142">Превышено максимальное значение размера пакета.</span><span class="sxs-lookup"><span data-stu-id="34794-142">Maximum batch size exceeded.</span></span> <span data-ttu-id="34794-143">Получено: {размер пакетов получен}, разрешено: {разрешен размер пакетов}.</span><span class="sxs-lookup"><span data-stu-id="34794-143">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="34794-144">миссингрекуиредпараметер</span><span class="sxs-lookup"><span data-stu-id="34794-144">MissingRequiredParameter</span></span> | <span data-ttu-id="34794-145">Бадрекуест (400)</span><span class="sxs-lookup"><span data-stu-id="34794-145">BadRequest (400)</span></span> | <span data-ttu-id="34794-146">Параметр {пропущен отсутствующий параметр}.</span><span class="sxs-lookup"><span data-stu-id="34794-146">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="34794-147">осплатформнотсуппортед</span><span class="sxs-lookup"><span data-stu-id="34794-147">OsPlatformNotSupported</span></span> | <span data-ttu-id="34794-148">Бадрекуест (400)</span><span class="sxs-lookup"><span data-stu-id="34794-148">BadRequest (400)</span></span> | <span data-ttu-id="34794-149">Платформа ОС {клиентская платформа ОС} не поддерживается для этого действия.</span><span class="sxs-lookup"><span data-stu-id="34794-149">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="34794-150">клиентверсионнотсуппортед</span><span class="sxs-lookup"><span data-stu-id="34794-150">ClientVersionNotSupported</span></span> | <span data-ttu-id="34794-151">Бадрекуест (400)</span><span class="sxs-lookup"><span data-stu-id="34794-151">BadRequest (400)</span></span> | <span data-ttu-id="34794-152">{Запрошенное действие} поддерживается в версии клиента {поддерживаемая версия клиента} и выше.</span><span class="sxs-lookup"><span data-stu-id="34794-152">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="34794-153">Не авторизован (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="34794-153">Unauthorized</span></span> | <span data-ttu-id="34794-154">Несанкционированный доступ (401)</span><span class="sxs-lookup"><span data-stu-id="34794-154">Unauthorized (401)</span></span> | <span data-ttu-id="34794-155">Несанкционированный (обычно недопустимый или просроченный заголовок авторизации).</span><span class="sxs-lookup"><span data-stu-id="34794-155">Unauthorized (usually invalid or expired authorization header).</span></span>
<span data-ttu-id="34794-156">Запрещено</span><span class="sxs-lookup"><span data-stu-id="34794-156">Forbidden</span></span> | <span data-ttu-id="34794-157">Запрещено (403)</span><span class="sxs-lookup"><span data-stu-id="34794-157">Forbidden (403)</span></span> | <span data-ttu-id="34794-158">"Запрещено" (действительный маркер, но недостаточно разрешений для действия).</span><span class="sxs-lookup"><span data-stu-id="34794-158">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="34794-159">дисабледфеатуре</span><span class="sxs-lookup"><span data-stu-id="34794-159">DisabledFeature</span></span> | <span data-ttu-id="34794-160">Запрещено (403)</span><span class="sxs-lookup"><span data-stu-id="34794-160">Forbidden (403)</span></span> | <span data-ttu-id="34794-161">Компонент клиента не включен.</span><span class="sxs-lookup"><span data-stu-id="34794-161">Tenant feature is not enabled.</span></span>
<span data-ttu-id="34794-162">дисалловедоператион</span><span class="sxs-lookup"><span data-stu-id="34794-162">DisallowedOperation</span></span> | <span data-ttu-id="34794-163">Запрещено (403)</span><span class="sxs-lookup"><span data-stu-id="34794-163">Forbidden (403)</span></span> | <span data-ttu-id="34794-164">{неразрешенная операция и причина}.</span><span class="sxs-lookup"><span data-stu-id="34794-164">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="34794-165">нотфаунд</span><span class="sxs-lookup"><span data-stu-id="34794-165">NotFound</span></span> | <span data-ttu-id="34794-166">Не найдено (404)</span><span class="sxs-lookup"><span data-stu-id="34794-166">Not Found (404)</span></span> | <span data-ttu-id="34794-167">Общее сообщение об ошибке "не найдено".</span><span class="sxs-lookup"><span data-stu-id="34794-167">General Not Found error message.</span></span>
<span data-ttu-id="34794-168">ресаурценотфаунд</span><span class="sxs-lookup"><span data-stu-id="34794-168">ResourceNotFound</span></span> | <span data-ttu-id="34794-169">Не найдено (404)</span><span class="sxs-lookup"><span data-stu-id="34794-169">Not Found (404)</span></span> | <span data-ttu-id="34794-170">Ресурс {запрошенный ресурс} не найден.</span><span class="sxs-lookup"><span data-stu-id="34794-170">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="34794-171">интерналсервереррор</span><span class="sxs-lookup"><span data-stu-id="34794-171">InternalServerError</span></span> | <span data-ttu-id="34794-172">Внутренняя ошибка сервера (500)</span><span class="sxs-lookup"><span data-stu-id="34794-172">Internal Server Error (500)</span></span> | <span data-ttu-id="34794-173">(Сообщение об ошибке не появляется, повторите операцию или свяжитесь с нами, если она не разрешена)</span><span class="sxs-lookup"><span data-stu-id="34794-173">(No error message,  retry the operation or contact us if it does not get resolved)</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="34794-174">В параметрах Body учитывается регистр</span><span class="sxs-lookup"><span data-stu-id="34794-174">Body parameters are case-sensitive</span></span>

<span data-ttu-id="34794-175">В настоящее время параметры текста сообщения чувствительны к регистру.</span><span class="sxs-lookup"><span data-stu-id="34794-175">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="34794-176">Если вы появилось сообщение об ошибке **инвалидрекуестбоди** или **миссингрекуиредпараметер** , это может быть вызвано неправильной заглавной буквой параметра или буквой нижнего регистра.</span><span class="sxs-lookup"><span data-stu-id="34794-176">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="34794-177">Рекомендуем ознакомиться со страницей документация по API и проверить, что отправленные параметры соответствуют соответствующему примеру.</span><span class="sxs-lookup"><span data-stu-id="34794-177">We recommend that you review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="34794-178">Идентификатор запроса корреляции</span><span class="sxs-lookup"><span data-stu-id="34794-178">Correlation request ID</span></span>

<span data-ttu-id="34794-179">Каждый ответ с сообщением об ошибке содержит уникальный параметр ID для отслеживания.</span><span class="sxs-lookup"><span data-stu-id="34794-179">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="34794-180">Имя свойства для этого параметра — "Target".</span><span class="sxs-lookup"><span data-stu-id="34794-180">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="34794-181">При обращении к нам об ошибке прикрепление этого идентификатора поможет найти основную причину проблемы.</span><span class="sxs-lookup"><span data-stu-id="34794-181">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="34794-182">Примеры</span><span class="sxs-lookup"><span data-stu-id="34794-182">Examples</span></span>

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

