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
description: Администраторы могут узнать о массовых значениях соответствия требованиям,которые используются в Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d85dca6e18ebdad4d8f2a5c5f6c5b613c23b47d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073478"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="60d90-103">Уровень массовой жалобы (BCL) в EOP</span><span class="sxs-lookup"><span data-stu-id="60d90-103">Bulk complaint level (BCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="60d90-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="60d90-104">**Applies to**</span></span>
- [<span data-ttu-id="60d90-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="60d90-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="60d90-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="60d90-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="60d90-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="60d90-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="60d90-108">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online EOP назначает входящие сообщения из массовых почтовых ящиков на уровне, удовлетворяемом требованиям.</span><span class="sxs-lookup"><span data-stu-id="60d90-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="60d90-109">BCL добавляется в сообщение в X-header и похож на уровень доверия нежелательной почты [(SCL),](spam-confidence-levels.md) который используется для идентификации сообщений как нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="60d90-109">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="60d90-110">Более высокий уровень BCL указывает на то, что массовое сообщение с большей вероятностью вызывает жалобы (и, следовательно, чаще является нежелательной почтой).</span><span class="sxs-lookup"><span data-stu-id="60d90-110">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="60d90-111">Корпорация Майкрософт использует внутренние и сторонние источники для идентификации массовой почты и определения соответствующего BCL.</span><span class="sxs-lookup"><span data-stu-id="60d90-111">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="60d90-112">Массовые почтовые ящики различаются по шаблонам отправки, созданию контента и приему получателей.</span><span class="sxs-lookup"><span data-stu-id="60d90-112">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="60d90-113">Хорошие массовые почтовые ящики отправляют нужные сообщения с соответствующим контентом своим подписчикам.</span><span class="sxs-lookup"><span data-stu-id="60d90-113">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="60d90-114">Такие сообщения вызывают очень мало жалоб со стороны получателей.</span><span class="sxs-lookup"><span data-stu-id="60d90-114">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="60d90-115">Другие же системы массовой рассылки распространяют нежелательные сообщения, похожие на спам, и тем самым вызывают множество жалоб от получателей.</span><span class="sxs-lookup"><span data-stu-id="60d90-115">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="60d90-116">Сообщения из массовой почты называются массовой почтой или серой почтой.</span><span class="sxs-lookup"><span data-stu-id="60d90-116">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="60d90-117">Фильтрация нежелательной почты отмечает сообщения как массовая электронная почта, основанная на пороге BCL (значение по умолчанию или указанное значение) и принимает указанное действие в сообщении (действие по умолчанию — доставка сообщения в папку нежелательной почты получателя). </span><span class="sxs-lookup"><span data-stu-id="60d90-117">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="60d90-118">Дополнительные сведения см. в [рублях Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="60d90-118">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="60d90-119">Пороговые значения BCL описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="60d90-119">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="60d90-120">BCL</span><span class="sxs-lookup"><span data-stu-id="60d90-120">BCL</span></span>|<span data-ttu-id="60d90-121">Описание</span><span class="sxs-lookup"><span data-stu-id="60d90-121">Description</span></span>|
|:---:|---|
|<span data-ttu-id="60d90-122">0</span><span class="sxs-lookup"><span data-stu-id="60d90-122">0</span></span>|<span data-ttu-id="60d90-123">Сообщение отправлено без использования систем массовой рассылки.</span><span class="sxs-lookup"><span data-stu-id="60d90-123">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="60d90-124">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="60d90-124">1, 2, 3</span></span>|<span data-ttu-id="60d90-125">Сообщение от системы массовой рассылки, которое вызывает малое количество жалоб.</span><span class="sxs-lookup"><span data-stu-id="60d90-125">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="60d90-126">4, 5, 6, 7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="60d90-126">4, 5, 6, 7<sup>\*</sup></span></span>|<span data-ttu-id="60d90-127">Сообщение от системы массовой рассылки, которое может вызвать как малое, так и большое количество жалоб.</span><span class="sxs-lookup"><span data-stu-id="60d90-127">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="60d90-128">8, 9</span><span class="sxs-lookup"><span data-stu-id="60d90-128">8, 9</span></span>|<span data-ttu-id="60d90-129">Сообщение от отправитель массы, который генерирует большое количество жалоб.</span><span class="sxs-lookup"><span data-stu-id="60d90-129">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|

<span data-ttu-id="60d90-130"><sup>\*</sup> Это пороговое значение по умолчанию, используемого в политиках по борьбе со спамом.</span><span class="sxs-lookup"><span data-stu-id="60d90-130"><sup>\*</sup> This is the default threshold value that's used in anti-spam policies.</span></span>
