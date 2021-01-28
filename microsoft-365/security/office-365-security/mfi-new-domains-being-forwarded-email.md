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
description: Администраторы могут узнать, как использовать новые домены, пересылаемые по электронной почте, на панели мониторинга потока обработки почты в Центре безопасности и соответствия требованиям, чтобы выяснить, когда их пользователи пересылают сообщения на внешние домены, на которые никогда не пересылались сообщения. &
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: eb44f5d577d18fc38333cca5e8d2d862f288a2e0
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029862"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="d02e1-103">Новые домены, перена которые будут перенаад а через Центр безопасности и соответствия & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="d02e1-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d02e1-104">Существуют допустимые бизнес-причины для переадружия сообщений электронной почты внешним получателям в определенных доменах.</span><span class="sxs-lookup"><span data-stu-id="d02e1-104">There are valid business reasons to forward email messages to external recipients in specific domains.</span></span> <span data-ttu-id="d02e1-105">Тем не менее, это подозрительно, когда пользователи в вашей организации внезапно начинают переададантовку сообщений на домен, в который никто в вашей организации никогда не переадрил сообщения (новый домен).</span><span class="sxs-lookup"><span data-stu-id="d02e1-105">However, it's suspicious when users in your organization suddenly start forwarding messages to a domain where no one in your organization has ever forwarded messages to (a new domain).</span></span>

<span data-ttu-id="d02e1-106">Это условие может указывать на то, что учетные записи пользователей скомпрометированы.</span><span class="sxs-lookup"><span data-stu-id="d02e1-106">This condition might indicate that the user accounts are compromised.</span></span> <span data-ttu-id="d02e1-107">Если вы подозреваете, что учетные записи были скомпрометированы, см. ответ на компрометации учетной [записи электронной почты.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="d02e1-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="d02e1-108">Сведения **о новых доменах,** перена которые будут перена отправляться по электронной почте в Центре безопасности & [соответствия](https://protection.office.com) требованиям, будут извещение о том, когда пользователи в вашей организации перенабовыют сообщения на новые домены.</span><span class="sxs-lookup"><span data-stu-id="d02e1-108">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="d02e1-109">Эта информация отображается только при обнаружении проблемы и отображается на странице отчета ["Переадпорт".](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="d02e1-109">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Анализ новых доменов, на которые пересылаются сообщения электронной почты](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="d02e1-111">При нажатии мини-приложения появится элемент, в котором можно найти дополнительные сведения о переададантных сообщениях, в том числе ссылку на отчет о [переадпорте.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="d02e1-111">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![Flyout Details that appears after clicking on the New domains being forwarded email insight](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="d02e1-113">Вы также можете вернуться на эту страницу  сведений при выборе статистики после нажатия кнопки "Просмотреть все в области "Лучшие **сведения&** рекомендации"**(** панель мониторинга отчетов \>  или <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="d02e1-113">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="d02e1-114">Чтобы запретить автоматическую переадружение сообщений на внешние домены, настройте удаленный домен для некоторых или всех внешних доменов.</span><span class="sxs-lookup"><span data-stu-id="d02e1-114">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="d02e1-115">Дополнительные сведения см. в под [управлением удаленных доменов в Exchange Online.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)</span><span class="sxs-lookup"><span data-stu-id="d02e1-115">For more information, see [Manage remote domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d02e1-116">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="d02e1-116">Related topics</span></span>

<span data-ttu-id="d02e1-117">Сведения о других сведениях на панели мониторинга потока обработки почты см. в анализе потока обработки почты в Центре безопасности [& соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="d02e1-117">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
