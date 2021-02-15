---
title: Создание пользовательских правил обнаружения и управление ими в Microsoft 365 Defender
description: Узнайте, как создавать настраиваемые правила обнаружения и управлять ими на основе запросов на расширенный поиск
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, custom detections, rules, schema, kusto, microsoft 365, Microsoft Threat Protection, RBAC, permissions, Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d58292f658446259bfab5b1b55c8b462d081421c
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080627"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="32ca9-104">Создание пользовательских правил обнаружения и управление ими</span><span class="sxs-lookup"><span data-stu-id="32ca9-104">Create and manage custom detections rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="32ca9-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="32ca9-105">**Applies to:**</span></span>
- <span data-ttu-id="32ca9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="32ca9-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="32ca9-107">Настраиваемые правила обнаружения — это правила, которые можно проектировать и настраивать с помощью [запросов на расширенный](advanced-hunting-overview.md) поиск.</span><span class="sxs-lookup"><span data-stu-id="32ca9-107">Custom detection rules are rules you can design and tweak using [advanced hunting](advanced-hunting-overview.md) queries.</span></span> <span data-ttu-id="32ca9-108">Эти правила по-настоящему отслеживают различные события и состояния системы, включая подозрительные нарушения безопасности и неправильные конечные точки.</span><span class="sxs-lookup"><span data-stu-id="32ca9-108">These rules let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="32ca9-109">Вы можете настроить их на регулярный запуск с регулярными интервалами, создавая оповещения и принимая ответные действия при совпадениях.</span><span class="sxs-lookup"><span data-stu-id="32ca9-109">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="32ca9-110">Необходимые разрешения для управления пользовательскими обнаружениями</span><span class="sxs-lookup"><span data-stu-id="32ca9-110">Required permissions for managing custom detections</span></span>

<span data-ttu-id="32ca9-111">Для управления пользовательскими обнаружениями вам должна быть назначена одна из этих ролей:</span><span class="sxs-lookup"><span data-stu-id="32ca9-111">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="32ca9-112">**Администратор безопасности**— пользователи с этой ролью [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) могут управлять настройками безопасности в Центре безопасности Microsoft 365 и других порталах и службах.</span><span class="sxs-lookup"><span data-stu-id="32ca9-112">**Security administrator**—Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage security settings in Microsoft 365 security center and other portals and services.</span></span>

- <span data-ttu-id="32ca9-113">**Оператор безопасности**— пользователи с этой ролью [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) могут управлять оповещениями и иметь глобальный доступ только для чтения к функциям, связанным с безопасностью, включая всю информацию в Центре безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="32ca9-113">**Security operator**—Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage alerts and have global read-only access to security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="32ca9-114">Этой роли достаточно для управления пользовательскими обнаружениями, только если управление доступом на основе ролей (RBAC) отключено в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="32ca9-114">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="32ca9-115">Если вы настроили RBAC,  вам также потребуется разрешение на управление настройками безопасности для Защитника для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="32ca9-115">If you have RBAC configured, you also need the **manage security settings** permission for Defender for Endpoint.</span></span>

<span data-ttu-id="32ca9-116">Для управления требуемой разрешениями **глобальный администратор** может:</span><span class="sxs-lookup"><span data-stu-id="32ca9-116">To manage required permissions, a **global administrator** can:</span></span>

