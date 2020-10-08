---
title: Создание настраиваемых правил обнаружения в защите от угроз Майкрософт и управление ими
description: Узнайте, как создавать и управлять пользовательскими правилами обнаружения на основе расширенных запросов поиска.
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, пользовательские обнаружения, правила, схема, Кусто, Microsoft 365, защита от угроз Майкрософт, RBAC, разрешения, защитник Майкрософт
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: e3388bd0d3a7ac6afff0109eb80945d3ddc362fd
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198901"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="08921-104">Создание настраиваемых правил обнаружения и управление ими</span><span class="sxs-lookup"><span data-stu-id="08921-104">Create and manage custom detections rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="08921-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="08921-105">**Applies to:**</span></span>
- <span data-ttu-id="08921-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="08921-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="08921-107">Настраиваемые правила обнаружения — это правила, которые можно спроектировать и настроить с помощью [расширенных](advanced-hunting-overview.md) запросов поиска.</span><span class="sxs-lookup"><span data-stu-id="08921-107">Custom detection rules are rules you can design and tweak using [advanced hunting](advanced-hunting-overview.md) queries.</span></span> <span data-ttu-id="08921-108">Эти правила позволяют наблюдать за различными событиями и состояниями системы, включая невероятные действия и ненастроенные конечные точки.</span><span class="sxs-lookup"><span data-stu-id="08921-108">These rules let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="08921-109">Вы можете настроить их для запуска через определенные интервалы, создавая оповещения и отменяя действия ответа при обнаружении совпадений.</span><span class="sxs-lookup"><span data-stu-id="08921-109">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="08921-110">Необходимые разрешения для управления пользовательскими обнаружениями</span><span class="sxs-lookup"><span data-stu-id="08921-110">Required permissions for managing custom detections</span></span>

<span data-ttu-id="08921-111">Для управления пользовательскими обнаружениями необходимо назначить одну из этих ролей:</span><span class="sxs-lookup"><span data-stu-id="08921-111">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="08921-112">**Администратор безопасности**— пользователи с этой [ролью Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) могут управлять параметрами безопасности в центре безопасности Microsoft 365 и других порталах и службах.</span><span class="sxs-lookup"><span data-stu-id="08921-112">**Security administrator**—Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage security settings in Microsoft 365 security center and other portals and services.</span></span>

- <span data-ttu-id="08921-113">**Оператор безопасности**— пользователи с этой [ролью Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) могут управлять оповещениями и иметь глобальный доступ только для чтения к функциям, связанным с безопасностью, включая все сведения в центре безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="08921-113">**Security operator**—Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage alerts and have global read-only access to security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="08921-114">Эта роль достаточно для управления пользовательскими обнаружениями только в том случае, если управление доступом на основе ролей (RBAC) отключено в Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="08921-114">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender ATP.</span></span> <span data-ttu-id="08921-115">Если вы настроили RBAC, вам также потребуется разрешение на **Управление параметрами безопасности** для пакета ATP для защитника Microsoft.</span><span class="sxs-lookup"><span data-stu-id="08921-115">If you have RBAC configured, you also need the **manage security settings** permission for Microsoft Defender ATP.</span></span>

<span data-ttu-id="08921-116">Для управления необходимыми разрешениями **глобальный администратор** может:</span><span class="sxs-lookup"><span data-stu-id="08921-116">To manage required permissions, a **global administrator** can:</span></span>

