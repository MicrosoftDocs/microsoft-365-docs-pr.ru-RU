---
title: Анализ новых доменов, на которые пересылаются сообщения электронной почты
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: Администраторы могут узнать, как использовать новые домены, передав данные электронной почты в панели мониторинга потока почты в Центре соответствия требованиям & безопасности, чтобы выяснить, когда их пользователи переадружали сообщения на внешние домены, которые никогда не были переадружались.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1310350bd4ff6b43d321f5888c9436ac71debb82
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929352"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="6a35d-103">Новые домены, которые будут отправлены по электронной почте в Центре & безопасности</span><span class="sxs-lookup"><span data-stu-id="6a35d-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6a35d-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="6a35d-104">**Applies to**</span></span>
- [<span data-ttu-id="6a35d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="6a35d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="6a35d-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="6a35d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="6a35d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6a35d-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="6a35d-108">Существуют веские бизнес-причины для отправки сообщений электронной почты внешним получателям в определенных доменах.</span><span class="sxs-lookup"><span data-stu-id="6a35d-108">There are valid business reasons to forward email messages to external recipients in specific domains.</span></span> <span data-ttu-id="6a35d-109">Однако подозрительным является то, что пользователи в вашей организации внезапно начинают отправлять сообщения на домен, в котором никто из вашей организации никогда не переадверял сообщения в (новый домен).</span><span class="sxs-lookup"><span data-stu-id="6a35d-109">However, it's suspicious when users in your organization suddenly start forwarding messages to a domain where no one in your organization has ever forwarded messages to (a new domain).</span></span>

<span data-ttu-id="6a35d-110">Это условие может указывать на то, что учетные записи пользователей скомпрометированы.</span><span class="sxs-lookup"><span data-stu-id="6a35d-110">This condition might indicate that the user accounts are compromised.</span></span> <span data-ttu-id="6a35d-111">Если вы подозреваете, что учетные записи были скомпрометированы, см. в сообщении [Responding to a compromised email account.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="6a35d-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="6a35d-112">Сведения **о новых доменах,** [которые](https://protection.office.com) будут перенаадють по электронной почте в Центре соответствия требованиям & безопасности, будут извещение о том, когда пользователи в вашей организации перенаадлиют сообщения в новые домены.</span><span class="sxs-lookup"><span data-stu-id="6a35d-112">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="6a35d-113">Это представление появляется только при обнаружении проблемы и отображается на странице [отчета о переадпорте.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="6a35d-113">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Анализ новых доменов, на которые пересылаются сообщения электронной почты](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="6a35d-115">При нажатии на виджет появляется флажок, в котором можно найти дополнительные сведения о переадпортных сообщениях, включая ссылку на отчет [о переадпорте.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="6a35d-115">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![Подробные сведения, которые появляются после нажатия на новые домены, отправленные по электронной почте.](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="6a35d-117">Вы также можете получить эту страницу сведений,  когда вы  выберите представление после нажатия Просмотреть все в области & рекомендации на (**Отчеты** \> **панель мониторинга** или <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="6a35d-117">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="6a35d-118">Чтобы предотвратить автоматическую передачу сообщений во внешние домены, настройте удаленный домен для некоторых или всех внешних доменов.</span><span class="sxs-lookup"><span data-stu-id="6a35d-118">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="6a35d-119">Дополнительные сведения см. в [рублях Управление удаленными доменами в Exchange Online.](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)</span><span class="sxs-lookup"><span data-stu-id="6a35d-119">For more information, see [Manage remote domains in Exchange Online](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="6a35d-120">Родственные темы</span><span class="sxs-lookup"><span data-stu-id="6a35d-120">Related topics</span></span>

<span data-ttu-id="6a35d-121">Сведения о других сведениях в панели мониторинга потока почты см. в странице Анализ потока почты в Центре [& соответствия](mail-flow-insights-v2.md)требованиям.</span><span class="sxs-lookup"><span data-stu-id="6a35d-121">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>