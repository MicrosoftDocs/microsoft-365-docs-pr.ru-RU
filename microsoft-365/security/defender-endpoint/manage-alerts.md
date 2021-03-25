---
title: Управление оповещениями Защитника Майкрософт для конечных точек
description: Измените состояние оповещений, создайте правила подавления, чтобы скрыть оповещения, отправить комментарии и просмотреть историю изменений для отдельных оповещений с помощью меню Manage Alert.
keywords: управление оповещениями, управление, оповещений, состояние, новое, в процессе выполнения, разрешено, устранение оповещений, подавление, подавление, правила, контекст, история, комментарии, изменения
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f03c2209b369e6fb9e001452c53073daeb5fe1c6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187005"
---
# <a name="manage-microsoft-defender-for-endpoint-alerts"></a><span data-ttu-id="f917f-104">Управление оповещениями Защитника Майкрософт для конечных точек</span><span class="sxs-lookup"><span data-stu-id="f917f-104">Manage Microsoft Defender for Endpoint alerts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f917f-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f917f-105">**Applies to:**</span></span>
- [<span data-ttu-id="f917f-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f917f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f917f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f917f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="f917f-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="f917f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f917f-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="f917f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

<span data-ttu-id="f917f-110">Defender for Endpoint оповещает вас о возможных вредоносных событиях, атрибутах и контекстной информации с помощью оповещений.</span><span class="sxs-lookup"><span data-stu-id="f917f-110">Defender for Endpoint notifies you of possible malicious events, attributes, and contextual information through alerts.</span></span> <span data-ttu-id="f917f-111">Сводка новых оповещений отображается на панели мониторинга операций **безопасности,** и вы можете получить доступ ко всем оповещениям в **очереди Оповещения.**</span><span class="sxs-lookup"><span data-stu-id="f917f-111">A summary of new alerts is displayed in the **Security operations dashboard**, and you can access all alerts in the **Alerts queue**.</span></span>

<span data-ttu-id="f917f-112">Управлять оповещениями можно, выбрав оповещение в очереди Оповещений или вкладку **Оповещений** на странице Device для отдельного устройства. </span><span class="sxs-lookup"><span data-stu-id="f917f-112">You can manage alerts by selecting an alert in the **Alerts queue**, or the **Alerts** tab of the Device page for an individual device.</span></span>

<span data-ttu-id="f917f-113">Выбор оповещений в любом из этих мест приводит к области управления **оповещением.**</span><span class="sxs-lookup"><span data-stu-id="f917f-113">Selecting an alert in either of those places brings up the **Alert management pane**.</span></span>

![Изображение области управления оповещениями и очереди оповещений](images/atp-alerts-selected.png)

## <a name="link-to-another-incident"></a><span data-ttu-id="f917f-115">Ссылка на другой инцидент</span><span class="sxs-lookup"><span data-stu-id="f917f-115">Link to another incident</span></span>
<span data-ttu-id="f917f-116">Вы можете создать новый инцидент из оповещений или ссылки на существующий инцидент.</span><span class="sxs-lookup"><span data-stu-id="f917f-116">You can create a new incident from the alert or link to an existing incident.</span></span> 

## <a name="assign-alerts"></a><span data-ttu-id="f917f-117">Назначение оповещений</span><span class="sxs-lookup"><span data-stu-id="f917f-117">Assign alerts</span></span>
<span data-ttu-id="f917f-118">Если оповещение еще не назначено, вы можете выбрать **Назначение** мне, чтобы назначить оповещение себе.</span><span class="sxs-lookup"><span data-stu-id="f917f-118">If an alert is not yet assigned, you can select **Assign to me** to assign the alert to yourself.</span></span>


## <a name="suppress-alerts"></a><span data-ttu-id="f917f-119">Подавление оповещений</span><span class="sxs-lookup"><span data-stu-id="f917f-119">Suppress alerts</span></span>
<span data-ttu-id="f917f-120">Возможны сценарии, в которых необходимо подавить оповещения, появляющиеся в Центре безопасности Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f917f-120">There might be scenarios where you need to suppress alerts from appearing in Microsoft Defender Security Center.</span></span> <span data-ttu-id="f917f-121">Defender for Endpoint позволяет создавать правила подавления для определенных оповещений, которые, как известно, являются безобидными, например известных инструментов или процессов в организации.</span><span class="sxs-lookup"><span data-stu-id="f917f-121">Defender for Endpoint lets you create suppression rules for specific alerts that are known to be innocuous such as known tools or processes in your organization.</span></span>

<span data-ttu-id="f917f-122">Правила подавления могут создаваться из существующего оповещения.</span><span class="sxs-lookup"><span data-stu-id="f917f-122">Suppression rules can be created from an existing alert.</span></span> <span data-ttu-id="f917f-123">При необходимости их можно отключить и повторно использовать.</span><span class="sxs-lookup"><span data-stu-id="f917f-123">They can be disabled and reenabled if needed.</span></span>

<span data-ttu-id="f917f-124">Когда создается правило подавления, оно вступает в силу с момента создания правила.</span><span class="sxs-lookup"><span data-stu-id="f917f-124">When a suppression rule is created, it will take effect from the point when the rule is created.</span></span> <span data-ttu-id="f917f-125">Правило не повлияет на существующие оповещения, уже в очереди, до создания правила.</span><span class="sxs-lookup"><span data-stu-id="f917f-125">The rule will not affect existing alerts already in the queue, prior to the rule creation.</span></span> <span data-ttu-id="f917f-126">Правило будет применяться только для оповещений, удовлетворяющих условиям, установленным после создания правила.</span><span class="sxs-lookup"><span data-stu-id="f917f-126">The rule will only be applied on alerts that satisfy the conditions set after the rule is created.</span></span>

<span data-ttu-id="f917f-127">Существует два контекста для правила подавления, которое можно выбрать из:</span><span class="sxs-lookup"><span data-stu-id="f917f-127">There are two contexts for a suppression rule that you can choose from:</span></span>

- <span data-ttu-id="f917f-128">**Подавление оповещения на этом устройстве**</span><span class="sxs-lookup"><span data-stu-id="f917f-128">**Suppress alert on this device**</span></span>
- <span data-ttu-id="f917f-129">**Подавление оповещений в организации**</span><span class="sxs-lookup"><span data-stu-id="f917f-129">**Suppress alert in my organization**</span></span>

<span data-ttu-id="f917f-130">Контекст правила позволяет адаптировать то, что попадает на портал, и убедиться, что на портале всплыли только реальные оповещения о безопасности.</span><span class="sxs-lookup"><span data-stu-id="f917f-130">The context of the rule lets you tailor what gets surfaced into the portal and ensure that only real security alerts are surfaced into the portal.</span></span>

<span data-ttu-id="f917f-131">Вы можете использовать примеры в следующей таблице, чтобы помочь выбрать контекст для правила подавления:</span><span class="sxs-lookup"><span data-stu-id="f917f-131">You can use the examples in the following table to help you choose the context for a suppression rule:</span></span>

| <span data-ttu-id="f917f-132">**Context**</span><span class="sxs-lookup"><span data-stu-id="f917f-132">**Context**</span></span>                           | <span data-ttu-id="f917f-133">**Определение**</span><span class="sxs-lookup"><span data-stu-id="f917f-133">**Definition**</span></span>                                                                                                                                              | <span data-ttu-id="f917f-134">**Примеры сценариев**</span><span class="sxs-lookup"><span data-stu-id="f917f-134">**Example scenarios**</span></span>                                                                                                                                                                                                  |
|:--------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="f917f-135">**Подавление оповещения на этом устройстве**</span><span class="sxs-lookup"><span data-stu-id="f917f-135">**Suppress alert on this device**</span></span>    | <span data-ttu-id="f917f-136">Оповещения с тем же заголовком оповещения и только на этом конкретном устройстве будут подавлены.</span><span class="sxs-lookup"><span data-stu-id="f917f-136">Alerts with the same alert title and on that specific device only will be suppressed.</span></span> <br /><br /><span data-ttu-id="f917f-137">Все остальные оповещения на этом устройстве не будут подавлены.</span><span class="sxs-lookup"><span data-stu-id="f917f-137">All other alerts on that device will not be suppressed.</span></span> | <ul><li><span data-ttu-id="f917f-138">Исследователь безопасности изучает вредоносный сценарий, который использовался для атаки на другие устройства в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f917f-138">A security researcher is investigating a malicious script that has been used to attack other devices in your organization.</span></span></li><li><span data-ttu-id="f917f-139">Разработчик регулярно создает сценарии PowerShell для своей команды.</span><span class="sxs-lookup"><span data-stu-id="f917f-139">A developer regularly creates PowerShell scripts for their team.</span></span></li></ul> |
| <span data-ttu-id="f917f-140">**Подавление оповещений в организации**</span><span class="sxs-lookup"><span data-stu-id="f917f-140">**Suppress alert in my organization**</span></span> | <span data-ttu-id="f917f-141">Оповещения с одинаковым названием оповещений на любом устройстве будут подавлены.</span><span class="sxs-lookup"><span data-stu-id="f917f-141">Alerts with the same alert title on any device will be suppressed.</span></span>                                                                                         | <ul><li><span data-ttu-id="f917f-142">Доброкачественная административная программа используется всеми в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f917f-142">A benign administrative tool is used by everyone in your organization.</span></span></li></ul>                                                                                                                               |

### <a name="suppress-an-alert-and-create-a-new-suppression-rule"></a><span data-ttu-id="f917f-143">Подавляйте оповещение и создайте новое правило подавления:</span><span class="sxs-lookup"><span data-stu-id="f917f-143">Suppress an alert and create a new suppression rule:</span></span>
<span data-ttu-id="f917f-144">Создайте настраиваемые правила для управления при подавлении или урегулировании оповещений.</span><span class="sxs-lookup"><span data-stu-id="f917f-144">Create custom rules to control when alerts are suppressed, or resolved.</span></span> <span data-ttu-id="f917f-145">Вы можете контролировать контекст при подавлении оповещения, указав заголовок оповещений, индикатор компромисса и условия.</span><span class="sxs-lookup"><span data-stu-id="f917f-145">You can control the context for when an alert is suppressed by specifying the alert title, Indicator of compromise, and the conditions.</span></span> <span data-ttu-id="f917f-146">После указания контекста можно настроить действие и область в оповещении.</span><span class="sxs-lookup"><span data-stu-id="f917f-146">After specifying the context, you’ll be able to configure the action and scope on the alert.</span></span> 

1. <span data-ttu-id="f917f-147">Выберите оповещение, необходимое для подавления.</span><span class="sxs-lookup"><span data-stu-id="f917f-147">Select the alert you'd like to suppress.</span></span> <span data-ttu-id="f917f-148">Это приводит к области **управления alert.**</span><span class="sxs-lookup"><span data-stu-id="f917f-148">This brings up the **Alert management** pane.</span></span>

2.  <span data-ttu-id="f917f-149">Выберите **Создать правило подавления.**</span><span class="sxs-lookup"><span data-stu-id="f917f-149">Select **Create a suppression rule**.</span></span>

    <span data-ttu-id="f917f-150">С помощью этих атрибутов можно создать условие подавления.</span><span class="sxs-lookup"><span data-stu-id="f917f-150">You can create a suppression condition using these attributes.</span></span> <span data-ttu-id="f917f-151">Оператор AND применяется между каждым условием, поэтому подавление происходит только в том случае, если все условия выполнены.</span><span class="sxs-lookup"><span data-stu-id="f917f-151">An AND operator is applied between each condition, so suppression occurs only if all conditions are met.</span></span>
    
    * <span data-ttu-id="f917f-152">Файл SHA1</span><span class="sxs-lookup"><span data-stu-id="f917f-152">File SHA1</span></span>
    * <span data-ttu-id="f917f-153">Имя файла — поддерживаемая подмайка</span><span class="sxs-lookup"><span data-stu-id="f917f-153">File name - wildcard supported</span></span>
    * <span data-ttu-id="f917f-154">Путь папки — поддерживаемая подмастерье</span><span class="sxs-lookup"><span data-stu-id="f917f-154">Folder path - wildcard supported</span></span>
    * <span data-ttu-id="f917f-155">IP-адрес</span><span class="sxs-lookup"><span data-stu-id="f917f-155">IP address</span></span>
    * <span data-ttu-id="f917f-156">URL-адрес — поддерживаемая подмайка</span><span class="sxs-lookup"><span data-stu-id="f917f-156">URL - wildcard supported</span></span>
    * <span data-ttu-id="f917f-157">Командная строка — подстройка поддерживается</span><span class="sxs-lookup"><span data-stu-id="f917f-157">Command line - wildcard supported</span></span>

3. <span data-ttu-id="f917f-158">Выберите **запуск МОК**.</span><span class="sxs-lookup"><span data-stu-id="f917f-158">Select the **Triggering IOC**.</span></span>
    
4. <span data-ttu-id="f917f-159">Укажите действие и область в оповещении.</span><span class="sxs-lookup"><span data-stu-id="f917f-159">Specify the action and scope on the alert.</span></span> <br>
   <span data-ttu-id="f917f-160">Вы можете автоматически разрешить предупреждение или скрыть его от портала.</span><span class="sxs-lookup"><span data-stu-id="f917f-160">You can automatically resolve an alert or hide it from the portal.</span></span> <span data-ttu-id="f917f-161">Оповещения, которые будут автоматически устранены, будут отображаться в разрешенных разделах очереди оповещений, страницы оповещения и временной шкалы устройств и будут отображаться как разрешенные в API Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="f917f-161">Alerts that are automatically resolved will appear in the resolved section of the alerts queue, alert page, and device timeline and will appear as resolved across Defender for Endpoint APIs.</span></span> <br><br> <span data-ttu-id="f917f-162">Оповещения, помеченные как скрытые, будут подавляться из всей системы, как на связанных оповещениях устройства, так и на панели мониторинга и не будут передаваться по API Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="f917f-162">Alerts that are marked as hidden will be suppressed from the entire system, both on the device's associated alerts and from the dashboard and will not be streamed across Defender for Endpoint APIs.</span></span>


5. <span data-ttu-id="f917f-163">Введите имя правила и комментарий.</span><span class="sxs-lookup"><span data-stu-id="f917f-163">Enter a rule name and a comment.</span></span>

6. <span data-ttu-id="f917f-164">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f917f-164">Click **Save**.</span></span>

#### <a name="view-the-list-of-suppression-rules"></a><span data-ttu-id="f917f-165">Просмотр списка правил подавления</span><span class="sxs-lookup"><span data-stu-id="f917f-165">View the list of suppression rules</span></span>

1. <span data-ttu-id="f917f-166">В области навигации выберите подавление **параметров**  >  **оповещения.**</span><span class="sxs-lookup"><span data-stu-id="f917f-166">In the navigation pane, select **Settings** > **Alert suppression**.</span></span>

2. <span data-ttu-id="f917f-167">В списке правил подавления показаны все правила, созданные пользователями в организации.</span><span class="sxs-lookup"><span data-stu-id="f917f-167">The list of suppression rules shows all the rules that users in your organization have created.</span></span>

<span data-ttu-id="f917f-168">Дополнительные сведения об управлении правилами подавления см. в дополнительных сведениях [об управлении правилами подавления.](manage-suppression-rules.md)</span><span class="sxs-lookup"><span data-stu-id="f917f-168">For more information on managing suppression rules, see [Manage suppression rules](manage-suppression-rules.md)</span></span>

## <a name="change-the-status-of-an-alert"></a><span data-ttu-id="f917f-169">Изменение состояния оповещений</span><span class="sxs-lookup"><span data-stu-id="f917f-169">Change the status of an alert</span></span>

<span data-ttu-id="f917f-170">Вы можете классифицировать оповещения **(как New,** **In Progress** или **Resolved),** изменяя их состояние по мере выполнения расследования.</span><span class="sxs-lookup"><span data-stu-id="f917f-170">You can categorize alerts (as **New**, **In Progress**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="f917f-171">Это поможет вам организовать и управлять тем, как ваша команда может реагировать на оповещения.</span><span class="sxs-lookup"><span data-stu-id="f917f-171">This helps you organize and manage how your team can respond to alerts.</span></span>

<span data-ttu-id="f917f-172">Например, руководитель группы может  просмотреть все новые оповещений и назначить их в очередь **In Progress** для дальнейшего анализа.</span><span class="sxs-lookup"><span data-stu-id="f917f-172">For example, a team leader can review all **New** alerts, and decide to assign them to the **In Progress** queue for further analysis.</span></span>

<span data-ttu-id="f917f-173">Кроме того, руководитель группы может назначить оповещение в очередь **Resolved,** если они знают, что оповещение является доброкачественным, исходя из устройства, которое не имеет значения (например, одного из администраторов безопасности), или рассматривается с помощью более ранней оповещений.</span><span class="sxs-lookup"><span data-stu-id="f917f-173">Alternatively, the team leader might assign the alert to the **Resolved** queue if they know the alert is benign, coming from a device that is irrelevant (such as one belonging to a security administrator), or is being dealt with through an earlier alert.</span></span>



## <a name="alert-classification"></a><span data-ttu-id="f917f-174">Классификация оповещений</span><span class="sxs-lookup"><span data-stu-id="f917f-174">Alert classification</span></span>
<span data-ttu-id="f917f-175">Вы можете не устанавливать классификацию или указывать, является ли предупреждение настоящим оповещением или ложным предупреждением.</span><span class="sxs-lookup"><span data-stu-id="f917f-175">You can choose not to set a classification, or specify whether an alert is a true alert or a false alert.</span></span> <span data-ttu-id="f917f-176">Важно предоставить классификацию истинного положительного или ложного срабатыва.</span><span class="sxs-lookup"><span data-stu-id="f917f-176">It's important to provide the classification of true positive/false positive.</span></span> <span data-ttu-id="f917f-177">Эта классификация используется для мониторинга качества оповещения и повышения точности оповещений.</span><span class="sxs-lookup"><span data-stu-id="f917f-177">This classification is used to monitor alert quality, and make alerts more accurate.</span></span> <span data-ttu-id="f917f-178">Поле "определение" определяет дополнительную верность для "истинно положительной" классификации.</span><span class="sxs-lookup"><span data-stu-id="f917f-178">The "determination" field defines additional fidelity for a "true positive" classification.</span></span> 

## <a name="add-comments-and-view-the-history-of-an-alert"></a><span data-ttu-id="f917f-179">Добавление комментариев и просмотр истории оповещения</span><span class="sxs-lookup"><span data-stu-id="f917f-179">Add comments and view the history of an alert</span></span>
<span data-ttu-id="f917f-180">Вы можете добавить комментарии и просмотреть исторические события о предупреждении, чтобы увидеть предыдущие изменения, внесенные в оповещение.</span><span class="sxs-lookup"><span data-stu-id="f917f-180">You can add comments and view historical events about an alert to see previous changes made to the alert.</span></span>

<span data-ttu-id="f917f-181">Всякий раз, когда в оповещение внося изменения или комментарии, они записывают в **разделе Комментарии и история.**</span><span class="sxs-lookup"><span data-stu-id="f917f-181">Whenever a change or comment is made to an alert, it is recorded in the **Comments and history** section.</span></span>

<span data-ttu-id="f917f-182">Добавленные комментарии сразу же появляются в соответствующей области.</span><span class="sxs-lookup"><span data-stu-id="f917f-182">Added comments instantly appear on the pane.</span></span>


## <a name="related-topics"></a><span data-ttu-id="f917f-183">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f917f-183">Related topics</span></span>
- [<span data-ttu-id="f917f-184">Управление правилами подавления</span><span class="sxs-lookup"><span data-stu-id="f917f-184">Manage suppression rules</span></span>](manage-suppression-rules.md)
- [<span data-ttu-id="f917f-185">Просмотр и организация очереди оповещений Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="f917f-185">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="f917f-186">Исследование оповещений Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="f917f-186">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="f917f-187">Исследование файла, связанного с оповещением Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="f917f-187">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="f917f-188">Исследование устройств в списке Устройств конечных точек Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="f917f-188">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="f917f-189">Исследование IP-адреса, связанного с оповещением Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f917f-189">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="f917f-190">Исследование домена, связанного с оповещением Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f917f-190">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="f917f-191">Исследование учетной записи пользователя в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f917f-191">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
