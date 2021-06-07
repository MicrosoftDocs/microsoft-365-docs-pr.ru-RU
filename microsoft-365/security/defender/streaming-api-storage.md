---
title: Поток Microsoft 365 событий Defender на свою служба хранилища учетную запись
description: Узнайте, как настроить Microsoft 365 Defender для потоковой передачи событий advanced Hunting в свою служба хранилища учетную запись.
keywords: экспорт необработанных данных, потоковый API, API, концентраторы событий, хранилище Azure, учетная запись хранилища, расширенный доступ к данным, обмен необработанные данные
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
ms.openlocfilehash: a4e706bbb2246bd0629db721373ffcd4164d123d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772559"
---
# <a name="configure--microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a>Настройка Microsoft 365 Defender для потоковой передачи событий advanced Hunting в служба хранилища учетную запись

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


## <a name="before-you-begin"></a>Подготовка:

1. Создайте [служба хранилища учетную запись](/azure/storage/common/storage-account-overview) в клиенте.

2. Войдите в клиент [Azure,](https://ms.portal.azure.com/)перейдите к подпискам > подписки > поставщиков ресурсов **> в Microsoft.Insights**.

## <a name="enable-raw-data-streaming"></a>Включить потоковую передачу необработанных данных:

1. Войдите [в Microsoft 365 центр безопасности Defender](https://security.microsoft.com) в качестве ***Глобального** администратора _ или _*_Администратора_ безопасности **.

2. Перейдите [на страницу Параметры экспорта](https://security.microsoft.com/settings/mtp_settings/raw_data_export) данных в Центр безопасности в Microsoft Defender.

3. Нажмите **кнопку Добавить параметры экспорта данных.**

4. Выберите имя для новых параметров.

5. Выберите **события Forward для служба хранилища Azure**.

6. Введите **служба хранилища ИД ресурса учетной записи.** Чтобы получить служба хранилища ресурса учетной записи, перейдите на страницу служба хранилища учетной записи на вкладке > свойств [Azure](https://ms.portal.azure.com/) > скопируйте текст под **служба хранилища ID** ресурса учетной записи: 

   ![Изображение ID1 ресурса центра событий](../defender-endpoint/images/storage-account-resource-id.png)

7. Выберите события, которые необходимо транслировать, и нажмите кнопку **Сохранить**.

## <a name="the-schema-of-the-events-in-the-storage-account"></a>Схема событий в учетной записи служба хранилища:

- Для каждого типа событий будет создан контейнер blob: 

  ![Изображение ID2 ресурса центра событий](../defender-endpoint/images/storage-account-event-schema.png)

- Схема каждой строки в blob является следующей JSON: 

  ```
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }               
  ```

- Каждый blob содержит несколько строк.

- Каждая строка содержит имя события, время получения события Defender для Конечной точки, его место для клиента (вы получите события только от клиента) и событие в формате JSON в свойстве под названием "свойства".

- Дополнительные сведения о схеме событий Microsoft 365 Defender см. в [обзоре Advanced Hunting.](../defender/advanced-hunting-overview.md)


## <a name="data-types-mapping"></a>Сопоставление типов данных

Чтобы получить типы данных для свойств событий, сделайте следующее:

1. Войдите в [Microsoft 365 центр безопасности](https://security.microsoft.com) и перейдите на [страницу Расширенный поиск](https://security.microsoft.com/hunting-package).

2. Запустите следующий запрос, чтобы получить сопоставление типов данных для каждого события: 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Вот пример события "Информация о устройстве": 

  ![Изображение ID3 ресурса центра событий](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенных охоты](../defender/advanced-hunting-overview.md)
- [Microsoft 365 API потоковой передачи Defender](streaming-api.md)
- [Поток событий Microsoft 365 Defender в учетную запись хранилища Azure](streaming-api-storage.md)
- [служба хранилища Azure Документация по учетной записи](/azure/storage/common/storage-account-overview)
