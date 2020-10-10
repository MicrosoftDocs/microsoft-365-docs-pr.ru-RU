---
title: Сведения и результаты автоматического исследования
description: Во время и после автоматического исследования вы можете просматривать результаты и основные выводы
keywords: автоматически, исследование, результаты, анализ, сведения, исправление, автоматизированный анализ угроз и реакция на них
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.openlocfilehash: 96fa036d3154b15499303623efe027e4d340c98a
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413630"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="3ecac-104">Сведения и результаты автоматического исследования</span><span class="sxs-lookup"><span data-stu-id="3ecac-104">Details and results of an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3ecac-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3ecac-105">**Applies to:**</span></span>
- <span data-ttu-id="3ecac-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="3ecac-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="3ecac-107">При проведении автоматического исследования в службе защиты от угроз (Майкрософт) сведения о нем доступны во время и после автоматического исследования.</span><span class="sxs-lookup"><span data-stu-id="3ecac-107">When an automated investigation occurs in Microsoft Threat Protection, details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="3ecac-108">Если у вас есть [необходимые разрешения](mtp-action-center.md#required-permissions-for-action-center-tasks), вы можете просмотреть эти подробности в представлении со сведениями об исследовании.</span><span class="sxs-lookup"><span data-stu-id="3ecac-108">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="3ecac-109">В представлении со сведениями об исследовании содержится актуальное состояние и можно утвердить ожидающие действия.</span><span class="sxs-lookup"><span data-stu-id="3ecac-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![Сведения об исследовании](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="3ecac-111">Открытие представления со сведениями об исследовании</span><span class="sxs-lookup"><span data-stu-id="3ecac-111">Open the investigation details view</span></span>

<span data-ttu-id="3ecac-112">Чтобы открыть представление со сведениями об исследовании, можно использовать один из указанных ниже способов.</span><span class="sxs-lookup"><span data-stu-id="3ecac-112">You can open the investigation details view by using one of the following methods:</span></span>
- [<span data-ttu-id="3ecac-113">Выбор элемента в центре уведомлений</span><span class="sxs-lookup"><span data-stu-id="3ecac-113">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="3ecac-114">Выбор исследования на странице сведений об инциденте</span><span class="sxs-lookup"><span data-stu-id="3ecac-114">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="3ecac-115">Выбор элемента в центре уведомлений</span><span class="sxs-lookup"><span data-stu-id="3ecac-115">Select an item in the Action center</span></span>

<span data-ttu-id="3ecac-116">В центре уведомлений можно просмотреть действия, ожидающие утверждения (на вкладке **Ожидание**), или утвержденные действия (на вкладке **Журнал**).</span><span class="sxs-lookup"><span data-stu-id="3ecac-116">Use the Action center to view actions that are either pending approval (on the **Pending** tab) or were already approved (on the **History** tab).</span></span> 

1. <span data-ttu-id="3ecac-117">Перейдите на страницу [https://security.microsoft.com](https://security.microsoft.com) и войдите.</span><span class="sxs-lookup"><span data-stu-id="3ecac-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="3ecac-118">В панели навигации щелкните **Центр уведомлений**.</span><span class="sxs-lookup"><span data-stu-id="3ecac-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="3ecac-119">На вкладке **Ожидание** или **Журнал** выберите элемент.</span><span class="sxs-lookup"><span data-stu-id="3ecac-119">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="3ecac-120">Если у вас есть [необходимые разрешения](mtp-action-center.md#required-permissions-for-action-center-tasks), вы можете утвердить (или отклонить) ожидающие действия.</span><span class="sxs-lookup"><span data-stu-id="3ecac-120">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can approve (or reject) pending actions.</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="3ecac-121">Открытие исследования на странице сведений об инциденте</span><span class="sxs-lookup"><span data-stu-id="3ecac-121">Open an investigation from an incident details page</span></span>

<span data-ttu-id="3ecac-122">На странице сведений об инциденте можно просмотреть подробные сведения об инциденте, включая инициированные предупреждения с информацией о любых затрагиваемых устройствах, учетных записях пользователей и почтовых ящиках.</span><span class="sxs-lookup"><span data-stu-id="3ecac-122">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="3ecac-123">Перейдите на страницу [https://security.microsoft.com](https://security.microsoft.com) и войдите.</span><span class="sxs-lookup"><span data-stu-id="3ecac-123">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="3ecac-124">В панели навигации щелкните **Инциденты**.</span><span class="sxs-lookup"><span data-stu-id="3ecac-124">In the navigation pane, choose **Incidents**.</span></span> 

3. <span data-ttu-id="3ecac-125">Выберите элемент в списке, чтобы открыть представление со сведениями об инциденте.</span><span class="sxs-lookup"><span data-stu-id="3ecac-125">Select an item in the list to open the incident details view.</span></span><br/>![Сведения об инциденте](../../media/mtp-incidentdetails-tabs.png)

4. <span data-ttu-id="3ecac-127">На вкладке **Исследования** выберите исследование из списка.</span><span class="sxs-lookup"><span data-stu-id="3ecac-127">On the **Investigations** tab, select an investigation in the list.</span></span>

## <a name="investigation-details"></a><span data-ttu-id="3ecac-128">Сведения об исследовании</span><span class="sxs-lookup"><span data-stu-id="3ecac-128">Investigation details</span></span>

<span data-ttu-id="3ecac-129">В представлении со сведениями об исследовании можно просмотреть прошлые, текущие и ожидающие действия, относящиеся к исследованию.</span><span class="sxs-lookup"><span data-stu-id="3ecac-129">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="3ecac-130">Представление со сведениями об исследовании выглядит примерно так:</span><span class="sxs-lookup"><span data-stu-id="3ecac-130">The investigation details view resembles the following image:</span></span>

![Сведения об исследовании](../../media/mtp-air-investdetails.png)

<span data-ttu-id="3ecac-132">В представлении со сведениями об исследовании можно просмотреть информацию на вкладках **Граф исследования**, **Оповещения**, **Устройства**, **Удостоверения**, **Основные выводы**, **Объекты**, **Журнал** и **Ожидающие выполнения действия**, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="3ecac-132">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

|<span data-ttu-id="3ecac-133">Вкладка</span><span class="sxs-lookup"><span data-stu-id="3ecac-133">Tab</span></span>    |<span data-ttu-id="3ecac-134">Описание</span><span class="sxs-lookup"><span data-stu-id="3ecac-134">Description</span></span> |
|--------|--------|
|<span data-ttu-id="3ecac-135">Граф исследования</span><span class="sxs-lookup"><span data-stu-id="3ecac-135">Investigation graph</span></span>    |<span data-ttu-id="3ecac-136">Визуальное представление исследования.</span><span class="sxs-lookup"><span data-stu-id="3ecac-136">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="3ecac-137">Описывает сущности и перечисляет обнаруженные угрозы, содержит оповещения и указывает на наличие действий, ожидающих утверждения.</span><span class="sxs-lookup"><span data-stu-id="3ecac-137">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="3ecac-138">Для просмотра дополнительных сведений можно щелкнуть элемент на диаграмме.</span><span class="sxs-lookup"><span data-stu-id="3ecac-138">You can click an item on the graph to view more details.</span></span> <span data-ttu-id="3ecac-139">Например, щелкнув значок **Обнаруженные угрозы** вы перейдете на вкладку **Основные выводы**.</span><span class="sxs-lookup"><span data-stu-id="3ecac-139">For example, clicking the **Threats found** icon takes you to the **Key findings** tab.</span></span> |
|<span data-ttu-id="3ecac-140">Оповещения</span><span class="sxs-lookup"><span data-stu-id="3ecac-140">Alerts</span></span> |<span data-ttu-id="3ecac-141">Содержит список оповещений, связанных с исследованием.</span><span class="sxs-lookup"><span data-stu-id="3ecac-141">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="3ecac-142">Оповещения могут поступать из функций защиты от угроз на компьютере пользователя, приложений Office, Cloud App Security и других компонентов защиты от угроз в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3ecac-142">Alerts can come from threat protection features on a user's machine, in Office apps, Cloud App Security, and other Microsoft 365 Threat Protection features.</span></span>|
|<span data-ttu-id="3ecac-143">Устройства</span><span class="sxs-lookup"><span data-stu-id="3ecac-143">Devices</span></span>|<span data-ttu-id="3ecac-144">Содержит список компьютеров, включенных в исследование, а также уровень исправления.</span><span class="sxs-lookup"><span data-stu-id="3ecac-144">Lists machines included in the investigation along with remediation level.</span></span>|
|<span data-ttu-id="3ecac-145">Основные выводы</span><span class="sxs-lookup"><span data-stu-id="3ecac-145">Key findings</span></span>   |<span data-ttu-id="3ecac-146">Содержит список результатов исследования, а также состояние и выполненные или ожидающие действия.</span><span class="sxs-lookup"><span data-stu-id="3ecac-146">Lists results from the investigation along with status and actions taken or pending.</span></span> <span data-ttu-id="3ecac-147">На этой вкладке можно утвердить ожидающие действия для устройств и удостоверений.</span><span class="sxs-lookup"><span data-stu-id="3ecac-147">You can approve pending actions for devices and identities in on this tab.</span></span>|
|<span data-ttu-id="3ecac-148">Объекты</span><span class="sxs-lookup"><span data-stu-id="3ecac-148">Entities</span></span>   |<span data-ttu-id="3ecac-149">Содержит список действий пользователей, файлов, процессов, служб, драйверов, IP-адресов и методов сохранения, связанных с исследованием, а также состояние и выполненные действия.</span><span class="sxs-lookup"><span data-stu-id="3ecac-149">Lists user activities, files, processes, services, drivers, IP addresses, and persistence methods associated with the investigation, along with status and actions taken.</span></span>|
|<span data-ttu-id="3ecac-150">Журнал</span><span class="sxs-lookup"><span data-stu-id="3ecac-150">Log</span></span>    |<span data-ttu-id="3ecac-151">Содержите подробное представление всех действий, выполненных в ходе исследования, и сведения о состоянии.</span><span class="sxs-lookup"><span data-stu-id="3ecac-151">Provides a detailed view of all steps taken during the investigation, along with status.</span></span>|
|<span data-ttu-id="3ecac-152">Ожидающие выполнения действия</span><span class="sxs-lookup"><span data-stu-id="3ecac-152">Pending actions</span></span>    |<span data-ttu-id="3ecac-153">Содержит список элементов, требующих утверждения для продолжения.</span><span class="sxs-lookup"><span data-stu-id="3ecac-153">Lists items that require approval to proceed.</span></span>|

## <a name="next-steps"></a><span data-ttu-id="3ecac-154">Дальнейшие действия:</span><span class="sxs-lookup"><span data-stu-id="3ecac-154">Next steps</span></span>

- [<span data-ttu-id="3ecac-155">Утверждение или отклонение действий, относящихся к автоматизированному анализу угроз и реакции на угрозы</span><span class="sxs-lookup"><span data-stu-id="3ecac-155">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)

