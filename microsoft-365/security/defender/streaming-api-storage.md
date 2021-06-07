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
# <a name="configure--microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="f35f9-104">Настройка Microsoft 365 Defender для потоковой передачи событий advanced Hunting в служба хранилища учетную запись</span><span class="sxs-lookup"><span data-stu-id="f35f9-104">Configure  Microsoft 365 Defender to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f35f9-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f35f9-105">**Applies to:**</span></span>
- [<span data-ttu-id="f35f9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f35f9-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


## <a name="before-you-begin"></a><span data-ttu-id="f35f9-107">Подготовка:</span><span class="sxs-lookup"><span data-stu-id="f35f9-107">Before you begin:</span></span>

1. <span data-ttu-id="f35f9-108">Создайте [служба хранилища учетную запись](/azure/storage/common/storage-account-overview) в клиенте.</span><span class="sxs-lookup"><span data-stu-id="f35f9-108">Create a [Storage account](/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="f35f9-109">Войдите в клиент [Azure,](https://ms.portal.azure.com/)перейдите к подпискам > подписки > поставщиков ресурсов **> в Microsoft.Insights**.</span><span class="sxs-lookup"><span data-stu-id="f35f9-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="f35f9-110">Включить потоковую передачу необработанных данных:</span><span class="sxs-lookup"><span data-stu-id="f35f9-110">Enable raw data streaming:</span></span>

1. <span data-ttu-id="f35f9-111">Войдите [в Microsoft 365 центр безопасности Defender](https://security.microsoft.com) в качестве ***Глобального** администратора _ или _*_Администратора_ безопасности \*\*.</span><span class="sxs-lookup"><span data-stu-id="f35f9-111">Log in to [Microsoft 365 Defender security center](https://security.microsoft.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="f35f9-112">Перейдите [на страницу Параметры экспорта](https://security.microsoft.com/settings/mtp_settings/raw_data_export) данных в Центр безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="f35f9-112">Go to [Data export settings page](https://security.microsoft.com/settings/mtp_settings/raw_data_export) in Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="f35f9-113">Нажмите **кнопку Добавить параметры экспорта данных.**</span><span class="sxs-lookup"><span data-stu-id="f35f9-113">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="f35f9-114">Выберите имя для новых параметров.</span><span class="sxs-lookup"><span data-stu-id="f35f9-114">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="f35f9-115">Выберите **события Forward для служба хранилища Azure**.</span><span class="sxs-lookup"><span data-stu-id="f35f9-115">Choose **Forward events to Azure Storage**.</span></span>

6. <span data-ttu-id="f35f9-116">Введите **служба хранилища ИД ресурса учетной записи.**</span><span class="sxs-lookup"><span data-stu-id="f35f9-116">Type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="f35f9-117">Чтобы получить служба хранилища ресурса учетной записи, перейдите на страницу служба хранилища учетной записи на вкладке > свойств [Azure](https://ms.portal.azure.com/) > скопируйте текст под **служба хранилища ID** ресурса учетной записи: </span><span class="sxs-lookup"><span data-stu-id="f35f9-117">In order to get your **Storage Account Resource ID**, go to your Storage account page on [Azure portal](https://ms.portal.azure.com/) > properties tab > copy the text under **Storage Account Resource ID**:</span></span>

   ![Изображение ID1 ресурса центра событий](../defender-endpoint/images/storage-account-resource-id.png)

7. <span data-ttu-id="f35f9-119">Выберите события, которые необходимо транслировать, и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f35f9-119">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="f35f9-120">Схема событий в учетной записи служба хранилища:</span><span class="sxs-lookup"><span data-stu-id="f35f9-120">The schema of the events in the Storage account:</span></span>

- <span data-ttu-id="f35f9-121">Для каждого типа событий будет создан контейнер blob:</span><span class="sxs-lookup"><span data-stu-id="f35f9-121">A blob container will be created for each event type:</span></span> 

  ![Изображение ID2 ресурса центра событий](../defender-endpoint/images/storage-account-event-schema.png)

- <span data-ttu-id="f35f9-123">Схема каждой строки в blob является следующей JSON:</span><span class="sxs-lookup"><span data-stu-id="f35f9-123">The schema of each row in a blob is the following JSON:</span></span> 

  ```
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }               
  ```

- <span data-ttu-id="f35f9-124">Каждый blob содержит несколько строк.</span><span class="sxs-lookup"><span data-stu-id="f35f9-124">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="f35f9-125">Каждая строка содержит имя события, время получения события Defender для Конечной точки, его место для клиента (вы получите события только от клиента) и событие в формате JSON в свойстве под названием "свойства".</span><span class="sxs-lookup"><span data-stu-id="f35f9-125">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="f35f9-126">Дополнительные сведения о схеме событий Microsoft 365 Defender см. в [обзоре Advanced Hunting.](../defender/advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f35f9-126">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span></span>


## <a name="data-types-mapping"></a><span data-ttu-id="f35f9-127">Сопоставление типов данных</span><span class="sxs-lookup"><span data-stu-id="f35f9-127">Data types mapping</span></span>

<span data-ttu-id="f35f9-128">Чтобы получить типы данных для свойств событий, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="f35f9-128">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="f35f9-129">Войдите в [Microsoft 365 центр безопасности](https://security.microsoft.com) и перейдите на [страницу Расширенный поиск](https://security.microsoft.com/hunting-package).</span><span class="sxs-lookup"><span data-stu-id="f35f9-129">Log in to [Microsoft 365 security center](https://security.microsoft.com) and go to [Advanced Hunting page](https://security.microsoft.com/hunting-package).</span></span>

2. <span data-ttu-id="f35f9-130">Запустите следующий запрос, чтобы получить сопоставление типов данных для каждого события:</span><span class="sxs-lookup"><span data-stu-id="f35f9-130">Run the following query to get the data types mapping for each event:</span></span> 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="f35f9-131">Вот пример события "Информация о устройстве":</span><span class="sxs-lookup"><span data-stu-id="f35f9-131">Here is an example for Device Info event:</span></span> 

  ![Изображение ID3 ресурса центра событий](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="f35f9-133">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="f35f9-133">Related topics</span></span>
- [<span data-ttu-id="f35f9-134">Обзор расширенных охоты</span><span class="sxs-lookup"><span data-stu-id="f35f9-134">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="f35f9-135">Microsoft 365 API потоковой передачи Defender</span><span class="sxs-lookup"><span data-stu-id="f35f9-135">Microsoft 365 Defender Streaming API</span></span>](streaming-api.md)
- [<span data-ttu-id="f35f9-136">Поток событий Microsoft 365 Defender в учетную запись хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="f35f9-136">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](streaming-api-storage.md)
- [<span data-ttu-id="f35f9-137">служба хранилища Azure Документация по учетной записи</span><span class="sxs-lookup"><span data-stu-id="f35f9-137">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
