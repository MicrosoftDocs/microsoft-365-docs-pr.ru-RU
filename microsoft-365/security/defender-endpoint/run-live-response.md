---
title: Запуск команд живого ответа на устройстве
description: Узнайте, как запустить последовательность команд живого ответа на устройстве.
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
ms.openlocfilehash: 2a7daf18b1a1d791e7b92ded0a6b839bba1fd4c2
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879764"
---
#  <a name="run-live-response-commands-on-a-device"></a><span data-ttu-id="2c06a-104">Запуск команд живого ответа на устройстве</span><span class="sxs-lookup"><span data-stu-id="2c06a-104">Run live response commands on a device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2c06a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="2c06a-105">**Applies to:**</span></span>
- [<span data-ttu-id="2c06a-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="2c06a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)


[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="2c06a-107">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="2c06a-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2c06a-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="2c06a-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="2c06a-109">Описание API</span><span class="sxs-lookup"><span data-stu-id="2c06a-109">API description</span></span>

<span data-ttu-id="2c06a-110">Выполняет последовательность команд живого ответа на устройстве</span><span class="sxs-lookup"><span data-stu-id="2c06a-110">Runs a sequence of live response commands on a device</span></span>

## <a name="limitations"></a><span data-ttu-id="2c06a-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="2c06a-111">Limitations</span></span>

1.  <span data-ttu-id="2c06a-112">Ограничения скорости для этого API : 10 вызовов в минуту (дополнительные запросы отвечают http 429).</span><span class="sxs-lookup"><span data-stu-id="2c06a-112">Rate limitations for this API are 10 calls per minute (additional requests are responded with HTTP 429).</span></span>

2.  <span data-ttu-id="2c06a-113">25 одновременно запущенных сеансов (запросы, превышающие ограничение регулирования, получат ответ "429 - слишком много запросов").</span><span class="sxs-lookup"><span data-stu-id="2c06a-113">25 concurrently running sessions (requests exceeding the throttling limit will receive a "429 - Too many requests" response).</span></span>

3.  <span data-ttu-id="2c06a-114">Если машина недоступна, сеанс будет стоять в очереди до 3 дней.</span><span class="sxs-lookup"><span data-stu-id="2c06a-114">If the machine is not available, the session will be queued for up to 3 days.</span></span>

4.  <span data-ttu-id="2c06a-115">Время ото дня команд runScript через 10 минут.</span><span class="sxs-lookup"><span data-stu-id="2c06a-115">RunScript command timeouts after 10 minutes.</span></span>

5.  <span data-ttu-id="2c06a-116">При сбойе команды живого ответа все последующие действия не будут выполнены.</span><span class="sxs-lookup"><span data-stu-id="2c06a-116">When a live response command fails all followed actions will not be executed.</span></span>

## <a name="permissions"></a><span data-ttu-id="2c06a-117">Разрешения</span><span class="sxs-lookup"><span data-stu-id="2c06a-117">Permissions</span></span>

<span data-ttu-id="2c06a-118">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="2c06a-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2c06a-119">Подробнее, в том числе о выборе разрешений, см. в [руб. Начало работы.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2c06a-119">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

| <span data-ttu-id="2c06a-120">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="2c06a-120">Permission type</span></span>                    | <span data-ttu-id="2c06a-121">Разрешение</span><span class="sxs-lookup"><span data-stu-id="2c06a-121">Permission</span></span>           | <span data-ttu-id="2c06a-122">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="2c06a-122">Permission display name</span></span>                   |
|------------------------------------|----------------------|-------------------------------------------|
| <span data-ttu-id="2c06a-123">Приложение</span><span class="sxs-lookup"><span data-stu-id="2c06a-123">Application</span></span>                        | <span data-ttu-id="2c06a-124">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="2c06a-124">Machine.LiveResponse</span></span> | <span data-ttu-id="2c06a-125">Запуск ответа в прямом эфире на определенном компьютере</span><span class="sxs-lookup"><span data-stu-id="2c06a-125">Run live response on a specific machine</span></span> |
| <span data-ttu-id="2c06a-126">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="2c06a-126">Delegated (work or school account)</span></span> | <span data-ttu-id="2c06a-127">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="2c06a-127">Machine.LiveResponse</span></span> | <span data-ttu-id="2c06a-128">Запуск ответа в прямом эфире на определенном компьютере</span><span class="sxs-lookup"><span data-stu-id="2c06a-128">Run live response on a specific machine</span></span> |

## <a name="http-request"></a><span data-ttu-id="2c06a-129">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="2c06a-129">HTTP request</span></span>

```HTTP
POST
https://api.securitycenter.microsoft.com/API/machines/{machine_id}/runliveresponse
```

## <a name="request-headers"></a><span data-ttu-id="2c06a-130">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="2c06a-130">Request headers</span></span>

| <span data-ttu-id="2c06a-131">Имя</span><span class="sxs-lookup"><span data-stu-id="2c06a-131">Name</span></span>      | <span data-ttu-id="2c06a-132">Тип</span><span class="sxs-lookup"><span data-stu-id="2c06a-132">Type</span></span> | <span data-ttu-id="2c06a-133">Описание</span><span class="sxs-lookup"><span data-stu-id="2c06a-133">Description</span></span>                 |
|---------------|----------|---------------------------------|
| <span data-ttu-id="2c06a-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="2c06a-134">Authorization</span></span> | <span data-ttu-id="2c06a-135">String</span><span class="sxs-lookup"><span data-stu-id="2c06a-135">String</span></span>   | <span data-ttu-id="2c06a-136">Bearer\<token>\.</span><span class="sxs-lookup"><span data-stu-id="2c06a-136">Bearer\<token>\.</span></span> <span data-ttu-id="2c06a-137">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="2c06a-137">Required.</span></span>   |
| <span data-ttu-id="2c06a-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="2c06a-138">Content-Type</span></span>  | <span data-ttu-id="2c06a-139">string</span><span class="sxs-lookup"><span data-stu-id="2c06a-139">string</span></span>   | <span data-ttu-id="2c06a-p104">application/json. Обязательный.</span><span class="sxs-lookup"><span data-stu-id="2c06a-p104">application/json. Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="2c06a-142">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="2c06a-142">Request body</span></span>

| <span data-ttu-id="2c06a-143">Параметр</span><span class="sxs-lookup"><span data-stu-id="2c06a-143">Parameter</span></span> | <span data-ttu-id="2c06a-144">Тип</span><span class="sxs-lookup"><span data-stu-id="2c06a-144">Type</span></span> | <span data-ttu-id="2c06a-145">Описание</span><span class="sxs-lookup"><span data-stu-id="2c06a-145">Description</span></span>                                                        |
|---------------|----------|------------------------------------------------------------------------|
| <span data-ttu-id="2c06a-146">Comment</span><span class="sxs-lookup"><span data-stu-id="2c06a-146">Comment</span></span>       | <span data-ttu-id="2c06a-147">String</span><span class="sxs-lookup"><span data-stu-id="2c06a-147">String</span></span>   | <span data-ttu-id="2c06a-148">Комментарий для связи с действием.</span><span class="sxs-lookup"><span data-stu-id="2c06a-148">Comment to associate with the action.</span></span>                                 |
| <span data-ttu-id="2c06a-149">Команды</span><span class="sxs-lookup"><span data-stu-id="2c06a-149">Commands</span></span>      | <span data-ttu-id="2c06a-150">Массив</span><span class="sxs-lookup"><span data-stu-id="2c06a-150">Array</span></span>    | <span data-ttu-id="2c06a-151">Команды для запуска.</span><span class="sxs-lookup"><span data-stu-id="2c06a-151">Commands to run.</span></span> <span data-ttu-id="2c06a-152">Допустимые значения: PutFile, RunScript, GetFile.</span><span class="sxs-lookup"><span data-stu-id="2c06a-152">Allowed values are PutFile, RunScript, GetFile.</span></span> |

<span data-ttu-id="2c06a-153">Команды:</span><span class="sxs-lookup"><span data-stu-id="2c06a-153">Commands:</span></span>

| <span data-ttu-id="2c06a-154">Тип команды</span><span class="sxs-lookup"><span data-stu-id="2c06a-154">Command Type</span></span> | <span data-ttu-id="2c06a-155">Параметры</span><span class="sxs-lookup"><span data-stu-id="2c06a-155">Parameters</span></span>                                                                          | <span data-ttu-id="2c06a-156">Описание</span><span class="sxs-lookup"><span data-stu-id="2c06a-156">Description</span></span>                                                                                                                      |
|------------------|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="2c06a-157">PutFile</span><span class="sxs-lookup"><span data-stu-id="2c06a-157">PutFile</span></span>      | <span data-ttu-id="2c06a-158">Клавиша: FileName</span><span class="sxs-lookup"><span data-stu-id="2c06a-158">Key: FileName</span></span>  <br><br>  <span data-ttu-id="2c06a-159">Значение: \<file name\></span><span class="sxs-lookup"><span data-stu-id="2c06a-159">Value: \<file name\></span></span>                                                                          | <span data-ttu-id="2c06a-160">Помещает файл из библиотеки на устройство.</span><span class="sxs-lookup"><span data-stu-id="2c06a-160">Puts a file from the library to the device.</span></span> <span data-ttu-id="2c06a-161">Файлы сохраняются в рабочей папке и удаляются при перезапуске устройства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2c06a-161">Files are saved in a working folder and are deleted when the device restarts by default.</span></span>
| <span data-ttu-id="2c06a-162">RunScript</span><span class="sxs-lookup"><span data-stu-id="2c06a-162">RunScript</span></span>    | <span data-ttu-id="2c06a-163">Key: ScriptName</span><span class="sxs-lookup"><span data-stu-id="2c06a-163">Key: ScriptName</span></span><br><span data-ttu-id="2c06a-164">Значение: \<Script from library\></span><span class="sxs-lookup"><span data-stu-id="2c06a-164">Value: \<Script from library\></span></span> <br><br> <span data-ttu-id="2c06a-165">Key: Args</span><span class="sxs-lookup"><span data-stu-id="2c06a-165">Key: Args</span></span>  <br> <span data-ttu-id="2c06a-166">Значение: \<Script arguments\></span><span class="sxs-lookup"><span data-stu-id="2c06a-166">Value: \<Script arguments\></span></span>                          | <span data-ttu-id="2c06a-167">Запускает скрипт из библиотеки на устройстве.</span><span class="sxs-lookup"><span data-stu-id="2c06a-167">Runs a script from the library on a device.</span></span>    <br><br>  <span data-ttu-id="2c06a-168">Параметр Args передается в скрипт.</span><span class="sxs-lookup"><span data-stu-id="2c06a-168">The Args parameter is passed to your script.</span></span> <br><br> <span data-ttu-id="2c06a-169">Время ото дня через 10 минут.</span><span class="sxs-lookup"><span data-stu-id="2c06a-169">Timeouts after 10 minutes.</span></span>     
| <span data-ttu-id="2c06a-170">GetFile</span><span class="sxs-lookup"><span data-stu-id="2c06a-170">GetFile</span></span>      | <span data-ttu-id="2c06a-171">Ключ. Путь</span><span class="sxs-lookup"><span data-stu-id="2c06a-171">Key: Path</span></span> <br> <span data-ttu-id="2c06a-172">Значение: \<File path\></span><span class="sxs-lookup"><span data-stu-id="2c06a-172">Value: \<File path\></span></span>                                                        | <span data-ttu-id="2c06a-173">Сбор файла с устройства.</span><span class="sxs-lookup"><span data-stu-id="2c06a-173">Collect file from a device.</span></span> <span data-ttu-id="2c06a-174">ПРИМЕЧАНИЕ. Необходимо избежать отщепок на пути.</span><span class="sxs-lookup"><span data-stu-id="2c06a-174">NOTE: Backslashes in path must be escaped.</span></span>                                                                      |

## <a name="response"></a><span data-ttu-id="2c06a-175">Отклик</span><span class="sxs-lookup"><span data-stu-id="2c06a-175">Response</span></span>

-   <span data-ttu-id="2c06a-176">В случае успеха этот метод возвращает 200, Ок.</span><span class="sxs-lookup"><span data-stu-id="2c06a-176">If successful, this method returns 200, Ok.</span></span>
    <span data-ttu-id="2c06a-177">Сущность действия.</span><span class="sxs-lookup"><span data-stu-id="2c06a-177">Action entity.</span></span> <span data-ttu-id="2c06a-178">Если машина с указанным ИД не найдена - 404 Не найдено.</span><span class="sxs-lookup"><span data-stu-id="2c06a-178">If machine with the specified ID was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="2c06a-179">Пример</span><span class="sxs-lookup"><span data-stu-id="2c06a-179">Example</span></span>

<span data-ttu-id="2c06a-180">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="2c06a-180">**Request**</span></span>

<span data-ttu-id="2c06a-181">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="2c06a-181">Here is an example of the request.</span></span>

```HTTP

POST
https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runliveresponse

```
<span data-ttu-id="2c06a-182">**JSON**</span><span class="sxs-lookup"><span data-stu-id="2c06a-182">**JSON**</span></span>

```JSON
{
   "Commands":[
      {
         "type":"RunScript",
         "params":[
            {
               "key":"ScriptName",
               "value":"minidump.ps1"
            },
            {
               "key":"Args",
               "value":"OfficeClickToRun"
            }

         ]
      },
      {
         "type":"GetFile",
         "params":[
            {
               "key":"Path",
               "value":"C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
            }
         ]
      }
   ],
   "Comment":"Testing Live Response API"
}
```

<span data-ttu-id="2c06a-183">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="2c06a-183">**Response**</span></span>

<span data-ttu-id="2c06a-184">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="2c06a-184">Here is an example of the response.</span></span>

```HTTP
HTTP/1.1 200 Ok
```

<span data-ttu-id="2c06a-185">Тип контента: приложение/json</span><span class="sxs-lookup"><span data-stu-id="2c06a-185">Content-type: application/json</span></span>

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "{machine_action_id}",
    "type": "LiveResponse",
    "requestor": "analyst@microsoft.com",
    "requestorComment": "Testing Live Response API",
    "status": "Pending",
    "machineId": "{machine_id}",
    "computerDnsName": "hostname",
    "creationDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "lastUpdateDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "errorHResult": 0,
    "commands": [
        {
            "index": 0,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "RunScript",
                "params": [
                    {
                        "key": "ScriptName",
                        "value": "minidump.ps1"
                    },{
                        "key": "Args",
                        "value": "OfficeClickToRun"
                    }
                ]
            }
        }, {
            "index": 1,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "GetFile",
                "params": [{
                        "key": "Path", "value": "C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
                    }
                ]
            }
        }
    ]
}


```

## <a name="related-topics"></a><span data-ttu-id="2c06a-186">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="2c06a-186">Related topics</span></span>
- [<span data-ttu-id="2c06a-187">Получите API действий машины</span><span class="sxs-lookup"><span data-stu-id="2c06a-187">Get machine action API</span></span>](get-machineaction-object.md)
- [<span data-ttu-id="2c06a-188">Получить результат ответа в прямом эфире</span><span class="sxs-lookup"><span data-stu-id="2c06a-188">Get live response result</span></span>](get-live-response-result.md)
- [<span data-ttu-id="2c06a-189">Отмена действия машины</span><span class="sxs-lookup"><span data-stu-id="2c06a-189">Cancel machine action</span></span>](cancel-machine-action.md)
