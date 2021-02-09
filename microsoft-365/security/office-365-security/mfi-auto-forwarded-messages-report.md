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
description: Администраторы могут узнать об отчете об автоматической пересылке сообщений на панели мониторинга потока обработки почты в Центре безопасности & соответствия требованиям.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c95c403e0b342bf0466c45804ba3975c492b8e1b
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150606"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="e0df3-103">Анализ автоматически переад вперед сообщений в Центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="e0df3-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e0df3-104">**Относится к**</span><span class="sxs-lookup"><span data-stu-id="e0df3-104">**Applies to**</span></span>
- [<span data-ttu-id="e0df3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e0df3-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="e0df3-106">Microsoft Defender для Office 365 (план 1) и план 2</span><span class="sxs-lookup"><span data-stu-id="e0df3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="e0df3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e0df3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="e0df3-108">Анализ автоматически пересылаемой [](mail-flow-insights-v2.md) почты на [](https://protection.office.com) панели мониторинга потока обработки почты в Центре безопасности и соответствия требованиям & отображает сведения о сообщениях, которые автоматически пересылаются из организации получателям во внешних доменах. </span><span class="sxs-lookup"><span data-stu-id="e0df3-108">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Мини-приложения "Автооададант сообщений" в Центре & соответствия требованиям](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="e0df3-110">Сведения об автоматически переададантных сообщениях</span><span class="sxs-lookup"><span data-stu-id="e0df3-110">Auto-forwarded messages details</span></span>

<span data-ttu-id="e0df3-111">При нажатии на количество сообщений в мини-приложения появится отображаемая войдите в нее с дополнительными сведениями о сообщениях с автоматической переадной почтой:</span><span class="sxs-lookup"><span data-stu-id="e0df3-111">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="e0df3-112">**Автоматическая переададка сообщений с помощью методов переадной:**</span><span class="sxs-lookup"><span data-stu-id="e0df3-112">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="e0df3-113">**По правилам потока почты**</span><span class="sxs-lookup"><span data-stu-id="e0df3-113">**By mail flow rules**</span></span>
  - <span data-ttu-id="e0df3-114">**По правилам для входящих сообщений**</span><span class="sxs-lookup"><span data-stu-id="e0df3-114">**By Inbox rules**</span></span>
  - <span data-ttu-id="e0df3-115">**При пересылке SMTP** этот метод указывает автоматическую пересылку, которую администраторы могут настроить для почтового ящика, как описано в описании настройки пересылки электронной почты [для почтового ящика.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)</span><span class="sxs-lookup"><span data-stu-id="e0df3-115">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="e0df3-116">Ссылка на отчет о [переададпорте для](view-mail-flow-reports.md#forwarding-report) получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="e0df3-116">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="e0df3-117">**Автоматически переададантные сообщения по доменам и пользователям:**</span><span class="sxs-lookup"><span data-stu-id="e0df3-117">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="e0df3-118">**5 доменов, на которые переад.**</span><span class="sxs-lookup"><span data-stu-id="e0df3-118">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="e0df3-119">**Новые домены (на прошлой неделе)**</span><span class="sxs-lookup"><span data-stu-id="e0df3-119">**New domains (last week)**</span></span>
  - <span data-ttu-id="e0df3-120">**5 пользователей, переадлицющих в первую**</span><span class="sxs-lookup"><span data-stu-id="e0df3-120">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="e0df3-121">**Новые пользователи (на прошлой неделе)**</span><span class="sxs-lookup"><span data-stu-id="e0df3-121">**New users (last week)**</span></span>
  - <span data-ttu-id="e0df3-122">Ссылка на отчет об изменениях [переададантов](mfi-new-users-forwarding-email.md#forwarding-modifications-report) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="e0df3-122">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Details flyout for the Auto-forwarded messages report in the Security & Compliance Center](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="e0df3-124">Аналитика</span><span class="sxs-lookup"><span data-stu-id="e0df3-124">Insights</span></span>

<span data-ttu-id="e0df3-125">На основе данных отчета создаются два анализа:</span><span class="sxs-lookup"><span data-stu-id="e0df3-125">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="e0df3-126">Новые пользователи, переадлиющие электронную почту</span><span class="sxs-lookup"><span data-stu-id="e0df3-126">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="e0df3-127">Новые домены, переададантуемые по электронной почте</span><span class="sxs-lookup"><span data-stu-id="e0df3-127">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="e0df3-128">См. также</span><span class="sxs-lookup"><span data-stu-id="e0df3-128">See also</span></span>

<span data-ttu-id="e0df3-129">Сведения о других сведениях на панели мониторинга потока обработки почты см. в анализе потока обработки почты в Центре безопасности [& соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="e0df3-129">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
