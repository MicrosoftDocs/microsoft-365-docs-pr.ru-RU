---
title: Рассеивание и EOP
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
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: Почтовые рассеивания — это автоматизированные сообщения, которые отправляются на подложные адреса электронной почты. DNSBL указывает серверы, которые отправляют сообщения с небольшими отрезками (которые могут включать множество допустимых источников электронной почты). Так как он не является списком нежелательной почты, мы не пытаемся удалить себя из DNSBL.
ms.openlocfilehash: 22eeec29722cf1742e096234aad95b9f6ee407e2
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895409"
---
# <a name="backscatter-and-eop"></a><span data-ttu-id="0e5f3-105">Рассеивание и EOP</span><span class="sxs-lookup"><span data-stu-id="0e5f3-105">Backscatter and EOP</span></span>

<span data-ttu-id="0e5f3-106">" *Поточечная диаграмма* " — это отчеты о недоставке (также называемые сообщениями NDR или Bounce), которые вы получаете для сообщений, которые вы не отправляли.</span><span class="sxs-lookup"><span data-stu-id="0e5f3-106">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="0e5f3-107">Нежелательные сообщения могут подделываться (подделываться) адрес отправителя и часто используют действительные адреса электронной почты для того, чтобы получить авторитетную противозаконную для своих сообщений.</span><span class="sxs-lookup"><span data-stu-id="0e5f3-107">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="0e5f3-108">Таким образом, когда отправители с нежелательной почтой неизбежно отправляют сообщения несуществующим получателям (Нежелательная почта — это операция большого объема), конечный сервер электронной почты, по сути, может вернуть недоставленное сообщение в отчете о недоставке в адрес отправителя в поле "от:".</span><span class="sxs-lookup"><span data-stu-id="0e5f3-108">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="0e5f3-109">Exchange Online Protection (EOP) позволяет выполнять все усилия по определению и автоматическому удалению сообщений из источников дубиаус, не создавая отчет о недоставке.</span><span class="sxs-lookup"><span data-stu-id="0e5f3-109">Exchange Online Protection (EOP) makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="0e5f3-110">Однако в зависимости от объема электронной почты, передаваемых через службу, всегда существует вероятность непреднамеренной отправки EOP.</span><span class="sxs-lookup"><span data-stu-id="0e5f3-110">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="0e5f3-111">Backscatterer.org поддерживает список заблокированных серверов электронной почты, которые отвечают за отправку почтовых элементов, которые отвечают за отправку почтовых рассеивания, а также могут отображаться в этом списке.</span><span class="sxs-lookup"><span data-stu-id="0e5f3-111">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="0e5f3-112">Но мы не пытаемся удалить себя из черного списка Backscatterer.org, так как он не является списком нежелательных сообщений (по их допуску).</span><span class="sxs-lookup"><span data-stu-id="0e5f3-112">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="0e5f3-113">Веб-сайт Backscatter.org<http://www.backscatterer.org/?target=usage>() рекомендует использовать службу для проверки входящей электронной почты в безопасном режиме, а не в режиме отклонения (большие службы электронной почты почти всегда отправляют некоторую почтовые рассеивание).</span><span class="sxs-lookup"><span data-stu-id="0e5f3-113">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
