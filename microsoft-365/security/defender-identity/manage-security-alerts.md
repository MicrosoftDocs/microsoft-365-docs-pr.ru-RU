---
title: Microsoft Defender для оповещений о безопасности удостоверений в Microsoft 365 Defender
description: Узнайте, как управлять и пересматривать оповещения о безопасности, выданные Microsoft Defender для удостоверений в Microsoft 365 Defender
ms.date: 05/20/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.openlocfilehash: c81f14b92b285359bda7e291bd8d3a8b636ae54d
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228967"
---
# <a name="defender-for-identity-security-alerts-in-microsoft-365-defender"></a><span data-ttu-id="0db34-103">Defender for Identity security alerts in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0db34-103">Defender for Identity security alerts in Microsoft 365 Defender</span></span>

<span data-ttu-id="0db34-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="0db34-104">**Applies to:**</span></span>

- <span data-ttu-id="0db34-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0db34-105">Microsoft 365 Defender</span></span>
- <span data-ttu-id="0db34-106">Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="0db34-106">Defender for Identity</span></span>

<span data-ttu-id="0db34-107">В этой статье рассказывается об основах работы с оповещений [microsoft Defender](/defender-for-identity) для безопасности удостоверений в центре Microsoft 365 [безопасности.](/microsoft-365/security/defender/overview-security-center)</span><span class="sxs-lookup"><span data-stu-id="0db34-107">This article explains the basics of how to work with [Microsoft Defender for Identity](/defender-for-identity) security alerts in the [Microsoft 365 security center](/microsoft-365/security/defender/overview-security-center).</span></span>

