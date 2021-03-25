---
title: Создание настраиваемой системы обнаружения в ATP Защитника Майкрософт
ms.reviewer: ''
description: Узнайте, как создать настраиваемые правила обнаружения на основе расширенных запросов на охоту
keywords: настраиваемые обнаружения, создание, управление, оповещения, редактирование, запуск по требованию, частота, интервал, правила обнаружения, расширенные правила охоты, охота, запрос, действия отклика, mdatp, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: fc4c15d2e391176ed0b4420c13fb865674da0361
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163591"
---
# <a name="create-custom-detection-rules"></a><span data-ttu-id="96c6f-104">Создание настраиваемой системы обнаружения</span><span class="sxs-lookup"><span data-stu-id="96c6f-104">Create custom detection rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="96c6f-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="96c6f-105">**Applies to:**</span></span>
- [<span data-ttu-id="96c6f-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="96c6f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="96c6f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="96c6f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="96c6f-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="96c6f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="96c6f-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="96c6f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="96c6f-110">Настраиваемые правила [](advanced-hunting-overview.md) обнаружения, созданные из расширенных запросов на охоту, позволяет активно отслеживать различные события и состояния системы, включая предполагаемые нарушения и неправильно настроенные устройства.</span><span class="sxs-lookup"><span data-stu-id="96c6f-110">Custom detection rules built from [advanced hunting](advanced-hunting-overview.md) queries let you proactively monitor various events and system states, including suspected breach activity and misconfigured devices.</span></span> <span data-ttu-id="96c6f-111">Вы можете настроить их для запуска с регулярными интервалами, создавая оповещения и принимая ответные действия при совпадениях.</span><span class="sxs-lookup"><span data-stu-id="96c6f-111">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="96c6f-112">Ознакомьтесь с этой статьей, чтобы узнать, как создать новые пользовательские правила обнаружения.</span><span class="sxs-lookup"><span data-stu-id="96c6f-112">Read this article to learn how to create new custom detection rules.</span></span> <span data-ttu-id="96c6f-113">Или [см. просмотр и управление существующими правилами.](custom-detections-manage.md)</span><span class="sxs-lookup"><span data-stu-id="96c6f-113">Or [see viewing and managing existing rules](custom-detections-manage.md).</span></span>

> [!NOTE]
> <span data-ttu-id="96c6f-114">Чтобы создать или управлять пользовательскими обнаружениями, [ваша роль](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) должна иметь разрешение на управление **настройками безопасности.**</span><span class="sxs-lookup"><span data-stu-id="96c6f-114">To create or manage custom detections, [your role](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) needs to have the **manage security settings** permission.</span></span>

## <a name="1-prepare-the-query"></a><span data-ttu-id="96c6f-115">1. Подготовка запроса.</span><span class="sxs-lookup"><span data-stu-id="96c6f-115">1. Prepare the query.</span></span>

<span data-ttu-id="96c6f-116">В центре безопасности Microsoft Defender перейдите в **расширенный** поиск и выберите существующий запрос или создайте новый запрос.</span><span class="sxs-lookup"><span data-stu-id="96c6f-116">In Microsoft Defender Security Center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="96c6f-117">При использовании нового запроса запустите запрос для выявления ошибок и понимания возможных результатов.</span><span class="sxs-lookup"><span data-stu-id="96c6f-117">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="96c6f-118">Чтобы служба не возвращала слишком много оповещений, каждое правило ограничивается созданием только 100 оповещений при каждом запуске.</span><span class="sxs-lookup"><span data-stu-id="96c6f-118">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="96c6f-119">Перед созданием правила необходимо настроить запрос, чтобы не предупреждать о нормальной ежедневной активности.</span><span class="sxs-lookup"><span data-stu-id="96c6f-119">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>

### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="96c6f-120">Необходимые столбцы в результатах запроса</span><span class="sxs-lookup"><span data-stu-id="96c6f-120">Required columns in the query results</span></span>

<span data-ttu-id="96c6f-121">Чтобы использовать запрос для пользовательского правила обнаружения, запрос должен возвращать следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="96c6f-121">To use a query for a custom detection rule, the query must return the following columns:</span></span>

- `Timestamp`
- `DeviceId`
- `ReportId`

<span data-ttu-id="96c6f-122">Простые запросы, например запросы, которые не используют оператор или оператор для настройки или агрегированных результатов, обычно возвращают `project` `summarize` эти общие столбцы.</span><span class="sxs-lookup"><span data-stu-id="96c6f-122">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="96c6f-123">Существуют различные способы обеспечения более сложных запросов, возвращая эти столбцы.</span><span class="sxs-lookup"><span data-stu-id="96c6f-123">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="96c6f-124">Например, если вы предпочитаете агрегировать и считать по, вы все равно можете вернуться и получить их из последнего события `DeviceId` `Timestamp` с участием каждого `ReportId` устройства.</span><span class="sxs-lookup"><span data-stu-id="96c6f-124">For example, if you prefer to aggregate and count by `DeviceId`, you can still return `Timestamp` and `ReportId` by getting them from the most recent event involving each device.</span></span>

<span data-ttu-id="96c6f-125">В приведенной ниже примере запроса учитывается количество уникальных устройств () с обнаружениями антивирусов и используется для поиска только тех устройств с более чем `DeviceId` пятью обнаружениями.</span><span class="sxs-lookup"><span data-stu-id="96c6f-125">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this to find only those devices with more than five detections.</span></span> <span data-ttu-id="96c6f-126">Чтобы вернуть последнюю и `Timestamp` `ReportId` соответствующую, он использует оператора с `summarize` `arg_max` функцией.</span><span class="sxs-lookup"><span data-stu-id="96c6f-126">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="96c6f-127">Для улучшения производительности запроса установите фильтр времени, который соответствует вашей назначенной частоте выполнения для правила.</span><span class="sxs-lookup"><span data-stu-id="96c6f-127">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="96c6f-128">Так как наименее частый запуск происходит каждые 24 часа, фильтрация за прошедший день будет охватывать все новые данные.</span><span class="sxs-lookup"><span data-stu-id="96c6f-128">Since the least frequent run is every 24 hours, filtering for the past day will cover all new data.</span></span>

## <a name="2-create-a-new-rule-and-provide-alert-details"></a><span data-ttu-id="96c6f-129">2. Создайте новое правило и укажу сведения об оповещении.</span><span class="sxs-lookup"><span data-stu-id="96c6f-129">2. Create a new rule and provide alert details.</span></span>

<span data-ttu-id="96c6f-130">С помощью запроса в редакторе запроса выберите **правило Создать** обнаружение и укажите следующие сведения оповещения:</span><span class="sxs-lookup"><span data-stu-id="96c6f-130">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="96c6f-131">**Имя обнаружения**— имя правила обнаружения</span><span class="sxs-lookup"><span data-stu-id="96c6f-131">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="96c6f-132">**Частота**— интервал для выполнения запроса и принятия действий.</span><span class="sxs-lookup"><span data-stu-id="96c6f-132">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="96c6f-133">Дополнительные рекомендации см. ниже</span><span class="sxs-lookup"><span data-stu-id="96c6f-133">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="96c6f-134">**Предупреждение название**— заголовок, отображаемый с оповещениями, инициированными правилом</span><span class="sxs-lookup"><span data-stu-id="96c6f-134">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="96c6f-135">**Серьезность**— потенциальный риск компонента или действия, определяемого правилом.</span><span class="sxs-lookup"><span data-stu-id="96c6f-135">**Severity**—potential risk of the component or activity identified by the rule.</span></span> [<span data-ttu-id="96c6f-136">Чтение о серьезности оповещений</span><span class="sxs-lookup"><span data-stu-id="96c6f-136">Read about alert severities</span></span>](alerts-queue.md#severity)
- <span data-ttu-id="96c6f-137">**Категория —** тип компонента угрозы или действий, если таковой существует.</span><span class="sxs-lookup"><span data-stu-id="96c6f-137">**Category**—type of threat component or activity, if any.</span></span> [<span data-ttu-id="96c6f-138">Чтение о категориях оповещений</span><span class="sxs-lookup"><span data-stu-id="96c6f-138">Read about alert categories</span></span>](alerts-queue.md#understanding-alert-categories)
- <span data-ttu-id="96c6f-139">**МЕТОДЫ ATT&CK**— одна или несколько методов атаки, которые определены правилом, как описано в рамках ATT MITRE&CK.</span><span class="sxs-lookup"><span data-stu-id="96c6f-139">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the MITRE ATT&CK framework.</span></span> <span data-ttu-id="96c6f-140">Этот раздел недо доступен с определенными категориями оповещений, такими как вредоносные программы, программы-вымогательства, подозрительные действия и нежелательное программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="96c6f-140">This section is not available with certain alert categories, such as malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="96c6f-141">**Описание**— дополнительные сведения о компоненте или действии, выявленных правилом</span><span class="sxs-lookup"><span data-stu-id="96c6f-141">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="96c6f-142">**Рекомендуемые действия**— дополнительные действия, которые могут приниматься ответчиками в ответ на предупреждение</span><span class="sxs-lookup"><span data-stu-id="96c6f-142">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

<span data-ttu-id="96c6f-143">Дополнительные сведения о том, как отображаются сведения об оповещении, [читайте в публикации "Ъ" "Очередь оповещения".](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="96c6f-143">For more information about how alert details are displayed, [read about the alert queue](alerts-queue.md).</span></span>

### <a name="rule-frequency"></a><span data-ttu-id="96c6f-144">Частота правил</span><span class="sxs-lookup"><span data-stu-id="96c6f-144">Rule frequency</span></span>

<span data-ttu-id="96c6f-145">При сэкономлении запускается новое пользовательское правило обнаружения, проверяя совпадения за последние 30 дней данных.</span><span class="sxs-lookup"><span data-stu-id="96c6f-145">When saved, a new custom detection rule immediately runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="96c6f-146">Затем правило выполняется снова с фиксированными интервалами и длительностью обратного воспроизведения в зависимости от частоты, которая вы выбираете:</span><span class="sxs-lookup"><span data-stu-id="96c6f-146">The rule then runs again at fixed intervals and lookback durations based on the frequency you choose:</span></span>

- <span data-ttu-id="96c6f-147">**Каждые 24 часа**— выполняется каждые 24 часа, проверяя данные за последние 30 дней</span><span class="sxs-lookup"><span data-stu-id="96c6f-147">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="96c6f-148">**Каждые 12 часов**— выполняется каждые 12 часов, проверяя данные за последние 24 часа</span><span class="sxs-lookup"><span data-stu-id="96c6f-148">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="96c6f-149">**Каждые 3 часа**— выполняется каждые 3 часа, проверяя данные за последние 6 часов</span><span class="sxs-lookup"><span data-stu-id="96c6f-149">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="96c6f-150">**Каждый** час — выполняется почасовая проверка данных за последние 2 часа.</span><span class="sxs-lookup"><span data-stu-id="96c6f-150">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96c6f-151">При изменении запроса, который уже запланирован в качестве настраиваемого обнаружения, следующее немедленное выполнение будет иметь окно в 30 дней, точно так же, как если бы создавался новый запрос.</span><span class="sxs-lookup"><span data-stu-id="96c6f-151">When changing a query that is already scheduled as a Custom Detection, it's next immediate execution will have a lookback window of 30 days, exactly as if a new query was being created.</span></span> <span data-ttu-id="96c6f-152">Изменения большого количества запросов и с фильтрами времени, которые по умолчанию больше, чем по умолчанию для выбранной частоты, могут повлиять на общее потребление квот в Advanced Hunting и привести к исчерпанию дневной квоты.</span><span class="sxs-lookup"><span data-stu-id="96c6f-152">Changes to a large number of queries, and with time filters higher than the default lookback duration for the selected frequency, might have an impact in the overall quota consumption of Advanced Hunting and resulting in exhausting the daily quota.</span></span>

> [!TIP]
> <span data-ttu-id="96c6f-153">Соответствие фильтрам времени в запросе с длительностью отката.</span><span class="sxs-lookup"><span data-stu-id="96c6f-153">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="96c6f-154">Результаты за пределами длительности поиска игнорируются.</span><span class="sxs-lookup"><span data-stu-id="96c6f-154">Results outside of the lookback duration are ignored.</span></span>

<span data-ttu-id="96c6f-155">Выберите частоту, которая совпадает с тем, как тщательно следует отслеживать обнаружение, и рассмотрите возможности организации для реагирования на оповещения.</span><span class="sxs-lookup"><span data-stu-id="96c6f-155">Select the frequency that matches how closely you want to monitor detections, and consider your organization's capacity to respond to the alerts.</span></span>

## <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="96c6f-156">3. Выберите сущностями с влиянием.</span><span class="sxs-lookup"><span data-stu-id="96c6f-156">3. Choose the impacted entities.</span></span>

<span data-ttu-id="96c6f-157">Определите столбцы в результатах запроса, в которых ожидается найти основную затронутую или затрагиваемую сущность.</span><span class="sxs-lookup"><span data-stu-id="96c6f-157">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="96c6f-158">Например, запрос может возвращать ИД устройств и пользователей.</span><span class="sxs-lookup"><span data-stu-id="96c6f-158">For example, a query might return both device and user IDs.</span></span> <span data-ttu-id="96c6f-159">Определение того, какие из этих столбцов представляют основную объектную сущность, помогает службе агрегировать соответствующие оповещения, соотносить инциденты и целевые действия реагирования.</span><span class="sxs-lookup"><span data-stu-id="96c6f-159">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="96c6f-160">Для каждого типа сущности можно выбрать только один столбец.</span><span class="sxs-lookup"><span data-stu-id="96c6f-160">You can select only one column for each entity type.</span></span> <span data-ttu-id="96c6f-161">Столбцы, не возвращенные запросом, не могут быть выбраны.</span><span class="sxs-lookup"><span data-stu-id="96c6f-161">Columns that are not returned by your query can't be selected.</span></span>

## <a name="4-specify-actions"></a><span data-ttu-id="96c6f-162">4. Укажите действия.</span><span class="sxs-lookup"><span data-stu-id="96c6f-162">4. Specify actions.</span></span>

<span data-ttu-id="96c6f-163">Ваше пользовательское правило обнаружения может автоматически принимать действия на файлах или устройствах, возвращаемые запросом.</span><span class="sxs-lookup"><span data-stu-id="96c6f-163">Your custom detection rule can automatically take actions on files or devices that are returned by the query.</span></span>

### <a name="actions-on-devices"></a><span data-ttu-id="96c6f-164">Действия на устройствах</span><span class="sxs-lookup"><span data-stu-id="96c6f-164">Actions on devices</span></span>

<span data-ttu-id="96c6f-165">Эти действия применяются к устройствам в `DeviceId` столбце результатов запроса:</span><span class="sxs-lookup"><span data-stu-id="96c6f-165">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>

- <span data-ttu-id="96c6f-166">**Изолировать устройство**— применяется полная изоляция сети, предотвращая подключение устройства к любому приложению или службе, за исключением службы Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="96c6f-166">**Isolate device**—applies full network isolation, preventing the device from connecting to any application or service, except for the Defender for Endpoint service.</span></span> [<span data-ttu-id="96c6f-167">Дополнительные информацию об изоляции устройств</span><span class="sxs-lookup"><span data-stu-id="96c6f-167">Learn more about device isolation</span></span>](respond-machine-alerts.md#isolate-devices-from-the-network)
- <span data-ttu-id="96c6f-168">**Сбор пакета исследований**— сбор сведений об устройствах в файле ZIP.</span><span class="sxs-lookup"><span data-stu-id="96c6f-168">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="96c6f-169">Дополнительные информацию о пакете исследований</span><span class="sxs-lookup"><span data-stu-id="96c6f-169">Learn more about the investigation package</span></span>](respond-machine-alerts.md#collect-investigation-package-from-devices)
- <span data-ttu-id="96c6f-170">**Запуск антивирусного сканирования**— выполняет полное антивирусное сканирование Microsoft Defender на устройстве</span><span class="sxs-lookup"><span data-stu-id="96c6f-170">**Run antivirus scan**—performs a full Microsoft Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="96c6f-171">**Инициировать** расследование — [начинается автоматическое расследование](automated-investigations.md) на устройстве</span><span class="sxs-lookup"><span data-stu-id="96c6f-171">**Initiate investigation**—starts an [automated investigation](automated-investigations.md) on the device</span></span>
- <span data-ttu-id="96c6f-172">**Ограничение выполнения приложения**— устанавливает ограничения на устройстве, позволяя запускать только файлы, подписанные с помощью сертификата, выданного Корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="96c6f-172">**Restrict app execution**—sets restrictions on the device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="96c6f-173">Подробнее об ограничении выполнения приложений</span><span class="sxs-lookup"><span data-stu-id="96c6f-173">Learn more about restricting app execution</span></span>](respond-machine-alerts.md#restrict-app-execution)

### <a name="actions-on-files"></a><span data-ttu-id="96c6f-174">Действия в файлах</span><span class="sxs-lookup"><span data-stu-id="96c6f-174">Actions on files</span></span>

<span data-ttu-id="96c6f-175">Эти действия применяются к файлам в столбце или `SHA1` `InitiatingProcessSHA1` столбце результатов запроса:</span><span class="sxs-lookup"><span data-stu-id="96c6f-175">These actions are applied to files in the `SHA1` or the `InitiatingProcessSHA1` column of the query results:</span></span>

- <span data-ttu-id="96c6f-176">**Разрешить/заблокировать**— автоматически добавляет файл [](manage-indicators.md) в настраиваемый список индикаторов, чтобы всегда было разрешено запускать или блокировать запуск.</span><span class="sxs-lookup"><span data-stu-id="96c6f-176">**Allow/Block**—automatically adds the file to your [custom indicator list](manage-indicators.md) so that it is always allowed to run or blocked from running.</span></span> <span data-ttu-id="96c6f-177">Область действия можно настроить таким образом, чтобы оно было принято только в выбранных группах устройств.</span><span class="sxs-lookup"><span data-stu-id="96c6f-177">You can set the scope of this action so that it is taken only on selected device groups.</span></span> <span data-ttu-id="96c6f-178">Эта область не зависит от области действия правила.</span><span class="sxs-lookup"><span data-stu-id="96c6f-178">This scope is independent of the scope of the rule.</span></span>
- <span data-ttu-id="96c6f-179">**Файл карантина** удаляет файл из текущего расположения и помещает копию в карантин</span><span class="sxs-lookup"><span data-stu-id="96c6f-179">**Quarantine file**—deletes the file from its current location and places a copy in quarantine</span></span>

### <a name="actions-on-users"></a><span data-ttu-id="96c6f-180">Действия для пользователей</span><span class="sxs-lookup"><span data-stu-id="96c6f-180">Actions on users</span></span>

- <span data-ttu-id="96c6f-181">**Пометить** пользователя как скомпрометированного — задает уровень риска пользователя до "высокого" в Azure Active Directory, запуская соответствующие [политики защиты удостоверений.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels)</span><span class="sxs-lookup"><span data-stu-id="96c6f-181">**Mark user as compromised**—sets the user's risk level to "high" in Azure Active Directory, triggering the corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels).</span></span>

## <a name="5-set-the-rule-scope"></a><span data-ttu-id="96c6f-182">5. Установите область правил.</span><span class="sxs-lookup"><span data-stu-id="96c6f-182">5. Set the rule scope.</span></span>

<span data-ttu-id="96c6f-183">Установите область, чтобы указать, какие устройства охвачены правилом:</span><span class="sxs-lookup"><span data-stu-id="96c6f-183">Set the scope to specify which devices are covered by the rule:</span></span>

- <span data-ttu-id="96c6f-184">Все устройства</span><span class="sxs-lookup"><span data-stu-id="96c6f-184">All devices</span></span>
- <span data-ttu-id="96c6f-185">Конкретные группы устройств</span><span class="sxs-lookup"><span data-stu-id="96c6f-185">Specific device groups</span></span>

<span data-ttu-id="96c6f-186">Запрашиваются только данные с устройств в области.</span><span class="sxs-lookup"><span data-stu-id="96c6f-186">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="96c6f-187">Кроме того, действия будут приниматься только на этих устройствах.</span><span class="sxs-lookup"><span data-stu-id="96c6f-187">Also, actions will be taken only on those devices.</span></span>

## <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="96c6f-188">6. Просмотрите и включите правило.</span><span class="sxs-lookup"><span data-stu-id="96c6f-188">6. Review and turn on the rule.</span></span>

<span data-ttu-id="96c6f-189">После просмотра правила выберите **Создать, чтобы** сохранить его.</span><span class="sxs-lookup"><span data-stu-id="96c6f-189">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="96c6f-190">Правило настраиваемой диагностики немедленно запускается.</span><span class="sxs-lookup"><span data-stu-id="96c6f-190">The custom detection rule immediately runs.</span></span> <span data-ttu-id="96c6f-191">Он снова запускается на основе настроенной частоты для проверки совпадений, создания оповещений и реагировать на действия.</span><span class="sxs-lookup"><span data-stu-id="96c6f-191">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

<span data-ttu-id="96c6f-192">Вы можете [просматривать и управлять пользовательскими](custom-detections-manage.md)правилами обнаружения, проверять их предыдущие запуски и просматривать срабатываемые ими оповещения.</span><span class="sxs-lookup"><span data-stu-id="96c6f-192">You can [view and manage custom detection rules](custom-detections-manage.md), check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="96c6f-193">Вы также можете запустить правило по запросу и изменить его.</span><span class="sxs-lookup"><span data-stu-id="96c6f-193">You can also run a rule on demand and modify it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="96c6f-194">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="96c6f-194">Related topics</span></span>

- [<span data-ttu-id="96c6f-195">Просмотр и управление пользовательскими правилами обнаружения</span><span class="sxs-lookup"><span data-stu-id="96c6f-195">View and manage custom detection rules</span></span>](custom-detections-manage.md)
- [<span data-ttu-id="96c6f-196">Обзор настраиваемых обнаружений</span><span class="sxs-lookup"><span data-stu-id="96c6f-196">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="96c6f-197">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="96c6f-197">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="96c6f-198">Познакомьтесь с языком запросов расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="96c6f-198">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="96c6f-199">Просмотр и организация оповещений</span><span class="sxs-lookup"><span data-stu-id="96c6f-199">View and organize alerts</span></span>](alerts-queue.md)