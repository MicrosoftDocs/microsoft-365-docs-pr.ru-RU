---
title: Поток событий Microsoft Defender для конечных точек в концентраторы событий Azure
description: Узнайте, как настроить Microsoft Defender для конечной точки для потоковой передачи событий advanced Hunting в центр событий.
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
ms.openlocfilehash: 8985a40c99ad4db9710dfbf9805d537a921f6c96
ms.sourcegitcommit: f0118e61e490496cb23189cc5c73b23e2ba939be
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2021
ms.locfileid: "52780169"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a><span data-ttu-id="adea0-104">Настройка Microsoft Defender для конечной точки для потоковой передачи событий предварительной охоты в центры событий Azure</span><span class="sxs-lookup"><span data-stu-id="adea0-104">Configure Microsoft Defender for Endpoint to stream Advanced Hunting events to your Azure Event Hubs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="adea0-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="adea0-105">**Applies to:**</span></span>

- [<span data-ttu-id="adea0-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="adea0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="adea0-107">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="adea0-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="adea0-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="adea0-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a><span data-ttu-id="adea0-109">Подготовка</span><span class="sxs-lookup"><span data-stu-id="adea0-109">Before you begin</span></span>

1. <span data-ttu-id="adea0-110">Создайте [центр событий в](/azure/event-hubs/) клиенте.</span><span class="sxs-lookup"><span data-stu-id="adea0-110">Create an [event hub](/azure/event-hubs/) in your tenant.</span></span>

2. <span data-ttu-id="adea0-111">Войдите в клиент [Azure,](https://ms.portal.azure.com/)перейдите в \*\*Subscriptions > Поставщики > ресурсов > зарегистрируйтесь в \*\*Microsoft.insights\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="adea0-111">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to \*\*Subscriptions > Your subscription > Resource Providers > Register to \*\*Microsoft.insights\*\*\*\*.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="adea0-112">Включить потоковую передачу необработанных данных</span><span class="sxs-lookup"><span data-stu-id="adea0-112">Enable raw data streaming</span></span>

1. <span data-ttu-id="adea0-113">Войдите в [Центр безопасности в Microsoft Defender](https://securitycenter.windows.com) как **глобальный** администратор _ или _\*_Администратор_ безопасности \*\*.</span><span class="sxs-lookup"><span data-stu-id="adea0-113">Log in to the [Microsoft Defender Security Center](https://securitycenter.windows.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="adea0-114">Перейдите на [страницу Параметры экспорта](https://securitycenter.windows.com/interoperability/dataexport) данных на Центр безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="adea0-114">Go to the [Data export settings page](https://securitycenter.windows.com/interoperability/dataexport) on Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="adea0-115">Нажмите **кнопку Добавить параметры экспорта данных.**</span><span class="sxs-lookup"><span data-stu-id="adea0-115">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="adea0-116">Выберите имя для новых параметров.</span><span class="sxs-lookup"><span data-stu-id="adea0-116">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="adea0-117">Выберите **перенаступив события в концентраторы событий Azure.**</span><span class="sxs-lookup"><span data-stu-id="adea0-117">Choose **Forward events to Azure Event Hubs**.</span></span>

6. <span data-ttu-id="adea0-118">Введите **имя концентраторов событий** и свой **ИД ресурса Event Hubs.**</span><span class="sxs-lookup"><span data-stu-id="adea0-118">Type your **Event Hubs name** and your **Event Hubs resource ID**.</span></span>

   <span data-ttu-id="adea0-119">Чтобы получить ИД ресурса **Event Hubs,** перейдите на страницу пространства имен Azure Event Hubs на вкладке Свойства [Azure](https://ms.portal.azure.com/) > > скопируйте текст в статье **Resource ID:**</span><span class="sxs-lookup"><span data-stu-id="adea0-119">In order to get your **Event Hubs resource ID**, go to your Azure Event Hubs namespace page on [Azure](https://ms.portal.azure.com/) > properties tab > copy the text under **Resource ID**:</span></span>

   ![Изображение ресурса центра событий Id1](images/event-hub-resource-id.png)

7. <span data-ttu-id="adea0-121">Выберите события, которые необходимо транслировать, и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="adea0-121">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a><span data-ttu-id="adea0-122">Схема событий в центрах событий Azure</span><span class="sxs-lookup"><span data-stu-id="adea0-122">The schema of the events in Azure Event Hubs</span></span>

```
{
    "records": [
                    {
                        "time": "<The time WDATP received the event>"
                        "tenantId": "<The Id of the tenant that the event belongs to>"
                        "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                        "properties": { <WDATP Advanced Hunting event as Json> }
                    }
                    ...
                ]
}
```

- <span data-ttu-id="adea0-123">Каждое сообщение концентратора событий в центрах событий Azure содержит список записей.</span><span class="sxs-lookup"><span data-stu-id="adea0-123">Each event hub message in Azure Event Hubs contains list of records.</span></span>

- <span data-ttu-id="adea0-124">Каждая запись содержит имя события, время получения события Microsoft Defender для конечной точки, его место клиента (вы получите события только от клиента) и событие в формате JSON в свойстве под названием **"свойства".**</span><span class="sxs-lookup"><span data-stu-id="adea0-124">Each record contains the event name, the time Microsoft Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "**properties**".</span></span>

- <span data-ttu-id="adea0-125">Дополнительные сведения о схеме событий Microsoft Defender для конечных точек см. в [обзоре Advanced Hunting.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="adea0-125">For more information about the schema of Microsoft Defender for Endpoint events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="adea0-126">В таблице Advanced Hunting **в таблице DeviceInfo** имеется столбец **MachineGroup,** содержащий группу устройства.</span><span class="sxs-lookup"><span data-stu-id="adea0-126">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="adea0-127">Здесь каждое событие также будет украшено этим столбцом.</span><span class="sxs-lookup"><span data-stu-id="adea0-127">Here every event will be decorated with this column as well.</span></span> <span data-ttu-id="adea0-128">Дополнительные [сведения см.](machine-groups.md) в группе устройств.</span><span class="sxs-lookup"><span data-stu-id="adea0-128">See [Device Groups](machine-groups.md) for more information.</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="adea0-129">Сопоставление типов данных</span><span class="sxs-lookup"><span data-stu-id="adea0-129">Data types mapping</span></span>

<span data-ttu-id="adea0-130">Чтобы получить типы данных для свойств событий, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="adea0-130">To get the data types for event properties do the following:</span></span>

1. <span data-ttu-id="adea0-131">Войдите в [Центр безопасности в Microsoft Defender](https://securitycenter.windows.com) и перейдите на [страницу Расширенный поиск](https://securitycenter.windows.com/hunting-package).</span><span class="sxs-lookup"><span data-stu-id="adea0-131">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com) and go to [Advanced Hunting page](https://securitycenter.windows.com/hunting-package).</span></span>

2. <span data-ttu-id="adea0-132">Запустите следующий запрос, чтобы получить сопоставление типов данных для каждого события:</span><span class="sxs-lookup"><span data-stu-id="adea0-132">Run the following query to get the data types mapping for each event:</span></span>
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="adea0-133">Вот пример события "Информация о устройстве":</span><span class="sxs-lookup"><span data-stu-id="adea0-133">Here is an example for Device Info event:</span></span> 

  ![Изображение Id2 ресурса концентратора событий](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="adea0-135">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="adea0-135">Related topics</span></span>
- [<span data-ttu-id="adea0-136">Обзор расширенных охоты</span><span class="sxs-lookup"><span data-stu-id="adea0-136">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="adea0-137">Microsoft Defender для API потоковой передачи конечных точек</span><span class="sxs-lookup"><span data-stu-id="adea0-137">Microsoft Defender for Endpoint streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="adea0-138">Поток событий Microsoft Defender для событий конечной точки в учетную запись хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="adea0-138">Stream Microsoft Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="adea0-139">Документация по центрам событий Azure</span><span class="sxs-lookup"><span data-stu-id="adea0-139">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="adea0-140">Устранение неполадок с подключением — концентраторы событий Azure</span><span class="sxs-lookup"><span data-stu-id="adea0-140">Troubleshoot connectivity issues - Azure Event Hubs</span></span>](/azure/event-hubs/troubleshooting-guide)