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
description: В этой статье вы узнаете о backscatter и Microsoft Exchange Online защите (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e5882f611c3feec9a22760e696973cd0713649b2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205111"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="adf4d-103">Подложное уведомление о недоставленном сообщении в EOP</span><span class="sxs-lookup"><span data-stu-id="adf4d-103">Backscatter in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="adf4d-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="adf4d-104">**Applies to**</span></span>
- [<span data-ttu-id="adf4d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="adf4d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="adf4d-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="adf4d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="adf4d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="adf4d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="adf4d-108">*Backscatter* — это отчеты о невывозе (также известные как NDRs или сообщения отказов), которые вы получаете для сообщений, которые вы не отправили.</span><span class="sxs-lookup"><span data-stu-id="adf4d-108">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="adf4d-109">Спамеры подделывают (так называемый спуфинг) поле От: своих сообщений, и часто используют реальные адреса электронной почты, чтобы вызвать доверие к своим сообщениям.</span><span class="sxs-lookup"><span data-stu-id="adf4d-109">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="adf4d-110">Таким образом, когда спамеры неизбежно отправляют сообщения несуществующим получателям (спам — это операция с высоким уровнем громкости), сервер электронной почты назначения по сути обманным образом возвращает недостижимое сообщение в NDR поддельной отправительнице в адресе From: address.</span><span class="sxs-lookup"><span data-stu-id="adf4d-110">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="adf4d-111">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online EOP делает все возможное для выявления и бесшумного сброса сообщений из сомнительных источников без создания NDR.</span><span class="sxs-lookup"><span data-stu-id="adf4d-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="adf4d-112">Но, в зависимости от простого объема электронной почты, течет через службу, всегда есть возможность того, что EOP будет непреднамеренно отправлять backscatter.</span><span class="sxs-lookup"><span data-stu-id="adf4d-112">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="adf4d-113">Backscatterer.org поддерживает блок-список (также известный как список блоков DNS или DNSBL) серверов электронной почты, ответственных за отправку backscatter, и В этом списке могут появиться серверы EOP.</span><span class="sxs-lookup"><span data-stu-id="adf4d-113">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="adf4d-114">Но мы не пытаемся удалить себя из списка Backscatterer.org, так как это не список спамеров (по их собственному признанию).</span><span class="sxs-lookup"><span data-stu-id="adf4d-114">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="adf4d-115">Веб Backscatter.org веб-сайт () рекомендует использовать свою службу для проверки входящих сообщений электронной почты в безопасном режиме вместо режима Reject (крупные службы электронной почты почти всегда отправляют некоторые <http://www.backscatterer.org/?target=usage> backscatter).</span><span class="sxs-lookup"><span data-stu-id="adf4d-115">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