- <span data-ttu-id="32ca9-117">**Назначьте роль администратора** безопасности или оператора **безопасности** в Центре администрирования [Microsoft 365](https://admin.microsoft.com/) в области **"Администратор безопасности**  >  **ролей".**</span><span class="sxs-lookup"><span data-stu-id="32ca9-117">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="32ca9-118">Проверьте параметры RBAC для Microsoft Defender для конечной точки в Центре безопасности [Microsoft Defender](https://securitycenter.windows.com/) в области **"Роли разрешений**  >  **параметров".**  >  </span><span class="sxs-lookup"><span data-stu-id="32ca9-118">Check RBAC settings for Microsoft Defender for Endpoint in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="32ca9-119">Выберите соответствующую роль, чтобы назначить **разрешение на управление настройками безопасности.**</span><span class="sxs-lookup"><span data-stu-id="32ca9-119">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="32ca9-120">Для управления пользовательскими  обнаружениями операторам  безопасности потребуется разрешение на управление настройками безопасности в Microsoft Defender для конечной точки, если включен RBAC.</span><span class="sxs-lookup"><span data-stu-id="32ca9-120">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender for Endpoint if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="32ca9-121">Создание настраиваемой правила обнаружения</span><span class="sxs-lookup"><span data-stu-id="32ca9-121">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="32ca9-122">1. Подготовьте запрос.</span><span class="sxs-lookup"><span data-stu-id="32ca9-122">1. Prepare the query.</span></span>

<span data-ttu-id="32ca9-123">В Центре безопасности Microsoft 365 перейдите в службу **"Расширенный** поиск" и выберите существующий запрос или создайте новый запрос.</span><span class="sxs-lookup"><span data-stu-id="32ca9-123">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="32ca9-124">При использовании нового запроса запустите запрос, чтобы определить ошибки и понять возможные результаты.</span><span class="sxs-lookup"><span data-stu-id="32ca9-124">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="32ca9-125">Чтобы служба не возвращала слишком много оповещений, каждое правило может создавать только 100 оповещений при каждом запуске.</span><span class="sxs-lookup"><span data-stu-id="32ca9-125">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="32ca9-126">Перед созданием правила оповещайте запрос о нормальной ежедневной активности.</span><span class="sxs-lookup"><span data-stu-id="32ca9-126">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="32ca9-127">Необходимые столбцы в результатах запроса</span><span class="sxs-lookup"><span data-stu-id="32ca9-127">Required columns in the query results</span></span>
<span data-ttu-id="32ca9-128">Чтобы создать пользовательское правило обнаружения, запрос должен вернуть следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="32ca9-128">To create a custom detection rule, the query must return the following columns:</span></span>

- <span data-ttu-id="32ca9-129">`Timestamp`— используется для замещений времени для созданных оповещений</span><span class="sxs-lookup"><span data-stu-id="32ca9-129">`Timestamp`—used to set the timestamp for generated alerts</span></span>
- <span data-ttu-id="32ca9-130">`ReportId`— включает подыском для исходных записей</span><span class="sxs-lookup"><span data-stu-id="32ca9-130">`ReportId`—enables lookups for the original records</span></span>
- <span data-ttu-id="32ca9-131">Один из следующих столбцов, которые определяют определенные устройства, пользователей или почтовые ящики:</span><span class="sxs-lookup"><span data-stu-id="32ca9-131">One of the following columns that identify specific devices, users, or mailboxes:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="32ca9-132">`SenderFromAddress` (отправитель конверта или Return-Path адрес)</span><span class="sxs-lookup"><span data-stu-id="32ca9-132">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="32ca9-133">`SenderMailFromAddress` (адрес отправитель отображается почтовым клиентом)</span><span class="sxs-lookup"><span data-stu-id="32ca9-133">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
><span data-ttu-id="32ca9-134">Поддержка дополнительных сущностям будет добавлена по мере того, как новые таблицы будут добавлены в схему [дополнительной охоты.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="32ca9-134">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="32ca9-135">Простые запросы, такие как запросы, которые не используют оператор или для настройки или агрегировать результаты, обычно возвращают `project` `summarize` эти общие столбцы.</span><span class="sxs-lookup"><span data-stu-id="32ca9-135">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="32ca9-136">Существуют различные способы, чтобы более сложные запросы возвращали эти столбцы.</span><span class="sxs-lookup"><span data-stu-id="32ca9-136">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="32ca9-137">Например, если вы предпочитаете агрегировать и подсчитать по объекту в столбце, например, вы можете возвращать и получать его из последнего события, включаемого в `DeviceId` `Timestamp` `ReportId` каждый уникальный `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="32ca9-137">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` and `ReportId` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="32ca9-138">В приведенного ниже примере запроса подсчитываются уникальные устройства () с антивирусными средствами, и этот подсчет используется для поиска только устройств с более чем `DeviceId` пятью обнаружениями.</span><span class="sxs-lookup"><span data-stu-id="32ca9-138">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="32ca9-139">Для возврата последней `Timestamp` версии и соответствующей `ReportId` функции используется оператор с `summarize` `arg_max` функцией.</span><span class="sxs-lookup"><span data-stu-id="32ca9-139">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="32ca9-140">Для улучшения производительности запроса установите фильтр времени, который соответствует назначенной частоте выполнения для правила.</span><span class="sxs-lookup"><span data-stu-id="32ca9-140">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="32ca9-141">Так как наименее частый запуск _происходит каждые 24_ часа, фильтрация за последний день охватывает все новые данные.</span><span class="sxs-lookup"><span data-stu-id="32ca9-141">Since the least frequent run is _every 24 hours_, filtering for the past day will cover all new data.</span></span>

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="32ca9-142">2. Создание нового правила и предоставление сведений об оповещении.</span><span class="sxs-lookup"><span data-stu-id="32ca9-142">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="32ca9-143">С помощью запроса в редакторе запросов выберите **"Создать** правило обнаружения" и укажите следующие сведения об оповещении:</span><span class="sxs-lookup"><span data-stu-id="32ca9-143">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="32ca9-144">**Имя обнаружения**— имя правила обнаружения</span><span class="sxs-lookup"><span data-stu-id="32ca9-144">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="32ca9-145">**Частота**— интервал выполнения запроса и выполнения действий.</span><span class="sxs-lookup"><span data-stu-id="32ca9-145">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="32ca9-146">См. дополнительные рекомендации ниже</span><span class="sxs-lookup"><span data-stu-id="32ca9-146">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="32ca9-147">**Заголовок оповещения**— заголовок, отображаемая с оповещениями, инициированными правилом</span><span class="sxs-lookup"><span data-stu-id="32ca9-147">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="32ca9-148">**Серьезность**— потенциальный риск для компонента или действия, определяемого правилом</span><span class="sxs-lookup"><span data-stu-id="32ca9-148">**Severity**—potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="32ca9-149">**Категория —** компонент угрозы или действие, заданной правилом</span><span class="sxs-lookup"><span data-stu-id="32ca9-149">**Category**—threat component or activity identified by the rule</span></span>
- <span data-ttu-id="32ca9-150">**MITRE ATT&CK**— один или несколько методов атаки, выявленных правилом, как описано в документе [MITRE ATT&CK framework.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="32ca9-150">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="32ca9-151">Этот раздел скрыт для определенных категорий оповещений, в том числе вредоносных программ, программ-вымогателей, подозрительных действий и нежелательных программ</span><span class="sxs-lookup"><span data-stu-id="32ca9-151">This section is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="32ca9-152">**Описание**— дополнительные сведения о компоненте или действии, выявленных правилом</span><span class="sxs-lookup"><span data-stu-id="32ca9-152">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="32ca9-153">**Рекомендуемые действия**— дополнительные действия, которые ответчики могут принять в ответ на оповещение</span><span class="sxs-lookup"><span data-stu-id="32ca9-153">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="32ca9-154">Частота правил</span><span class="sxs-lookup"><span data-stu-id="32ca9-154">Rule frequency</span></span>
<span data-ttu-id="32ca9-155">Когда вы сохраняете или редактируете новое правило, оно запускается и проверяет совпадения с данными за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="32ca9-155">When you save or edit a new rule, it runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="32ca9-156">Затем правило выполняется снова с фиксированными интервалами, применяя длительность обратного перенаправки в зависимости от частоты, которая вы выбираете:</span><span class="sxs-lookup"><span data-stu-id="32ca9-156">The rule then runs again at fixed intervals, applying a lookback duration based on the frequency you choose:</span></span>

- <span data-ttu-id="32ca9-157">**Каждые 24 часа —** выполняется каждые 24 часа, проверяя данные за последние 30 дней</span><span class="sxs-lookup"><span data-stu-id="32ca9-157">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="32ca9-158">**Каждые 12 часов —** выполняется каждые 12 часов, проверяя данные за последние 24 часа</span><span class="sxs-lookup"><span data-stu-id="32ca9-158">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="32ca9-159">**Каждые 3 часа —** выполняется каждые 3 часа, проверяя данные за последние 6 часов</span><span class="sxs-lookup"><span data-stu-id="32ca9-159">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="32ca9-160">**Каждый час**— выполняется каждый час, проверяя данные за последние 2 часа</span><span class="sxs-lookup"><span data-stu-id="32ca9-160">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

>[!TIP]
> <span data-ttu-id="32ca9-161">Со соответствовать фильтрам времени в запросе с длительностью возвращения.</span><span class="sxs-lookup"><span data-stu-id="32ca9-161">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="32ca9-162">Результаты вне периода поиска игнорируются.</span><span class="sxs-lookup"><span data-stu-id="32ca9-162">Results outside of the lookback duration are ignored.</span></span>  

<span data-ttu-id="32ca9-163">Выберите частоту, которая соответствует частоте отслеживания обнаружений.</span><span class="sxs-lookup"><span data-stu-id="32ca9-163">Select the frequency that matches how closely you want to monitor detections.</span></span> <span data-ttu-id="32ca9-164">Рассмотрите возможность организации реагировать на оповещения.</span><span class="sxs-lookup"><span data-stu-id="32ca9-164">Consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="32ca9-165">3. Выберите объекты, на которые они влияют.</span><span class="sxs-lookup"><span data-stu-id="32ca9-165">3. Choose the impacted entities.</span></span>
<span data-ttu-id="32ca9-166">Определите столбцы в результатах запроса, в которых ожидается найти основную затронутую или затронутую сущность.</span><span class="sxs-lookup"><span data-stu-id="32ca9-166">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="32ca9-167">Например, запрос может возвращать адреса отправитель `SenderFromAddress` `SenderMailFromAddress` (или) и получатель ( `RecipientEmailAddress` ).</span><span class="sxs-lookup"><span data-stu-id="32ca9-167">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="32ca9-168">Определение того, какой из этих столбцов представляет собой основной объект, помогает службе агрегировать соответствующие оповещения, соотносить инциденты и целевые действия реагирования.</span><span class="sxs-lookup"><span data-stu-id="32ca9-168">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="32ca9-169">Для каждого типа сущности (почтового ящика, пользователя или устройства) можно выбрать только один столбец.</span><span class="sxs-lookup"><span data-stu-id="32ca9-169">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="32ca9-170">Столбцы, которые не возвращаются запросом, не могут быть выбраны.</span><span class="sxs-lookup"><span data-stu-id="32ca9-170">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="32ca9-171">4. Укажите действия.</span><span class="sxs-lookup"><span data-stu-id="32ca9-171">4. Specify actions.</span></span>
<span data-ttu-id="32ca9-172">Настраиваемые правила обнаружения могут автоматически принимать действия с устройствами, файлами или пользователями, возвращенными запросом.</span><span class="sxs-lookup"><span data-stu-id="32ca9-172">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="32ca9-173">Действия на устройствах</span><span class="sxs-lookup"><span data-stu-id="32ca9-173">Actions on devices</span></span>
<span data-ttu-id="32ca9-174">Эти действия применяются к устройствам в `DeviceId` столбце результатов запроса:</span><span class="sxs-lookup"><span data-stu-id="32ca9-174">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="32ca9-175">**Изолировать устройство —** использует Microsoft Defender для конечной точки, чтобы применить полную сетевую изоляцию, не мешая устройству подключаться к любому приложению или службе.</span><span class="sxs-lookup"><span data-stu-id="32ca9-175">**Isolate device**—uses Microsoft Defender for Endpoint to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="32ca9-176">Дополнительные информации о Microsoft Defender для изоляции конечной точки компьютера</span><span class="sxs-lookup"><span data-stu-id="32ca9-176">Learn more about Microsoft Defender for Endpoint machine isolation</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="32ca9-177">**Сбор пакета исследования**— собирает сведения об устройстве в ZIP-файле.</span><span class="sxs-lookup"><span data-stu-id="32ca9-177">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="32ca9-178">Узнайте больше о пакете исследования в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="32ca9-178">Learn more about the Microsoft Defender for Endpoint investigation package</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="32ca9-179">**Запуск антивирусной проверки**— выполняет полную Защитник Windows антивирусную проверку на устройстве</span><span class="sxs-lookup"><span data-stu-id="32ca9-179">**Run antivirus scan**—performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="32ca9-180">**Инициирует** исследование — [инициирует автоматическое исследование](mtp-autoir.md) на устройстве</span><span class="sxs-lookup"><span data-stu-id="32ca9-180">**Initiate investigation**—initiates an [automated investigation](mtp-autoir.md) on the device</span></span>
- <span data-ttu-id="32ca9-181">**Ограничение выполнения приложения**— устанавливает ограничения на устройстве, чтобы разрешить запуск только файлов, подписанных с помощью выданного корпорацией Майкрософт сертификата.</span><span class="sxs-lookup"><span data-stu-id="32ca9-181">**Restrict app execution**—sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="32ca9-182">Узнайте больше об ограничениях приложений в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="32ca9-182">Learn more about app restrictions with Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="32ca9-183">Действия с файлами</span><span class="sxs-lookup"><span data-stu-id="32ca9-183">Actions on files</span></span>
<span data-ttu-id="32ca9-184">Если этот вариант выбран, вы  можете применить действие к файлу карантина к файлам в столбце , , или столбце `SHA1` `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="32ca9-184">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="32ca9-185">Это действие удаляет файл из текущего расположения и помещает копию в карантин.</span><span class="sxs-lookup"><span data-stu-id="32ca9-185">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="32ca9-186">Действия над пользователями</span><span class="sxs-lookup"><span data-stu-id="32ca9-186">Actions on users</span></span>
<span data-ttu-id="32ca9-187">Если этот вариант  выбран, пользователь пометит пользователя как скомпрометированную меру над пользователями в столбце или столбце результатов `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` запроса.</span><span class="sxs-lookup"><span data-stu-id="32ca9-187">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="32ca9-188">Это действие устанавливает для пользователей высокий уровень риска в Azure Active Directory, запуская соответствующие политики [защиты удостоверений.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)</span><span class="sxs-lookup"><span data-stu-id="32ca9-188">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="32ca9-189">Действие "Разрешить или заблокировать" для пользовательских правил обнаружения в настоящее время не поддерживается в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="32ca9-189">The allow or block action for custom detection rules is currently not supported on Microsoft 365 Defender.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="32ca9-190">5. За установите область действия правила.</span><span class="sxs-lookup"><span data-stu-id="32ca9-190">5. Set the rule scope.</span></span>
<span data-ttu-id="32ca9-191">Установите область, чтобы указать, на какие устройства распространяется правило.</span><span class="sxs-lookup"><span data-stu-id="32ca9-191">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="32ca9-192">Область влияет на правила проверки устройств и не влияет на правила, которые проверяют только почтовые ящики и учетные записи пользователей или удостоверения.</span><span class="sxs-lookup"><span data-stu-id="32ca9-192">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="32ca9-193">При настройке области можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="32ca9-193">When setting the scope, you can select:</span></span>

- <span data-ttu-id="32ca9-194">Все устройства</span><span class="sxs-lookup"><span data-stu-id="32ca9-194">All devices</span></span>
- <span data-ttu-id="32ca9-195">Конкретные группы устройств</span><span class="sxs-lookup"><span data-stu-id="32ca9-195">Specific device groups</span></span>

<span data-ttu-id="32ca9-196">Запрашиваются только данные с устройств в области.</span><span class="sxs-lookup"><span data-stu-id="32ca9-196">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="32ca9-197">Кроме того, действия будут предприняты только на этих устройствах.</span><span class="sxs-lookup"><span data-stu-id="32ca9-197">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="32ca9-198">6. Просмотрите и включите правило.</span><span class="sxs-lookup"><span data-stu-id="32ca9-198">6. Review and turn on the rule.</span></span>
<span data-ttu-id="32ca9-199">После проверки правила выберите **"Создать",** чтобы сохранить его.</span><span class="sxs-lookup"><span data-stu-id="32ca9-199">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="32ca9-200">Настраиваемые правила обнаружения немедленно выполняется.</span><span class="sxs-lookup"><span data-stu-id="32ca9-200">The custom detection rule immediately runs.</span></span> <span data-ttu-id="32ca9-201">Он запускается снова в зависимости от настроенной частоты проверки совпадений, создания оповещений и реагировать на них.</span><span class="sxs-lookup"><span data-stu-id="32ca9-201">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="32ca9-202">Управление существующими пользовательскими правилами обнаружения</span><span class="sxs-lookup"><span data-stu-id="32ca9-202">Manage existing custom detection rules</span></span>
<span data-ttu-id="32ca9-203">Вы можете просмотреть список существующих пользовательских правил обнаружения, проверить их предыдущие запуски и просмотреть оповещения, которые они сработали.</span><span class="sxs-lookup"><span data-stu-id="32ca9-203">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="32ca9-204">Вы также можете запустить правило по запросу и изменить его.</span><span class="sxs-lookup"><span data-stu-id="32ca9-204">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="32ca9-205">Просмотр существующих правил</span><span class="sxs-lookup"><span data-stu-id="32ca9-205">View existing rules</span></span>

<span data-ttu-id="32ca9-206">Чтобы просмотреть все существующие пользовательские правила обнаружения, перейдите к  >  **настраиваемой охоте на обнаружения.**</span><span class="sxs-lookup"><span data-stu-id="32ca9-206">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="32ca9-207">На странице перечислены все правила со следующими сведениями о запуске:</span><span class="sxs-lookup"><span data-stu-id="32ca9-207">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="32ca9-208">**Последний запуск**— когда правило было в последний раз запускаться для проверки совпадений запросов и создания оповещений</span><span class="sxs-lookup"><span data-stu-id="32ca9-208">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="32ca9-209">**Состояние последнего запуска**— успешно ли прошло правило</span><span class="sxs-lookup"><span data-stu-id="32ca9-209">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="32ca9-210">**Следующий запуск**— следующий запланированный запуск</span><span class="sxs-lookup"><span data-stu-id="32ca9-210">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="32ca9-211">**Состояние**— было ли правило включено или отключено</span><span class="sxs-lookup"><span data-stu-id="32ca9-211">**Status**—whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="32ca9-212">Просмотр сведений о правиле, изменение правила и правило запуска</span><span class="sxs-lookup"><span data-stu-id="32ca9-212">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="32ca9-213">Чтобы просмотреть всесторонние сведения о настраиваемом правиле обнаружения, перейдите к настраиваемой охоте на обнаружения  >   и выберите имя правила.</span><span class="sxs-lookup"><span data-stu-id="32ca9-213">To view comprehensive information about a custom detection rule, go to **Hunting** > **Custom detections** and then select the name of rule.</span></span> <span data-ttu-id="32ca9-214">Затем можно просмотреть общие сведения о правиле, включая сведения о состоянии и области его запуска.</span><span class="sxs-lookup"><span data-stu-id="32ca9-214">You can then view general information about the rule, including information its run status and scope.</span></span> <span data-ttu-id="32ca9-215">На странице также содержится список инициированных оповещений и действий.</span><span class="sxs-lookup"><span data-stu-id="32ca9-215">The page also provides the list of triggered alerts and actions.</span></span>

<span data-ttu-id="32ca9-216">![Страница сведений о настраиваемом правиле обнаружения](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="32ca9-216">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="32ca9-217">*Сведения о настраиваемом правиле обнаружения*</span><span class="sxs-lookup"><span data-stu-id="32ca9-217">*Custom detection rule details*</span></span>

<span data-ttu-id="32ca9-218">На этой странице также можно сделать следующие действия с правилом:</span><span class="sxs-lookup"><span data-stu-id="32ca9-218">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="32ca9-219">**Запустите** правило немедленно.</span><span class="sxs-lookup"><span data-stu-id="32ca9-219">**Run**—run the rule immediately.</span></span> <span data-ttu-id="32ca9-220">Это также сбрасывает интервал для следующего запуска.</span><span class="sxs-lookup"><span data-stu-id="32ca9-220">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="32ca9-221">**Изменение**— изменение правила без изменения запроса</span><span class="sxs-lookup"><span data-stu-id="32ca9-221">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="32ca9-222">**Изменение запроса**— изменение запроса в режиме расширенных поисков</span><span class="sxs-lookup"><span data-stu-id="32ca9-222">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="32ca9-223">**Включить**  /  **Отключение**— включите правило или остановите его работу</span><span class="sxs-lookup"><span data-stu-id="32ca9-223">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="32ca9-224">**Удаление**— отключите правило и удалите его</span><span class="sxs-lookup"><span data-stu-id="32ca9-224">**Delete**—turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="32ca9-225">Просмотр инициированных оповещений и управление ими</span><span class="sxs-lookup"><span data-stu-id="32ca9-225">View and manage triggered alerts</span></span>

<span data-ttu-id="32ca9-226">На экране сведений о правиле (**поиск** пользовательских обнаружений  >    >  **[имя правила]**) перейдите к триггерным оповещениям, в котором перечислены оповещения, созданные совпадениями с правилом.</span><span class="sxs-lookup"><span data-stu-id="32ca9-226">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to  **Triggered alerts**, which lists the alerts generated by matches to the rule.</span></span> <span data-ttu-id="32ca9-227">Выберите оповещение, чтобы просмотреть подробные сведения о нем и принять следующие меры:</span><span class="sxs-lookup"><span data-stu-id="32ca9-227">Select an alert to view detailed information about it and take the following actions:</span></span>

- <span data-ttu-id="32ca9-228">Управление оповещением путем настройки его состояния и классификации (true или false alert)</span><span class="sxs-lookup"><span data-stu-id="32ca9-228">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="32ca9-229">Связывать оповещение с инцидентом</span><span class="sxs-lookup"><span data-stu-id="32ca9-229">Link the alert to an incident</span></span>
- <span data-ttu-id="32ca9-230">Запуск запроса, который инициирует оповещение при повышенном поиске</span><span class="sxs-lookup"><span data-stu-id="32ca9-230">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="32ca9-231">Проверка действий</span><span class="sxs-lookup"><span data-stu-id="32ca9-231">Review actions</span></span>
<span data-ttu-id="32ca9-232">In the rule details screen (**Hunting**  >  **Custom detections**  >  **[Rule name]**), go to **Triggered actions**, which lists the actions taken based on matches to the rule.</span><span class="sxs-lookup"><span data-stu-id="32ca9-232">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions**, which lists the actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="32ca9-233">Чтобы быстро просмотреть сведения и принять меры к элементу в таблице, используйте столбец выбора [&#10003;] в левой части таблицы.</span><span class="sxs-lookup"><span data-stu-id="32ca9-233">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="see-also"></a><span data-ttu-id="32ca9-234">См. также</span><span class="sxs-lookup"><span data-stu-id="32ca9-234">See also</span></span>
- [<span data-ttu-id="32ca9-235">Обзор настраиваемых обнаружений</span><span class="sxs-lookup"><span data-stu-id="32ca9-235">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="32ca9-236">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="32ca9-236">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="32ca9-237">Познакомьтесь с языком запросов расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="32ca9-237">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="32ca9-238">Перенос запросов на расширенный поиск из Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="32ca9-238">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mdatp.md)
