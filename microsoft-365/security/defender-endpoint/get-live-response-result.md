---
title: Получения результатов живого ответа
description: Узнайте, как получить определенный результат командной команды в прямом эфире по индексу.
keywords: apis, graph api, поддерживаемые apis, отправка в библиотеку
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d58fc87d16bb58199c95933d85752008a08a0e81
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879787"
---
#  <a name="get-live-response-results"></a><span data-ttu-id="72aa6-104">Получения результатов живого ответа</span><span class="sxs-lookup"><span data-stu-id="72aa6-104">Get live response results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="72aa6-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="72aa6-105">**Applies to:**</span></span>
- [<span data-ttu-id="72aa6-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="72aa6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="72aa6-107">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="72aa6-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="72aa6-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="72aa6-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="72aa6-109">Описание API</span><span class="sxs-lookup"><span data-stu-id="72aa6-109">API description</span></span>

<span data-ttu-id="72aa6-110">Извлекает определенный результат команды живого ответа по индексу.</span><span class="sxs-lookup"><span data-stu-id="72aa6-110">Retrieves a specific live response command result by its index.</span></span>

## <a name="limitations"></a><span data-ttu-id="72aa6-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="72aa6-111">Limitations</span></span>

1.  <span data-ttu-id="72aa6-112">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="72aa6-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="72aa6-113">Разрешения</span><span class="sxs-lookup"><span data-stu-id="72aa6-113">Permissions</span></span>

<span data-ttu-id="72aa6-114">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="72aa6-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="72aa6-115">Подробнее, в том числе о выборе разрешений, см. в [руб. Начало работы.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="72aa6-115">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

| <span data-ttu-id="72aa6-116">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="72aa6-116">Permission type</span></span>                    | <span data-ttu-id="72aa6-117">Разрешение</span><span class="sxs-lookup"><span data-stu-id="72aa6-117">Permission</span></span>           | <span data-ttu-id="72aa6-118">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="72aa6-118">Permission display name</span></span>                   |
|------------------------------------|----------------------|-------------------------------------------|
| <span data-ttu-id="72aa6-119">Приложение</span><span class="sxs-lookup"><span data-stu-id="72aa6-119">Application</span></span>                        | <span data-ttu-id="72aa6-120">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="72aa6-120">Machine.LiveResponse</span></span> | <span data-ttu-id="72aa6-121">Запуск ответа в прямом эфире на определенном компьютере</span><span class="sxs-lookup"><span data-stu-id="72aa6-121">Run live response on a specific machine</span></span> |
| <span data-ttu-id="72aa6-122">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="72aa6-122">Delegated (work or school account)</span></span> | <span data-ttu-id="72aa6-123">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="72aa6-123">Machine.LiveResponse</span></span> | <span data-ttu-id="72aa6-124">Запуск ответа в прямом эфире на определенном компьютере</span><span class="sxs-lookup"><span data-stu-id="72aa6-124">Run live response on a specific machine</span></span> |

## <a name="http-request"></a><span data-ttu-id="72aa6-125">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="72aa6-125">HTTP request</span></span>

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action
id}/GetLiveResponseResultDownloadLink(index={command-index})
```

## <a name="request-headers"></a><span data-ttu-id="72aa6-126">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="72aa6-126">Request headers</span></span>

| <span data-ttu-id="72aa6-127">Имя</span><span class="sxs-lookup"><span data-stu-id="72aa6-127">Name</span></span>      | <span data-ttu-id="72aa6-128">Тип</span><span class="sxs-lookup"><span data-stu-id="72aa6-128">Type</span></span> | <span data-ttu-id="72aa6-129">Описание</span><span class="sxs-lookup"><span data-stu-id="72aa6-129">Description</span></span>               |
|---------------|----------|-------------------------------|
| <span data-ttu-id="72aa6-130">Authorization</span><span class="sxs-lookup"><span data-stu-id="72aa6-130">Authorization</span></span> | <span data-ttu-id="72aa6-131">String</span><span class="sxs-lookup"><span data-stu-id="72aa6-131">String</span></span>   | <span data-ttu-id="72aa6-p103">Bearer {токен}. Обязательный.</span><span class="sxs-lookup"><span data-stu-id="72aa6-p103">Bearer {token}. Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="72aa6-134">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="72aa6-134">Request body</span></span>

<span data-ttu-id="72aa6-135">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="72aa6-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="72aa6-136">Отклик</span><span class="sxs-lookup"><span data-stu-id="72aa6-136">Response</span></span>

<span data-ttu-id="72aa6-137">В случае успешного результата этот метод возвращает код ответа 200 Ok с объектом, который содержит ссылку на команду, приводит к свойству *значения.*</span><span class="sxs-lookup"><span data-stu-id="72aa6-137">If successful, this method returns 200, Ok response code with object that holds the link to the command result in the *value* property.</span></span> <span data-ttu-id="72aa6-138">Эта ссылка действительна в течение 30 минут и должна быть немедленно использована для скачивания пакета в локальное хранилище.</span><span class="sxs-lookup"><span data-stu-id="72aa6-138">This link is valid for 30 minutes and should be used immediately for downloading the package to a local storage.</span></span> <span data-ttu-id="72aa6-139">Просроченная ссылка может быть повторно создана другим вызовом, и нет необходимости повторно запускать живой ответ.</span><span class="sxs-lookup"><span data-stu-id="72aa6-139">An expired link can be re-created by another call, and there is no need to run live response again.</span></span>

<span data-ttu-id="72aa6-140">*Свойства транскрипта runscript:*</span><span class="sxs-lookup"><span data-stu-id="72aa6-140">*Runscript transcript properties:*</span></span>

| <span data-ttu-id="72aa6-141">Свойство</span><span class="sxs-lookup"><span data-stu-id="72aa6-141">Property</span></span>  | <span data-ttu-id="72aa6-142">Описание</span><span class="sxs-lookup"><span data-stu-id="72aa6-142">Description</span></span>                       |
|---------------|---------------------------------------|
| <span data-ttu-id="72aa6-143">name</span><span class="sxs-lookup"><span data-stu-id="72aa6-143">name</span></span>          | <span data-ttu-id="72aa6-144">Имя исполняемой скрипта</span><span class="sxs-lookup"><span data-stu-id="72aa6-144">Executed script name</span></span>                  |
| <span data-ttu-id="72aa6-145">exit_code</span><span class="sxs-lookup"><span data-stu-id="72aa6-145">exit_code</span></span>     | <span data-ttu-id="72aa6-146">Выполненный код выхода скрипта</span><span class="sxs-lookup"><span data-stu-id="72aa6-146">Executed script exit code</span></span>             |
| <span data-ttu-id="72aa6-147">script_output</span><span class="sxs-lookup"><span data-stu-id="72aa6-147">script_output</span></span> | <span data-ttu-id="72aa6-148">Выполнение стандартных выходных данных сценариев</span><span class="sxs-lookup"><span data-stu-id="72aa6-148">Executed script standard output</span></span>       |
| <span data-ttu-id="72aa6-149">script_error</span><span class="sxs-lookup"><span data-stu-id="72aa6-149">script_error</span></span>  | <span data-ttu-id="72aa6-150">Выполнение стандартных выходных ошибок скрипта</span><span class="sxs-lookup"><span data-stu-id="72aa6-150">Executed script standard error output</span></span> |

## <a name="example"></a><span data-ttu-id="72aa6-151">Пример</span><span class="sxs-lookup"><span data-stu-id="72aa6-151">Example</span></span>

<span data-ttu-id="72aa6-152">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="72aa6-152">**Request**</span></span>

<span data-ttu-id="72aa6-153">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="72aa6-153">Here is an example of the request.</span></span>

```HTTP
GET
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/GetLiveResponseResultDownloadLink(index=0)
```

<span data-ttu-id="72aa6-154">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="72aa6-154">**Response**</span></span>

<span data-ttu-id="72aa6-155">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="72aa6-155">Here is an example of the response.</span></span>

<span data-ttu-id="72aa6-156">HTTP/1.1 200 Ok</span><span class="sxs-lookup"><span data-stu-id="72aa6-156">HTTP/1.1 200 Ok</span></span>

<span data-ttu-id="72aa6-157">Тип контента: приложение/json</span><span class="sxs-lookup"><span data-stu-id="72aa6-157">Content-type: application/json</span></span>

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "https://core.windows.net/investigation-actions-data/ID/CustomPlaybookCommandOutput/4ed5e7807ad1fe59b00b664fe06a0f07?se=2021-02-04T16%3A13%3A50Z&sp=r&sv=2019-07-07&sr=b&sig=1dYGe9rPvUlXBPvYSmr6/OLXPY98m8qWqfIQCBbyZTY%3D"
}
```

