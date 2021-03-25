---
title: Добавление или удаление API тегов машин
description: Узнайте, как использовать API тегов добавить или удалить для добавления или удаления тега для машины в Microsoft Defender для конечной точки.
keywords: apis, graph api, supported apis, tags, machine tags
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
ms.openlocfilehash: 98dd513cc66683ff1b95f66d6d7b89916ce54bab
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199781"
---
# <a name="add-or-remove-machine-tags-api"></a>Добавление или удаление API тегов машин

**Область применения:**

- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Описание API

Добавляет или удаляет тег в определенный [компьютер.](machine.md)

## <a name="limitations"></a>Ограничения

1. Вы можете размещать сообщения на компьютерах в последний раз в соответствии с настроенным периодом хранения.

2. Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.


## <a name="permissions"></a>Разрешения

Для вызова этого API требуется одно из следующих разрешений. Дополнительные новости, в том числе выбор разрешений, см. в этой [ссылке: Use Defender for Endpoint API](apis-intro.md)

Тип разрешения |    Разрешение    |    Имя отображения разрешений
:---|:---|:---
Application |    Machine.ReadWrite.All |    'Read and write all machine information'
Делегированное (рабочая или учебная учетная запись) | Machine.ReadWrite | 'Read and write machine information'

>[!Note]
> При получении маркера с помощью учетных данных пользователей:
>
>- У пользователя должно быть по крайней мере следующее разрешение на роль: "Управление параметром безопасности". Дополнительные сведения (см. [дополнительные сведения](user-roles.md) о создании ролей и управлении ими)
>- Пользователь должен иметь доступ к машине на основе параметров группы машин (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) машин).

## <a name="http-request"></a>HTTP-запрос

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/tags
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
:---|:---|:---
Авторизация | Строка | Bearer {token}. **Обязательное поле**.
Content-Type | string | application/json. **Обязательное поле**.

## <a name="request-body"></a>Текст запроса

В теле запроса поставляем объект JSON со следующими параметрами:

Параметр |    Тип    | Описание
:---|:---|:---
Значение |    Строка |    Имя тега. **Обязательное поле**.
Действие    | Перечисление |    Добавление или удаление. Допустимые значения: "Добавить" или "Удалить". **Обязательное поле**.


## <a name="response"></a>Отклик

В случае успешной работы этот метод возвращает код ответа 200 — Ok и обновленный компьютер в тексте отклика.

## <a name="example"></a>Пример

**Запрос**

Вот пример запроса, который добавляет тег машины.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/tags
```

```json
{
  "Value" : "test Tag 2",
  "Action": "Add"
}
```

- Чтобы удалить тег машины, установите действие "Удалить", а не "Добавить" в теле запроса.
