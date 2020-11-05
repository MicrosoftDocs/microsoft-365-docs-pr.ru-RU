---
title: Анализ автоматически пересылаемых сообщений
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Администраторы могут ознакомиться с отчетом о сообщениях с автоматическим пересылкой в панели мониторинга "Направление почты" в центре безопасности & соответствия требованиям.
ms.openlocfilehash: 28cb593d56d0b0054c8c8cbe4596d4f7df6442ab
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920600"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="12842-103">Автоматически переадресованные сообщения в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="12842-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="12842-104">**Автоматически переадресованные сообщения** в [панели мониторинга "Направление почты](mail-flow-insights-v2.md) " в [центре безопасности & соответствия требованиям](https://protection.office.com) отображаются сведения о сообщениях, которые автоматически пересылаются из организации получателям во внешние домены.</span><span class="sxs-lookup"><span data-stu-id="12842-104">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Мини-приложение "автоматически переадресованные сообщения" в центре безопасности & соответствия требованиям](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="12842-106">Сведения о автоматически пересылаемых сообщениях</span><span class="sxs-lookup"><span data-stu-id="12842-106">Auto-forwarded messages details</span></span>

<span data-ttu-id="12842-107">Если щелкнуть число сообщений в мини-приложении, отобразится раскрывающаяся меню с дополнительными сведениями об автоматически пересылаемых сообщениях:</span><span class="sxs-lookup"><span data-stu-id="12842-107">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="12842-108">**Автоматически переадресованные сообщения пересылаются методами пересылки** :</span><span class="sxs-lookup"><span data-stu-id="12842-108">**Auto-forwarded messages by forwarding methods** :</span></span>

  - <span data-ttu-id="12842-109">**По правилам для почтового процесса**</span><span class="sxs-lookup"><span data-stu-id="12842-109">**By mail flow rules**</span></span>
  - <span data-ttu-id="12842-110">**Правила для папки "Входящие"**</span><span class="sxs-lookup"><span data-stu-id="12842-110">**By Inbox rules**</span></span>
  - <span data-ttu-id="12842-111">**При пересылке SMTP** : Этот метод указывает на автоматическую пересылку, которую администраторы могут настроить для почтового ящика, как описано в разделе [Настройка переадресации электронной почты для почтового ящика](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span><span class="sxs-lookup"><span data-stu-id="12842-111">**By SMTP forwarding** : This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="12842-112">Ссылка на [отчет о перенаправлении](view-mail-flow-reports.md#forwarding-report) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="12842-112">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="12842-113">**Автоматически перенаправляемые сообщения доменами и пользователями** :</span><span class="sxs-lookup"><span data-stu-id="12842-113">**Auto-forwarded messages by domains and users** :</span></span>

  - <span data-ttu-id="12842-114">**5 самых популярных доменов, переадресованных**</span><span class="sxs-lookup"><span data-stu-id="12842-114">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="12842-115">**Новые домены (за последнюю неделю)**</span><span class="sxs-lookup"><span data-stu-id="12842-115">**New domains (last week)**</span></span>
  - <span data-ttu-id="12842-116">**5 Топ пользователей пересылки**</span><span class="sxs-lookup"><span data-stu-id="12842-116">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="12842-117">**Новых пользователей (за последнюю неделю)**</span><span class="sxs-lookup"><span data-stu-id="12842-117">**New users (last week)**</span></span>
  - <span data-ttu-id="12842-118">Ссылка на отчет об [изменениях пересылки](mfi-new-users-forwarding-email.md#forwarding-modifications-report) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="12842-118">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Всплывающее меню сведений для отчета о автоматически пересылаемых сообщениях в центре безопасности & соответствия требованиям](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="12842-120">Аналитика</span><span class="sxs-lookup"><span data-stu-id="12842-120">Insights</span></span>

<span data-ttu-id="12842-121">В зависимости от данных отчета создается два аналитических отчета:</span><span class="sxs-lookup"><span data-stu-id="12842-121">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="12842-122">Новые пользователи, пересылаемые по электронной почте</span><span class="sxs-lookup"><span data-stu-id="12842-122">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="12842-123">Пересылка сообщений электронной почты для новых доменов</span><span class="sxs-lookup"><span data-stu-id="12842-123">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="12842-124">См. также</span><span class="sxs-lookup"><span data-stu-id="12842-124">See also</span></span>

<span data-ttu-id="12842-125">Сведения о других аналитиках в панели мониторинга для почтового процесса приведены в статье сведения о [почтовых сообщениях в центре безопасности & соответствия требованиям](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="12842-125">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
