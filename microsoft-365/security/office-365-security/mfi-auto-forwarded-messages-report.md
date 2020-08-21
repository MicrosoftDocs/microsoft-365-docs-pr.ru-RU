---
title: Анализ автоматически пересылаемых сообщений
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Администраторы могут получить информацию об отчете по автоматически пересылаемым сообщениям на панели мониторинга потока обработки почты в Центре безопасности & соответствия требованиям.
ms.openlocfilehash: 8d1a3ffe5ffc16a7793826b98b130121b8e68599
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827031"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="ebbcd-103">Аналитика автоматически пересланных сообщений в Центре безопасности & требованиям</span><span class="sxs-lookup"><span data-stu-id="ebbcd-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

<span data-ttu-id="ebbcd-104">На **информационной панели** потока обработки [Mail flow dashboard](mail-flow-insights-v2.md) почты в Центре соответствия требованиям безопасности & отображаются сведения о сообщениях, автоматически пересланных из вашей организации получателям во внешние домены.</span><span class="sxs-lookup"><span data-stu-id="ebbcd-104">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Мини-приложение "Автоматически пересылаемые сообщения" в Центре безопасности & соответствия требованиям](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="ebbcd-106">Сведения об автоматической пересылке сообщений</span><span class="sxs-lookup"><span data-stu-id="ebbcd-106">Auto-forwarded messages details</span></span>

<span data-ttu-id="ebbcd-107">Если щелкнуть количество сообщений в мини-приложении, появится всплывающий элемент, в котором отображаются дополнительные сведения об автоматически пересылаемых сообщениях:</span><span class="sxs-lookup"><span data-stu-id="ebbcd-107">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="ebbcd-108">**Автоматически пересылаемые сообщения путем пересылки методов:**</span><span class="sxs-lookup"><span data-stu-id="ebbcd-108">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="ebbcd-109">**по правилам потока обработки почты;**</span><span class="sxs-lookup"><span data-stu-id="ebbcd-109">**By mail flow rules**</span></span>
  - <span data-ttu-id="ebbcd-110">**Правилами для папки "Входящие"**</span><span class="sxs-lookup"><span data-stu-id="ebbcd-110">**By Inbox rules**</span></span>
  - <span data-ttu-id="ebbcd-111">**пересылка SMTP;**</span><span class="sxs-lookup"><span data-stu-id="ebbcd-111">**By SMTP forwarding**</span></span>
  - <span data-ttu-id="ebbcd-112">Ссылка на отчет о [пересылке для получения](view-mail-flow-reports.md#forwarding-report) дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="ebbcd-112">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="ebbcd-113">**Автоматически пересылаемые сообщения доменами и пользователями:**</span><span class="sxs-lookup"><span data-stu-id="ebbcd-113">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="ebbcd-114">**5: перенаправленные 5 доменов**</span><span class="sxs-lookup"><span data-stu-id="ebbcd-114">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="ebbcd-115">**Новые домены (последняя неделя)**</span><span class="sxs-lookup"><span data-stu-id="ebbcd-115">**New domains (last week)**</span></span>
  - <span data-ttu-id="ebbcd-116">**5 пользователей с пересылкой: 5 пользователей с пересылк**</span><span class="sxs-lookup"><span data-stu-id="ebbcd-116">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="ebbcd-117">**Новые пользователи (прошлая неделя)**</span><span class="sxs-lookup"><span data-stu-id="ebbcd-117">**New users (last week)**</span></span>
  - <span data-ttu-id="ebbcd-118">Ссылка на отчет [изменений пересылки для получения дополнительных](mfi-new-users-forwarding-email.md#forwarding-modifications-report) сведений.</span><span class="sxs-lookup"><span data-stu-id="ebbcd-118">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Всплывающую информацию о отчете автоматически пересылаемых сообщений в Центре безопасности & требованиям](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="ebbcd-120">Аналитика</span><span class="sxs-lookup"><span data-stu-id="ebbcd-120">Insights</span></span>

<span data-ttu-id="ebbcd-121">На основе данных отчета создаются два данных:</span><span class="sxs-lookup"><span data-stu-id="ebbcd-121">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="ebbcd-122">Новые пользователи пересылают электронную почту</span><span class="sxs-lookup"><span data-stu-id="ebbcd-122">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="ebbcd-123">Сообщения электронной почты, пересылаемые для новых доменов</span><span class="sxs-lookup"><span data-stu-id="ebbcd-123">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="ebbcd-124">См. также</span><span class="sxs-lookup"><span data-stu-id="ebbcd-124">See also</span></span>

<span data-ttu-id="ebbcd-125">Сведения о других аналитических данных на панели мониторинга потока обработки почты см. в статье "Аналитика потока [обработки почты" в Центре безопасности & соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="ebbcd-125">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
