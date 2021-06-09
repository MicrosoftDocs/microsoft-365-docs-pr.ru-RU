---
title: Исправление уязвимостей с помощью контроль угроз и уязвимостей
description: Устранение недостатков безопасности, обнаруженных с помощью рекомендаций по безопасности, и создание исключений при необходимости в контроль угроз и уязвимостей.
keywords: Исправление microsoft Defender для конечного твма, Microsoft Defender для endpoint tvm, контроль угроз и уязвимостей, угрозы & управление уязвимостями, устранение угрозы & управление уязвимостями, intune восстановления tvm, sccm восстановления tvm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 602a38d8ad27505e81628db265681ac89218e593
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840915"
---
# <a name="remediate-vulnerabilities-with-threat-and-vulnerability-management"></a><span data-ttu-id="af961-104">Исправление уязвимостей с помощью контроль угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="af961-104">Remediate vulnerabilities with threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="af961-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="af961-105">**Applies to:**</span></span>
- [<span data-ttu-id="af961-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="af961-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="af961-107">Угроза и управление уязвимостями</span><span class="sxs-lookup"><span data-stu-id="af961-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="af961-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="af961-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="af961-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="af961-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="af961-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="af961-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="request-remediation"></a><span data-ttu-id="af961-111">Запрос на исправление</span><span class="sxs-lookup"><span data-stu-id="af961-111">Request remediation</span></span>

<span data-ttu-id="af961-112">Возможности контроль угроз и уязвимостей в Microsoft Defender для конечной точки устраняют разрыв между администраторами безопасности и ИТ-службами с помощью рабочего процесса запроса на исправление.</span><span class="sxs-lookup"><span data-stu-id="af961-112">The threat and vulnerability management capability in Microsoft Defender for Endpoint bridges the gap between Security and IT administrators through the remediation request workflow.</span></span> <span data-ttu-id="af961-113">Администраторы безопасности, такие как вы, могут запрашивать у  ИТ-администратора исправление уязвимости со страниц рекомендаций по безопасности в Intune.</span><span class="sxs-lookup"><span data-stu-id="af961-113">Security admins like you can request for the IT Administrator to remediate a vulnerability from the **Security recommendation** pages to Intune.</span></span>

### <a name="enable-microsoft-intune-connection"></a><span data-ttu-id="af961-114">Включить Microsoft Intune подключение</span><span class="sxs-lookup"><span data-stu-id="af961-114">Enable Microsoft Intune connection</span></span>

<span data-ttu-id="af961-115">Чтобы использовать эту возможность, в Microsoft Intune подключений.</span><span class="sxs-lookup"><span data-stu-id="af961-115">To use this capability, enable your Microsoft Intune connections.</span></span> <span data-ttu-id="af961-116">В Центр безопасности в Microsoft Defender перейдите к **Параметры**  >  **общие**  >  **расширенные функции**.</span><span class="sxs-lookup"><span data-stu-id="af961-116">In the Microsoft Defender Security Center, navigate to **Settings** > **General** > **Advanced features**.</span></span> <span data-ttu-id="af961-117">Прокрутите вниз **и Microsoft Intune подключение.**</span><span class="sxs-lookup"><span data-stu-id="af961-117">Scroll down and look for **Microsoft Intune connection**.</span></span> <span data-ttu-id="af961-118">По умолчанию отключается тоггл.</span><span class="sxs-lookup"><span data-stu-id="af961-118">By default, the toggle is turned off.</span></span> <span data-ttu-id="af961-119">**Включите Microsoft Intune подключение.** </span><span class="sxs-lookup"><span data-stu-id="af961-119">Turn your **Microsoft Intune connection** toggle **On**.</span></span>

<span data-ttu-id="af961-120">**Примечание.** Если включено подключение Intune, можно создать задачу безопасности Intune при создании запроса на исправление.</span><span class="sxs-lookup"><span data-stu-id="af961-120">**Note**: If you have the Intune connection enabled, you get an option to create an Intune security task when creating a remediation request.</span></span> <span data-ttu-id="af961-121">Этот параметр не появится, если подключение не установлено.</span><span class="sxs-lookup"><span data-stu-id="af961-121">This option does not appear if the connection is not set.</span></span>

<span data-ttu-id="af961-122">Подробные сведения см. в материале [Использование Intune](/intune/atp-manage-vulnerabilities) для устранения уязвимостей, выявленных Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="af961-122">See [Use Intune to remediate vulnerabilities identified by Microsoft Defender for Endpoint](/intune/atp-manage-vulnerabilities) for details.</span></span>

### <a name="remediation-request-steps"></a><span data-ttu-id="af961-123">Действия запроса на исправление</span><span class="sxs-lookup"><span data-stu-id="af961-123">Remediation request steps</span></span>

1. <span data-ttu-id="af961-124">Перейдите в контроль угроз и уязвимостей меню навигации в Центр безопасности в Microsoft Defender и выберите [**рекомендации по безопасности.**](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="af961-124">Go to the threat and vulnerability management navigation menu in the Microsoft Defender Security Center, and select [**Security recommendations**](tvm-security-recommendation.md).</span></span>

2. <span data-ttu-id="af961-125">Выберите рекомендацию по безопасности, для чего необходимо запросить исправление, а затем выберите **параметры исправлений.**</span><span class="sxs-lookup"><span data-stu-id="af961-125">Select a security recommendation you would like to request remediation for, and then select **Remediation options**.</span></span>

3. <span data-ttu-id="af961-126">Заполните форму, в том числе запрашиваемую исправление для применимых групп устройств, приоритета, даты и необязательных заметок.</span><span class="sxs-lookup"><span data-stu-id="af961-126">Fill out the form, including what you are requesting remediation for, applicable device groups, priority, due date, and optional notes.</span></span>
    1. <span data-ttu-id="af961-127">Если вы выбираете параметр "требуемого внимания", выбор даты не будет доступен, так как не существует конкретных действий.</span><span class="sxs-lookup"><span data-stu-id="af961-127">If you choose the "attention required" remediation option, selecting a due date will not be available since there is no specific action.</span></span>

4. <span data-ttu-id="af961-128">Выберите **отправку запроса**.</span><span class="sxs-lookup"><span data-stu-id="af961-128">Select **Submit request**.</span></span> <span data-ttu-id="af961-129">Отправка запроса на исправление создает элемент действия по исправлению в контроль угроз и уязвимостей, который можно использовать для мониторинга хода восстановления для этой рекомендации.</span><span class="sxs-lookup"><span data-stu-id="af961-129">Submitting a remediation request creates a remediation activity item within threat and vulnerability management, which can be used for monitoring the remediation progress for this recommendation.</span></span> <span data-ttu-id="af961-130">Это не вызовет исправление и не будет применять какие-либо изменения к устройствам.</span><span class="sxs-lookup"><span data-stu-id="af961-130">This will not trigger a remediation or apply any changes to devices.</span></span>

5. <span data-ttu-id="af961-131">Уведомите ИТ-администратора о новом запросе и зайдите в Intune, чтобы утвердить или отклонить запрос и запустить развертывание пакета.</span><span class="sxs-lookup"><span data-stu-id="af961-131">Notify your IT Administrator about the new request and have them log into Intune to approve or reject the request and start a package deployment.</span></span>

6. <span data-ttu-id="af961-132">Перейдите на [**страницу**](tvm-remediation.md) Исправление, чтобы просмотреть состояние запроса на исправление.</span><span class="sxs-lookup"><span data-stu-id="af961-132">Go to the [**Remediation**](tvm-remediation.md) page to view the status of your remediation request.</span></span>

<span data-ttu-id="af961-133">Чтобы проверить, как будет показан билет в [Intune,](/intune/atp-manage-vulnerabilities) см. в материале Use Intune для устранения уязвимостей, выявленных в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="af961-133">If you want to check how the ticket shows up in Intune, see [Use Intune to remediate vulnerabilities identified by Microsoft Defender for Endpoint](/intune/atp-manage-vulnerabilities) for details.</span></span>

>[!NOTE]
><span data-ttu-id="af961-134">Если ваш запрос включает в себя исправление более 10 000 устройств, мы можем отправить только 10 000 устройств для восстановления в Intune.</span><span class="sxs-lookup"><span data-stu-id="af961-134">If your request involves remediating more than 10,000 devices, we can only send 10,000 devices for remediation to Intune.</span></span>

<span data-ttu-id="af961-135">После того, как слабые стороны кибербезопасности организации будут выявлены и отнеслись к рекомендациям по [безопасности,](tvm-security-recommendation.md)приступить к созданию задач безопасности.</span><span class="sxs-lookup"><span data-stu-id="af961-135">After your organization's cybersecurity weaknesses are identified and mapped to actionable [security recommendations](tvm-security-recommendation.md), start creating security tasks.</span></span> <span data-ttu-id="af961-136">Задачи можно создавать с помощью интеграции с Microsoft Intune, где создаются билеты на исправление.</span><span class="sxs-lookup"><span data-stu-id="af961-136">You can create tasks through the integration with Microsoft Intune where remediation tickets are created.</span></span>

<span data-ttu-id="af961-137">Снижение воздействия уязвимостей в организации и повышение конфигурации безопасности путем устранения рекомендаций по безопасности.</span><span class="sxs-lookup"><span data-stu-id="af961-137">Lower your organization's exposure from vulnerabilities and increase your security configuration by remediating the security recommendations.</span></span>

## <a name="view-your-remediation-activities"></a><span data-ttu-id="af961-138">Просмотр действий по исправлению</span><span class="sxs-lookup"><span data-stu-id="af961-138">View your remediation activities</span></span>

<span data-ttu-id="af961-139">При отправке запроса на исправление со страницы рекомендации по безопасности оно привнося в действие исправление.</span><span class="sxs-lookup"><span data-stu-id="af961-139">When you submit a remediation request from the Security recommendations page, it kicks-off a remediation activity.</span></span> <span data-ttu-id="af961-140">Создается задача безопасности, **которую** можно отслеживать на странице контроль угроз и уязвимостей исправлении, а в Microsoft Intune создается билет на исправление.</span><span class="sxs-lookup"><span data-stu-id="af961-140">A security task is created that can be tracked in the threat and vulnerability management **Remediation** page, and a remediation ticket is created in Microsoft Intune.</span></span>

<span data-ttu-id="af961-141">Если вы выбрали параметр "требуемого внимания", не будет панели прогресса, состояния билета или даты выполнения, так как не существует фактических действий, которые мы можем отслеживать.</span><span class="sxs-lookup"><span data-stu-id="af961-141">If you chose the "attention required" remediation option, there will be no progress bar, ticket status, or due date since there is no actual action we can monitor.</span></span>

<span data-ttu-id="af961-142">После того как вы находитесь на странице Исправление, выберите действия по исправлению, которые необходимо просмотреть.</span><span class="sxs-lookup"><span data-stu-id="af961-142">Once you are in the Remediation page, select the remediation activity that you want to view.</span></span> <span data-ttu-id="af961-143">Вы можете выполнять действия по исправлению, отслеживать ход выполнения, просматривать соответствующие рекомендации, экспортировать в CSV или отмечать как завершенные.</span><span class="sxs-lookup"><span data-stu-id="af961-143">You can follow the remediation steps, track progress, view the related recommendation, export to CSV, or mark as complete.</span></span>
<span data-ttu-id="af961-144">![Пример страницы Исправление, с выбранным действием по исправлению и вылетом этого действия с описанием, средствами управления ИТ-службой и устройствами, а также ходом восстановления устройств.](images/remediation_flyouteolsw.png)</span><span class="sxs-lookup"><span data-stu-id="af961-144">![Example of the Remediation page, with a selected remediation activity, and that activity's flyout listing the description, IT service and device management tools, and device remediation progress.](images/remediation_flyouteolsw.png)</span></span>

>[!NOTE]
> <span data-ttu-id="af961-145">Существует 180-дневный период хранения для завершенных действий по исправлению.</span><span class="sxs-lookup"><span data-stu-id="af961-145">There is a 180 day retention period for completed remediation activities.</span></span> <span data-ttu-id="af961-146">Чтобы страница Исправление выполнялась оптимально, действие по исправлению будет удалено через 6 месяцев после ее завершения.</span><span class="sxs-lookup"><span data-stu-id="af961-146">To keep the Remediation page performing optimally, the remediation activity will be removed 6 months after its completion.</span></span>

### <a name="completed-by-column"></a><span data-ttu-id="af961-147">Завершено столбцом</span><span class="sxs-lookup"><span data-stu-id="af961-147">Completed by column</span></span>

<span data-ttu-id="af961-148">Отслеживайте, кто закрыл действие по исправлению с помощью столбца "Завершено" на странице Исправление.</span><span class="sxs-lookup"><span data-stu-id="af961-148">Track who closed the remediation activity with the "Completed by" column on the Remediation page.</span></span>

- <span data-ttu-id="af961-149">**Адрес электронной** почты: электронная почта человека, который вручную выполнил задачу</span><span class="sxs-lookup"><span data-stu-id="af961-149">**Email address**: The email of the person who manually completed the task</span></span>
- <span data-ttu-id="af961-150">**Подтверждение системы:** задача была автоматически выполнена (все устройства исправлены)</span><span class="sxs-lookup"><span data-stu-id="af961-150">**System confirmation**: The task was automatically completed (all devices remediated)</span></span>
- <span data-ttu-id="af961-151">**N/A.** Информация недоступна, так как мы не знаем, как была выполнена эта более старая задача</span><span class="sxs-lookup"><span data-stu-id="af961-151">**N/A**: Information is not available because we don't know how this older task was completed</span></span>

![Создан столбцами с двумя строками и завершен.](images/tvm-completed-by.png)

### <a name="top-remediation-activities-in-the-dashboard"></a><span data-ttu-id="af961-154">Топ действий по исправлению в панели мониторинга</span><span class="sxs-lookup"><span data-stu-id="af961-154">Top remediation activities in the dashboard</span></span>

<span data-ttu-id="af961-155">Просмотр **действий по исправлению** верхнего контроль угроз и уязвимостей [панели мониторинга.](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="af961-155">View **Top remediation activities** in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md).</span></span> <span data-ttu-id="af961-156">Выберите любой из записей, чтобы перейти на страницу **Исправление.**</span><span class="sxs-lookup"><span data-stu-id="af961-156">Select any of the entries to go to the **Remediation** page.</span></span> <span data-ttu-id="af961-157">Вы можете пометить действие по исправлению после устранения задачи командой ИТ-администратора.</span><span class="sxs-lookup"><span data-stu-id="af961-157">You can mark the remediation activity as completed after the IT admin team remediates the task.</span></span>

![Пример карты действий по исправлению с таблицей, в которую перечислены топовые действия, созданные из рекомендаций по безопасности.](images/tvm-remediation-activities-card.png)

## <a name="related-articles"></a><span data-ttu-id="af961-159">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="af961-159">Related articles</span></span>

- [<span data-ttu-id="af961-160">Обзор угроз и управление уязвимостями</span><span class="sxs-lookup"><span data-stu-id="af961-160">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="af961-161">Панель мониторинга</span><span class="sxs-lookup"><span data-stu-id="af961-161">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="af961-162">Рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="af961-162">Security recommendations</span></span>](tvm-security-recommendation.md)