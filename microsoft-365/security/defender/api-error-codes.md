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
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>Общие коды ошибок API API Defender REST 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Защита от угроз (Майкрософт)

> [!IMPORTANT]
> Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска. Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.

Коды ошибок могут быть возвращены операцией на любом из API Защитника Microsoft 365. В каждом ответе на ошибку будет содержаться сообщение об ошибке, которое поможет устранить проблему. Столбец сообщения об ошибке в разделе таблицы содержит некоторые примеры сообщений. Содержимое фактических сообщений зависит от факторов, которые вызвали отклик. Переменное содержимое указывается в таблице угловым скобками.

## <a name="error-codes"></a>Коды ошибок

Код ошибки | Код состояния HTTP | Сообщение
-|-|-
BadRequest | BadRequest (400) | Общее сообщение об ошибке "Плохой запрос".
ODataError | BadRequest (400) | Недействительный запрос URI OData \<the specific error is specified\> .
InvalidInput | BadRequest (400) | Недействительный \<the invalid input\> вход.
InvalidRequestBody | BadRequest (400) | Недействительное тело запроса.
InvalidHashValue | BadRequest (400) | Значение hash \<the invalid hash\> является недействительным.
InvalidDomainName | BadRequest (400) | Доменное \<the invalid domain\> имя является недействительным.
InvalidIpAddress | BadRequest (400) | \<the invalid IP\>IP-адрес недействителен.
InvalidUrl | BadRequest (400) | \<the invalid URL\>URL-адрес недействителен.
MaximumBatchSizeExceeded | BadRequest (400) | Максимальный размер пакета превышен. Получено: \<batch size received\> , разрешено: {размер пакета разрешен}.
MissingRequiredParameter | BadRequest (400) | Параметр \<the missing parameter\> отсутствует.
OsPlatformNotSupported | BadRequest (400) | Платформа ОС \<the client OS Platform\> не поддерживается для этого действия.
ClientVersionNotSupported | BadRequest (400) | \<The requested action\> поддерживается в клиентской версии \<supported client version\> и выше.
Не авторизован (Unauthorized) | Несанкционированный (401) | Не авторизован (Unauthorized) <br /><br />*Примечание. Обычно это вызвано недействительным или просроченным загонщиком авторизации.*
Запрещено | Запрет (403) | Запрещено <br /><br />*Примечание. Допустимый маркер, но недостаточное разрешение для действия*.
DisabledFeature | Запрет (403) | Функция tenant не включена.
DisallowedOperation | Запрет (403) | \<the disallowed operation and the reason\>.
NotFound | Не найден (404) | Сообщение об ошибке General Not Found.
ResourceNotFound | Не найден (404) | Ресурс \<the requested resource\> не найден.
InternalServerError | Ошибка внутреннего сервера (500) | *Примечание. Отсутствие сообщения об ошибке, повторное повторить операцию или связаться с Microsoft, если она не будет решена*

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

## <a name="body-parameters"></a>Параметры тела

> [!IMPORTANT]
> Параметры тела являются чувствительными к делу.

Если вы испытываете *ошибку InvalidRequestBody* или *MissingRequiredParameter,* она может быть вызвана опечатка. Просмотрите документацию по API и убедитесь, что представленные параметры соответствуют соответствующему примеру.

## <a name="tracking-id"></a>Отслеживание ID

Каждый ответ на ошибку содержит уникальный параметр ID для отслеживания. Имя свойства этого параметра является *целевым.* При контакте с нами об ошибке, присоединение этого ID поможет нам найти корневую причину проблемы.

## <a name="related-articles"></a>Связанные статьи

- [Обзор API защитника Microsoft 365](api-overview.md)
- [Поддерживаемые API Microsoft 365 Defender](api-supported.md)
- [Доступ к API защитника Microsoft 365](api-access.md)
- [Узнайте о ограничениях API и лицензировании](api-terms.md)
