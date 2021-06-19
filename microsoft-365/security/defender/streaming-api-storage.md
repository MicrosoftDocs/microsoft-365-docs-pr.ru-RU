---
title: Поток Microsoft 365 Defender событий в служба хранилища учетную запись
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
ms.openlocfilehash: 656387e60bac90c7e9de4852779948dabce0efe3
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029661"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="efe59-104">Настройка Microsoft 365 Defender для потоковой передачи событий advanced Hunting в служба хранилища учетную запись</span><span class="sxs-lookup"><span data-stu-id="efe59-104">Configure Microsoft 365 Defender to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="efe59-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="efe59-105">**Applies to:**</span></span>
- [<span data-ttu-id="efe59-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="efe59-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a><span data-ttu-id="efe59-107">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="efe59-107">Before you begin</span></span>

1. <span data-ttu-id="efe59-108">Создайте [служба хранилища учетную запись](/azure/storage/common/storage-account-overview) в клиенте.</span><span class="sxs-lookup"><span data-stu-id="efe59-108">Create a [Storage account](/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="efe59-109">Войдите в клиент [Azure,](https://ms.portal.azure.com/)перейдите на подписки > подписки > поставщиков ресурсов > зарегистрироваться в **Microsoft.Аналитика.**</span><span class="sxs-lookup"><span data-stu-id="efe59-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="efe59-110">Включить потоковую передачу необработанных данных</span><span class="sxs-lookup"><span data-stu-id="efe59-110">Enable raw data streaming</span></span>

1. <span data-ttu-id="efe59-111">Войдите на портал Microsoft 365 Defender () в качестве <https://security.microsoft.com> ***Глобального** администратора _ или _*_администратора_ безопасности \*\*.</span><span class="sxs-lookup"><span data-stu-id="efe59-111">Log in to the Microsoft 365 Defender portal (<https://security.microsoft.com>) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="efe59-112">Перейдите **Параметры** \> **Microsoft 365 Defender** \> **API потоковой передачи.**</span><span class="sxs-lookup"><span data-stu-id="efe59-112">Go to **Settings** \> **Microsoft 365 Defender** \> **Streaming API**.</span></span> <span data-ttu-id="efe59-113">Чтобы перейти непосредственно на страницу **API потоковой** передачи, используйте <https://security.microsoft.com/settings/mtp_settings/raw_data_export> .</span><span class="sxs-lookup"><span data-stu-id="efe59-113">To go directly to the **Streaming API** page, use <https://security.microsoft.com/settings/mtp_settings/raw_data_export>.</span></span>

3. <span data-ttu-id="efe59-114">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="efe59-114">Click **Add**.</span></span>

4. <span data-ttu-id="efe59-115">В **вылете добавлены новые параметры API** потокового воспроизведения, которые появляются, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="efe59-115">In the **Add new Streaming API settings** flyout that appears, configure the following settings:</span></span>
   1. <span data-ttu-id="efe59-116">**Имя.** Выберите имя для новых параметров.</span><span class="sxs-lookup"><span data-stu-id="efe59-116">**Name**: Choose a name for your new settings.</span></span>
   2. <span data-ttu-id="efe59-117">Выберите **события Forward для служба хранилища Azure**.</span><span class="sxs-lookup"><span data-stu-id="efe59-117">Select **Forward events to Azure Storage**.</span></span>
   3. <span data-ttu-id="efe59-118">В поле **служба хранилища ресурса** учетной записи, которое отображается, **введите служба хранилища-служба хранилища учетной записи.**</span><span class="sxs-lookup"><span data-stu-id="efe59-118">In the **Storage Account Resource ID** box that appears, type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="efe59-119">Чтобы получить **служба хранилища** ресурса учетной записи, откройте портал Azure по ссылке , нажмите кнопку служба хранилища учетные записи перейдите на вкладку свойств скопируйте текст под служба хранилища ID ресурса учетной <https://portal.azure.com>  \> \> **записи**.</span><span class="sxs-lookup"><span data-stu-id="efe59-119">To get your **Storage Account Resource ID**, open the Azure portal at <https://portal.azure.com>, click **Storage accounts** \> go to the properties tab \> copy the text under **Storage Account Resource ID**.</span></span>

      ![Изображение ID1 ресурса центра событий](../defender-endpoint/images/storage-account-resource-id.png)

   4. <span data-ttu-id="efe59-121">Возвращаясь к **вылету Добавить новые параметры API** потоковой передачи, выберите типы **событий,** которые необходимо транслировать.</span><span class="sxs-lookup"><span data-stu-id="efe59-121">Back on the **Add new Streaming API settings** flyout, choose the **Event types** that you want to stream.</span></span>

   <span data-ttu-id="efe59-122">По завершению нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="efe59-122">When you're finished, click **Submit**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="efe59-123">Схема событий в служба хранилища учетной записи</span><span class="sxs-lookup"><span data-stu-id="efe59-123">The schema of the events in the Storage account</span></span>

- <span data-ttu-id="efe59-124">Для каждого типа событий будет создан контейнер blob:</span><span class="sxs-lookup"><span data-stu-id="efe59-124">A blob container will be created for each event type:</span></span>

  ![Изображение ID2 ресурса центра событий](../defender-endpoint/images/storage-account-event-schema.png)

- <span data-ttu-id="efe59-126">Схема каждой строки в blob является следующей JSON:</span><span class="sxs-lookup"><span data-stu-id="efe59-126">The schema of each row in a blob is the following JSON:</span></span>

  ```JSON
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }
  ```

- <span data-ttu-id="efe59-127">Каждый blob содержит несколько строк.</span><span class="sxs-lookup"><span data-stu-id="efe59-127">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="efe59-128">Каждая строка содержит имя события, время получения события Defender для Конечной точки, его место для клиента (вы получите события только от клиента) и событие в формате JSON в свойстве под названием "свойства".</span><span class="sxs-lookup"><span data-stu-id="efe59-128">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="efe59-129">Дополнительные сведения о схеме событий Microsoft 365 Defender см. в [обзоре Advanced Hunting.](../defender/advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="efe59-129">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="efe59-130">Сопоставление типов данных</span><span class="sxs-lookup"><span data-stu-id="efe59-130">Data types mapping</span></span>

<span data-ttu-id="efe59-131">Чтобы получить типы данных для свойств событий, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="efe59-131">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="efe59-132">Войдите на портал Microsoft 365 Defender () и <https://security.microsoft.com> перейдите на **охоту** \> **advanced hunting**.</span><span class="sxs-lookup"><span data-stu-id="efe59-132">Log in to the Microsoft 365 Defender portal (<https://security.microsoft.com>) and go to **Hunting** \> **Advanced hunting**.</span></span> <span data-ttu-id="efe59-133">Чтобы перейти непосредственно на **страницу Расширенный поиск,** используйте <security.microsoft.com/advanced-hunting>.</span><span class="sxs-lookup"><span data-stu-id="efe59-133">To go directly to the **Advanced hunting** page, use <security.microsoft.com/advanced-hunting>.</span></span>

2. <span data-ttu-id="efe59-134">На **вкладке Запрос** запустите следующий запрос, чтобы получить сопоставление типов данных для каждого события:</span><span class="sxs-lookup"><span data-stu-id="efe59-134">On the **Query** tab, run the following query to get the data types mapping for each event:</span></span>

   ```text
   {EventType}
   | getschema
   | project ColumnName, ColumnType
   ```

- <span data-ttu-id="efe59-135">Вот пример события "Информация о устройстве":</span><span class="sxs-lookup"><span data-stu-id="efe59-135">Here is an example for Device Info event:</span></span>

  ![Изображение ID3 ресурса центра событий](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="efe59-137">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="efe59-137">Related topics</span></span>

- [<span data-ttu-id="efe59-138">Обзор расширенных охоты</span><span class="sxs-lookup"><span data-stu-id="efe59-138">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="efe59-139">Microsoft 365 Defender Потоковый API</span><span class="sxs-lookup"><span data-stu-id="efe59-139">Microsoft 365 Defender Streaming API</span></span>](streaming-api.md)
- [<span data-ttu-id="efe59-140">Поток Microsoft 365 Defender событий в учетную запись хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="efe59-140">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](streaming-api-storage.md)
- [<span data-ttu-id="efe59-141">служба хранилища Azure Документация по учетной записи</span><span class="sxs-lookup"><span data-stu-id="efe59-141">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
