---
title: Поток событий Microsoft Defender для событий конечной точки в учетную запись хранилища
description: Узнайте, как настроить ATP Защитника Майкрософт для потоковой передачи событий advanced Hunting в учетную запись хранилища.
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
ms.openlocfilehash: 9f1eb79bbf617afad58b7e4d70e1f40e422f9046
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071886"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-storage-account"></a>Настройка Microsoft Defender для конечной точки для потоковой передачи событий предварительной охоты на учетную запись хранилища

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a>Подготовка:

1. Создайте [учетную запись хранилища](https://docs.microsoft.com/azure/storage/common/storage-account-overview) в клиенте.

2. Войдите в клиент [Azure,](https://ms.portal.azure.com/)перейдите на подписки > подписки > поставщиков ресурсов **> в Microsoft.insights**.

## <a name="enable-raw-data-streaming"></a>Включить потоковую передачу необработанных данных:

1. Войдите на [портал Microsoft Defender для конечных точек](https://securitycenter.windows.com) в качестве ***Глобального** администратора _ или _*_Администратора_ безопасности **.

2. Перейдите [на страницу Параметры экспорта данных](https://securitycenter.windows.com/interoperability/dataexport) в Центре безопасности Защитника Майкрософт.

3. Нажмите **кнопку Добавить параметры экспорта данных.**

4. Выберите имя для новых параметров.

5. Выберите **перенадвигать события в Azure Storage.**

6. Введите свой **ID ресурса учетной записи хранилища.** Чтобы получить **ID** ресурса учетной записи хранилища, перейдите на страницу учетной записи хранилища на портале [Azure](https://ms.portal.azure.com/) > вкладке свойств > скопируйте текст под ИД ресурса учетной записи хранилища:

   ![Изображение ID1 ресурса центра событий](images/storage-account-resource-id.png)

7. Выберите события, которые необходимо транслировать, и нажмите кнопку **Сохранить**.

## <a name="the-schema-of-the-events-in-the-storage-account"></a>Схема событий в учетной записи Хранилища:

- Для каждого типа событий будет создан контейнер blob: 

  ![Изображение ID2 ресурса центра событий](images/storage-account-event-schema.png)

- Схема каждой строки в blob является следующей JSON: 

  ```
  {
          "time": "<The time WDATP received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <WDATP Advanced Hunting event as Json> }
  }               
  ```

- Каждый blob содержит несколько строк.

- Каждая строка содержит имя события, время получения события Defender для Конечной точки, его место для клиента (вы получите события только от клиента) и событие в формате JSON в свойстве под названием "свойства".

- Дополнительные сведения о схеме событий Microsoft Defender для конечных точек см. в [обзоре Advanced Hunting.](advanced-hunting-overview.md)

- В таблице Advanced Hunting **в таблице DeviceInfo** имеется столбец **MachineGroup,** содержащий группу устройства. Здесь каждое событие также будет украшено этим столбцом. Дополнительные [сведения см.](machine-groups.md) в группе устройств.

## <a name="data-types-mapping"></a>Сопоставление типов данных:

Чтобы получить типы данных для свойств событий, сделайте следующее:

1. Войдите в [Центр безопасности Защитника Майкрософт](https://securitycenter.windows.com) и перейдите на [страницу Расширенный поиск](https://securitycenter.windows.com/hunting-package).

2. Запустите следующий запрос, чтобы получить сопоставление типов данных для каждого события: 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Вот пример события "Информация о устройстве": 

  ![Изображение ID3 ресурса центра событий](images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенных охоты](advanced-hunting-overview.md)
- [Microsoft Defender для API потоковой передачи конечных точек](raw-data-export.md)
- [Поток событий Microsoft Defender для событий конечной точки в учетную запись хранилища Azure](raw-data-export-storage.md)
- [Документация по учетной записи Хранилища Azure](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
