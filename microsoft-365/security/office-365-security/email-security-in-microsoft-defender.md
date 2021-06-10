---
title: Безопасность электронной почты с помощью обозревателя угроз в Microsoft Defender для Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Просмотр и расследование попыток фишинга вредоносных программ.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0326a51f14b402b9a579e8668ef2c026f9de789
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2021
ms.locfileid: "52877900"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a><span data-ttu-id="f11dc-103">Безопасность электронной почты с помощью обозревателя угроз в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="f11dc-103">Email security with Threat Explorer in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="f11dc-104">В этой статье</span><span class="sxs-lookup"><span data-stu-id="f11dc-104">In this article:</span></span>

- [<span data-ttu-id="f11dc-105">Просмотр вредоносных программ, обнаруженных в электронной почте</span><span class="sxs-lookup"><span data-stu-id="f11dc-105">View malware detected in email</span></span>](#view-malware-detected-in-email)
- [<span data-ttu-id="f11dc-106">Просмотр фишинговых URL-адресов и щелкните данные вердикта</span><span class="sxs-lookup"><span data-stu-id="f11dc-106">View phishing URL and click verdict data</span></span>](#view-phishing-url-and-click-verdict-data)
- [<span data-ttu-id="f11dc-107">Запуск автоматического расследования и ответа</span><span class="sxs-lookup"><span data-stu-id="f11dc-107">Start automated investigation and response</span></span>](#start-automated-investigation-and-response)

> [!NOTE]
> <span data-ttu-id="f11dc-108">Это часть трехсерийной серии по обозревателю угроз **(Explorer),** безопасности электронной почты **и** основам обнаружения explorer и в режиме реального времени **(например,** различия между инструментами и разрешениями, необходимыми для их работы). </span><span class="sxs-lookup"><span data-stu-id="f11dc-108">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="f11dc-109">Другие две статьи этой серии : "Поиск угроз" в ["Обозревателе](threat-hunting-in-threat-explorer.md) угроз" и "Обозреватель угроз" и "Обнаружение в режиме [реального времени".](real-time-detections.md)</span><span class="sxs-lookup"><span data-stu-id="f11dc-109">The other two articles in this series are [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span> 

<span data-ttu-id="f11dc-110">В этой статье рассказывается, как просматривать вредоносные программы и попытки фишинга, обнаруженные в электронной почте Microsoft 365 функциями безопасности.</span><span class="sxs-lookup"><span data-stu-id="f11dc-110">This article explains how to view and investigate malware and phishing attempts that are detected in email by Microsoft 365 security features.</span></span> 

<span data-ttu-id="f11dc-111">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="f11dc-111">**Applies to**</span></span>

- [<span data-ttu-id="f11dc-112">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="f11dc-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f11dc-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f11dc-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

## <a name="view-malware-detected-in-email"></a><span data-ttu-id="f11dc-114">Просмотр вредоносных программ, обнаруженных в электронной почте</span><span class="sxs-lookup"><span data-stu-id="f11dc-114">View malware detected in email</span></span>

<span data-ttu-id="f11dc-115">Чтобы увидеть вредоносные программы, обнаруженные в электронной [](threat-explorer-views.md#email--malware) почте, отсортировали Microsoft 365 технологию, используйте представление > вредоносных программ Explorer (или обнаружения в режиме реального времени).</span><span class="sxs-lookup"><span data-stu-id="f11dc-115">To see malware detected in email sorted by Microsoft 365 technology, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span> <span data-ttu-id="f11dc-116">Вредоносные программы — это представление по умолчанию, поэтому его можно выбрать, как только откроете Explorer.</span><span class="sxs-lookup"><span data-stu-id="f11dc-116">Malware is the default view, so it may be selected as soon as you open Explorer.</span></span>

1. <span data-ttu-id="f11dc-117">В Центре & безопасности выберите Обозреватель управления угрозами (или обнаружение в <https://protection.office.com>  \>  **режиме реального времени).**</span><span class="sxs-lookup"><span data-stu-id="f11dc-117">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="f11dc-118">(В этом примере используется Explorer.)</span><span class="sxs-lookup"><span data-stu-id="f11dc-118">(This example uses Explorer.)</span></span>

   <span data-ttu-id="f11dc-119">Если вы на конвергентной Microsoft 365 Defender ( ) прокрутите до обозревателя <https://security.microsoft.com> **&**  >  **совместной работы.**</span><span class="sxs-lookup"><span data-stu-id="f11dc-119">If you're in the converged Microsoft 365 Defender portal (<https://security.microsoft.com>) scroll to **Email & collaboration** > **Explorer**.</span></span>

   <span data-ttu-id="f11dc-120">Отсюда, начните с представления, выберите определенный период времени для исследования (если это необходимо) и сосредоточьте фильтры, как по погонам [Обозревателя.](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through)</span><span class="sxs-lookup"><span data-stu-id="f11dc-120">From here, start at the View, choose a particular frame of time to investigate (if needed), and focus your filters, as per the [Explorer walk- through](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through).</span></span>

2. <span data-ttu-id="f11dc-121">В меню **Просмотр** выберите вредоносные **программы электронной** \> **почты**.</span><span class="sxs-lookup"><span data-stu-id="f11dc-121">In the **View** menu, choose **Email** \> **Malware**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f11dc-122">![Просмотр меню для Обозревателя](../../media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="f11dc-122">![View menu for Explorer](../../media/ExplorerViewEmailMalwareMenu.png)</span></span>

3. <span data-ttu-id="f11dc-123">Щелкните **отправитель,** а затем выберите **технологию Basic** \> **Detection.**</span><span class="sxs-lookup"><span data-stu-id="f11dc-123">Click **Sender**, and then choose **Basic** \> **Detection technology**.</span></span>

   <span data-ttu-id="f11dc-124">Теперь технологии обнаружения доступны в качестве фильтров для отчета.</span><span class="sxs-lookup"><span data-stu-id="f11dc-124">Your detection technologies are now available as filters for the report.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f11dc-125">![Технологии обнаружения вредоносных программ](../../media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="f11dc-125">![Malware detection technologies](../../media/ExplorerEmailMalwareDetectionTech.png)</span></span>

4. <span data-ttu-id="f11dc-126">Выберите параметр.</span><span class="sxs-lookup"><span data-stu-id="f11dc-126">Choose an option.</span></span> <span data-ttu-id="f11dc-127">Затем выберите **кнопку Обновить,** чтобы применить этот фильтр.</span><span class="sxs-lookup"><span data-stu-id="f11dc-127">Then select the **Refresh** button to apply that filter.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f11dc-128">![Выбранная технология обнаружения](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="f11dc-128">![Selected detection technology](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span></span>

   <span data-ttu-id="f11dc-129">Отчет обновляется, чтобы показать результаты, обнаруженные вредоносными программами в электронной почте с помощью выбранного вами параметра технологии.</span><span class="sxs-lookup"><span data-stu-id="f11dc-129">The report refreshes to show the results that malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="f11dc-130">Далее можно провести дополнительный анализ.</span><span class="sxs-lookup"><span data-stu-id="f11dc-130">From here, you can conduct further analysis.</span></span> 

## <a name="view-phishing-url-and-click-verdict-data"></a><span data-ttu-id="f11dc-131">Просмотр фишинговых URL-адресов и щелкните данные вердикта</span><span class="sxs-lookup"><span data-stu-id="f11dc-131">View phishing URL and click verdict data</span></span>

<span data-ttu-id="f11dc-132">Вы можете просматривать попытки фишинга с помощью URL-адресов в электронной почте, включая список URL-адресов, которые были разрешены, заблокированы и переопределены.</span><span class="sxs-lookup"><span data-stu-id="f11dc-132">You can view phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="f11dc-133">Чтобы определить url-адреса, которые были нажаты, [необходимо настроить Сейф ссылки.](safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="f11dc-133">To identify URLs that were clicked, [Safe Links](safe-links.md) must be configured.</span></span> <span data-ttu-id="f11dc-134">Убедитесь, что Сейф [ссылки](set-up-safe-links-policies.md) для защиты и ведения журнала по ссылкам при Сейф ссылки.</span><span class="sxs-lookup"><span data-stu-id="f11dc-134">Make sure that you set up [Safe Links policies](set-up-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

<span data-ttu-id="f11dc-135">Чтобы просмотреть URL-адреса фишинга в сообщениях и нажать [   >   ](threat-explorer-views.md#email--phish) на URL-адреса в фишинговых сообщениях, используйте представление фишинга электронной почты Explorer или обнаружения в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="f11dc-135">To review phish URLs in messages and clicks on URLs in phish messages, use the [**Email** > **Phish**](threat-explorer-views.md#email--phish) view of Explorer or Real-time detections.</span></span>

1. <span data-ttu-id="f11dc-136">В Центре & безопасности выберите Обозреватель управления угрозами (или обнаружение в <https://protection.office.com>  \>  **режиме реального времени).**</span><span class="sxs-lookup"><span data-stu-id="f11dc-136">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="f11dc-137">(В этом примере используется Explorer.)</span><span class="sxs-lookup"><span data-stu-id="f11dc-137">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="f11dc-138">В меню **Просмотр** выберите фишинг **электронной** \> **почты**.</span><span class="sxs-lookup"><span data-stu-id="f11dc-138">In the **View** menu, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f11dc-139">![Просмотр меню обозревателя в контексте фишинга](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="f11dc-139">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="f11dc-140">Щелкните **отправитель,** а затем выберите **URL-адреса** \> **нажмите кнопку вердикт**.</span><span class="sxs-lookup"><span data-stu-id="f11dc-140">Click **Sender**, and then choose **URLs** \> **Click verdict**.</span></span>

4. <span data-ttu-id="f11dc-141">Выберите один или несколько  параметров, таких как Заблокировано и **Блок** переопределено, а затем выберите кнопку **Обновление** на той же строке, что и параметры для применения этого фильтра.</span><span class="sxs-lookup"><span data-stu-id="f11dc-141">Select one or more options, such as **Blocked** and **Block overridden**, and then select the **Refresh** button on the same line as the options to apply that filter.</span></span> <span data-ttu-id="f11dc-142">(Не обновляйте окно браузера.)</span><span class="sxs-lookup"><span data-stu-id="f11dc-142">(Don't refresh your browser window.)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f11dc-143">![URL-адреса и щелкните вердикты](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="f11dc-143">![URLs and click verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span>

   <span data-ttu-id="f11dc-144">Отчет обновляется, чтобы показать две разные таблицы URL-адресов на вкладке URL-адреса в отчете:</span><span class="sxs-lookup"><span data-stu-id="f11dc-144">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="f11dc-145">**Верхние URL-адреса** — это URL-адреса в сообщениях, которые отфильтровываются, и для каждого URL-адреса учитываются действия доставки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f11dc-145">**Top URLs** are the URLs in the messages that you filtered down to and the email delivery action counts for each URL.</span></span> <span data-ttu-id="f11dc-146">В представлении электронной почты Фишинг этот список обычно содержит законные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="f11dc-146">In the Phish email view, this list typically contains legitimate URLs.</span></span> <span data-ttu-id="f11dc-147">Злоумышленники включают сочетание хороших и плохих URL-адресов в сообщениях, чтобы попытаться доставить их, но они делают вредоносные ссылки более интересными.</span><span class="sxs-lookup"><span data-stu-id="f11dc-147">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they make the malicious links look more interesting.</span></span> <span data-ttu-id="f11dc-148">Таблица URL-адресов сортируется по общему счету электронной почты, но этот столбец скрыт для упрощения представления.</span><span class="sxs-lookup"><span data-stu-id="f11dc-148">The table of URLs is sorted by total email count, but this column is hidden to simplify the view.</span></span>

   - <span data-ttu-id="f11dc-149">**Верхние щелчки** — Сейф url-адреса, на которые были нажаты ссылки, отсортировали по общему счету щелчка.</span><span class="sxs-lookup"><span data-stu-id="f11dc-149">**Top clicks** are the Safe Links-wrapped URLs that were clicked, sorted by total click count.</span></span> <span data-ttu-id="f11dc-150">Этот столбец также не отображается, чтобы упростить представление.</span><span class="sxs-lookup"><span data-stu-id="f11dc-150">This column also isn't displayed, to simplify the view.</span></span> <span data-ttu-id="f11dc-151">Общие числа по столбцу указывают, Сейф ссылки нажмите количество приговора для каждого нажав URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="f11dc-151">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="f11dc-152">В представлении электронной почты Фишинг это обычно подозрительные или вредоносные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="f11dc-152">In the Phish email view, these are usually suspicious or malicious URLs.</span></span> <span data-ttu-id="f11dc-153">Но представление может включать URL-адреса, которые не являются угрозами, но находятся в фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="f11dc-153">But the view could include URLs that aren't threats but are in phish messages.</span></span> <span data-ttu-id="f11dc-154">URL-адреса, нажав на незаверстатьные ссылки, здесь не указаны.</span><span class="sxs-lookup"><span data-stu-id="f11dc-154">URL clicks on unwrapped links don't show up here.</span></span>

   <span data-ttu-id="f11dc-155">В двух таблицах URL-адресов указаны лучшие URL-адреса в фишинговых сообщениях электронной почты по действию доставки и расположению.</span><span class="sxs-lookup"><span data-stu-id="f11dc-155">The two URL tables show top URLs in phishing email messages by delivery action and location.</span></span> <span data-ttu-id="f11dc-156">В таблицах указаны url-адреса, которые были заблокированы или посещаемы, несмотря на предупреждение, поэтому вы можете увидеть, какие потенциальные плохие ссылки были представлены пользователям и какие пользователи нажали.</span><span class="sxs-lookup"><span data-stu-id="f11dc-156">The tables show URL clicks that were blocked or visited despite a warning, so you can see what potential bad links were presented to users and that the users clicked.</span></span> <span data-ttu-id="f11dc-157">Далее можно провести дополнительный анализ.</span><span class="sxs-lookup"><span data-stu-id="f11dc-157">From here, you can conduct further analysis.</span></span> <span data-ttu-id="f11dc-158">Например, ниже диаграммы можно увидеть верхние URL-адреса в сообщениях электронной почты, заблокированных в среде организации.</span><span class="sxs-lookup"><span data-stu-id="f11dc-158">For example, below the chart you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f11dc-159">![URL-адреса explorer, заблокированные](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="f11dc-159">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="f11dc-160">Выберите URL-адрес, чтобы просмотреть более подробные сведения.</span><span class="sxs-lookup"><span data-stu-id="f11dc-160">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f11dc-161">В диалоговом окне флажок URL-адреса фильтрация сообщений электронной почты удаляется, чтобы показать полное представление экспозиции URL-адреса в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="f11dc-161">In the URL flyout dialog box, the filtering on email messages is removed to show the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="f11dc-162">Это позволяет фильтровать сообщения электронной почты, которые вас беспокоят в Explorer, находить конкретные URL-адреса, которые являются потенциальными угрозами, а затем расширять представление об экспозиции URL-адресов в среде (через диалоговое окно сведений URL-адреса), не добавляя url-адреса в представление обозревателя.</span><span class="sxs-lookup"><span data-stu-id="f11dc-162">This lets you filter for email messages you're concerned about in Explorer, find specific URLs that are potential threats, and then expand your understanding of the URL exposure in your environment (via the URL details dialog box) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-click-verdicts"></a><span data-ttu-id="f11dc-163">Интерпретация вердиктов нажмите кнопку</span><span class="sxs-lookup"><span data-stu-id="f11dc-163">Interpretation of click verdicts</span></span>

<span data-ttu-id="f11dc-164">В вылетах электронной почты или URL-адресов, нажатии верхнего щелчка мыши и в наших впечатлениях от фильтрации вы увидите различные значения вердикта.</span><span class="sxs-lookup"><span data-stu-id="f11dc-164">In the Email or URL flyouts, Top Clicks, and in our filtering experiences, you'll see different click verdict values:</span></span>

- <span data-ttu-id="f11dc-165">**Нет:** Невозможно зафиксировать вердикт для URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="f11dc-165">**None:** Unable to capture the verdict for the URL.</span></span> <span data-ttu-id="f11dc-166">Пользователь мог щелкнуть URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="f11dc-166">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="f11dc-167">**Разрешено:** Пользователю было разрешено перемещаться по URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="f11dc-167">**Allowed:** The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="f11dc-168">**Заблокировано:** Пользователю было заблокировано перемещение по URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="f11dc-168">**Blocked:** The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="f11dc-169">**Ожидая вердикта:** Пользователю была представлена страница, ожидаемая детонации.</span><span class="sxs-lookup"><span data-stu-id="f11dc-169">**Pending verdict:** The user was presented with the detonation-pending page.</span></span>
- <span data-ttu-id="f11dc-170">**Заблокировано переопределено:** Пользователю было заблокировано перемещение непосредственно по URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="f11dc-170">**Blocked overridden:** The user was blocked from navigating directly to the URL.</span></span> <span data-ttu-id="f11dc-171">Но пользователь перегородит блок, чтобы перейти к URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="f11dc-171">But the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="f11dc-172">**В ожидании вердикта обойти:** Пользователю была представлена страница детонации.</span><span class="sxs-lookup"><span data-stu-id="f11dc-172">**Pending verdict bypassed:** The user was presented with the detonation page.</span></span> <span data-ttu-id="f11dc-173">Но пользователь перегородит сообщение, чтобы получить доступ к URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="f11dc-173">But the user overrode the message to access the URL.</span></span>
- <span data-ttu-id="f11dc-174">**Ошибка:** Пользователю была представлена страница ошибки или произошла ошибка при захвате вердикта.</span><span class="sxs-lookup"><span data-stu-id="f11dc-174">**Error:** The user was presented with the error page, or an error occurred in capturing the verdict.</span></span>
- <span data-ttu-id="f11dc-175">**Сбой:** При записи приговора произошло неизвестное исключение.</span><span class="sxs-lookup"><span data-stu-id="f11dc-175">**Failure:** An unknown exception occurred while capturing the verdict.</span></span> <span data-ttu-id="f11dc-176">Пользователь мог щелкнуть URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="f11dc-176">The user might have clicked through the URL.</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="f11dc-177">Запуск автоматического расследования и ответа</span><span class="sxs-lookup"><span data-stu-id="f11dc-177">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="f11dc-178">Возможности автоматического расследования и ответа доступны в Microsoft Defender для Office 365 *2* и *Office 365 E5.*</span><span class="sxs-lookup"><span data-stu-id="f11dc-178">Automated investigation and response capabilities are available in *Microsoft Defender for Office 365 Plan 2* and *Office 365 E5*.</span></span>

<span data-ttu-id="f11dc-179">[Автоматическое расследование и реагирование](automated-investigation-response-office.md) могут сэкономить время и усилия группы операций безопасности, затраченные на расследование и смягчение кибератак.</span><span class="sxs-lookup"><span data-stu-id="f11dc-179">[Automated investigation and response](automated-investigation-response-office.md) can save your security operations team time and effort spent investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="f11dc-180">Помимо настройки оповещений, которые могут вызвать книгу безопасности, можно запустить автоматизированный процесс расследования и ответа из представления в Explorer.</span><span class="sxs-lookup"><span data-stu-id="f11dc-180">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> <span data-ttu-id="f11dc-181">Дополнительные сведения [см. в примере. Администратор безопасности запускает расследование из Explorer.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)</span><span class="sxs-lookup"><span data-stu-id="f11dc-181">For details, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="other-articles"></a><span data-ttu-id="f11dc-182">Другие статьи</span><span class="sxs-lookup"><span data-stu-id="f11dc-182">Other articles</span></span>

[<span data-ttu-id="f11dc-183">Изучение сообщений электронной почты на странице Сущности электронной почты</span><span class="sxs-lookup"><span data-stu-id="f11dc-183">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)
