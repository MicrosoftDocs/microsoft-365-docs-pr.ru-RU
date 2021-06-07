---
title: Поток событий Microsoft Defender для конечных точек в служба хранилища учетную запись
description: Узнайте, как настроить Microsoft Defender для конечной точки для потоковой передачи событий advanced Hunting в служба хранилища учетную запись.
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
ms.custom: api
ms.openlocfilehash: 6be79e4991c9e20c46458eacd97ac0b7b7466bc8
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771661"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="7fc87-104">Настройка Microsoft Defender для конечной точки для потоковой передачи событий advanced Hunting в свою служба хранилища учетную запись</span><span class="sxs-lookup"><span data-stu-id="7fc87-104">Configure Microsoft Defender for Endpoint to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7fc87-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="7fc87-105">**Applies to:**</span></span>
- [<span data-ttu-id="7fc87-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="7fc87-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="7fc87-107">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="7fc87-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7fc87-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="7fc87-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a><span data-ttu-id="7fc87-109">Подготовка</span><span class="sxs-lookup"><span data-stu-id="7fc87-109">Before you begin</span></span>

1. <span data-ttu-id="7fc87-110">Создайте [служба хранилища учетную запись](/azure/storage/common/storage-account-overview) в клиенте.</span><span class="sxs-lookup"><span data-stu-id="7fc87-110">Create a [Storage account](/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="7fc87-111">Войдите в клиент [Azure,](https://ms.portal.azure.com/)перейдите на подписки > подписки > поставщиков ресурсов **> в Microsoft.insights**.</span><span class="sxs-lookup"><span data-stu-id="7fc87-111">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="7fc87-112">Включить потоковую передачу необработанных данных</span><span class="sxs-lookup"><span data-stu-id="7fc87-112">Enable raw data streaming</span></span>

1. <span data-ttu-id="7fc87-113">Войдите на [портал Microsoft Defender для конечных точек](https://securitycenter.windows.com) в качестве ***Глобального** администратора _ или _*_Администратора_ безопасности \*\*.</span><span class="sxs-lookup"><span data-stu-id="7fc87-113">Log in to [Microsoft Defender for Endpoint portal](https://securitycenter.windows.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="7fc87-114">Перейдите [на страницу Параметры экспорта](https://securitycenter.windows.com/interoperability/dataexport) данных на Центр безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="7fc87-114">Go to [Data export settings page](https://securitycenter.windows.com/interoperability/dataexport) on Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="7fc87-115">Нажмите **кнопку Добавить параметры экспорта данных.**</span><span class="sxs-lookup"><span data-stu-id="7fc87-115">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="7fc87-116">Выберите имя для новых параметров.</span><span class="sxs-lookup"><span data-stu-id="7fc87-116">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="7fc87-117">Выберите **события Forward для служба хранилища Azure**.</span><span class="sxs-lookup"><span data-stu-id="7fc87-117">Choose **Forward events to Azure Storage**.</span></span>

6. <span data-ttu-id="7fc87-118">Введите **служба хранилища ИД ресурса учетной записи.**</span><span class="sxs-lookup"><span data-stu-id="7fc87-118">Type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="7fc87-119">Чтобы получить служба хранилища ресурса учетной записи, перейдите на страницу служба хранилища учетной записи на вкладке Свойств [Azure](https://ms.portal.azure.com/) > > скопируйте текст под ИД ресурса служба хранилища учетной записи: </span><span class="sxs-lookup"><span data-stu-id="7fc87-119">In order to get your **Storage Account Resource ID**, go to your Storage account page on [Azure portal](https://ms.portal.azure.com/) > properties tab > copy the text under **Storage account resource ID**:</span></span>

   ![Изображение ID1 ресурса центра событий](images/storage-account-resource-id.png)

7. <span data-ttu-id="7fc87-121">Выберите события, которые необходимо транслировать, и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7fc87-121">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="7fc87-122">Схема событий в служба хранилища учетной записи</span><span class="sxs-lookup"><span data-stu-id="7fc87-122">The schema of the events in the Storage account</span></span>

- <span data-ttu-id="7fc87-123">Для каждого типа событий будет создан контейнер blob:</span><span class="sxs-lookup"><span data-stu-id="7fc87-123">A blob container will be created for each event type:</span></span> 

  ![Изображение ID2 ресурса центра событий](images/storage-account-event-schema.png)

- <span data-ttu-id="7fc87-125">Схема каждой строки в blob является следующей JSON:</span><span class="sxs-lookup"><span data-stu-id="7fc87-125">The schema of each row in a blob is the following JSON:</span></span> 

  ```
  {
          "time": "<The time WDATP received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <WDATP Advanced Hunting event as Json> }
  }               
  ```

- <span data-ttu-id="7fc87-126">Каждый blob содержит несколько строк.</span><span class="sxs-lookup"><span data-stu-id="7fc87-126">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="7fc87-127">Каждая строка содержит имя события, время получения события Defender для Конечной точки, его место для клиента (вы получите события только от клиента) и событие в формате JSON в свойстве под названием "свойства".</span><span class="sxs-lookup"><span data-stu-id="7fc87-127">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="7fc87-128">Дополнительные сведения о схеме событий Microsoft Defender для конечных точек см. в [обзоре Advanced Hunting.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="7fc87-128">For more information about the schema of Microsoft Defender for Endpoint events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="7fc87-129">В таблице Advanced Hunting **в таблице DeviceInfo** имеется столбец **MachineGroup,** содержащий группу устройства.</span><span class="sxs-lookup"><span data-stu-id="7fc87-129">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="7fc87-130">Здесь каждое событие также будет украшено этим столбцом.</span><span class="sxs-lookup"><span data-stu-id="7fc87-130">Here every event will be decorated with this column as well.</span></span> <span data-ttu-id="7fc87-131">Дополнительные [сведения см.](machine-groups.md) в группе устройств.</span><span class="sxs-lookup"><span data-stu-id="7fc87-131">See [Device Groups](machine-groups.md) for more information.</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="7fc87-132">Сопоставление типов данных</span><span class="sxs-lookup"><span data-stu-id="7fc87-132">Data types mapping</span></span>

<span data-ttu-id="7fc87-133">Чтобы получить типы данных для свойств событий, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="7fc87-133">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="7fc87-134">Войдите в [Центр безопасности в Microsoft Defender](https://securitycenter.windows.com) и перейдите на [страницу Расширенный поиск](https://securitycenter.windows.com/hunting-package).</span><span class="sxs-lookup"><span data-stu-id="7fc87-134">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com) and go to [Advanced Hunting page](https://securitycenter.windows.com/hunting-package).</span></span>

2. <span data-ttu-id="7fc87-135">Запустите следующий запрос, чтобы получить сопоставление типов данных для каждого события:</span><span class="sxs-lookup"><span data-stu-id="7fc87-135">Run the following query to get the data types mapping for each event:</span></span> 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="7fc87-136">Вот пример события "Информация о устройстве":</span><span class="sxs-lookup"><span data-stu-id="7fc87-136">Here is an example for Device Info event:</span></span> 

  ![Изображение ID3 ресурса центра событий](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="7fc87-138">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="7fc87-138">Related topics</span></span>
- [<span data-ttu-id="7fc87-139">Обзор расширенных охоты</span><span class="sxs-lookup"><span data-stu-id="7fc87-139">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7fc87-140">Microsoft Defender для API потоковой передачи конечных точек</span><span class="sxs-lookup"><span data-stu-id="7fc87-140">Microsoft Defender for Endpoint Streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="7fc87-141">Поток событий Microsoft Defender для событий конечной точки в учетную запись хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="7fc87-141">Stream Microsoft Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="7fc87-142">служба хранилища Azure Документация по учетной записи</span><span class="sxs-lookup"><span data-stu-id="7fc87-142">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)