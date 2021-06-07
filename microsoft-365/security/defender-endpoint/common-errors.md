---
title: Общие ошибки API API Для защитника Майкрософт для конечной точки
description: Список распространенных ошибок API API для Защитника Майкрософт для конечных точек с описаниями.
keywords: API, Microsoft Defender для API конечной точки, ошибки, устранение неполадок
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: c2e52b7074dcd15e7f6852a11ccb7793572cd9b5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771013"
---
# <a name="common-rest-api-error-codes"></a>Коды распространенных ошибок REST API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* Коды ошибок, перечисленные в следующей таблице, могут быть возвращены операцией на любом из API Конечных точек Microsoft Defender.
* В дополнение к коду ошибки каждый ответ на ошибку содержит сообщение об ошибке, которое может помочь устранить проблему.
* Сообщение — это бесплатный текст, который можно изменить.
* В нижней части страницы можно найти примеры ответов.

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Код ошибки |Код состояния HTTP |Сообщение 
:---|:---|:---
BadRequest | BadRequest (400) | Общее сообщение об ошибке "Плохой запрос".
ODataError | BadRequest (400) | Недействительный запрос OData URI (указана конкретная ошибка).
InvalidInput | BadRequest (400) | Недействительный вход {недопустимый ввод}.
InvalidRequestBody | BadRequest (400) | Недействительное тело запроса.
InvalidHashValue | BadRequest (400) | Значение Hash {недействительный hash} является недействительным.
InvalidDomainName | BadRequest (400) | Доменное имя {недействительный домен} является недействительным.
InvalidIpAddress | BadRequest (400) | IP-адрес {недействительный IP} является недействительным.
InvalidUrl | BadRequest (400) | URL-адрес {недопустимый URL-адрес} является недействительным.
MaximumBatchSizeExceeded | BadRequest (400) | Максимальный размер пакета превышен. Получено: {размер пакета получен}, разрешено: {размер пакета разрешен}.
MissingRequiredParameter | BadRequest (400) | Параметр {отсутствующий параметр} отсутствует.
OsPlatformNotSupported | BadRequest (400) | Платформа OS {клиентская платформа ОС} не поддерживается для этого действия.
ClientVersionNotSupported | BadRequest (400) | {Запрашиваемая мера} поддерживается в клиентской версии {поддерживаемой клиентской версии} и выше.
Не авторизован (Unauthorized) | Несанкционированный (401) | Несанкционированный (недействительный или просроченный загон авторизации).
Запрещено | Запрет (403) | Запрет (допустимый маркер, но недостаточное разрешение для действия).
DisabledFeature | Запрет (403) | Функция tenant не включена.
DisallowedOperation | Запрет (403) | {отложенная операция и причина}.
NotFound | Не найден (404) | Сообщение об ошибке General Not Found.
ResourceNotFound | Не найден (404) | Ресурс {запрашиваемом ресурсе} не найден.
InternalServerError | Ошибка внутреннего сервера (500) | (Нет сообщения об ошибке, повторить операцию)
TooManyRequests | Слишком много запросов (429) | Ответ будет представлять достижение ограничения квоты либо по количеству запросов, либо по ЦП.

## <a name="body-parameters-are-case-sensitive"></a>Параметры тела являются чувствительными к делу

Представленные параметры тела в настоящее время чувствительны к делу.
<br>Если вы испытываете **ошибки InvalidRequestBody** или **MissingRequiredParameter,** это может быть вызвано неправильным капиталом параметров или письмом нижнего уровня.
<br>Просмотрите страницу документации API и убедитесь, что представленные параметры соответствуют соответствующему примеру.

## <a name="correlation-request-id"></a>ID запроса корреляции

Каждый ответ на ошибку содержит уникальный параметр ID для отслеживания.
<br>Имя свойства этого параметра — "target".
<br>При контакте с нами об ошибке, присоединение этого ID поможет найти корневую причину проблемы.

## <a name="examples"></a>Примеры

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
