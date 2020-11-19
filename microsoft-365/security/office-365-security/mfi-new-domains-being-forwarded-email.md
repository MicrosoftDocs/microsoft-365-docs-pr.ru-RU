---
title: Анализ новых доменов, на которые пересылаются сообщения электронной почты
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Администраторы могут узнать, как использовать новые домены перенаправляемую электронную почту в панели мониторинга "Управление почтовыми ящиками" в центре безопасности & соответствия требованиям, чтобы выяснить, когда их пользователи пересылают сообщения на внешние домены, которые никогда не были переадресованы.
ms.openlocfilehash: a72ffd001ea22972d9dc6c00af8a4dd7881386b7
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356959"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="df987-103">Новые домены перенаправляемые сообщения электронной почты в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="df987-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="df987-104">Существуют допустимые бизнес-причины пересылки сообщений электронной почты внешним получателям в определенных доменах.</span><span class="sxs-lookup"><span data-stu-id="df987-104">There are valid business reasons to forward email messages to external recipients in specific domains.</span></span> <span data-ttu-id="df987-105">Однако она подозрительна, когда пользователи в вашей организации неожиданно начинают пересылать сообщения в домен, в котором никто из вашей организации не перенаправлял сообщения в (новый домен).</span><span class="sxs-lookup"><span data-stu-id="df987-105">However, it's suspicious when users in your organization suddenly start forwarding messages to a domain where no one in your organization has ever forwarded messages to (a new domain).</span></span>

<span data-ttu-id="df987-106">Это условие может означать, что учетные записи пользователей скомпрометированы.</span><span class="sxs-lookup"><span data-stu-id="df987-106">This condition might indicate that the user accounts are compromised.</span></span> <span data-ttu-id="df987-107">Если вы подозреваете, что учетные записи были скомпрометированы, ознакомьтесь со [статьей ответ на скомпрометированную учетную запись электронной почты](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="df987-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="df987-108">**Новые домены пересылаемые сообщения электронной почты** в [центре безопасности & соответствия требованиям](https://protection.office.com) уведомляют пользователя в Организации о пересылке сообщений в новые домены.</span><span class="sxs-lookup"><span data-stu-id="df987-108">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="df987-109">Это представление отображается только в том случае, если проблема обнаружена, и она отображается на странице [отчет о переадресации](view-mail-flow-reports.md#forwarding-report) .</span><span class="sxs-lookup"><span data-stu-id="df987-109">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Анализ новых доменов, на которые пересылаются сообщения электронной почты](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="df987-111">Если щелкнуть мини-приложение, появится раскрывающееся меню, в котором можно найти дополнительные сведения о переадресованных сообщениях, в том числе ссылку обратно в [отчет о переадресации](view-mail-flow-reports.md#forwarding-report).</span><span class="sxs-lookup"><span data-stu-id="df987-111">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![Всплывающее окно со сведениями, которое появляется после щелчка новых доменов, которые пересылаются по электронной почте](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="df987-113">Кроме того, вы можете перейти к этой странице сведений при выборе команды **Просмотреть все** в верхней области сведений **& рекомендации** (**Reports** \> **панель мониторинга** отчетов или <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="df987-113">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="df987-114">Чтобы предотвратить автоматическую переадресацию сообщений во внешние домены, настройте удаленный домен для некоторых или всех внешних доменов.</span><span class="sxs-lookup"><span data-stu-id="df987-114">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="df987-115">Дополнительные сведения см в разделе [Manage Remote Domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span><span class="sxs-lookup"><span data-stu-id="df987-115">For more information, see [Manage remote domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="df987-116">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="df987-116">Related topics</span></span>

<span data-ttu-id="df987-117">Сведения о других аналитиках в панели мониторинга для почтового процесса приведены в статье сведения о [почтовых сообщениях в центре безопасности & соответствия требованиям](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="df987-117">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
