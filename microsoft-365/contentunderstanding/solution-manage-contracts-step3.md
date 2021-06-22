---
title: Шаг 3. Используйте Power Automate для создания потока для обработки контрактов
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
description: Узнайте, как использовать Power Automate для создания потока для обработки контрактов с помощью Microsoft 365 решения.
ms.openlocfilehash: e6c1d1e53363f996241efb2394189853d840c6c2
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054470"
---
# <a name="step-3-use-power-automate-to-create-your-flow-to-process-your-contracts"></a><span data-ttu-id="1e057-104">Этап 3.</span><span class="sxs-lookup"><span data-stu-id="1e057-104">Step 3.</span></span> <span data-ttu-id="1e057-105">Используйте Power Automate для создания потока для обработки контрактов</span><span class="sxs-lookup"><span data-stu-id="1e057-105">Use Power Automate to create your flow to process your contracts</span></span>

<span data-ttu-id="1e057-106">Вы создали канал управления контрактами и прикрепили SharePoint библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="1e057-106">You've created your Contract Management channel and have attached your SharePoint document library.</span></span> <span data-ttu-id="1e057-107">Следующий шаг — создание потока Power Automate обработки контрактов, которые идентифицирует и классифицирует SharePoint Syntex модель.</span><span class="sxs-lookup"><span data-stu-id="1e057-107">The next step is to create a Power Automate flow to process your contracts that your SharePoint Syntex model identifies and classifies.</span></span> <span data-ttu-id="1e057-108">Вы можете сделать этот шаг, [создав поток Power Automate в библиотеке](https://support.microsoft.com/office/create-a-flow-for-a-list-or-library-in-sharepoint-or-onedrive-a9c3e03b-0654-46af-a254-20252e580d01)SharePoint документов.</span><span class="sxs-lookup"><span data-stu-id="1e057-108">You can do this step by [creating a Power Automate flow in your SharePoint document library](https://support.microsoft.com/office/create-a-flow-for-a-list-or-library-in-sharepoint-or-onedrive-a9c3e03b-0654-46af-a254-20252e580d01).</span></span>

<span data-ttu-id="1e057-109">Для решения управления контрактами необходимо создать поток Power Automate для следующих действий:</span><span class="sxs-lookup"><span data-stu-id="1e057-109">For your contracts management solution, you want to create a Power Automate flow to do the following actions:</span></span>

-  <span data-ttu-id="1e057-110">После того как контракт классифицируется SharePoint Syntex моделью, измените состояние контракта на **"В обзоре".**</span><span class="sxs-lookup"><span data-stu-id="1e057-110">After a contract has been classified by your SharePoint Syntex model, change the contract status to **In review**.</span></span>
- <span data-ttu-id="1e057-111">Затем контракт пересматривается и утверждается или отклоняется.</span><span class="sxs-lookup"><span data-stu-id="1e057-111">The contract is then reviewed and is either approved or rejected.</span></span>
- <span data-ttu-id="1e057-112">Для утвержденных контрактов сведения о контракте вывешив на вкладке для обработки платежей.</span><span class="sxs-lookup"><span data-stu-id="1e057-112">For approved contracts, the contract information is posted to a tab for payment processing.</span></span>
- <span data-ttu-id="1e057-113">Для отклоненных контрактов команда уведомлена для дальнейшего анализа.</span><span class="sxs-lookup"><span data-stu-id="1e057-113">For rejected contracts, the team is notified for further analysis.</span></span> 

<span data-ttu-id="1e057-114">На следующей схеме показан Power Automate для решения по управлению контрактами.</span><span class="sxs-lookup"><span data-stu-id="1e057-114">The following diagram shows the Power Automate flow for the contract management solution.</span></span>

![Flow схема, показывающая все решение.](../media/content-understanding/flow-entire-process.png)

## <a name="prepare-your-contract-for-review"></a><span data-ttu-id="1e057-116">Подготовка контракта для проверки</span><span class="sxs-lookup"><span data-stu-id="1e057-116">Prepare your contract for review</span></span>

