---
title: Архивация сторонних данных
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: Узнайте, как импортировать сторонние данные с платформ социальных сетей, платформы обмена мгновенными сообщениями и платформы совместной работы с документами в почтовые ящики Microsoft 365.
ms.openlocfilehash: 0db7019b607388b7c62fe19210b85b8410083f32
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035487"
---
# <a name="archive-third-party-data"></a><span data-ttu-id="2d556-103">Архивация сторонних данных</span><span class="sxs-lookup"><span data-stu-id="2d556-103">Archive third-party data</span></span>

<span data-ttu-id="2d556-104">Microsoft 365 позволяет администраторам импортировать и архивировать сторонние данные с платформ социальных сетей, платформ обмена мгновенными сообщениями и платформ совместной работы с документами в почтовые ящики в организации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2d556-104">Microsoft 365 lets administrators import and archive third-party data from social media platforms, instant messaging platforms, and document collaboration platforms, to mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="2d556-105">Примеры сторонних источников данных, которые можно импортировать в Microsoft 365, включают следующие службы:</span><span class="sxs-lookup"><span data-stu-id="2d556-105">Examples of third-party data sources that you can import to Microsoft 365 include the following services:</span></span> 
  
- <span data-ttu-id="2d556-106">**Социальные сети:** Facebook, LinkedIn, Twitter и Yammer</span><span class="sxs-lookup"><span data-stu-id="2d556-106">**Social:** Facebook, LinkedIn, Twitter, and Yammer</span></span>

- <span data-ttu-id="2d556-107">Обмен **мгновенными сообщениями:** Yahoo Messenger и Гуглеталк</span><span class="sxs-lookup"><span data-stu-id="2d556-107">**Instant messaging:** Yahoo Messenger and GoogleTalk</span></span>

- <span data-ttu-id="2d556-108">**Совместная работа с документами:** Box и DropBox</span><span class="sxs-lookup"><span data-stu-id="2d556-108">**Document collaboration:** Box and DropBox</span></span>

- <span data-ttu-id="2d556-109">**Вертикальные отрасли:** Управление взаимоотношениями с клиентами (например, Salesforce chatter;) и финансовые службы (например, Bloomberg и Thomson Reuters)</span><span class="sxs-lookup"><span data-stu-id="2d556-109">**Vertical industries:** Customer Relationship Management (such as Salesforce Chatter) and Financial Services (such as Bloomberg and Thomson Reuters)</span></span>

- <span data-ttu-id="2d556-110">**SMS/Text Messaging:** BlackBerry</span><span class="sxs-lookup"><span data-stu-id="2d556-110">**SMS/text messaging:** BlackBerry</span></span>

<span data-ttu-id="2d556-111">После импорта сторонних данных вы можете применять функции соответствия требованиям Microsoft 365, такие как хранение для судебного разбирательства, обнаружение электронных данных, Архивация на месте, аудит, соответствие требованиям и политики хранения для этих данных.</span><span class="sxs-lookup"><span data-stu-id="2d556-111">After third-party data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, Communication compliance, and retention policies to this data.</span></span> <span data-ttu-id="2d556-112">Например, при перемещении почтового ящика на хранение для судебного разбирательства сохраняются данные третьих лиц.</span><span class="sxs-lookup"><span data-stu-id="2d556-112">For example, when a mailbox is placed on Litigation Hold, third-party data is preserved.</span></span> <span data-ttu-id="2d556-113">С помощью средств обнаружения электронных данных Майкрософт можно выполнять поиск сторонних данных.</span><span class="sxs-lookup"><span data-stu-id="2d556-113">You can search third-party data by using Microsoft eDiscovery tools.</span></span> <span data-ttu-id="2d556-114">Кроме того, вы можете применять политики архивации и хранения к сторонним данным, как и к данным Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2d556-114">Or you can apply archiving and retention policies to third-party data just like you can for Microsoft data.</span></span> <span data-ttu-id="2d556-115">Коротко говоря, архивация сторонних данных в Microsoft 365 может помочь организации соответствовать государственным и нормативным политикам.</span><span class="sxs-lookup"><span data-stu-id="2d556-115">In short, archiving third-party data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

<span data-ttu-id="2d556-116">Существует два способа импорта и архивации сторонних данных в Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="2d556-116">There are two ways to import and archive third-party data in Microsoft 365:</span></span>

