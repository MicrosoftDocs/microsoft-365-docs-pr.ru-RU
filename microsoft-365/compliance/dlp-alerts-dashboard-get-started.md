---
title: Начало работы с панелью мониторинга оповещений для защиты от потери данных
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Начало работы с определением и управлением оповещениями для политик предотвращения потери данных.
ms.openlocfilehash: ad117eb0c5460b90c92c664f0c233b81d1882327
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843870"
---
# <a name="get-started-with-the-data-loss-prevention-alert-dashboard"></a><span data-ttu-id="31268-103">Начало работы с панелью мониторинга оповещений для защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="31268-103">Get started with the data loss prevention alert dashboard</span></span>

<span data-ttu-id="31268-104">Политики предотвращения потери данных (DLP) могут принимать защитные меры, чтобы предотвратить непреднамеренное совместное использование конфиденциальных элементов.</span><span class="sxs-lookup"><span data-stu-id="31268-104">Data loss prevention (DLP) policies can take protective actions to prevent unintentional sharing of sensitive items.</span></span> <span data-ttu-id="31268-105">При действии по конфиденциальному элементу вы можете быть уведомлены путем настройки оповещений для DLP.</span><span class="sxs-lookup"><span data-stu-id="31268-105">When an action is taken on a sensitive item, you can be notified by configuring alerts for DLP.</span></span> <span data-ttu-id="31268-106">В этой статье показано, как определить политики оповещения, связанные с политиками предотвращения потери данных (DLP).</span><span class="sxs-lookup"><span data-stu-id="31268-106">This article shows you how to define rich alert policies that are linked to your data loss prevention (DLP) policies.</span></span> <span data-ttu-id="31268-107">Вы увидите, как использовать панель управления оповещениями [](https://compliance.microsoft.com/) [DLP](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) в центре Microsoft 365 для просмотра оповещений, событий и связанных метаданных для нарушений политики DLP.</span><span class="sxs-lookup"><span data-stu-id="31268-107">You'll see how to use the [DLP alert management dashboard](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) in the [Microsoft 365 compliance center](https://compliance.microsoft.com/) to view alerts, events, and associated metadata for DLP policy violations.</span></span>

<span data-ttu-id="31268-108">Если у вас нет оповещений о DLP, необходимо просмотреть панель оповещений о предотвращении [потери данных.](dlp-alerts-dashboard-learn.md)</span><span class="sxs-lookup"><span data-stu-id="31268-108">If you are new to DLP alerts, you should review [Learn about the data loss prevention alerts dashboard](dlp-alerts-dashboard-learn.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="31268-109">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="31268-109">Before you begin</span></span>

<span data-ttu-id="31268-110">Перед началом работы убедитесь, что у вас есть необходимые условия:</span><span class="sxs-lookup"><span data-stu-id="31268-110">Before you begin, make sure you have the necessary prerequisites:</span></span>

-   <span data-ttu-id="31268-111">Лицензирование панели управления оповещений DLP</span><span class="sxs-lookup"><span data-stu-id="31268-111">Licensing for the DLP alerts management dashboard</span></span>
-   <span data-ttu-id="31268-112">Лицензирование параметров конфигурации оповещений</span><span class="sxs-lookup"><span data-stu-id="31268-112">Licensing for alert configuration options</span></span>
-   <span data-ttu-id="31268-113">Роли</span><span class="sxs-lookup"><span data-stu-id="31268-113">Roles</span></span>

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a><span data-ttu-id="31268-114">Лицензирование панели управления оповещениями DLP</span><span class="sxs-lookup"><span data-stu-id="31268-114">Licensing for the DLP alert management dashboard</span></span>

<span data-ttu-id="31268-115">Все подходящие клиенты для Office 365 DLP могут получить доступ к панели мониторинга управления оповещениями DLP.</span><span class="sxs-lookup"><span data-stu-id="31268-115">All eligible tenants for Office 365 DLP can access the DLP alert management dashboard.</span></span> <span data-ttu-id="31268-116">Чтобы начать работу, вы должны иметь право на Office 365 DLP для Exchange Online, SharePoint Online и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="31268-116">To get started, you should be eligible for Office 365 DLP for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="31268-117">Дополнительные сведения о требованиях к лицензированию для Office 365 DLP см. в таблице Какие лицензии предоставляют пользователю права на получение [выгоды от службы?.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)</span><span class="sxs-lookup"><span data-stu-id="31268-117">For more information about the licensing requirements for Office 365 DLP, see [Which licenses provide the rights for a user to benefit from the service?](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).</span></span>

<span data-ttu-id="31268-118">Клиенты, [](endpoint-dlp-learn-about.md) которые используют DLP конечной точки, имеющие право на Teams [DLP,](dlp-microsoft-teams.md) увидят оповещения о политике DLP конечной точки и Teams оповещений о политике DLP в панели управления оповещениями DLP.</span><span class="sxs-lookup"><span data-stu-id="31268-118">Customers who use [Endpoint DLP](endpoint-dlp-learn-about.md) who are eligible for [Teams DLP](dlp-microsoft-teams.md) will see their endpoint DLP policy alerts and Teams DLP policy alerts in the DLP alert management dashboard.</span></span>

<span data-ttu-id="31268-119">Функция **предварительного просмотра** контента доступна только для этих лицензий:</span><span class="sxs-lookup"><span data-stu-id="31268-119">The **content preview** feature is available only for these licenses:</span></span>

- <span data-ttu-id="31268-120">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="31268-120">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="31268-121">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="31268-121">Office 365 (E5)</span></span>
- <span data-ttu-id="31268-122">Добавление дополнительных требований к требованиям (E5)</span><span class="sxs-lookup"><span data-stu-id="31268-122">Advanced Compliance (E5) add on</span></span>
- <span data-ttu-id="31268-123">Microsoft 365 E5/A5 Защита и управление информацией</span><span class="sxs-lookup"><span data-stu-id="31268-123">Microsoft 365 E5/A5 Information Protection and Governance</span></span>
- <span data-ttu-id="31268-124">Соответствие требованиям Microsft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="31268-124">Microsft 365 E5/A5 Compliance</span></span>

### <a name="licensing-for-alert-configuration-options"></a><span data-ttu-id="31268-125">Лицензирование параметров конфигурации оповещений</span><span class="sxs-lookup"><span data-stu-id="31268-125">Licensing for alert configuration options</span></span>

<span data-ttu-id="31268-126">**Конфигурация** оповещений об одном событии. Организации, у которых есть подписка на E1, F1 или G1 или подписка на E3 или G3, могут создавать политики оповещения только там, где оповещения запускаются каждый раз при каждом действии.</span><span class="sxs-lookup"><span data-stu-id="31268-126">**Single-event alert configuration**: Organizations that have an E1, F1, or G1 subscription or an E3 or G3 subscription can create alert policies only where an alert is triggered every time an activity occurs.</span></span>

<span data-ttu-id="31268-127">**Агрегированная конфигурация** оповещений. Чтобы настроить агрегированные политики оповещения на основе порога, необходимо одну из этих конфигураций лицензирования:</span><span class="sxs-lookup"><span data-stu-id="31268-127">**Aggregated alert configuration**: To configure aggregate alert policies based on a threshold, you must one of these licensing configurations:</span></span>

- <span data-ttu-id="31268-128">Подписка на E5 или G5</span><span class="sxs-lookup"><span data-stu-id="31268-128">An E5 or G5 subscription</span></span>
- <span data-ttu-id="31268-129">Подписка на E1, F1 или G1 или подписка на E3 или G3, которая включает одну из следующих функций:</span><span class="sxs-lookup"><span data-stu-id="31268-129">An E1, F1, or G1 subscription or an E3 or G3 subscription that includes one of the following features:</span></span>
    - <span data-ttu-id="31268-130">Office 365 Advanced Threat Protection (план 2)</span><span class="sxs-lookup"><span data-stu-id="31268-130">Office 365 Advanced Threat Protection Plan 2</span></span>
    - <span data-ttu-id="31268-131">Соответствие требованиям Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="31268-131">Microsoft 365 E5 Compliance</span></span>
    - <span data-ttu-id="31268-132">Microsoft 365 лицензии на проверку и проверку</span><span class="sxs-lookup"><span data-stu-id="31268-132">Microsoft 365 eDiscovery and Audit add-on license</span></span>

### <a name="roles"></a><span data-ttu-id="31268-133">Роли</span><span class="sxs-lookup"><span data-stu-id="31268-133">Roles</span></span>


<span data-ttu-id="31268-134">Чтобы просмотреть панель управления оповещениями DLP или изменить параметры конфигурации оповещений в политике DLP, необходимо быть членом одной из этих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="31268-134">If you want to view the DLP alert management dashboard or to edit the alert configuration options in a DLP policy, you must be a member of one of these role groups:</span></span>

- <span data-ttu-id="31268-135">Администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="31268-135">Compliance Administrator</span></span>
- <span data-ttu-id="31268-136">Администратор данных соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="31268-136">Compliance Data Administrator</span></span>
- <span data-ttu-id="31268-137">"Администратор безопасности"</span><span class="sxs-lookup"><span data-stu-id="31268-137">Security Administrator</span></span>
- <span data-ttu-id="31268-138">Оператор безопасности</span><span class="sxs-lookup"><span data-stu-id="31268-138">Security Operator</span></span>
- <span data-ttu-id="31268-139">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="31268-139">Security Reader</span></span>

<span data-ttu-id="31268-140">Чтобы получить доступ к панели управления оповещениями DLP, необходимо:</span><span class="sxs-lookup"><span data-stu-id="31268-140">To access the DLP alert management dashboard, you need the:</span></span>

- <span data-ttu-id="31268-141">Управление оповещениями</span><span class="sxs-lookup"><span data-stu-id="31268-141">Manage alerts</span></span>

<span data-ttu-id="31268-142">и обе эти роли:</span><span class="sxs-lookup"><span data-stu-id="31268-142">and either of these two roles:</span></span>

- <span data-ttu-id="31268-143">Управление соответствием требованиям DLP</span><span class="sxs-lookup"><span data-stu-id="31268-143">DLP Compliance Management</span></span>
- <span data-ttu-id="31268-144">View-Only управления соответствием требованиям DLP</span><span class="sxs-lookup"><span data-stu-id="31268-144">View-Only DLP Compliance Management</span></span>

<span data-ttu-id="31268-145">Чтобы получить доступ к функции предварительного просмотра контента и соотносятого конфиденциального контента и контекстных функций, вы должны быть членом:</span><span class="sxs-lookup"><span data-stu-id="31268-145">To access the Content preview feature and the Matched sensitive content and context features you must be a member of:</span></span>

- <span data-ttu-id="31268-146">Группа ролей просмотра контента Обозреватель контента</span><span class="sxs-lookup"><span data-stu-id="31268-146">Content Explorer Content Viewer role group</span></span>

<span data-ttu-id="31268-147">которая имеет предварительно назначенную роль просмотра контента классификации данных.</span><span class="sxs-lookup"><span data-stu-id="31268-147">which has the data classification content viewer role pre-assigned.</span></span>

## <a name="dlp-alert-configuration"></a><span data-ttu-id="31268-148">Конфигурация оповещений DLP</span><span class="sxs-lookup"><span data-stu-id="31268-148">DLP alert configuration</span></span>

<span data-ttu-id="31268-149">Сведения о настройке оповещений в политике DLP см. в таблице [Where to start with data loss prevention.](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)</span><span class="sxs-lookup"><span data-stu-id="31268-149">To learn how to configure an alert in your DLP policy, see [Where to start with data loss prevention](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention).</span></span>

### <a name="aggregate-event-alert-configuration"></a><span data-ttu-id="31268-150">Агрегированная конфигурация оповещения о событиях</span><span class="sxs-lookup"><span data-stu-id="31268-150">Aggregate event alert configuration</span></span>

<span data-ttu-id="31268-151">Если ваша org лицензирована для [агрегированных](#licensing-for-alert-configuration-options)параметров конфигурации оповещений, вы увидите эти параметры при создании или редактировании политики DLP.</span><span class="sxs-lookup"><span data-stu-id="31268-151">If your org is licensed for [aggregated alert configuration options](#licensing-for-alert-configuration-options), then you'll see these options when you create or edit a DLP policy.</span></span>

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Снимок экрана, показывающий параметры отчетов об инцидентах для пользователей, имеющих право на агрегированные параметры конфигурации оповещений." border="false":::

<span data-ttu-id="31268-153">Эта конфигурация позволяет настроить политику для создания оповещений при каждом совпадении действий с условиями политики или при превышении определенного порогового значения в зависимости от количества действий или объема exfiltrated данных.</span><span class="sxs-lookup"><span data-stu-id="31268-153">This configuration allows you to set up a policy to generate an alert every time an activity matches the policy conditions or when a certain threshold is exceeded, based on the number of activities or based on the volume of exfiltrated data.</span></span>

### <a name="single-event-alert-configuration"></a><span data-ttu-id="31268-154">Конфигурация оповещения об одном событии</span><span class="sxs-lookup"><span data-stu-id="31268-154">Single event alert configuration</span></span>

<span data-ttu-id="31268-155">Если у вашей организации есть лицензия [на](#licensing-for-alert-configuration-options)параметры конфигурации оповещения об одном событии, вы увидите эти параметры при создании или редактировании политики DLP.</span><span class="sxs-lookup"><span data-stu-id="31268-155">If your org is licensed for [single-event alert configuration options](#licensing-for-alert-configuration-options), then you'll see these options when you create or edit a DLP policy.</span></span> <span data-ttu-id="31268-156">Используйте этот параметр, чтобы создать оповещение, которое повышается при каждом совпадении правил DLP.</span><span class="sxs-lookup"><span data-stu-id="31268-156">Use this option to create an alert that's raised every time a DLP rule match happens.</span></span>

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Снимок экрана, показывающий параметры отчетов об инцидентах для пользователей, имеющих право на параметры конфигурации оповещения об одном событии." border="false":::

## <a name="investigate-a-dlp-alert"></a><span data-ttu-id="31268-158">Исследование оповещений о DLP</span><span class="sxs-lookup"><span data-stu-id="31268-158">Investigate a DLP alert</span></span>

<span data-ttu-id="31268-159">Для работы с панелью управления оповещением DLP:</span><span class="sxs-lookup"><span data-stu-id="31268-159">To work with the DLP alert management dashboard:</span></span>

1. <span data-ttu-id="31268-160">В центре [Microsoft 365 потери](https://www.compliance.microsoft.com)данных перейдите в центр по предотвращению **потери данных.**</span><span class="sxs-lookup"><span data-stu-id="31268-160">In the [Microsoft 365 compliance center](https://www.compliance.microsoft.com), go to **Data Loss Prevention**.</span></span>
2. <span data-ttu-id="31268-161">Выберите **вкладку Оповещения,** чтобы просмотреть панель оповещений DLP.</span><span class="sxs-lookup"><span data-stu-id="31268-161">Select the **Alerts** tab to view the DLP alerts dashboard.</span></span>
3. <span data-ttu-id="31268-162">Выберите оповещение, чтобы узнать подробности:</span><span class="sxs-lookup"><span data-stu-id="31268-162">Select an alert to see details:</span></span>

:::image type="content" source="../media/alert-details.png" alt-text="Снимок экрана, показывающий сведения об оповещении на панели управления оповещением DLP." border="false":::

4. <span data-ttu-id="31268-164">Выберите **вкладку События,** чтобы просмотреть все события, связанные с оповещением.</span><span class="sxs-lookup"><span data-stu-id="31268-164">Select the **Events** tab to view all of the events associated with the alert.</span></span> <span data-ttu-id="31268-165">Для просмотра его сведений можно выбрать определенное событие.</span><span class="sxs-lookup"><span data-stu-id="31268-165">You can choose a particular event to view its details.</span></span> <span data-ttu-id="31268-166">Список доступных сведений о событиях см. в материале "Сведения о панели мониторинга оповещений о предотвращении потери [данных".](dlp-alerts-dashboard-learn.md)</span><span class="sxs-lookup"><span data-stu-id="31268-166">For a list of some of the available event details, see, [Learn about the data loss prevention Alerts dashboard](dlp-alerts-dashboard-learn.md).</span></span>
5. <span data-ttu-id="31268-167">Выберите **Сведения,** чтобы **открыть страницу Обзор** для оповещения.</span><span class="sxs-lookup"><span data-stu-id="31268-167">Select **Details** to open the **Overview** page for the alert.</span></span> <span data-ttu-id="31268-168">На странице обзоров приводится сводка:</span><span class="sxs-lookup"><span data-stu-id="31268-168">The overview page provides a summary:</span></span>
    1. <span data-ttu-id="31268-169">о том, что произошло</span><span class="sxs-lookup"><span data-stu-id="31268-169">of what happened</span></span>
    1. <span data-ttu-id="31268-170">которые выполняли действия, вызваввшие совпадение политики</span><span class="sxs-lookup"><span data-stu-id="31268-170">who performed the actions that caused the policy match</span></span>
    1. <span data-ttu-id="31268-171">сведения о совпадаем политике и</span><span class="sxs-lookup"><span data-stu-id="31268-171">information about the matched policy, and more</span></span> 

6. <span data-ttu-id="31268-172">Выберите **вкладку События,** чтобы получить доступ к:</span><span class="sxs-lookup"><span data-stu-id="31268-172">Choose the **Events** tab to access the:</span></span>
    1. <span data-ttu-id="31268-173">участие контента</span><span class="sxs-lookup"><span data-stu-id="31268-173">content involved</span></span>
    1. <span data-ttu-id="31268-174">типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="31268-174">sensitive information types matched</span></span>
    1. <span data-ttu-id="31268-175">метаданные</span><span class="sxs-lookup"><span data-stu-id="31268-175">metadata</span></span>

7. <span data-ttu-id="31268-176">Выберите **вкладку Типы** конфиденциальной информации, чтобы просмотреть сведения о типах конфиденциальной информации, обнаруженных в содержимом.</span><span class="sxs-lookup"><span data-stu-id="31268-176">Select the **Sensitive Info Types** tab to view details about the sensitive information types detected in the content.</span></span> <span data-ttu-id="31268-177">Сведения включают доверие, количество и содержимое, которое соответствует типу конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="31268-177">Details include confidence, count, and the content that matches the sensitive information type.</span></span>

8. <span data-ttu-id="31268-178">После изучения оповещений вернись на вкладку **Обзор,** где можно управлять триаджем и управлять расположением оповещений и добавлять комментарии.</span><span class="sxs-lookup"><span data-stu-id="31268-178">After you investigate the alert, return to the **Overview** tab where you can manage triage and manage the disposition of the alert and add comments.</span></span>

- <span data-ttu-id="31268-179">Чтобы узнать историю управления рабочего процесса, выберите **журнал Management.**</span><span class="sxs-lookup"><span data-stu-id="31268-179">To see the history of workflow management, choose **Management log**.</span></span>
- <span data-ttu-id="31268-180">После принятия необходимых действий для оповещения установите состояние оповещений **в Resolved**.</span><span class="sxs-lookup"><span data-stu-id="31268-180">After you take the required action for the alert, set the status of the alert to **Resolved**.</span></span>

## <a name="see-also"></a><span data-ttu-id="31268-181">См. также</span><span class="sxs-lookup"><span data-stu-id="31268-181">See also</span></span>

- [<span data-ttu-id="31268-182">Сведения о оповещениях о предотвращении потери данных и панели мониторинга оповещений</span><span class="sxs-lookup"><span data-stu-id="31268-182">Learn about data loss prevention alerts and the alerts dashboard</span></span>](dlp-alerts-dashboard-learn.md)
- [<span data-ttu-id="31268-183">Создание, тестирование и настройка политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="31268-183">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)