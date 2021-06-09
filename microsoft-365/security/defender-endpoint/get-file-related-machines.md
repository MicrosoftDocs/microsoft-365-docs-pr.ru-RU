---
title: Получить API машин, связанных с файлами
description: Узнайте, как использовать API машин Get, связанных с файлами, чтобы получить коллекцию машин, связанных с hash файла в Microsoft Defender для конечной точки.
keywords: apis, graph api, supported apis, get, devices, hash
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
ms.openlocfilehash: 211a29bcd9265ae20c4f3e1817fcaaf562260d39
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770281"
---
# <a name="get-file-related-machines-api"></a>Получить API машин, связанных с файлами

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Описание API
Извлекает коллекцию [машин, связанных](machine.md) с данными файлами.


## <a name="limitations"></a>Ограничения
1. Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.


## <a name="permissions"></a>Разрешения
Для вызова этого API требуется одно из следующих разрешений. Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)

Тип разрешения |   Разрешение  |   Имя отображения разрешений
:---|:---|:---
Приложение |   Machine.Read.All |  'Read all machine profiles'
Приложение |   Machine.ReadWrite.All | 'Read and write all machine information'
Делегированные (рабочая или учебная учетная запись) | Machine.Read | 'Read machine information'
Делегированные (рабочая или учебная учетная запись) | Machine.ReadWrite | 'Read and write machine information'

>[!Note]
> При получении маркера с помощью учетных данных пользователей:
>- Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)
>- Ответ будет включать только устройства, к которые пользователь имеет доступ на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).

## <a name="http-request"></a>HTTP-запрос
```
GET /api/files/{id}/machines
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
:---|:---|:---
Авторизация | String | Bearer {token}. **Обязательное поле**.


## <a name="request-body"></a>Тело запроса
переменная Empty

## <a name="response"></a>Отклик
При успешном и файле существует — [](machine.md) 200 ОК со списком машинных сущностями в теле. Если файл не существует - 404 Не найден.


## <a name="example"></a>Пример

**Запрос**

Ниже приведен пример запроса.

```http
GET https://api.securitycenter.microsoft.com/api/files/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/machines
```
