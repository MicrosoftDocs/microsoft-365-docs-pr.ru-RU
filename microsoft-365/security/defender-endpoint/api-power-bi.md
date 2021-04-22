---
title: Microsoft Defender для подключения API конечных точек к Power BI
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
ms.openlocfilehash: 7c99267d75c89b3484d207cd763131e4bcc91527
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935045"
---
# <a name="create-custom-reports-using-power-bi"></a><span data-ttu-id="fc280-104">Создание настраиваемой отчетности с помощью Power BI</span><span class="sxs-lookup"><span data-stu-id="fc280-104">Create custom reports using Power BI</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fc280-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="fc280-105">**Applies to:**</span></span>
- [<span data-ttu-id="fc280-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="fc280-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fc280-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fc280-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="fc280-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="fc280-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="fc280-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="fc280-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="fc280-110">В этом разделе вы узнаете, как создать отчет Power BI поверх API Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="fc280-110">In this section you will learn create a Power BI report on top of Defender for Endpoint APIs.</span></span>

<span data-ttu-id="fc280-111">В первом примере показано, как подключить Power BI к API advanced Hunting, а во втором примере — подключение к API OData, таким как действия машины или оповещения.</span><span class="sxs-lookup"><span data-stu-id="fc280-111">The first example demonstrates how to connect Power BI to Advanced Hunting API and the second example demonstrates a connection to our OData APIs, such as Machine Actions or Alerts.</span></span>

## <a name="connect-power-bi-to-advanced-hunting-api"></a><span data-ttu-id="fc280-112">Подключение Power BI к API расширенных охот</span><span class="sxs-lookup"><span data-stu-id="fc280-112">Connect Power BI to Advanced Hunting API</span></span>

- <span data-ttu-id="fc280-113">Open Microsoft Power BI</span><span class="sxs-lookup"><span data-stu-id="fc280-113">Open Microsoft Power BI</span></span>

- <span data-ttu-id="fc280-114">Нажмите **кнопку Получить пустой** запрос  >  **данных**</span><span class="sxs-lookup"><span data-stu-id="fc280-114">Click **Get Data** > **Blank Query**</span></span>

    ![Изображение создания пустого запроса](images/power-bi-create-blank-query.png)

- <span data-ttu-id="fc280-116">Нажмите **кнопку Расширенный редактор**</span><span class="sxs-lookup"><span data-stu-id="fc280-116">Click **Advanced Editor**</span></span>

    ![Изображение открытого продвинутого редактора](images/power-bi-open-advanced-editor.png)

- <span data-ttu-id="fc280-118">Скопируйте ниже и вклеите его в редактор:</span><span class="sxs-lookup"><span data-stu-id="fc280-118">Copy the below and paste it in the editor:</span></span>

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

- <span data-ttu-id="fc280-119">Нажмите **кнопку Готово**</span><span class="sxs-lookup"><span data-stu-id="fc280-119">Click **Done**</span></span>

- <span data-ttu-id="fc280-120">Нажмите **кнопку Изменить учетные данные**</span><span class="sxs-lookup"><span data-stu-id="fc280-120">Click **Edit Credentials**</span></span>

    ![Изображение редактирования учетных данных0](images/power-bi-edit-credentials.png)

- <span data-ttu-id="fc280-122">Выбор **входной**  >  **записи организации**</span><span class="sxs-lookup"><span data-stu-id="fc280-122">Select **Organizational account** > **Sign in**</span></span>

    ![Изображение набора учетных данных1](images/power-bi-set-credentials-organizational.png)

- <span data-ttu-id="fc280-124">Ввод учетных данных и ожидание входа в</span><span class="sxs-lookup"><span data-stu-id="fc280-124">Enter your credentials and wait to be signed in</span></span>

- <span data-ttu-id="fc280-125">Нажмите **кнопку Подключение**</span><span class="sxs-lookup"><span data-stu-id="fc280-125">Click **Connect**</span></span>

    ![Изображение набора учетных данных2](images/power-bi-set-credentials-organizational-cont.png)

- <span data-ttu-id="fc280-127">Теперь результаты запроса будут отображаться в таблице, и вы можете начать создавать визуализации поверх него!</span><span class="sxs-lookup"><span data-stu-id="fc280-127">Now the results of your query will appear as table and you can start build visualizations on top of it!</span></span>

- <span data-ttu-id="fc280-128">Вы можете повторить эту таблицу, переименовать ее и изменить запрос Advanced Hunting внутри, чтобы получить любые данные, которые вы хотите.</span><span class="sxs-lookup"><span data-stu-id="fc280-128">You can duplicate this table, rename it and edit the Advanced Hunting query inside to get any data you would like.</span></span>

## <a name="connect-power-bi-to-odata-apis"></a><span data-ttu-id="fc280-129">Подключение Power BI к API OData</span><span class="sxs-lookup"><span data-stu-id="fc280-129">Connect Power BI to OData APIs</span></span>

- <span data-ttu-id="fc280-130">Единственное отличие от вышеуказанного примера — запрос внутри редактора.</span><span class="sxs-lookup"><span data-stu-id="fc280-130">The only difference from the above example is the query inside the editor.</span></span> 

- <span data-ttu-id="fc280-131">Скопируйте ниже и вклейте его в редактор, чтобы вытащить все **действия машины** из организации:</span><span class="sxs-lookup"><span data-stu-id="fc280-131">Copy the below and paste it in the editor to pull all **Machine Actions** from your organization:</span></span>

```
    let

        Query = "MachineActions",

        Source = OData.Feed("https://api.securitycenter.microsoft.com/api/" & Query, null, [Implementation="2.0", MoreColumns=true])
    in
        Source

```

- <span data-ttu-id="fc280-132">Вы можете сделать то же самое для **оповещений** и **машин.**</span><span class="sxs-lookup"><span data-stu-id="fc280-132">You can do the same for **Alerts** and **Machines**.</span></span>

- <span data-ttu-id="fc280-133">Запросы OData также можно использовать для фильтрации запросов, см. в [рублях Using OData Queries](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="fc280-133">You also can use OData queries for queries filters, see [Using OData Queries](exposed-apis-odata-samples.md)</span></span>


## <a name="power-bi-dashboard-samples-in-github"></a><span data-ttu-id="fc280-134">Примеры панели мониторинга Power BI в GitHub</span><span class="sxs-lookup"><span data-stu-id="fc280-134">Power BI dashboard samples in GitHub</span></span>
<span data-ttu-id="fc280-135">Дополнительные сведения см. в шаблонах [отчетов Power BI.](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI)</span><span class="sxs-lookup"><span data-stu-id="fc280-135">For more information see the [Power BI report templates](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI).</span></span>

## <a name="sample-reports"></a><span data-ttu-id="fc280-136">Примеры отчетов</span><span class="sxs-lookup"><span data-stu-id="fc280-136">Sample reports</span></span>
<span data-ttu-id="fc280-137">Просмотр примеров отчетов Microsoft Defender для конечной точки power BI.</span><span class="sxs-lookup"><span data-stu-id="fc280-137">View the Microsoft Defender for Endpoint Power BI report samples.</span></span> <span data-ttu-id="fc280-138">Дополнительные сведения см. в [обзоре примеров кода.](https://docs.microsoft.com/samples/browse/?products=mdatp)</span><span class="sxs-lookup"><span data-stu-id="fc280-138">For more information, see [Browse code samples](https://docs.microsoft.com/samples/browse/?products=mdatp).</span></span>


## <a name="related-topic"></a><span data-ttu-id="fc280-139">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="fc280-139">Related topic</span></span>
- [<span data-ttu-id="fc280-140">Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="fc280-140">Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="fc280-141">Программный интерфейс расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="fc280-141">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="fc280-142">Использование запросов OData</span><span class="sxs-lookup"><span data-stu-id="fc280-142">Using OData Queries</span></span>](exposed-apis-odata-samples.md)
