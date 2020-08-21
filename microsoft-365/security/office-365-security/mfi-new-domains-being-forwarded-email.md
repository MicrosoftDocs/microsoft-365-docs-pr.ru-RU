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
description: Администраторы могут научиться использовать информацию о новых доменах, пересылаемых в современном Центре администрирования Exchange, чтобы определить, когда пользователи в организации пересылают сообщения на внешние домены, которые никогда не пересылались.
ms.openlocfilehash: 0b4cd0490feebc8e05deb889b3cf54e1ea9f5928
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826933"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="e5ad3-103">Новые домены, которые пересылают ся в Центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="e5ad3-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

<span data-ttu-id="e5ad3-104">Хотя у вас могут быть допустимые по финансовой причине пересылать сообщения внешним получателям в определенных доменах, подозрительным случаем может понадобиться, когда пользователи в организации неожиданны постоянно пересылают сообщения на внешние домены и никто в организации не останавливал отправлять сообщения еще до (новые домены).</span><span class="sxs-lookup"><span data-stu-id="e5ad3-104">Although you might have valid business reasons to forward email messages to external recipients in specific domains, it's suspicious when users in your organization suddenly start forwarding messages to external domains, and no one in the organization has ever forwarded messages to those domains before (new domains).</span></span> <span data-ttu-id="e5ad3-105">Это состояние может означать, что учетные записи пользователей были скомпрометированы.</span><span class="sxs-lookup"><span data-stu-id="e5ad3-105">This condition could indicate the user accounts are compromised.</span></span> <span data-ttu-id="e5ad3-106">Если вы подозревали, что учетные записи были скомпрометированы, см. раздел ["Реагирование на компрометацию учетной записи электронной почты".](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account)</span><span class="sxs-lookup"><span data-stu-id="e5ad3-106">If you suspect the accounts have been compromised, see [Responding to a compromised email account](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span></span>

<span data-ttu-id="e5ad3-107">Новые **домены, которые пересылают** сообщения электронной почты, уведомляют вас о пересылке сообщений пользователями в организации в новые домены.</span><span class="sxs-lookup"><span data-stu-id="e5ad3-107">The **New domains being forwarded email** insight notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="e5ad3-108">Эта аналитика появляется только при обнаружении проблемы и отображается на странице [отчета о пересылке.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="e5ad3-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Анализ новых доменов, на которые пересылаются сообщения электронной почты](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="e5ad3-110">Если щелкнуть мини-приложение, появляется всплывающий элемент, в котором можно получить дополнительные сведения о пересылаемых сообщениях, включая обратную ссылку на [отчет о пересылке.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="e5ad3-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![Всплывающий элемент "Подробности", который отображается после нажатия на новые домены, которые пересылают сообщения электронной почты](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="e5ad3-112">Вы также можете попадать на эту страницу сведений при выборе аналитики после нажатия кнопки **"Просмотреть** все" **в верхней & рекомендаций** в области рекомендования (**на панели** \> **мониторинга** <https://protection.office.com/insightdashboard> или).</span><span class="sxs-lookup"><span data-stu-id="e5ad3-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="e5ad3-113">Чтобы запретить автоматическую переадресацию сообщений на внешние домены, настройте удаленный домен для нескольких или всех этих доменов.</span><span class="sxs-lookup"><span data-stu-id="e5ad3-113">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="e5ad3-114">Дополнительные сведения см. в разделе ["Управление удаленными доменами" в Exchange Online.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)</span><span class="sxs-lookup"><span data-stu-id="e5ad3-114">For more information, see [Manage remote domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e5ad3-115">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="e5ad3-115">Related topics</span></span>

<span data-ttu-id="e5ad3-116">Сведения о других аналитических данных на панели мониторинга потока обработки почты см. в статье "Аналитика потока [обработки почты" в Центре безопасности & соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="e5ad3-116">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
