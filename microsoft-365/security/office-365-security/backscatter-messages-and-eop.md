---
title: Обратное рассеяние в EOP
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
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: В этой статье вы узнаете о подложных питаниях и службе Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: f1705fd7fc30c9a8cde5f6acfaf145861de3af08
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827789"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="3395c-103">Обратное рассеяние в EOP</span><span class="sxs-lookup"><span data-stu-id="3395c-103">Backscatter in EOP</span></span>

<span data-ttu-id="3395c-104">*Подложные уведомления о недоставленном* сообщении — это отчеты о недоставке (также известные как сообщения возврата), полученные для сообщений, которые вы не отправляли.</span><span class="sxs-lookup"><span data-stu-id="3395c-104">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="3395c-105">Отправители нежелательной почты подделывают (подделку) сообщения от: адрес своих сообщений, и зачастую используют настоящие адреса электронной почты, чтобы получать достоинство своих сообщений.</span><span class="sxs-lookup"><span data-stu-id="3395c-105">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="3395c-106">Поэтому, когда злоумышленники спамерно отправляют сообщения несуществующим получателям (спам большого объема), почтовый сервер назначения должен отправлять в отчете о недоставке поддельное сообщение поддельному отправителю в поле "От": адрес.</span><span class="sxs-lookup"><span data-stu-id="3395c-106">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="3395c-107">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online служба EOP позволяет идентифицировать и автоматически отключать сообщения из двузначных источников без создания отчета о недоставке.</span><span class="sxs-lookup"><span data-stu-id="3395c-107">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="3395c-108">Но на основании объема громкости электронной почты, проходящей через службу, всегда есть возможность случайно отправить подложное уведомление о недоставленном сообщении.</span><span class="sxs-lookup"><span data-stu-id="3395c-108">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="3395c-109">Backscatterer.org поддерживает список блокировок (также список блокировок DNS или DNSBL) для серверов электронной почты, которые отвечали за отправку подложного уведомления о недоставленном сообщении, а серверы EOP могут отображаться в этом списке.</span><span class="sxs-lookup"><span data-stu-id="3395c-109">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="3395c-110">Однако мы не стараемся удалить наших пользователей из списка заблокированных Backscatterer.org-адресов, потому что это не список рассылки нежелательной почты (собственные)</span><span class="sxs-lookup"><span data-stu-id="3395c-110">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="3395c-111">На вебBackscatter.orgсайте ( ) рекомендуется использовать свою службу для проверки входящей электронной почты в безопасном <http://www.backscatterer.org/?target=usage> режиме вместо режима отклонения (почти всегда отправляется недвижная подложка уведомлений).</span><span class="sxs-lookup"><span data-stu-id="3395c-111">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
