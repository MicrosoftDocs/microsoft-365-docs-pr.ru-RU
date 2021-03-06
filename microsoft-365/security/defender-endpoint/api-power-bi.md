---
title: Подключение Microsoft Defender для API конечных точек Power BI
ms.reviewer: ''
description: Создайте отчет Power Business Intelligence (BI) поверх API Microsoft Defender для конечных точек.
keywords: apis, поддерживаемые apis, Power BI, отчеты
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
ms.openlocfilehash: 23d9d61644b4c9adad69a5e467e49ca2b1d92413
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290235"
---
# <a name="create-custom-reports-using-power-bi"></a>Создание настраиваемой отчетности с Power BI

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


- Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

В этом разделе вы узнаете, как создать отчет Power BI в верхней части API Defender для конечных точек.

В первом примере показано, как подключить Power BI к API advanced Hunting, а во втором примере — подключение к API OData, таким как действия машины или оповещения.

## <a name="connect-power-bi-to-advanced-hunting-api"></a>Подключение Power BI расширенный API охоты

- Откройте microsoft Power BI

- Нажмите **кнопку Получить пустой** запрос  >  **данных**

  ![Изображение создания пустого запроса](images/power-bi-create-blank-query.png)

- Нажмите **кнопку Расширенный редактор**

  ![Изображение открытого продвинутого редактора](images/power-bi-open-advanced-editor.png)

- Скопируйте ниже и вклеите его в редактор:

```
    let
        AdvancedHuntingQuery = "DeviceEvents | where ActionType contains 'Anti' | limit 20",

        HuntingUrl = "https://api.securitycenter.microsoft.com/api/advancedqueries",

        Response = Json.Document(Web.Contents(HuntingUrl, [Query=[key=AdvancedHuntingQuery]])),

        TypeMap = #table(
            { "Type", "PowerBiType" },
            {
                { "Double",   Double.Type },
                { "Int64",    Int64.Type },
                { "Int32",    Int32.Type },
                { "Int16",    Int16.Type },
                { "UInt64",   Number.Type },
                { "UInt32",   Number.Type },
                { "UInt16",   Number.Type },
                { "Byte",     Byte.Type },
                { "Single",   Single.Type },
                { "Decimal",  Decimal.Type },
                { "TimeSpan", Duration.Type },
                { "DateTime", DateTimeZone.Type },
                { "String",   Text.Type },
                { "Boolean",  Logical.Type },
                { "SByte",    Logical.Type },
                { "Guid",     Text.Type }
            }),

        Schema = Table.FromRecords(Response[Schema]),
        TypedSchema = Table.Join(Table.SelectColumns(Schema, {"Name", "Type"}), {"Type"}, TypeMap , {"Type"}),
        Results = Response[Results],
        Rows = Table.FromRecords(Results, Schema[Name]),
        Table = Table.TransformColumnTypes(Rows, Table.ToList(TypedSchema, (c) => {c{0}, c{2}}))

    in Table
```

- Нажмите **кнопку Готово**

- Нажмите **кнопку Изменить учетные данные**

    ![Изображение редактирования учетных данных0](images/power-bi-edit-credentials.png)

- Выбор **входной**  >  **записи организации**

    ![Изображение набора учетных данных1](images/power-bi-set-credentials-organizational.png)

- Ввод учетных данных и ожидание входа в

- Щелкните **Подключение**

    ![Изображение набора учетных данных2](images/power-bi-set-credentials-organizational-cont.png)

- Теперь результаты запроса будут отображаться в таблице, и вы можете начать создавать визуализации поверх него!

- Вы можете повторить эту таблицу, переименовать ее и изменить запрос Advanced Hunting внутри, чтобы получить любые данные, которые вы хотите.

## <a name="connect-power-bi-to-odata-apis"></a>Подключение Power BI API OData

- Единственное отличие от вышеуказанного примера — запрос внутри редактора.

- Скопируйте ниже и вклейте его в редактор, чтобы вытащить все **действия машины** из организации:

```
    let

        Query = "MachineActions",

        Source = OData.Feed("https://api.securitycenter.microsoft.com/api/" & Query, null, [Implementation="2.0", MoreColumns=true])
    in
        Source
```

- Вы можете сделать то же самое для **оповещений** и **машин.**
- Запросы OData также можно использовать для фильтрации запросов, см. в [рублях Using OData Queries](exposed-apis-odata-samples.md)

## <a name="power-bi-dashboard-samples-in-github"></a>Power BI панели мониторинга в GitHub

Дополнительные сведения см. [в Power BI отчетов.](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI)

## <a name="sample-reports"></a>Примеры отчетов

Просмотр примеров отчетов microsoft Defender для Power BI конечных точек. Дополнительные сведения см. в [обзоре примеров кода.](/samples/browse/?products=mdatp)

## <a name="related-topics"></a>Статьи по теме

- [Defender for Endpoint API](apis-intro.md)
- [API расширенной охоты](run-advanced-query-api.md)
- [Использование запросов OData](exposed-apis-odata-samples.md)
