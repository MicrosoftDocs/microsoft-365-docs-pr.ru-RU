---
title: Массовые значения уровня жалоб, массовые почтовые ящики, уровни BCL, принципы работы BCL, оценки BCL, защиты от спама, заголовок защиты от спама, фильтрация массовых сообщений, остановка массовой почты
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
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
description: Сведения о значениях массового уровня соответствия (BCL) в Office 365.
ms.openlocfilehash: e45b08756dd528e56b24635d670ddcd05e4396e4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630639"
---
# <a name="bulk-complaint-level-bcl-in-office-365"></a><span data-ttu-id="b7789-103">Уровень жалоб (BCL) в Office 365</span><span class="sxs-lookup"><span data-stu-id="b7789-103">Bulk complaint level (BCL) in Office 365</span></span>

<span data-ttu-id="b7789-104">Массовые почтовые ящики отличаются в соответствии с их шаблонами отправки, созданием контента и приемом получения получателей.</span><span class="sxs-lookup"><span data-stu-id="b7789-104">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="b7789-105">Некоторые — это хорошие массовые почтовые сообщения, которые отправляют нужные сообщения с релевантным содержимым подписчикам.</span><span class="sxs-lookup"><span data-stu-id="b7789-105">Some are good bulk mailers that send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="b7789-106">Такие сообщения вызывают очень мало жалоб со стороны получателей.</span><span class="sxs-lookup"><span data-stu-id="b7789-106">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="b7789-107">Другие же системы массовой рассылки распространяют нежелательные сообщения, похожие на спам, и тем самым вызывают множество жалоб от получателей.</span><span class="sxs-lookup"><span data-stu-id="b7789-107">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="b7789-108">Сообщения из массового почтового ящика называются нефасованной или серой почтой.</span><span class="sxs-lookup"><span data-stu-id="b7789-108">Messages from a bulk mailer is known as bulk mail or gray mail.</span></span>

<span data-ttu-id="b7789-109">Чтобы отличать сообщения от различных типов массовых почтовых ящиков, входящую почту из массовых почтовых ящиков (Exchange Online или отдельная служба Exchange Online Protection (EOP) без почтовых ящиков Exchange Online), можно добавить BCL (BCL), добавленную к сообщению в X-заголовке.</span><span class="sxs-lookup"><span data-stu-id="b7789-109">To distinguish messages from different types of bulk mailers, inbound email from bulk mailers (Exchange Online or standalone Exchange Online Protection (EOP) without Exchange Online mailboxes) is assigned a bulk complaint level (BCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="b7789-110">BCL похожа на уровень вероятности [нежелательной почты](spam-confidence-levels.md) , который используется для идентификации сообщений как спама.</span><span class="sxs-lookup"><span data-stu-id="b7789-110">The BCL is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="b7789-111">Более высокая причина в том, что массовые сообщения, скорее всего, будут создавать жалобы (и, следовательно, скорее всего, не спама).</span><span class="sxs-lookup"><span data-stu-id="b7789-111">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="b7789-112">Корпорация Майкрософт использует как внутренние, так и сторонние источники для идентификации массовой почты и определения соответствующей BCL.</span><span class="sxs-lookup"><span data-stu-id="b7789-112">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

 <span data-ttu-id="b7789-113">Фильтрация нежелательной почты помечает сообщения как **массовые** сообщения на основе порога BCL (значение по умолчанию или заданное значение) и выполняет указанное действие с сообщением (действием по умолчанию является доставка сообщения в папку "Нежелательная почта" получателя).</span><span class="sxs-lookup"><span data-stu-id="b7789-113">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="b7789-114">Дополнительные сведения: [Настройка политик защиты от нежелательной почты](configure-your-spam-filter-policies.md) , а также [различия между нежелательной почтой и групповой почтой](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="b7789-114">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="b7789-115">Пороговые значения BCL описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="b7789-115">The BCL thresholds are described in the following table.</span></span>

|||
|:---:|---|
|<span data-ttu-id="b7789-116">**BCL**</span><span class="sxs-lookup"><span data-stu-id="b7789-116">**BCL**</span></span>|<span data-ttu-id="b7789-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b7789-117">**Description**</span></span>|
|<span data-ttu-id="b7789-118">нуль</span><span class="sxs-lookup"><span data-stu-id="b7789-118">0</span></span>|<span data-ttu-id="b7789-119">Сообщение отправлено без использования систем массовой рассылки.</span><span class="sxs-lookup"><span data-stu-id="b7789-119">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="b7789-120">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="b7789-120">1, 2, 3</span></span>|<span data-ttu-id="b7789-121">Сообщение от системы массовой рассылки, которое вызывает малое количество жалоб.</span><span class="sxs-lookup"><span data-stu-id="b7789-121">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="b7789-122">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="b7789-122">4, 5, 6, 7</span></span>|<span data-ttu-id="b7789-123">Сообщение от системы массовой рассылки, которое может вызвать как малое, так и большое количество жалоб.</span><span class="sxs-lookup"><span data-stu-id="b7789-123">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="b7789-124">8, 9</span><span class="sxs-lookup"><span data-stu-id="b7789-124">8, 9</span></span>|<span data-ttu-id="b7789-125">Сообщение получено от массового отправителя, который создает большое количество жалоб.</span><span class="sxs-lookup"><span data-stu-id="b7789-125">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|
