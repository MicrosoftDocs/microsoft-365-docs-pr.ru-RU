---
title: Анализ автоматически пересылаемых сообщений
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Администраторы могут узнать о отчете о автоматических пересылаемом сообщении на панели мониторинга потока почты в Центре & соответствия требованиям.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1882c0506093816e9bb85ae3ba90decd4e0e0d74
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071317"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="41265-103">Сведения о автоматических сообщениях в Центре & безопасности</span><span class="sxs-lookup"><span data-stu-id="41265-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="41265-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="41265-104">**Applies to**</span></span>
- [<span data-ttu-id="41265-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="41265-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="41265-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="41265-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="41265-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41265-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="41265-108">В **информационной** панели потока почты в Центре обеспечения соответствия требованиям & автоматически переадружаемой из организации сообщения получателям во внешние [](mail-flow-insights-v2.md) домены. [](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="41265-108">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Виджет автопроизводимых сообщений в Центре & соответствия требованиям](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="41265-110">Сведения о автоматических сообщениях</span><span class="sxs-lookup"><span data-stu-id="41265-110">Auto-forwarded messages details</span></span>

<span data-ttu-id="41265-111">При нажатии на количество сообщений в виджете появляется поле для вылетов, которое отображает дополнительные сведения о автоматически переададных сообщениях:</span><span class="sxs-lookup"><span data-stu-id="41265-111">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="41265-112">**Автопроизводимые сообщения путем переададки методов:**</span><span class="sxs-lookup"><span data-stu-id="41265-112">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="41265-113">**По правилам потока почты**</span><span class="sxs-lookup"><span data-stu-id="41265-113">**By mail flow rules**</span></span>
  - <span data-ttu-id="41265-114">**По правилам "Входящие"**</span><span class="sxs-lookup"><span data-stu-id="41265-114">**By Inbox rules**</span></span>
  - <span data-ttu-id="41265-115">**По SMTP** пересылания : Этот метод указывает автоматическую пересылку, что администраторы могут настроить на почтовый ящик, как описано в Настройка пересылания электронной почты [для почтового ящика](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span><span class="sxs-lookup"><span data-stu-id="41265-115">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="41265-116">Дополнительные сведения по ссылке [на отчет о переадпорте.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="41265-116">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="41265-117">**Автопроизводимые сообщения доменов и пользователей:**</span><span class="sxs-lookup"><span data-stu-id="41265-117">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="41265-118">**Топ-5 доменов, переад**</span><span class="sxs-lookup"><span data-stu-id="41265-118">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="41265-119">**Новые домены (на прошлой неделе)**</span><span class="sxs-lookup"><span data-stu-id="41265-119">**New domains (last week)**</span></span>
  - <span data-ttu-id="41265-120">**Топ-5 пользователей переададки**</span><span class="sxs-lookup"><span data-stu-id="41265-120">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="41265-121">**Новые пользователи (на прошлой неделе)**</span><span class="sxs-lookup"><span data-stu-id="41265-121">**New users (last week)**</span></span>
  - <span data-ttu-id="41265-122">Дополнительные сведения по ссылке на отчет об [изменениях](mfi-new-users-forwarding-email.md#forwarding-modifications-report) в переадпорте.</span><span class="sxs-lookup"><span data-stu-id="41265-122">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Подробные сведения о отчете о автоматических сообщениях в Центре & безопасности](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="41265-124">Наблюдения</span><span class="sxs-lookup"><span data-stu-id="41265-124">Insights</span></span>

<span data-ttu-id="41265-125">На основе данных отчета создаются два анализа:</span><span class="sxs-lookup"><span data-stu-id="41265-125">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="41265-126">Новые пользователи, переададные электронной почте</span><span class="sxs-lookup"><span data-stu-id="41265-126">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="41265-127">Новые домены, отправленные по электронной почте</span><span class="sxs-lookup"><span data-stu-id="41265-127">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="41265-128">См. также</span><span class="sxs-lookup"><span data-stu-id="41265-128">See also</span></span>

<span data-ttu-id="41265-129">Сведения о других сведениях в панели мониторинга потока почты см. в странице Анализ потока почты в Центре [& соответствия](mail-flow-insights-v2.md)требованиям.</span><span class="sxs-lookup"><span data-stu-id="41265-129">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>