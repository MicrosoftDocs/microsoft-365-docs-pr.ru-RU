---
title: Вероятность нежелательной почты
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать о вероятности нежелательной почты (SCL), которая применяется к сообщениям в Exchange Online Protection (EOP).
ms.openlocfilehash: fbd892b0171cee71f516d7ca3b26b91da664af79
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202237"
---
# <a name="spam-confidence-level-scl-in-eop"></a><span data-ttu-id="e0be5-103">Уровень вероятности нежелательной почты (SCL) в EOP</span><span class="sxs-lookup"><span data-stu-id="e0be5-103">Spam confidence level (SCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e0be5-104">В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или Exchange Online Protection (EOP) без почтовых ящиков Exchange Online входящие сообщения проходят через фильтрацию нежелательной почты в EOP и им назначаются оценки нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="e0be5-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound messages go through spam filtering in EOP and are assigned a spam score.</span></span> <span data-ttu-id="e0be5-105">Этот показатель сопоставлен с конкретным уровнем вероятности нежелательной почты (SCL), который добавляется к сообщению в X-заголовке.</span><span class="sxs-lookup"><span data-stu-id="e0be5-105">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="e0be5-106">Повышенная вероятность нежелательной почты означает, что сообщение, скорее всего, будет нежелательным.</span><span class="sxs-lookup"><span data-stu-id="e0be5-106">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="e0be5-107">EOP выполняет действия с сообщением на основе вероятности нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="e0be5-107">EOP takes action on the message based on the SCL.</span></span>

<span data-ttu-id="e0be5-108">Сведения о вероятности нежелательной почты и действиях по умолчанию, выполняемые над сообщениями, описаны в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="e0be5-108">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="e0be5-109">Дополнительные сведения о действиях, которые можно выполнять над сообщениями на основе вредоносности фильтрации нежелательной почты, см [в разделе Настройка политик защиты от нежелательной почты в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e0be5-109">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

****

|<span data-ttu-id="e0be5-110">SCL</span><span class="sxs-lookup"><span data-stu-id="e0be5-110">SCL</span></span>|<span data-ttu-id="e0be5-111">Определение</span><span class="sxs-lookup"><span data-stu-id="e0be5-111">Definition</span></span>|<span data-ttu-id="e0be5-112">Действие по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e0be5-112">Default action</span></span>|
|:---:|---|---|
|<span data-ttu-id="e0be5-113">–1</span><span class="sxs-lookup"><span data-stu-id="e0be5-113">-1</span></span>|<span data-ttu-id="e0be5-114">Сообщение пропустила фильтрацию нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="e0be5-114">The message skipped spam filtering.</span></span> <span data-ttu-id="e0be5-115">Например, сообщение получено от надежного отправителя, отправлено безопасному получателю или находится на исходном сервере электронной почты в списке разрешенных IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="e0be5-115">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="e0be5-116">Дополнительные сведения см. [в статье Создание списков надежных отправителей в EOP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="e0be5-116">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="e0be5-117">Доставка сообщения в папку входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="e0be5-117">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="e0be5-118">0, 1</span><span class="sxs-lookup"><span data-stu-id="e0be5-118">0, 1</span></span>|<span data-ttu-id="e0be5-119">Фильтрация нежелательной почты определила, что сообщение не было спама.</span><span class="sxs-lookup"><span data-stu-id="e0be5-119">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="e0be5-120">Доставка сообщения в папку входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="e0be5-120">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="e0be5-121">5, 6</span><span class="sxs-lookup"><span data-stu-id="e0be5-121">5, 6</span></span>|<span data-ttu-id="e0be5-122">Фильтрация нежелательной почты пометила сообщение как **Нежелательная**</span><span class="sxs-lookup"><span data-stu-id="e0be5-122">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="e0be5-123">Доставка сообщения в папку нежелательной почты получателя.</span><span class="sxs-lookup"><span data-stu-id="e0be5-123">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="e0be5-124">9 </span><span class="sxs-lookup"><span data-stu-id="e0be5-124">9</span></span>|<span data-ttu-id="e0be5-125">Фильтрация нежелательной почты пометила сообщение как **Нежелательная почта высокой достоверности**</span><span class="sxs-lookup"><span data-stu-id="e0be5-125">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="e0be5-126">Доставка сообщения в папку нежелательной почты получателя.</span><span class="sxs-lookup"><span data-stu-id="e0be5-126">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="e0be5-127">Вы заметите, что для фильтрации нежелательной почты не используются SCL 2, 3, 4, 7 и 8.</span><span class="sxs-lookup"><span data-stu-id="e0be5-127">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="e0be5-128">Для отметки вероятности нежелательной почты в сообщениях можно использовать правила для поток обработки почты (также называемые правилами транспорта).</span><span class="sxs-lookup"><span data-stu-id="e0be5-128">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="e0be5-129">Если вы используете правило обработки почты для установки вероятности нежелательной почты, значения 5 или 6 инициируют действие фильтрации нежелательной почты для **спама**, а значения 7, 8 или 9 запускают действие фильтрации нежелательной почты для **нежелательной почты высокой надежности**.</span><span class="sxs-lookup"><span data-stu-id="e0be5-129">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="e0be5-130">Дополнительные сведения см. в статье [Использование правил для обработки почты для установки уровня вероятности нежелательной почты (SCL) в сообщениях](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span><span class="sxs-lookup"><span data-stu-id="e0be5-130">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="e0be5-131">Как и в случае нежелательной почты, уровень жалоб (BCL) определяет неправильные массовые сообщения электронной почты (также называемые _серой почтой_).</span><span class="sxs-lookup"><span data-stu-id="e0be5-131">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="e0be5-132">Более высокий уровень BCL указывает, что массово рассылаемое сообщение часто вызовет жалобы (и поэтому скорее всего является спамом).</span><span class="sxs-lookup"><span data-stu-id="e0be5-132">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="e0be5-133">Вы настраиваете пороговое значение BCL в политиках защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="e0be5-133">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="e0be5-134">Дополнительные сведения: [Настройка политик защиты от нежелательной почты в EOP](configure-your-spam-filter-policies.md), [массовых жалобах (BCL) в EOP)](bulk-complaint-level-values.md), а также [различия между нежелательной почтой и групповой почтой?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span><span class="sxs-lookup"><span data-stu-id="e0be5-134">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

|<!-- -->|
|---|
|<span data-ttu-id="e0be5-135">![Короткий значок LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **, впервые появился в Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="e0be5-135">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="e0be5-136">Бесплатные видеокурсы для **администраторов и ИТ-специалистов по Microsoft 365**, которые можно найти в LinkedIn Learning.</span><span class="sxs-lookup"><span data-stu-id="e0be5-136">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
