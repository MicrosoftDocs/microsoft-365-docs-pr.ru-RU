---
title: Подключение API API ДЛЯ AP Защитника Майкрософт к Power BI
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
ms.technology: mde
ms.openlocfilehash: 696782ca03e5494c3fc5ca08943d1079c5d78f8a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167035"
---
# <a name="create-custom-reports-using-power-bi"></a><span data-ttu-id="261ff-104">Создание настраиваемой отчетности с помощью Power BI</span><span class="sxs-lookup"><span data-stu-id="261ff-104">Create custom reports using Power BI</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="261ff-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="261ff-105">**Applies to:**</span></span>
- [<span data-ttu-id="261ff-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="261ff-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="261ff-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="261ff-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="261ff-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="261ff-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="261ff-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="261ff-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="261ff-110">В этом разделе вы узнаете, как создать отчет Power BI поверх API Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="261ff-110">In this section you will learn create a Power BI report on top of Defender for Endpoint APIs.</span></span>

<span data-ttu-id="261ff-111">В первом примере показано, как подключить Power BI к API advanced Hunting, а во втором примере — подключение к API OData, таким как действия машины или оповещения.</span><span class="sxs-lookup"><span data-stu-id="261ff-111">The first example demonstrates how to connect Power BI to Advanced Hunting API and the second example demonstrates a connection to our OData APIs, such as Machine Actions or Alerts.</span></span>

## <a name="connect-power-bi-to-advanced-hunting-api"></a><span data-ttu-id="261ff-112">Подключение Power BI к API расширенных охот</span><span class="sxs-lookup"><span data-stu-id="261ff-112">Connect Power BI to Advanced Hunting API</span></span>

- <span data-ttu-id="261ff-113">Open Microsoft Power BI</span><span class="sxs-lookup"><span data-stu-id="261ff-113">Open Microsoft Power BI</span></span>

- <span data-ttu-id="261ff-114">Нажмите **кнопку Получить пустой** запрос  >  **данных**</span><span class="sxs-lookup"><span data-stu-id="261ff-114">Click **Get Data** > **Blank Query**</span></span>

    ![Изображение создания пустого запроса](images/power-bi-create-blank-query.png)

- <span data-ttu-id="261ff-116">Нажмите **кнопку Расширенный редактор**</span><span class="sxs-lookup"><span data-stu-id="261ff-116">Click **Advanced Editor**</span></span>

    ![Изображение открытого продвинутого редактора](images/power-bi-open-advanced-editor.png)

- <span data-ttu-id="261ff-118">Скопируйте ниже и вклеите его в редактор:</span><span class="sxs-lookup"><span data-stu-id="261ff-118">Copy the below and paste it in the editor:</span></span>

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

- <span data-ttu-id="261ff-119">Нажмите **кнопку Готово**</span><span class="sxs-lookup"><span data-stu-id="261ff-119">Click **Done**</span></span>

- <span data-ttu-id="261ff-120">Нажмите **кнопку Изменить учетные данные**</span><span class="sxs-lookup"><span data-stu-id="261ff-120">Click **Edit Credentials**</span></span>

    ![Изображение редактирования учетных данных0](images/power-bi-edit-credentials.png)

- <span data-ttu-id="261ff-122">Выбор **входной**  >  **записи организации**</span><span class="sxs-lookup"><span data-stu-id="261ff-122">Select **Organizational account** > **Sign in**</span></span>

    ![Изображение набора учетных данных1](images/power-bi-set-credentials-organizational.png)

- <span data-ttu-id="261ff-124">Ввод учетных данных и ожидание входа в</span><span class="sxs-lookup"><span data-stu-id="261ff-124">Enter your credentials and wait to be signed in</span></span>

- <span data-ttu-id="261ff-125">Нажмите **кнопку Подключение**</span><span class="sxs-lookup"><span data-stu-id="261ff-125">Click **Connect**</span></span>

    ![Изображение набора учетных данных2](images/power-bi-set-credentials-organizational-cont.png)

- <span data-ttu-id="261ff-127">Теперь результаты запроса будут отображаться в таблице, и вы можете начать создавать визуализации поверх него!</span><span class="sxs-lookup"><span data-stu-id="261ff-127">Now the results of your query will appear as table and you can start build visualizations on top of it!</span></span>

- <span data-ttu-id="261ff-128">Вы можете повторить эту таблицу, переименовать ее и изменить запрос Advanced Hunting внутри, чтобы получить любые данные, которые вы хотите.</span><span class="sxs-lookup"><span data-stu-id="261ff-128">You can duplicate this table, rename it and edit the Advanced Hunting query inside to get any data you would like.</span></span>

## <a name="connect-power-bi-to-odata-apis"></a><span data-ttu-id="261ff-129">Подключение Power BI к API OData</span><span class="sxs-lookup"><span data-stu-id="261ff-129">Connect Power BI to OData APIs</span></span>

- <span data-ttu-id="261ff-130">Единственное отличие от вышеуказанного примера — запрос внутри редактора.</span><span class="sxs-lookup"><span data-stu-id="261ff-130">The only difference from the above example is the query inside the editor.</span></span> 

- <span data-ttu-id="261ff-131">Скопируйте ниже и вклейте его в редактор, чтобы вытащить все **действия машины** из организации:</span><span class="sxs-lookup"><span data-stu-id="261ff-131">Copy the below and paste it in the editor to pull all **Machine Actions** from your organization:</span></span>

```
    let

        Query = "MachineActions",

        Source = OData.Feed("https://api.securitycenter.microsoft.com/api/" & Query, null, [Implementation="2.0", MoreColumns=true])
    in
        Source

```

- <span data-ttu-id="261ff-132">Вы можете сделать то же самое для **оповещений** и **машин.**</span><span class="sxs-lookup"><span data-stu-id="261ff-132">You can do the same for **Alerts** and **Machines**.</span></span>

- <span data-ttu-id="261ff-133">Запросы OData также можно использовать для фильтрации запросов, см. в [рублях Using OData Queries](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="261ff-133">You also can use OData queries for queries filters, see [Using OData Queries](exposed-apis-odata-samples.md)</span></span>


## <a name="power-bi-dashboard-samples-in-github"></a><span data-ttu-id="261ff-134">Примеры панели мониторинга Power BI в GitHub</span><span class="sxs-lookup"><span data-stu-id="261ff-134">Power BI dashboard samples in GitHub</span></span>
<span data-ttu-id="261ff-135">Дополнительные сведения см. в шаблонах [отчетов Power BI.](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI)</span><span class="sxs-lookup"><span data-stu-id="261ff-135">For more information see the [Power BI report templates](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI).</span></span>

## <a name="sample-reports"></a><span data-ttu-id="261ff-136">Примеры отчетов</span><span class="sxs-lookup"><span data-stu-id="261ff-136">Sample reports</span></span>
<span data-ttu-id="261ff-137">Просмотреть примеры отчетов о power BI Microsoft Defender ATP Power.</span><span class="sxs-lookup"><span data-stu-id="261ff-137">View the Microsoft Defender ATP Power BI report samples.</span></span> <span data-ttu-id="261ff-138">Дополнительные сведения см. в [обзоре примеров кода.](https://docs.microsoft.com/samples/browse/?products=mdatp)</span><span class="sxs-lookup"><span data-stu-id="261ff-138">For more information, see [Browse code samples](https://docs.microsoft.com/samples/browse/?products=mdatp).</span></span>


## <a name="related-topic"></a><span data-ttu-id="261ff-139">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="261ff-139">Related topic</span></span>
- [<span data-ttu-id="261ff-140">Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="261ff-140">Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="261ff-141">Программный интерфейс расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="261ff-141">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="261ff-142">Использование запросов OData</span><span class="sxs-lookup"><span data-stu-id="261ff-142">Using OData Queries</span></span>](exposed-apis-odata-samples.md)
