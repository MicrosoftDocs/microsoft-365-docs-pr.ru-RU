---
title: Сведения и результаты автоматического расследования
description: Просмотр результатов и ключевых результатов автоматического расследования в Microsoft 365 Defender
keywords: автоматически, исследование, результаты, анализ, сведения, исправление, автоматизированный анализ угроз и реакция на них
search.appverid: met150
ms.prod: m365-security
ms.technology: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: 9ee2f0402e8cfd184e59dce5a382f835b706d6aa
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022573"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="e09e6-104">Сведения и результаты автоматического расследования</span><span class="sxs-lookup"><span data-stu-id="e09e6-104">Details and results of an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e09e6-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e09e6-105">**Applies to:**</span></span>
- <span data-ttu-id="e09e6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e09e6-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e09e6-107">С Microsoft 365 Defender, когда запускается автоматическое расследование, сведения об этом расследовании доступны как во время, так и после автоматизированного процесса расследования. [](m365d-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="e09e6-107">With Microsoft 365 Defender, when an [automated investigation](m365d-autoir.md) runs, details about that investigation are available both during and after the automated investigation process.</span></span> <span data-ttu-id="e09e6-108">Если у вас есть [необходимые разрешения](m365d-action-center.md#required-permissions-for-action-center-tasks), вы можете просмотреть эти подробности в представлении со сведениями об исследовании.</span><span class="sxs-lookup"><span data-stu-id="e09e6-108">If you have the [necessary permissions](m365d-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="e09e6-109">Это представление предоставляет вам состояние в курсе и возможность утверждать любые ожидающих действий.</span><span class="sxs-lookup"><span data-stu-id="e09e6-109">This view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

:::image type="content" source="../../media/mtp-air-investdetails.png" alt-text="Сведения об анализе":::

## <a name="new-unified-investigation-page"></a><span data-ttu-id="e09e6-111">(NEW!) Страница Единое исследование</span><span class="sxs-lookup"><span data-stu-id="e09e6-111">(NEW!) Unified investigation page</span></span>

<span data-ttu-id="e09e6-112">Страница расследования недавно была обновлена, чтобы включить сведения на устройствах, электронной почте и совместном контенте.</span><span class="sxs-lookup"><span data-stu-id="e09e6-112">The investigation page has recently been updated to include information across your devices, email, and collaboration content.</span></span> <span data-ttu-id="e09e6-113">Новая унифицированная страница исследования определяет общий язык и предоставляет унифицированный опыт для автоматических расследований в [Microsoft Defender для конечной](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) точки и [Microsoft Defender для Office 365](../office-365-security/defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="e09e6-113">The new, unified investigation page defines a common language and provides a unified experience for automatic investigations across [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) and [Microsoft Defender for Office 365](../office-365-security/defender-for-office-365.md).</span></span> <span data-ttu-id="e09e6-114">Чтобы получить доступ к единой странице расследования, выберите ссылку в желтом баннере, который вы увидите на:</span><span class="sxs-lookup"><span data-stu-id="e09e6-114">To access the unified investigation page, select the link in the yellow banner you'll see on:</span></span>

- <span data-ttu-id="e09e6-115">Любая страница расследования в центре Office 365 безопасности & соответствия требованиям ( [https://protection.office.com](https://protection.office.com) )</span><span class="sxs-lookup"><span data-stu-id="e09e6-115">Any investigation page in the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com))</span></span>
- <span data-ttu-id="e09e6-116">Любая страница расследования в Центр безопасности в Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) )</span><span class="sxs-lookup"><span data-stu-id="e09e6-116">Any investigation page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com))</span></span>
- <span data-ttu-id="e09e6-117">Любой инцидент или опыт центра действий на Microsoft 365 Defender портале ( [https://security.microsoft.com](https://security.microsoft.com) )</span><span class="sxs-lookup"><span data-stu-id="e09e6-117">Any incident or Action center experience in the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com))</span></span>

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="e09e6-118">Открытие представления со сведениями об исследовании</span><span class="sxs-lookup"><span data-stu-id="e09e6-118">Open the investigation details view</span></span>

<span data-ttu-id="e09e6-119">Чтобы открыть представление со сведениями об исследовании, можно использовать один из указанных ниже способов.</span><span class="sxs-lookup"><span data-stu-id="e09e6-119">You can open the investigation details view by using one of the following methods:</span></span>

- [<span data-ttu-id="e09e6-120">Выбор элемента в центре уведомлений</span><span class="sxs-lookup"><span data-stu-id="e09e6-120">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="e09e6-121">Выбор исследования на странице сведений об инциденте</span><span class="sxs-lookup"><span data-stu-id="e09e6-121">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="e09e6-122">Выбор элемента в центре уведомлений</span><span class="sxs-lookup"><span data-stu-id="e09e6-122">Select an item in the Action center</span></span>

<span data-ttu-id="e09e6-123">Улучшенный центр [действий](m365d-action-center.md) () объединяет действия по исправлению на ваших устройствах, & контента совместной работы и [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) удостоверений. [](m365d-remediation-actions.md)</span><span class="sxs-lookup"><span data-stu-id="e09e6-123">The improved [Action center](m365d-action-center.md) ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) brings together [remediation actions](m365d-remediation-actions.md) across your devices, email & collaboration content, and identities.</span></span> <span data-ttu-id="e09e6-124">Перечисленные действия включают действия по исправлению, которые были предприняты автоматически или вручную.</span><span class="sxs-lookup"><span data-stu-id="e09e6-124">Listed actions include remediation actions that were taken automatically or manually.</span></span> <span data-ttu-id="e09e6-125">В центре действий можно просмотреть действия, ожидающие утверждения, и действия, которые уже утверждены или завершены.</span><span class="sxs-lookup"><span data-stu-id="e09e6-125">In the Action center, you can view actions that are awaiting approval and actions that were already approved or completed.</span></span> <span data-ttu-id="e09e6-126">Вы также можете перейти к более подробным сведениям, например к странице расследования.</span><span class="sxs-lookup"><span data-stu-id="e09e6-126">You can also navigate to more details, such as an investigation page.</span></span>

> [!TIP]
> <span data-ttu-id="e09e6-127">У вас должны [быть определенные разрешения на](m365d-action-center.md#required-permissions-for-action-center-tasks) утверждение, отклонение или отмену действий.</span><span class="sxs-lookup"><span data-stu-id="e09e6-127">You must have [certain permissions](m365d-action-center.md#required-permissions-for-action-center-tasks) to approve, reject, or undo actions.</span></span>

1. <span data-ttu-id="e09e6-128">Перейдите на страницу [https://security.microsoft.com](https://security.microsoft.com) и войдите.</span><span class="sxs-lookup"><span data-stu-id="e09e6-128">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="e09e6-129">В панели навигации щелкните **Центр уведомлений**.</span><span class="sxs-lookup"><span data-stu-id="e09e6-129">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="e09e6-130">На вкладке **Ожидание** или **Журнал** выберите элемент.</span><span class="sxs-lookup"><span data-stu-id="e09e6-130">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="e09e6-131">Откроется его поле для вылетов.</span><span class="sxs-lookup"><span data-stu-id="e09e6-131">Its flyout pane opens.</span></span>

4. <span data-ttu-id="e09e6-132">Просмотрите сведения в области вылетов и примите один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="e09e6-132">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="e09e6-133">Выберите **страницу Open investigation,** чтобы просмотреть дополнительные сведения о расследовании.</span><span class="sxs-lookup"><span data-stu-id="e09e6-133">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="e09e6-134">Выберите **Утверждение,** чтобы инициировать ожидающих действий.</span><span class="sxs-lookup"><span data-stu-id="e09e6-134">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="e09e6-135">Выберите **Отклонение,** чтобы предотвратить ожидающих действий.</span><span class="sxs-lookup"><span data-stu-id="e09e6-135">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="e09e6-136">Выберите **go hunt,** чтобы перейти в [расширенный поиск.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e09e6-136">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="e09e6-137">Открытие исследования на странице сведений об инциденте</span><span class="sxs-lookup"><span data-stu-id="e09e6-137">Open an investigation from an incident details page</span></span>

<span data-ttu-id="e09e6-138">На странице сведений об инциденте можно просмотреть подробные сведения об инциденте, включая инициированные предупреждения с информацией о любых затрагиваемых устройствах, учетных записях пользователей и почтовых ящиках.</span><span class="sxs-lookup"><span data-stu-id="e09e6-138">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="e09e6-139">Перейдите на страницу [https://security.microsoft.com](https://security.microsoft.com) и войдите.</span><span class="sxs-lookup"><span data-stu-id="e09e6-139">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="e09e6-140">В области навигации выберите **Инциденты & оповещений**  >  **Об инцидентах**.</span><span class="sxs-lookup"><span data-stu-id="e09e6-140">In the navigation pane, choose **Incidents & alerts** > **Incidents**.</span></span> 

3. <span data-ttu-id="e09e6-141">Выберите элемент в списке, а затем выберите страницу **Открытый инцидент**.</span><span class="sxs-lookup"><span data-stu-id="e09e6-141">Select an item in the list, and then choose **Open incident page**.</span></span>

4. <span data-ttu-id="e09e6-142">Выберите **вкладку Исследования** и выберите исследование в списке.</span><span class="sxs-lookup"><span data-stu-id="e09e6-142">Select the **Investigations** tab, and then select an investigation in the list.</span></span> <span data-ttu-id="e09e6-143">Откроется его поле для вылетов.</span><span class="sxs-lookup"><span data-stu-id="e09e6-143">Its flyout pane opens.</span></span>

5. <span data-ttu-id="e09e6-144">Выберите **страницу Open investigation**.</span><span class="sxs-lookup"><span data-stu-id="e09e6-144">Select **Open investigation page**.</span></span> 

<span data-ttu-id="e09e6-145">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="e09e6-145">Here's an example.</span></span>

:::image type="content" source="../../media/mtp-incidentdetails-tabs.png" alt-text="Сведения об инциденте":::

## <a name="investigation-details"></a><span data-ttu-id="e09e6-147">Сведения об исследовании</span><span class="sxs-lookup"><span data-stu-id="e09e6-147">Investigation details</span></span>

<span data-ttu-id="e09e6-148">В представлении со сведениями об исследовании можно просмотреть прошлые, текущие и ожидающие действия, относящиеся к исследованию.</span><span class="sxs-lookup"><span data-stu-id="e09e6-148">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="e09e6-149">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="e09e6-149">Here's an example.</span></span>

:::image type="content" source="../../media/mtp-air-investdetails.png" alt-text="Сведения об исследовании":::

<span data-ttu-id="e09e6-151">В представлении со сведениями об исследовании можно просмотреть информацию на вкладках **Граф исследования**, **Оповещения**, **Устройства**, **Удостоверения**, **Основные выводы**, **Объекты**, **Журнал** и **Ожидающие выполнения действия**, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="e09e6-151">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="e09e6-152">Конкретные вкладки, которые вы видите на странице сведений о расследовании, зависят от того, что включает подписка.</span><span class="sxs-lookup"><span data-stu-id="e09e6-152">The specific tabs you see in an investigation details page depends on what your subscription includes.</span></span> <span data-ttu-id="e09e6-153">Например, если подписка не включает Microsoft Defender для Office 365 плана 2, вкладка **почтовых ящиков не будет.**</span><span class="sxs-lookup"><span data-stu-id="e09e6-153">For example, if your subscription does not include Microsoft Defender for Office 365 Plan 2, you won't see a **Mailboxes** tab.</span></span>

| <span data-ttu-id="e09e6-154">Вкладка</span><span class="sxs-lookup"><span data-stu-id="e09e6-154">Tab</span></span> | <span data-ttu-id="e09e6-155">Описание</span><span class="sxs-lookup"><span data-stu-id="e09e6-155">Description</span></span> |
|:--------|:--------|
| <span data-ttu-id="e09e6-156">**Граф исследования**</span><span class="sxs-lookup"><span data-stu-id="e09e6-156">**Investigation graph**</span></span>   | <span data-ttu-id="e09e6-157">Визуальное представление исследования.</span><span class="sxs-lookup"><span data-stu-id="e09e6-157">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="e09e6-158">Описывает сущности и перечисляет обнаруженные угрозы, содержит оповещения и указывает на наличие действий, ожидающих утверждения.</span><span class="sxs-lookup"><span data-stu-id="e09e6-158">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="e09e6-159">Чтобы просмотреть дополнительные сведения, можно выбрать элемент на графике.</span><span class="sxs-lookup"><span data-stu-id="e09e6-159">You can select an item on the graph to view more details.</span></span> <span data-ttu-id="e09e6-160">Например, при выборе значка **Evidence** вы будете на вкладке **Evidence,** где можно увидеть обнаруженные объекты и их вердикты.</span><span class="sxs-lookup"><span data-stu-id="e09e6-160">For example, selecting the **Evidence** icon takes you to the **Evidence** tab, where you can see detected entities and their verdicts.</span></span> |
| <span data-ttu-id="e09e6-161">**Alerts**</span><span class="sxs-lookup"><span data-stu-id="e09e6-161">**Alerts**</span></span>    | <span data-ttu-id="e09e6-162">Содержит список оповещений, связанных с исследованием.</span><span class="sxs-lookup"><span data-stu-id="e09e6-162">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="e09e6-163">Оповещения могут исходить из функций защиты от угроз на устройстве пользователя, в Office приложениях, Microsoft Cloud App Security и других Microsoft 365 Defender функций.</span><span class="sxs-lookup"><span data-stu-id="e09e6-163">Alerts can come from threat protection features on a user's device, in Office apps, Microsoft Cloud App Security, and other Microsoft 365 Defender features.</span></span>|
| <span data-ttu-id="e09e6-164">**Устройства**</span><span class="sxs-lookup"><span data-stu-id="e09e6-164">**Devices**</span></span> | <span data-ttu-id="e09e6-165">Списки устройств, включенных в исследование, а также их уровень исправлений.</span><span class="sxs-lookup"><span data-stu-id="e09e6-165">Lists devices included in the investigation along with their remediation level.</span></span> <span data-ttu-id="e09e6-166">(Уровни восстановления соответствуют уровню [автоматизации для групп устройств.)](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups)</span><span class="sxs-lookup"><span data-stu-id="e09e6-166">(Remediation levels correspond to [the automation level for device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups).)</span></span> |
| <span data-ttu-id="e09e6-167">**Почтовые ящики**</span><span class="sxs-lookup"><span data-stu-id="e09e6-167">**Mailboxes**</span></span> |<span data-ttu-id="e09e6-168">Списки почтовых ящиков, на которые влияют обнаруженные угрозы.</span><span class="sxs-lookup"><span data-stu-id="e09e6-168">Lists mailboxes that are impacted by detected threats.</span></span>  |
| <span data-ttu-id="e09e6-169">**Пользователи**</span><span class="sxs-lookup"><span data-stu-id="e09e6-169">**Users**</span></span>  | <span data-ttu-id="e09e6-170">Списки учетных записей пользователей, на которые влияют обнаруженные угрозы.</span><span class="sxs-lookup"><span data-stu-id="e09e6-170">Lists user accounts that are impacted by detected threats.</span></span> |
| <span data-ttu-id="e09e6-171">**Доказательства**</span><span class="sxs-lookup"><span data-stu-id="e09e6-171">**Evidence**</span></span> | <span data-ttu-id="e09e6-172">Списки доказательств, поднятые оповещений или расследований.</span><span class="sxs-lookup"><span data-stu-id="e09e6-172">Lists pieces of evidence raised by alerts or investigations.</span></span> <span data-ttu-id="e09e6-173">Включает вердикты *(вредоносные,* *подозрительные,* *неизвестные* или не найденные угрозы) и состояние исправлений.</span><span class="sxs-lookup"><span data-stu-id="e09e6-173">Includes verdicts (*Malicious*, *Suspicious*, *Unknown*, or *No threats found*) and remediation status.</span></span> |
| <span data-ttu-id="e09e6-174">**Entities**</span><span class="sxs-lookup"><span data-stu-id="e09e6-174">**Entities**</span></span>  | <span data-ttu-id="e09e6-175">Содержит сведения о каждой анализируемой сущности, включая вердикт для каждого типа сущности *(вредоносный,* подозрительный или не *найденный).*</span><span class="sxs-lookup"><span data-stu-id="e09e6-175">Provides details about each analyzed entity, including a verdict for each entity type (*Malicious*, *Suspicious*, or *No threats found*).</span></span>|
|<span data-ttu-id="e09e6-176">**Log**</span><span class="sxs-lookup"><span data-stu-id="e09e6-176">**Log**</span></span>    | <span data-ttu-id="e09e6-177">Предоставляет хронологическое, подробное представление всех действий по расследованию, принятых после срабатывного оповещения.</span><span class="sxs-lookup"><span data-stu-id="e09e6-177">Provides a chronological, detailed view of all the investigation actions taken after an alert was triggered.</span></span>|
| <span data-ttu-id="e09e6-178">**История ожидающих действий**</span><span class="sxs-lookup"><span data-stu-id="e09e6-178">**Pending actions history**</span></span> | <span data-ttu-id="e09e6-179">Содержит список элементов, требующих утверждения для продолжения.</span><span class="sxs-lookup"><span data-stu-id="e09e6-179">Lists items that require approval to proceed.</span></span> <span data-ttu-id="e09e6-180">Перейдите в Центр действий () для [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) утверждения ожидающих действий.</span><span class="sxs-lookup"><span data-stu-id="e09e6-180">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) to approve pending actions.</span></span> |

## <a name="next-steps"></a><span data-ttu-id="e09e6-181">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="e09e6-181">Next steps</span></span>

- [<span data-ttu-id="e09e6-182">Просмотр действий по исправлению и управление ими</span><span class="sxs-lookup"><span data-stu-id="e09e6-182">View and manage remediation actions</span></span>](m365d-autoir-actions.md)
- [<span data-ttu-id="e09e6-183">Дополнительные информацию о действиях по исправлению</span><span class="sxs-lookup"><span data-stu-id="e09e6-183">Learn more about remediation actions</span></span>](m365d-remediation-actions.md)
