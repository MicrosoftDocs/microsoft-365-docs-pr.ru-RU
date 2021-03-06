---
title: Поток Microsoft 365 Defender событий в Центр событий Azure
description: Узнайте, как настроить Microsoft 365 Defender для потоковой передачи событий advanced Hunting в центр событий.
keywords: экспорт необработанных данных, потоковый API, API, Центр событий Azure, хранилище Azure, учетная запись хранилища, расширенный доступ к данным, обмен необработанные данные
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: 2e43b75e49d01a05fdacae0adf63ea3337631dfd
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289251"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hub"></a>Настройка Microsoft 365 Defender для потоковой передачи событий advanced Hunting в центр событий Azure

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a>Подготовка

1. Создайте [центр событий в](/azure/event-hubs/) клиенте.

2. Войдите в клиент [Azure,](https://ms.portal.azure.com/)перейдите на подписки > подписки > поставщиков ресурсов > зарегистрироваться в **Microsoft.Аналитика.**

3. Создайте пространство имен центра событий, **перейдите в** центр событий > добавить и выбрать уровень цен, единицы пропускной способности и авто-надувка, соответствующие ожидаемой нагрузке. Дополнительные сведения см. в [этой теме Pricing - Event Hub | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).  

### <a name="add-contributor-permissions"></a>Добавление разрешений для участников

После создания пространства имен Центра событий необходимо:

1. Определите пользователя, который будет войти в Microsoft 365 Defender в качестве участника.

2. Если вы подключались к приложению, добавьте главу службы регистрации приложений в качестве reader, приемник данных Azure Event Hub (это также можно сделать на уровне Группы ресурсов или подписки). 

    Перейдите в пространство имен узлов событий > управления доступом **(IAM)** > добавить и проверить в соответствии **с назначениями роли**.

## <a name="enable-raw-data-streaming"></a>Включить потоковую передачу необработанных данных

1. Войдите в [центр Microsoft 365 Defender безопасности](https://security.microsoft.com) в качестве ***Глобального** администратора _ или _*_Администратора_ безопасности **.

2. Перейдите на [страницу Параметры API потокового воспроизведения.](https://security.microsoft.com/settings/mtp_settings/raw_data_export)

3. Нажмите **кнопку Добавить**.

4. Выберите имя для новых параметров.

5. Выберите **перенаступив события в Центр событий Azure.**

6. Вы можете выбрать, хотите ли вы экспортировать данные событий в единый центр событий или экспортировать каждую таблицу событий в другой центр событий в пространстве имен Event Hub. 

7. Чтобы экспортировать данные событий в единый  центр событий, введите имя центра событий и свой ИД ресурса **Event Hub.**

   Чтобы получить ИД ресурса **Event Hub,** перейдите на страницу пространства имен Azure Event Hub на вкладке [Azure](https://ms.portal.azure.com/)Properties > скопируйте текст в  >   статье Resource **ID:**

   ![Изображение Id1 ресурса Event Hub](../defender-endpoint/images/event-hub-resource-id.png)

8. Выберите события, которые необходимо транслировать, и нажмите кнопку **Сохранить**.

## <a name="the-schema-of-the-events-in-azure-event-hub"></a>Схема событий в центре событий Azure

```JSON
{
   "records": [
               {
                  "time": "<The time Microsoft 365 Defender received the event>"
                  "tenantId": "<The Id of the tenant that the event belongs to>"
                  "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                  "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
               }
               ...
            ]
}
```

- Каждое сообщение Центра событий в Центре событий Azure содержит список записей.

- Каждая запись содержит имя события, Microsoft 365 Defender событие, клиент, который ему принадлежит (события будут получены только от клиента), а также событие в формате JSON в свойстве под названием **"свойства".**

- Дополнительные сведения о схеме событий Microsoft 365 Defender см. в [обзоре Advanced Hunting.](advanced-hunting-overview.md)

- В таблице Advanced Hunting **в таблице DeviceInfo** имеется столбец **MachineGroup,** содержащий группу устройства. Здесь каждое событие также будет украшено этим столбцом. 

## <a name="data-types-mapping"></a>Сопоставление типов данных

Чтобы получить типы данных для свойств событий, сделайте следующее:

1. Войдите в [Microsoft 365 центр безопасности](https://security.microsoft.com) и перейдите на [страницу Расширенный поиск](https://security.microsoft.com/hunting-package).

2. Запустите следующий запрос, чтобы получить сопоставление типов данных для каждого события:

   ```kusto
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Вот пример события "Информация о устройстве": 

  ![Изображение Id2 ресурса Event Hub](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Статьи по теме

- [Обзор расширенных охоты](advanced-hunting-overview.md)
- [Microsoft 365 Defender потокового API](streaming-api.md)
- [Поток Microsoft 365 Defender событий в учетную запись хранилища Azure](streaming-api-storage.md)
- [Документация azure Event Hub](/azure/event-hubs/)
- [Устранение проблем с подключением - Центр событий Azure](/azure/event-hubs/troubleshooting-guide)