- <span data-ttu-id="08921-117">Назначьте роль **администратора безопасности** или **оператора безопасности** в [центре администрирования Microsoft 365](https://admin.microsoft.com/) в разделе **Roles**  >  **администратор безопасности**ролей.</span><span class="sxs-lookup"><span data-stu-id="08921-117">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="08921-118">Проверьте параметры RBAC для защитника Майкрософт в [центре безопасности защитника Microsoft](https://securitycenter.windows.com/) в разделе **Параметры**  >  **разрешений**  >  **Roles**.</span><span class="sxs-lookup"><span data-stu-id="08921-118">Check RBAC settings for Microsoft Defender ATP in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="08921-119">Выберите соответствующую роль, чтобы назначить разрешение " **Управление параметрами безопасности** ".</span><span class="sxs-lookup"><span data-stu-id="08921-119">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="08921-120">Чтобы управлять пользовательскими обнаружениями, для **операторов безопасности** потребуется разрешение на **Управление параметрами безопасности** в защитнике Майкрософт, если параметр RBAC включен.</span><span class="sxs-lookup"><span data-stu-id="08921-120">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender ATP if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="08921-121">Создание настраиваемого правила обнаружения</span><span class="sxs-lookup"><span data-stu-id="08921-121">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="08921-122">1. Подготовьте запрос.</span><span class="sxs-lookup"><span data-stu-id="08921-122">1. Prepare the query.</span></span>

<span data-ttu-id="08921-123">В центре безопасности Microsoft 365 перейдите в раздел **Расширенный** Поиск и выберите существующий или создайте новый запрос.</span><span class="sxs-lookup"><span data-stu-id="08921-123">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="08921-124">При использовании нового запроса выполните запрос, чтобы выявить ошибки и понять возможные результаты.</span><span class="sxs-lookup"><span data-stu-id="08921-124">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="08921-125">Чтобы служба не возвращала слишком много оповещений, каждое правило ограничено созданием только 100 оповещений при каждом запуске.</span><span class="sxs-lookup"><span data-stu-id="08921-125">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="08921-126">Прежде чем создавать правило, необходимо настроить запрос, чтобы избежать оповещений о нормальных действиях в день.</span><span class="sxs-lookup"><span data-stu-id="08921-126">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="08921-127">Обязательные столбцы в результатах запроса</span><span class="sxs-lookup"><span data-stu-id="08921-127">Required columns in the query results</span></span>
<span data-ttu-id="08921-128">Чтобы создать настраиваемое правило обнаружения, запрос должен возвратить следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="08921-128">To create a custom detection rule, the query must return the following columns:</span></span>

- <span data-ttu-id="08921-129">`Timestamp`— используется для задания метки времени для созданных оповещений</span><span class="sxs-lookup"><span data-stu-id="08921-129">`Timestamp`—used to set the timestamp for generated alerts</span></span>
- <span data-ttu-id="08921-130">`ReportId`— включает подстановки для исходных записей</span><span class="sxs-lookup"><span data-stu-id="08921-130">`ReportId`—enables lookups for the original records</span></span>
- <span data-ttu-id="08921-131">Один из следующих столбцов, идентифицирующих определенные устройства, пользователей или почтовые ящики:</span><span class="sxs-lookup"><span data-stu-id="08921-131">One of the following columns that identify specific devices, users, or mailboxes:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="08921-132">`SenderFromAddress` (отправитель или обратный путь к конверту)</span><span class="sxs-lookup"><span data-stu-id="08921-132">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="08921-133">`SenderMailFromAddress` (адрес отправителя, отображаемый клиентом электронной почты)</span><span class="sxs-lookup"><span data-stu-id="08921-133">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
><span data-ttu-id="08921-134">Поддержка дополнительных сущностей будет добавлена при добавлении новых таблиц в [расширенную схему](advanced-hunting-schema-tables.md)подпоисков.</span><span class="sxs-lookup"><span data-stu-id="08921-134">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="08921-135">Простые запросы, например те, которые не используют `project` оператор OR `summarize` для настройки или агрегирования результатов, обычно возвращают эти общие столбцы.</span><span class="sxs-lookup"><span data-stu-id="08921-135">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="08921-136">Существует несколько способов, позволяющих обеспечить более сложные запросы возвращать эти столбцы.</span><span class="sxs-lookup"><span data-stu-id="08921-136">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="08921-137">Например, если вы предпочитаете объединить и подсчитать подсчета сущностями в столбце `DeviceId` , например, вы по-прежнему можете возвратить `Timestamp` и `ReportId` получать его из самого последнего события с использованием каждого уникального события `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="08921-137">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` and `ReportId` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="08921-138">Ниже приведен пример запроса, который подсчитывает количество уникальных устройств ( `DeviceId` ) с обнаружением вирусов и использует этот счетчик для поиска устройств с более чем пятью обнаружениями.</span><span class="sxs-lookup"><span data-stu-id="08921-138">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="08921-139">Для возврата последней `Timestamp` и соответствующей версии `ReportId` используется `summarize` оператор с `arg_max` функцией.</span><span class="sxs-lookup"><span data-stu-id="08921-139">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="08921-140">Для повышения производительности запросов установите фильтр времени, соответствующий предполагаемой частоте выполнения для правила.</span><span class="sxs-lookup"><span data-stu-id="08921-140">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="08921-141">Так как наименее часто выполняется _каждые 24 часа_, фильтрация за последний день будет охватывать все новые данные.</span><span class="sxs-lookup"><span data-stu-id="08921-141">Since the least frequent run is _every 24 hours_, filtering for the past day will cover all new data.</span></span>

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="08921-142">2. Создайте новое правило и предоставьте сведения об оповещении.</span><span class="sxs-lookup"><span data-stu-id="08921-142">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="08921-143">С помощью запроса в редакторе запросов выберите **создать правило обнаружения** и укажите следующие сведения об оповещении:</span><span class="sxs-lookup"><span data-stu-id="08921-143">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="08921-144">**Имя для обнаружения**— имя правила обнаружения</span><span class="sxs-lookup"><span data-stu-id="08921-144">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="08921-145">**Частота**— интервал для выполнения запроса и выполнения действия.</span><span class="sxs-lookup"><span data-stu-id="08921-145">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="08921-146">Дополнительные рекомендации приведены ниже</span><span class="sxs-lookup"><span data-stu-id="08921-146">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="08921-147">**Заголовок оповещения**— заголовок, отображаемый с оповещениями, инициированными правилом</span><span class="sxs-lookup"><span data-stu-id="08921-147">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="08921-148">**Severity**— потенциальный риск для компонента или действия, идентифицируемого правилом</span><span class="sxs-lookup"><span data-stu-id="08921-148">**Severity**—potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="08921-149">**Category (категория**) — компонент угрозы или действия, определяемые правилом</span><span class="sxs-lookup"><span data-stu-id="08921-149">**Category**—threat component or activity identified by the rule</span></span>
- <span data-ttu-id="08921-150">**МИТРЕ ATT&а методы**— одна или несколько способов атаки, определяемых правилом, описанных в разделе [МИТРЕ ATT&а Framework](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="08921-150">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="08921-151">Этот раздел скрыт для определенных категорий оповещений, в том числе вредоносных программ, программы-шантажистом, подозрительных действий и нежелательного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="08921-151">This section is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="08921-152">**Description (описание**) — Дополнительные сведения о компоненте или действии, определяемом правилом</span><span class="sxs-lookup"><span data-stu-id="08921-152">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="08921-153">**Рекомендуемые действия**— дополнительные действия, которые могут принимать ответчики в ответ на оповещение</span><span class="sxs-lookup"><span data-stu-id="08921-153">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="08921-154">Частота правил</span><span class="sxs-lookup"><span data-stu-id="08921-154">Rule frequency</span></span>
<span data-ttu-id="08921-155">При сохранении или изменении нового правила оно выполняется и проверяется на соответствие за прошедшие 30 дней данных.</span><span class="sxs-lookup"><span data-stu-id="08921-155">When you save or edit a new rule, it runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="08921-156">Затем правило выполняется повторно через фиксированные промежутки времени, в соответствии с выбираемой частотой лукбакк.</span><span class="sxs-lookup"><span data-stu-id="08921-156">The rule then runs again at fixed intervals, applying a lookback duration based on the frequency you choose:</span></span>

- <span data-ttu-id="08921-157">**Каждые 24 часа**— выполняется каждые 24 часа, проверяя данные за прошедшие 30 дней.</span><span class="sxs-lookup"><span data-stu-id="08921-157">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="08921-158">**Каждые 12 часов**— выполняется каждые 12 часов, выполняется проверка данных за прошедшие 24 часа</span><span class="sxs-lookup"><span data-stu-id="08921-158">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="08921-159">**Каждые 3 часа**— выполняется каждые 3 часа, проверка данных за прошедшие 6 часов</span><span class="sxs-lookup"><span data-stu-id="08921-159">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="08921-160">**Каждый час**— выполняется Почасовая проверка данных за прошлые 2 часа</span><span class="sxs-lookup"><span data-stu-id="08921-160">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

>[!TIP]
> <span data-ttu-id="08921-161">Сопоставьте фильтры времени в запросе с лукбакк длительностью.</span><span class="sxs-lookup"><span data-stu-id="08921-161">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="08921-162">Результаты за пресроком лукбакк игнорируются.</span><span class="sxs-lookup"><span data-stu-id="08921-162">Results outside of the lookback duration are ignored.</span></span>  

<span data-ttu-id="08921-163">Выберите частоту, которая соответствует тому, насколько вы хотите отслеживать обнаружение.</span><span class="sxs-lookup"><span data-stu-id="08921-163">Select the frequency that matches how closely you want to monitor detections.</span></span> <span data-ttu-id="08921-164">Рассмотрите способность Организации отвечать на оповещения.</span><span class="sxs-lookup"><span data-stu-id="08921-164">Consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="08921-165">3. Выберите затронутые объекты.</span><span class="sxs-lookup"><span data-stu-id="08921-165">3. Choose the impacted entities.</span></span>
<span data-ttu-id="08921-166">Определите столбцы в результатах запроса, где ожидается Поиск основной затронутой или затронутой сущности.</span><span class="sxs-lookup"><span data-stu-id="08921-166">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="08921-167">Например, запрос может возвращать адреса отправителя ( `SenderFromAddress` или `SenderMailFromAddress` ) и получателей ( `RecipientEmailAddress` ).</span><span class="sxs-lookup"><span data-stu-id="08921-167">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="08921-168">Определение того, какие из этих столбцов представляют основную затронутую сущность, помогает службе собирать соответствующие оповещения, сопоставлять инциденты и целевые действия отклика.</span><span class="sxs-lookup"><span data-stu-id="08921-168">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="08921-169">Можно выбрать только один столбец для каждого типа сущности (почтовый ящик, пользователь или устройство).</span><span class="sxs-lookup"><span data-stu-id="08921-169">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="08921-170">Столбцы, которые не возвращаются запросом, не могут быть выбраны.</span><span class="sxs-lookup"><span data-stu-id="08921-170">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="08921-171">4. Укажите действия.</span><span class="sxs-lookup"><span data-stu-id="08921-171">4. Specify actions.</span></span>
<span data-ttu-id="08921-172">Настраиваемое правило обнаружения может автоматически выполнять действия на устройствах, файлах или пользователях, возвращенных запросом.</span><span class="sxs-lookup"><span data-stu-id="08921-172">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="08921-173">Действия на устройствах</span><span class="sxs-lookup"><span data-stu-id="08921-173">Actions on devices</span></span>
<span data-ttu-id="08921-174">Эти действия применяются к устройствам в `DeviceId` столбце результатов запроса:</span><span class="sxs-lookup"><span data-stu-id="08921-174">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="08921-175">**Изолировать устройство**— использует Microsoft Defender ATP для применения полной изоляции сети, что не позволяет устройству подключаться к любому приложению или службе.</span><span class="sxs-lookup"><span data-stu-id="08921-175">**Isolate device**—uses Microsoft Defender ATP to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="08921-176">Дополнительные сведения о изоляции компьютеров ATP для защитника Майкрософт</span><span class="sxs-lookup"><span data-stu-id="08921-176">Learn more about Microsoft Defender ATP machine isolation</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="08921-177">**Собрать пакет для расследования**— собирает сведения об устройствах в ZIP-файле.</span><span class="sxs-lookup"><span data-stu-id="08921-177">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="08921-178">Дополнительные сведения о пакете исследования Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="08921-178">Learn more about the Microsoft Defender ATP investigation package</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="08921-179">**Запустить антивирусное сканирование**— выполняет полную проверку на устройстве антивирусной программы "Защитник Windows"</span><span class="sxs-lookup"><span data-stu-id="08921-179">**Run antivirus scan**—performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="08921-180">**Initiate расследования**— инициирует [Автоматическое исследование](mtp-autoir.md) на устройстве</span><span class="sxs-lookup"><span data-stu-id="08921-180">**Initiate investigation**—initiates an [automated investigation](mtp-autoir.md) on the device</span></span>
- <span data-ttu-id="08921-181">**Ограничить выполнение приложения**— устанавливает ограничения на устройство, чтобы разрешить запуск только тех файлов, которые подписаны на сертификат, выданный корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="08921-181">**Restrict app execution**—sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="08921-182">Дополнительные сведения об ограничениях приложений с помощью защитника Майкрософт для ATP</span><span class="sxs-lookup"><span data-stu-id="08921-182">Learn more about app restrictions with Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="08921-183">Действия с файлами</span><span class="sxs-lookup"><span data-stu-id="08921-183">Actions on files</span></span>
<span data-ttu-id="08921-184">Если выбран этот параметр, вы можете применить действие к **файлу в карантине** к файлам в `SHA1` результатах запроса,, или в `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` столбце.</span><span class="sxs-lookup"><span data-stu-id="08921-184">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="08921-185">Это действие удаляет файл из текущего расположения и помещает копию в карантин.</span><span class="sxs-lookup"><span data-stu-id="08921-185">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="08921-186">Действия для пользователей</span><span class="sxs-lookup"><span data-stu-id="08921-186">Actions on users</span></span>
<span data-ttu-id="08921-187">Если выбран этот параметр, **пользователь пометить как Скомпрометированное** действие будет выполняться для пользователей `AccountObjectId` в `InitiatingProcessAccountObjectId` столбце, или в `RecipientObjectId` столбце результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="08921-187">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="08921-188">Это действие устанавливает для уровня риска "высокий" в Azure Active Directory, активируя соответствующие [политики защиты удостоверений](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="08921-188">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="08921-189">Действие разрешить или блокировать для правил настраиваемого обнаружения в настоящее время не поддерживается в защите от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="08921-189">The allow or block action for custom detection rules is currently not supported on Microsoft Threat Protection.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="08921-190">5. Задайте область применения правила.</span><span class="sxs-lookup"><span data-stu-id="08921-190">5. Set the rule scope.</span></span>
<span data-ttu-id="08921-191">Задайте область, чтобы указать, какие устройства попадают под действие правила.</span><span class="sxs-lookup"><span data-stu-id="08921-191">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="08921-192">Правила влияния на области, которые проверяют устройства и не влияют на правила, которые проверяют только почтовые ящики, учетные записи пользователей и удостоверения.</span><span class="sxs-lookup"><span data-stu-id="08921-192">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="08921-193">При задании области можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="08921-193">When setting the scope, you can select:</span></span>

- <span data-ttu-id="08921-194">Все устройства</span><span class="sxs-lookup"><span data-stu-id="08921-194">All devices</span></span>
- <span data-ttu-id="08921-195">Конкретные группы устройств</span><span class="sxs-lookup"><span data-stu-id="08921-195">Specific device groups</span></span>

<span data-ttu-id="08921-196">Будут запрашиваться только данные из устройств в области.</span><span class="sxs-lookup"><span data-stu-id="08921-196">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="08921-197">Кроме того, действия будут выполняться только для этих устройств.</span><span class="sxs-lookup"><span data-stu-id="08921-197">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="08921-198">6. Проверьте и включите правило.</span><span class="sxs-lookup"><span data-stu-id="08921-198">6. Review and turn on the rule.</span></span>
<span data-ttu-id="08921-199">После просмотра правила нажмите кнопку **создать** , чтобы сохранить его.</span><span class="sxs-lookup"><span data-stu-id="08921-199">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="08921-200">Пользовательское правило обнаружения сразу же запустится.</span><span class="sxs-lookup"><span data-stu-id="08921-200">The custom detection rule immediately runs.</span></span> <span data-ttu-id="08921-201">Он выполняется повторно в зависимости от настроенной частоты для проверки совпадений, создания оповещений и выполнения действий ответа.</span><span class="sxs-lookup"><span data-stu-id="08921-201">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="08921-202">Управление существующими пользовательскими правилами обнаружения</span><span class="sxs-lookup"><span data-stu-id="08921-202">Manage existing custom detection rules</span></span>
<span data-ttu-id="08921-203">Вы можете просмотреть список существующих настраиваемых правил обнаружения, проверить их предыдущие запуски и просмотреть оповещения, которые они инициировали.</span><span class="sxs-lookup"><span data-stu-id="08921-203">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="08921-204">Вы также можете выполнить правило по требованию и изменить его.</span><span class="sxs-lookup"><span data-stu-id="08921-204">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="08921-205">Просмотр существующих правил</span><span class="sxs-lookup"><span data-stu-id="08921-205">View existing rules</span></span>

<span data-ttu-id="08921-206">**Чтобы просмотреть**все существующие настраиваемые правила обнаружения, перейдите к разделу  >  **Поиск с пользовательским обнаружением**.</span><span class="sxs-lookup"><span data-stu-id="08921-206">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="08921-207">На странице перечислены все правила со следующими сведениями о запуске:</span><span class="sxs-lookup"><span data-stu-id="08921-207">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="08921-208">**Последнее выполнение**— при последнем запуске правила для проверки совпадений запросов и создания оповещений</span><span class="sxs-lookup"><span data-stu-id="08921-208">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="08921-209">**Состояние последнего запуска**— успешно ли выполнено правило</span><span class="sxs-lookup"><span data-stu-id="08921-209">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="08921-210">**Следующий запуск**— следующее запланированное выполнение</span><span class="sxs-lookup"><span data-stu-id="08921-210">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="08921-211">**Status (состояние**) — включено ли правило</span><span class="sxs-lookup"><span data-stu-id="08921-211">**Status**—whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="08921-212">Просмотр сведений о правиле, правила изменения и запуска</span><span class="sxs-lookup"><span data-stu-id="08921-212">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="08921-213">Чтобы просмотреть подробные сведения о настраиваемом правиле обнаружения, перейдите **в раздел**  >  **Поиск нестандартных обнаружений** и выберите имя правила.</span><span class="sxs-lookup"><span data-stu-id="08921-213">To view comprehensive information about a custom detection rule, go to **Hunting** > **Custom detections** and then select the name of rule.</span></span> <span data-ttu-id="08921-214">Затем вы можете просмотреть общие сведения о правиле, в том числе сведения о состоянии его запуска и области.</span><span class="sxs-lookup"><span data-stu-id="08921-214">You can then view general information about the rule, including information its run status and scope.</span></span> <span data-ttu-id="08921-215">На странице также представлен список инициированных оповещений и действий.</span><span class="sxs-lookup"><span data-stu-id="08921-215">The page also provides the list of triggered alerts and actions.</span></span>

<span data-ttu-id="08921-216">![Страница сведений о настраиваемом правиле обнаружения](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="08921-216">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="08921-217">*Сведения о настраиваемом правиле обнаружения*</span><span class="sxs-lookup"><span data-stu-id="08921-217">*Custom detection rule details*</span></span>

<span data-ttu-id="08921-218">На этой странице можно также выполнить следующие действия для правила:</span><span class="sxs-lookup"><span data-stu-id="08921-218">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="08921-219">**Run**— немедленное выполнение правила.</span><span class="sxs-lookup"><span data-stu-id="08921-219">**Run**—run the rule immediately.</span></span> <span data-ttu-id="08921-220">При этом также сбрасывается интервал следующего запуска.</span><span class="sxs-lookup"><span data-stu-id="08921-220">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="08921-221">**Изменить**— изменить правило, не изменяя запрос</span><span class="sxs-lookup"><span data-stu-id="08921-221">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="08921-222">**Изменение запроса**— изменение запроса в расширенном поиске</span><span class="sxs-lookup"><span data-stu-id="08921-222">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="08921-223">**Включение**  /  **Отключить**— включить или остановить выполнение правила</span><span class="sxs-lookup"><span data-stu-id="08921-223">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="08921-224">**Удалить**— отключить правило и удалить его</span><span class="sxs-lookup"><span data-stu-id="08921-224">**Delete**—turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="08921-225">Просмотр и управление инициированными оповещениями</span><span class="sxs-lookup"><span data-stu-id="08921-225">View and manage triggered alerts</span></span>

<span data-ttu-id="08921-226">На экране сведения о правиле **(**  >  **Поиск пользовательских обнаружений**  >  **[имя правила]**) перейдите к **триггерным оповещениям**, в которых перечислены оповещения, созданные в соответствии с правилом.</span><span class="sxs-lookup"><span data-stu-id="08921-226">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to  **Triggered alerts**, which lists the alerts generated by matches to the rule.</span></span> <span data-ttu-id="08921-227">Выберите оповещение, чтобы просмотреть подробные сведения о нем и выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="08921-227">Select an alert to view detailed information about it and take the following actions:</span></span>

- <span data-ttu-id="08921-228">Управление предупреждением с помощью задания его состояния и классификации (true или false Alert)</span><span class="sxs-lookup"><span data-stu-id="08921-228">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="08921-229">Связывание предупреждения с инцидентом</span><span class="sxs-lookup"><span data-stu-id="08921-229">Link the alert to an incident</span></span>
- <span data-ttu-id="08921-230">Запуск запроса, запускающего оповещение при расширенном поиске</span><span class="sxs-lookup"><span data-stu-id="08921-230">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="08921-231">Проверка действий</span><span class="sxs-lookup"><span data-stu-id="08921-231">Review actions</span></span>
<span data-ttu-id="08921-232">На экране сведения о правиле **(**  >  **Поиск пользовательских обнаружений**  >  **[имя правила]**) перейдите к **триггерным действиям**, в которых перечислены действия, выполненные на основании совпадений с правилом.</span><span class="sxs-lookup"><span data-stu-id="08921-232">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions**, which lists the actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="08921-233">Чтобы быстро просмотреть сведения и выполнить действия над элементом таблицы, используйте столбец Selection [&#10003;] слева от таблицы.</span><span class="sxs-lookup"><span data-stu-id="08921-233">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topic"></a><span data-ttu-id="08921-234">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="08921-234">Related topic</span></span>
- [<span data-ttu-id="08921-235">Обзор настраиваемых обнаружений</span><span class="sxs-lookup"><span data-stu-id="08921-235">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="08921-236">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="08921-236">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="08921-237">Познакомьтесь с языком запросов расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="08921-237">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
