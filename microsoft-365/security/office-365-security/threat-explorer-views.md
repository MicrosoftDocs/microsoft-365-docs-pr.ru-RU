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
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Узнайте, как использовать обозреватель угроз и отчет об обнаружении угроз в режиме реального времени для изучения угроз и реагирования на них в Центре безопасности & соответствия требованиям.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: aef3f7fe69e5cbd1d70b7aee3284f0c5dc6416df
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290289"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="9cdc3-103">Представления в обозревателе угроз и обнаружения в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="9cdc3-103">Views in Threat Explorer and real-time detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9cdc3-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="9cdc3-104">**Applies to**</span></span>
- [<span data-ttu-id="9cdc3-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="9cdc3-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="9cdc3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9cdc3-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


![Обозреватель угроз](../../media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="9cdc3-108">[Обозреватель угроз](threat-explorer.md) (и отчет об обнаружении в режиме реального времени) — это мощное практически в реальном времени средство, помогая группам по операциям безопасности исследовать угрозы и реагировать на них в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-108">[Threat Explorer](threat-explorer.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security & Compliance Center.</span></span> <span data-ttu-id="9cdc3-109">Проводник (и отчет об обнаружении в режиме реального времени) отображает сведения о подозрительных вредоносных программах и фишинге в электронной почте и файлах в Office 365, а также о других угрозах безопасности и рисках для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-109">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span>

- <span data-ttu-id="9cdc3-110">Если у вас есть [Microsoft Defender для Office 365](office-365-atp.md) (план 2), то у вас есть проводник.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-110">If you have [Microsoft Defender for Office 365](office-365-atp.md) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="9cdc3-111">Если у вас есть Microsoft Defender для Office 365 (план 1), у вас есть обнаружение в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-111">If you have Microsoft Defender for Office 365 Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="9cdc3-112">Когда вы впервые открываете проводник (или отчет об обнаружении в режиме реального времени), в представлении по умолчанию показано обнаружение вредоносных программ электронной почты за последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-112">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="9cdc3-113">В этом отчете также могут быть обнаружены вредоносные URL-адреса, обнаруженные службой "Безопасные ссылки", и вредоносные файлы, обнаруженные службой "Безопасные [](atp-safe-links.md)вложения". [](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="9cdc3-113">This report can also show Microsoft Defender for Office 365 detections, such as malicious URLs detected by [Safe Links](atp-safe-links.md), and malicious files detected by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="9cdc3-114">Этот отчет можно изменить, чтобы показать данные за последние 30 дней (с платной подпиской Microsoft Defender для Office 365 P2).</span><span class="sxs-lookup"><span data-stu-id="9cdc3-114">This report can be modified to show data for the past 30 days (with a Microsoft Defender for Office 365 P2 paid subscription).</span></span> <span data-ttu-id="9cdc3-115">Пробные подписки будут включать данные только за последние семь дней.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-115">Trial subscriptions will include data for the past seven days only.</span></span>

****

|<span data-ttu-id="9cdc3-116">Подписка</span><span class="sxs-lookup"><span data-stu-id="9cdc3-116">Subscription</span></span>|<span data-ttu-id="9cdc3-117">Служебная программа</span><span class="sxs-lookup"><span data-stu-id="9cdc3-117">Utility</span></span>|<span data-ttu-id="9cdc3-118">Дни данных</span><span class="sxs-lookup"><span data-stu-id="9cdc3-118">Days of Data</span></span>|
|---|---|---|
|<span data-ttu-id="9cdc3-119">Пробная версия Microsoft Defender для Office 365 P1</span><span class="sxs-lookup"><span data-stu-id="9cdc3-119">Microsoft Defender for Office 365 P1 trial</span></span>|<span data-ttu-id="9cdc3-120">Обнаружение в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="9cdc3-120">Real-time detections</span></span>|<span data-ttu-id="9cdc3-121">7 </span><span class="sxs-lookup"><span data-stu-id="9cdc3-121">7</span></span>|
|<span data-ttu-id="9cdc3-122">Платный Microsoft Defender для Office 365 P1</span><span class="sxs-lookup"><span data-stu-id="9cdc3-122">Microsoft Defender for Office 365 P1 paid</span></span>|<span data-ttu-id="9cdc3-123">Обнаружение в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="9cdc3-123">Real-time detections</span></span>|<span data-ttu-id="9cdc3-124">30</span><span class="sxs-lookup"><span data-stu-id="9cdc3-124">30</span></span>|
|<span data-ttu-id="9cdc3-125">Платный тест "Защитник Microsoft Defender для Office 365 P1" для пробной программы Office 365 P2</span><span class="sxs-lookup"><span data-stu-id="9cdc3-125">Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="9cdc3-126">Обозреватель угроз</span><span class="sxs-lookup"><span data-stu-id="9cdc3-126">Threat Explorer</span></span>|<span data-ttu-id="9cdc3-127">7 </span><span class="sxs-lookup"><span data-stu-id="9cdc3-127">7</span></span>|
|<span data-ttu-id="9cdc3-128">Пробная версия Microsoft Defender для Office 365 P2</span><span class="sxs-lookup"><span data-stu-id="9cdc3-128">Microsoft Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="9cdc3-129">Обозреватель угроз</span><span class="sxs-lookup"><span data-stu-id="9cdc3-129">Threat Explorer</span></span>|<span data-ttu-id="9cdc3-130">7 </span><span class="sxs-lookup"><span data-stu-id="9cdc3-130">7</span></span>|
|<span data-ttu-id="9cdc3-131">Платный Microsoft Defender для Office 365 P2</span><span class="sxs-lookup"><span data-stu-id="9cdc3-131">Microsoft Defender for Office 365 P2 paid</span></span>|<span data-ttu-id="9cdc3-132">Обозреватель угроз</span><span class="sxs-lookup"><span data-stu-id="9cdc3-132">Threat Explorer</span></span>|<span data-ttu-id="9cdc3-133">30</span><span class="sxs-lookup"><span data-stu-id="9cdc3-133">30</span></span>|
|

<span data-ttu-id="9cdc3-134">Используйте меню **"Вид",** чтобы изменить отображаемую информацию.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-134">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="9cdc3-135">С помощью tooltips можно определить, какое представление использовать.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-135">Tooltips help you determine which view to use.</span></span>

![Меню "Просмотр обозревателя угроз"](../../media/ThreatExplorerViewMenu.png)

<span data-ttu-id="9cdc3-137">Выбрав представление, можно применить фильтры и настроить запросы для дальнейшего анализа.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-137">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="9cdc3-138">В следующих разделах представлен краткий обзор различных представлений, доступных в проводнике (или обнаружения в режиме реального времени).</span><span class="sxs-lookup"><span data-stu-id="9cdc3-138">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>

## <a name="email--malware"></a><span data-ttu-id="9cdc3-139">Вредоносные > электронной почты</span><span class="sxs-lookup"><span data-stu-id="9cdc3-139">Email > Malware</span></span>

<span data-ttu-id="9cdc3-140">Чтобы просмотреть этот отчет, в проводнике (или при обнаружении в режиме реального времени) выберите **"Просмотр вредоносных** программ \>  \> **электронной почты".**</span><span class="sxs-lookup"><span data-stu-id="9cdc3-140">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Malware**.</span></span> <span data-ttu-id="9cdc3-141">В этом представлении показаны сведения о сообщениях электронной почты, которые были определены как содержащие вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-141">This view shows information about email messages that were identified as containing malware.</span></span>

![Просмотр данных о сообщениях электронной почты, которые определены как вредоносные программы](../../media/ExplorerEmailMalwareMenu.png)

<span data-ttu-id="9cdc3-143">Щелкните **"Отправитель",** чтобы открыть список параметров просмотра.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-143">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="9cdc3-144">Используйте этот список для просмотра данных по отправителю, получателям, домену отправитель, теме, технологии обнаружения, статусу защиты и многому другое.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-144">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span>

<span data-ttu-id="9cdc3-145">Например, чтобы узнать, какие действия были предприняты с обнаруженными сообщениями электронной почты, выберите состояние **защиты** в списке.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-145">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="9cdc3-146">Выберите параметр и нажмите кнопку "Обновить", чтобы применить этот фильтр к отчету.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-146">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![Параметры состояния защиты от угроз для обозревателя угроз](../../media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="9cdc3-148">Под диаграммой см. дополнительные сведения об определенных сообщениях.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-148">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="9cdc3-149">При выборе элемента в списке откроется окно, в котором вы сможете узнать больше об выбранном элементе.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-149">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Обозреватель угроз с открытым flyout](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="9cdc3-151">Фишинг > электронной почты</span><span class="sxs-lookup"><span data-stu-id="9cdc3-151">Email > Phish</span></span>

<span data-ttu-id="9cdc3-152">Чтобы просмотреть этот отчет, в проводнике (или при обнаружении в режиме реального времени) выберите **"Просмотр** \> **фишинга** \> **электронной почты".**</span><span class="sxs-lookup"><span data-stu-id="9cdc3-152">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Phish**.</span></span> <span data-ttu-id="9cdc3-153">В этом представлении показаны сообщения электронной почты, которые считаются фишинговыми.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-153">This view shows email messages identified as phishing attempts.</span></span>

![Просмотр данных о сообщениях электронной почты, которые определены как попытки фишинга](../../media/ThreatExplorerEmailPhish.png)

<span data-ttu-id="9cdc3-155">Щелкните **"Отправитель",** чтобы открыть список параметров просмотра.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-155">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="9cdc3-156">Используйте этот список для просмотра данных по отправителю, получателям, домену отправитель, IP-адресу отправляемого адреса, домену URL-адреса, по нажатию решения и других данных.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-156">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span>

<span data-ttu-id="9cdc3-157">Например, чтобы узнать, какие действия были предприняты, когда люди щелкнули  URL-адреса, которые были определены как фишинговые, выберите в списке "Заключение нажми и выбирай", выберите один или несколько параметров, а затем нажмите кнопку "Обновить".</span><span class="sxs-lookup"><span data-stu-id="9cdc3-157">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![Варианты решения по выбору для отчета о фишинге](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="9cdc3-159">Под диаграммой можно просмотреть дополнительные сведения об определенных сообщениях, щелчках URL-адресов, URL-адресах и источниках электронной почты.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-159">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span>

![URL-адреса, обнаруженные как фишинговые в сообщениях электронной почты](../../media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="9cdc3-161">При выборе элемента в списке, например обнаруженного URL-адреса, откроется окно, где вы сможете узнать больше об выбранном элементе.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-161">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Сведения об обнаружении URL-адреса](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a><span data-ttu-id="9cdc3-163">Отправки > электронной почты</span><span class="sxs-lookup"><span data-stu-id="9cdc3-163">Email > Submissions</span></span>

<span data-ttu-id="9cdc3-164">Чтобы просмотреть этот отчет, в проводнике (или при обнаружении в режиме реального времени) выберите **"Просмотр** \> **от** \> **отправленных сообщений электронной почты".**</span><span class="sxs-lookup"><span data-stu-id="9cdc3-164">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Submissions**.</span></span> <span data-ttu-id="9cdc3-165">В этом представлении показана электронная почта, о которую пользователи сообщили как о нежелательной, а не о нежелательной или фишинговой.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-165">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>

![Сообщения электронной почты, отправленные пользователями](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

<span data-ttu-id="9cdc3-167">Щелкните **"Отправитель",** чтобы открыть список параметров просмотра.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-167">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="9cdc3-168">Используйте этот список для просмотра сведений по отправителю, получателям, типу отчета (определение пользователя о том, что сообщение нежелательное, а не нежелательное или фишинговое) и другие сведения.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-168">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span>

<span data-ttu-id="9cdc3-169">Например, чтобы просмотреть сведения о сообщениях электронной почты, которые считаются фишинговыми, щелкните "Тип отчета отправитель", выберите "Фишинг" и нажмите кнопку  \> "Обновить". </span><span class="sxs-lookup"><span data-stu-id="9cdc3-169">For example, to view information about email messages that were reported as phishing attempts, click **Sender** \> **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![Фишинг, выбранный для фильтра типов отчетов](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="9cdc3-171">Под диаграммой можно просмотреть дополнительные сведения об определенных сообщениях электронной почты, таких как строка темы, IP-адрес отправитель, пользователь, который сообщил о сообщении как нежелательное, а не как нежелательное или фишинговое и другие.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-171">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span>

![Сообщения, которые были засчитано как попытки фишинга](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="9cdc3-173">Выберите элемент в списке, чтобы просмотреть дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-173">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="9cdc3-174">Электронная > все сообщения электронной почты</span><span class="sxs-lookup"><span data-stu-id="9cdc3-174">Email > All email</span></span>

<span data-ttu-id="9cdc3-175">Чтобы просмотреть этот отчет, в проводнике выберите **"Просмотреть почту** \>  \> **вся почта".**</span><span class="sxs-lookup"><span data-stu-id="9cdc3-175">To view this report, in Explorer, choose **View** \> **Email** \> **All mail**.</span></span> <span data-ttu-id="9cdc3-176">В этом представлении показано все виды действий с электронной почтой, включая сообщения, которые считаются вредоносными из-за фишинга или вредоносных программ, а также все не вредоносные сообщения (обычная почта, нежелаическая почта и массовая рассылка).</span><span class="sxs-lookup"><span data-stu-id="9cdc3-176">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span>

> [!NOTE]
> <span data-ttu-id="9cdc3-177">Если вы получаете ошибку, которая читает слишком много данных для **отображения,** добавьте фильтр и при необходимости сужайте диапазон дат, который вы просматриваете.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-177">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span>

<span data-ttu-id="9cdc3-178">Чтобы применить фильтр, выберите **"Отправитель",** выберите элемент в списке и нажмите кнопку "Обновить".</span><span class="sxs-lookup"><span data-stu-id="9cdc3-178">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="9cdc3-179">В нашем примере мы использовали **технологию обнаружения** в качестве фильтра (доступно несколько вариантов).</span><span class="sxs-lookup"><span data-stu-id="9cdc3-179">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="9cdc3-180">Просмотр сведений по отправителю, домену отправитель, получателям, теме, имени файла вложения, семейство вредоносных программ, состояние защиты (действия, предпринятые функциями и политиками защиты от угроз в Office 365), технологию обнаружения (как было обнаружено вредоносное ПО) и другие сведения.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-180">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span>

![Просмотр данных об обнаруженной электронной почте с помощью технологии обнаружения](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

<span data-ttu-id="9cdc3-182">Под диаграммой можно просмотреть дополнительные сведения об определенных сообщениях электронной почты, таких как строка темы, получатель, отправитель, состояние и так далее.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-182">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span>

## <a name="content--malware"></a><span data-ttu-id="9cdc3-183">Вредоносные > контента</span><span class="sxs-lookup"><span data-stu-id="9cdc3-183">Content > Malware</span></span>

<span data-ttu-id="9cdc3-184">Чтобы просмотреть этот отчет, в проводнике (или при обнаружении в режиме реального времени) выберите **"Просмотр** \> **вредоносных программ для** \> **содержимого".**</span><span class="sxs-lookup"><span data-stu-id="9cdc3-184">To view this report, in Explorer (or real-time detections), choose **View** \> **Content** \> **Malware**.</span></span> <span data-ttu-id="9cdc3-185">В этом представлении показаны файлы, которые были определены Как вредоносные с помощью [Microsoft Defender для Office 365 в SharePoint Online, OneDrive для](atp-for-spo-odb-and-teams.md)бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-185">This view shows files that were identified as malicious by [Microsoft Defender for Office 365 in SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="9cdc3-186">Просмотр информации по семейство вредоносных программ, технологии обнаружения (как было обнаружено вредоносное ПО) и рабочей нагрузке (OneDrive, SharePoint или Teams).</span><span class="sxs-lookup"><span data-stu-id="9cdc3-186">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span>

![Просмотр данных об обнаруженной вредоносной программе](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

<span data-ttu-id="9cdc3-188">Под диаграммой можно просмотреть дополнительные сведения об определенных файлах, таких как имя файла вложения, рабочая нагрузка, размер файла, кто последним изменил файл и другие.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-188">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span>

## <a name="click-to-filter-capabilities"></a><span data-ttu-id="9cdc3-189">Возможности "нажми и фильтрация"</span><span class="sxs-lookup"><span data-stu-id="9cdc3-189">Click-to-filter capabilities</span></span>

<span data-ttu-id="9cdc3-190">С помощью проводника (и обнаружения в режиме реального времени) можно применить фильтр одним щелчком мыши.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-190">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="9cdc3-191">Щелкните элемент в легенде, и он станет фильтром для отчета.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-191">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="9cdc3-192">Например, предположим, что мы просматриваем представление "Вредоносные программы" в проводнике:</span><span class="sxs-lookup"><span data-stu-id="9cdc3-192">For example, suppose we are looking at the Malware view in Explorer:</span></span>

![Перейти в обозреватель управления \> угрозами](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="9cdc3-194">**Нажатие кнопки "Детонация ATP"** на этой диаграмме приводит к следующему представлению:</span><span class="sxs-lookup"><span data-stu-id="9cdc3-194">Clicking **ATP Detonation** in this chart results in a view like this:</span></span>

![Отфильтрованный проводник для отображения результатов детонации в Защитнике Office 365](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

<span data-ttu-id="9cdc3-196">В этом представлении теперь мы просматриваем данные для файлов, которые были детонировали с помощью [безопасных вложений.](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="9cdc3-196">In this view, we are now looking at data for files that were detonated by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="9cdc3-197">Под диаграммой можно увидеть подробные сведения об определенных сообщениях электронной почты с вложениями, обнаруженными функцией "Безопасные вложения".</span><span class="sxs-lookup"><span data-stu-id="9cdc3-197">Below the chart, we can see details about specific email messages that had attachments that were detected by Safe Attachments.</span></span>

![Конкретные сведения о сообщениях электронной почты с обнаруженными вложениями](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

<span data-ttu-id="9cdc3-199">Выбор одного или нескольких элементов активирует меню "Действия", которое предлагает несколько вариантов выбора выбранных элементов. </span><span class="sxs-lookup"><span data-stu-id="9cdc3-199">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span>

![Выбор элемента активирует меню "Действия"](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

<span data-ttu-id="9cdc3-201">Возможность фильтрации по щелчку и переход к определенным сведениям может сэкономить много времени при расследовании угроз.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-201">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="9cdc3-202">Запросы и фильтры</span><span class="sxs-lookup"><span data-stu-id="9cdc3-202">Queries and filters</span></span>

<span data-ttu-id="9cdc3-203">В проводнике (а также в отчете об обнаружении вредоносных программ в режиме реального времени) есть несколько мощных фильтров и функций запроса, позволяющих подробно иное, например, наиболее целевые пользователи, семейства вредоносных программ, технология обнаружения и другие.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-203">Explorer (as well as the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="9cdc3-204">Каждый вид отчета предлагает различные способы просмотра и изучения данных.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-204">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9cdc3-205">Не используйте подкалярные знаки, например звездочки или вопросители, на панели запросов для проводника (или обнаружения в режиме реального времени).</span><span class="sxs-lookup"><span data-stu-id="9cdc3-205">Do not use wildcard characters, such as an asterisk or a question mark, in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="9cdc3-206">При поиске  сообщений электронной почты в поле "Тема" проводник (или обнаружение в режиме реального времени) выполнит частичное совпадение и даст результаты, аналогичные поиску с подкалярами.</span><span class="sxs-lookup"><span data-stu-id="9cdc3-206">When you search on the **Subject field** for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