- <span data-ttu-id="2d556-117">**Использование стороннего соединителя данных в центре безопасности & соответствия требованиям:** Используйте пользовательский соединитель данных, который доступен в центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2d556-117">**Use a third-party data connector in the Security & Compliance Center:** Use a custom data connector that's available in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="2d556-118">После настройки и настройки соединителя он подключается к стороннему источнику данных, преобразует содержимое элемента в формат сообщений электронной почты, а затем импортирует его в почтовый ящик в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2d556-118">After you set up and configure the connector, it connects to the third-party data source, converts the content of an item to an email message format, and then imports the item to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="2d556-119">В настоящее время вы можете реализовать соединители для импорта и архивирования данных из бизнес-страниц Facebook, корпоративных учетных записей Twitter, LinkedIn, мгновенных Bloomberg и данных отдела кадров Организации (HR).</span><span class="sxs-lookup"><span data-stu-id="2d556-119">Currently, you can implement connectors to import and archive data from Facebook Business pages, corporate Twitter accounts, LinkedIn, Instant Bloomberg, and your organization's human resources (HR) data.</span></span> <span data-ttu-id="2d556-120">Пошаговые инструкции по настройке одного из этих соединителей приведены в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="2d556-120">For the step-by-step instructions to set up one of these connectors, see:</span></span>

   - <span data-ttu-id="2d556-121">**Facebook:** [Использование соединителя для архивации данных Facebook](archive-facebook-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="2d556-121">**Facebook:** [Use a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md)</span></span>

   - <span data-ttu-id="2d556-122">**Twitter:** [Использование соединителя для архивации данных Twitter](archive-twitter-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="2d556-122">**Twitter:** [Use a connector to archive Twitter data](archive-twitter-data-with-sample-connector.md)</span></span>

   - <span data-ttu-id="2d556-123">**LinkedIn:** [Настройка соединителя для архивации данных LinkedIn](archive-linkedin-data.md)</span><span class="sxs-lookup"><span data-stu-id="2d556-123">**LinkedIn:** [Set up a connector to archive LinkedIn data](archive-linkedin-data.md)</span></span>

   - <span data-ttu-id="2d556-124">**Instant Bloomberg:** [Настройка соединителя для архивации данных мгновенных Bloomberg](archive-instant-bloomberg-data.md)</span><span class="sxs-lookup"><span data-stu-id="2d556-124">**Instant Bloomberg:** [Set up a connector to archive Instant Bloomberg data](archive-instant-bloomberg-data.md)</span></span>

   - <span data-ttu-id="2d556-125">**Данные отдела кадров:** [Настройка соединителя для импорта данных о персонале](import-hr-data.md)</span><span class="sxs-lookup"><span data-stu-id="2d556-125">**HR data:** [Set up a connector to import HR data](import-hr-data.md)</span></span>

- <span data-ttu-id="2d556-126">**Работайте с партнером Майкрософт:** Ваша организация работает с партнером корпорации Майкрософт, который будет предоставлять настраиваемый соединитель, который будет настроен на регулярное извлечение элементов из стороннего источника данных, а затем подключается к Microsoft Cloud с помощью стороннего API и импортирует эти элементы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2d556-126">**Work with a Microsoft partner:** Your organization works with a Microsoft Partner who will provide a custom connector that will be configured to extract items from the third-party data source on a regular basis and then connect to the Microsoft cloud by a third-party API and import those items to Microsoft 365.</span></span> <span data-ttu-id="2d556-127">Соединитель партнера также Преобразовывает содержимое элемента из стороннего источника данных в сообщение электронной почты, а затем импортирует его в почтовый ящик в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2d556-127">The partner connector also converts the content of an item from the third-party data source to an email message and then imports it to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="2d556-128">Список партнеров, с которыми вы можете работать, а также пошагового процесса для этого метода, приведен в статье [Работа с партнером для архивации сторонних данных в Microsoft 365](work-with-partner-to-archive-third-party-data.md).</span><span class="sxs-lookup"><span data-stu-id="2d556-128">For a list of partners that you can work with and the step-by-step process for this method, see [Work with a partner to archive third-party data in Microsoft 365](work-with-partner-to-archive-third-party-data.md).</span></span>
