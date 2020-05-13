---
title: Значения уровня жалоб для массовых жалоб
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать о значениях массового уровня соответствия (BCL), используемых в Exchange Online Protection (EOP).
ms.openlocfilehash: 87ef0787aad12022d9034800c4ddc72e54445f5d
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209611"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="d0b06-103">Уровень жалоб (BCL) в EOP</span><span class="sxs-lookup"><span data-stu-id="d0b06-103">Bulk complaint level (BCL) in EOP</span></span>

<span data-ttu-id="d0b06-104">В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или автономной службе Exchange Online Protection (EOP) без почтовых ящиков Exchange Online, EOP назначает набор BCL для входящих сообщений от массовых почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="d0b06-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="d0b06-105">BCL добавляется в сообщение в виде X-заголовка и аналогично вероятности нежелательной [почты](spam-confidence-levels.md) , используемой для идентификации сообщений как спама.</span><span class="sxs-lookup"><span data-stu-id="d0b06-105">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="d0b06-106">Более высокая причина в том, что массовые сообщения, скорее всего, будут создавать жалобы (и, следовательно, скорее всего, не спама).</span><span class="sxs-lookup"><span data-stu-id="d0b06-106">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="d0b06-107">Корпорация Майкрософт использует как внутренние, так и сторонние источники для идентификации массовой почты и определения соответствующей BCL.</span><span class="sxs-lookup"><span data-stu-id="d0b06-107">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="d0b06-108">Массовые почтовые ящики отличаются в соответствии с их шаблонами отправки, созданием контента и приемом получения получателей.</span><span class="sxs-lookup"><span data-stu-id="d0b06-108">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="d0b06-109">Хорошие массовые почтовые ящики отправляют желаемые сообщения с релевантным содержимым подписчикам.</span><span class="sxs-lookup"><span data-stu-id="d0b06-109">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="d0b06-110">Такие сообщения вызывают очень мало жалоб со стороны получателей.</span><span class="sxs-lookup"><span data-stu-id="d0b06-110">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="d0b06-111">Другие же системы массовой рассылки распространяют нежелательные сообщения, похожие на спам, и тем самым вызывают множество жалоб от получателей.</span><span class="sxs-lookup"><span data-stu-id="d0b06-111">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="d0b06-112">Сообщения из массового почтового ящика называются нефасованной или серой почтой.</span><span class="sxs-lookup"><span data-stu-id="d0b06-112">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="d0b06-113">Фильтрация нежелательной почты помечает сообщения как **массовые** сообщения на основе порога BCL (значение по умолчанию или заданное значение) и выполняет указанное действие с сообщением (действием по умолчанию является доставка сообщения в папку "Нежелательная почта" получателя).</span><span class="sxs-lookup"><span data-stu-id="d0b06-113">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="d0b06-114">Дополнительные сведения: [Настройка политик защиты от нежелательной почты](configure-your-spam-filter-policies.md) , а также [различия между нежелательной почтой и групповой почтой](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="d0b06-114">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="d0b06-115">Пороговые значения BCL описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="d0b06-115">The BCL thresholds are described in the following table.</span></span>

|||
|:---:|---|
|<span data-ttu-id="d0b06-116">**BCL**</span><span class="sxs-lookup"><span data-stu-id="d0b06-116">**BCL**</span></span>|<span data-ttu-id="d0b06-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d0b06-117">**Description**</span></span>|
|<span data-ttu-id="d0b06-118">нуль</span><span class="sxs-lookup"><span data-stu-id="d0b06-118">0</span></span>|<span data-ttu-id="d0b06-119">Сообщение отправлено без использования систем массовой рассылки.</span><span class="sxs-lookup"><span data-stu-id="d0b06-119">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="d0b06-120">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="d0b06-120">1, 2, 3</span></span>|<span data-ttu-id="d0b06-121">Сообщение от системы массовой рассылки, которое вызывает малое количество жалоб.</span><span class="sxs-lookup"><span data-stu-id="d0b06-121">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="d0b06-122">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="d0b06-122">4, 5, 6, 7</span></span>|<span data-ttu-id="d0b06-123">Сообщение от системы массовой рассылки, которое может вызвать как малое, так и большое количество жалоб.</span><span class="sxs-lookup"><span data-stu-id="d0b06-123">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="d0b06-124">8, 9</span><span class="sxs-lookup"><span data-stu-id="d0b06-124">8, 9</span></span>|<span data-ttu-id="d0b06-125">Сообщение получено от массового отправителя, который создает большое количество жалоб.</span><span class="sxs-lookup"><span data-stu-id="d0b06-125">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|
