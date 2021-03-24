---
title: Создание и управление пользовательскими правилами обнаружения в Microsoft 365 Defender
description: Узнайте, как создавать и управлять пользовательскими правилами обнаружения на основе расширенных запросов на охоту
keywords: передовая охота, охота на угрозы, охота на киберугрозы, защита от угроз Майкрософт, Microsoft 365, mtp, m365, поиск, запрос, телеметрия, пользовательские обнаружения, правила, схема, кусто, Microsoft 365, Microsoft Threat Protection, RBAC, разрешения, ATP Защитника Майкрософт
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9699b5e2bc2e33b94795b7c23bd3f34f0383a8cc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068980"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="1db47-104">Создание и управление пользовательскими правилами обнаружения</span><span class="sxs-lookup"><span data-stu-id="1db47-104">Create and manage custom detections rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1db47-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1db47-105">**Applies to:**</span></span>
- <span data-ttu-id="1db47-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1db47-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="1db47-107">Настраиваемые правила обнаружения — это правила, которые можно разработать и настроить с помощью [расширенных запросов](advanced-hunting-overview.md) на охоту.</span><span class="sxs-lookup"><span data-stu-id="1db47-107">Custom detection rules are rules you can design and tweak using [advanced hunting](advanced-hunting-overview.md) queries.</span></span> <span data-ttu-id="1db47-108">Эти правила позволяет активно отслеживать различные события и состояния системы, в том числе предполагаемые нарушения и неправильные конечные точки.</span><span class="sxs-lookup"><span data-stu-id="1db47-108">These rules let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="1db47-109">Вы можете настроить их для запуска с регулярными интервалами, создавая оповещения и принимая ответные действия при совпадениях.</span><span class="sxs-lookup"><span data-stu-id="1db47-109">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="1db47-110">Необходимые разрешения для управления пользовательскими обнаружениями</span><span class="sxs-lookup"><span data-stu-id="1db47-110">Required permissions for managing custom detections</span></span>

