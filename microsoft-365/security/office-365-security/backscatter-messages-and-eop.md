---
title: Подложные уведомления о недоставленном сообщении и EOP
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
description: Сообщения с рассеиванием являются автоматизированными сообщениями, которые отправляются на подложные адреса электронной почты. DNSBL указывает серверы, которые отправляют сообщения с небольшими отрезками (которые могут включать множество допустимых источников электронной почты). Так как он не является списком нежелательной почты, мы не пытаемся удалить себя из DNSBL.
ms.openlocfilehash: 20ed828680dd20e82819730e6dcd509b896d8616
ms.sourcegitcommit: 1b1425142ae06deae3da10a7d30dce4db029d6d3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "42313814"
---
# <a name="backscatter-messages-and-eop"></a><span data-ttu-id="94256-105">Подложные уведомления о недоставленном сообщении и EOP</span><span class="sxs-lookup"><span data-stu-id="94256-105">Backscatter messages and EOP</span></span>

<span data-ttu-id="94256-106">Недоставленные *сообщения* — это отчеты о недоставке (также называемые сообщениями о недоставке или сообщениях Bounce), которые вы получаете для сообщений, которые вы не отправляли.</span><span class="sxs-lookup"><span data-stu-id="94256-106">*Backscatter messages* are non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="94256-107">Нежелательные сообщения могут подделываться (подделываться) адрес отправителя и часто используют действительные адреса электронной почты для того, чтобы получить авторитетную противозаконную для своих сообщений.</span><span class="sxs-lookup"><span data-stu-id="94256-107">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="94256-108">Таким образом, когда Нежелательная почта неизбежно отправляет сообщения несуществующим получателям (Нежелательная почта является операцией большого объема), конечный сервер электронной почты, скорее всего, будет возвращать недоставленное сообщение в отчете о недоставке, которое отправляется подпадающему отправителю в адресе from:.</span><span class="sxs-lookup"><span data-stu-id="94256-108">So, when a spammer inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server will likely return the undeliverable message in an NDR, which is sent to the forged sender in the From: address.</span></span>

<span data-ttu-id="94256-109">Exchange Online Protection (EOP) позволяет выполнять все усилия по определению и автоматическому удалению сообщений из источников дубиаус, не создавая отчет о недоставке.</span><span class="sxs-lookup"><span data-stu-id="94256-109">Exchange Online Protection (EOP) makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="94256-110">Но в зависимости от объема электронной почты, передаваемых через службу, всегда существует вероятность того, что EOP будет непреднамеренно отправлять сообщения с недостаточной прокрутки.</span><span class="sxs-lookup"><span data-stu-id="94256-110">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter messages.</span></span>

<span data-ttu-id="94256-111">Backscatterer.org поддерживает список заблокированных серверов электронной почты, которые отвечают за отправку сообщений об ошибках, а также серверы EOP, которые могут отображаться в этом списке.</span><span class="sxs-lookup"><span data-stu-id="94256-111">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter messages, and EOP servers might appear on this list.</span></span> <span data-ttu-id="94256-112">Но мы не пытаемся удалить себя из черного списка Backscatterer.org, так как он не является списком нежелательных сообщений (по их допуску).</span><span class="sxs-lookup"><span data-stu-id="94256-112">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="94256-113">Веб-сайт Backscatter.org<http://www.backscatterer.org/?target=usage>() рекомендует использовать службу для проверки входящей электронной почты в безопасном режиме, а не в режиме отклонения (большие службы электронной почты почти всегда отправляют некоторые сообщения в виде рассеивания).</span><span class="sxs-lookup"><span data-stu-id="94256-113">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter messages).</span></span>
