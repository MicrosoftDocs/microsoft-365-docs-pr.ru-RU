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
ms.openlocfilehash: eb62961bb26b079c508cbd5bc559a95d172cff86
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029889"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a><span data-ttu-id="39ae0-103">Безопасность электронной почты с помощью обозревателя угроз в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="39ae0-103">Email security with Threat Explorer in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="39ae0-104">В этой статье</span><span class="sxs-lookup"><span data-stu-id="39ae0-104">In this article:</span></span>

- [<span data-ttu-id="39ae0-105">Просмотр вредоносных программ, обнаруженных в электронной почте</span><span class="sxs-lookup"><span data-stu-id="39ae0-105">View malware detected in email</span></span>](#view-malware-detected-in-email)
- [<span data-ttu-id="39ae0-106">Просмотр фишинговых URL-адресов и щелкните данные вердикта</span><span class="sxs-lookup"><span data-stu-id="39ae0-106">View phishing URL and click verdict data</span></span>](#view-phishing-url-and-click-verdict-data)
- [<span data-ttu-id="39ae0-107">Запуск автоматического расследования и ответа</span><span class="sxs-lookup"><span data-stu-id="39ae0-107">Start automated investigation and response</span></span>](#start-automated-investigation-and-response)

> [!NOTE]
> <span data-ttu-id="39ae0-108">Это часть трехсерийной серии по обозревателю угроз **(Explorer),** безопасности электронной почты **и** основам обнаружения explorer и в режиме реального времени **(например,** различия между инструментами и разрешениями, необходимыми для их работы). </span><span class="sxs-lookup"><span data-stu-id="39ae0-108">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="39ae0-109">Другие две статьи этой серии : "Поиск угроз" в ["Обозревателе](threat-hunting-in-threat-explorer.md) угроз" и "Обозреватель угроз" и "Обнаружение в режиме [реального времени".](real-time-detections.md)</span><span class="sxs-lookup"><span data-stu-id="39ae0-109">The other two articles in this series are [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span>

<span data-ttu-id="39ae0-110">В этой статье рассказывается, как просматривать вредоносные программы и попытки фишинга, обнаруженные в электронной почте Microsoft 365 функциями безопасности.</span><span class="sxs-lookup"><span data-stu-id="39ae0-110">This article explains how to view and investigate malware and phishing attempts that are detected in email by Microsoft 365 security features.</span></span>

<span data-ttu-id="39ae0-111">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="39ae0-111">**Applies to:**</span></span>

- [<span data-ttu-id="39ae0-112">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="39ae0-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="39ae0-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="39ae0-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

## <a name="view-malware-detected-in-email"></a><span data-ttu-id="39ae0-114">Просмотр вредоносных программ, обнаруженных в электронной почте</span><span class="sxs-lookup"><span data-stu-id="39ae0-114">View malware detected in email</span></span>

<span data-ttu-id="39ae0-115">Чтобы увидеть вредоносные программы, обнаруженные в электронной [](threat-explorer-views.md#email--malware) почте, отсортировали Microsoft 365 технологию, используйте представление > вредоносных программ Explorer (или обнаружения в режиме реального времени).</span><span class="sxs-lookup"><span data-stu-id="39ae0-115">To see malware detected in email sorted by Microsoft 365 technology, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span> <span data-ttu-id="39ae0-116">Вредоносные программы — это представление по умолчанию, поэтому оно может быть выбрано, как только вы откроете Explorer.</span><span class="sxs-lookup"><span data-stu-id="39ae0-116">Malware is the default view, so it might be selected as soon as you open Explorer.</span></span>

1. <span data-ttu-id="39ae0-117">На портале Microsoft 365 Defender () выберите обозреватель & электронной почты (или обнаружения в режиме <https://security.microsoft.com>  \>  **реального времени;** В этом примере используется Explorer).</span><span class="sxs-lookup"><span data-stu-id="39ae0-117">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), choose **Email & collaboration** \> **Explorer** (or **Real-time detections**; This example uses Explorer).</span></span>

   <span data-ttu-id="39ae0-118">Отсюда, начните с представления, выберите определенный период времени для исследования (если это необходимо) и сосредоточьте фильтры, как по погонам [Обозревателя.](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through)</span><span class="sxs-lookup"><span data-stu-id="39ae0-118">From here, start at the View, choose a particular frame of time to investigate (if needed), and focus your filters, as per the [Explorer walk- through](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through).</span></span>

2. <span data-ttu-id="39ae0-119">В **списке drop** down View убедитесь, что **выбрано вредоносное** по \>  электронной почте.</span><span class="sxs-lookup"><span data-stu-id="39ae0-119">In the **View** drop down list, verify that **Email** \> **Malware** is selected.</span></span>

3. <span data-ttu-id="39ae0-120">Щелкните **отправитель,** а затем выберите **технологию Basic** \> **Detection** в списке drop down.</span><span class="sxs-lookup"><span data-stu-id="39ae0-120">Click **Sender**, and then choose **Basic** \> **Detection technology** in the drop down list.</span></span>

   :::image type="content" source="../../media/exploreremailmalwaredetectiontech-newimg.png" alt-text="технология обнаружения вредоносных программ":::

   <span data-ttu-id="39ae0-122">Теперь технологии обнаружения доступны в качестве фильтров для отчета.</span><span class="sxs-lookup"><span data-stu-id="39ae0-122">Your detection technologies are now available as filters for the report.</span></span>

4. <span data-ttu-id="39ae0-123">Выберите параметр, а затем нажмите **кнопку Обновить,** чтобы применить этот фильтр (не обновляйте окно браузера).</span><span class="sxs-lookup"><span data-stu-id="39ae0-123">Choose an option, and then click **Refresh** to apply that filter (don't refresh your browser window).</span></span>

   :::image type="content" source="../../media/exploreremailmalwaredetectiontech2-new.png" alt-text="выбранная технология обнаружения":::

   <span data-ttu-id="39ae0-125">Отчет обновляется, чтобы показать результаты, обнаруженные вредоносными программами в электронной почте с помощью выбранного вами параметра технологии.</span><span class="sxs-lookup"><span data-stu-id="39ae0-125">The report refreshes to show the results that malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="39ae0-126">Далее можно провести дополнительный анализ.</span><span class="sxs-lookup"><span data-stu-id="39ae0-126">From here, you can conduct further analysis.</span></span>

## <a name="view-phishing-url-and-click-verdict-data"></a><span data-ttu-id="39ae0-127">Просмотр фишинговых URL-адресов и щелкните данные вердикта</span><span class="sxs-lookup"><span data-stu-id="39ae0-127">View phishing URL and click verdict data</span></span>

<span data-ttu-id="39ae0-128">Вы можете просматривать попытки фишинга с помощью URL-адресов в электронной почте, включая список URL-адресов, которые были разрешены, заблокированы и переопределены.</span><span class="sxs-lookup"><span data-stu-id="39ae0-128">You can view phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="39ae0-129">Чтобы определить url-адреса, которые были нажаты, [необходимо настроить Сейф ссылки.](safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="39ae0-129">To identify URLs that were clicked, [Safe Links](safe-links.md) must be configured.</span></span> <span data-ttu-id="39ae0-130">Убедитесь, что Сейф [ссылки](set-up-safe-links-policies.md) для защиты и ведения журнала по ссылкам при Сейф ссылки.</span><span class="sxs-lookup"><span data-stu-id="39ae0-130">Make sure that you set up [Safe Links policies](set-up-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

1. <span data-ttu-id="39ae0-131">На портале Microsoft 365 Defender () выберите обозреватель & электронной почты (или обнаружения в режиме <https://security.microsoft.com>  \>  **реального времени;** В этом примере используется Explorer).</span><span class="sxs-lookup"><span data-stu-id="39ae0-131">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), choose **Email & collaboration** \> **Explorer** (or **Real-time detections**; This example uses Explorer).</span></span>

2. <span data-ttu-id="39ae0-132">В **выпадаемом** списке Просмотр выберите **фишинг** \> **электронной почты**.</span><span class="sxs-lookup"><span data-stu-id="39ae0-132">In the **View** drop down list, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="39ae0-133">![Просмотр меню обозревателя в контексте фишинга](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="39ae0-133">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="39ae0-134">Щелкните **Отправитель** и выберите **URL-адреса** \> **в** списке drop down.</span><span class="sxs-lookup"><span data-stu-id="39ae0-134">Click **Sender**, and then choose **URLs** \> **Click verdict** in the drop down list.</span></span>

4. <span data-ttu-id="39ae0-135">В появившимся вариантах выберите один  или несколько параметров, например заблокированные и переопределяемые блоки, а затем нажмите кнопку **Обновить** (не обновляйте окно браузера).</span><span class="sxs-lookup"><span data-stu-id="39ae0-135">In options that appear, select one or more options, such as **Blocked** and **Block overridden**, and then click **Refresh** (don't refresh your browser window).</span></span>

    :::image type="content" source="../../media/threatexploreremailphishclickverdict-new.png" alt-text="URL-адреса и щелкните вердикты":::

   <span data-ttu-id="39ae0-137">Отчет обновляется, чтобы показать две разные таблицы URL-адресов на вкладке **URL-адресов** в отчете:</span><span class="sxs-lookup"><span data-stu-id="39ae0-137">The report refreshes to show two different URL tables on the **URLs** tab under the report:</span></span>

   - <span data-ttu-id="39ae0-138">**Верхние URL-адреса** — это URL-адреса в сообщениях, которые отфильтровываются, и для каждого URL-адреса учитываются действия доставки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="39ae0-138">**Top URLs** are the URLs in the messages that you filtered down to and the email delivery action counts for each URL.</span></span> <span data-ttu-id="39ae0-139">В представлении электронной почты Фишинг этот список обычно содержит законные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="39ae0-139">In the Phish email view, this list typically contains legitimate URLs.</span></span> <span data-ttu-id="39ae0-140">Злоумышленники включают сочетание хороших и плохих URL-адресов в сообщениях, чтобы попытаться доставить их, но они делают вредоносные ссылки более интересными.</span><span class="sxs-lookup"><span data-stu-id="39ae0-140">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they make the malicious links look more interesting.</span></span> <span data-ttu-id="39ae0-141">Таблица URL-адресов сортируется по общему счету электронной почты, но этот столбец скрыт для упрощения представления.</span><span class="sxs-lookup"><span data-stu-id="39ae0-141">The table of URLs is sorted by total email count, but this column is hidden to simplify the view.</span></span>

   - <span data-ttu-id="39ae0-142">**Верхние щелчки** — Сейф url-адреса, на которые были нажаты ссылки, отсортировали по общему счету щелчка.</span><span class="sxs-lookup"><span data-stu-id="39ae0-142">**Top clicks** are the Safe Links-wrapped URLs that were clicked, sorted by total click count.</span></span> <span data-ttu-id="39ae0-143">Этот столбец также не отображается, чтобы упростить представление.</span><span class="sxs-lookup"><span data-stu-id="39ae0-143">This column also isn't displayed, to simplify the view.</span></span> <span data-ttu-id="39ae0-144">Общие числа по столбцу указывают, Сейф ссылки нажмите количество приговора для каждого нажав URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="39ae0-144">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="39ae0-145">В представлении электронной почты Фишинг это обычно подозрительные или вредоносные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="39ae0-145">In the Phish email view, these are usually suspicious or malicious URLs.</span></span> <span data-ttu-id="39ae0-146">Но представление может включать URL-адреса, которые не являются угрозами, но находятся в фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="39ae0-146">But the view could include URLs that aren't threats but are in phish messages.</span></span> <span data-ttu-id="39ae0-147">URL-адреса, нажав на незаверстатьные ссылки, здесь не указаны.</span><span class="sxs-lookup"><span data-stu-id="39ae0-147">URL clicks on unwrapped links don't show up here.</span></span>

   <span data-ttu-id="39ae0-148">В двух таблицах URL-адресов указаны лучшие URL-адреса в фишинговых сообщениях электронной почты по действию доставки и расположению.</span><span class="sxs-lookup"><span data-stu-id="39ae0-148">The two URL tables show top URLs in phishing email messages by delivery action and location.</span></span> <span data-ttu-id="39ae0-149">В таблицах указаны url-адреса, которые были заблокированы или посещаемы, несмотря на предупреждение, поэтому вы можете увидеть, какие потенциальные плохие ссылки были представлены пользователям и какие пользователи нажали.</span><span class="sxs-lookup"><span data-stu-id="39ae0-149">The tables show URL clicks that were blocked or visited despite a warning, so you can see what potential bad links were presented to users and that the users clicked.</span></span> <span data-ttu-id="39ae0-150">Далее можно провести дополнительный анализ.</span><span class="sxs-lookup"><span data-stu-id="39ae0-150">From here, you can conduct further analysis.</span></span> <span data-ttu-id="39ae0-151">Например, ниже диаграммы можно увидеть верхние URL-адреса в сообщениях электронной почты, заблокированных в среде организации.</span><span class="sxs-lookup"><span data-stu-id="39ae0-151">For example, below the chart you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="39ae0-152">![URL-адреса explorer, заблокированные](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="39ae0-152">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="39ae0-153">Выберите URL-адрес, чтобы просмотреть более подробные сведения.</span><span class="sxs-lookup"><span data-stu-id="39ae0-153">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="39ae0-154">В диалоговом окне флажок URL-адреса фильтрация сообщений электронной почты удаляется, чтобы показать полное представление экспозиции URL-адреса в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="39ae0-154">In the URL flyout dialog box, the filtering on email messages is removed to show the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="39ae0-155">Это позволяет фильтровать сообщения электронной почты, которые вас беспокоят в Explorer, находить конкретные URL-адреса, которые являются потенциальными угрозами, а затем расширять представление об экспозиции URL-адресов в среде (через диалоговое окно сведений URL-адреса), не добавляя url-адреса в представление обозревателя.</span><span class="sxs-lookup"><span data-stu-id="39ae0-155">This lets you filter for email messages you're concerned about in Explorer, find specific URLs that are potential threats, and then expand your understanding of the URL exposure in your environment (via the URL details dialog box) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-click-verdicts"></a><span data-ttu-id="39ae0-156">Интерпретация вердиктов нажмите кнопку</span><span class="sxs-lookup"><span data-stu-id="39ae0-156">Interpretation of click verdicts</span></span>

<span data-ttu-id="39ae0-157">В вылетах электронной почты или URL-адресов, нажатии верхнего щелчка мыши и в наших впечатлениях от фильтрации вы увидите различные значения вердикта.</span><span class="sxs-lookup"><span data-stu-id="39ae0-157">In the Email or URL flyouts, Top Clicks, and in our filtering experiences, you'll see different click verdict values:</span></span>

- <span data-ttu-id="39ae0-158">**Нет:** Невозможно зафиксировать вердикт для URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="39ae0-158">**None:** Unable to capture the verdict for the URL.</span></span> <span data-ttu-id="39ae0-159">Пользователь мог щелкнуть URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="39ae0-159">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="39ae0-160">**Разрешено:** Пользователю было разрешено перемещаться по URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="39ae0-160">**Allowed:** The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="39ae0-161">**Заблокировано:** Пользователю было заблокировано перемещение по URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="39ae0-161">**Blocked:** The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="39ae0-162">**Ожидая вердикта:** Пользователю была представлена страница, ожидаемая детонации.</span><span class="sxs-lookup"><span data-stu-id="39ae0-162">**Pending verdict:** The user was presented with the detonation-pending page.</span></span>
- <span data-ttu-id="39ae0-163">**Заблокировано переопределено:** Пользователю было заблокировано перемещение непосредственно по URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="39ae0-163">**Blocked overridden:** The user was blocked from navigating directly to the URL.</span></span> <span data-ttu-id="39ae0-164">Но пользователь перегородит блок, чтобы перейти к URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="39ae0-164">But the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="39ae0-165">**В ожидании вердикта обойти:** Пользователю была представлена страница детонации.</span><span class="sxs-lookup"><span data-stu-id="39ae0-165">**Pending verdict bypassed:** The user was presented with the detonation page.</span></span> <span data-ttu-id="39ae0-166">Но пользователь перегородит сообщение, чтобы получить доступ к URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="39ae0-166">But the user overrode the message to access the URL.</span></span>
- <span data-ttu-id="39ae0-167">**Ошибка:** Пользователю была представлена страница ошибки или произошла ошибка при захвате вердикта.</span><span class="sxs-lookup"><span data-stu-id="39ae0-167">**Error:** The user was presented with the error page, or an error occurred in capturing the verdict.</span></span>
- <span data-ttu-id="39ae0-168">**Сбой:** При записи приговора произошло неизвестное исключение.</span><span class="sxs-lookup"><span data-stu-id="39ae0-168">**Failure:** An unknown exception occurred while capturing the verdict.</span></span> <span data-ttu-id="39ae0-169">Пользователь мог щелкнуть URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="39ae0-169">The user might have clicked through the URL.</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="39ae0-170">Запуск автоматического расследования и ответа</span><span class="sxs-lookup"><span data-stu-id="39ae0-170">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="39ae0-171">Возможности автоматического расследования и ответа доступны в Microsoft Defender для Office 365 *2* и *Office 365 E5.*</span><span class="sxs-lookup"><span data-stu-id="39ae0-171">Automated investigation and response capabilities are available in *Microsoft Defender for Office 365 Plan 2* and *Office 365 E5*.</span></span>

<span data-ttu-id="39ae0-172">[Автоматическое расследование и реагирование](automated-investigation-response-office.md) могут сэкономить время и усилия группы операций безопасности, затраченные на расследование и смягчение кибератак.</span><span class="sxs-lookup"><span data-stu-id="39ae0-172">[Automated investigation and response](automated-investigation-response-office.md) can save your security operations team time and effort spent investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="39ae0-173">Помимо настройки оповещений, которые могут вызвать книгу безопасности, можно запустить автоматизированный процесс расследования и ответа из представления в Explorer.</span><span class="sxs-lookup"><span data-stu-id="39ae0-173">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> <span data-ttu-id="39ae0-174">Дополнительные сведения [см. в примере. Администратор безопасности запускает расследование из Explorer.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)</span><span class="sxs-lookup"><span data-stu-id="39ae0-174">For details, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="other-articles"></a><span data-ttu-id="39ae0-175">Другие статьи</span><span class="sxs-lookup"><span data-stu-id="39ae0-175">Other articles</span></span>

[<span data-ttu-id="39ae0-176">Изучение сообщений электронной почты на странице Сущности электронной почты</span><span class="sxs-lookup"><span data-stu-id="39ae0-176">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)
