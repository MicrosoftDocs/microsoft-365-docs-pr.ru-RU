---
title: Этап 2. Используйте Microsoft Teams для создания канала управления контрактами
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: Узнайте, как использовать Microsoft Teams для создания канала управления контрактами с помощью Microsoft 365 решения.
ms.openlocfilehash: 7c7d3ef30d376e14e033243413637cdb51ba548a
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2021
ms.locfileid: "53148978"
---
# <a name="step-2-use-microsoft-teams-to-create-your-contract-management-channel"></a><span data-ttu-id="44443-104">Этап 2.</span><span class="sxs-lookup"><span data-stu-id="44443-104">Step 2.</span></span> <span data-ttu-id="44443-105">Используйте Microsoft Teams для создания канала управления контрактами</span><span class="sxs-lookup"><span data-stu-id="44443-105">Use Microsoft Teams to create your contract management channel</span></span>

<span data-ttu-id="44443-106">Когда организация создает решение по управлению контрактами, необходимо центральное расположение, в котором заинтересованные стороны могут просмотреть и управлять контрактами.</span><span class="sxs-lookup"><span data-stu-id="44443-106">When your organization sets up a contracts management solution, you need a central location in which stakeholders can review and manage contracts.</span></span> <span data-ttu-id="44443-107">Для этого можно использовать [](/microsoftteams/) Microsoft Teams для Teams канала и использовать функции в Teams:</span><span class="sxs-lookup"><span data-stu-id="44443-107">For this purpose, you can use [Microsoft Teams](/microsoftteams/) to set up a Teams channel and use the features in Teams to:</span></span>

- <span data-ttu-id="44443-108">**Создайте расположение для заинтересованных сторон, чтобы легко видеть все контракты, которые требуют действий.**</span><span class="sxs-lookup"><span data-stu-id="44443-108">**Create a location for stakeholders to easily see all contracts that require action.**</span></span> <span data-ttu-id="44443-109">Например, в Teams вы можете создать вкладку **Контракты** в канале управления контрактами, в которой участники смогут увидеть полезное представление плитки для всех контрактов, которые требуют утверждения.</span><span class="sxs-lookup"><span data-stu-id="44443-109">For example, in Teams you can create a **Contracts** tab in the Contract Management channel in which members can see a useful tile view of all contracts that need approval.</span></span> <span data-ttu-id="44443-110">Вы также можете настроить представление таким образом, чтобы каждая "карта" перечисляла важные данные, которые вам важны (например, клиент, *подрядчик* и сумма *платы).*</span><span class="sxs-lookup"><span data-stu-id="44443-110">You can also configure the view so that each "card" lists the important data you care about (such as *Client*, *Contractor*, and *Fee amount*).</span></span>

     ![Вкладка Контракты.](../media/content-understanding/tile-view.png)

- <span data-ttu-id="44443-112">**У участников есть расположение, чтобы взаимодействовать друг с другом и видеть важные события.**</span><span class="sxs-lookup"><span data-stu-id="44443-112">**Have a location for members to interact with each other and see important events.**</span></span> <span data-ttu-id="44443-113">Например, в Teams вкладка **"Сообщения"** можно использовать для бесед, получения обновлений и действий (например, для участника, отклонить контракт).</span><span class="sxs-lookup"><span data-stu-id="44443-113">For example, in Teams, the **Posts** tab can be used to have conversations, get updates, and see actions (such as a member rejecting a contract).</span></span> <span data-ttu-id="44443-114">Если что-то произошло (например, новый контракт, отправленный на утверждение), вкладка **Posts** может использоваться не только для его анонса, но и для записи.</span><span class="sxs-lookup"><span data-stu-id="44443-114">When something has happened (such as a new contract submitted for approval), the **Posts** tab can be used not only to announce it, but also to keep a record of it.</span></span> <span data-ttu-id="44443-115">Если участники подписываются на уведомления, они будут получать уведомления при обновлении.</span><span class="sxs-lookup"><span data-stu-id="44443-115">And if members subscribe to notifications, they'll get notified whenever there's an update.</span></span>

     ![Вкладка "Сообщения".](../media/content-understanding/posts.png)

