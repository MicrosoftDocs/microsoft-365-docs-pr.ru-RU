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
ms.openlocfilehash: c892400152df15adb3dfeb0c747ed7fae034d3d6
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029946"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="5725d-103">Анализ автоматически переададантных сообщений в Центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="5725d-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="5725d-104">Анализ автоматически пересылаемой [](mail-flow-insights-v2.md) почты на [](https://protection.office.com) панели мониторинга потока обработки почты в Центре безопасности и соответствия требованиям & отображает сведения о сообщениях, которые автоматически пересылаются из организации получателям во внешних доменах. </span><span class="sxs-lookup"><span data-stu-id="5725d-104">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Мини-приложения "Автооададант сообщений" в Центре & соответствия требованиям](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="5725d-106">Сведения об автоматически переададантных сообщениях</span><span class="sxs-lookup"><span data-stu-id="5725d-106">Auto-forwarded messages details</span></span>

<span data-ttu-id="5725d-107">При нажатии на количество сообщений в мини-приложения появляется выпадающего области, которая отображает дополнительные сведения о сообщениях с автоматической переадной:</span><span class="sxs-lookup"><span data-stu-id="5725d-107">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="5725d-108">**Автоматическая переададка сообщений с помощью методов переадной:**</span><span class="sxs-lookup"><span data-stu-id="5725d-108">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="5725d-109">**По правилам потока почты**</span><span class="sxs-lookup"><span data-stu-id="5725d-109">**By mail flow rules**</span></span>
  - <span data-ttu-id="5725d-110">**По правилам для входящих сообщений**</span><span class="sxs-lookup"><span data-stu-id="5725d-110">**By Inbox rules**</span></span>
  - <span data-ttu-id="5725d-111">**По пересылке SMTP:** этот метод указывает автоматическую пересылку, которую администраторы могут настроить для почтового ящика, как описано в описании настройки пересылки электронной почты [для почтового ящика.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)</span><span class="sxs-lookup"><span data-stu-id="5725d-111">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="5725d-112">Ссылка на отчет о [переададпорте для](view-mail-flow-reports.md#forwarding-report) получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="5725d-112">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="5725d-113">**Автоматически переадливаемые сообщения по доменам и пользователям:**</span><span class="sxs-lookup"><span data-stu-id="5725d-113">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="5725d-114">**5 доменов, на которые переад.**</span><span class="sxs-lookup"><span data-stu-id="5725d-114">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="5725d-115">**Новые домены (на прошлой неделе)**</span><span class="sxs-lookup"><span data-stu-id="5725d-115">**New domains (last week)**</span></span>
  - <span data-ttu-id="5725d-116">**5 пользователей, переадлицющих в верхнюю часть**</span><span class="sxs-lookup"><span data-stu-id="5725d-116">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="5725d-117">**Новые пользователи (на прошлой неделе)**</span><span class="sxs-lookup"><span data-stu-id="5725d-117">**New users (last week)**</span></span>
  - <span data-ttu-id="5725d-118">Ссылка на отчет об изменениях [переададантов](mfi-new-users-forwarding-email.md#forwarding-modifications-report) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="5725d-118">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Details flyout for the Auto-forwarded messages report in the Security & Compliance Center](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="5725d-120">Аналитика</span><span class="sxs-lookup"><span data-stu-id="5725d-120">Insights</span></span>

<span data-ttu-id="5725d-121">На основе данных отчета создаются два анализа:</span><span class="sxs-lookup"><span data-stu-id="5725d-121">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="5725d-122">Новые пользователи, переадлиющие электронную почту</span><span class="sxs-lookup"><span data-stu-id="5725d-122">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="5725d-123">Новые домены, перена которые перенабовыются по электронной почте</span><span class="sxs-lookup"><span data-stu-id="5725d-123">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="5725d-124">См. также</span><span class="sxs-lookup"><span data-stu-id="5725d-124">See also</span></span>

<span data-ttu-id="5725d-125">Сведения о других сведениях на панели мониторинга потока обработки почты см. в анализе потока обработки почты в Центре безопасности [& соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="5725d-125">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
