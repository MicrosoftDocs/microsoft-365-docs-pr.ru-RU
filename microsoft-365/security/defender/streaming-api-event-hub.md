---
title: Поток Microsoft 365 событий Defender в концентраторы событий Azure
description: Узнайте, как настроить Microsoft 365 Defender для потоковой передачи событий advanced Hunting в центр событий.
keywords: экспорт необработанных данных, потоковый API, API, концентраторы событий Azure, хранилище Azure, учетная запись хранилища, расширенный доступ к данным, обмен необработанные данные
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
ms.openlocfilehash: b96ae78b0f2decfe7b2c6f695a4456ac93919c35
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772560"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a>Настройка Microsoft 365 Defender для потоковой передачи событий advanced Hunting в центры событий Azure

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a>Подготовка:

1. Создайте [центр событий в](/azure/event-hubs/) клиенте.

2. Войдите в клиент [Azure,](https://ms.portal.azure.com/)перейдите к подпискам > подписки > поставщиков ресурсов **> в Microsoft.Insights**.

3. Создайте пространство имен центра событий, **перейдите** в концентраторы событий > добавить и выбрать уровень цен, единицы пропускной способности и автоматическое надувка, соответствующие ожидаемой нагрузке. Дополнительные сведения см. в [руберсе Pricing - Event Hubs | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).  

4. После создания пространства имен центра событий вам потребуется добавить главу службы регистрации приложений в качестве reader, приемник данных Azure Event Hubs и пользователя, который будет войти в Microsoft 365 Defender в качестве участника (это также можно сделать на уровне Resource Group или Подписка). Перейдите в пространство имен узлов событий > управления доступом **(IAM)** > добавить и проверить в соответствии **с назначением ролей.**

## <a name="enable-raw-data-streaming"></a>Включить потоковую передачу необработанных данных:

1. Войдите в [центр безопасности Microsoft 365 Defender](https://security.microsoft.com) в качестве ***Глобального** администратора _ или _*_Администратора_ безопасности **.

2. Перейдите на [страницу Параметры экспорта данных.](https://security.microsoft.com/settings/mtp_settings/raw_data_export)

3. Нажмите **кнопку Добавить**.

4. Выберите имя для новых параметров.

5. Выберите **перенаступив события в концентраторы событий Azure.**

6. Вы можете выбрать, хотите ли вы экспортировать данные событий в единый центр событий или экспортировать каждую таблицу событий в другой центр имен центра событий. 

7. Чтобы экспортировать данные событий в единый  центр событий, введите имя центра событий и свой ИД ресурса **Event Hub.**

   Чтобы получить ИД ресурса **Event Hubs,** перейдите на страницу пространства имен Azure Event Hubs на вкладке [Azure](https://ms.portal.azure.com/)Properties > скопируйте текст под  >   **ИД ресурса:**

   ![Изображение ресурса центра событий Id1](../defender-endpoint/images/event-hub-resource-id.png)

8. Выберите события, которые необходимо транслировать, и нажмите кнопку **Сохранить**.

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a>Схема событий в центрах событий Azure:

```
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

- Каждое сообщение концентратора событий в центрах событий Azure содержит список записей.

- Каждая запись содержит имя события, Microsoft 365 защитник получил событие, клиент, который ему принадлежит (события будут получены только от клиента), и событие в формате JSON в свойстве под названием **"свойства".**

- Дополнительные сведения о схеме событий Microsoft 365 Defender см. в [обзоре Advanced Hunting.](advanced-hunting-overview.md)

- В таблице Advanced Hunting **в таблице DeviceInfo** имеется столбец **MachineGroup,** содержащий группу устройства. Здесь каждое событие также будет украшено этим столбцом. 

9. Чтобы экспортировать каждую таблицу событий в  другой центр событий, просто оставьте имя центра событий пустым, а Microsoft 365 Defender сделает все остальное.


## <a name="data-types-mapping"></a>Сопоставление типов данных:

Чтобы получить типы данных для свойств событий, сделайте следующее:

1. Войдите в [Microsoft 365 центр безопасности](https://security.microsoft.com) и перейдите на [страницу Расширенный поиск](https://security.microsoft.com/hunting-package).

2. Запустите следующий запрос, чтобы получить сопоставление типов данных для каждого события:
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Вот пример события "Информация о устройстве": 

  ![Изображение Id2 ресурса концентратора событий](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенных охоты](advanced-hunting-overview.md)
- [Microsoft 365 Защитник потокового API](streaming-api.md)
- [Поток событий Microsoft 365 Defender в учетную запись хранилища Azure](streaming-api-storage.md)
- [Документация по центрам событий Azure](/azure/event-hubs/)
- [Устранение неполадок с подключением — концентраторы событий Azure](/azure/event-hubs/troubleshooting-guide)