- <span data-ttu-id="44443-117">**У вас есть расположение для участников, чтобы увидеть утвержденные контракты, чтобы узнать, когда они могут быть отправлены для оплаты.**</span><span class="sxs-lookup"><span data-stu-id="44443-117">**Have a location for members to see approved contracts to know when they can be submitted for payment.**</span></span> <span data-ttu-id="44443-118">В SharePoint необходимо создать список выплат и  включить столбцы для клиента, подрядчика и суммы  платы, выбрав одну строку текста в качестве типа столбца.  </span><span class="sxs-lookup"><span data-stu-id="44443-118">In SharePoint, you'll need to create a **For Payout** list and include columns for **Client**, **Contractor**, and **Fee amount**, selecting **Single line of text** as the column type.</span></span> <span data-ttu-id="44443-119">В качестве вкладки  Teams в канале управления контрактами необходимо добавить список для выплат, аналогичный тому, что вы будете делать для вкладки [ **"Контракты".**](solution-manage-contracts-step2.md#attach-your-sharepoint-document-library-to-the-contracts-tab) Вкладка **For Payout** будет перечислять все контракты, которые необходимо будет представить для оплаты.</span><span class="sxs-lookup"><span data-stu-id="44443-119">You'll need to add the **For Payout** list as a Teams tab in the Contract Management channel, similar to [what you'll do for the **Contracts** tab](solution-manage-contracts-step2.md#attach-your-sharepoint-document-library-to-the-contracts-tab). The **For Payout** tab will list all contracts that will need to be submitted for payment.</span></span> <span data-ttu-id="44443-120">Вы можете легко расширить это решение, чтобы вместо этого написать эту информацию непосредственно в стороннее финансовое приложение (например, Dynamics CRM).</span><span class="sxs-lookup"><span data-stu-id="44443-120">You can easily extend this solution to instead write this information directly to a third-party financial application (for example, Dynamics CRM).</span></span> 


## <a name="attach-your-sharepoint-document-library-to-the-contracts-tab"></a><span data-ttu-id="44443-121">Прикрепите библиотеку SharePoint документов к вкладке Контракты</span><span class="sxs-lookup"><span data-stu-id="44443-121">Attach your SharePoint document library to the Contracts tab</span></span>

<span data-ttu-id="44443-122">После создания вкладки **"Контракты"** в канале управления контрактами необходимо прикрепить к нему SharePoint [документации.](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b)</span><span class="sxs-lookup"><span data-stu-id="44443-122">After you create a **Contracts** tab in your Contracts Management channel, you need to [attach your SharePoint document library to it](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b).</span></span> <span data-ttu-id="44443-123">Библиотека SharePoint документов, которую вы хотите прикрепить, — это библиотека, в которой вы применяли SharePoint Syntex модели понимания документов в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="44443-123">The SharePoint document library you want to attach is the one in which you applied your SharePoint Syntex document understanding model to in the previous section.</span></span>

<span data-ttu-id="44443-124">После прикрепления SharePoint документа вы сможете просматривать любые секретные контракты с помощью представления списка по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="44443-124">After you attach the SharePoint document library, you'll be able to view any classified contracts through a default list view.</span></span>

   ![Представление списка SharePoint библиотеки.](../media/content-understanding/list-view.png)

## <a name="customize-your-contracts-tab-tile-view"></a><span data-ttu-id="44443-126">Настройка представления плитки вкладок Contracts</span><span class="sxs-lookup"><span data-stu-id="44443-126">Customize your Contracts tab tile view</span></span>

> [!NOTE]
> <span data-ttu-id="44443-127">В этом разделе ссылаются на примеры кода, [содержащиеся](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) вContractTileFormatting.jsфайле, который включен в репозиторий решения по управлению [контрактами.](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management)</span><span class="sxs-lookup"><span data-stu-id="44443-127">This section references code examples that are contained in the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file that is included in the [Contracts Management Solution Assets repository](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management).</span></span>

<span data-ttu-id="44443-128">Хотя Teams позволяет просматривать контракты в представлении плитки, может потребоваться настроить его для просмотра данных контрактов, которые необходимо сделать видимыми на карточке контракта.</span><span class="sxs-lookup"><span data-stu-id="44443-128">While Teams lets you view your contracts in a tile view, you might want to customize it to view the contract data you want to make visible in the contract card.</span></span> <span data-ttu-id="44443-129">Например, для вкладки **"Контракты"** важно, чтобы участники видели на карточке контракта сумму клиента, подрядчика и сумму платы.</span><span class="sxs-lookup"><span data-stu-id="44443-129">For example, for the **Contracts** tab, it is important for members to see the client, contractor, and fee amount on the contract card.</span></span> <span data-ttu-id="44443-130">Все эти поля извлекались из каждого контракта с помощью SharePoint Syntex модели, применяемой в библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="44443-130">All of these fields were extracted from each contract through your SharePoint Syntex model that was applied to your document library.</span></span> <span data-ttu-id="44443-131">Кроме того, необходимо изменить планку заголовки плитки на разные цвета для каждого состояния, чтобы участники могли легко видеть, где находится контракт в процессе утверждения.</span><span class="sxs-lookup"><span data-stu-id="44443-131">You also want to be able to change the tile header bar to different colors for each status so that members can easily see where the contract is in the approval process.</span></span> <span data-ttu-id="44443-132">Например, во всех утвержденных контрактах будет синяя заголовка.</span><span class="sxs-lookup"><span data-stu-id="44443-132">For example, all approved contracts will have a blue header bar.</span></span>

   ![Представление плитки SharePoint библиотеки.](../media/content-understanding/tile.png)

<span data-ttu-id="44443-134">Пользовательский вид плитки, который вы используете, требует внесения изменений в файл JSON, используемый для формата текущего представления плитки.</span><span class="sxs-lookup"><span data-stu-id="44443-134">The custom tile view you use requires you to make changes to the JSON file used to format the current tile view.</span></span> <span data-ttu-id="44443-135">Вы можете ссылаться на файл JSON, используемый для создания представления карты,ContractTileFormatting.js[ в](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) файле.</span><span class="sxs-lookup"><span data-stu-id="44443-135">You can reference the JSON file used to create the card view by looking at the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file.</span></span> <span data-ttu-id="44443-136">В следующих разделах вы увидите определенные разделы кода для функций, которые находятся в карточках контрактов.</span><span class="sxs-lookup"><span data-stu-id="44443-136">In the following sections, you'll see specific sections of the code for features that are in the contract cards.</span></span>

<span data-ttu-id="44443-137">Если вы хотите увидеть или внести изменения в код JSON для просмотра в канале Teams, в канале Teams, выберите выпадаемое меню представления, а затем выберите текущее представление **Format**.</span><span class="sxs-lookup"><span data-stu-id="44443-137">If you want to see or make changes to the JSON code for your view in your Teams channel, in the Teams channel, select the view drop-down menu, and then select **Format current view**.</span></span>

   ![Снимок экрана формата json в Teams канале.](../media/content-understanding/jason-format.png)

## <a name="card-size-and-shape"></a><span data-ttu-id="44443-139">Размер и форма карты</span><span class="sxs-lookup"><span data-stu-id="44443-139">Card size and shape</span></span>

<span data-ttu-id="44443-140">ВContractTileFormatting.js[ в](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) файле см. следующий раздел, чтобы увидеть код формата размера и формы карты.</span><span class="sxs-lookup"><span data-stu-id="44443-140">In the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file, look at the following section to see the code for how the size and shape of the card is formatted.</span></span>

```JSON
                  {
                    "elmType": "div",
                    "style": {
                      "background-color": "#f5f5f5",
                      "padding": "5px",
                      "width": "180px"
                    },
                    "children": [
                      {
                        "elmType": "img",
                        "attributes": {
                          "src": "@thumbnail.large"
                        },
                        "style": {
                          "width": "185px",
                          "height": "248px"
                        }
                      }
```

## <a name="contract-status"></a><span data-ttu-id="44443-141">Состояние контракта</span><span class="sxs-lookup"><span data-stu-id="44443-141">Contract status</span></span>

<span data-ttu-id="44443-142">Следующий код позволяет определить состояние каждой титульной карточки.</span><span class="sxs-lookup"><span data-stu-id="44443-142">The following code lets you define the status of each title card.</span></span> <span data-ttu-id="44443-143">Обратите внимание, что каждое значение состояния *(New,* *In review,* *Approved* и *Rejected)* будет отображать различные цветовые коды для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="44443-143">Note that each status value (*New*, *In review*, *Approved*, and *Rejected*) will display a different color code for each.</span></span> <span data-ttu-id="44443-144">ВContractTileFormatting.js[ в](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) файле посмотрите раздел, который определяет состояние.</span><span class="sxs-lookup"><span data-stu-id="44443-144">In the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file, look at the section that defines the status.</span></span>

```JSON
          {
            "elmType": "div",
            "children": [
              {
                "elmType": "div",
                "style": {
                  "color": "white",
                  "background-color": "=if([$Status] == 'New', '#00b7c3', if([$Status] == 'In review', '#ffaa44', if([$Status] == 'Approved', '#0078d4', if([$Status] == 'Rejected', '#d13438', '#8378de'))))",
                  "padding": "5px 15px",
                  "height": "auto",
                  "text-transform": "uppercase",
                  "font-size": "12.5px"
                },
                "txtContent": "[$Status]"
              }
```

## <a name="extracted-fields"></a><span data-ttu-id="44443-145">Извлеченные поля</span><span class="sxs-lookup"><span data-stu-id="44443-145">Extracted fields</span></span>

<span data-ttu-id="44443-146">Каждая карта контракта будет отображать три поля, извлеченные для каждого контракта *(клиент,* *подрядчик* и *сумма платы).*</span><span class="sxs-lookup"><span data-stu-id="44443-146">Each contract card will display three fields that were extracted for each contract (*Client*, *Contractor*, and *Fee Amount*).</span></span> <span data-ttu-id="44443-147">Кроме того, необходимо также отобразить время и дату классификации файла SharePoint Syntex модели, используемой для его идентификации.</span><span class="sxs-lookup"><span data-stu-id="44443-147">Additionally, you also want to display the time/date that the file was classified by the SharePoint Syntex model used to identify it.</span></span>

<span data-ttu-id="44443-148">ВContractTileFormatting.js[ файле](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) указанные ниже разделы определяют каждый из них.</span><span class="sxs-lookup"><span data-stu-id="44443-148">In the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file, the following sections define each of these.</span></span>

### <a name="client"></a><span data-ttu-id="44443-149">Клиент</span><span class="sxs-lookup"><span data-stu-id="44443-149">Client</span></span>

<span data-ttu-id="44443-150">В этом разделе определяется, как "Клиент" будет отображаться на карте, и используется значение для конкретного контракта.</span><span class="sxs-lookup"><span data-stu-id="44443-150">This section defines how "Client" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px"
                        },
                        "txtContent": "Client"
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "16px",
                          "font-weight": "600"
                        },
                        "txtContent": "[$Client]"
                      },