<span data-ttu-id="1db47-111">Чтобы управлять пользовательскими обнаружениями, вам должна быть назначена одна из этих ролей:</span><span class="sxs-lookup"><span data-stu-id="1db47-111">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="1db47-112">**Администратор безопасности**— пользователи с этой ролью [Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) могут управлять настройками безопасности в центре безопасности Microsoft 365 и других порталах и службах.</span><span class="sxs-lookup"><span data-stu-id="1db47-112">**Security administrator**—Users with this [Azure Active Directory role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage security settings in Microsoft 365 security center and other portals and services.</span></span>

- <span data-ttu-id="1db47-113">**Оператор безопасности**— Пользователи с этой ролью [Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) могут управлять оповещениями и иметь глобальный доступ только для чтения к функциям, связанным с безопасностью, включая всю информацию в центре безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1db47-113">**Security operator**—Users with this [Azure Active Directory role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage alerts and have global read-only access to security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="1db47-114">Эта роль достаточна для управления пользовательскими обнаружениями только в том случае, если управление доступом на основе ролей (RBAC) отключено в Microsoft Defender для endpoint.</span><span class="sxs-lookup"><span data-stu-id="1db47-114">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="1db47-115">Если настроена RBAC, необходимо также  разрешение на управление настройками безопасности для Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1db47-115">If you have RBAC configured, you also need the **manage security settings** permission for Defender for Endpoint.</span></span>

<span data-ttu-id="1db47-116">Чтобы управлять требуемой разрешениями, **глобальный администратор** может:</span><span class="sxs-lookup"><span data-stu-id="1db47-116">To manage required permissions, a **global administrator** can:</span></span>

- <span data-ttu-id="1db47-117">**Назначьте администратору безопасности** или **оператору** безопасности роль в центре администрирования [Microsoft 365](https://admin.microsoft.com/) под руководством **администратора**  >  **службы безопасности ролей.**</span><span class="sxs-lookup"><span data-stu-id="1db47-117">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="1db47-118">Проверьте параметры RBAC для Защитника Майкрософт для конечной точки в Центре безопасности [Защитника Майкрософт](https://securitycenter.windows.com/) в роли **параметров**  >    >  **разрешений.**</span><span class="sxs-lookup"><span data-stu-id="1db47-118">Check RBAC settings for Microsoft Defender for Endpoint in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="1db47-119">Выберите соответствующую роль, чтобы назначить **разрешение на управление настройками безопасности.**</span><span class="sxs-lookup"><span data-stu-id="1db47-119">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="1db47-120">Для управления пользовательскими  обнаружениями операторам  безопасности потребуется разрешение на управление настройками безопасности в Microsoft Defender для конечной точки, если включен RBAC.</span><span class="sxs-lookup"><span data-stu-id="1db47-120">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender for Endpoint if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="1db47-121">Создание настраиваемой нормы обнаружения</span><span class="sxs-lookup"><span data-stu-id="1db47-121">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="1db47-122">1. Подготовка запроса.</span><span class="sxs-lookup"><span data-stu-id="1db47-122">1. Prepare the query.</span></span>

<span data-ttu-id="1db47-123">В центре безопасности Microsoft 365 перейдите в **расширенный** поиск и выберите существующий запрос или создайте новый запрос.</span><span class="sxs-lookup"><span data-stu-id="1db47-123">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="1db47-124">При использовании нового запроса запустите запрос для выявления ошибок и понимания возможных результатов.</span><span class="sxs-lookup"><span data-stu-id="1db47-124">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="1db47-125">Чтобы служба не возвращала слишком много оповещений, каждое правило ограничивается созданием только 100 оповещений при каждом запуске.</span><span class="sxs-lookup"><span data-stu-id="1db47-125">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="1db47-126">Перед созданием правила необходимо настроить запрос, чтобы не предупреждать о нормальной ежедневной активности.</span><span class="sxs-lookup"><span data-stu-id="1db47-126">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="1db47-127">Необходимые столбцы в результатах запроса</span><span class="sxs-lookup"><span data-stu-id="1db47-127">Required columns in the query results</span></span>
<span data-ttu-id="1db47-128">Чтобы создать настраиваемую норму обнаружения, запрос должен вернуть следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="1db47-128">To create a custom detection rule, the query must return the following columns:</span></span>

- <span data-ttu-id="1db47-129">`Timestamp`— используется для набора времени для генерируемых оповещений</span><span class="sxs-lookup"><span data-stu-id="1db47-129">`Timestamp`—used to set the timestamp for generated alerts</span></span>
- <span data-ttu-id="1db47-130">`ReportId`— позволяет искать исходные записи</span><span class="sxs-lookup"><span data-stu-id="1db47-130">`ReportId`—enables lookups for the original records</span></span>
- <span data-ttu-id="1db47-131">Один из следующих столбцов, определяя конкретные устройства, пользователей или почтовые ящики:</span><span class="sxs-lookup"><span data-stu-id="1db47-131">One of the following columns that identify specific devices, users, or mailboxes:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="1db47-132">`SenderFromAddress` (отправитель конверта или Return-Path адрес)</span><span class="sxs-lookup"><span data-stu-id="1db47-132">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="1db47-133">`SenderMailFromAddress` (адрес отправитель, отображаемый клиентом электронной почты)</span><span class="sxs-lookup"><span data-stu-id="1db47-133">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
><span data-ttu-id="1db47-134">Поддержка дополнительных сущностям будет добавлена по мере того, как новые таблицы будут добавлены в [расширенный схему охоты.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="1db47-134">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="1db47-135">Простые запросы, например запросы, которые не используют оператор или оператор для настройки или агрегированных результатов, обычно возвращают `project` `summarize` эти общие столбцы.</span><span class="sxs-lookup"><span data-stu-id="1db47-135">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="1db47-136">Существуют различные способы обеспечения более сложных запросов, возвращая эти столбцы.</span><span class="sxs-lookup"><span data-stu-id="1db47-136">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="1db47-137">Например, если вы предпочитаете агрегировать и считать по сущности в столбце, например, вы можете вернуться и получить его из последнего события с участием каждого `DeviceId` `Timestamp` `ReportId` уникального `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="1db47-137">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` and `ReportId` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="1db47-138">В приведенной ниже примере запросов подсчитываются количество уникальных устройств () с обнаружениями антивирусов и используется этот подсчет, чтобы найти только устройства с более чем `DeviceId` пятью обнаружениями.</span><span class="sxs-lookup"><span data-stu-id="1db47-138">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="1db47-139">Чтобы вернуть последнюю и `Timestamp` `ReportId` соответствующую, он использует оператора с `summarize` `arg_max` функцией.</span><span class="sxs-lookup"><span data-stu-id="1db47-139">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="1db47-140">Для улучшения производительности запроса установите фильтр времени, который соответствует вашей назначенной частоте выполнения для правила.</span><span class="sxs-lookup"><span data-stu-id="1db47-140">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="1db47-141">Так как наименее частый запуск происходит _каждые 24_ часа, фильтрация за прошедший день будет охватывать все новые данные.</span><span class="sxs-lookup"><span data-stu-id="1db47-141">Since the least frequent run is _every 24 hours_, filtering for the past day will cover all new data.</span></span>

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="1db47-142">2. Создайте новое правило и укажу сведения об оповещении.</span><span class="sxs-lookup"><span data-stu-id="1db47-142">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="1db47-143">С помощью запроса в редакторе запроса выберите **правило Создать** обнаружение и укажите следующие сведения оповещения:</span><span class="sxs-lookup"><span data-stu-id="1db47-143">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="1db47-144">**Имя обнаружения**— имя правила обнаружения</span><span class="sxs-lookup"><span data-stu-id="1db47-144">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="1db47-145">**Частота**— интервал для выполнения запроса и принятия действий.</span><span class="sxs-lookup"><span data-stu-id="1db47-145">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="1db47-146">Дополнительные рекомендации см. ниже</span><span class="sxs-lookup"><span data-stu-id="1db47-146">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="1db47-147">**Предупреждение название**— заголовок, отображаемый с оповещениями, инициированными правилом</span><span class="sxs-lookup"><span data-stu-id="1db47-147">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="1db47-148">**Серьезность**— потенциальный риск компонента или действия, определяемого правилом</span><span class="sxs-lookup"><span data-stu-id="1db47-148">**Severity**—potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="1db47-149">**Категория —** компонент угрозы или действия, которые определены правилом</span><span class="sxs-lookup"><span data-stu-id="1db47-149">**Category**—threat component or activity identified by the rule</span></span>
- <span data-ttu-id="1db47-150">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="1db47-150">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="1db47-151">Этот раздел скрыт для определенных категорий оповещений, в том числе вредоносных программ, программ-вымогателей, подозрительных действий и нежелательного программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="1db47-151">This section is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="1db47-152">**Описание**— дополнительные сведения о компоненте или действии, выявленных правилом</span><span class="sxs-lookup"><span data-stu-id="1db47-152">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="1db47-153">**Рекомендуемые действия**— дополнительные действия, которые могут приниматься ответчиками в ответ на предупреждение</span><span class="sxs-lookup"><span data-stu-id="1db47-153">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="1db47-154">Частота правил</span><span class="sxs-lookup"><span data-stu-id="1db47-154">Rule frequency</span></span>
<span data-ttu-id="1db47-155">При сохранения или редактировании нового правила выполняется проверка совпадений за последние 30 дней данных.</span><span class="sxs-lookup"><span data-stu-id="1db47-155">When you save or edit a new rule, it runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="1db47-156">Затем правило выполняется снова с фиксированными интервалами, применяя длительность обратного воспроизведения в зависимости от частоты, которая вы выбираете:</span><span class="sxs-lookup"><span data-stu-id="1db47-156">The rule then runs again at fixed intervals, applying a lookback duration based on the frequency you choose:</span></span>

- <span data-ttu-id="1db47-157">**Каждые 24 часа**— выполняется каждые 24 часа, проверяя данные за последние 30 дней</span><span class="sxs-lookup"><span data-stu-id="1db47-157">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="1db47-158">**Каждые 12 часов**— выполняется каждые 12 часов, проверяя данные за последние 24 часа</span><span class="sxs-lookup"><span data-stu-id="1db47-158">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="1db47-159">**Каждые 3 часа**— выполняется каждые 3 часа, проверяя данные за последние 6 часов</span><span class="sxs-lookup"><span data-stu-id="1db47-159">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="1db47-160">**Каждый** час — выполняется почасовая проверка данных за последние 2 часа.</span><span class="sxs-lookup"><span data-stu-id="1db47-160">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

>[!TIP]
> <span data-ttu-id="1db47-161">Соответствие фильтрам времени в запросе с длительностью отката.</span><span class="sxs-lookup"><span data-stu-id="1db47-161">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="1db47-162">Результаты за пределами длительности поиска игнорируются.</span><span class="sxs-lookup"><span data-stu-id="1db47-162">Results outside of the lookback duration are ignored.</span></span>  

<span data-ttu-id="1db47-163">Выберите частоту, которая соответствует точному мониторингу обнаружения.</span><span class="sxs-lookup"><span data-stu-id="1db47-163">Select the frequency that matches how closely you want to monitor detections.</span></span> <span data-ttu-id="1db47-164">Рассмотрите возможности организации для реагирования на оповещения.</span><span class="sxs-lookup"><span data-stu-id="1db47-164">Consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="1db47-165">3. Выберите сущностями с влиянием.</span><span class="sxs-lookup"><span data-stu-id="1db47-165">3. Choose the impacted entities.</span></span>
<span data-ttu-id="1db47-166">Определите столбцы в результатах запроса, в которых ожидается найти основную затронутую или затрагиваемую сущность.</span><span class="sxs-lookup"><span data-stu-id="1db47-166">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="1db47-167">Например, запрос может возвращать адреса отправитель `SenderFromAddress` (или) и `SenderMailFromAddress` `RecipientEmailAddress` получатель ().</span><span class="sxs-lookup"><span data-stu-id="1db47-167">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="1db47-168">Определение того, какие из этих столбцов представляют основную объектную сущность, помогает службе агрегировать соответствующие оповещения, соотносить инциденты и целевые действия реагирования.</span><span class="sxs-lookup"><span data-stu-id="1db47-168">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="1db47-169">Для каждого типа сущности (почтовый ящик, пользователь или устройство) можно выбрать только один столбец.</span><span class="sxs-lookup"><span data-stu-id="1db47-169">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="1db47-170">Столбцы, не возвращенные запросом, не могут быть выбраны.</span><span class="sxs-lookup"><span data-stu-id="1db47-170">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="1db47-171">4. Укажите действия.</span><span class="sxs-lookup"><span data-stu-id="1db47-171">4. Specify actions.</span></span>
<span data-ttu-id="1db47-172">Ваше пользовательское правило обнаружения может автоматически принимать действия на устройствах, файлах или пользователях, возвращаемые запросом.</span><span class="sxs-lookup"><span data-stu-id="1db47-172">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="1db47-173">Действия на устройствах</span><span class="sxs-lookup"><span data-stu-id="1db47-173">Actions on devices</span></span>
<span data-ttu-id="1db47-174">Эти действия применяются к устройствам в `DeviceId` столбце результатов запроса:</span><span class="sxs-lookup"><span data-stu-id="1db47-174">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="1db47-175">**Изолировать устройство**— использует Microsoft Defender для конечной точки, чтобы применять полную изоляцию сети, не мешая устройству подключаться к любому приложению или службе.</span><span class="sxs-lookup"><span data-stu-id="1db47-175">**Isolate device**—uses Microsoft Defender for Endpoint to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="1db47-176">Дополнительные информацию об изоляции компьютера с конечными точками в Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="1db47-176">Learn more about Microsoft Defender for Endpoint machine isolation</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="1db47-177">**Сбор пакета исследований**— сбор сведений об устройствах в файле ZIP.</span><span class="sxs-lookup"><span data-stu-id="1db47-177">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="1db47-178">Дополнительные информацию о пакете исследований Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1db47-178">Learn more about the Microsoft Defender for Endpoint investigation package</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="1db47-179">**Запуск антивирусного сканирования**— выполняет полное Защитник Windows антивирусное сканирование на устройстве</span><span class="sxs-lookup"><span data-stu-id="1db47-179">**Run antivirus scan**—performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="1db47-180">**Инициировать** расследование — [инициирует автоматическое расследование](m365d-autoir.md) на устройстве</span><span class="sxs-lookup"><span data-stu-id="1db47-180">**Initiate investigation**—initiates an [automated investigation](m365d-autoir.md) on the device</span></span>
- <span data-ttu-id="1db47-181">**Ограничение выполнения приложения**— устанавливает ограничения для устройства, позволяющее запускать только те файлы, которые подписаны сертификатом, выданным Корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1db47-181">**Restrict app execution**—sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="1db47-182">Дополнительные новости об ограничениях приложений в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1db47-182">Learn more about app restrictions with Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="1db47-183">Действия в файлах</span><span class="sxs-lookup"><span data-stu-id="1db47-183">Actions on files</span></span>
<span data-ttu-id="1db47-184">При выборе можно применить действие  карантиного файла к файлам в столбце , или столбце `SHA1` `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="1db47-184">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="1db47-185">Это действие удаляет файл из текущего расположения и помещает копию в карантин.</span><span class="sxs-lookup"><span data-stu-id="1db47-185">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="1db47-186">Действия для пользователей</span><span class="sxs-lookup"><span data-stu-id="1db47-186">Actions on users</span></span>
<span data-ttu-id="1db47-187">При выборе пользователь Mark как **скомпрометированное** действие будет приниматься для пользователей в столбце или столбце `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="1db47-187">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="1db47-188">Это действие задает пользователям уровень риска до "высокого" в Azure Active Directory, запуская соответствующие [политики защиты удостоверений.](/azure/active-directory/identity-protection/overview-identity-protection)</span><span class="sxs-lookup"><span data-stu-id="1db47-188">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="1db47-189">Действие разрешить или заблокировать для пользовательских правил обнаружения в настоящее время не поддерживается в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="1db47-189">The allow or block action for custom detection rules is currently not supported on Microsoft 365 Defender.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="1db47-190">5. Установите область правил.</span><span class="sxs-lookup"><span data-stu-id="1db47-190">5. Set the rule scope.</span></span>
<span data-ttu-id="1db47-191">Установите область, чтобы указать, какие устройства охвачены правилом.</span><span class="sxs-lookup"><span data-stu-id="1db47-191">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="1db47-192">Область влияет на правила проверки устройств и не влияет на правила, которые проверяют только почтовые ящики и учетные записи пользователей или удостоверения.</span><span class="sxs-lookup"><span data-stu-id="1db47-192">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="1db47-193">При настройке области можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="1db47-193">When setting the scope, you can select:</span></span>

- <span data-ttu-id="1db47-194">Все устройства</span><span class="sxs-lookup"><span data-stu-id="1db47-194">All devices</span></span>
- <span data-ttu-id="1db47-195">Конкретные группы устройств</span><span class="sxs-lookup"><span data-stu-id="1db47-195">Specific device groups</span></span>

<span data-ttu-id="1db47-196">Запрашиваются только данные с устройств в области.</span><span class="sxs-lookup"><span data-stu-id="1db47-196">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="1db47-197">Кроме того, действия будут приниматься только на этих устройствах.</span><span class="sxs-lookup"><span data-stu-id="1db47-197">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="1db47-198">6. Просмотрите и включите правило.</span><span class="sxs-lookup"><span data-stu-id="1db47-198">6. Review and turn on the rule.</span></span>
<span data-ttu-id="1db47-199">После просмотра правила выберите **Создать, чтобы** сохранить его.</span><span class="sxs-lookup"><span data-stu-id="1db47-199">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="1db47-200">Правило настраиваемой диагностики немедленно запускается.</span><span class="sxs-lookup"><span data-stu-id="1db47-200">The custom detection rule immediately runs.</span></span> <span data-ttu-id="1db47-201">Он снова запускается на основе настроенной частоты для проверки совпадений, создания оповещений и реагировать на действия.</span><span class="sxs-lookup"><span data-stu-id="1db47-201">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>


>[!Important] 
><span data-ttu-id="1db47-202">Настраиваемые обнаружения следует регулярно проверять на эффективность и эффективность.</span><span class="sxs-lookup"><span data-stu-id="1db47-202">Custom detections should be regularly reviewed for efficiency and effectiveness.</span></span> <span data-ttu-id="1db47-203">Чтобы убедиться, что вы создаете обнаружения, которые вызывают истинные оповещения, необходимо время, чтобы просмотреть существующие пользовательские обнаружения, следуя шагам в управлении существующими пользовательскими [правилами обнаружения.](#manage-existing-custom-detection-rules)</span><span class="sxs-lookup"><span data-stu-id="1db47-203">To make sure you are creating detections that trigger true alerts, take time to review your existing custom detections by following the steps in [Manage existing custom detection rules](#manage-existing-custom-detection-rules).</span></span> <br>  
<span data-ttu-id="1db47-204">Вы поддерживаете контроль над широкостью или спецификой настраиваемых обнаружений, поэтому любые ложные оповещения, созданные пользовательскими обнаружениями, могут указывать на необходимость изменения определенных параметров правил.</span><span class="sxs-lookup"><span data-stu-id="1db47-204">You maintain control over the broadness or specificity of your custom detections so any false alerts generated by custom detections might indicate a need to modify certain parameters of the rules.</span></span>


## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="1db47-205">Управление существующими пользовательскими правилами обнаружения</span><span class="sxs-lookup"><span data-stu-id="1db47-205">Manage existing custom detection rules</span></span>
<span data-ttu-id="1db47-206">Вы можете просмотреть список существующих пользовательских правил обнаружения, проверить их предыдущие запуски и просмотреть оповещения, которые они вызвали.</span><span class="sxs-lookup"><span data-stu-id="1db47-206">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="1db47-207">Вы также можете запустить правило по запросу и изменить его.</span><span class="sxs-lookup"><span data-stu-id="1db47-207">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="1db47-208">Просмотр существующих правил</span><span class="sxs-lookup"><span data-stu-id="1db47-208">View existing rules</span></span>

<span data-ttu-id="1db47-209">Чтобы просмотреть все существующие пользовательские правила обнаружения, перейдите к **обнаружениям Hunting**  >  **Custom.**</span><span class="sxs-lookup"><span data-stu-id="1db47-209">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="1db47-210">На странице перечислены все правила со следующими сведениями о запуске:</span><span class="sxs-lookup"><span data-stu-id="1db47-210">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="1db47-211">**Последний запуск**— при последнем запуске правила для проверки совпадений запросов и создания оповещений</span><span class="sxs-lookup"><span data-stu-id="1db47-211">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="1db47-212">**Состояние последнего запуска**— успешно ли выполнило правило</span><span class="sxs-lookup"><span data-stu-id="1db47-212">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="1db47-213">**Следующий запуск**— следующий запланированный запуск</span><span class="sxs-lookup"><span data-stu-id="1db47-213">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="1db47-214">**Состояние**— независимо от того, включено или отключено правило</span><span class="sxs-lookup"><span data-stu-id="1db47-214">**Status**—whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="1db47-215">Просмотр сведений о правилах, изменение правила и правила запуска</span><span class="sxs-lookup"><span data-stu-id="1db47-215">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="1db47-216">Чтобы просмотреть всестороннюю информацию о настраиваемом правиле обнаружения, перейдите к **обнаружению Hunting** Custom и выберите  >   имя правила.</span><span class="sxs-lookup"><span data-stu-id="1db47-216">To view comprehensive information about a custom detection rule, go to **Hunting** > **Custom detections** and then select the name of rule.</span></span> <span data-ttu-id="1db47-217">Затем можно просмотреть общие сведения о правиле, включая сведения о состоянии и области запуска.</span><span class="sxs-lookup"><span data-stu-id="1db47-217">You can then view general information about the rule, including information its run status and scope.</span></span> <span data-ttu-id="1db47-218">На странице также содержится список срабатывуемого оповещений и действий.</span><span class="sxs-lookup"><span data-stu-id="1db47-218">The page also provides the list of triggered alerts and actions.</span></span>

<span data-ttu-id="1db47-219">![Страница пользовательских сведений о правилах обнаружения](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="1db47-219">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="1db47-220">*Пользовательские сведения о правилах обнаружения*</span><span class="sxs-lookup"><span data-stu-id="1db47-220">*Custom detection rule details*</span></span>

<span data-ttu-id="1db47-221">На этой странице также можно принять следующие действия по правилу:</span><span class="sxs-lookup"><span data-stu-id="1db47-221">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="1db47-222">**Запустите**— запустите правило немедленно.</span><span class="sxs-lookup"><span data-stu-id="1db47-222">**Run**—run the rule immediately.</span></span> <span data-ttu-id="1db47-223">Это также сбрасывает интервал для следующего запуска.</span><span class="sxs-lookup"><span data-stu-id="1db47-223">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="1db47-224">**Изменение**— изменение правила без изменения запроса</span><span class="sxs-lookup"><span data-stu-id="1db47-224">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="1db47-225">**Изменение запроса**— изменение запроса в продвинутой охоте</span><span class="sxs-lookup"><span data-stu-id="1db47-225">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="1db47-226">**Включаем**  /  **Отключите** правило или остановите его работу</span><span class="sxs-lookup"><span data-stu-id="1db47-226">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="1db47-227">**Удаление**— отключите правило и удалите его</span><span class="sxs-lookup"><span data-stu-id="1db47-227">**Delete**—turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="1db47-228">Просмотр и управление срабатывными оповещениями</span><span class="sxs-lookup"><span data-stu-id="1db47-228">View and manage triggered alerts</span></span>

<span data-ttu-id="1db47-229">На экране сведений правила **(Hunting**  >  **Custom detections**[Rule name] ) перейдите к триггерным оповещениям, в которых перечислены оповещения, созданные совпадениями,  >  к правилу. </span><span class="sxs-lookup"><span data-stu-id="1db47-229">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to  **Triggered alerts**, which lists the alerts generated by matches to the rule.</span></span> <span data-ttu-id="1db47-230">Выберите оповещение, чтобы просмотреть подробные сведения о нем и принять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="1db47-230">Select an alert to view detailed information about it and take the following actions:</span></span>

- <span data-ttu-id="1db47-231">Управление оповещением путем настройки его состояния и классификации (true или false alert)</span><span class="sxs-lookup"><span data-stu-id="1db47-231">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="1db47-232">Ссылка оповещений на инцидент</span><span class="sxs-lookup"><span data-stu-id="1db47-232">Link the alert to an incident</span></span>
- <span data-ttu-id="1db47-233">Запустите запрос, который вызвал оповещение при продвинутой охоте</span><span class="sxs-lookup"><span data-stu-id="1db47-233">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="1db47-234">Проверка действий</span><span class="sxs-lookup"><span data-stu-id="1db47-234">Review actions</span></span>
<span data-ttu-id="1db47-235">В экране сведений правила **(Hunting**  >  **Custom detections**  >  **[Rule name]),** перейдите к **triggered actions**, в котором перечислены действия, принятые на основе совпадений с правилом.</span><span class="sxs-lookup"><span data-stu-id="1db47-235">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions**, which lists the actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="1db47-236">Чтобы быстро просмотреть сведения и принять меры по элементу в таблице, используйте столбец выбора [&#10003;] слева от таблицы.</span><span class="sxs-lookup"><span data-stu-id="1db47-236">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="see-also"></a><span data-ttu-id="1db47-237">См. также</span><span class="sxs-lookup"><span data-stu-id="1db47-237">See also</span></span>
- [<span data-ttu-id="1db47-238">Обзор настраиваемых обнаружений</span><span class="sxs-lookup"><span data-stu-id="1db47-238">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="1db47-239">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="1db47-239">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1db47-240">Познакомьтесь с языком запросов расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="1db47-240">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="1db47-241">Перенос расширенных запросов на охоту из Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1db47-241">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
