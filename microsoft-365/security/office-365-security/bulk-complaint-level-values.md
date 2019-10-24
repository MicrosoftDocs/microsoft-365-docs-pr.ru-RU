---
title: Массовые значения уровня жалоб, массовые почтовые ящики, уровни BCL, принципы работы BCL, оценки BCL, защиты от спама, заголовок защиты от спама, фильтрация массовых сообщений, остановка массовой почты
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/23/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Узнайте о значениях массовых рассылок (BCL) в Office 365.
ms.openlocfilehash: 822c84ea9b36cfdae1d8faccf7e0c7d9f747c917
ms.sourcegitcommit: 7830969c8fa41724359657910716f3ce312cc2cf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2019
ms.locfileid: "37650121"
---
# <a name="bulk-complaint-level-values"></a><span data-ttu-id="fbe79-103">Уровни жалоб на массовые сообщения</span><span class="sxs-lookup"><span data-stu-id="fbe79-103">Bulk Complaint Level values</span></span>

<span data-ttu-id="fbe79-104">Разные системы массовой рассылки используют различные шаблоны, средства создания контента и списки адресатов.</span><span class="sxs-lookup"><span data-stu-id="fbe79-104">Bulk mailers vary in their sending patterns, content creation, and list acquisition practices.</span></span> <span data-ttu-id="fbe79-105">Некоторые из них отправляют подписчикам полезные сообщения с соответствующим содержимым.</span><span class="sxs-lookup"><span data-stu-id="fbe79-105">Some are good bulk mailers that send wanted messages with relevant content to their subscribers.</span></span> <span data-ttu-id="fbe79-106">Такие сообщения вызывают очень мало жалоб со стороны получателей.</span><span class="sxs-lookup"><span data-stu-id="fbe79-106">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="fbe79-107">Другие же системы массовой рассылки распространяют нежелательные сообщения, похожие на спам, и тем самым вызывают множество жалоб от получателей.</span><span class="sxs-lookup"><span data-stu-id="fbe79-107">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span>

<span data-ttu-id="fbe79-108">Для распознавания таких систем рассылок групповым сообщениям присваивается оценка BCL (уровень жалоб на массовые сообщения).</span><span class="sxs-lookup"><span data-stu-id="fbe79-108">To distinguish these types of bulk mailers, messages from bulk mailers are assigned a Bulk Complaint Level (BCL) rating.</span></span> <span data-ttu-id="fbe79-109">Оценка BCL может варьироваться от 1 до 9 в зависимости от того, насколько высока вероятность получения жалоб на сообщения, рассылаемые системой.</span><span class="sxs-lookup"><span data-stu-id="fbe79-109">BCL ratings range from 1 to 9 depending on how likely the bulk mailer is to generate complaints.</span></span> <span data-ttu-id="fbe79-110">Система массовой рассылки с оценкой BCL 9 вызовет намного больше жалоб со стороны получателей, чем система с оценкой BCL 3.</span><span class="sxs-lookup"><span data-stu-id="fbe79-110">A sender that has a rating of BCL 9 is likely to generate many complaints from recipients, whereas a rating of BCL 3 is unlikely to generate many complaints.</span></span> <span data-ttu-id="fbe79-111">Майкрософт использует внутренние и сторонние источники для идентификации массовых рассылок и присвоения соответствующей оценки BCL.</span><span class="sxs-lookup"><span data-stu-id="fbe79-111">Microsoft uses both internal and third-party sources to identify bulk mail and determine the appropriate BCL.</span></span> <span data-ttu-id="fbe79-112">Дополнительные сведения об этом заголовке сообщения приведены в разделе [заголовки сообщений по защите от нежелательной почты](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="fbe79-112">For more information about this message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="fbe79-113">Так как массовая рассылка с рейтингом 9, скорее всего, будет создавать жалобы, BCL по умолчанию составляет 7.</span><span class="sxs-lookup"><span data-stu-id="fbe79-113">Since a bulk mailer with a rating of 9 is likely to generate complaints, the default BCL is 7.</span></span> <span data-ttu-id="fbe79-114">Это означает, что массовые почтовые сообщения будут приниматься до тех пор, пока уровень жалоб 7 и почта не будут приниматься после этого.</span><span class="sxs-lookup"><span data-stu-id="fbe79-114">This means that bulk mails will be accepted until the complaint level of 7 and mail won't be accepted thereafter.</span></span> <span data-ttu-id="fbe79-115">Чем ниже оценка, тем меньше будет приемка массовой почты.</span><span class="sxs-lookup"><span data-stu-id="fbe79-115">The lower the rating, the less bulk mail is accepted.</span></span> <span data-ttu-id="fbe79-116">Если у вас есть пользователи, и их работа зависит от массовой рассылки, а для BCL задано значение 4, при этом не будет приниматься массовая почта с более высокой BCL, чем 4.</span><span class="sxs-lookup"><span data-stu-id="fbe79-116">If your users are, and their work is, sensitive to bulk mail, and your BCL is set to 4, then no bulk mail with a higher BCL than 4 will be accepted.</span></span>

<span data-ttu-id="fbe79-117">Вы можете использовать значения BCL, чтобы установить уровень фильтрации массовых рассылок, соответствующий требованиям вашей организации. Для этого нужно выполнить действия, приведенные в статье [Настройте политики защиты от спама](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="fbe79-117">You can use BCL values to set the desired level of bulk filtering your organization requires by following the steps in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="fbe79-118">В следующей таблице описаны значения BCL, которые используются в данный момент.</span><span class="sxs-lookup"><span data-stu-id="fbe79-118">The following table describes the BCL values that are currently in use.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="fbe79-119">**Значение BCL**</span><span class="sxs-lookup"><span data-stu-id="fbe79-119">**BCL Value**</span></span>|<span data-ttu-id="fbe79-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="fbe79-120">**Description**</span></span>|
|<span data-ttu-id="fbe79-121">нуль</span><span class="sxs-lookup"><span data-stu-id="fbe79-121">0</span></span>|<span data-ttu-id="fbe79-122">Сообщение отправлено без использования систем массовой рассылки.</span><span class="sxs-lookup"><span data-stu-id="fbe79-122">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="fbe79-123">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="fbe79-123">1, 2, 3</span></span>|<span data-ttu-id="fbe79-124">Сообщение от системы массовой рассылки, которое вызывает малое количество жалоб.</span><span class="sxs-lookup"><span data-stu-id="fbe79-124">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="fbe79-125">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="fbe79-125">4, 5, 6, 7</span></span>|<span data-ttu-id="fbe79-126">Сообщение от системы массовой рассылки, которое может вызвать как малое, так и большое количество жалоб.</span><span class="sxs-lookup"><span data-stu-id="fbe79-126">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="fbe79-127">8, 9</span><span class="sxs-lookup"><span data-stu-id="fbe79-127">8, 9</span></span>|<span data-ttu-id="fbe79-128">Сообщение получено от массового отправителя, который создает большое количество жалоб.</span><span class="sxs-lookup"><span data-stu-id="fbe79-128">The message is from a bulk sender that generates a high number of complaints.</span></span>|