```

### <a name="contractor"></a><span data-ttu-id="44443-151">Подрядчик</span><span class="sxs-lookup"><span data-stu-id="44443-151">Contractor</span></span>

<span data-ttu-id="44443-152">В этом разделе определяется, как "Подрядчик" будет отображаться на карте, и используется значение для конкретного контракта.</span><span class="sxs-lookup"><span data-stu-id="44443-152">This section defines how the "Contractor" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                        {
                            "elmType": "div",
                            "txtContent": "Contractor",
                            "style": {
                              "color": "#767676",
                              "font-size": "12px",
                              "margin-bottom": "2px"
                            }
                          },
                          {
                            "elmType": "div",
                            "style": {
                              "margin-bottom": "12px",
                              "font-size": "14px"
                            },
                            "txtContent": "[$Contractor]"
                          },
```

### <a name="fee-amount"></a><span data-ttu-id="44443-153">Сумма гонорара</span><span class="sxs-lookup"><span data-stu-id="44443-153">Fee amount</span></span>

<span data-ttu-id="44443-154">В этом разделе определяется, как "Сумма платы" будет отображаться на карте, и используется значение для конкретного контракта.</span><span class="sxs-lookup"><span data-stu-id="44443-154">This section defines how the "Fee Amount" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "txtContent": "Fee amount",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px",
                          "margin-bottom": "2px"
                        }
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "14px"
                        },
                        "txtContent": "[$FeeAmount]"
                      },
```

### <a name="classification-date"></a><span data-ttu-id="44443-155">Дата классификации</span><span class="sxs-lookup"><span data-stu-id="44443-155">Classification date</span></span>

<span data-ttu-id="44443-156">В этом разделе определяется, как "Классификация" будет отображаться на карте, и используется значение для конкретного контракта.</span><span class="sxs-lookup"><span data-stu-id="44443-156">This section defines how "Classification" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "txtContent": "Classified",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px",
                          "margin-bottom": "2px"
                        }
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "14px"
                        },
                        "txtContent": "[$PrimeLastClassified]"
                      }
```

## <a name="next-step"></a><span data-ttu-id="44443-157">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="44443-157">Next step</span></span>

[<span data-ttu-id="44443-158">Шаг 3. Используйте Power Automate для создания потока для обработки контрактов</span><span class="sxs-lookup"><span data-stu-id="44443-158">Step 3. Use Power Automate to create your flow to process your contracts</span></span>](solution-manage-contracts-step3.md)
