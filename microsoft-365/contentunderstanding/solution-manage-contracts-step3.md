---
title: Шаг 3. Используйте Power Automate для создания потока для обработки контрактов
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/19/2021
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Узнайте, как использовать Power Automate для создания потока для обработки контрактов с помощью Microsoft 365 решения.
ms.openlocfilehash: 54e92f36b19cefde92111cdbc960fad7715cf8b0
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583104"
---
# <a name="step-3-use-power-automate-to-create-your-flow-to-process-your-contracts"></a>Этап 3. Используйте Power Automate для создания потока для обработки контрактов

Вы создали канал управления контрактами и прикрепили SharePoint библиотеку документов. Следующий шаг — создание потока Power Automate обработки контрактов, которые идентифицирует и классифицирует SharePoint syntex. Вы можете сделать этот шаг, [создав поток Power Automate в библиотеке](https://support.microsoft.com/office/create-a-flow-for-a-list-or-library-in-sharepoint-or-onedrive-a9c3e03b-0654-46af-a254-20252e580d01)SharePoint документов.

Для решения управления контрактами необходимо создать поток Power Automate для следующих действий:

-  После того, как контракт был классифицирован SharePoint моделью Syntex, измените состояние контракта на **In review**.
- Затем контракт пересматривается и утверждается или отклоняется.
- Для утвержденных контрактов сведения о контракте вывешив на вкладке для обработки платежей.
- Для отклоненных контрактов команда уведомлена для дальнейшего анализа. 

На следующей схеме показан Power Automate для решения по управлению контрактами.

![Flow схема, показывающая все решение.](../media/content-understanding/flow-entire-process.png)

## <a name="prepare-your-contract-for-review"></a>Подготовка контракта для проверки

При выявлении и классификации контракта SharePoint модели понимания документов Syntex поток Power Automate сначала изменит состояние на **Обзор**.

![Состояние обновления.](../media/content-understanding/flow-overview.png)

После проверки файла измените значение состояния на **"В обзоре".**

![В состоянии проверки.](../media/content-understanding/in-review.png)

На следующем этапе необходимо создать адаптивную карту, указывав, что контракт ожидает рассмотрения и отправки в канал управления контрактами.

![Сообщение о просмотре контракта.](../media/content-understanding/contract-approval-post.png)


![Создание адаптивной карты для проверки.](../media/content-understanding/adaptive-card.png)

Ниже приводится код JSON, используемый для этого шага в потоке Power Automate.

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


## <a name="conditional"></a>Условный

В потоке далее необходимо создать условие, при котором ваш контракт будет либо утвержден, либо отклонен.

![Условный.](../media/content-understanding/condition.png)

## <a name="if-the-contract-is-approved"></a>Если контракт утвержден

После утверждения контракта возникают следующие вещи:

- На **вкладке "Контракты"** состояние карты контракта будет изменяться на **"Утверждено".**

   ![Состояние карты утверждено.](../media/content-understanding/approved-contracts-tab.png)

- В потоке состояние изменено на **"Утверждено".**

   ![Flow статус утвержден.](../media/content-understanding/status-approved.png)

- В этом решении данные о контракте будут добавлены на вкладку **For Payout,** чтобы можно было управлять выплатами. Этот процесс можно расширить, чтобы разрешить потоку отправлять контракты на оплату сторонним финансовым приложением (например, Dynamics CRM).

   ![Контракт перенесен в Pay Out.](../media/content-understanding/for-payout.png)

- В потоке создается следующий элемент для перемещения утвержденных контрактов на вкладку **For Payout.**

   ![Flow элемент для перемещения в Pay Out.](../media/content-understanding/ready-for-payout.png)

- Адаптивная карта, указывательная, что контракт утвержден, создается и вывешиваться в канале управления контрактами.

   ![Опубликовано утверждение контракта.](../media/content-understanding/adaptive-card-approval.png)

   ![Утверждение адаптивной карты.](../media/content-understanding/adaptive-card.png)


   Ниже приводится код JSON, используемый для этого шага в потоке Power Automate.

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

## <a name="if-the-contract-is-rejected"></a>Если контракт отклонен

При отклонении контракта возникают следующие действия:

- На **вкладке Контракты** состояние карты контракта будет изменяться на **Отклонено.**

   ![Состояние карты отклонено.](../media/content-understanding/rejected-contracts-tab.png)

- В потоке проверьте файл контракта, измените состояние на **Отклонено,** а затем проверьте файл обратно.

   ![Flow статус отклонен.](../media/content-understanding/reject-flow.png)

- В потоке создается адаптивная карта, указывляемая, что контракт отклонен.

   ![Flow статус отклонен.](../media/content-understanding/reject-flow-item.png)

Ниже приводится код JSON, используемый для этого шага в потоке Power Automate.

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

- Карта размещена в канале управления контрактами.

   ![Flow адаптивную карту отклонить.](../media/content-understanding/rejected.png)