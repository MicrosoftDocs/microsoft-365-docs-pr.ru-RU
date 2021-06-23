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
ms.openlocfilehash: 2b0c0c36cb481aac64b55467da4aaf9e3cf7a493
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083564"
---
# <a name="threat-hunting-in-threat-explorer-for-microsoft-defender-for-office-365"></a><span data-ttu-id="4e88e-103">Охота на угрозы в обозревателе угроз для Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="4e88e-103">Threat hunting in Threat Explorer for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="4e88e-104">В этой статье</span><span class="sxs-lookup"><span data-stu-id="4e88e-104">In this article:</span></span>

- [<span data-ttu-id="4e88e-105">Обозреватель угроз</span><span class="sxs-lookup"><span data-stu-id="4e88e-105">Threat Explorer walk-through</span></span>](#threat-explorer-walk-through)
- [<span data-ttu-id="4e88e-106">Исследование электронной почты</span><span class="sxs-lookup"><span data-stu-id="4e88e-106">Email investigation</span></span>](#email-investigation)
- [<span data-ttu-id="4e88e-107">Исправление электронной почты</span><span class="sxs-lookup"><span data-stu-id="4e88e-107">Email remediation</span></span>](#email-remediation)
- [<span data-ttu-id="4e88e-108">Улучшения в области охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="4e88e-108">Improvements to threat hunting experience</span></span>](#improvements-to-threat-hunting-experience)

> [!NOTE]
> <span data-ttu-id="4e88e-109">Это часть трехсерийной серии по обозревателю угроз **(Explorer),** безопасности электронной почты **и** основам обнаружения explorer и в режиме реального времени **(например,** различия между инструментами и разрешениями, необходимыми для их работы). </span><span class="sxs-lookup"><span data-stu-id="4e88e-109">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="4e88e-110">Другие две статьи этой серии : безопасность электронной почты с помощью [обозревателя](email-security-in-microsoft-defender.md) угроз и обозревателя угроз и базов обнаружения [в режиме реального времени.](real-time-detections.md)</span><span class="sxs-lookup"><span data-stu-id="4e88e-110">The other two articles in this series are [Email security with Threat Explorer](email-security-in-microsoft-defender.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span>


<span data-ttu-id="4e88e-111">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="4e88e-111">**Applies to**</span></span>
- [<span data-ttu-id="4e88e-112">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="4e88e-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="4e88e-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4e88e-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="4e88e-114">Если в вашей организации есть [microsoft Defender для](defender-for-office-365.md)Office 365, и у вас  есть [разрешения,](#required-licenses-and-permissions)вы можете использовать обнаружения **Explorer** или в режиме реального времени для обнаружения и устранения угроз.</span><span class="sxs-lookup"><span data-stu-id="4e88e-114">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Explorer** or **Real-time detections** to detect and remediate threats.</span></span> 

<span data-ttu-id="4e88e-115">На **портале Microsoft 365 Defender перейдите** к совместной & электронной почты, а затем выберите **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="4e88e-115">In the **Microsoft 365 Defender portal**, go to **Email & collaboration**, and then choose **Explorer**.</span></span>

<br>

****

|<span data-ttu-id="4e88e-116">В Microsoft Defender для Office 365 Plan 2 см.:</span><span class="sxs-lookup"><span data-stu-id="4e88e-116">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="4e88e-117">В Microsoft Defender для Office 365 1 см.:</span><span class="sxs-lookup"><span data-stu-id="4e88e-117">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![Обозреватель угроз](../../media/path-to-explorer.png)|![Обнаружение в режиме реального времени](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="4e88e-120">С помощью этих средств можно выполнять перечисленные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="4e88e-120">With these tools, you can:</span></span>

- <span data-ttu-id="4e88e-121">См. вредоносные программы, обнаруженные Microsoft 365 функциями безопасности</span><span class="sxs-lookup"><span data-stu-id="4e88e-121">See malware detected by Microsoft 365 security features</span></span>
- <span data-ttu-id="4e88e-122">Просмотр фишинговых URL-адресов и щелкните данные вердикта</span><span class="sxs-lookup"><span data-stu-id="4e88e-122">View phishing URL and click verdict data</span></span>
- <span data-ttu-id="4e88e-123">Запуск автоматизированного процесса расследования и ответа из представления в Explorer</span><span class="sxs-lookup"><span data-stu-id="4e88e-123">Start an automated investigation and response process from a view in Explorer</span></span>
- <span data-ttu-id="4e88e-124">Изучение вредоносных сообщений электронной почты и других</span><span class="sxs-lookup"><span data-stu-id="4e88e-124">Investigate malicious email, and more</span></span>

<span data-ttu-id="4e88e-125">Дополнительные сведения см. в [сообщении email security with Threat Explorer.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="4e88e-125">For more information, see [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span> 

## <a name="threat-explorer-walk-through"></a><span data-ttu-id="4e88e-126">Обозреватель угроз</span><span class="sxs-lookup"><span data-stu-id="4e88e-126">Threat Explorer walk-through</span></span>

<span data-ttu-id="4e88e-127">В Microsoft Defender для Office 365 существуют два плана подписки: Plan 1 и Plan 2.</span><span class="sxs-lookup"><span data-stu-id="4e88e-127">In Microsoft Defender for Office 365, there are two subscription plans—Plan 1 and Plan 2.</span></span> <span data-ttu-id="4e88e-128">Средства для охоты на угрозы, управляемые вручную, существуют в обоих планах под разными именами и с различными возможностями.</span><span class="sxs-lookup"><span data-stu-id="4e88e-128">Manually operated Threat hunting tools exist in both plans, under different names and with different capabilities.</span></span>

<span data-ttu-id="4e88e-129">Defender for Office 365 Plan 1 *использует* обнаружения в режиме реального времени , который является подмножество средства охоты Найт Explorer *(также* называемый *Explorer)* в плане 2.</span><span class="sxs-lookup"><span data-stu-id="4e88e-129">Defender for Office 365 Plan 1 uses *Real-time detections*, which is a subset of the *Threat Explorer* (also called *Explorer*) hunting tool in Plan 2.</span></span> <span data-ttu-id="4e88e-130">В этой серии статей большинство примеров были созданы с помощью полного обозревателя угроз.</span><span class="sxs-lookup"><span data-stu-id="4e88e-130">In this series of articles, most of the examples were created using the full Threat Explorer.</span></span> <span data-ttu-id="4e88e-131">Администраторы должны проверить все действия в обнаружениях в режиме реального времени, чтобы узнать, где они применяются.</span><span class="sxs-lookup"><span data-stu-id="4e88e-131">Admins should test any steps in Real-time detections to see where they apply.</span></span>

<span data-ttu-id="4e88e-132">Чтобы открыть средство Explorer, перейдите **на Microsoft 365 Defender email**&  >    >  **explorer.**</span><span class="sxs-lookup"><span data-stu-id="4e88e-132">To open the Explorer tool, go to **Microsoft 365 Defender portal** > **Email & collaboration** > **Explorer**.</span></span> <span data-ttu-id="4e88e-133">По умолчанию вы прибудете на страницу **Вредоносные** программы, но для ознакомления с вашими вариантами используйте падение **View.**</span><span class="sxs-lookup"><span data-stu-id="4e88e-133">By default, you’ll arrive on the **Malware** page, but use the **View** drop down to get familiar with your options.</span></span> <span data-ttu-id="4e88e-134">Если вы охотитесь за фишингом или копаете в кампанию угроз, выберите эти представления.</span><span class="sxs-lookup"><span data-stu-id="4e88e-134">If you’re hunting Phish, or digging into a threat campaign, choose those views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4e88e-135">![Просмотр drop down в Обозревателе угроз](../../media/view-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="4e88e-135">![View drop down in Threat Explorer](../../media/view-drop-down.png)</span></span>

<span data-ttu-id="4e88e-136">После того, как пользователь операции безопасности (Sec Ops) выбирает данные, которые они хотят видеть, является ли область узкого представления,  как пользовательские **представления,** или более широкое представление, как все сообщения электронной почты, они могут использовать кнопку Отправитель для дальнейшего фильтрации.</span><span class="sxs-lookup"><span data-stu-id="4e88e-136">Once a security operations (Sec Ops) person selects the data they want to see, whether the scope is narrow view like user **Submissions**, or a wider view, like **All email**, they can use the **Sender** button to further filter.</span></span> <span data-ttu-id="4e88e-137">Не забудьте выбрать Обновление для выполнения действий фильтрации.</span><span class="sxs-lookup"><span data-stu-id="4e88e-137">Remember to select Refresh to complete your filtering actions.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4e88e-138">![Кнопка отправитель в Обозревателе угроз](../../media/sender-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="4e88e-138">![Sender button in Threat Explorer](../../media/sender-drop-down.png)</span></span>

<span data-ttu-id="4e88e-139">Уточнение фокуса в explorer или обнаружение в режиме реального времени можно мыслить в слоях.</span><span class="sxs-lookup"><span data-stu-id="4e88e-139">Refining focus in Explorer or Real-time detection can be thought of in layers.</span></span> <span data-ttu-id="4e88e-140">Первый — **Просмотр**.</span><span class="sxs-lookup"><span data-stu-id="4e88e-140">The first is **View**.</span></span> <span data-ttu-id="4e88e-141">Второй можно подумать как *фильтрованный фокус*.</span><span class="sxs-lookup"><span data-stu-id="4e88e-141">The second can be thought of as a *filtered focus*.</span></span> <span data-ttu-id="4e88e-142">Например, вы можете отследить действия, предпринятые при поиске угрозы, записав такие решения: Чтобы найти проблему в Explorer, я выбрал просмотр вредоносных программ с фокусом фильтра **получателя.**</span><span class="sxs-lookup"><span data-stu-id="4e88e-142">For example, you can retrace the steps you took in finding a threat by recording your decisions like this: To find the issue in Explorer, **I chose the Malware View with a Recipient filter focus**.</span></span> <span data-ttu-id="4e88e-143">Это упрощает отслеживание действий.</span><span class="sxs-lookup"><span data-stu-id="4e88e-143">This makes retracing your steps easier.</span></span>

> [!TIP]
> <span data-ttu-id="4e88e-144">Если sec Ops использует теги для маркировки учетных записей, которые они считают высокооценными целями, они могут делать выборы, такие как просмотр фишинга с фокусом фильтра Теги (включив диапазон дат, если *используется)*. </span><span class="sxs-lookup"><span data-stu-id="4e88e-144">If Sec Ops uses **Tags** to mark accounts they consider high valued targets, they can make selections like *Phish View with a Tags filter focus (include a date range if used)*.</span></span> <span data-ttu-id="4e88e-145">Это покажет им все попытки фишинга, направленные на их высокие целевые значения пользователей во время диапазона времени (например, даты, когда некоторые фишинговые атаки происходят много для их отрасли).</span><span class="sxs-lookup"><span data-stu-id="4e88e-145">This will show them any phishing attempts directed at their high value user targets during a time-range (like dates when certain phishing attacks are happening a lot for their industry).</span></span> 

<span data-ttu-id="4e88e-146">Уточнения можно сделать в диапазоне дат с помощью элементов управления диапазоном дат.</span><span class="sxs-lookup"><span data-stu-id="4e88e-146">Refinements can be made on date ranges by using the date range controls.</span></span> <span data-ttu-id="4e88e-147">Здесь вы можете увидеть Обозреватель в **представлении вредоносных программ** с фокусом **фильтра технологии** обнаружения.</span><span class="sxs-lookup"><span data-stu-id="4e88e-147">Here you can see Explorer in **Malware** view, with a **Detection Technology** filter focus.</span></span> <span data-ttu-id="4e88e-148">Но это кнопка **Расширенный фильтр,** которая позволяет командам Sec Ops копать глубоко.</span><span class="sxs-lookup"><span data-stu-id="4e88e-148">But it’s the **Advanced filter** button that lets Sec Ops teams dig deep.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4e88e-149">![Расширенный фильтр в обозревателе угроз](../../media/advanced-filter.png)</span><span class="sxs-lookup"><span data-stu-id="4e88e-149">![Advanced filter in Threat Explorer](../../media/advanced-filter.png)</span></span>

<span data-ttu-id="4e88e-150">Щелкнув **расширенный** фильтр, всплывет панель, которая позволит охотникам sec Ops самостоятельно создавать запросы, позволяя им включать или исключать сведения, которые они должны видеть.</span><span class="sxs-lookup"><span data-stu-id="4e88e-150">Clicking the **Advanced filter** pops a panel that will let Sec Ops hunters build queries themselves, letting them include or exclude the information they need to see.</span></span> <span data-ttu-id="4e88e-151">И диаграмма, и таблица на странице Explorer будут отражать их результаты.</span><span class="sxs-lookup"><span data-stu-id="4e88e-151">Both the chart and table on the Explorer page will reflect their results.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4e88e-152">![Результаты запроса](../../media/threat-explorer-chart-table.png)</span><span class="sxs-lookup"><span data-stu-id="4e88e-152">![Results from a query](../../media/threat-explorer-chart-table.png)</span></span>

<span data-ttu-id="4e88e-153">Используйте **кнопку Параметры Столбец,** чтобы получить наиболее полезные сведения на таблице:</span><span class="sxs-lookup"><span data-stu-id="4e88e-153">Use the **Column options** button to get the kind of information on the table that would be most helpful:</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4e88e-154">![Кнопка параметры столбца выделена](../../media/threat-explorer-column-options.png)</span><span class="sxs-lookup"><span data-stu-id="4e88e-154">![Column options button highlighted](../../media/threat-explorer-column-options.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4e88e-155">![Доступные параметры в столбцах](../../media/column-options.png)</span><span class="sxs-lookup"><span data-stu-id="4e88e-155">![Available options in Columns](../../media/column-options.png)</span></span>

<span data-ttu-id="4e88e-156">В том же мьене убедитесь, что протестировать параметры отображения.</span><span class="sxs-lookup"><span data-stu-id="4e88e-156">In the same mien, make sure to test your display options.</span></span> <span data-ttu-id="4e88e-157">Различные аудитории будут хорошо реагировать на различные презентации одинаковых данных.</span><span class="sxs-lookup"><span data-stu-id="4e88e-157">Different audiences will react well to different presentations of the same data.</span></span> <span data-ttu-id="4e88e-158">Для некоторых зрителей карта **"Происхождение** электронной почты" может показать, что угроза распространена или скрыта быстрее, чем параметр **отображения** Кампании рядом с ней.</span><span class="sxs-lookup"><span data-stu-id="4e88e-158">For some viewers, the **Email Origins** map can show that a threat is widespread or discreet more quickly than the **Campaign display** option right next to it.</span></span> <span data-ttu-id="4e88e-159">Sec Ops может использовать эти дисплеи, чтобы наилучшим образом сделать пункты, подчеркивая необходимость безопасности и защиты, или для более позднего сравнения, чтобы продемонстрировать эффективность своих действий.</span><span class="sxs-lookup"><span data-stu-id="4e88e-159">Sec Ops can make use of these displays to best make points that underscore the need for security and protection, or for later comparison, to demonstrate the effectiveness of their actions.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4e88e-160">![Карта "Происхождение электронной почты"](../../media/threat-explorer-email-origin-map.png)</span><span class="sxs-lookup"><span data-stu-id="4e88e-160">![Email Origins map](../../media/threat-explorer-email-origin-map.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4e88e-161">![Параметры отображения кампании](../../media/threat-explorer-campaign-display.png)</span><span class="sxs-lookup"><span data-stu-id="4e88e-161">![Campaign display options](../../media/threat-explorer-campaign-display.png)</span></span>

### <a name="email-investigation"></a><span data-ttu-id="4e88e-162">Исследование электронной почты</span><span class="sxs-lookup"><span data-stu-id="4e88e-162">Email investigation</span></span>

<span data-ttu-id="4e88e-163">Когда вы видите подозрительное сообщение электронной почты, щелкните имя, чтобы расширить флажок справа.</span><span class="sxs-lookup"><span data-stu-id="4e88e-163">When you see a suspicious email, click the name to expand the flyout on the right.</span></span> <span data-ttu-id="4e88e-164">Здесь доступен баннер, который позволяет sec Ops видеть страницу сущности [электронной](mdo-email-entity-page.md) почты.</span><span class="sxs-lookup"><span data-stu-id="4e88e-164">Here, the banner that lets Sec Ops see the [email entity page](mdo-email-entity-page.md) is available.</span></span>

<span data-ttu-id="4e88e-165">Страница сущности электронной почты объединяет содержимое, которое можно найти в статье **Details,** **Attachments**, **Devices,** но включает более организованные данные.</span><span class="sxs-lookup"><span data-stu-id="4e88e-165">The email entity page pulls together contents that can be found under **Details**, **Attachments**, **Devices**, but includes more organized data.</span></span> <span data-ttu-id="4e88e-166">Это включает в себя такие вещи, как результаты DMARC, простой текстовый дисплей заголовка электронной почты с вариантом копирования, сведения о вердикте о вложениях, которые были надежно взорваны, и файлы эти детонации упали (могут включать IP-адреса, которые были связаться и скриншоты страниц или файлов).</span><span class="sxs-lookup"><span data-stu-id="4e88e-166">This includes things like DMARC results, plain text display of the email header with a copy option, verdict information on attachments that were securely detonated, and files those detonations dropped (can include IP addresses that were contacted and screenshots of pages or files).</span></span> <span data-ttu-id="4e88e-167">Url-адреса и их решения также перечислены с аналогичными сведениями.</span><span class="sxs-lookup"><span data-stu-id="4e88e-167">URLs and their verdicts are also listed with similar details reported.</span></span> 

<span data-ttu-id="4e88e-168">Когда вы достигнете этого этапа, страница сущности электронной почты будет иметь решающее значение для последнего шага —*исправление.*</span><span class="sxs-lookup"><span data-stu-id="4e88e-168">When you reach this stage, the email entity page will be critical to the final step—*remediation*.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4e88e-169">![Страница сущности электронной почты](../../media/threat-explorer-email-entity-page.png)</span><span class="sxs-lookup"><span data-stu-id="4e88e-169">![The email entity page](../../media/threat-explorer-email-entity-page.png)</span></span>

> [!TIP]
> <span data-ttu-id="4e88e-170">Дополнительные сведения о богатой странице сущности электронной почты (см. ниже на вкладке **Analysis),** включая результаты взорванных вложений, результаты для включенных URL-адресов и безопасный предварительный просмотр электронной почты, нажмите [здесь](mdo-email-entity-page.md).</span><span class="sxs-lookup"><span data-stu-id="4e88e-170">To learn more about the rich email entity page (seen below on the **Analysis** tab), including the results of detonated Attachments, findings for included URLs, and safe Email preview, click [here](mdo-email-entity-page.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4e88e-171">![Вкладка анализа страницы сущности электронной почты](../../media/threat-explorer-analysis-tab.png)</span><span class="sxs-lookup"><span data-stu-id="4e88e-171">![Analysis tab of the email entity page](../../media/threat-explorer-analysis-tab.png)</span></span>

### <a name="email-remediation"></a><span data-ttu-id="4e88e-172">Исправление электронной почты</span><span class="sxs-lookup"><span data-stu-id="4e88e-172">Email remediation</span></span>

<span data-ttu-id="4e88e-173">После того как человек Sec Ops определяет, что сообщение электронной почты представляет собой угрозу, следующий шаг обнаружения Explorer или в режиме реального времени устраняет угрозу и устраняет ее.</span><span class="sxs-lookup"><span data-stu-id="4e88e-173">Once a Sec Ops person determines that an email is a threat, the next Explorer or Real-time detection step is dealing with the threat and remediating it.</span></span> <span data-ttu-id="4e88e-174">Это можно сделать, вернувшись в Обозреватель угроз, выбрав почтовый ящик для проблемной электронной почты и используя кнопку **Действия.**</span><span class="sxs-lookup"><span data-stu-id="4e88e-174">This can be done by returning to Threat Explorer, selecting the checkbox for the problem email, and using the **Actions** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4e88e-175">![Кнопка Действия в обозревателе угроз](../../media/threat-explorer-email-actions-button.png)</span><span class="sxs-lookup"><span data-stu-id="4e88e-175">![Actions button in Threat Explorer](../../media/threat-explorer-email-actions-button.png)</span></span>

<span data-ttu-id="4e88e-176">Здесь аналитик может принимать меры, такие как сообщение почты как спам, фишинг или вредоносные программы, контакты с получателями или дальнейшие расследования, которые могут включать запуск книг автоматического расследования и ответа (или AIR) (если у вас есть план 2).</span><span class="sxs-lookup"><span data-stu-id="4e88e-176">Here, the analyst can take actions like reporting the mail as Spam, Phishing, or Malware, contacting recipients, or further investigations that can include triggering Automated Investigation and Response (or AIR) playbooks (if you have Plan 2).</span></span> <span data-ttu-id="4e88e-177">Или, почта также может быть отчитаться как чистая.</span><span class="sxs-lookup"><span data-stu-id="4e88e-177">Or, the mail can also be reported as clean.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4e88e-178">![Действие падает](../../media/threat-explorer-email-actions-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="4e88e-178">![The Actions drop down](../../media/threat-explorer-email-actions-drop-down.png)</span></span>

## <a name="improvements-to-threat-hunting-experience"></a><span data-ttu-id="4e88e-179">Улучшения в области охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="4e88e-179">Improvements to threat hunting experience</span></span>

### <a name="alert-id"></a><span data-ttu-id="4e88e-180">Alert ID</span><span class="sxs-lookup"><span data-stu-id="4e88e-180">Alert ID</span></span>

<span data-ttu-id="4e88e-181">При переходе из оповещений в Обозреватель угроз представление будет фильтроваться по **alert ID**. </span><span class="sxs-lookup"><span data-stu-id="4e88e-181">When navigating from an alert into Threat Explorer, the **View** will be filtered by **Alert ID**.</span></span> <span data-ttu-id="4e88e-182">Это также применяется при обнаружении в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="4e88e-182">This also applies in Real-time detection.</span></span> <span data-ttu-id="4e88e-183">Показаны сообщения, соответствующие определенному оповещению, а также общее число сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4e88e-183">Messages relevant to the specific alert, and an email total (a count) are shown.</span></span> <span data-ttu-id="4e88e-184">Вы сможете узнать, было ли сообщение частью оповещений, а также перейти от этого сообщения к связанному оповещению.</span><span class="sxs-lookup"><span data-stu-id="4e88e-184">You will be able to see if a message was part of an alert, as well as navigate from that message to the related alert.</span></span>

<span data-ttu-id="4e88e-185">Наконец, в URL-адрес включен iD оповещений, например: `https://https://security.microsoft.com/viewalerts`</span><span class="sxs-lookup"><span data-stu-id="4e88e-185">Finally, alert ID is included in the URL, for example: `https://https://security.microsoft.com/viewalerts`</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4e88e-186">![Фильтрация для alert ID](../../media/AlertID-Filter.png)</span><span class="sxs-lookup"><span data-stu-id="4e88e-186">![Filtering for Alert ID](../../media/AlertID-Filter.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4e88e-187">![Alert ID in details flyout](../../media/AlertID-DetailsFlyout.png)</span><span class="sxs-lookup"><span data-stu-id="4e88e-187">![Alert ID in details flyout](../../media/AlertID-DetailsFlyout.png)</span></span>

### <a name="extending-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants"></a><span data-ttu-id="4e88e-188">Расширение лимита хранения и поиска данных Explorer (и обнаружения в режиме реального времени) для клиентов пробных периодов</span><span class="sxs-lookup"><span data-stu-id="4e88e-188">Extending Explorer (and Real-time detections) data retention and search limit for trial tenants</span></span> 

<span data-ttu-id="4e88e-189">В рамках этого изменения аналитики смогут искать и фильтровать данные электронной почты в течение 30 дней (увеличено с семи дней) при обнаружении в обозревателе угроз и в режиме реального времени для клиентов defender для Office P1 и P2.</span><span class="sxs-lookup"><span data-stu-id="4e88e-189">As part of this change, analysts will be able to search for, and filter email data across 30 days (increased from seven days) in Threat Explorer and Real-time detections for both Defender for Office P1 and P2 trial tenants.</span></span> <span data-ttu-id="4e88e-190">Это не влияет на производственных клиентов P1 и P2 E5, где по умолчанию хранения уже 30 дней.</span><span class="sxs-lookup"><span data-stu-id="4e88e-190">This doesn’t impact any production tenants for both P1 and P2 E5 customers, where the retention default is already 30 days.</span></span>

### <a name="updated-export-limit"></a><span data-ttu-id="4e88e-191">Обновленный лимит экспорта</span><span class="sxs-lookup"><span data-stu-id="4e88e-191">Updated Export limit</span></span> 

<span data-ttu-id="4e88e-192">Количество записей электронной почты, которые можно экспортировать из Обозревателя угроз, сейчас составляет 200 000 (было 9990).</span><span class="sxs-lookup"><span data-stu-id="4e88e-192">The number of Emails records that can be exported from Threat Explorer is now 200,000 (was 9990).</span></span> <span data-ttu-id="4e88e-193">Набор столбцов, которые можно экспортировать, не изменяется.</span><span class="sxs-lookup"><span data-stu-id="4e88e-193">The set of columns that can be exported is unchanged.</span></span> 

### <a name="tags-in-threat-explorer"></a><span data-ttu-id="4e88e-194">Теги в обозревателе угроз</span><span class="sxs-lookup"><span data-stu-id="4e88e-194">Tags in Threat Explorer</span></span>

> [!NOTE]
> <span data-ttu-id="4e88e-195">Функция тегов пользователя находится в предварительной версии и может быть доступна не всем.</span><span class="sxs-lookup"><span data-stu-id="4e88e-195">The user tags feature is in Preview and may not be available to everyone.</span></span> <span data-ttu-id="4e88e-196">Кроме того, предварительные просмотры могут изменяться.</span><span class="sxs-lookup"><span data-stu-id="4e88e-196">Also, Previews are subject to change.</span></span> <span data-ttu-id="4e88e-197">Сведения о расписании выпуска ознакомьтесь с Microsoft 365 плана.</span><span class="sxs-lookup"><span data-stu-id="4e88e-197">For information about the release schedule, check out the Microsoft 365 roadmap.</span></span>

<span data-ttu-id="4e88e-198">Теги пользователей определяют определенные группы пользователей в Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="4e88e-198">User tags identify specific groups of users in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="4e88e-199">Дополнительные сведения о тегах, включая лицензирование и конфигурацию, см. в [тегах User.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="4e88e-199">For more information about tags, including licensing and configuration, see [User tags](user-tags.md).</span></span>

<span data-ttu-id="4e88e-200">В Обозревателе угроз можно увидеть сведения о тегах пользователей в следующих действиях.</span><span class="sxs-lookup"><span data-stu-id="4e88e-200">In Threat Explorer, you can see information about user tags in the following experiences.</span></span>

#### <a name="email-grid-view"></a><span data-ttu-id="4e88e-201">Представление сетки электронной почты</span><span class="sxs-lookup"><span data-stu-id="4e88e-201">Email grid view</span></span>

<span data-ttu-id="4e88e-202">Когда аналитики смотрят на столбец **Теги** сетки электронной почты, они видят все теги, которые были применены к почтовым ящикам отправитель или получатель.</span><span class="sxs-lookup"><span data-stu-id="4e88e-202">When analysts look at the **Tags** column the email grid, they are seeing all tags that have been applied to sender or recipient mailboxes.</span></span> <span data-ttu-id="4e88e-203">По умолчанию сначала показаны системные теги, такие как *учетные* записи приоритетов.</span><span class="sxs-lookup"><span data-stu-id="4e88e-203">By default, system tags like *priority accounts* are shown first.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4e88e-204">![Фильтрация тегов в представлении сетки электронной почты](../../media/tags-grid.png)</span><span class="sxs-lookup"><span data-stu-id="4e88e-204">![Filter tags in email grid view](../../media/tags-grid.png)</span></span>

#### <a name="filtering"></a><span data-ttu-id="4e88e-205">Фильтрация</span><span class="sxs-lookup"><span data-stu-id="4e88e-205">Filtering</span></span>

<span data-ttu-id="4e88e-206">Теги можно использовать в качестве фильтров.</span><span class="sxs-lookup"><span data-stu-id="4e88e-206">Tags can be used as filters.</span></span> <span data-ttu-id="4e88e-207">Охота только на учетные записи приоритетов или использование определенных сценариев тегов пользователей таким образом.</span><span class="sxs-lookup"><span data-stu-id="4e88e-207">Hunt among priority accounts only, or use specific user tags scenarios this way.</span></span> <span data-ttu-id="4e88e-208">Можно также исключить результаты с определенными тегами.</span><span class="sxs-lookup"><span data-stu-id="4e88e-208">You can also exclude results that have certain tags.</span></span> <span data-ttu-id="4e88e-209">Объединяйте теги с другими фильтрами и диапазонами дат, чтобы сузить область исследования.</span><span class="sxs-lookup"><span data-stu-id="4e88e-209">Combine Tags with other filters and date ranges to narrow your scope of investigation.</span></span> 

<span data-ttu-id="4e88e-210">[![Теги фильтрации](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="4e88e-210">[![Filter tags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4e88e-211">![Не фильтровать теги](../../media/tags-filter-not.png)</span><span class="sxs-lookup"><span data-stu-id="4e88e-211">![Not filter tags](../../media/tags-filter-not.png)</span></span>

#### <a name="email-detail-flyout"></a><span data-ttu-id="4e88e-212">Вылет детализации электронной почты</span><span class="sxs-lookup"><span data-stu-id="4e88e-212">Email detail flyout</span></span>

<span data-ttu-id="4e88e-213">Чтобы просмотреть отдельные теги для отправитель и получатель, выберите электронную почту, чтобы открыть вылет сведений о сообщении.</span><span class="sxs-lookup"><span data-stu-id="4e88e-213">To view the individual tags for sender and recipient, select an email to open the message details flyout.</span></span> <span data-ttu-id="4e88e-214">На **вкладке Сводка** теги отправитель и получатель показаны отдельно.</span><span class="sxs-lookup"><span data-stu-id="4e88e-214">On the **Summary** tab, the sender and recipient tags are shown separately.</span></span> <span data-ttu-id="4e88e-215">Сведения об отдельных тегах отправитель и получатель могут экспортироваться в качестве данных CSV.</span><span class="sxs-lookup"><span data-stu-id="4e88e-215">The information about individual tags for sender and recipient can be exported as CSV data.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4e88e-216">![Теги сведений электронной почты](../../media/tags-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="4e88e-216">![Email Details tags](../../media/tags-flyout.png)</span></span>

<span data-ttu-id="4e88e-217">Сведения о тегах также показаны в вылете url-адресов.</span><span class="sxs-lookup"><span data-stu-id="4e88e-217">Tags information is also shown in the URL clicks flyout.</span></span> <span data-ttu-id="4e88e-218">Чтобы просмотреть его, перейдите в фишинг или все представления электронной почты > **URL-адрес** или вкладку **Щелчки** URL-адресов. Выберите отдельный url-адрес, чтобы узнать дополнительные сведения о щелчках для этого URL-адреса, включая все теги, связанные с этим щелчком.</span><span class="sxs-lookup"><span data-stu-id="4e88e-218">To see it, go to Phish or All Email view > **URLs** or **URL Clicks** tab. Select an individual URL flyout to see additional details about clicks for that URL, including any Tags associated with that click.</span></span>

### <a name="updated-timeline-view"></a><span data-ttu-id="4e88e-219">Обновленное представление Временной шкалы</span><span class="sxs-lookup"><span data-stu-id="4e88e-219">Updated Timeline View</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4e88e-220">![ТЕГИ URL-адресов](../../media/tags-urls.png)</span><span class="sxs-lookup"><span data-stu-id="4e88e-220">![URL tags](../../media/tags-urls.png)</span></span>
>
<span data-ttu-id="4e88e-221">Узнайте больше, посмотрев [это](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4) видео.</span><span class="sxs-lookup"><span data-stu-id="4e88e-221">Learn more by watching [this video](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).</span></span>

## <a name="extended-capabilities"></a><span data-ttu-id="4e88e-222">Расширенные возможности</span><span class="sxs-lookup"><span data-stu-id="4e88e-222">Extended capabilities</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="4e88e-223">Лучшие целевые пользователи</span><span class="sxs-lookup"><span data-stu-id="4e88e-223">Top targeted users</span></span>

<span data-ttu-id="4e88e-224">Топ семей вредоносных программ показывает **топ целевых пользователей в** разделе Вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="4e88e-224">Top Malware Families shows the **top targeted users** in the Malware section.</span></span> <span data-ttu-id="4e88e-225">Верхние целевые пользователи также будут расширены с помощью представлений фишинга и всех сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4e88e-225">Top targeted users will be extended through Phish and All Email views too.</span></span> <span data-ttu-id="4e88e-226">Аналитики смогут видеть топ-5 целевых пользователей, а также количество попыток для каждого пользователя в каждом представлении.</span><span class="sxs-lookup"><span data-stu-id="4e88e-226">Analysts will be able to see the top-five targeted users, along with the number of attempts for each user in each view.</span></span> 

<span data-ttu-id="4e88e-227">Пользователи операций безопасности смогут экспортировать список целевых пользователей, не более 3000, а также количество попыток для автономного анализа для каждого представления электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4e88e-227">Security operations people be able to export the list of targeted users, up to a limit of 3,000, along with the number of attempts made, for offline analysis for each email view.</span></span> <span data-ttu-id="4e88e-228">Кроме того, выбор количества попыток (например, 13 попыток на изображении ниже) откроет фильтрованное представление в Обозревателе угроз, чтобы вы могли видеть дополнительные сведения по электронной почте и угрозы для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="4e88e-228">Also, selecting the number of attempts (for example, 13 attempts in the image below) will open a filtered view in Threat Explorer, so you can see more details across emails, and threats for that user.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4e88e-229">![Лучшие целевые пользователи](../../media/Top_Targeted_Users.png)</span><span class="sxs-lookup"><span data-stu-id="4e88e-229">![Top targeted users](../../media/Top_Targeted_Users.png)</span></span>

### <a name="exchange-transport-rules"></a><span data-ttu-id="4e88e-230">Exchange правила транспорта</span><span class="sxs-lookup"><span data-stu-id="4e88e-230">Exchange transport rules</span></span>

<span data-ttu-id="4e88e-231">Группа операций безопасности сможет просматривать все правила транспорта Exchange (или правила потока почты), применяемые к сообщению, в представлении сетки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4e88e-231">The security operations team will be able to see all the Exchange transport rules (or Mail flow rules) applied to a message, in the Email grid view.</span></span> <span data-ttu-id="4e88e-232">Выберите **параметры Столбец** в сетке и добавьте **Exchange правила транспорта** из столбцов.</span><span class="sxs-lookup"><span data-stu-id="4e88e-232">Select **Column options** in the grid and then **Add Exchange Transport Rule** from the column options.</span></span> <span data-ttu-id="4e88e-233">Параметр Exchange транспортных правил также отображается в вылете **Details** в электронной почте.</span><span class="sxs-lookup"><span data-stu-id="4e88e-233">The Exchange transport rules option is also visible on the **Details** flyout in the email.</span></span> 

<span data-ttu-id="4e88e-234">Отображаются имена и GUID правил транспорта, применяемых к сообщению.</span><span class="sxs-lookup"><span data-stu-id="4e88e-234">Names and GUIDs of the transport rules applied to the message appear.</span></span> <span data-ttu-id="4e88e-235">Аналитики смогут искать сообщения с помощью имени правила транспорта.</span><span class="sxs-lookup"><span data-stu-id="4e88e-235">Analysts will be able to search for messages by using the name of the transport rule.</span></span> <span data-ttu-id="4e88e-236">Это поиск CONTAINS, который означает, что вы также можете делать частичные поиски.</span><span class="sxs-lookup"><span data-stu-id="4e88e-236">This is a CONTAINS search, which means you can do partial searches as well.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="4e88e-237">Exchange поиска правил транспорта и доступности имен зависит от конкретной роли, назначенной вам.</span><span class="sxs-lookup"><span data-stu-id="4e88e-237">Exchange transport rule search and name availability depend on the specific role assigned to you.</span></span> <span data-ttu-id="4e88e-238">Для просмотра имен правил транспорта и поиска необходимо иметь одну из следующих ролей или разрешений.</span><span class="sxs-lookup"><span data-stu-id="4e88e-238">You need to have one of the following roles or permissions to view the transport rule names and search.</span></span> <span data-ttu-id="4e88e-239">Однако даже без ролей или разрешений ниже аналитик может видеть метку правил транспорта и сведения GUID в сведениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4e88e-239">However, even without the roles or permissions below, an analyst may see the transport rule label and GUID information in the Email Details.</span></span> <span data-ttu-id="4e88e-240">Другие опытом просмотра записей в сетках электронной почты, вылеты электронной почты, фильтры и экспорт не затронуты.</span><span class="sxs-lookup"><span data-stu-id="4e88e-240">Other record-viewing experiences in Email Grids, Email flyouts, Filters, and Export are not affected.</span></span>
>
> - <span data-ttu-id="4e88e-241">Exchange Online Только - Предотвращение потери данных: все</span><span class="sxs-lookup"><span data-stu-id="4e88e-241">Exchange Online Only - Data Loss Prevention: All</span></span>
> - <span data-ttu-id="4e88e-242">Exchange Online Только - O365SupportViewConfig: Все</span><span class="sxs-lookup"><span data-stu-id="4e88e-242">Exchange Online Only - O365SupportViewConfig: All</span></span>
> - <span data-ttu-id="4e88e-243">Microsoft Azure Active Directory или Exchange Online - администратор безопасности: все</span><span class="sxs-lookup"><span data-stu-id="4e88e-243">Microsoft Azure Active Directory or Exchange Online - Security Admin: All</span></span>
> - <span data-ttu-id="4e88e-244">Azure Active Directory или Exchange Online - Считыватель безопасности: все</span><span class="sxs-lookup"><span data-stu-id="4e88e-244">Azure Active Directory or Exchange Online - Security Reader: All</span></span>
> - <span data-ttu-id="4e88e-245">Exchange Online Только - Правила транспорта: Все</span><span class="sxs-lookup"><span data-stu-id="4e88e-245">Exchange Online Only - Transport Rules: All</span></span>
> - <span data-ttu-id="4e88e-246">Exchange Online Только — View-Only конфигурация: все</span><span class="sxs-lookup"><span data-stu-id="4e88e-246">Exchange Online Only - View-Only Configuration: All</span></span>
>
> <span data-ttu-id="4e88e-247">В сетке электронной почты, вылете Подробные сведения и экспортируемом CSV etRs представлены с именем/GUID, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="4e88e-247">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>
>
> > [!div class="mx-imgBorder"]
> > <span data-ttu-id="4e88e-248">![Exchange Правила транспорта](../../media/ETR_Details.png)</span><span class="sxs-lookup"><span data-stu-id="4e88e-248">![Exchange Transport Rules](../../media/ETR_Details.png)</span></span>

### <a name="inbound-connectors"></a><span data-ttu-id="4e88e-249">Входящие соединители</span><span class="sxs-lookup"><span data-stu-id="4e88e-249">Inbound connectors</span></span>

<span data-ttu-id="4e88e-250">Соединители — это набор инструкций, которые настраивают потоки электронной почты в вашу Microsoft 365 или Office 365 организацию.</span><span class="sxs-lookup"><span data-stu-id="4e88e-250">Connectors are a collection of instructions that customize how your email flows to and from your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="4e88e-251">Они позволяют применять любые ограничения безопасности или элементы управления.</span><span class="sxs-lookup"><span data-stu-id="4e88e-251">They enable you to apply any security restrictions or controls.</span></span> <span data-ttu-id="4e88e-252">В Обозревателе угроз можно просматривать соединители, связанные с электронной почтой, и искать сообщения с помощью имен соединитеителей.</span><span class="sxs-lookup"><span data-stu-id="4e88e-252">In Threat Explorer, you can view the connectors that are related to an email and search for emails using connector names.</span></span> 

<span data-ttu-id="4e88e-253">Поиск соединители — это запрос CONTAINS, что означает, что может работать частичный поиск по ключевым словам:</span><span class="sxs-lookup"><span data-stu-id="4e88e-253">The search for connectors is a CONTAINS query, which means partial keyword searches can work:</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4e88e-254">![Сведения о соединители](../../media/Connector_Details.png)</span><span class="sxs-lookup"><span data-stu-id="4e88e-254">![Connector details](../../media/Connector_Details.png)</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="4e88e-255">Обязательные лицензии и разрешения</span><span class="sxs-lookup"><span data-stu-id="4e88e-255">Required licenses and permissions</span></span>

<span data-ttu-id="4e88e-256">Вы должны иметь [Microsoft Defender для Office 365](defender-for-office-365.md) для использования обнаружения Explorer или в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="4e88e-256">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use Explorer or Real-time detections.</span></span>

- <span data-ttu-id="4e88e-257">Explorer включен в Defender для Office 365 Plan 2.</span><span class="sxs-lookup"><span data-stu-id="4e88e-257">Explorer is included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="4e88e-258">Отчет о обнаружениях в режиме реального времени включен в Defender для Office 365 плана 1.</span><span class="sxs-lookup"><span data-stu-id="4e88e-258">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>
- <span data-ttu-id="4e88e-259">Планирование назначения лицензий для всех пользователей, которые должны быть защищены Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="4e88e-259">Plan to assign licenses for all users who should be protected by Defender for Office 365.</span></span> <span data-ttu-id="4e88e-260">Обнаружение explorer и в режиме реального времени показывает данные обнаружения для лицензированных пользователей.</span><span class="sxs-lookup"><span data-stu-id="4e88e-260">Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="4e88e-261">Чтобы просмотреть и использовать обнаружения Explorer или в режиме реального времени, необходимо иметь следующее:</span><span class="sxs-lookup"><span data-stu-id="4e88e-261">To view and use Explorer or Real-time detections, you must have the following:</span></span>

- <span data-ttu-id="4e88e-262">Для портала Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="4e88e-262">For the Microsoft 365 Defender portal:</span></span>

  - <span data-ttu-id="4e88e-263">Управление организацией</span><span class="sxs-lookup"><span data-stu-id="4e88e-263">Organization Management</span></span>
  - <span data-ttu-id="4e88e-264">Администратор безопасности (это может быть назначено в центре администрирования Azure Active Directory ( <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="4e88e-264">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="4e88e-265">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="4e88e-265">Security Reader</span></span>

- <span data-ttu-id="4e88e-266">Для Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="4e88e-266">For Exchange Online:</span></span>

  - <span data-ttu-id="4e88e-267">Управление организацией</span><span class="sxs-lookup"><span data-stu-id="4e88e-267">Organization Management</span></span>
  - <span data-ttu-id="4e88e-268">Управление организацией только с правом на просмотр</span><span class="sxs-lookup"><span data-stu-id="4e88e-268">View-Only Organization Management</span></span>
  - <span data-ttu-id="4e88e-269">Получатели только для чтения</span><span class="sxs-lookup"><span data-stu-id="4e88e-269">View-Only Recipients</span></span>
  - <span data-ttu-id="4e88e-270">Управление соответствием требованиям</span><span class="sxs-lookup"><span data-stu-id="4e88e-270">Compliance Management</span></span>

<span data-ttu-id="4e88e-271">Дополнительные информацию о ролях и разрешениях см. в следующих ресурсах:</span><span class="sxs-lookup"><span data-stu-id="4e88e-271">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="4e88e-272">Разрешения на портале Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4e88e-272">Permissions in the Microsoft 365 Defender portal</span></span>](permissions-microsoft-365-security-center.md)
- [<span data-ttu-id="4e88e-273">Разрешения компонентов в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4e88e-273">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)
- [<span data-ttu-id="4e88e-274">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e88e-274">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a><span data-ttu-id="4e88e-275">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="4e88e-275">More information</span></span>

- [<span data-ttu-id="4e88e-276">Поиск и изучение доставленной нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="4e88e-276">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md) 
- [<span data-ttu-id="4e88e-277">Просмотр вредоносных файлов, обнаруженных в SharePoint Online, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4e88e-277">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md) 
- [<span data-ttu-id="4e88e-278">Обзор представлений в Обозревателе угроз (и обнаружения в режиме реального времени)</span><span class="sxs-lookup"><span data-stu-id="4e88e-278">Get an overview of the views in Threat Explorer (and Real-time detections)</span></span>](threat-explorer-views.md) 
- <span data-ttu-id="4e88e-279">[отчет о состоянии защиты от угроз](view-email-security-reports.md#threat-protection-status-report);</span><span class="sxs-lookup"><span data-stu-id="4e88e-279">[Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span> 
- [<span data-ttu-id="4e88e-280">Автоматизированный анализ угроз и реакция на угрозы в службе защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="4e88e-280">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md) 
- [<span data-ttu-id="4e88e-281">Изучение сообщений электронной почты на странице Сущности электронной почты</span><span class="sxs-lookup"><span data-stu-id="4e88e-281">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)