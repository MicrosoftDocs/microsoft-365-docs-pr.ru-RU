---
title: Представления в обозревателе угроз и обнаружения в режиме реального времени
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Узнайте, как использовать обозреватель угроз и отчет об обнаружении в реальном времени для изучения угроз и реагирования на них в центре безопасности & соответствия требованиям.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b7300f8c87b100a38117b0cc4bee1bb95c9584c6
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615712"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="38023-103">Представления в обозревателе угроз и обнаружения в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="38023-103">Views in Threat Explorer and real-time detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


![Обозреватель угроз](../../media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="38023-105">[Обозреватель угроз](threat-explorer.md) (и отчет об обнаружении в режиме реального времени) — это мощное почти то же средство, которое помогает системам безопасности Teams исследовать и отвечать на угрозы в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="38023-105">[Threat Explorer](threat-explorer.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security & Compliance Center.</span></span> <span data-ttu-id="38023-106">В проводнике (и отчете об обнаружении в режиме реального времени) отображаются сведения о потенциальных вредоносных и мошеннических программах в электронной почте и файлах в Office 365, а также о других угрозах безопасности и рисках для Организации.</span><span class="sxs-lookup"><span data-stu-id="38023-106">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span>

- <span data-ttu-id="38023-107">Если у вас есть [защитник Майкрософт для Office 365](office-365-atp.md) (план 2), то у вас есть проводник.</span><span class="sxs-lookup"><span data-stu-id="38023-107">If you have [Microsoft Defender for Office 365](office-365-atp.md) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="38023-108">Если у вас есть защитник Майкрософт для Office 365, план 1, то у вас есть обнаружение в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="38023-108">If you have Microsoft Defender for Office 365 Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="38023-109">При первом открытии проводника (или отчета по обнаружениям в режиме реального времени) представление по умолчанию показывает обнаружение вредоносных программ по электронной почте за прошедшие 7 дней.</span><span class="sxs-lookup"><span data-stu-id="38023-109">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="38023-110">В этом отчете также могут отображаться защитники Майкрософт для Office 365, например вредоносные ссылки, обнаруженные [безопасными ссылками](atp-safe-links.md), а также вредоносные файлы, обнаруженные [безопасными вложениями](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="38023-110">This report can also show Microsoft Defender for Office 365 detections, such as malicious URLs detected by [Safe Links](atp-safe-links.md), and malicious files detected by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="38023-111">Этот отчет можно изменить, чтобы показать данные за прошедшие 30 дней (с помощью защитника Майкрософт для подписки Майкрософт на Office 365 P2).</span><span class="sxs-lookup"><span data-stu-id="38023-111">This report can be modified to show data for the past 30 days (with a Microsoft Defender for Office 365 P2 paid subscription).</span></span> <span data-ttu-id="38023-112">Пробные подписки будут включать данные только за прошедшие семь дней.</span><span class="sxs-lookup"><span data-stu-id="38023-112">Trial subscriptions will include data for the past seven days only.</span></span>

****

|<span data-ttu-id="38023-113">Подписка</span><span class="sxs-lookup"><span data-stu-id="38023-113">Subscription</span></span>|<span data-ttu-id="38023-114">Служебная программа</span><span class="sxs-lookup"><span data-stu-id="38023-114">Utility</span></span>|<span data-ttu-id="38023-115">Дни данных</span><span class="sxs-lookup"><span data-stu-id="38023-115">Days of Data</span></span>|
|---|---|---|
|<span data-ttu-id="38023-116">Пробная версия защитника Майкрософт для Office 365 P1</span><span class="sxs-lookup"><span data-stu-id="38023-116">Microsoft Defender for Office 365 P1 trial</span></span>|<span data-ttu-id="38023-117">Обнаружение в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="38023-117">Real-time detections</span></span>|<span data-ttu-id="38023-118">7 </span><span class="sxs-lookup"><span data-stu-id="38023-118">7</span></span>|
|<span data-ttu-id="38023-119">Защитник Майкрософт для Office 365 P1 оплачен</span><span class="sxs-lookup"><span data-stu-id="38023-119">Microsoft Defender for Office 365 P1 paid</span></span>|<span data-ttu-id="38023-120">Обнаружение в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="38023-120">Real-time detections</span></span>|<span data-ttu-id="38023-121">более</span><span class="sxs-lookup"><span data-stu-id="38023-121">30</span></span>|
|<span data-ttu-id="38023-122">Защитник Майкрософт для Office 365 P1 с платным тестированием — пробная версия защитника для Office 365 P2</span><span class="sxs-lookup"><span data-stu-id="38023-122">Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="38023-123">Обозреватель угроз</span><span class="sxs-lookup"><span data-stu-id="38023-123">Threat Explorer</span></span>|<span data-ttu-id="38023-124">7 </span><span class="sxs-lookup"><span data-stu-id="38023-124">7</span></span>|
|<span data-ttu-id="38023-125">Пробная версия защитника Майкрософт для Office 365 P2</span><span class="sxs-lookup"><span data-stu-id="38023-125">Microsoft Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="38023-126">Обозреватель угроз</span><span class="sxs-lookup"><span data-stu-id="38023-126">Threat Explorer</span></span>|<span data-ttu-id="38023-127">7 </span><span class="sxs-lookup"><span data-stu-id="38023-127">7</span></span>|
|<span data-ttu-id="38023-128">Защитник Майкрософт для Office 365 P2 оплачен</span><span class="sxs-lookup"><span data-stu-id="38023-128">Microsoft Defender for Office 365 P2 paid</span></span>|<span data-ttu-id="38023-129">Обозреватель угроз</span><span class="sxs-lookup"><span data-stu-id="38023-129">Threat Explorer</span></span>|<span data-ttu-id="38023-130">более</span><span class="sxs-lookup"><span data-stu-id="38023-130">30</span></span>|
|

<span data-ttu-id="38023-131">Используйте меню **вид** для изменения отображаемых сведений.</span><span class="sxs-lookup"><span data-stu-id="38023-131">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="38023-132">Подсказки помогут определить, какое представление использовать.</span><span class="sxs-lookup"><span data-stu-id="38023-132">Tooltips help you determine which view to use.</span></span>

![Меню "вид" обозревателя угроз](../../media/ThreatExplorerViewMenu.png)

<span data-ttu-id="38023-134">После выбора представления можно применить фильтры и настроить запросы для дальнейшего анализа.</span><span class="sxs-lookup"><span data-stu-id="38023-134">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="38023-135">В следующих разделах представлен краткий обзор различных представлений, доступных в проводнике (или обнаружения в режиме реального времени).</span><span class="sxs-lookup"><span data-stu-id="38023-135">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>

## <a name="email--malware"></a><span data-ttu-id="38023-136">Вредоносная > по электронной почте</span><span class="sxs-lookup"><span data-stu-id="38023-136">Email > Malware</span></span>

<span data-ttu-id="38023-137">Чтобы просмотреть этот отчет, в проводнике (или обнаружения в режиме реального времени) выберите **Просмотр** \>  \> **вредоносных программ** электронной почты.</span><span class="sxs-lookup"><span data-stu-id="38023-137">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Malware**.</span></span> <span data-ttu-id="38023-138">В этом представлении отображаются сведения о сообщениях электронной почты, которые были идентифицированы как содержащие вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="38023-138">This view shows information about email messages that were identified as containing malware.</span></span>

![Просмотр данных о сообщении электронной почты, которое определено как вредоносное](../../media/ExplorerEmailMalwareMenu.png)

<span data-ttu-id="38023-140">Нажмите кнопку **отправитель** , чтобы открыть список параметров просмотра.</span><span class="sxs-lookup"><span data-stu-id="38023-140">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="38023-141">Этот список используется для просмотра данных по отправителям, получателям, доменам отправителей, темам, технологиям обнаружения, состояниям защиты и т. д.</span><span class="sxs-lookup"><span data-stu-id="38023-141">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span>

<span data-ttu-id="38023-142">Например, чтобы узнать, какие действия были выполнены с обнаруженными сообщениями электронной почты, выберите **состояние защиты** в списке.</span><span class="sxs-lookup"><span data-stu-id="38023-142">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="38023-143">Выберите параметр, а затем нажмите кнопку обновить, чтобы применить этот фильтр к отчету.</span><span class="sxs-lookup"><span data-stu-id="38023-143">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![Параметры состояния защиты от угроз для обозревателя угроз](../../media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="38023-145">Под диаграммой просмотрите дополнительные сведения о конкретных сообщениях.</span><span class="sxs-lookup"><span data-stu-id="38023-145">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="38023-146">При выборе элемента в списке открывается область "вылет", в которой можно узнать больше о выбранном элементе.</span><span class="sxs-lookup"><span data-stu-id="38023-146">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Обозреватель угроз с открытым всплывающим окном](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="38023-148">Электронная почта > фишинга</span><span class="sxs-lookup"><span data-stu-id="38023-148">Email > Phish</span></span>

<span data-ttu-id="38023-149">Чтобы просмотреть этот отчет, в проводнике (или обнаружения в режиме реального времени) выберите **Просмотр** \>  \> **фишинга** электронной почты.</span><span class="sxs-lookup"><span data-stu-id="38023-149">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Phish**.</span></span> <span data-ttu-id="38023-150">В этом представлении отображаются сообщения электронной почты, которые определены как попытки фишинга.</span><span class="sxs-lookup"><span data-stu-id="38023-150">This view shows email messages identified as phishing attempts.</span></span>

![Просмотр данных о почтовых сообщениях, определенных как попытки фишинга](../../media/ThreatExplorerEmailPhish.png)

<span data-ttu-id="38023-152">Нажмите кнопку **отправитель** , чтобы открыть список параметров просмотра.</span><span class="sxs-lookup"><span data-stu-id="38023-152">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="38023-153">Используйте этот список для просмотра данных по отправителям, получателям, доменам отправителей, IP-адресу отправителя, домену URL-адресов, нажмите вредоносности и дополнительно.</span><span class="sxs-lookup"><span data-stu-id="38023-153">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span>

<span data-ttu-id="38023-154">Например, чтобы узнать, какие действия были предприняты при нажатии на URL-адреса, идентифицированные как попытки фишинга, выберите **пункт вредоносности** в списке, выберите один или несколько параметров, а затем нажмите кнопку Обновить.</span><span class="sxs-lookup"><span data-stu-id="38023-154">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![Нажмите кнопку вредоносности Options (параметры) для отчета по фишингу](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="38023-156">Под диаграммой просмотрите дополнительные сведения о конкретных сообщениях, нажатии URL-адресов, URL-адреса и источник электронной почты.</span><span class="sxs-lookup"><span data-stu-id="38023-156">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span>

![URL-адреса, обнаруженные в сообщениях электронной почты как фишинг](../../media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="38023-158">При выборе элемента в списке, например обнаруженного URL-адреса, открывается область "вылет", в которой можно узнать больше о выбранном элементе.</span><span class="sxs-lookup"><span data-stu-id="38023-158">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Сведения об обнаруженном URL-адресе](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a><span data-ttu-id="38023-160">Отправка > электронной почты</span><span class="sxs-lookup"><span data-stu-id="38023-160">Email > Submissions</span></span>

<span data-ttu-id="38023-161">Чтобы просмотреть этот отчет, в проводнике (или обнаружения в режиме реального времени) выберите **Просмотр** \> отправленных **сообщений электронной почты** \> .</span><span class="sxs-lookup"><span data-stu-id="38023-161">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Submissions**.</span></span> <span data-ttu-id="38023-162">В этом представлении отображаются сообщения электронной почты о том, что пользователи сообщили о нежелательной почте, нежелательной почте или фишинге.</span><span class="sxs-lookup"><span data-stu-id="38023-162">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>

![Сообщения электронной почты, сообщаемые пользователями](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

<span data-ttu-id="38023-164">Нажмите кнопку **отправитель** , чтобы открыть список параметров просмотра.</span><span class="sxs-lookup"><span data-stu-id="38023-164">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="38023-165">Этот список используется для просмотра сведений по отправителям, получателям, типам отчетов (определение пользователя на нежелательное, не спаме или фишинге) и многое другое.</span><span class="sxs-lookup"><span data-stu-id="38023-165">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span>

<span data-ttu-id="38023-166">Например, чтобы просмотреть сведения о сообщениях электронной почты, которые были зарегистрированы как попытки фишинга, щелкните тип отчета по **отправителю** \> , выберите пункт **Фишинг**, а затем нажмите кнопку Обновить.</span><span class="sxs-lookup"><span data-stu-id="38023-166">For example, to view information about email messages that were reported as phishing attempts, click **Sender** \> **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![Фишинг, выбранный для фильтра типа отчета](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="38023-168">Под диаграммой просмотрите дополнительные сведения об определенных сообщениях электронной почты, таких как строка темы, IP-адрес отправителя, пользователь, который сообщил сообщение как нежелательное, нежелательное или фишинг, а также другие сведения.</span><span class="sxs-lookup"><span data-stu-id="38023-168">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span>

![Сообщения, которые были зарегистрированы как попытки фишинга](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="38023-170">Выберите элемент в списке, чтобы просмотреть дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="38023-170">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="38023-171">Электронная почта > всю почту</span><span class="sxs-lookup"><span data-stu-id="38023-171">Email > All email</span></span>

<span data-ttu-id="38023-172">Чтобы просмотреть этот отчет, в проводнике выберите **Просмотр** \> **электронной почты по электронной почте** \> .</span><span class="sxs-lookup"><span data-stu-id="38023-172">To view this report, in Explorer, choose **View** \> **Email** \> **All mail**.</span></span> <span data-ttu-id="38023-173">В этом представлении отображается представление действий с электронной почтой, в том числе сообщение электронной почты, которое определено как вредоносное по причине фишинга или вредоносных программ, а также для всех невредоносных сообщений (обычной электронной почты, спама и массовой почты).</span><span class="sxs-lookup"><span data-stu-id="38023-173">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span>

> [!NOTE]
> <span data-ttu-id="38023-174">Если вы получаете сообщение об ошибке, которое считывает **слишком много данных**, добавьте фильтр и при необходимости Сократите диапазон дат, который вы просматриваете.</span><span class="sxs-lookup"><span data-stu-id="38023-174">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span>

<span data-ttu-id="38023-175">Чтобы применить фильтр, выберите **отправитель**, выберите элемент в списке, а затем нажмите кнопку Обновить.</span><span class="sxs-lookup"><span data-stu-id="38023-175">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="38023-176">В нашем примере мы использовали **технологию обнаружения** в качестве фильтра (доступно несколько вариантов).</span><span class="sxs-lookup"><span data-stu-id="38023-176">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="38023-177">Просмотр сведений по отправителям, доменам отправителя, получателям, темам, вложениям filename, семействам вредоносных программ, состоянию защиты (действия, выполняемые функциями и политиками защиты от угроз в Office 365), технология обнаружения (способ обнаружения вредоносных программ) и многое другое.</span><span class="sxs-lookup"><span data-stu-id="38023-177">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span>

![Просмотр данных об обнаруженных сообщениях электронной почты с помощью технологии обнаружения](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

<span data-ttu-id="38023-179">Под диаграммой просмотрите дополнительные сведения об определенных сообщениях электронной почты, таких как строка темы, получатель, отправитель, состояние и т. д.</span><span class="sxs-lookup"><span data-stu-id="38023-179">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span>

## <a name="content--malware"></a><span data-ttu-id="38023-180">Контент > вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="38023-180">Content > Malware</span></span>

<span data-ttu-id="38023-181">Чтобы просмотреть этот отчет, в проводнике (или обнаружения в режиме реального времени) выберите **Просмотр** \>  \> **вредоносных программ**.</span><span class="sxs-lookup"><span data-stu-id="38023-181">To view this report, in Explorer (or real-time detections), choose **View** \> **Content** \> **Malware**.</span></span> <span data-ttu-id="38023-182">В этом представлении отображаются файлы, которые были определены как вредоносные [защитником Майкрософт для Office 365 в SharePoint Online, OneDrive для бизнеса и Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="38023-182">This view shows files that were identified as malicious by [Microsoft Defender for Office 365 in SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="38023-183">Просмотр сведений о семействе вредоносных программ, технологии обнаружения (способе обнаружения вредоносных программ) и рабочей нагрузке (OneDrive, SharePoint или Teams).</span><span class="sxs-lookup"><span data-stu-id="38023-183">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span>

![Просмотр данных об обнаруженных вредоносных программах](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

<span data-ttu-id="38023-185">Под диаграммой просмотрите дополнительные сведения о конкретных файлах, таких как имя файла вложения, Рабочая нагрузка, размер файла, Последнее изменение файла и т. д.</span><span class="sxs-lookup"><span data-stu-id="38023-185">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span>

## <a name="click-to-filter-capabilities"></a><span data-ttu-id="38023-186">Возможности "нажми и работай"</span><span class="sxs-lookup"><span data-stu-id="38023-186">Click-to-filter capabilities</span></span>

<span data-ttu-id="38023-187">С помощью проводника (и обнаружения в режиме реального времени) можно применить фильтр по щелчку.</span><span class="sxs-lookup"><span data-stu-id="38023-187">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="38023-188">Щелкните элемент в условных обозначениях, и этот элемент становится фильтром для отчета.</span><span class="sxs-lookup"><span data-stu-id="38023-188">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="38023-189">Например, предположим, что вы ищете представление вредоносных программ в проводнике:</span><span class="sxs-lookup"><span data-stu-id="38023-189">For example, suppose we are looking at the Malware view in Explorer:</span></span>

![Перейти к обозревателю управления угрозами \>](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="38023-191">Выбор **ATP детонации** в этой диаграмме приводит к представлению следующего вида:</span><span class="sxs-lookup"><span data-stu-id="38023-191">Clicking **ATP Detonation** in this chart results in a view like this:</span></span>

![Explorer фильтруется, чтобы отображать только защитник для Office 365 детонации результаты](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

<span data-ttu-id="38023-193">В этом представлении теперь мы рассмотрим данные для файлов, которые были обезвреженоы с помощью [безопасных вложений](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="38023-193">In this view, we are now looking at data for files that were detonated by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="38023-194">Под диаграммой можно просмотреть подробные сведения об определенных сообщениях электронной почты, для которых были обнаружены вложения, обнаруженные безопасными вложениями.</span><span class="sxs-lookup"><span data-stu-id="38023-194">Below the chart, we can see details about specific email messages that had attachments that were detected by Safe Attachments.</span></span>

![Конкретные сведения о сообщениях электронной почты с обнаруженными вложениями](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

<span data-ttu-id="38023-196">При выборе одного или нескольких элементов активируется меню **действия** , в котором предлагается несколько вариантов выбора для выбранных элементов.</span><span class="sxs-lookup"><span data-stu-id="38023-196">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span>

![Выбор элемента активирует меню "действия"](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

<span data-ttu-id="38023-198">Возможность фильтрации в нажатии и переходе к определенным сведениям может значительно сэкономить время при изучении угроз.</span><span class="sxs-lookup"><span data-stu-id="38023-198">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="38023-199">Запросы и фильтры</span><span class="sxs-lookup"><span data-stu-id="38023-199">Queries and filters</span></span>

<span data-ttu-id="38023-200">В проводнике (а также в отчете об обнаружении в реальном времени) есть несколько мощных фильтров и запросов, позволяющих переходить к детальным сведениям, таким как самые популярные целевые пользователи, основные семейства вредоносных программ, технологию обнаружения и многое другое.</span><span class="sxs-lookup"><span data-stu-id="38023-200">Explorer (as well as the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="38023-201">Каждый вид отчета предлагает различные способы просмотра и изучения данных.</span><span class="sxs-lookup"><span data-stu-id="38023-201">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="38023-202">Не используйте подстановочные знаки, такие как звездочка или вопросительный знак, на панели запросов проводника (или обнаружения в режиме реального времени).</span><span class="sxs-lookup"><span data-stu-id="38023-202">Do not use wildcard characters, such as an asterisk or a question mark, in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="38023-203">При поиске в **поле subject** для сообщений электронной почты проводник (или обнаружение в режиме реального времени) выполняет частичные совпадения и дают результаты, аналогичные условиям поиска по шаблону.</span><span class="sxs-lookup"><span data-stu-id="38023-203">When you search on the **Subject field** for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
