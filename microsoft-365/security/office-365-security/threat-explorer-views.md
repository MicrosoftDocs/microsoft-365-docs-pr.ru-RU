---
title: Представления в Обозревателе угроз и обнаружения в режиме реального времени
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
description: Узнайте, как использовать Обозреватель угроз и отчет о обнаружениях в режиме реального времени для расследования и реагирования на угрозы в Центре & соответствия требованиям.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b00b78432a34ec982208586f2fe19c1588354293
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406484"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="86be5-103">Представления в Обозревателе угроз и обнаружения в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="86be5-103">Views in Threat Explorer and real-time detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="86be5-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="86be5-104">**Applies to**</span></span>
- [<span data-ttu-id="86be5-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="86be5-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="86be5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="86be5-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


![Обозреватель угроз](../../media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="86be5-108">[Обозреватель](threat-explorer.md) угроз (и отчет об обнаружении в режиме реального времени) — это мощное средство в режиме реального времени, помогая группам по операциям безопасности исследовать и реагировать на угрозы в Центре & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="86be5-108">[Threat Explorer](threat-explorer.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security & Compliance Center.</span></span> <span data-ttu-id="86be5-109">Explorer (и отчет об обнаружении в режиме реального времени) отображает сведения о подозрительных вредоносных программах и фишинге в электронной почте и файлах в Office 365, а также о других угрозах и рисках для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="86be5-109">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span>

- <span data-ttu-id="86be5-110">Если у вас [есть Microsoft Defender для Office 365](office-365-atp.md) Plan 2, у вас есть Explorer.</span><span class="sxs-lookup"><span data-stu-id="86be5-110">If you have [Microsoft Defender for Office 365](office-365-atp.md) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="86be5-111">Если у вас есть Microsoft Defender для Office 365 Plan 1, у вас есть обнаружения в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="86be5-111">If you have Microsoft Defender for Office 365 Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="86be5-112">Когда вы впервые откроете Explorer (или отчет об обнаружении в режиме реального времени), в представлении по умолчанию показано обнаружение вредоносных программ по электронной почте в течение последних 7 дней.</span><span class="sxs-lookup"><span data-stu-id="86be5-112">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="86be5-113">В этом отчете также могут быть обнаружены обнаружения Microsoft Defender для Office [](atp-safe-links.md)365, такие как вредоносные URL-адреса, обнаруженные службами безопасных ссылок, и вредоносные файлы, обнаруженные в безопасных [вложениях.](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="86be5-113">This report can also show Microsoft Defender for Office 365 detections, such as malicious URLs detected by [Safe Links](atp-safe-links.md), and malicious files detected by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="86be5-114">Этот отчет можно изменить, чтобы показать данные за последние 30 дней (с платной подпиской Microsoft Defender для Office 365 P2).</span><span class="sxs-lookup"><span data-stu-id="86be5-114">This report can be modified to show data for the past 30 days (with a Microsoft Defender for Office 365 P2 paid subscription).</span></span> <span data-ttu-id="86be5-115">Пробные подписки будут включать данные только за последние семь дней.</span><span class="sxs-lookup"><span data-stu-id="86be5-115">Trial subscriptions will include data for the past seven days only.</span></span>

****

|<span data-ttu-id="86be5-116">Подписка</span><span class="sxs-lookup"><span data-stu-id="86be5-116">Subscription</span></span>|<span data-ttu-id="86be5-117">Служебная программа</span><span class="sxs-lookup"><span data-stu-id="86be5-117">Utility</span></span>|<span data-ttu-id="86be5-118">Дни данных</span><span class="sxs-lookup"><span data-stu-id="86be5-118">Days of Data</span></span>|
|---|---|---|
|<span data-ttu-id="86be5-119">Пробная версия Microsoft Defender для Office 365 P1</span><span class="sxs-lookup"><span data-stu-id="86be5-119">Microsoft Defender for Office 365 P1 trial</span></span>|<span data-ttu-id="86be5-120">Обнаружение в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="86be5-120">Real-time detections</span></span>|<span data-ttu-id="86be5-121">7 </span><span class="sxs-lookup"><span data-stu-id="86be5-121">7</span></span>|
|<span data-ttu-id="86be5-122">Microsoft Defender для Office 365 P1 платная</span><span class="sxs-lookup"><span data-stu-id="86be5-122">Microsoft Defender for Office 365 P1 paid</span></span>|<span data-ttu-id="86be5-123">Обнаружение в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="86be5-123">Real-time detections</span></span>|<span data-ttu-id="86be5-124">30</span><span class="sxs-lookup"><span data-stu-id="86be5-124">30</span></span>|
|<span data-ttu-id="86be5-125">Microsoft Defender для Office 365 P1 оплатил тестирование Defender для пробной пробной программы Office 365 P2</span><span class="sxs-lookup"><span data-stu-id="86be5-125">Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="86be5-126">Обозреватель угроз</span><span class="sxs-lookup"><span data-stu-id="86be5-126">Threat Explorer</span></span>|<span data-ttu-id="86be5-127">7 </span><span class="sxs-lookup"><span data-stu-id="86be5-127">7</span></span>|
|<span data-ttu-id="86be5-128">Пробная версия Microsoft Defender для Office 365 P2</span><span class="sxs-lookup"><span data-stu-id="86be5-128">Microsoft Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="86be5-129">Обозреватель угроз</span><span class="sxs-lookup"><span data-stu-id="86be5-129">Threat Explorer</span></span>|<span data-ttu-id="86be5-130">7 </span><span class="sxs-lookup"><span data-stu-id="86be5-130">7</span></span>|
|<span data-ttu-id="86be5-131">Microsoft Defender для Office 365 P2 платная</span><span class="sxs-lookup"><span data-stu-id="86be5-131">Microsoft Defender for Office 365 P2 paid</span></span>|<span data-ttu-id="86be5-132">Обозреватель угроз</span><span class="sxs-lookup"><span data-stu-id="86be5-132">Threat Explorer</span></span>|<span data-ttu-id="86be5-133">30</span><span class="sxs-lookup"><span data-stu-id="86be5-133">30</span></span>|
|

> [!NOTE]
> <span data-ttu-id="86be5-134">В ближайшее время мы расширяем ограничение хранения и поиска данных Explorer (и обнаружения в режиме реального времени) для пробных клиентов с 7 до 30 дней.</span><span class="sxs-lookup"><span data-stu-id="86be5-134">We will soon be extending the Explorer (and Real-time detections) data retention and search limit for trial tenants from 7 to 30 days.</span></span> <span data-ttu-id="86be5-135">Это изменение отслеживается в рамках элемента дорожной карты No 70544 и в настоящее время находится на этапе выкатки.</span><span class="sxs-lookup"><span data-stu-id="86be5-135">This change is being tracked as part of roadmap item no. 70544, and is currently in a roll-out phase.</span></span>

<span data-ttu-id="86be5-136">Чтобы изменить отображаемую информацию, используйте меню **Просмотр.**</span><span class="sxs-lookup"><span data-stu-id="86be5-136">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="86be5-137">Инструменты помогают определить, какой вид использовать.</span><span class="sxs-lookup"><span data-stu-id="86be5-137">Tooltips help you determine which view to use.</span></span>

![Меню Просмотра обозревателя угроз](../../media/ThreatExplorerViewMenu.png)

<span data-ttu-id="86be5-139">После выбора представления можно применить фильтры и настроить запросы для дальнейшего анализа.</span><span class="sxs-lookup"><span data-stu-id="86be5-139">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="86be5-140">В следующих разделах представлен краткий обзор различных представлений, доступных в Explorer (или обнаружения в режиме реального времени).</span><span class="sxs-lookup"><span data-stu-id="86be5-140">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>

## <a name="email--malware"></a><span data-ttu-id="86be5-141">Вредоносные программы > электронной почты</span><span class="sxs-lookup"><span data-stu-id="86be5-141">Email > Malware</span></span>

<span data-ttu-id="86be5-142">Чтобы просмотреть этот отчет, в Explorer (или обнаружения в режиме реального времени) выберите **Просмотр вредоносных** программ \> **электронной** \> **почты**.</span><span class="sxs-lookup"><span data-stu-id="86be5-142">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Malware**.</span></span> <span data-ttu-id="86be5-143">В этом представлении показаны сведения о сообщениях электронной почты, которые были определены как содержащие вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="86be5-143">This view shows information about email messages that were identified as containing malware.</span></span>

![Просмотр данных об электронной почте, идентифицированной как вредоносная программа](../../media/ExplorerEmailMalwareMenu.png)

<span data-ttu-id="86be5-145">Щелкните **Отправитель,** чтобы открыть список параметров просмотра.</span><span class="sxs-lookup"><span data-stu-id="86be5-145">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="86be5-146">Используйте этот список для просмотра данных отправительством, получателями, доменом отправитель, предметом, технологией обнаружения, состоянием защиты и более.</span><span class="sxs-lookup"><span data-stu-id="86be5-146">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span>

<span data-ttu-id="86be5-147">Например, чтобы узнать, какие действия были приняты при обнаружении сообщений электронной почты, выберите **состояние защиты** в списке.</span><span class="sxs-lookup"><span data-stu-id="86be5-147">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="86be5-148">Выберите параметр, а затем нажмите кнопку Обновить, чтобы применить этот фильтр к отчету.</span><span class="sxs-lookup"><span data-stu-id="86be5-148">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![Параметры состояния защиты от угроз для обозревателя угроз](../../media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="86be5-150">Ниже диаграммы см. дополнительные сведения о конкретных сообщениях.</span><span class="sxs-lookup"><span data-stu-id="86be5-150">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="86be5-151">При выборе элемента в списке открывается поле для вылетов, где можно узнать больше о выбранном элементе.</span><span class="sxs-lookup"><span data-stu-id="86be5-151">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Обозреватель угроз с открываемой вылетной](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="86be5-153">Фишинг > электронной почты</span><span class="sxs-lookup"><span data-stu-id="86be5-153">Email > Phish</span></span>

<span data-ttu-id="86be5-154">Чтобы просмотреть этот отчет, в Explorer (или обнаружения в режиме реального времени) выберите **Просмотр** \> **фишинга** \> **электронной почты**.</span><span class="sxs-lookup"><span data-stu-id="86be5-154">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Phish**.</span></span> <span data-ttu-id="86be5-155">В этом представлении показаны сообщения электронной почты, идентифицированные как попытки фишинга.</span><span class="sxs-lookup"><span data-stu-id="86be5-155">This view shows email messages identified as phishing attempts.</span></span>

![Просмотр данных о электронной почте, идентифицированной как попытки фишинга](../../media/ThreatExplorerEmailPhish.png)

<span data-ttu-id="86be5-157">Щелкните **Отправитель,** чтобы открыть список параметров просмотра.</span><span class="sxs-lookup"><span data-stu-id="86be5-157">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="86be5-158">Используйте этот список для просмотра данных отправив, получателей, домена отправитель, IP-адрес отправитель, URL-адрес, щелкните вердикт и другие.</span><span class="sxs-lookup"><span data-stu-id="86be5-158">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span>

<span data-ttu-id="86be5-159">Например, чтобы узнать, какие действия были предприняты при нажатии на  URL-адреса, которые были идентифицированы как попытки фишинга, выберите нажмите кнопку Нажмите кнопку Вердикт в списке, выберите один или несколько параметров, а затем нажмите кнопку Обновить.</span><span class="sxs-lookup"><span data-stu-id="86be5-159">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![Щелкните параметры вердикта для отчета Phish](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="86be5-161">Ниже диаграммы см. дополнительные сведения о конкретных сообщениях, url-адресах, URL-адресах и происхождении электронной почты.</span><span class="sxs-lookup"><span data-stu-id="86be5-161">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span>

![URL-адреса, обнаруженные как фишинг в сообщениях электронной почты](../../media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="86be5-163">При выборе элемента в списке, например обнаруженного URL-адреса, открывается флайер, где можно узнать больше о выбранном элементе.</span><span class="sxs-lookup"><span data-stu-id="86be5-163">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Сведения об обнаружении URL-адреса](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a><span data-ttu-id="86be5-165">Отправка > электронной почты</span><span class="sxs-lookup"><span data-stu-id="86be5-165">Email > Submissions</span></span>

<span data-ttu-id="86be5-166">Чтобы просмотреть этот отчет, в Explorer (или обнаружения в режиме реального времени) выберите **Просмотр** \>  \> **отправки электронной почты**.</span><span class="sxs-lookup"><span data-stu-id="86be5-166">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Submissions**.</span></span> <span data-ttu-id="86be5-167">В этом представлении показано сообщение электронной почты, которое пользователи сообщали как нежелательное, а не нежелательное или фишинговое.</span><span class="sxs-lookup"><span data-stu-id="86be5-167">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>

![Сообщения электронной почты, отчитались пользователи](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

<span data-ttu-id="86be5-169">Щелкните **Отправитель,** чтобы открыть список параметров просмотра.</span><span class="sxs-lookup"><span data-stu-id="86be5-169">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="86be5-170">Используйте этот список для просмотра сведений отправив, получателей, типа отчетов (определение пользователя о том, что электронная почта является нежелательной, а не нежелательной или фишинговой) и другие.</span><span class="sxs-lookup"><span data-stu-id="86be5-170">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span>

<span data-ttu-id="86be5-171">Например, чтобы просмотреть сведения о сообщениях электронной почты, которые сообщались как попытки фишинга, щелкните тип **отчетов** отправитель, выберите Фишинг, а затем нажмите \> кнопку Обновить.</span><span class="sxs-lookup"><span data-stu-id="86be5-171">For example, to view information about email messages that were reported as phishing attempts, click **Sender** \> **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![Фишинг, выбранный для фильтра типа отчетов](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="86be5-173">Ниже диаграммы см. дополнительные сведения о конкретных сообщениях электронной почты, таких как строка темы, IP-адрес отправитель, пользователь, который сообщил сообщение как нежелательное, а не нежелательное или фишинговое, и другие.</span><span class="sxs-lookup"><span data-stu-id="86be5-173">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span>

![Сообщения, которые сообщались как попытки фишинга](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="86be5-175">Выберите элемент в списке, чтобы просмотреть дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="86be5-175">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="86be5-176">Электронная > Вся электронная почта</span><span class="sxs-lookup"><span data-stu-id="86be5-176">Email > All email</span></span>

<span data-ttu-id="86be5-177">Чтобы просмотреть этот отчет, в Проводнике выберите **Просмотр** \>  \> **электронной почты вся почта**.</span><span class="sxs-lookup"><span data-stu-id="86be5-177">To view this report, in Explorer, choose **View** \> **Email** \> **All mail**.</span></span> <span data-ttu-id="86be5-178">В этих представлениях показано представление об активности электронной почты, включая сообщения электронной почты, идентифицированные как вредоносные из-за фишинга или вредоносных программ, а также все не вредоносные сообщения (обычная электронная почта, спам и массовая почта).</span><span class="sxs-lookup"><span data-stu-id="86be5-178">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span>

> [!NOTE]
> <span data-ttu-id="86be5-179">Если вы получаете ошибку, которая читает слишком много данных для **отображения,** добавьте фильтр и, при необходимости, сузить диапазон дат, который вы просматриваете.</span><span class="sxs-lookup"><span data-stu-id="86be5-179">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span>

<span data-ttu-id="86be5-180">Чтобы применить фильтр, выберите **отправитель,** выберите элемент в списке и нажмите кнопку Обновить.</span><span class="sxs-lookup"><span data-stu-id="86be5-180">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="86be5-181">В нашем примере в качестве фильтра используется технология **Detection** (доступно несколько вариантов).</span><span class="sxs-lookup"><span data-stu-id="86be5-181">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="86be5-182">Просмотр сведений по отправителю, домену отправитель, получателям, субъекту, имени файла вложения, семейство вредоносных программ, состояние защиты (действия, предпринятые функциями и политиками защиты от угроз в Office 365), технологии обнаружения (как было обнаружено вредоносное ПО) и другие.</span><span class="sxs-lookup"><span data-stu-id="86be5-182">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span>

![Просмотр данных об обнаруженной электронной почте с помощью технологии обнаружения](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

<span data-ttu-id="86be5-184">Ниже диаграммы см. дополнительные сведения о конкретных сообщениях электронной почты, таких как строка темы, получатель, отправитель, состояние и так далее.</span><span class="sxs-lookup"><span data-stu-id="86be5-184">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span>

## <a name="content--malware"></a><span data-ttu-id="86be5-185">Вредоносные программы > контента</span><span class="sxs-lookup"><span data-stu-id="86be5-185">Content > Malware</span></span>

<span data-ttu-id="86be5-186">Чтобы просмотреть этот отчет, в Explorer (или обнаружения в режиме реального времени) выберите **Просмотр** \> **вредоносных программ** \> **содержимого**.</span><span class="sxs-lookup"><span data-stu-id="86be5-186">To view this report, in Explorer (or real-time detections), choose **View** \> **Content** \> **Malware**.</span></span> <span data-ttu-id="86be5-187">В этом представлении показаны файлы, которые были идентифицированы microsoft [Defender для Office 365 в SharePoint Online, OneDrive для](atp-for-spo-odb-and-teams.md)бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="86be5-187">This view shows files that were identified as malicious by [Microsoft Defender for Office 365 in SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="86be5-188">Просмотр сведений семейства вредоносных программ, технологии обнаружения (как было обнаружено вредоносное ПО) и рабочей нагрузки (OneDrive, SharePoint или Teams).</span><span class="sxs-lookup"><span data-stu-id="86be5-188">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span>

![Просмотр данных об обнаружении вредоносных программ](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

<span data-ttu-id="86be5-190">Ниже диаграммы см. дополнительные сведения о конкретных файлах, таких как имя файла вложения, рабочая нагрузка, размер файла, которые в последний раз изменили файл и другие.</span><span class="sxs-lookup"><span data-stu-id="86be5-190">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span>

## <a name="click-to-filter-capabilities"></a><span data-ttu-id="86be5-191">Возможности "Щелкнуть на фильтр"</span><span class="sxs-lookup"><span data-stu-id="86be5-191">Click-to-filter capabilities</span></span>

<span data-ttu-id="86be5-192">С помощью Explorer (и обнаружения в режиме реального времени) можно применить фильтр одним щелчком мыши.</span><span class="sxs-lookup"><span data-stu-id="86be5-192">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="86be5-193">Щелкните элемент в легенде, и этот элемент станет фильтром для отчета.</span><span class="sxs-lookup"><span data-stu-id="86be5-193">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="86be5-194">Например, предположим, что мы рассматриваем представление вредоносных программ в Explorer:</span><span class="sxs-lookup"><span data-stu-id="86be5-194">For example, suppose we are looking at the Malware view in Explorer:</span></span>

![Перейдите к обозревателю управления \> угрозами](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="86be5-196">**Щелкнув atP Detonation** на этой диаграмме, вы можете увидеть это:</span><span class="sxs-lookup"><span data-stu-id="86be5-196">Clicking **ATP Detonation** in this chart results in a view like this:</span></span>

![Explorer отфильтрован для отображения результатов детонации Defender для Office 365](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

<span data-ttu-id="86be5-198">В этом представлении мы сейчас рассматриваем данные для файлов, которые были взорваны с помощью [безопасных вложений.](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="86be5-198">In this view, we are now looking at data for files that were detonated by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="86be5-199">Ниже диаграммы приведены сведения о конкретных сообщениях электронной почты, которые были обнаружены вложениями, обнаруженными в безопасных вложениях.</span><span class="sxs-lookup"><span data-stu-id="86be5-199">Below the chart, we can see details about specific email messages that had attachments that were detected by Safe Attachments.</span></span>

![Конкретные сведения о сообщениях электронной почты с обнаруженными вложениями](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

<span data-ttu-id="86be5-201">Выбор одного или нескольких элементов активирует меню **Действия,** которое предлагает несколько вариантов выбора для выбранного элемента(ы).</span><span class="sxs-lookup"><span data-stu-id="86be5-201">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span>

![Выбор элемента активирует меню Действия](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

<span data-ttu-id="86be5-203">Возможность фильтрации в щелчке мыши и переход к конкретным деталям может сэкономить много времени при расследовании угроз.</span><span class="sxs-lookup"><span data-stu-id="86be5-203">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="86be5-204">Запросы и фильтры</span><span class="sxs-lookup"><span data-stu-id="86be5-204">Queries and filters</span></span>

<span data-ttu-id="86be5-205">Explorer (а также отчет о обнаружениях в режиме реального времени) имеет несколько мощных фильтров и возможностей запроса, которые позволяют подробно и подробно и подробно, например, топовых пользователей, семейства вредоносных программ, технологию обнаружения и другие.</span><span class="sxs-lookup"><span data-stu-id="86be5-205">Explorer (as well as the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="86be5-206">Каждый вид отчета предлагает различные способы просмотра и изучения данных.</span><span class="sxs-lookup"><span data-stu-id="86be5-206">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="86be5-207">Не используйте символы подтекста, такие как звездочка или знак вопроса, в панели запросов для Explorer (или обнаружения в режиме реального времени).</span><span class="sxs-lookup"><span data-stu-id="86be5-207">Do not use wildcard characters, such as an asterisk or a question mark, in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="86be5-208">При поиске в поле **Subject** сообщений электронной почты Explorer (или обнаружения в режиме реального времени) выполнит частичное соответствие и результаты, аналогичные поиску подтекстов.</span><span class="sxs-lookup"><span data-stu-id="86be5-208">When you search on the **Subject field** for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
