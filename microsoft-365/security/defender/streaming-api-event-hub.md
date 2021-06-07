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
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a><span data-ttu-id="56fea-104">Настройка Microsoft 365 Defender для потоковой передачи событий advanced Hunting в центры событий Azure</span><span class="sxs-lookup"><span data-stu-id="56fea-104">Configure Microsoft 365 Defender to stream Advanced Hunting events to your Azure Event Hubs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="56fea-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="56fea-105">**Applies to:**</span></span>
- [<span data-ttu-id="56fea-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="56fea-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a><span data-ttu-id="56fea-107">Подготовка:</span><span class="sxs-lookup"><span data-stu-id="56fea-107">Before you begin:</span></span>

1. <span data-ttu-id="56fea-108">Создайте [центр событий в](/azure/event-hubs/) клиенте.</span><span class="sxs-lookup"><span data-stu-id="56fea-108">Create an [event hub](/azure/event-hubs/) in your tenant.</span></span>

2. <span data-ttu-id="56fea-109">Войдите в клиент [Azure,](https://ms.portal.azure.com/)перейдите к подпискам > подписки > поставщиков ресурсов **> в Microsoft.Insights**.</span><span class="sxs-lookup"><span data-stu-id="56fea-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

3. <span data-ttu-id="56fea-110">Создайте пространство имен центра событий, **перейдите** в концентраторы событий > добавить и выбрать уровень цен, единицы пропускной способности и автоматическое надувка, соответствующие ожидаемой нагрузке.</span><span class="sxs-lookup"><span data-stu-id="56fea-110">Create an Event Hub Namespace, go to **Event Hubs > Add** and select the pricing tier, throughput units and Auto-Inflate appropriate for expected load.</span></span> <span data-ttu-id="56fea-111">Дополнительные сведения см. в [руберсе Pricing - Event Hubs | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).</span><span class="sxs-lookup"><span data-stu-id="56fea-111">For more information, see [Pricing - Event Hubs | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).</span></span>  

4. <span data-ttu-id="56fea-112">После создания пространства имен центра событий вам потребуется добавить главу службы регистрации приложений в качестве reader, приемник данных Azure Event Hubs и пользователя, который будет войти в Microsoft 365 Defender в качестве участника (это также можно сделать на уровне Resource Group или Подписка).</span><span class="sxs-lookup"><span data-stu-id="56fea-112">Once the event hub namespace is created you will need to add the App Registration Service Principal as Reader, Azure Event Hubs Data Receiver and the user who will be logging into Microsoft 365 Defender as Contributor (this can also be done at Resource Group or Subscription level).</span></span> <span data-ttu-id="56fea-113">Перейдите в пространство имен узлов событий > управления доступом **(IAM)** > добавить и проверить в соответствии **с назначением ролей.**</span><span class="sxs-lookup"><span data-stu-id="56fea-113">Go to **Event hubs namespace > Access control (IAM) > Add** and verify under **Role assignements**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="56fea-114">Включить потоковую передачу необработанных данных:</span><span class="sxs-lookup"><span data-stu-id="56fea-114">Enable raw data streaming:</span></span>

1. <span data-ttu-id="56fea-115">Войдите в [центр безопасности Microsoft 365 Defender](https://security.microsoft.com) в качестве ***Глобального** администратора _ или _*_Администратора_ безопасности \*\*.</span><span class="sxs-lookup"><span data-stu-id="56fea-115">Log in to the [Microsoft 365 Defender security center](https://security.microsoft.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="56fea-116">Перейдите на [страницу Параметры экспорта данных.](https://security.microsoft.com/settings/mtp_settings/raw_data_export)</span><span class="sxs-lookup"><span data-stu-id="56fea-116">Go to the [Data export settings page](https://security.microsoft.com/settings/mtp_settings/raw_data_export).</span></span>

3. <span data-ttu-id="56fea-117">Нажмите **кнопку Добавить**.</span><span class="sxs-lookup"><span data-stu-id="56fea-117">Click on **Add**.</span></span>

4. <span data-ttu-id="56fea-118">Выберите имя для новых параметров.</span><span class="sxs-lookup"><span data-stu-id="56fea-118">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="56fea-119">Выберите **перенаступив события в концентраторы событий Azure.**</span><span class="sxs-lookup"><span data-stu-id="56fea-119">Choose **Forward events to Azure Event Hubs**.</span></span>

6. <span data-ttu-id="56fea-120">Вы можете выбрать, хотите ли вы экспортировать данные событий в единый центр событий или экспортировать каждую таблицу событий в другой центр имен центра событий.</span><span class="sxs-lookup"><span data-stu-id="56fea-120">You can select if you want to export the event data to a single event hub, or to export each event table to a different even hub in your event hub namespace.</span></span> 

7. <span data-ttu-id="56fea-121">Чтобы экспортировать данные событий в единый  центр событий, введите имя центра событий и свой ИД ресурса **Event Hub.**</span><span class="sxs-lookup"><span data-stu-id="56fea-121">To export the event data to a single event hub, Enter your **Event Hub name** and your **Event Hub resource ID**.</span></span>

   <span data-ttu-id="56fea-122">Чтобы получить ИД ресурса **Event Hubs,** перейдите на страницу пространства имен Azure Event Hubs на вкладке [Azure](https://ms.portal.azure.com/)Properties > скопируйте текст под  >   **ИД ресурса:**</span><span class="sxs-lookup"><span data-stu-id="56fea-122">To get your **Event Hubs resource ID**, go to your Azure Event Hubs namespace page on [Azure](https://ms.portal.azure.com/) > **Properties** tab > copy the text under **Resource ID**:</span></span>

   ![Изображение ресурса центра событий Id1](../defender-endpoint/images/event-hub-resource-id.png)

8. <span data-ttu-id="56fea-124">Выберите события, которые необходимо транслировать, и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="56fea-124">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a><span data-ttu-id="56fea-125">Схема событий в центрах событий Azure:</span><span class="sxs-lookup"><span data-stu-id="56fea-125">The schema of the events in Azure Event Hubs:</span></span>

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

- <span data-ttu-id="56fea-126">Каждое сообщение концентратора событий в центрах событий Azure содержит список записей.</span><span class="sxs-lookup"><span data-stu-id="56fea-126">Each event hub message in Azure Event Hubs contains list of records.</span></span>

- <span data-ttu-id="56fea-127">Каждая запись содержит имя события, Microsoft 365 защитник получил событие, клиент, который ему принадлежит (события будут получены только от клиента), и событие в формате JSON в свойстве под названием **"свойства".**</span><span class="sxs-lookup"><span data-stu-id="56fea-127">Each record contains the event name, the time Microsoft 365 Defender received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "**properties**".</span></span>

- <span data-ttu-id="56fea-128">Дополнительные сведения о схеме событий Microsoft 365 Defender см. в [обзоре Advanced Hunting.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="56fea-128">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="56fea-129">В таблице Advanced Hunting **в таблице DeviceInfo** имеется столбец **MachineGroup,** содержащий группу устройства.</span><span class="sxs-lookup"><span data-stu-id="56fea-129">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="56fea-130">Здесь каждое событие также будет украшено этим столбцом.</span><span class="sxs-lookup"><span data-stu-id="56fea-130">Here every event will be decorated with this column as well.</span></span> 

9. <span data-ttu-id="56fea-131">Чтобы экспортировать каждую таблицу событий в  другой центр событий, просто оставьте имя центра событий пустым, а Microsoft 365 Defender сделает все остальное.</span><span class="sxs-lookup"><span data-stu-id="56fea-131">To export each event table to a different event hub, simply leave the **Event hub name** empty, and Microsoft 365 Defender will do the rest.</span></span>


## <a name="data-types-mapping"></a><span data-ttu-id="56fea-132">Сопоставление типов данных:</span><span class="sxs-lookup"><span data-stu-id="56fea-132">Data types mapping:</span></span>

<span data-ttu-id="56fea-133">Чтобы получить типы данных для свойств событий, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="56fea-133">To get the data types for event properties do the following:</span></span>

1. <span data-ttu-id="56fea-134">Войдите в [Microsoft 365 центр безопасности](https://security.microsoft.com) и перейдите на [страницу Расширенный поиск](https://security.microsoft.com/hunting-package).</span><span class="sxs-lookup"><span data-stu-id="56fea-134">Log in to [Microsoft 365 security center](https://security.microsoft.com) and go to [Advanced Hunting page](https://security.microsoft.com/hunting-package).</span></span>

2. <span data-ttu-id="56fea-135">Запустите следующий запрос, чтобы получить сопоставление типов данных для каждого события:</span><span class="sxs-lookup"><span data-stu-id="56fea-135">Run the following query to get the data types mapping for each event:</span></span>
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="56fea-136">Вот пример события "Информация о устройстве":</span><span class="sxs-lookup"><span data-stu-id="56fea-136">Here is an example for Device Info event:</span></span> 

  ![Изображение Id2 ресурса концентратора событий](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="56fea-138">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="56fea-138">Related topics</span></span>
- [<span data-ttu-id="56fea-139">Обзор расширенных охоты</span><span class="sxs-lookup"><span data-stu-id="56fea-139">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="56fea-140">Microsoft 365 Защитник потокового API</span><span class="sxs-lookup"><span data-stu-id="56fea-140">Microsoft 365 Defender streaming API</span></span>](streaming-api.md)
- [<span data-ttu-id="56fea-141">Поток событий Microsoft 365 Defender в учетную запись хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="56fea-141">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](streaming-api-storage.md)
- [<span data-ttu-id="56fea-142">Документация по центрам событий Azure</span><span class="sxs-lookup"><span data-stu-id="56fea-142">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="56fea-143">Устранение неполадок с подключением — концентраторы событий Azure</span><span class="sxs-lookup"><span data-stu-id="56fea-143">Troubleshoot connectivity issues - Azure Event Hubs</span></span>](/azure/event-hubs/troubleshooting-guide)
