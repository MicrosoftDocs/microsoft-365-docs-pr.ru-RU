---
title: Охота на угрозы в обозревателе угроз для Microsoft Defender для Office 365
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
description: Для эффективного расследования и реагирования на угрозы используйте обнаружения в Microsoft 365 Defender или в режиме реального времени.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0ad5d73abae71cc7cc00e12665d96b2020da0c41
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105433"
---
# <a name="threat-hunting-in-threat-explorer-for-microsoft-defender-for-office-365"></a><span data-ttu-id="91560-103">Охота на угрозы в обозревателе угроз для Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="91560-103">Threat hunting in Threat Explorer for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="91560-104">В этой статье</span><span class="sxs-lookup"><span data-stu-id="91560-104">In this article:</span></span>

- [<span data-ttu-id="91560-105">Обозреватель угроз</span><span class="sxs-lookup"><span data-stu-id="91560-105">Threat Explorer walk-through</span></span>](#threat-explorer-walk-through)
- [<span data-ttu-id="91560-106">Исследование электронной почты</span><span class="sxs-lookup"><span data-stu-id="91560-106">Email investigation</span></span>](#email-investigation)
- [<span data-ttu-id="91560-107">Исправление электронной почты</span><span class="sxs-lookup"><span data-stu-id="91560-107">Email remediation</span></span>](#email-remediation)
- [<span data-ttu-id="91560-108">Улучшения в области охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="91560-108">Improvements to threat hunting experience</span></span>](#improvements-to-threat-hunting-experience)

> [!NOTE]
> <span data-ttu-id="91560-109">Это часть трехсерийной серии по обозревателю угроз **(Explorer),** безопасности электронной почты **и** основам обнаружения explorer и в режиме реального времени **(например,** различия между инструментами и разрешениями, необходимыми для их работы). </span><span class="sxs-lookup"><span data-stu-id="91560-109">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="91560-110">Другие две статьи этой серии : безопасность электронной почты с помощью [обозревателя](email-security-in-microsoft-defender.md) угроз и обозревателя угроз и базов обнаружения [в режиме реального времени.](real-time-detections.md)</span><span class="sxs-lookup"><span data-stu-id="91560-110">The other two articles in this series are [Email security with Threat Explorer](email-security-in-microsoft-defender.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span>


<span data-ttu-id="91560-111">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="91560-111">**Applies to**</span></span>
- [<span data-ttu-id="91560-112">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="91560-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="91560-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="91560-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="91560-114">Если в вашей организации есть [microsoft Defender для](defender-for-office-365.md)Office 365, и у вас  есть [разрешения,](#required-licenses-and-permissions)вы можете использовать обнаружения **Explorer** или в режиме реального времени для обнаружения и устранения угроз.</span><span class="sxs-lookup"><span data-stu-id="91560-114">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Explorer** or **Real-time detections** to detect and remediate threats.</span></span>

<span data-ttu-id="91560-115">На портале Microsoft 365 Defender () перейдите к совместной работе & электронной почты, а затем выберите обнаружение Explorer или в <https://security.microsoft.com>   **режиме реального времени.**</span><span class="sxs-lookup"><span data-stu-id="91560-115">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), go to **Email & collaboration**, and then choose **Explorer** or **Real-time detections**.</span></span> <span data-ttu-id="91560-116">Чтобы сделать непосредственно на странице, используйте <https://security.microsoft.com/threatexplorer> или <https://security.microsoft.com/realtimereports></span><span class="sxs-lookup"><span data-stu-id="91560-116">To do directly to the page, use <https://security.microsoft.com/threatexplorer> or <https://security.microsoft.com/realtimereports></span></span>

<span data-ttu-id="91560-117">С помощью этих средств можно выполнять перечисленные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="91560-117">With these tools, you can:</span></span>

- <span data-ttu-id="91560-118">См. вредоносные программы, обнаруженные Microsoft 365 функциями безопасности</span><span class="sxs-lookup"><span data-stu-id="91560-118">See malware detected by Microsoft 365 security features</span></span>
- <span data-ttu-id="91560-119">Просмотр фишинговых URL-адресов и щелкните данные вердикта</span><span class="sxs-lookup"><span data-stu-id="91560-119">View phishing URL and click verdict data</span></span>
- <span data-ttu-id="91560-120">Запуск автоматизированного процесса расследования и ответа из представления в Explorer</span><span class="sxs-lookup"><span data-stu-id="91560-120">Start an automated investigation and response process from a view in Explorer</span></span>
- <span data-ttu-id="91560-121">Изучение вредоносных сообщений электронной почты и других</span><span class="sxs-lookup"><span data-stu-id="91560-121">Investigate malicious email, and more</span></span>

<span data-ttu-id="91560-122">Дополнительные сведения см. в [сообщении email security with Threat Explorer.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="91560-122">For more information, see [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span>

## <a name="threat-explorer-walk-through"></a><span data-ttu-id="91560-123">Обозреватель угроз</span><span class="sxs-lookup"><span data-stu-id="91560-123">Threat Explorer walk-through</span></span>

<span data-ttu-id="91560-124">В Microsoft Defender для Office 365 существуют два плана подписки: Plan 1 и Plan 2.</span><span class="sxs-lookup"><span data-stu-id="91560-124">In Microsoft Defender for Office 365, there are two subscription plans—Plan 1 and Plan 2.</span></span> <span data-ttu-id="91560-125">Средства для охоты на угрозы, управляемые вручную, существуют в обоих планах под разными именами и с различными возможностями.</span><span class="sxs-lookup"><span data-stu-id="91560-125">Manually operated Threat hunting tools exist in both plans, under different names and with different capabilities.</span></span>

<span data-ttu-id="91560-126">Defender for Office 365 Plan 1 *использует* обнаружения в режиме реального времени , который является подмножество средства охоты Найт Explorer *(также* называемый *Explorer)* в плане 2.</span><span class="sxs-lookup"><span data-stu-id="91560-126">Defender for Office 365 Plan 1 uses *Real-time detections*, which is a subset of the *Threat Explorer* (also called *Explorer*) hunting tool in Plan 2.</span></span> <span data-ttu-id="91560-127">В этой серии статей большинство примеров были созданы с помощью полного обозревателя угроз.</span><span class="sxs-lookup"><span data-stu-id="91560-127">In this series of articles, most of the examples were created using the full Threat Explorer.</span></span> <span data-ttu-id="91560-128">Администраторы должны проверить все действия в обнаружениях в режиме реального времени, чтобы узнать, где они применяются.</span><span class="sxs-lookup"><span data-stu-id="91560-128">Admins should test any steps in Real-time detections to see where they apply.</span></span>

<span data-ttu-id="91560-129">После того как вы перейдите в **Explorer,** по умолчанию, вы прибудете на страницу **Вредоносные** программы, но используйте падение **представления,** чтобы ознакомиться с вашими вариантами.</span><span class="sxs-lookup"><span data-stu-id="91560-129">After you go to **Explorer**, by default, you'll arrive on the **Malware** page, but use the **View** drop down to get familiar with your options.</span></span> <span data-ttu-id="91560-130">Если вы охотитесь за фишингом или копаете в кампанию угроз, выберите эти представления.</span><span class="sxs-lookup"><span data-stu-id="91560-130">If you're hunting Phish, or digging into a threat campaign, choose those views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="91560-131">![Просмотр drop down в Обозревателе угроз](../../media/view-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="91560-131">![View drop down in Threat Explorer](../../media/view-drop-down.png)</span></span>

<span data-ttu-id="91560-132">После того, как пользователь операции безопасности (Sec Ops) выбирает данные, которые они хотят видеть, является ли область узкого представления,  как пользовательские **представления,** или более широкое представление, как все сообщения электронной почты, они могут использовать кнопку Отправитель для дальнейшего фильтрации.</span><span class="sxs-lookup"><span data-stu-id="91560-132">Once a security operations (Sec Ops) person selects the data they want to see, whether the scope is narrow view like user **Submissions**, or a wider view, like **All email**, they can use the **Sender** button to further filter.</span></span> <span data-ttu-id="91560-133">Не забудьте выбрать Обновление для выполнения действий фильтрации.</span><span class="sxs-lookup"><span data-stu-id="91560-133">Remember to select Refresh to complete your filtering actions.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="91560-134">![Кнопка отправитель в Обозревателе угроз](../../media/sender-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="91560-134">![Sender button in Threat Explorer](../../media/sender-drop-down.png)</span></span>

<span data-ttu-id="91560-135">Уточнение фокуса в explorer или обнаружение в режиме реального времени можно мыслить в слоях.</span><span class="sxs-lookup"><span data-stu-id="91560-135">Refining focus in Explorer or Real-time detection can be thought of in layers.</span></span> <span data-ttu-id="91560-136">Первый — **Просмотр**.</span><span class="sxs-lookup"><span data-stu-id="91560-136">The first is **View**.</span></span> <span data-ttu-id="91560-137">Второй можно подумать как *фильтрованный фокус*.</span><span class="sxs-lookup"><span data-stu-id="91560-137">The second can be thought of as a *filtered focus*.</span></span> <span data-ttu-id="91560-138">Например, вы можете отследить действия, предпринятые при поиске угрозы, записав такие решения: Чтобы найти проблему в Explorer, я выбрал просмотр вредоносных программ с фокусом фильтра **получателя.**</span><span class="sxs-lookup"><span data-stu-id="91560-138">For example, you can retrace the steps you took in finding a threat by recording your decisions like this: To find the issue in Explorer, **I chose the Malware View with a Recipient filter focus**.</span></span> <span data-ttu-id="91560-139">Это упрощает отслеживание действий.</span><span class="sxs-lookup"><span data-stu-id="91560-139">This makes retracing your steps easier.</span></span>

> [!TIP]
> <span data-ttu-id="91560-140">Если sec Ops использует теги для маркировки учетных записей, которые они считают высокооценными целями, они могут делать выборы, такие как просмотр фишинга с фокусом фильтра Теги (включив диапазон дат, если *используется)*. </span><span class="sxs-lookup"><span data-stu-id="91560-140">If Sec Ops uses **Tags** to mark accounts they consider high valued targets, they can make selections like *Phish View with a Tags filter focus (include a date range if used)*.</span></span> <span data-ttu-id="91560-141">Это покажет им все попытки фишинга, направленные на их высокие целевые значения пользователей во время диапазона времени (например, даты, когда некоторые фишинговые атаки происходят много для их отрасли).</span><span class="sxs-lookup"><span data-stu-id="91560-141">This will show them any phishing attempts directed at their high value user targets during a time-range (like dates when certain phishing attacks are happening a lot for their industry).</span></span>

<span data-ttu-id="91560-142">Уточнения можно сделать в диапазоне дат с помощью элементов управления диапазоном дат.</span><span class="sxs-lookup"><span data-stu-id="91560-142">Refinements can be made on date ranges by using the date range controls.</span></span> <span data-ttu-id="91560-143">Здесь вы можете увидеть Обозреватель в **представлении вредоносных программ** с фокусом **фильтра технологии** обнаружения.</span><span class="sxs-lookup"><span data-stu-id="91560-143">Here you can see Explorer in **Malware** view, with a **Detection Technology** filter focus.</span></span> <span data-ttu-id="91560-144">Но это кнопка **Расширенный фильтр,** которая позволяет командам Sec Ops копать глубоко.</span><span class="sxs-lookup"><span data-stu-id="91560-144">But it's the **Advanced filter** button that lets Sec Ops teams dig deep.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="91560-145">![Расширенный фильтр в обозревателе угроз](../../media/advanced-filter.png)</span><span class="sxs-lookup"><span data-stu-id="91560-145">![Advanced filter in Threat Explorer](../../media/advanced-filter.png)</span></span>

<span data-ttu-id="91560-146">Щелкнув **расширенный** фильтр, всплывет панель, которая позволит охотникам sec Ops самостоятельно создавать запросы, позволяя им включать или исключать сведения, которые они должны видеть.</span><span class="sxs-lookup"><span data-stu-id="91560-146">Clicking the **Advanced filter** pops a panel that will let Sec Ops hunters build queries themselves, letting them include or exclude the information they need to see.</span></span> <span data-ttu-id="91560-147">И диаграмма, и таблица на странице Explorer будут отражать их результаты.</span><span class="sxs-lookup"><span data-stu-id="91560-147">Both the chart and table on the Explorer page will reflect their results.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="91560-148">![Результаты запроса](../../media/threat-explorer-chart-table.png)</span><span class="sxs-lookup"><span data-stu-id="91560-148">![Results from a query](../../media/threat-explorer-chart-table.png)</span></span>

<span data-ttu-id="91560-149">Используйте **кнопку Параметры Столбец,** чтобы получить наиболее полезные сведения на таблице:</span><span class="sxs-lookup"><span data-stu-id="91560-149">Use the **Column options** button to get the kind of information on the table that would be most helpful:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="91560-150">![Кнопка параметры столбца выделена](../../media/threat-explorer-column-options.png)</span><span class="sxs-lookup"><span data-stu-id="91560-150">![Column options button highlighted](../../media/threat-explorer-column-options.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="91560-151">![Доступные параметры в столбцах](../../media/column-options.png)</span><span class="sxs-lookup"><span data-stu-id="91560-151">![Available options in Columns](../../media/column-options.png)</span></span>

<span data-ttu-id="91560-152">В том же мьене убедитесь, что протестировать параметры отображения.</span><span class="sxs-lookup"><span data-stu-id="91560-152">In the same mien, make sure to test your display options.</span></span> <span data-ttu-id="91560-153">Различные аудитории будут хорошо реагировать на различные презентации одинаковых данных.</span><span class="sxs-lookup"><span data-stu-id="91560-153">Different audiences will react well to different presentations of the same data.</span></span> <span data-ttu-id="91560-154">Для некоторых зрителей карта **"Происхождение** электронной почты" может показать, что угроза распространена или скрыта быстрее, чем параметр **отображения** Кампании рядом с ней.</span><span class="sxs-lookup"><span data-stu-id="91560-154">For some viewers, the **Email Origins** map can show that a threat is widespread or discreet more quickly than the **Campaign display** option right next to it.</span></span> <span data-ttu-id="91560-155">Sec Ops может использовать эти дисплеи, чтобы наилучшим образом сделать пункты, подчеркивая необходимость безопасности и защиты, или для более позднего сравнения, чтобы продемонстрировать эффективность своих действий.</span><span class="sxs-lookup"><span data-stu-id="91560-155">Sec Ops can make use of these displays to best make points that underscore the need for security and protection, or for later comparison, to demonstrate the effectiveness of their actions.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="91560-156">![Карта "Происхождение электронной почты"](../../media/threat-explorer-email-origin-map.png)</span><span class="sxs-lookup"><span data-stu-id="91560-156">![Email Origins map](../../media/threat-explorer-email-origin-map.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="91560-157">![Параметры отображения кампании](../../media/threat-explorer-campaign-display.png)</span><span class="sxs-lookup"><span data-stu-id="91560-157">![Campaign display options](../../media/threat-explorer-campaign-display.png)</span></span>

### <a name="email-investigation"></a><span data-ttu-id="91560-158">Исследование электронной почты</span><span class="sxs-lookup"><span data-stu-id="91560-158">Email investigation</span></span>

<span data-ttu-id="91560-159">Когда вы видите подозрительное сообщение электронной почты, щелкните имя, чтобы расширить флажок справа.</span><span class="sxs-lookup"><span data-stu-id="91560-159">When you see a suspicious email, click the name to expand the flyout on the right.</span></span> <span data-ttu-id="91560-160">Здесь доступен баннер, который позволяет sec Ops видеть страницу сущности [электронной](mdo-email-entity-page.md) почты.</span><span class="sxs-lookup"><span data-stu-id="91560-160">Here, the banner that lets Sec Ops see the [email entity page](mdo-email-entity-page.md) is available.</span></span>

<span data-ttu-id="91560-161">Страница сущности электронной почты объединяет содержимое, которое можно найти в статье **Details,** **Attachments**, **Devices,** но включает более организованные данные.</span><span class="sxs-lookup"><span data-stu-id="91560-161">The email entity page pulls together contents that can be found under **Details**, **Attachments**, **Devices**, but includes more organized data.</span></span> <span data-ttu-id="91560-162">Это включает в себя такие вещи, как результаты DMARC, простой текстовый дисплей заголовка электронной почты с вариантом копирования, сведения о вердикте о вложениях, которые были надежно взорваны, и файлы эти детонации упали (могут включать IP-адреса, которые были связаться и скриншоты страниц или файлов).</span><span class="sxs-lookup"><span data-stu-id="91560-162">This includes things like DMARC results, plain text display of the email header with a copy option, verdict information on attachments that were securely detonated, and files those detonations dropped (can include IP addresses that were contacted and screenshots of pages or files).</span></span> <span data-ttu-id="91560-163">Url-адреса и их решения также перечислены с аналогичными сведениями.</span><span class="sxs-lookup"><span data-stu-id="91560-163">URLs and their verdicts are also listed with similar details reported.</span></span>

<span data-ttu-id="91560-164">Когда вы достигнете этого этапа, страница сущности электронной почты будет иметь решающее значение для последнего шага —*исправление.*</span><span class="sxs-lookup"><span data-stu-id="91560-164">When you reach this stage, the email entity page will be critical to the final step—*remediation*.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="91560-165">![Страница сущности электронной почты](../../media/threat-explorer-email-entity-page.png)</span><span class="sxs-lookup"><span data-stu-id="91560-165">![The email entity page](../../media/threat-explorer-email-entity-page.png)</span></span>

> [!TIP]
> <span data-ttu-id="91560-166">Дополнительные сведения о богатой странице сущности электронной почты (см. ниже на вкладке **Analysis),** включая результаты взорванных вложений, результаты для включенных URL-адресов и безопасный предварительный просмотр электронной почты, нажмите [здесь](mdo-email-entity-page.md).</span><span class="sxs-lookup"><span data-stu-id="91560-166">To learn more about the rich email entity page (seen below on the **Analysis** tab), including the results of detonated Attachments, findings for included URLs, and safe Email preview, click [here](mdo-email-entity-page.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="91560-167">![Вкладка анализа страницы сущности электронной почты](../../media/threat-explorer-analysis-tab.png)</span><span class="sxs-lookup"><span data-stu-id="91560-167">![Analysis tab of the email entity page](../../media/threat-explorer-analysis-tab.png)</span></span>

### <a name="email-remediation"></a><span data-ttu-id="91560-168">Исправление электронной почты</span><span class="sxs-lookup"><span data-stu-id="91560-168">Email remediation</span></span>

<span data-ttu-id="91560-169">После того как человек Sec Ops определяет, что сообщение электронной почты представляет собой угрозу, следующий шаг обнаружения Explorer или в режиме реального времени устраняет угрозу и устраняет ее.</span><span class="sxs-lookup"><span data-stu-id="91560-169">Once a Sec Ops person determines that an email is a threat, the next Explorer or Real-time detection step is dealing with the threat and remediating it.</span></span> <span data-ttu-id="91560-170">Это можно сделать, вернувшись в Обозреватель угроз, выбрав почтовый ящик для проблемной электронной почты и используя кнопку **Действия.**</span><span class="sxs-lookup"><span data-stu-id="91560-170">This can be done by returning to Threat Explorer, selecting the checkbox for the problem email, and using the **Actions** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="91560-171">![Кнопка Действия в обозревателе угроз](../../media/threat-explorer-email-actions-button.png)</span><span class="sxs-lookup"><span data-stu-id="91560-171">![Actions button in Threat Explorer](../../media/threat-explorer-email-actions-button.png)</span></span>

<span data-ttu-id="91560-172">Здесь аналитик может принимать меры, такие как сообщение почты как спам, фишинг или вредоносные программы, контакты с получателями или дальнейшие расследования, которые могут включать запуск книг автоматического расследования и ответа (или AIR) (если у вас есть план 2).</span><span class="sxs-lookup"><span data-stu-id="91560-172">Here, the analyst can take actions like reporting the mail as Spam, Phishing, or Malware, contacting recipients, or further investigations that can include triggering Automated Investigation and Response (or AIR) playbooks (if you have Plan 2).</span></span> <span data-ttu-id="91560-173">Или, почта также может быть отчитаться как чистая.</span><span class="sxs-lookup"><span data-stu-id="91560-173">Or, the mail can also be reported as clean.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="91560-174">![Действие падает](../../media/threat-explorer-email-actions-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="91560-174">![The Actions drop down](../../media/threat-explorer-email-actions-drop-down.png)</span></span>

## <a name="improvements-to-threat-hunting-experience"></a><span data-ttu-id="91560-175">Улучшения в области охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="91560-175">Improvements to threat hunting experience</span></span>

### <a name="alert-id"></a><span data-ttu-id="91560-176">Alert ID</span><span class="sxs-lookup"><span data-stu-id="91560-176">Alert ID</span></span>

<span data-ttu-id="91560-177">При переходе из оповещений в Обозреватель угроз представление будет фильтроваться по **alert ID**. </span><span class="sxs-lookup"><span data-stu-id="91560-177">When navigating from an alert into Threat Explorer, the **View** will be filtered by **Alert ID**.</span></span> <span data-ttu-id="91560-178">Это также применяется при обнаружении в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="91560-178">This also applies in Real-time detection.</span></span> <span data-ttu-id="91560-179">Показаны сообщения, соответствующие определенному оповещению, а также общее число сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="91560-179">Messages relevant to the specific alert, and an email total (a count) are shown.</span></span> <span data-ttu-id="91560-180">Вы сможете узнать, было ли сообщение частью оповещений, а также перейти от этого сообщения к связанному оповещению.</span><span class="sxs-lookup"><span data-stu-id="91560-180">You will be able to see if a message was part of an alert, as well as navigate from that message to the related alert.</span></span>

<span data-ttu-id="91560-181">Наконец, в URL-адрес включен iD оповещений, например: `https://https://security.microsoft.com/viewalerts`</span><span class="sxs-lookup"><span data-stu-id="91560-181">Finally, alert ID is included in the URL, for example: `https://https://security.microsoft.com/viewalerts`</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="91560-182">![Фильтрация для alert ID](../../media/AlertID-Filter.png)</span><span class="sxs-lookup"><span data-stu-id="91560-182">![Filtering for Alert ID](../../media/AlertID-Filter.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="91560-183">![Alert ID in details flyout](../../media/AlertID-DetailsFlyout.png)</span><span class="sxs-lookup"><span data-stu-id="91560-183">![Alert ID in details flyout](../../media/AlertID-DetailsFlyout.png)</span></span>

### <a name="extending-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants"></a><span data-ttu-id="91560-184">Расширение лимита хранения и поиска данных Explorer (и обнаружения в режиме реального времени) для клиентов пробных периодов</span><span class="sxs-lookup"><span data-stu-id="91560-184">Extending Explorer (and Real-time detections) data retention and search limit for trial tenants</span></span>

<span data-ttu-id="91560-185">В рамках этого изменения аналитики смогут искать и фильтровать данные электронной почты в течение 30 дней (увеличено с семи дней) при обнаружении в обозревателе угроз и в режиме реального времени для клиентов defender для Office P1 и P2.</span><span class="sxs-lookup"><span data-stu-id="91560-185">As part of this change, analysts will be able to search for, and filter email data across 30 days (increased from seven days) in Threat Explorer and Real-time detections for both Defender for Office P1 and P2 trial tenants.</span></span> <span data-ttu-id="91560-186">Это не влияет на производственных клиентов P1 и P2 E5, где по умолчанию хранения уже 30 дней.</span><span class="sxs-lookup"><span data-stu-id="91560-186">This doesn't impact any production tenants for both P1 and P2 E5 customers, where the retention default is already 30 days.</span></span>

### <a name="updated-export-limit"></a><span data-ttu-id="91560-187">Обновленный лимит экспорта</span><span class="sxs-lookup"><span data-stu-id="91560-187">Updated Export limit</span></span>

<span data-ttu-id="91560-188">Количество записей электронной почты, которые можно экспортировать из Обозревателя угроз, сейчас составляет 200 000 (было 9990).</span><span class="sxs-lookup"><span data-stu-id="91560-188">The number of Emails records that can be exported from Threat Explorer is now 200,000 (was 9990).</span></span> <span data-ttu-id="91560-189">Набор столбцов, которые можно экспортировать, не изменяется.</span><span class="sxs-lookup"><span data-stu-id="91560-189">The set of columns that can be exported is unchanged.</span></span>

### <a name="tags-in-threat-explorer"></a><span data-ttu-id="91560-190">Теги в обозревателе угроз</span><span class="sxs-lookup"><span data-stu-id="91560-190">Tags in Threat Explorer</span></span>

> [!NOTE]
> <span data-ttu-id="91560-191">Функция тегов пользователя находится в предварительной версии и может быть доступна не всем.</span><span class="sxs-lookup"><span data-stu-id="91560-191">The user tags feature is in Preview and may not be available to everyone.</span></span> <span data-ttu-id="91560-192">Кроме того, предварительные просмотры могут изменяться.</span><span class="sxs-lookup"><span data-stu-id="91560-192">Also, Previews are subject to change.</span></span> <span data-ttu-id="91560-193">Сведения о расписании выпуска ознакомьтесь с Microsoft 365 плана.</span><span class="sxs-lookup"><span data-stu-id="91560-193">For information about the release schedule, check out the Microsoft 365 roadmap.</span></span>

<span data-ttu-id="91560-194">Теги пользователей определяют определенные группы пользователей в Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="91560-194">User tags identify specific groups of users in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="91560-195">Дополнительные сведения о тегах, включая лицензирование и конфигурацию, см. в [тегах User.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="91560-195">For more information about tags, including licensing and configuration, see [User tags](user-tags.md).</span></span>

<span data-ttu-id="91560-196">В Обозревателе угроз можно увидеть сведения о тегах пользователей в следующих действиях.</span><span class="sxs-lookup"><span data-stu-id="91560-196">In Threat Explorer, you can see information about user tags in the following experiences.</span></span>

#### <a name="email-grid-view"></a><span data-ttu-id="91560-197">Представление сетки электронной почты</span><span class="sxs-lookup"><span data-stu-id="91560-197">Email grid view</span></span>

<span data-ttu-id="91560-198">Когда аналитики смотрят на столбец **Теги** сетки электронной почты, они видят все теги, которые были применены к почтовым ящикам отправитель или получатель.</span><span class="sxs-lookup"><span data-stu-id="91560-198">When analysts look at the **Tags** column the email grid, they are seeing all tags that have been applied to sender or recipient mailboxes.</span></span> <span data-ttu-id="91560-199">По умолчанию сначала показаны системные теги, такие как *учетные* записи приоритетов.</span><span class="sxs-lookup"><span data-stu-id="91560-199">By default, system tags like *priority accounts* are shown first.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="91560-200">![Фильтрация тегов в представлении сетки электронной почты](../../media/tags-grid.png)</span><span class="sxs-lookup"><span data-stu-id="91560-200">![Filter tags in email grid view](../../media/tags-grid.png)</span></span>

#### <a name="filtering"></a><span data-ttu-id="91560-201">Фильтрация</span><span class="sxs-lookup"><span data-stu-id="91560-201">Filtering</span></span>

<span data-ttu-id="91560-202">Теги можно использовать в качестве фильтров.</span><span class="sxs-lookup"><span data-stu-id="91560-202">Tags can be used as filters.</span></span> <span data-ttu-id="91560-203">Охота только на учетные записи приоритетов или использование определенных сценариев тегов пользователей таким образом.</span><span class="sxs-lookup"><span data-stu-id="91560-203">Hunt among priority accounts only, or use specific user tags scenarios this way.</span></span> <span data-ttu-id="91560-204">Можно также исключить результаты с определенными тегами.</span><span class="sxs-lookup"><span data-stu-id="91560-204">You can also exclude results that have certain tags.</span></span> <span data-ttu-id="91560-205">Объединяйте теги с другими фильтрами и диапазонами дат, чтобы сузить область исследования.</span><span class="sxs-lookup"><span data-stu-id="91560-205">Combine Tags with other filters and date ranges to narrow your scope of investigation.</span></span>

<span data-ttu-id="91560-206">[![Теги фильтрации](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="91560-206">[![Filter tags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="91560-207">![Не фильтровать теги](../../media/tags-filter-not.png)</span><span class="sxs-lookup"><span data-stu-id="91560-207">![Not filter tags](../../media/tags-filter-not.png)</span></span>

#### <a name="email-detail-flyout"></a><span data-ttu-id="91560-208">Вылет детализации электронной почты</span><span class="sxs-lookup"><span data-stu-id="91560-208">Email detail flyout</span></span>

<span data-ttu-id="91560-209">Чтобы просмотреть отдельные теги для отправитель и получатель, выберите электронную почту, чтобы открыть вылет сведений о сообщении.</span><span class="sxs-lookup"><span data-stu-id="91560-209">To view the individual tags for sender and recipient, select an email to open the message details flyout.</span></span> <span data-ttu-id="91560-210">На **вкладке Сводка** теги отправитель и получатель показаны отдельно.</span><span class="sxs-lookup"><span data-stu-id="91560-210">On the **Summary** tab, the sender and recipient tags are shown separately.</span></span> <span data-ttu-id="91560-211">Сведения об отдельных тегах отправитель и получатель могут экспортироваться в качестве данных CSV.</span><span class="sxs-lookup"><span data-stu-id="91560-211">The information about individual tags for sender and recipient can be exported as CSV data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="91560-212">![Теги сведений электронной почты](../../media/tags-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="91560-212">![Email Details tags](../../media/tags-flyout.png)</span></span>

<span data-ttu-id="91560-213">Сведения о тегах также показаны в вылете url-адресов.</span><span class="sxs-lookup"><span data-stu-id="91560-213">Tags information is also shown in the URL clicks flyout.</span></span> <span data-ttu-id="91560-214">Чтобы просмотреть его, перейдите в фишинг или все представления электронной почты > **URL-адрес** или вкладку **Щелчки** URL-адресов. Выберите отдельный url-адрес, чтобы узнать дополнительные сведения о щелчках для этого URL-адреса, включая все теги, связанные с этим щелчком.</span><span class="sxs-lookup"><span data-stu-id="91560-214">To see it, go to Phish or All Email view > **URLs** or **URL Clicks** tab. Select an individual URL flyout to see additional details about clicks for that URL, including any Tags associated with that click.</span></span>

### <a name="updated-timeline-view"></a><span data-ttu-id="91560-215">Обновленное представление Временной шкалы</span><span class="sxs-lookup"><span data-stu-id="91560-215">Updated Timeline View</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="91560-216">![ТЕГИ URL-адресов](../../media/tags-urls.png)</span><span class="sxs-lookup"><span data-stu-id="91560-216">![URL tags](../../media/tags-urls.png)</span></span>
>
<span data-ttu-id="91560-217">Узнайте больше, посмотрев [это](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4) видео.</span><span class="sxs-lookup"><span data-stu-id="91560-217">Learn more by watching [this video](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).</span></span>

## <a name="extended-capabilities"></a><span data-ttu-id="91560-218">Расширенные возможности</span><span class="sxs-lookup"><span data-stu-id="91560-218">Extended capabilities</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="91560-219">Лучшие целевые пользователи</span><span class="sxs-lookup"><span data-stu-id="91560-219">Top targeted users</span></span>

<span data-ttu-id="91560-220">Топ семей вредоносных программ показывает **топ целевых пользователей в** разделе Вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="91560-220">Top Malware Families shows the **top targeted users** in the Malware section.</span></span> <span data-ttu-id="91560-221">Верхние целевые пользователи также будут расширены с помощью представлений фишинга и всех сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="91560-221">Top targeted users will be extended through Phish and All Email views too.</span></span> <span data-ttu-id="91560-222">Аналитики смогут видеть топ-5 целевых пользователей, а также количество попыток для каждого пользователя в каждом представлении.</span><span class="sxs-lookup"><span data-stu-id="91560-222">Analysts will be able to see the top-five targeted users, along with the number of attempts for each user in each view.</span></span>

<span data-ttu-id="91560-223">Пользователи операций безопасности смогут экспортировать список целевых пользователей, не более 3000, а также количество попыток для автономного анализа для каждого представления электронной почты.</span><span class="sxs-lookup"><span data-stu-id="91560-223">Security operations people be able to export the list of targeted users, up to a limit of 3,000, along with the number of attempts made, for offline analysis for each email view.</span></span> <span data-ttu-id="91560-224">Кроме того, выбор количества попыток (например, 13 попыток на изображении ниже) откроет фильтрованное представление в Обозревателе угроз, чтобы вы могли видеть дополнительные сведения по электронной почте и угрозы для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="91560-224">Also, selecting the number of attempts (for example, 13 attempts in the image below) will open a filtered view in Threat Explorer, so you can see more details across emails, and threats for that user.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="91560-225">![Лучшие целевые пользователи](../../media/Top_Targeted_Users.png)</span><span class="sxs-lookup"><span data-stu-id="91560-225">![Top targeted users](../../media/Top_Targeted_Users.png)</span></span>

### <a name="exchange-transport-rules"></a><span data-ttu-id="91560-226">Exchange правила транспорта</span><span class="sxs-lookup"><span data-stu-id="91560-226">Exchange transport rules</span></span>

<span data-ttu-id="91560-227">Группа операций безопасности сможет просматривать все правила транспорта Exchange (или правила потока почты), применяемые к сообщению, в представлении сетки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="91560-227">The security operations team will be able to see all the Exchange transport rules (or Mail flow rules) applied to a message, in the Email grid view.</span></span> <span data-ttu-id="91560-228">Выберите **параметры Столбец** в сетке и добавьте **Exchange правила транспорта** из столбцов.</span><span class="sxs-lookup"><span data-stu-id="91560-228">Select **Column options** in the grid and then **Add Exchange Transport Rule** from the column options.</span></span> <span data-ttu-id="91560-229">Параметр Exchange транспортных правил также отображается в вылете **Details** в электронной почте.</span><span class="sxs-lookup"><span data-stu-id="91560-229">The Exchange transport rules option is also visible on the **Details** flyout in the email.</span></span>

<span data-ttu-id="91560-230">Отображаются имена и GUID правил транспорта, применяемых к сообщению.</span><span class="sxs-lookup"><span data-stu-id="91560-230">Names and GUIDs of the transport rules applied to the message appear.</span></span> <span data-ttu-id="91560-231">Аналитики смогут искать сообщения с помощью имени правила транспорта.</span><span class="sxs-lookup"><span data-stu-id="91560-231">Analysts will be able to search for messages by using the name of the transport rule.</span></span> <span data-ttu-id="91560-232">Это поиск CONTAINS, который означает, что вы также можете делать частичные поиски.</span><span class="sxs-lookup"><span data-stu-id="91560-232">This is a CONTAINS search, which means you can do partial searches as well.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="91560-233">Exchange поиска правил транспорта и доступности имен зависит от конкретной роли, назначенной вам.</span><span class="sxs-lookup"><span data-stu-id="91560-233">Exchange transport rule search and name availability depend on the specific role assigned to you.</span></span> <span data-ttu-id="91560-234">Для просмотра имен правил транспорта и поиска необходимо иметь одну из следующих ролей или разрешений.</span><span class="sxs-lookup"><span data-stu-id="91560-234">You need to have one of the following roles or permissions to view the transport rule names and search.</span></span> <span data-ttu-id="91560-235">Однако даже без ролей или разрешений ниже аналитик может видеть метку правил транспорта и сведения GUID в сведениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="91560-235">However, even without the roles or permissions below, an analyst may see the transport rule label and GUID information in the Email Details.</span></span> <span data-ttu-id="91560-236">Другие опытом просмотра записей в сетках электронной почты, вылеты электронной почты, фильтры и экспорт не затронуты.</span><span class="sxs-lookup"><span data-stu-id="91560-236">Other record-viewing experiences in Email Grids, Email flyouts, Filters, and Export are not affected.</span></span>
>
> - <span data-ttu-id="91560-237">Exchange Online Только - Предотвращение потери данных: все</span><span class="sxs-lookup"><span data-stu-id="91560-237">Exchange Online Only - Data Loss Prevention: All</span></span>
> - <span data-ttu-id="91560-238">Exchange Online Только - O365SupportViewConfig: Все</span><span class="sxs-lookup"><span data-stu-id="91560-238">Exchange Online Only - O365SupportViewConfig: All</span></span>
> - <span data-ttu-id="91560-239">Microsoft Azure Active Directory или Exchange Online - администратор безопасности: все</span><span class="sxs-lookup"><span data-stu-id="91560-239">Microsoft Azure Active Directory or Exchange Online - Security Admin: All</span></span>
> - <span data-ttu-id="91560-240">Azure Active Directory или Exchange Online - Считыватель безопасности: все</span><span class="sxs-lookup"><span data-stu-id="91560-240">Azure Active Directory or Exchange Online - Security Reader: All</span></span>
> - <span data-ttu-id="91560-241">Exchange Online Только - Правила транспорта: Все</span><span class="sxs-lookup"><span data-stu-id="91560-241">Exchange Online Only - Transport Rules: All</span></span>
> - <span data-ttu-id="91560-242">Exchange Online Только — View-Only конфигурация: все</span><span class="sxs-lookup"><span data-stu-id="91560-242">Exchange Online Only - View-Only Configuration: All</span></span>
>
> <span data-ttu-id="91560-243">В сетке электронной почты, вылете Подробные сведения и экспортируемом CSV etRs представлены с именем/GUID, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="91560-243">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>
>
> > [!div class="mx-imgBorder"]
> > <span data-ttu-id="91560-244">![Exchange Правила транспорта](../../media/ETR_Details.png)</span><span class="sxs-lookup"><span data-stu-id="91560-244">![Exchange Transport Rules](../../media/ETR_Details.png)</span></span>

### <a name="inbound-connectors"></a><span data-ttu-id="91560-245">Входящие соединители</span><span class="sxs-lookup"><span data-stu-id="91560-245">Inbound connectors</span></span>

<span data-ttu-id="91560-246">Соединители — это набор инструкций, которые настраивают потоки электронной почты в вашу Microsoft 365 или Office 365 организацию.</span><span class="sxs-lookup"><span data-stu-id="91560-246">Connectors are a collection of instructions that customize how your email flows to and from your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="91560-247">Они позволяют применять любые ограничения безопасности или элементы управления.</span><span class="sxs-lookup"><span data-stu-id="91560-247">They enable you to apply any security restrictions or controls.</span></span> <span data-ttu-id="91560-248">В Обозревателе угроз можно просматривать соединители, связанные с электронной почтой, и искать сообщения с помощью имен соединитеителей.</span><span class="sxs-lookup"><span data-stu-id="91560-248">In Threat Explorer, you can view the connectors that are related to an email and search for emails using connector names.</span></span>

<span data-ttu-id="91560-249">Поиск соединители — это запрос CONTAINS, что означает, что может работать частичный поиск по ключевым словам:</span><span class="sxs-lookup"><span data-stu-id="91560-249">The search for connectors is a CONTAINS query, which means partial keyword searches can work:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="91560-250">![Сведения о соединители](../../media/Connector_Details.png)</span><span class="sxs-lookup"><span data-stu-id="91560-250">![Connector details](../../media/Connector_Details.png)</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="91560-251">Обязательные лицензии и разрешения</span><span class="sxs-lookup"><span data-stu-id="91560-251">Required licenses and permissions</span></span>

<span data-ttu-id="91560-252">Вы должны иметь [Microsoft Defender для Office 365](defender-for-office-365.md) для использования обнаружения Explorer или в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="91560-252">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use Explorer or Real-time detections.</span></span>

- <span data-ttu-id="91560-253">Explorer включен в Defender для Office 365 Plan 2.</span><span class="sxs-lookup"><span data-stu-id="91560-253">Explorer is included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="91560-254">Отчет о обнаружениях в режиме реального времени включен в Defender для Office 365 плана 1.</span><span class="sxs-lookup"><span data-stu-id="91560-254">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>
- <span data-ttu-id="91560-255">Планирование назначения лицензий для всех пользователей, которые должны быть защищены Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="91560-255">Plan to assign licenses for all users who should be protected by Defender for Office 365.</span></span> <span data-ttu-id="91560-256">Обнаружение explorer и в режиме реального времени показывает данные обнаружения для лицензированных пользователей.</span><span class="sxs-lookup"><span data-stu-id="91560-256">Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="91560-257">Чтобы просмотреть и использовать обнаружения Explorer или в режиме реального времени, необходимо иметь следующие разрешения:</span><span class="sxs-lookup"><span data-stu-id="91560-257">To view and use Explorer or Real-time detections, you must have the following permissions:</span></span>

- <span data-ttu-id="91560-258">Для портала Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="91560-258">For the Microsoft 365 Defender portal:</span></span>
  - <span data-ttu-id="91560-259">Управление организацией</span><span class="sxs-lookup"><span data-stu-id="91560-259">Organization Management</span></span>
  - <span data-ttu-id="91560-260">Администратор безопасности (это может быть назначено в центре администрирования Azure Active Directory ( <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="91560-260">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="91560-261">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="91560-261">Security Reader</span></span>
- <span data-ttu-id="91560-262">Для Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="91560-262">For Exchange Online:</span></span>
  - <span data-ttu-id="91560-263">Управление организацией</span><span class="sxs-lookup"><span data-stu-id="91560-263">Organization Management</span></span>
  - <span data-ttu-id="91560-264">Управление организацией только с правом на просмотр</span><span class="sxs-lookup"><span data-stu-id="91560-264">View-Only Organization Management</span></span>
  - <span data-ttu-id="91560-265">Получатели только для чтения</span><span class="sxs-lookup"><span data-stu-id="91560-265">View-Only Recipients</span></span>
  - <span data-ttu-id="91560-266">Управление соответствием требованиям</span><span class="sxs-lookup"><span data-stu-id="91560-266">Compliance Management</span></span>

<span data-ttu-id="91560-267">Дополнительные информацию о ролях и разрешениях см. в следующих ресурсах:</span><span class="sxs-lookup"><span data-stu-id="91560-267">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="91560-268">Разрешения на портале Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="91560-268">Permissions in the Microsoft 365 Defender portal</span></span>](permissions-microsoft-365-security-center.md)
- [<span data-ttu-id="91560-269">Разрешения компонентов в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="91560-269">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)
- [<span data-ttu-id="91560-270">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="91560-270">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a><span data-ttu-id="91560-271">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="91560-271">More information</span></span>

- [<span data-ttu-id="91560-272">Поиск и изучение доставленной нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="91560-272">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="91560-273">Просмотр вредоносных файлов, обнаруженных в SharePoint Online, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="91560-273">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="91560-274">Обзор представлений в Обозревателе угроз (и обнаружения в режиме реального времени)</span><span class="sxs-lookup"><span data-stu-id="91560-274">Get an overview of the views in Threat Explorer (and Real-time detections)</span></span>](threat-explorer-views.md)
- <span data-ttu-id="91560-275">[отчет о состоянии защиты от угроз](view-email-security-reports.md#threat-protection-status-report);</span><span class="sxs-lookup"><span data-stu-id="91560-275">[Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="91560-276">Автоматизированный анализ угроз и реакция на угрозы в службе защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="91560-276">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md)
- [<span data-ttu-id="91560-277">Изучение сообщений электронной почты на странице Сущности электронной почты</span><span class="sxs-lookup"><span data-stu-id="91560-277">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)
