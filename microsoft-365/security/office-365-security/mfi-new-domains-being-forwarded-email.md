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
ms.openlocfilehash: a4429f1657861091082fdfaedb52c85cec3a0cc1
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150609"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="20e30-103">Новые домены, перена которые перена электронная почта передается в Центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="20e30-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="20e30-104">**Относится к**</span><span class="sxs-lookup"><span data-stu-id="20e30-104">**Applies to**</span></span>
- [<span data-ttu-id="20e30-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="20e30-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="20e30-106">Microsoft Defender для Office 365 (план 1) и план 2</span><span class="sxs-lookup"><span data-stu-id="20e30-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="20e30-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="20e30-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="20e30-108">Существуют допустимые бизнес-причины для переадружия сообщений электронной почты внешним получателям в определенных доменах.</span><span class="sxs-lookup"><span data-stu-id="20e30-108">There are valid business reasons to forward email messages to external recipients in specific domains.</span></span> <span data-ttu-id="20e30-109">Тем не менее, это подозрительно, когда пользователи в вашей организации внезапно начинают переададантовку сообщений на домен, в который никто в вашей организации никогда не переадрил сообщения (новый домен).</span><span class="sxs-lookup"><span data-stu-id="20e30-109">However, it's suspicious when users in your organization suddenly start forwarding messages to a domain where no one in your organization has ever forwarded messages to (a new domain).</span></span>

<span data-ttu-id="20e30-110">Это условие может указывать на то, что учетные записи пользователей скомпрометированы.</span><span class="sxs-lookup"><span data-stu-id="20e30-110">This condition might indicate that the user accounts are compromised.</span></span> <span data-ttu-id="20e30-111">Если вы подозреваете, что учетные записи были скомпрометированы, см. ответ на компрометации учетной [записи электронной почты.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="20e30-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="20e30-112">Сведения **о новых доменах,** перена которые будут перена отправляться по электронной почте в Центре безопасности и соответствия & соответствия требованиям, будут отправлять сообщения пользователям в организации на новые домены. [](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="20e30-112">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="20e30-113">Эта информация отображается только при обнаружении проблемы и отображается на странице отчета ["Переад](view-mail-flow-reports.md#forwarding-report) сообщений".</span><span class="sxs-lookup"><span data-stu-id="20e30-113">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Анализ новых доменов, на которые пересылаются сообщения электронной почты](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="20e30-115">При нажатии мини-приложения появится элемент, в котором можно найти дополнительные сведения о переададантных сообщениях, в том числе ссылку на отчет о [переадпорте.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="20e30-115">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![Flyout Details that appears after clicking on the New domains being forwarded email insight](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="20e30-117">Вы также можете вернуться на эту страницу  сведений при выборе статистики после нажатия кнопки "Просмотреть все в области "Лучшие **сведения&** рекомендации"**(** панель мониторинга отчетов \>  или <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="20e30-117">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="20e30-118">Чтобы запретить автоматическую переадружение сообщений на внешние домены, настройте удаленный домен для некоторых или всех внешних доменов.</span><span class="sxs-lookup"><span data-stu-id="20e30-118">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="20e30-119">Дополнительные сведения см. в под [управлением удаленных доменов в Exchange Online.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)</span><span class="sxs-lookup"><span data-stu-id="20e30-119">For more information, see [Manage remote domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="20e30-120">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="20e30-120">Related topics</span></span>

<span data-ttu-id="20e30-121">Сведения о других сведениях на панели мониторинга потока обработки почты см. в анализе потока обработки почты в Центре безопасности [& соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="20e30-121">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
