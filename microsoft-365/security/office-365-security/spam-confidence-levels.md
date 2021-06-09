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
description: Администраторы могут узнать об уровне доверия к нежелательной почте (SCL), который применяется к сообщениям в Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 55e64c72cc472e98baa8eb71e23dafb6b276ba01
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625285"
---
# <a name="spam-confidence-level-scl-in-eop"></a><span data-ttu-id="4ae38-103">Уровень доверия к нежелательной почте (SCL) в EOP</span><span class="sxs-lookup"><span data-stu-id="4ae38-103">Spam confidence level (SCL) in EOP</span></span>

<span data-ttu-id="4ae38-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="4ae38-104">**Applies to**</span></span>
- [<span data-ttu-id="4ae38-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4ae38-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="4ae38-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="4ae38-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="4ae38-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ae38-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4ae38-108">В Microsoft 365 организациях с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без Exchange Online почтовых ящиков входящие сообщения проходят фильтрацию нежелательной почты в EOP и за них назначена оценка нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="4ae38-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound messages go through spam filtering in EOP and are assigned a spam score.</span></span> <span data-ttu-id="4ae38-109">Этот показатель соединялся с отдельным уровнем доверия к нежелательной почте (SCL), который добавляется к сообщению в X-header.</span><span class="sxs-lookup"><span data-stu-id="4ae38-109">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="4ae38-110">Более высокий уровень SCL указывает на то, что сообщение чаще является нежелательной почтой.</span><span class="sxs-lookup"><span data-stu-id="4ae38-110">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="4ae38-111">EOP принимает меры по сообщению на основе SCL.</span><span class="sxs-lookup"><span data-stu-id="4ae38-111">EOP takes action on the message based on the SCL.</span></span>

<span data-ttu-id="4ae38-112">Значение SCL и действия по умолчанию, которые принимаются в сообщениях, описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="4ae38-112">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="4ae38-113">Дополнительные сведения о действиях, которые можно принять для сообщений на основе вердикта по фильтрации нежелательной почты, см. в статью Настройка политик по борьбе со спамом [в EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="4ae38-113">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

****

|<span data-ttu-id="4ae38-114">SCL</span><span class="sxs-lookup"><span data-stu-id="4ae38-114">SCL</span></span>|<span data-ttu-id="4ae38-115">Определение</span><span class="sxs-lookup"><span data-stu-id="4ae38-115">Definition</span></span>|<span data-ttu-id="4ae38-116">Действие по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4ae38-116">Default action</span></span>|
|:---:|---|---|
|<span data-ttu-id="4ae38-117">–1</span><span class="sxs-lookup"><span data-stu-id="4ae38-117">-1</span></span>|<span data-ttu-id="4ae38-118">В сообщении была пропущена фильтрация нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="4ae38-118">The message skipped spam filtering.</span></span> <span data-ttu-id="4ae38-119">Например, сообщение от безопасного отправитель, было отправлено безопасному получателю или находится с сервера источника электронной почты в списке ip Allow.</span><span class="sxs-lookup"><span data-stu-id="4ae38-119">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="4ae38-120">Дополнительные сведения см. в [списке Создание безопасных списков](create-safe-sender-lists-in-office-365.md)отправитель в EOP.</span><span class="sxs-lookup"><span data-stu-id="4ae38-120">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="4ae38-121">Доставка сообщения в папку входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="4ae38-121">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="4ae38-122">0, 1</span><span class="sxs-lookup"><span data-stu-id="4ae38-122">0, 1</span></span>|<span data-ttu-id="4ae38-123">Фильтрация нежелательной почты определила, что сообщение не является спамом.</span><span class="sxs-lookup"><span data-stu-id="4ae38-123">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="4ae38-124">Доставка сообщения в папку входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="4ae38-124">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="4ae38-125">5, 6</span><span class="sxs-lookup"><span data-stu-id="4ae38-125">5, 6</span></span>|<span data-ttu-id="4ae38-126">Фильтрация нежелательной почты помечена как **спам**</span><span class="sxs-lookup"><span data-stu-id="4ae38-126">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="4ae38-127">Доставка сообщения в папку нежелательной почты получателя.</span><span class="sxs-lookup"><span data-stu-id="4ae38-127">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="4ae38-128">9 </span><span class="sxs-lookup"><span data-stu-id="4ae38-128">9</span></span>|<span data-ttu-id="4ae38-129">Фильтрация нежелательной почты помечена как спам **с высокой уверенностью**</span><span class="sxs-lookup"><span data-stu-id="4ae38-129">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="4ae38-130">Доставка сообщения в папку нежелательной почты получателя.</span><span class="sxs-lookup"><span data-stu-id="4ae38-130">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="4ae38-131">Вы заметите, что SCL 2, 3, 4, 7 и 8 не используются для фильтрации нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="4ae38-131">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="4ae38-132">Для штамповки SCL в сообщениях можно использовать правила потока почты (также известные как правила транспорта).</span><span class="sxs-lookup"><span data-stu-id="4ae38-132">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="4ae38-133">Если для набора SCL используется правило потока почты, значения 5 или 6 вызывают действие фильтрации нежелательной почты для нежелательной почты, а значения 7, 8 или 9 вызывают действие фильтрации нежелательной почты для нежелательной почты с высокой **уверенностью.**</span><span class="sxs-lookup"><span data-stu-id="4ae38-133">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="4ae38-134">Дополнительные сведения см. в тексте Правила потока почты, чтобы установить уровень доверия к нежелательной почте [(SCL) в сообщениях.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)</span><span class="sxs-lookup"><span data-stu-id="4ae38-134">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).</span></span>

<span data-ttu-id="4ae38-135">Как и в SCL, уровень массовой жалобы (BCL) определяет плохое массовое сообщение электронной почты (также известное как _серая почта)._</span><span class="sxs-lookup"><span data-stu-id="4ae38-135">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="4ae38-136">Более высокий уровень BCL указывает, что массово рассылаемое сообщение часто вызовет жалобы (и поэтому скорее всего является спамом).</span><span class="sxs-lookup"><span data-stu-id="4ae38-136">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="4ae38-137">Порог BCL настраивается в политиках по борьбе со спамом.</span><span class="sxs-lookup"><span data-stu-id="4ae38-137">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="4ae38-138">Дополнительные сведения см. в перенастройке политик защиты от нежелательной почты в [EOP,](configure-your-spam-filter-policies.md)уровне массовой [жалобы (BCL) в EOP)](bulk-complaint-level-values.md)и в чем разница между нежелательной электронной почтой и массовой электронной [почтой?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span><span class="sxs-lookup"><span data-stu-id="4ae38-138">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

****

<span data-ttu-id="4ae38-139">![Короткий значок для LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="4ae38-139">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="4ae38-140">Откройте для себя бесплатные видео-курсы **для Microsoft 365 администраторов** и ИТ-специалистов, которые будут доставлены в LinkedIn Learning.</span><span class="sxs-lookup"><span data-stu-id="4ae38-140">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>
