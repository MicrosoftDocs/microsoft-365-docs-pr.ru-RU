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
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>Общие коды ошибок REST API в Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Защита от угроз (Майкрософт)

> [!IMPORTANT]
> Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть существенно изменены до его коммерческого выпуска. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Коды ошибок могут возвращаться операцией с любыми API Microsoft 365 Defender. Каждый ответ об ошибке будет содержать сообщение об ошибке, которое поможет устранить проблему. В столбце сообщения об ошибке в разделе таблицы есть примеры сообщений. Содержимое фактических сообщений зависит от факторов, которые вызвали отклик. Переменное содержимое указывается в таблице угловым скобками.

## <a name="error-codes"></a>Коды ошибок

Код ошибки | Код состояния HTTP | Сообщение
-|-|-
BadRequest | BadRequest (400) | Общее сообщение об ошибке "Bad Request".
ODataError | BadRequest (400) | Недопустимый запрос URI \<the specific error is specified\> OData.
InvalidInput | BadRequest (400) | Недопустимый \<the invalid input\> ввод.
InvalidRequestBody | BadRequest (400) | Недопустимый тело запроса.
InvalidHashValue | BadRequest (400) | Недопустимое значение \<the invalid hash\> hash.
InvalidDomainName | BadRequest (400) | Недопустимое \<the invalid domain\> доменное имя.
InvalidIpAddress | BadRequest (400) | НЕДОПУСТИМЫЙ \<the invalid IP\> IP-адрес.
InvalidUrl | BadRequest (400) | Недопустимый \<the invalid URL\> URL-адрес.
MaximumBatchSizeExceeded | BadRequest (400) | Превышен максимальный размер пакета. Received: \<batch size received\> , allowed: {batch size allowed}.
MissingRequiredParameter | BadRequest (400) | Отсутствует \<the missing parameter\> параметр.
OsPlatformNotSupported | BadRequest (400) | Платформа ОС \<the client OS Platform\> не поддерживается для этого действия.
ClientVersionNotSupported | BadRequest (400) | \<The requested action\> поддерживается в версии клиента \<supported client version\> и выше.
Не авторизован (Unauthorized) | Unauthorized (401) | Не авторизован (Unauthorized) <br /><br />*Примечание. Обычно это вызвано недопустимым или просроченным заголом авторизации.*
Запрещено | Запрещено (403) | Запрещено <br /><br />*Примечание. Допустимый маркер, но недостаточно разрешений для действия.*
DisabledFeature | Запрещено (403) | Функция клиента не включена.
DisallowedOperation | Запрещено (403) | \<the disallowed operation and the reason\>.
NotFound | Не найдено (404) | Сообщение об ошибке "Общие не найдено".
ResourceNotFound | Не найдено (404) | Ресурс \<the requested resource\> не найден.
InternalServerError | Внутренняя ошибка сервера (500) | *Примечание. Если сообщение об ошибке не устранено, повторно вы можете повторить операцию или обратиться в корпорацию Майкрософт.*

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
> Параметры тела чувствительны к делу.

Ошибка *InvalidRequestBody* или *MissingRequiredParameter* может быть вызвана опечатку. Просмотрите документацию по API и убедитесь, что отправленные параметры соответствуют соответствующему примеру.

## <a name="tracking-id"></a>ИД отслеживания

Каждый ответ об ошибке содержит уникальный параметр ID для отслеживания. Имя свойства этого параметра — *target*. Когда мы обращаемся к нам по поводу ошибки, прикрепление этого ИД поможет нам найти первопричину проблемы.

## <a name="related-articles"></a>Статьи по теме

- [Обзор API Microsoft 365 Defender](api-overview.md)
- [Поддерживаемые API Microsoft 365 Defender](api-supported.md)
- [Доступ к API Microsoft 365 Defender](api-access.md)
- [Узнайте об ограничениях API и лицензировании](api-terms.md)
