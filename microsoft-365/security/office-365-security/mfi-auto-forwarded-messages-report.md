---
title: Сведения о автоматически перенаправляемых сообщениях
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Администраторы могут ознакомиться с отчетом о сообщениях с автоматическим пересылкой в панели мониторинга "Направление почты" в центре безопасности & соответствия требованиям.
ms.openlocfilehash: 05e3f62610c32bc95caf579ef4dd46bf1ed90275
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577823"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="de4bf-103">Автоматически переадресованные сообщения в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="de4bf-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

<span data-ttu-id="de4bf-104">**Автоматически переадресованные сообщения** в [панели мониторинга "Направление почты](mail-flow-insights-v2.md) " в центре безопасности & соответствия требованиям отображаются сведения о сообщениях, которые автоматически пересылаются из организации получателям во внешние домены.</span><span class="sxs-lookup"><span data-stu-id="de4bf-104">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Мини-приложение "автоматически переадресованные сообщения" в центре безопасности & соответствия требованиям](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="de4bf-106">Сведения о автоматически пересылаемых сообщениях</span><span class="sxs-lookup"><span data-stu-id="de4bf-106">Auto-forwarded messages details</span></span>

<span data-ttu-id="de4bf-107">Если щелкнуть число сообщений в мини-приложении, отобразится раскрывающаяся меню с дополнительными сведениями об автоматически пересылаемых сообщениях:</span><span class="sxs-lookup"><span data-stu-id="de4bf-107">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="de4bf-108">**Автоматически переадресованные сообщения пересылаются методами пересылки**:</span><span class="sxs-lookup"><span data-stu-id="de4bf-108">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="de4bf-109">**По правилам для почтового процесса**</span><span class="sxs-lookup"><span data-stu-id="de4bf-109">**By mail flow rules**</span></span>
  - <span data-ttu-id="de4bf-110">**Правила для папки "Входящие"**</span><span class="sxs-lookup"><span data-stu-id="de4bf-110">**By Inbox rules**</span></span>
  - <span data-ttu-id="de4bf-111">**С помощью пересылки SMTP**</span><span class="sxs-lookup"><span data-stu-id="de4bf-111">**By SMTP forwarding**</span></span>
  - <span data-ttu-id="de4bf-112">Ссылка на [отчет о перенаправлении](view-mail-flow-reports.md#forwarding-report) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="de4bf-112">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="de4bf-113">**Автоматически перенаправляемые сообщения доменами и пользователями**:</span><span class="sxs-lookup"><span data-stu-id="de4bf-113">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="de4bf-114">**5 самых популярных доменов, переадресованных**</span><span class="sxs-lookup"><span data-stu-id="de4bf-114">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="de4bf-115">**Новые домены (за последнюю неделю)**</span><span class="sxs-lookup"><span data-stu-id="de4bf-115">**New domains (last week)**</span></span>
  - <span data-ttu-id="de4bf-116">**5 Топ пользователей пересылки**</span><span class="sxs-lookup"><span data-stu-id="de4bf-116">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="de4bf-117">**Новых пользователей (за последнюю неделю)**</span><span class="sxs-lookup"><span data-stu-id="de4bf-117">**New users (last week)**</span></span>
  - <span data-ttu-id="de4bf-118">Ссылка на отчет об [изменениях пересылки](mfi-new-users-forwarding-email.md#forwarding-modifications-report) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="de4bf-118">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Всплывающее меню сведений для отчета о автоматически пересылаемых сообщениях в центре безопасности & соответствия требованиям](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="de4bf-120">Аналитика</span><span class="sxs-lookup"><span data-stu-id="de4bf-120">Insights</span></span>

<span data-ttu-id="de4bf-121">В зависимости от данных отчета создается два аналитических отчета:</span><span class="sxs-lookup"><span data-stu-id="de4bf-121">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="de4bf-122">Новые пользователи, пересылаемые по электронной почте</span><span class="sxs-lookup"><span data-stu-id="de4bf-122">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="de4bf-123">Пересылка сообщений электронной почты для новых доменов</span><span class="sxs-lookup"><span data-stu-id="de4bf-123">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="de4bf-124">См. также</span><span class="sxs-lookup"><span data-stu-id="de4bf-124">See also</span></span>

<span data-ttu-id="de4bf-125">Сведения о других аналитиках в панели мониторинга для почтового процесса приведены в статье сведения о [почтовых сообщениях в центре безопасности & соответствия требованиям](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="de4bf-125">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