<span data-ttu-id="72aa6-158">*Содержимое файла:*</span><span class="sxs-lookup"><span data-stu-id="72aa6-158">*File content:*</span></span> 

```JSON
{
    "script_name": "minidump.ps1",
    "exit_code": 0,
    "script_output": "Transcript started, output file is C:\\ProgramData\\Microsoft\\Windows Defender Advanced Threat Protection\\Temp\\PSScriptOutputs\\PSScript_Transcript_{TRANSCRIPT_ID}.txt
C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip\n51 MB\n\u0000\u0000\u0000",
    "script_error":""
}
```

## <a name="related-topics"></a><span data-ttu-id="72aa6-159">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="72aa6-159">Related topics</span></span>

- [<span data-ttu-id="72aa6-160">Получите API действий машины</span><span class="sxs-lookup"><span data-stu-id="72aa6-160">Get machine action API</span></span>](get-machineaction-object.md)
- [<span data-ttu-id="72aa6-161">Отмена действия машины</span><span class="sxs-lookup"><span data-stu-id="72aa6-161">Cancel machine action</span></span>](cancel-machine-action.md)
- [<span data-ttu-id="72aa6-162">Запуск ответа в прямом эфире</span><span class="sxs-lookup"><span data-stu-id="72aa6-162">Run live response</span></span>](run-live-response.md) 
