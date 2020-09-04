---
title: Анализ новых доменов, на которые пересылаются сообщения электронной почты
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Администраторы могут узнать, как использовать новые домены, перенаправляемые по электронной почте, в современном центре администрирования Exchange, чтобы выяснить, когда пользователи в Организации пересылают сообщения на внешние домены, которые никогда не были переадресованы.
ms.openlocfilehash: 0f0622fc686cb9c90790630e16c187bf9f69d918
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358262"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="43606-103">Новые домены перенаправляемые сообщения электронной почты в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="43606-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

<span data-ttu-id="43606-104">Несмотря на то, что вы могли пересылать сообщения электронной почты внешним получателям в определенных доменах, это подозрительно, когда пользователи в вашей организации неожиданно начинают пересылать сообщения на внешние домены, и никто из них не перенаправлял сообщения в эти домены до (новые домены).</span><span class="sxs-lookup"><span data-stu-id="43606-104">Although you might have valid business reasons to forward email messages to external recipients in specific domains, it's suspicious when users in your organization suddenly start forwarding messages to external domains, and no one in the organization has ever forwarded messages to those domains before (new domains).</span></span> <span data-ttu-id="43606-105">Это условие может означать, что учетные записи пользователей скомпрометированы.</span><span class="sxs-lookup"><span data-stu-id="43606-105">This condition could indicate the user accounts are compromised.</span></span> <span data-ttu-id="43606-106">Если вы подозреваете, что учетные записи были скомпрометированы, ознакомьтесь со [статьей ответ на скомпрометированную учетную запись электронной почты](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span><span class="sxs-lookup"><span data-stu-id="43606-106">If you suspect the accounts have been compromised, see [Responding to a compromised email account](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span></span>

<span data-ttu-id="43606-107">**Новые домены пересылаемые сообщения электронной почты** в [центре безопасности & соответствия требованиям](https://protection.office.com) уведомляют пользователя в Организации о пересылке сообщений в новые домены.</span><span class="sxs-lookup"><span data-stu-id="43606-107">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="43606-108">Это представление отображается только в том случае, если проблема обнаружена, и она отображается на странице [отчет о переадресации](view-mail-flow-reports.md#forwarding-report) .</span><span class="sxs-lookup"><span data-stu-id="43606-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Анализ новых доменов, на которые пересылаются сообщения электронной почты](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="43606-110">Если щелкнуть мини-приложение, появится раскрывающееся меню, в котором можно найти дополнительные сведения о переадресованных сообщениях, в том числе ссылку обратно в [отчет о переадресации](view-mail-flow-reports.md#forwarding-report).</span><span class="sxs-lookup"><span data-stu-id="43606-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![Всплывающее окно со сведениями, которое появляется после щелчка новых доменов, которые пересылаются по электронной почте](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="43606-112">Кроме того, вы можете перейти к этой странице сведений при выборе команды **Просмотреть все** в верхней области сведений **& рекомендации** (**Reports** \> **панель мониторинга** отчетов или <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="43606-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="43606-113">Чтобы предотвратить автоматическую переадресацию сообщений во внешние домены, настройте удаленный домен для некоторых или всех внешних доменов.</span><span class="sxs-lookup"><span data-stu-id="43606-113">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="43606-114">Дополнительные сведения см в разделе [Manage Remote Domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span><span class="sxs-lookup"><span data-stu-id="43606-114">For more information, see [Manage remote domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="43606-115">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="43606-115">Related topics</span></span>

<span data-ttu-id="43606-116">Сведения о других аналитиках в панели мониторинга для почтового процесса приведены в статье сведения о [почтовых сообщениях в центре безопасности & соответствия требованиям](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="43606-116">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
