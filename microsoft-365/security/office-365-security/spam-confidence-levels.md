---
title: Вероятность нежелательной почты
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/02/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
description: Когда электронное сообщение проходит процесс фильтрации нежелательной почты, ему назначается область нежелательных сообщений. Эта область соотносится с оценкой вероятности нежелательной почты и отмечается в Х-заголовке. Служба предпринимает действия к сообщениям в зависимости от интерпретации оценки вероятности нежелательной почты. В таблице ниже показано, как разные оценки вероятности нежелательной почты интерпретируются фильтрами, а также действия по умолчанию, которые применяются к входящим сообщениям в зависимости от оценки.
ms.openlocfilehash: c40317833ea61424dab60ac858c2071f7891c4f8
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598316"
---
# <a name="spam-confidence-levels"></a><span data-ttu-id="77a52-106">Вероятность нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="77a52-106">Spam confidence levels</span></span>

<span data-ttu-id="77a52-p102">Когда электронное сообщение проходит процесс фильтрации нежелательной почты, ему назначается область нежелательных сообщений. Эта область соотносится с оценкой вероятности нежелательной почты и отмечается в Х-заголовке. Служба предпринимает действия к сообщениям в зависимости от интерпретации оценки вероятности нежелательной почты. В таблице ниже показано, как разные оценки вероятности нежелательной почты интерпретируются фильтрами, а также действия по умолчанию, которые применяются к входящим сообщениям в зависимости от оценки.</span><span class="sxs-lookup"><span data-stu-id="77a52-p102">When an email message goes through spam filtering it is assigned a spam score. That score is mapped to an individual Spam Confidence Level (SCL) rating and stamped in an X-header. The service takes actions upon the messages depending upon the spam confidence interpretation of the SCL rating. The following table shows how the different SCL ratings are interpreted by the filters and the default action that is taken on inbound messages for each rating.</span></span>
  
|<span data-ttu-id="77a52-111">**Оценка вероятности нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="77a52-111">**SCL Rating**</span></span>|<span data-ttu-id="77a52-112">**Интерпретации оценки вероятности нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="77a52-112">**Spam Confidence Interpretation**</span></span>|<span data-ttu-id="77a52-113">**Действие по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="77a52-113">**Default Action**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="77a52-114">-1</span><span class="sxs-lookup"><span data-stu-id="77a52-114">-1</span></span>|<span data-ttu-id="77a52-115">Нежелательная почта, исходящие от надежного отправителя, надежного получателя или списка надежных IP-адресов (доверенный партнер).</span><span class="sxs-lookup"><span data-stu-id="77a52-115">Non-spam coming from a safe sender, safe recipient, or safe listed IP address (trusted partner).</span></span>|<span data-ttu-id="77a52-116">Доставка сообщения в папку входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="77a52-116">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="77a52-117">0, 1</span><span class="sxs-lookup"><span data-stu-id="77a52-117">0, 1</span></span>|<span data-ttu-id="77a52-118">Нежелательная почта, так как сообщение было проверено и определено как ясное.</span><span class="sxs-lookup"><span data-stu-id="77a52-118">Non-spam because the message was scanned and determined to be clean.</span></span>|<span data-ttu-id="77a52-119">Доставка сообщения в папку входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="77a52-119">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="77a52-120">5, 6</span><span class="sxs-lookup"><span data-stu-id="77a52-120">5, 6</span></span>|<span data-ttu-id="77a52-121">Нежелательное сообщение</span><span class="sxs-lookup"><span data-stu-id="77a52-121">Spam</span></span>|<span data-ttu-id="77a52-122">Доставка сообщения в папку нежелательной почты получателя.</span><span class="sxs-lookup"><span data-stu-id="77a52-122">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="77a52-123">7, 8, 9</span><span class="sxs-lookup"><span data-stu-id="77a52-123">7, 8, 9</span></span>|<span data-ttu-id="77a52-124">Нежелательное сообщение высокого уровня</span><span class="sxs-lookup"><span data-stu-id="77a52-124">High confidence spam</span></span>|<span data-ttu-id="77a52-125">Доставка сообщения в папку нежелательной почты получателя.</span><span class="sxs-lookup"><span data-stu-id="77a52-125">Deliver the message to the recipients' Junk Email folder.</span></span>|
   
> [!TIP]
> <span data-ttu-id="77a52-126">Оценки SCL, равные 2, 3, 4, 7 и 8, не устанавливаются службой.</span><span class="sxs-lookup"><span data-stu-id="77a52-126">SCL ratings of 2, 3, 4, 7, and 8 are not set by the service.</span></span> <span data-ttu-id="77a52-127">Оценки вероятности нежелательной почты 5 или 6 предположительно относятся к нежелательной почте, но с меньшей вероятностью, чем оценка 9, которая характерна для нежелательных сообщений.</span><span class="sxs-lookup"><span data-stu-id="77a52-127">An SCL rating of 5 or 6 is considered suspected spam, which is less certain to be spam than an SCL rating of 9, which is considered certain spam.</span></span> <span data-ttu-id="77a52-128">Разные действия для нежелательных сообщений и нежелательных сообщений высокого уровня можно настроить с помощью политик фильтров содержимого в Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="77a52-128">Different actions for spam and high confidence spam can be configured via your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="77a52-129">Дополнительные сведения см. в статье [Настройка политик фильтрации спама](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="77a52-129">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="77a52-130">Вы также можете задать рейтинг вероятности нежелательной почты для сообщений, которые отвечают определенным условиям, с помощью правил для поток обработки почты (также называемых правилами транспорта), как описано в разделе Использование правил обработки почты для установки вероятности нежелательной [почты (SCL) в сообщениях](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span><span class="sxs-lookup"><span data-stu-id="77a52-130">You can also set the SCL rating for messages that match specific conditions by using mail flow rules (also known as transport rules), as described in [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span> <span data-ttu-id="77a52-131">Если вы используете правило обработки почты для настройки SCL в 7, 8 или 9, сообщение будет рассматриваться как нежелательная почта высокой достоверности.</span><span class="sxs-lookup"><span data-stu-id="77a52-131">If you use a mail flow rule to set SCL of 7, 8, or 9 the message will be treated as high confidence spam.</span></span> 
  
||
|:-----|
|<span data-ttu-id="77a52-p104">![Небольшой значок LinkedIn Learning](../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Никогда не работали с Office 365?**         Вам помогут бесплатные видеокурсы по **Office 365 admins and IT pros**, предоставленные платформой LinkedIn Learning.</span><span class="sxs-lookup"><span data-stu-id="77a52-p104">![The short icon for LinkedIn Learning](../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**         Discover free video courses for **Office 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
   