<span data-ttu-id="1e057-117">При выявлении и классификации контракта SharePoint Syntex модели понимания документов поток Power Automate сначала изменит состояние на **"В обзоре".**</span><span class="sxs-lookup"><span data-stu-id="1e057-117">When a contract is identified and classified by your SharePoint Syntex document understanding model, the Power Automate flow will first change the status to **In review**.</span></span>

![Состояние обновления.](../media/content-understanding/flow-overview.png)

<span data-ttu-id="1e057-119">После проверки файла измените значение состояния на **"В обзоре".**</span><span class="sxs-lookup"><span data-stu-id="1e057-119">After checking out the file, change the status value to **In review**.</span></span>

![В состоянии проверки.](../media/content-understanding/in-review.png)

<span data-ttu-id="1e057-121">На следующем этапе необходимо создать адаптивную карту, указывав, что контракт ожидает рассмотрения и отправки в канал управления контрактами.</span><span class="sxs-lookup"><span data-stu-id="1e057-121">The next step is to create an adaptive card stating that the contract is waiting for review and posting it to the Contract Management channel.</span></span>

![Сообщение о просмотре контракта.](../media/content-understanding/contract-approval-post.png)


![Создание адаптивной карты для проверки.](../media/content-understanding/adaptive-card.png)

<span data-ttu-id="1e057-124">Ниже приводится код JSON, используемый для этого шага в потоке Power Automate.</span><span class="sxs-lookup"><span data-stu-id="1e057-124">The following code is the JSON used for this step in the Power Automate flow.</span></span>

```JSON
{
"$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
"type": "AdaptiveCard",
"version": "1.0",
"body": [
    {
    "type": "TextBlock",
    "text": "Contract approval request",
    "size": "large",
    "weight": "bolder",
     "wrap": true
    },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Date created",
                            "value": "@{triggerOutputs()?['body/Modified']} "
                        },
                        {
                            "title": "Link",
                            "value": "[@{triggerOutputs()?['body/{FilenameWithExtension}']}](@{triggerOutputs()?['body/{Link}']})"
                        }
                    ]
                }
            ]
         },
    {
    "type": "TextBlock",
    "text": "Comment:"
    },
        {
            "type": "Input.Text",
            "placeholder": "Enter comments",
            "id": "acComments"
        }
],
"actions": [
    {
    "type": "Action.Submit",
    "title": "Approve",
    "data": {
        "x": "Approve"
    }
    },
    {
    "type": "Action.Submit",
    "title": "Reject",
    "data": {
        "x": "Reject"
    }
    }
]
}
```


## <a name="conditional-context"></a><span data-ttu-id="1e057-125">Условный контекст</span><span class="sxs-lookup"><span data-stu-id="1e057-125">Conditional context</span></span>

