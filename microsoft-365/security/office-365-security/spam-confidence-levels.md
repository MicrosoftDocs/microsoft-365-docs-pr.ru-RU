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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать об уровне уверенности в нежелательной почте (SCL), применяемом к сообщениям в Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 05faec8101bfb13265d3cca7c661f2e86ac21c8d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290409"
---
# <a name="spam-confidence-level-scl-in-eop"></a><span data-ttu-id="f696d-103">Уровень достоверности нежелательной почты (SCL) в EOP</span><span class="sxs-lookup"><span data-stu-id="f696d-103">Spam confidence level (SCL) in EOP</span></span>

<span data-ttu-id="f696d-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="f696d-104">**Applies to**</span></span>
- [<span data-ttu-id="f696d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f696d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f696d-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="f696d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="f696d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f696d-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f696d-108">В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online входящие сообщения проходят фильтрацию нежелательной почты в EOP и имеют оценку нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="f696d-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound messages go through spam filtering in EOP and are assigned a spam score.</span></span> <span data-ttu-id="f696d-109">Этот показатель со картой с отдельным уровнем уверенности в нежелательной почте (SCL), который добавляется к сообщению в X-заголе.</span><span class="sxs-lookup"><span data-stu-id="f696d-109">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="f696d-110">Чем выше вероятность нежелательной почты, тем выше вероятность того, что сообщение является спамом.</span><span class="sxs-lookup"><span data-stu-id="f696d-110">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="f696d-111">EOP принимает действие над сообщением на основе SCL.</span><span class="sxs-lookup"><span data-stu-id="f696d-111">EOP takes action on the message based on the SCL.</span></span>

<span data-ttu-id="f696d-112">Значения SCL и действия по умолчанию, которые принимаются в отношении сообщений, описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="f696d-112">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="f696d-113">Дополнительные сведения о действиях, которые можно принять с сообщениями на основе решения фильтра нежелательной почты, см. в подстройке "Настройка политик борьбы с нежелательной [почтой" в EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f696d-113">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

****

|<span data-ttu-id="f696d-114">SCL</span><span class="sxs-lookup"><span data-stu-id="f696d-114">SCL</span></span>|<span data-ttu-id="f696d-115">Определение</span><span class="sxs-lookup"><span data-stu-id="f696d-115">Definition</span></span>|<span data-ttu-id="f696d-116">Действие по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f696d-116">Default action</span></span>|
|:---:|---|---|
|<span data-ttu-id="f696d-117">–1</span><span class="sxs-lookup"><span data-stu-id="f696d-117">-1</span></span>|<span data-ttu-id="f696d-118">Сообщение пропустило фильтрацию нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="f696d-118">The message skipped spam filtering.</span></span> <span data-ttu-id="f696d-119">Например, сообщение отправлено надежному отправителю, отправлено безопасному получателю или с сервера электронной почты из списка ip-адресов.</span><span class="sxs-lookup"><span data-stu-id="f696d-119">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="f696d-120">Дополнительные сведения см. в сведениях [о создании списков надежных отправников в EOP.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="f696d-120">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="f696d-121">Доставка сообщения в папку входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="f696d-121">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="f696d-122">0, 1</span><span class="sxs-lookup"><span data-stu-id="f696d-122">0, 1</span></span>|<span data-ttu-id="f696d-123">При фильтрации нежелательной почты было определено, что сообщение не является спамом.</span><span class="sxs-lookup"><span data-stu-id="f696d-123">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="f696d-124">Доставка сообщения в папку входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="f696d-124">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="f696d-125">5, 6</span><span class="sxs-lookup"><span data-stu-id="f696d-125">5, 6</span></span>|<span data-ttu-id="f696d-126">Фильтрация нежелательной почты помечена как **нежелательное**</span><span class="sxs-lookup"><span data-stu-id="f696d-126">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="f696d-127">Доставка сообщения в папку нежелательной почты получателя.</span><span class="sxs-lookup"><span data-stu-id="f696d-127">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="f696d-128">9 </span><span class="sxs-lookup"><span data-stu-id="f696d-128">9</span></span>|<span data-ttu-id="f696d-129">При фильтрации нежелательной почты сообщение помечено как **нежелательное с высокой достоверности**</span><span class="sxs-lookup"><span data-stu-id="f696d-129">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="f696d-130">Доставка сообщения в папку нежелательной почты получателя.</span><span class="sxs-lookup"><span data-stu-id="f696d-130">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="f696d-131">Вы заметите, что 2, 3, 4, 7 и 8 не используются при фильтрации нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="f696d-131">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="f696d-132">Вы можете использовать правила потока почты (также известные как правила транспорта), чтобы пометь SCL для сообщений.</span><span class="sxs-lookup"><span data-stu-id="f696d-132">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="f696d-133">Если для этого используется правило потока почты, значения 5 или 6 запускают действие фильтрации нежелательной почты **для** нежелательной почты, а значения 7, 8 или 9 запускают действие фильтрации нежелательной почты для нежелательной почты с высокой достоверности. </span><span class="sxs-lookup"><span data-stu-id="f696d-133">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="f696d-134">Дополнительные сведения см. в настройках уровня уверенности нежелательной почты [(SCL)](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)в сообщениях с помощью правил потока почты.</span><span class="sxs-lookup"><span data-stu-id="f696d-134">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="f696d-135">Как и уровень SCL, уровень жалоб на массовые рассылки (BCL) определяет нелиствимую массовую рассылку (также известная как _серая почта)._</span><span class="sxs-lookup"><span data-stu-id="f696d-135">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="f696d-136">Более высокий уровень BCL указывает, что массово рассылаемое сообщение часто вызовет жалобы (и поэтому скорее всего является спамом).</span><span class="sxs-lookup"><span data-stu-id="f696d-136">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="f696d-137">Порог BCL настраивается в политиках борьбы с нежелательной почтой.</span><span class="sxs-lookup"><span data-stu-id="f696d-137">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="f696d-138">Дополнительные сведения см. в настройках политик защиты от нежелательной почты в [EOP,](configure-your-spam-filter-policies.md)уровне жалоб на массовую рассылку [(BCL) в EOP)](bulk-complaint-level-values.md)и в чем разница между нежелательной почтой и массовой рассылкой? [](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="f696d-138">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

****

<span data-ttu-id="f696d-139">![Короткий значок LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="f696d-139">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="f696d-140">Узнайте о бесплатных видео курсах для администраторов **Microsoft 365** и ИТ-специалистов, которые вы можете получить с помощью LinkedIn Learning.</span><span class="sxs-lookup"><span data-stu-id="f696d-140">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>