<span data-ttu-id="0db34-108">Оповещения Defender for Identity встроены в [](https://security.microsoft.com) центр безопасности Microsoft 365 с выделенным форматом страницы оповещения о удостоверениях.</span><span class="sxs-lookup"><span data-stu-id="0db34-108">Defender for Identity alerts are natively integrated into the [Microsoft 365 security center](https://security.microsoft.com) with a dedicated Identity alert page format.</span></span> <span data-ttu-id="0db34-109">Это первый шаг на пути к внедрению полного [опыта Microsoft Defender для удостоверений](/defender-for-identity/defender-for-identity-in-microsoft-365-defender)в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="0db34-109">This marks the first step in the journey to [introduce the full Microsoft Defender for Identity experience into Microsoft 365 Defender](/defender-for-identity/defender-for-identity-in-microsoft-365-defender).</span></span>

<span data-ttu-id="0db34-110">Новая страница оповещения о удостоверениях позволяет клиентам Microsoft Defender для удостоверений лучше обогатить сигналы меж домена и новые возможности автоматического ответа на запросы удостоверений.</span><span class="sxs-lookup"><span data-stu-id="0db34-110">The new Identity alert page gives Microsoft Defender for Identity customers better cross-domain signal enrichment and new automated identity response capabilities.</span></span> <span data-ttu-id="0db34-111">Это гарантирует безопасность и повышает эффективность операций безопасности.</span><span class="sxs-lookup"><span data-stu-id="0db34-111">It ensures that you stay secure and helps improve the efficiency of your security operations.</span></span>

<span data-ttu-id="0db34-112">Одно из преимуществ проверки оповещений через [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) в том, что оповещений Microsoft Defender для удостоверений дополнительно соотносится с информацией, полученной от каждого из других продуктов пакета.</span><span class="sxs-lookup"><span data-stu-id="0db34-112">One of the benefits of investigating alerts through [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) is that Microsoft Defender for Identity alerts are further correlated with information obtained from each of the other products in the suite.</span></span> <span data-ttu-id="0db34-113">Эти расширенные оповещений соответствуют другим форматам Microsoft 365 Defender, возникающим из [Microsoft Defender для](/microsoft-365/security/office-365-security) Office 365 и Microsoft Defender для [конечной точки.](/microsoft-365/security/defender-endpoint)</span><span class="sxs-lookup"><span data-stu-id="0db34-113">These enhanced alerts are consistent with the other Microsoft 365 Defender alert formats originating from [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security) and [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span></span> <span data-ttu-id="0db34-114">Новая страница эффективно устраняет необходимость переходить на другой портал продуктов для проверки оповещений, связанных с удостоверением.</span><span class="sxs-lookup"><span data-stu-id="0db34-114">The new page effectively eliminates the need to navigate to another product portal to investigate alerts associated with identity.</span></span>

<span data-ttu-id="0db34-115">Оповещения, возникающие из Defender for Identity, теперь могут запускать возможности автоматического Microsoft 365 Defender и [реагирования(AIR),](/microsoft-365/security/defender/m365d-autoir) включая автоматическое исправление оповещений и смягчение инструментов и процессов, которые могут способствовать подозрительной активности.</span><span class="sxs-lookup"><span data-stu-id="0db34-115">Alerts originating from Defender for Identity can now trigger the [Microsoft 365 Defender automated investigation and response (AIR)](/microsoft-365/security/defender/m365d-autoir) capabilities, including automatically remediating alerts and the mitigation of tools and processes that can contribute to the suspicious activity.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0db34-116">В рамках сближения с Microsoft 365 Defender некоторые параметры и сведения изменились с их расположения на портале Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="0db34-116">As part of the convergence with Microsoft 365 Defender, some options and details have changed from their location in the Defender for Identity portal.</span></span> <span data-ttu-id="0db34-117">Подробные сведения см. ниже, чтобы узнать, где найти знакомые и новые функции.</span><span class="sxs-lookup"><span data-stu-id="0db34-117">Please read the details below to discover where to find both the familiar and new features.</span></span>

## <a name="review-security-alerts"></a><span data-ttu-id="0db34-118">Просмотр оповещений о безопасности</span><span class="sxs-lookup"><span data-stu-id="0db34-118">Review security alerts</span></span>

<span data-ttu-id="0db34-119">Оповещения можно получить из нескольких местоположений, включая страницу **Оповещения,** страницу **Инциденты,** страницы отдельных устройств **и** страницу **расширенный** поиск.</span><span class="sxs-lookup"><span data-stu-id="0db34-119">Alerts can be accessed from multiple locations, including the **Alerts** page, the **Incidents** page, the pages of individual **Devices**, and from the **Advanced hunting** page.</span></span> <span data-ttu-id="0db34-120">В этом примере мы просмотрите страницу **Оповещений.**</span><span class="sxs-lookup"><span data-stu-id="0db34-120">In this example, we'll review the **Alerts page**.</span></span>

<span data-ttu-id="0db34-121">В центре [Microsoft 365 безопасности](https://security.microsoft.com/)перейдите  к & оповещениям, а затем к **оповещений.**</span><span class="sxs-lookup"><span data-stu-id="0db34-121">In the [Microsoft 365 security center](https://security.microsoft.com/), go to **Incidents & alerts** and then to **Alerts**.</span></span>

![Перейдите к инцидентам и оповещениям, а затем оповещений](../../media/defender-identity/incidents-alerts.png)

<span data-ttu-id="0db34-123">Чтобы увидеть оповещения из Defender для удостоверения, в правом  верхнем справа выберите **фильтр,** а затем в источниках служб выберите **Microsoft Defender для identity** и выберите **Apply**:</span><span class="sxs-lookup"><span data-stu-id="0db34-123">To see alerts from Defender for Identity, on the top-right select **Filter**, and then under **Service sources** select **Microsoft Defender for Identity**, and select **Apply**:</span></span>

![Фильтр событий Defender для удостоверений](../../media/defender-identity/filter-defender-for-identity.png)

<span data-ttu-id="0db34-125">Оповещений отображаются с информацией в следующих столбцах: Имя оповещения **,** Теги **,** Серьезность **,** Состояние исследования **,** Состояние **,** Категория **,** Источник обнаружения **,** Влияние активов **,** Первая деятельность , и последняя **активность**.</span><span class="sxs-lookup"><span data-stu-id="0db34-125">The alerts are displayed with information in the following columns: **Alert name**, **Tags**, **Severity**, **Investigation state**, **Status**, **Category**, **Detection source**, **Impacted assets**, **First activity**, and **Last activity**.</span></span>

![События Defender for Identity](../../media/defender-identity/filtered-alerts.png)

## <a name="manage-alerts"></a><span data-ttu-id="0db34-127">Управление оповещениями</span><span class="sxs-lookup"><span data-stu-id="0db34-127">Manage alerts</span></span>

<span data-ttu-id="0db34-128">Если вы нажмете имя **Оповещения** для одного из оповещений, вы перейдите на страницу с подробными сведениями о оповещении.</span><span class="sxs-lookup"><span data-stu-id="0db34-128">If you click the **Alert name** for one of the alerts, you'll go to the page with details about the alert.</span></span> <span data-ttu-id="0db34-129">В левой области вы увидите сводку о том, что **произошло:**</span><span class="sxs-lookup"><span data-stu-id="0db34-129">In the left pane, you'll see a summary of **What happened**:</span></span>

![Что произошло в оповещении](../../media/defender-identity/what-happened.png)

<span data-ttu-id="0db34-131">Над **полем What happened** находятся кнопки для  **учетных** записей, **хост назначения** и источник оповещения.</span><span class="sxs-lookup"><span data-stu-id="0db34-131">Above the **What happened** box are buttons for the **Accounts**, **Destination Host** and **Source Host** of the alert.</span></span> <span data-ttu-id="0db34-132">Для других оповещений можно увидеть кнопки для получения сведений о дополнительных хостах, учетных записях, IP-адресах, доменах и группах безопасности.</span><span class="sxs-lookup"><span data-stu-id="0db34-132">For other alerts, you might see buttons for details about additional hosts, accounts, IP addresses, domains, and security groups.</span></span> <span data-ttu-id="0db34-133">Выберите любой из них, чтобы получить дополнительные сведения о участвующих сущностях.</span><span class="sxs-lookup"><span data-stu-id="0db34-133">Select any of them to get more details about the entities involved.</span></span>

<span data-ttu-id="0db34-134">На правой области вы увидите сведения **оповещений.**</span><span class="sxs-lookup"><span data-stu-id="0db34-134">On the right pane, you'll see the **Alert details**.</span></span> <span data-ttu-id="0db34-135">Здесь вы можете увидеть дополнительные сведения и выполнить несколько задач:</span><span class="sxs-lookup"><span data-stu-id="0db34-135">Here you can see more details and perform several tasks:</span></span>

- <span data-ttu-id="0db34-136">**Классифицировать это** оповещение . Здесь вы можете назначить это оповещение как **true alert** или False **alert**</span><span class="sxs-lookup"><span data-stu-id="0db34-136">**Classify this alert** - Here you can designate this alert as a **True alert** or **False alert**</span></span>

    ![Классификация оповещений](../../media/defender-identity/classify-alert.png)

- <span data-ttu-id="0db34-138">**Состояние оповещений** . **В заданной** классификации можно классифицировать оповещение как **True** или **False**.</span><span class="sxs-lookup"><span data-stu-id="0db34-138">**Alert state** - In **Set Classification**, you can classify the alert as **True** or **False**.</span></span> <span data-ttu-id="0db34-139">В **назначенном для** вас оповещении можно назначить или отозначить его.</span><span class="sxs-lookup"><span data-stu-id="0db34-139">In **Assigned to**, you can assign the alert to yourself or unassign it.</span></span>

    ![Состояние оповещений](../../media/defender-identity/alert-state.png)

- <span data-ttu-id="0db34-141"> Сведения об оповещении . Дополнительные сведения о конкретном оповещении можно найти, перейдите по ссылке на документацию о типе оповещения, узнайте, с какой инцидент связан оповещение, просмотрите все автоматические расследования, связанные с этим типом оповещения, а также посмотрите, с чем связаны устройства и пользователи.</span><span class="sxs-lookup"><span data-stu-id="0db34-141">**Alert details** - Under **Alert details**, you can find more information about the specific alert, follow a link to documentation about the type of alert, see which incident the alert is associated with, review any automated investigations linked to this alert type, and see the impacted devices and users.</span></span>

    ![Сведения об оповещении](../../media/defender-identity/alert-details.png)

- <span data-ttu-id="0db34-143">**Комментарии &** истории . Здесь вы можете добавить свои комментарии в оповещение и увидеть историю всех действий, связанных с оповещением.</span><span class="sxs-lookup"><span data-stu-id="0db34-143">**Comments & history** - Here you can add your comments to the alert, and see the history of all actions associated with the alert.</span></span>

    ![Комментарии и история](../../media/defender-identity/comments-history.png)

- <span data-ttu-id="0db34-145">**Управление** оповещением . Если вы выберите **Управление** оповещением, вы перейдите на области, которая позволит вам изменить:</span><span class="sxs-lookup"><span data-stu-id="0db34-145">**Manage alert** - If you select **Manage alert**, you'll go to a pane that will allow you to edit the:</span></span>
  - <span data-ttu-id="0db34-146">**Состояние** — вы можете выбрать **New,** **Resolved** или **In Progress.**</span><span class="sxs-lookup"><span data-stu-id="0db34-146">**Status** - You can choose **New**, **Resolved** or **In progress**.</span></span>
  - <span data-ttu-id="0db34-147">**Классификация** . Вы можете выбрать **True alert** или **False alert**.</span><span class="sxs-lookup"><span data-stu-id="0db34-147">**Classification** - You can choose **True alert** or **False alert**.</span></span>
  - <span data-ttu-id="0db34-148">**Комментарий** . Вы можете добавить комментарий о оповещении.</span><span class="sxs-lookup"><span data-stu-id="0db34-148">**Comment** - You can add a comment about the alert.</span></span>

    <span data-ttu-id="0db34-149">Если вы выберите три точки рядом с управлением оповещением, вы можете проконсультироваться с экспертом по угрозам, экспортировать оповещение в файл Excel или ссылку на **другой инцидент**.   </span><span class="sxs-lookup"><span data-stu-id="0db34-149">If you select the three dots next to **Manage alert**, you can **Consult a threat expert**, **Export** the alert to an Excel file, or **Link to another incident**.</span></span>

    ![Управление оповещением](../../media/defender-identity/manage-alert.png)

    > [!NOTE]
    > <span data-ttu-id="0db34-151">В файле Excel теперь доступны две ссылки: Просмотр в **Microsoft Defender** для удостоверений и просмотр **в Microsoft 365 Defender**.</span><span class="sxs-lookup"><span data-stu-id="0db34-151">In the Excel file, you now have two links available: **View in Microsoft Defender for Identity** and **View in Microsoft 365 Defender**.</span></span> <span data-ttu-id="0db34-152">Каждая ссылка приведет вас на соответствующий портал и предоставит сведения о оповещении.</span><span class="sxs-lookup"><span data-stu-id="0db34-152">Each link will bring you to the relevant portal, and provide information about the alert there.</span></span>

## <a name="see-also"></a><span data-ttu-id="0db34-153">См. также</span><span class="sxs-lookup"><span data-stu-id="0db34-153">See also</span></span>

- [<span data-ttu-id="0db34-154">Изучение оповещений в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0db34-154">Investigate alerts in Microsoft 365 Defender</span></span>](../defender/investigate-alerts.md)
