---
title: Объемные значения уровня жалоб
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать о массовых значениях уровня жалоб (BCL), используемых в Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 11f884ec6b32795deba09c0f1ba88055a6422e9b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537947"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="c73bb-103">Уровень массовой жалобы (BCL) в EOP</span><span class="sxs-lookup"><span data-stu-id="c73bb-103">Bulk complaint level (BCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c73bb-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="c73bb-104">**Applies to**</span></span>
- [<span data-ttu-id="c73bb-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c73bb-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c73bb-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="c73bb-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c73bb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c73bb-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c73bb-108">В Microsoft 365 организациях с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без Exchange Online почтовых ящиков EOP назначает объемный уровень жалоб (BCL) для входящих сообщений из массовых почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="c73bb-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk complaint level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="c73bb-109">BCL добавляется в сообщение в X-header и похож на уровень доверия нежелательной почты [(SCL),](spam-confidence-levels.md) который используется для идентификации сообщений как нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="c73bb-109">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="c73bb-110">Более высокий уровень BCL указывает на то, что массовое сообщение с большей вероятностью вызывает жалобы (и, следовательно, чаще является нежелательной почтой).</span><span class="sxs-lookup"><span data-stu-id="c73bb-110">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="c73bb-111">Корпорация Майкрософт использует внутренние и сторонние источники для идентификации массовой почты и определения соответствующего BCL.</span><span class="sxs-lookup"><span data-stu-id="c73bb-111">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="c73bb-112">Массовые почтовые ящики различаются по шаблонам отправки, созданию контента и приему получателей.</span><span class="sxs-lookup"><span data-stu-id="c73bb-112">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="c73bb-113">Хорошие массовые почтовые ящики отправляют нужные сообщения с соответствующим контентом своим подписчикам.</span><span class="sxs-lookup"><span data-stu-id="c73bb-113">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="c73bb-114">Такие сообщения вызывают очень мало жалоб со стороны получателей.</span><span class="sxs-lookup"><span data-stu-id="c73bb-114">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="c73bb-115">Другие же системы массовой рассылки распространяют нежелательные сообщения, похожие на спам, и тем самым вызывают множество жалоб от получателей.</span><span class="sxs-lookup"><span data-stu-id="c73bb-115">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="c73bb-116">Сообщения из массовой почты называются массовой почтой или серой почтой.</span><span class="sxs-lookup"><span data-stu-id="c73bb-116">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="c73bb-117">Фильтрация нежелательной почты отмечает сообщения как массовая электронная почта, основанная на пороге BCL (значение по умолчанию или указанное значение) и принимает указанное действие в сообщении (действие по умолчанию — доставка сообщения в папку нежелательной почты получателя). </span><span class="sxs-lookup"><span data-stu-id="c73bb-117">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="c73bb-118">Дополнительные сведения см. в [рублях Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="c73bb-118">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="c73bb-119">Для настройки исключений для массовой фильтрации почты можно использовать список "Разрешить или блокировать клиента".</span><span class="sxs-lookup"><span data-stu-id="c73bb-119">You can use the Tenant Allow/Block List to configure exceptions for bulk mail filtering.</span></span> <span data-ttu-id="c73bb-120">Сообщения от отправителей в указанных доменах не получают  действий для вердикта о фильтрации нежелательной почты в политиках по борьбе со спамом.</span><span class="sxs-lookup"><span data-stu-id="c73bb-120">Messages from senders in the specified domains don't receive the action for the **Bulk email** spam filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="c73bb-121">Дополнительные сведения см. в [списке Управление списком разрешить или блокировать клиента.](tenant-allow-block-list.md)</span><span class="sxs-lookup"><span data-stu-id="c73bb-121">For more information, see [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

<span data-ttu-id="c73bb-122">Пороговые значения BCL описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="c73bb-122">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="c73bb-123">BCL</span><span class="sxs-lookup"><span data-stu-id="c73bb-123">BCL</span></span>|<span data-ttu-id="c73bb-124">Описание</span><span class="sxs-lookup"><span data-stu-id="c73bb-124">Description</span></span>|
|:---:|---|
|<span data-ttu-id="c73bb-125">0</span><span class="sxs-lookup"><span data-stu-id="c73bb-125">0</span></span>|<span data-ttu-id="c73bb-126">Сообщение отправлено без использования систем массовой рассылки.</span><span class="sxs-lookup"><span data-stu-id="c73bb-126">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="c73bb-127">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="c73bb-127">1, 2, 3</span></span>|<span data-ttu-id="c73bb-128">Сообщение от системы массовой рассылки, которое вызывает малое количество жалоб.</span><span class="sxs-lookup"><span data-stu-id="c73bb-128">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="c73bb-129">4, 5, 6, 7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c73bb-129">4, 5, 6, 7<sup>\*</sup></span></span>|<span data-ttu-id="c73bb-130">Сообщение от системы массовой рассылки, которое может вызвать как малое, так и большое количество жалоб.</span><span class="sxs-lookup"><span data-stu-id="c73bb-130">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="c73bb-131">8, 9</span><span class="sxs-lookup"><span data-stu-id="c73bb-131">8, 9</span></span>|<span data-ttu-id="c73bb-132">Сообщение от отправитель массы, который генерирует большое количество жалоб.</span><span class="sxs-lookup"><span data-stu-id="c73bb-132">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|

<span data-ttu-id="c73bb-133"><sup>\*</sup> Это пороговое значение по умолчанию, используемого в политиках по борьбе со спамом.</span><span class="sxs-lookup"><span data-stu-id="c73bb-133"><sup>\*</sup> This is the default threshold value that's used in anti-spam policies.</span></span>
