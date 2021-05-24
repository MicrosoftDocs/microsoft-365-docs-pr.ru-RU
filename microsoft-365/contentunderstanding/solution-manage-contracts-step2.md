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
ms.openlocfilehash: 81d5fe34383453b187363b13c21ef47844948193
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636186"
---
# <a name="step-2-use-microsoft-teams-to-create-your-contract-management-channel"></a>Этап 2. Используйте Microsoft Teams для создания канала управления контрактами

Когда организация создает решение по управлению контрактами, необходимо центральное расположение, в котором заинтересованные стороны могут просмотреть и управлять контрактами. Для этого можно использовать [](https://docs.microsoft.com/microsoftteams/) Microsoft Teams для Teams канала и использовать функции в Teams:

- **Создайте расположение для заинтересованных сторон, чтобы легко видеть все контракты, которые требуют действий.** Например, в Teams вы можете создать вкладку **Контракты** в канале управления контрактами, в которой участники смогут увидеть полезное представление плитки для всех контрактов, которые требуют утверждения. Вы также можете настроить представление таким образом, чтобы каждая "карта" перечисляла важные данные, которые вам важны (например, клиент, *подрядчик* и сумма *платы).*

     ![Вкладка Контракты.](../media/content-understanding/tile-view.png)

- **У участников есть расположение, чтобы взаимодействовать друг с другом и видеть важные события.** Например, в Teams вкладка **"Сообщения"** можно использовать для бесед, получения обновлений и действий (например, для участника, отклонить контракт). Если что-то произошло (например, новый контракт, отправленный на утверждение), вкладка **Posts** может использоваться не только для его анонса, но и для записи. Если участники подписываются на уведомления, они будут получать уведомления при обновлении. 

     ![Вкладка "Сообщения".](../media/content-understanding/posts.png)</br> 

- **У вас есть расположение для участников, чтобы увидеть утвержденные контракты, чтобы узнать, когда они могут быть отправлены для оплаты.** В Teams вы можете создать канал <b>для</b> оплаты, который будет перечислять все контракты, которые необходимо будет представить для оплаты. Вы можете легко расширить это решение, чтобы вместо этого написать эту информацию непосредственно в стороннее финансовое приложение (например, Dynamics CRM).

## <a name="attach-your-sharepoint-document-library-to-the-contracts-tab"></a>Прикрепите библиотеку SharePoint документов к вкладке Контракты 

После создания вкладки **"Контракты"** в канале управления контрактами необходимо прикрепить к нему SharePoint [документации.](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b) Библиотека SharePoint документов, к которой необходимо прикрепить, — это библиотека документов, в которой вы применяли SharePoint синтексовскую модель понимания документов в предыдущем разделе.

После прикрепления SharePoint документа вы сможете просматривать любые секретные контракты с помощью представления списка по умолчанию.

   ![Представление списка.](../media/content-understanding/list-view.png) 

## <a name="customize-your-contracts-tab-tile-view"></a>Настройка представления плитки вкладок Contracts

> [!NOTE]
> В этом разделе ссылаются на примеры кода, [содержащиеся](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) вContractTileFormatting.jsфайле, который включен в репозиторий решения по управлению [контрактами.](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management)

Хотя Teams позволяет просматривать контракты в представлении плитки, может потребоваться настроить его для просмотра данных контрактов, которые необходимо сделать видимыми на карточке контракта. Например, для вкладки **"Контракты"** важно, чтобы участники видели на карточке контракта сумму клиента, подрядчика и сумму платы. Все эти поля извлекались из каждого контракта с помощью модели SharePoint Syntex, которая была применена к библиотеке документов. Кроме того, необходимо изменить планку заголовки плитки на разные цвета для каждого состояния, чтобы участники могли легко видеть, где находится контракт в процессе утверждения. Например, во всех утвержденных контрактах будет синяя заголовка.

   ![Представление списка.](../media/content-understanding/tile.png)

Пользовательский вид плитки, который вы используете, требует внесения изменений в файл JSON, используемый для формата текущего представления плитки. Вы можете ссылаться на файл JSON, используемый для создания представления карты,ContractTileFormatting.js[ в](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) файле. В следующих разделах вы увидите определенные разделы кода для функций, которые находятся в карточках контрактов.

Если вы хотите увидеть или внести изменения в код JSON для просмотра в канале Teams, в канале Teams, выберите выпадаемое меню представления, а затем выберите текущее представление **Format**.

   ![json format.](../media/content-understanding/jason-format.png) 

## <a name="card-size-and-shape"></a>Размер и форма карты

ВContractTileFormatting.js[ в](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) файле см. следующий раздел, чтобы увидеть код формата размера и формы карты.

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


## <a name="contract-status"></a>Состояние контракта

Следующий код позволяет определить состояние каждой титульной карточки. Обратите внимание, что каждое значение состояния *(New,* *In review,* *Approved* и *Rejected)* будет отображать различные цветовые коды для каждого из них. ВContractTileFormatting.js[ в](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) файле посмотрите раздел, который определяет состояние.

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


## <a name="extracted-fields"></a>Извлеченные поля

Каждая карта контракта будет отображать три поля, извлеченные для каждого контракта *(клиент,* *подрядчик* и *сумма платы).* Кроме того, необходимо также отобразить время и дату классификации файла по модели SharePoint Syntex, используемой для его идентификации. 

ВContractTileFormatting.js[ файле](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) указанные ниже разделы определяют каждый из них.

### <a name="client"></a>Клиент

В этом разделе определяется, как "Клиент" будет отображаться на карте, и используется значение для конкретного контракта.

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

### <a name="contractor"></a>Подрядчик

В этом разделе определяется, как "Подрядчик" будет отображаться на карте, и используется значение для конкретного контракта.

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


### <a name="fee-amount"></a>Сумма платы

В этом разделе определяется, как "Сумма платы" будет отображаться на карте, и используется значение для конкретного контракта.

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



### <a name="classification-date"></a>Дата классификации

В этом разделе определяется, как "Классификация" будет отображаться на карте, и используется значение для конкретного контракта.

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

## <a name="next-step"></a>Следующий шаг

[Шаг 3. Используйте Power Automate для создания потока для обработки контрактов](solution-manage-contracts-step3.md)