<span data-ttu-id="1e057-126">В потоке далее необходимо создать условие, при котором [](#if-the-contract-is-approved) ваш контракт будет либо утвержден, либо [отклонен.](#if-the-contract-is-rejected)</span><span class="sxs-lookup"><span data-stu-id="1e057-126">In your flow, next you need to create a condition in which your contract will be either  [approved](#if-the-contract-is-approved) or [rejected](#if-the-contract-is-rejected).</span></span>

![Условный.](../media/content-understanding/condition.png)

## <a name="if-the-contract-is-approved"></a><span data-ttu-id="1e057-128">Если контракт утвержден</span><span class="sxs-lookup"><span data-stu-id="1e057-128">If the contract is approved</span></span>

<span data-ttu-id="1e057-129">После утверждения контракта возникают следующие вещи:</span><span class="sxs-lookup"><span data-stu-id="1e057-129">When a contract has been approved, the following things occur:</span></span>

- <span data-ttu-id="1e057-130">На **вкладке "Контракты"** состояние карты контракта будет изменяться на **"Утверждено".**</span><span class="sxs-lookup"><span data-stu-id="1e057-130">On the **Contracts** tab, the status in the contract card will change to **Approved**.</span></span>

   ![Состояние карты утверждено.](../media/content-understanding/approved-contracts-tab.png)

- <span data-ttu-id="1e057-132">В потоке состояние изменено на **"Утверждено".**</span><span class="sxs-lookup"><span data-stu-id="1e057-132">In your flow, the status is changed to **Approved**.</span></span>

   ![Flow статус утвержден.](../media/content-understanding/status-approved.png)

- <span data-ttu-id="1e057-134">В этом решении данные о контракте будут добавлены на вкладку **For Payout,** чтобы можно было управлять выплатами.</span><span class="sxs-lookup"><span data-stu-id="1e057-134">In this solution, the contract data will be added to the **For Payout** tab so that the payouts can be managed.</span></span> <span data-ttu-id="1e057-135">Этот процесс можно расширить, чтобы разрешить потоку отправлять контракты на оплату сторонним финансовым приложением (например, Dynamics CRM).</span><span class="sxs-lookup"><span data-stu-id="1e057-135">This process can be extended to allow the flow to submit the contracts for payment by a third-party financial application (for example, Dynamics CRM).</span></span>

   ![Контракт перенесен в Pay Out.](../media/content-understanding/for-payout.png)

- <span data-ttu-id="1e057-137">В потоке создается следующий элемент для перемещения утвержденных контрактов на вкладку **For Payout.**</span><span class="sxs-lookup"><span data-stu-id="1e057-137">In the flow, you create the following item to move approved contracts to the **For Payout** tab.</span></span>

   ![Flow элемент для перемещения в Pay Out.](../media/content-understanding/ready-for-payout.png)

    <span data-ttu-id="1e057-139">Чтобы получить выражения для сведений, необходимых с Teams карты, используйте значения, показанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="1e057-139">To get the expressions for the information needed from the Teams card, use the values shown in the following table.</span></span>
 
    |<span data-ttu-id="1e057-140">Имя</span><span class="sxs-lookup"><span data-stu-id="1e057-140">Name</span></span>     |<span data-ttu-id="1e057-141">Expression</span><span class="sxs-lookup"><span data-stu-id="1e057-141">Expression</span></span> |
    |---------|-----------|
    | <span data-ttu-id="1e057-142">Состояние утверждения</span><span class="sxs-lookup"><span data-stu-id="1e057-142">Approval state</span></span>  | <span data-ttu-id="1e057-143">body ('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?? ['submitActionId']</span><span class="sxs-lookup"><span data-stu-id="1e057-143">body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['submitActionId']</span></span>         |
    | <span data-ttu-id="1e057-144">Утверждено</span><span class="sxs-lookup"><span data-stu-id="1e057-144">Approved by</span></span>     | <span data-ttu-id="1e057-145">body ('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?? ['responder'] ['displayName']</span><span class="sxs-lookup"><span data-stu-id="1e057-145">body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responder']['displayName']</span></span>        |
    | <span data-ttu-id="1e057-146">Дата утверждения</span><span class="sxs-lookup"><span data-stu-id="1e057-146">Approval date</span></span>     | <span data-ttu-id="1e057-147">body ('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?? ['responseTime']</span><span class="sxs-lookup"><span data-stu-id="1e057-147">body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responseTime']</span></span>         |
    | <span data-ttu-id="1e057-148">Примечание</span><span class="sxs-lookup"><span data-stu-id="1e057-148">Comment</span></span>     | <span data-ttu-id="1e057-149">body ('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?? ['data'] ['acComments']</span><span class="sxs-lookup"><span data-stu-id="1e057-149">body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['data']['acComments']</span></span>         |
    
    <span data-ttu-id="1e057-150">В следующем примере показано, как использовать формулу в Power Automate для записи выражения.</span><span class="sxs-lookup"><span data-stu-id="1e057-150">The following example shows how to use the formula box in Power Automate to write an expression.</span></span>

   ![Снимок экрана Power Automate с указанием формулы выражения.](../media/content-understanding/expression-formula-power-automate.png)    

- <span data-ttu-id="1e057-152">Адаптивная карта, указывательная, что контракт утвержден, создается и вывешиваться в канале управления контрактами.</span><span class="sxs-lookup"><span data-stu-id="1e057-152">An adaptive card stating that the contract has been approved is created and posted to the Contract Management channel.</span></span>

   ![Опубликовано утверждение контракта.](../media/content-understanding/adaptive-card-approval.png)

   ![Утверждение адаптивной карты.](../media/content-understanding/adaptive-card.png)


   <span data-ttu-id="1e057-155">Ниже приводится код JSON, используемый для этого шага в потоке Power Automate.</span><span class="sxs-lookup"><span data-stu-id="1e057-155">The following code is the JSON used for this step in the Power Automate flow.</span></span>

```JSON
{ 
    "type": "AdaptiveCard",
    "body": [
        {
            "type": "Container",
            "style": "emphasis",
            "items": [
                {
                    "type": "ColumnSet",
                    "columns": [
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "size": "Large",
                                    "weight": "Bolder",
                                    "text": "CONTRACT APPROVED"
                                }
                            ],
                            "width": "stretch"
                        }
                    ]
                }
            ],
            "bleed": true
        },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Approval by",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responder']['displayName']}"
                        },
                        {
                            "title": "Approved date",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responseTime']}"
                        },
                        {
                            "title": "Approval comment",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['data']['acComments']}"
                        },
                        {
                            "title": " ",
                            "value": " "
                        },
                        {
                            "title": "Status",
                            "value": "Ready for payout"
                        }
                    ]
                }
            ]
        }
    ],
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "version": "1.2",
    "fallbackText": "This card requires Adaptive Cards v1.2 support to be rendered properly."
}
```

## <a name="if-the-contract-is-rejected"></a><span data-ttu-id="1e057-156">Если контракт отклонен</span><span class="sxs-lookup"><span data-stu-id="1e057-156">If the contract is rejected</span></span>

<span data-ttu-id="1e057-157">При отклонении контракта возникают следующие действия:</span><span class="sxs-lookup"><span data-stu-id="1e057-157">When a contract has been rejected, the following things occur:</span></span>

- <span data-ttu-id="1e057-158">На **вкладке Контракты** состояние карты контракта будет изменяться на **Отклонено.**</span><span class="sxs-lookup"><span data-stu-id="1e057-158">On the **Contracts** tab, the status in the contract card will change to **Rejected**.</span></span>

   ![Состояние карты отклонено.](../media/content-understanding/rejected-contracts-tab.png)

- <span data-ttu-id="1e057-160">В потоке проверьте файл контракта, измените состояние на **Отклонено,** а затем проверьте файл обратно.</span><span class="sxs-lookup"><span data-stu-id="1e057-160">In your flow, you check out the contract file, change the status to **Rejected**, and then check the file back in.</span></span>

   ![Flow отклоняется в файле контракта.](../media/content-understanding/reject-flow.png)

- <span data-ttu-id="1e057-162">В потоке создается адаптивная карта, указывляемая, что контракт отклонен.</span><span class="sxs-lookup"><span data-stu-id="1e057-162">In your flow, you create an adaptive card stating that the contract has been rejected.</span></span>

   ![Flow состояния отклоняется на адаптивной карте.](../media/content-understanding/reject-flow-item.png)

<span data-ttu-id="1e057-164">Ниже приводится код JSON, используемый для этого шага в потоке Power Automate.</span><span class="sxs-lookup"><span data-stu-id="1e057-164">The following code is the JSON used for this step in the Power Automate flow.</span></span>

```JSON
{ 
    "type": "AdaptiveCard",
    "body": [
        {
            "type": "Container",
            "style": "attention",
            "items": [
                {
                    "type": "ColumnSet",
                    "columns": [
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "size": "Large",
                                    "weight": "Bolder",
                                    "text": "CONTRACT REJECTED"
                                }
                            ],
                            "width": "stretch"
                        }
                    ]
                }
            ],
            "bleed": true
        },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Rejected by",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responder']['displayName']}"
                        },
                        {
                            "title": "Rejected date",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responseTime']}"
                        },
                        {
                            "title": "Comment",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['data']['acComments']}"
                        },
                        {
                            "title": " ",
                            "value": " "
                        },
                        {
                            "title": "Status",
                            "value": "Needs review"
                        }
                    ]
                }
            ]
        }
    ],
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "version": "1.2",
    "fallbackText": "This card requires Adaptive Cards v1.2 support to be rendered properly."
}
```

- <span data-ttu-id="1e057-165">Карта размещена в канале управления контрактами.</span><span class="sxs-lookup"><span data-stu-id="1e057-165">The card is posted in the Contract Management channel.</span></span>

   ![Flow адаптивную карту отклонить.](../media/content-understanding/rejected.png)