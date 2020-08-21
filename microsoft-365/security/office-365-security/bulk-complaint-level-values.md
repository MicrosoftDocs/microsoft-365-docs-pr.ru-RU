---
title: Уровни жалоб на массовые приемы
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать о массовых соответствия требованиям (BCL), используемых в Exchange Online Protection (EOP).
ms.openlocfilehash: e24c0c97afcca2e7aa014d929d7b2131c6a2d074
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827437"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="c3e0b-103">Массовый уровень жалоб (BCL) в EOP</span><span class="sxs-lookup"><span data-stu-id="c3e0b-103">Bulk complaint level (BCL) in EOP</span></span>

<span data-ttu-id="c3e0b-104">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в организациях с автономной службой Exchange Online Protection (EOP) без почтовых ящиков Exchange Online служба EOP назначает массовую рассылку для входящих сообщений от массовой рассылки.</span><span class="sxs-lookup"><span data-stu-id="c3e0b-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="c3e0b-105">Формат вероятности нежелательной почты добавляется в сообщение в X-заголовке и похож на вероятность нежелательной [почты,](spam-confidence-levels.md) которая используется для определения сообщений как нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="c3e0b-105">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="c3e0b-106">Более высокий уровень BCL указывает, что массовые сообщения будут создавать жалобы (и, следовательно, будут спамом).</span><span class="sxs-lookup"><span data-stu-id="c3e0b-106">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="c3e0b-107">Майкрософт использует внутренние и сторонние источники для идентификации массовых рассылок и определения соответствующего маркера BCL.</span><span class="sxs-lookup"><span data-stu-id="c3e0b-107">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="c3e0b-108">Разные почтовые системы могут различаться по различным шаблонам отправки, созданию контента и приобретению получателей.</span><span class="sxs-lookup"><span data-stu-id="c3e0b-108">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="c3e0b-109">Благодаря хорошей массовой рассылке отправляют подписчикам нужные сообщения с соответствующим содержимым.</span><span class="sxs-lookup"><span data-stu-id="c3e0b-109">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="c3e0b-110">Такие сообщения вызывают очень мало жалоб со стороны получателей.</span><span class="sxs-lookup"><span data-stu-id="c3e0b-110">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="c3e0b-111">Другие же системы массовой рассылки распространяют нежелательные сообщения, похожие на спам, и тем самым вызывают множество жалоб от получателей.</span><span class="sxs-lookup"><span data-stu-id="c3e0b-111">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="c3e0b-112">Сообщения от массовой рассылки называются массовой рассылкой или серьезной почтой.</span><span class="sxs-lookup"><span data-stu-id="c3e0b-112">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="c3e0b-113">При фильтрации спама сообщения **помечаются** как массовая рассылка на основе указанного порогового значения (значение по умолчанию или заданного значения) и выполняет указанное действие с сообщением (действие по умолчанию доставляет сообщение в папку "Нежелательная почта" получателя).</span><span class="sxs-lookup"><span data-stu-id="c3e0b-113">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="c3e0b-114">Дополнительные сведения см. в статье ["Настройка политик защиты от нежелательной почты"](configure-your-spam-filter-policies.md) и в [чем разница между нежелательной почтой и массовыми сообщениями электронной почты?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="c3e0b-114">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="c3e0b-115">Пороговые значения BCL описаны в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="c3e0b-115">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="c3e0b-116">BCL</span><span class="sxs-lookup"><span data-stu-id="c3e0b-116">BCL</span></span>|<span data-ttu-id="c3e0b-117">Описание</span><span class="sxs-lookup"><span data-stu-id="c3e0b-117">Description</span></span>|
|:---:|---|
|<span data-ttu-id="c3e0b-118">0</span><span class="sxs-lookup"><span data-stu-id="c3e0b-118">0</span></span>|<span data-ttu-id="c3e0b-119">Сообщение отправлено без использования систем массовой рассылки.</span><span class="sxs-lookup"><span data-stu-id="c3e0b-119">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="c3e0b-120">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="c3e0b-120">1, 2, 3</span></span>|<span data-ttu-id="c3e0b-121">Сообщение от системы массовой рассылки, которое вызывает малое количество жалоб.</span><span class="sxs-lookup"><span data-stu-id="c3e0b-121">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="c3e0b-122">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="c3e0b-122">4, 5, 6, 7</span></span>|<span data-ttu-id="c3e0b-123">Сообщение от системы массовой рассылки, которое может вызвать как малое, так и большое количество жалоб.</span><span class="sxs-lookup"><span data-stu-id="c3e0b-123">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="c3e0b-124">8, 9</span><span class="sxs-lookup"><span data-stu-id="c3e0b-124">8, 9</span></span>|<span data-ttu-id="c3e0b-125">Сообщение от системы массовой рассылки, которое формирует большое количество жалоб.</span><span class="sxs-lookup"><span data-stu-id="c3e0b-125">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|
