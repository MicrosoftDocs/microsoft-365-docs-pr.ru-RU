---
title: Подложное уведомление о недоставленном сообщении в EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: В этой статье вы узнаете о backscatter и Microsoft Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d9556c69e5db460933b355e8bf12903d56f21b5
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286973"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="9c1dd-103">Подложное уведомление о недоставленном сообщении в EOP</span><span class="sxs-lookup"><span data-stu-id="9c1dd-103">Backscatter in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9c1dd-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="9c1dd-104">**Applies to**</span></span>
- [<span data-ttu-id="9c1dd-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9c1dd-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9c1dd-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="9c1dd-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="9c1dd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9c1dd-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="9c1dd-108">*Подкадровка* — это отчеты о неотвечаемой доставке (также известные как сообщения о возврате), которые вы получаете для сообщений, которые вы не отправили.</span><span class="sxs-lookup"><span data-stu-id="9c1dd-108">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="9c1dd-109">Спамеры подделывают (подделывают) адрес от: адреса своих сообщений, и они часто используют реальные адреса электронной почты, чтобы сузить доверие к своим сообщениям.</span><span class="sxs-lookup"><span data-stu-id="9c1dd-109">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="9c1dd-110">Таким образом, когда отправители нежелательной почты неизбежно отправляют сообщения несуществующим получателям (нежелательная почта является большой объемной операцией), почтовый сервер назначения, по сути, обманным образом возвращает недостижимое сообщение в сообщении о недоверенном сообщении не подделанное отправитель в адресе Отправитель.</span><span class="sxs-lookup"><span data-stu-id="9c1dd-110">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="9c1dd-111">В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online EOP делает все возможное для идентификации и передачи сообщений из неявных источников без создания сообщения о неудаленном сообщении.</span><span class="sxs-lookup"><span data-stu-id="9c1dd-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="9c1dd-112">Но в зависимости от объема электронной почты, которая проходит через службу, всегда существует вероятность того, что EOP непреднамеренно отправит подкадровые сообщения.</span><span class="sxs-lookup"><span data-stu-id="9c1dd-112">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="9c1dd-113">Backscatterer.org списке заблокированных (также известных как список заблокированных DNS или DNSBL) почтовых серверов, отвечающих за отправку подкадров, и в этом списке могут появиться серверы EOP.</span><span class="sxs-lookup"><span data-stu-id="9c1dd-113">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="9c1dd-114">Но мы не пытаемся удалить нас из списка заблокированных Backscatterer.org, так как он не является списком лиц, рассыланий нежелательной почты (по их собственному допуску).</span><span class="sxs-lookup"><span data-stu-id="9c1dd-114">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="9c1dd-115">Веб-сайт Backscatter.org ( ) рекомендует использовать свою службу для проверки входящих сообщений электронной почты в безопасном режиме вместо режима "Отклонить" (крупные почтовые службы почти всегда отправляют некоторые <http://www.backscatterer.org/?target=usage> подмены).</span><span class="sxs-lookup"><span data-stu-id="9c1dd-115">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
