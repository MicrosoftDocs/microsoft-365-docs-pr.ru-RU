---
title: Добавление хранителей в Advanced eDiscovery случае
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Узнайте, как использовать встроенный инструмент управления хранителями в Advanced eDiscovery для координации рабочего процесса и определения соответствующих источников данных в случае.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9468fb889e9115b3652d1dba8a6c6632bb367fe3
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740346"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="cfc9e-103">Добавление хранителей в Advanced eDiscovery случае</span><span class="sxs-lookup"><span data-stu-id="cfc9e-103">Add custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="cfc9e-104">Используйте встроенный инструмент управления хранителями в Advanced eDiscovery для координации рабочего процесса по управлению хранителями и выявлению соответствующих источников данных, связанных с делом.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-104">Use the built-in custodian management tool in Advanced eDiscovery to coordinate your workflows around managing custodians and identifying relevant, custodial data sources associated with a case.</span></span> <span data-ttu-id="cfc9e-105">При добавлении хранителя система может автоматически идентифицировать и разместить удержание на Exchange и OneDrive для бизнеса учетной записи.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-105">When you add a custodian, the system can automatically identify and place a hold on their Exchange mailbox and OneDrive for Business account.</span></span> <span data-ttu-id="cfc9e-106">В процессе обнаружения при расследовании можно также идентифицировать другие источники данных (например, почтовые ящики, сайты или Teams), к которые был предоставлен доступ к хранителям или к ним.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-106">During the discovery process of your investigation, you might also identify other data sources (such as mailboxes, sites, or Teams) that a custodian accessed or contributed to.</span></span> <span data-ttu-id="cfc9e-107">В этой ситуации можно использовать средство управления хранителями, чтобы связать эти источники данных с конкретным хранителями.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-107">In this situation, you can use the custodian management tool to associate those data sources will a specific custodian.</span></span> <span data-ttu-id="cfc9e-108">После добавления хранителей в дело и связи другого источника данных с ними можно быстро сохранить данные и поиска данных хранения.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-108">After you add custodians to a case and associate other data source with them, you can quickly preserve data and search the custodial data.</span></span>

<span data-ttu-id="cfc9e-109">Вы можете добавлять и управлять хранителями в Advanced eDiscovery в четырех шагах:</span><span class="sxs-lookup"><span data-stu-id="cfc9e-109">You can add and manage custodians in Advanced eDiscovery cases in four steps:</span></span>

1. <span data-ttu-id="cfc9e-110">Определите хранителей.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-110">Identify the custodians.</span></span>

2. <span data-ttu-id="cfc9e-111">Выберите расположения данных хранителя.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-111">Choose custodian data locations.</span></span>

3. <span data-ttu-id="cfc9e-112">Настройка параметров удержания.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-112">Configure hold settings.</span></span>

4. <span data-ttu-id="cfc9e-113">Просмотрите хранителей и завершите процесс.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-113">Review the custodians and complete the process.</span></span>

   <span data-ttu-id="cfc9e-114">[![Вкладка Источники в Advanced eDiscovery случае ](../media/AeD-Sources-Tab.png)](../media/AeD-Sources-Tab.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="cfc9e-114">[ ![Sources tab in Advanced eDiscovery case](../media/AeD-Sources-Tab.png) ](../media/AeD-Sources-Tab.png#lightbox)</span></span>

## <a name="make-sure-you-have-the-necessary-permissions"></a><span data-ttu-id="cfc9e-115">Убедитесь, что у вас есть необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="cfc9e-115">Make sure you have the necessary permissions</span></span>

<span data-ttu-id="cfc9e-116">Чтобы добавить хранителей в дело, необходимо быть членом группы ролей диспетчера электронных открытий.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-116">To add custodians to a case, you must be a member of the eDiscovery Manager role group.</span></span> <span data-ttu-id="cfc9e-117">Это предоставляет вам необходимые разрешения для добавления хранителей в дело и хранения источников данных.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-117">This provides you with the necessary permissions to add custodians to a case and place a hold on the custodial data sources.</span></span> <span data-ttu-id="cfc9e-118">Дополнительные сведения см. в статье [Назначение разрешений на обнаружение электронных данных](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions).</span><span class="sxs-lookup"><span data-stu-id="cfc9e-118">For more information, see [Assign eDiscovery permissions](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions).</span></span>

## <a name="step-1-identify-custodians"></a><span data-ttu-id="cfc9e-119">Шаг 1. Определение хранителей</span><span class="sxs-lookup"><span data-stu-id="cfc9e-119">Step 1: Identify custodians</span></span>

1. <span data-ttu-id="cfc9e-120">Войдите и войдите в учетную запись пользователя, которая получила соответствующие разрешения на [https://compliance.microsoft.com](https://compliance.microsoft.com) открытие электронных данных.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-120">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in with a user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="cfc9e-121">В левой области навигации Центра соответствия требованиям Microsoft 365 нажмите **Показать все** и выберите **Обнаружение электронных данных > Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-121">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Advanced**.</span></span>

3. <span data-ttu-id="cfc9e-122">На **Advanced eDiscovery** нажмите вкладку **Cases** и выберите случай, в который необходимо добавить хранителей.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-122">On the **Advanced eDiscovery** page, click the **Cases** tab, and then select the case that you want to add custodians to.</span></span>

4. <span data-ttu-id="cfc9e-123">Щелкните **вкладку Источники** данных и нажмите **кнопку Добавить источник данных** Добавить новые  >  **хранители**.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-123">Click the **Data sources** tab and then click **Add data source** > **Add new custodians**.</span></span>

5. <span data-ttu-id="cfc9e-124">Добавьте в дело одного или несколько пользователей в качестве хранителей, введя первую часть имени или псевдонима пользователя.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-124">Add one or more users in your organization as custodians to the case by typing the first part of a person's name or alias.</span></span> <span data-ttu-id="cfc9e-125">После того как вы найдете правильного человека, выберите его имя, чтобы добавить их в список.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-125">After you find the correct person, select their name to add them to the list.</span></span>

## <a name="step-2-choose-custodian-data-locations"></a><span data-ttu-id="cfc9e-126">Шаг 2. Выбор расположения данных хранителя</span><span class="sxs-lookup"><span data-stu-id="cfc9e-126">Step 2: Choose custodian data locations</span></span>

<span data-ttu-id="cfc9e-127">После выбора хранителей система автоматически пытается определить и проверить этих пользователей и их источники данных.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-127">After you select custodians, the system automatically attempts to identify and verify these users and their data sources.</span></span> <span data-ttu-id="cfc9e-128">После добавления хранителей в список средство автоматически включает основной почтовый ящик и OneDrive учетную запись для каждого хранителя.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-128">After adding custodians to the list, the tool automatically includes the primary mailbox and OneDrive account for each custodian.</span></span> <span data-ttu-id="cfc9e-129">Вы можете не включать эти источники данных при добавлении хранителей в дело.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-129">You can choose not to include these data sources when adding custodians to the case.</span></span>

<span data-ttu-id="cfc9e-130">Помимо почтового ящика и учетной записи OneDrive хранителя вы также можете связать другие расположения данных с хранителями, такими как сайт SharePoint или Microsoft Team, в который входит хранитель.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-130">In addition to a custodian's mailbox and OneDrive account, you can also associate other data locations to a custodian, such as SharePoint site or a Microsoft Team the custodian is a member of.</span></span> <span data-ttu-id="cfc9e-131">Это позволяет сохранять, собирать, анализировать и анализировать контент в других источниках данных, связанных с хранителями дела.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-131">This allows you to preserve, collect, analyze, and review content in other data sources associated with the custodians of the case.</span></span>

<span data-ttu-id="cfc9e-132">Для отселки основного почтового ящика и OneDrive учетной записи хранителя:</span><span class="sxs-lookup"><span data-stu-id="cfc9e-132">To deselect the primary mailbox and OneDrive account for a custodian:</span></span>

1. <span data-ttu-id="cfc9e-133">Раздвойте хранителя, чтобы просмотреть основные расположения данных, автоматически связанные с каждым хранителями.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-133">Expand the custodian to view the primary data locations that have been automatically associated to each custodian.</span></span>

2. <span data-ttu-id="cfc9e-134">Выберите **Clear**  рядом с почтовым **ящиком или OneDrive,** чтобы удалить почтовый ящик или OneDrive или учетную запись хранителя в качестве расположения данных для этого хранителя.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-134">Select **Clear** next to **Mailbox** or **OneDrive** to remove a custodian's mailbox or OneDrive account from being associated as a data location for this custodian.</span></span>

   ![Настройка расположения для связывать с хранителями](../media/ConfigureCustodianLocations.png)

<span data-ttu-id="cfc9e-136">Чтобы связать другие почтовые ящики, сайты, Teams или Yammer группы с определенным хранителями:</span><span class="sxs-lookup"><span data-stu-id="cfc9e-136">To associate other mailboxes, sites, Teams, or Yammer groups to a specific custodian:</span></span>

1. <span data-ttu-id="cfc9e-137">Развяви хранителя, чтобы отобразить следующие службы, чтобы связать расположения данных с хранителями.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-137">Expand a custodian to display the following services to associate data locations with the custodian.</span></span> <span data-ttu-id="cfc9e-138">Нажмите **кнопку Изменить** рядом со службой, чтобы добавить расположение данных.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-138">Click **Edit** next to a service to add a data location.</span></span>

   - <span data-ttu-id="cfc9e-139">**Exchange:** Используйте для связывать другие почтовые ящики с хранителями.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-139">**Exchange**: Use to associate other mailboxes to the custodian.</span></span> <span data-ttu-id="cfc9e-140">Введите в поле поиска имя или псевдоним (не менее трех символов) почтовых ящиков пользователей или групп рассылки.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-140">Type into the search box the name or alias (a minimum of three characters) of user mailboxes or distribution groups.</span></span> <span data-ttu-id="cfc9e-141">Выберите почтовые ящики для назначения хранителю и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-141">Select the mailboxes to assign to the custodian and then click **Add**.</span></span>

   - <span data-ttu-id="cfc9e-142">**SharePoint:** Используйте для SharePoint сайтов с хранителями.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-142">**SharePoint**: Use to associate SharePoint sites to the custodian.</span></span> <span data-ttu-id="cfc9e-143">Выберите сайт в списке или наведите URL-адрес в поле поиска.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-143">Select a site in the list or search for a site by typing a URL in the search box.</span></span> <span data-ttu-id="cfc9e-144">Выберите сайты для назначения хранителю и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-144">Select the sites to assign to the custodian and then click **Add**.</span></span>

   - <span data-ttu-id="cfc9e-145">**Teams.** Используйте для назначения Microsoft Teams, в который в настоящее время входит хранитель.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-145">**Teams**: Use to assign the Microsoft Teams the custodian is currently a member of.</span></span> <span data-ttu-id="cfc9e-146">Выберите группы, назначив хранителю, а затем нажмите **кнопку Добавить**.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-146">Select the teams to assign to the custodian and then click **Add**.</span></span> <span data-ttu-id="cfc9e-147">После добавления группы система автоматически определяет и находит SharePoint и почтовый ящик группы, связанных с этой группой, и назначает их хранителю.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-147">After you add a team, the system automatically identifies and locates the SharePoint site and group mailbox associated to that team and assigns them to the custodian.</span></span>

   - <span data-ttu-id="cfc9e-148">**Yammer:** Используйте для назначения Yammer групп, в которые в настоящее время входит хранитель.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-148">**Yammer**:  Use to assign the Yammer groups the custodian is currently a member of.</span></span> <span data-ttu-id="cfc9e-149">Выберите группы для назначения хранителю и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-149">Select the groups to assign to the custodian and then click **Add**.</span></span> <span data-ttu-id="cfc9e-150">После добавления группы система автоматически определяет и находит SharePoint и почтовый ящик группы, связанных с этой группой, и назначает их хранителю.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-150">After you add a team, the system automatically identifies and locates the SharePoint site and group mailbox associated to that group and assigns them to the custodian.</span></span>

   > [!NOTE]
   > <span data-ttu-id="cfc9e-151">Вы можете  использовать Exchange и **SharePoint** для связывать другие группы или группы Yammer (в которые хранитель не входит) с хранителями.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-151">You can use the **Exchange** and **SharePoint** location pickers to associate other teams or Yammer groups (that a custodian is not a member of) to a custodian.</span></span> <span data-ttu-id="cfc9e-152">Для этого необходимо добавить почтовый ящик и сайт, связанный с каждой группой или Yammer группой.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-152">To do this, you have to add both the mailbox and site associated with each team or Yammer group.</span></span>

2. <span data-ttu-id="cfc9e-153">Вы можете просмотреть общее число почтовых ящиков, сайтов, Teams и Yammer групп, назначенных каждому хранителя, расширяя каждый хранитель в таблице.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-153">You can view the total number of mailboxes, sites, Teams, and Yammer groups assigned to each custodian by expanding each custodian in the table.</span></span> <span data-ttu-id="cfc9e-154">Когда вы завершите назначенное расположение данных для каждого хранителя, эти ассоциации будут поддерживаться и использоваться во время этапов сбора, обработки и проверки в процессе Advanced eDiscovery процесса.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-154">When you've finalized the assigned data locations for each custodian, these associations will be maintained and used during the collection, processing, and review stages in the Advanced eDiscovery workflow.</span></span>

3. <span data-ttu-id="cfc9e-155">После добавления хранителей и настройки расположения данных щелкните **Далее,** чтобы перейти на страницу **Параметры удержания.**</span><span class="sxs-lookup"><span data-stu-id="cfc9e-155">After adding custodians and configuring their data locations, click **Next** to go to the **Hold settings** page.</span></span>  

## <a name="step-3-configure-hold-settings"></a><span data-ttu-id="cfc9e-156">Шаг 3. Настройка параметров удержания</span><span class="sxs-lookup"><span data-stu-id="cfc9e-156">Step 3: Configure hold settings</span></span>

 <span data-ttu-id="cfc9e-157">После завершения работы с хранителями и расположениями данных можно придержать некоторых или всех хранителей.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-157">After you've finalized the custodians and their data locations, you can place some or all of the custodians on hold.</span></span> <span data-ttu-id="cfc9e-158">При удержании хранителя все содержимое во всех расположениях контента, связанных с хранителями, сохраняется до удаления удержания или освобождения хранителя из удержания.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-158">When you place a custodian on hold, all content in all content locations that are associated with the custodian is preserved until you remove the hold or release the custodian from the hold.</span></span> <span data-ttu-id="cfc9e-159">В некоторых случаях может потребоваться добавить хранителей в дело, не помещая их на удержание.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-159">In some cases, you may want to add custodians to a case without placing them on hold.</span></span>

<span data-ttu-id="cfc9e-160">Для удержания хранителей и источников данных:</span><span class="sxs-lookup"><span data-stu-id="cfc9e-160">To place the custodians and data sources on hold:</span></span>

1. <span data-ttu-id="cfc9e-161">На странице **Параметры удержания** можно применить удержание к отдельным хранителям, выбрав почтовый ящик в столбце **Удержание.**</span><span class="sxs-lookup"><span data-stu-id="cfc9e-161">On the **Hold settings** page, you can apply a hold to individual custodians by selecting the checkbox under the **Hold** column.</span></span>

   <span data-ttu-id="cfc9e-162">Кроме того, вы можете разместить всех хранителей на удержание, выбрав контрольный ящик **Hold** в верхней части столбца.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-162">Alternatively, you can place all custodians on hold by selecting the **Hold** checkbox at the top of the column.</span></span>

2. <span data-ttu-id="cfc9e-163">Проверьте выборы удержания хранителя и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-163">Verify the custodian hold selections and then click **Next**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="cfc9e-164">Если не разместить удержание на хранителях, хранитель и связанные с ним источники данных будут добавлены в дело, но содержимое в этих источниках данных не будет сохранено удержанием, связанным с делом.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-164">If you don't place a hold on a custodian, the custodian and their associated data sources will be added to the case but the content in those data sources won't preserved by the hold that associated with the case.</span></span>

## <a name="step-4-review-the-custodians-and-complete-the-process"></a><span data-ttu-id="cfc9e-165">Шаг 4. Просмотр хранителей и завершение процесса</span><span class="sxs-lookup"><span data-stu-id="cfc9e-165">Step 4: Review the custodians and complete the process</span></span>

<span data-ttu-id="cfc9e-166">Перед добавлением хранителей в дело можно просмотреть список хранителей, назначенное им расположение данных и параметры хранения.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-166">Before you actually add the custodians to the case, you can review the list of custodians, the data locations assigned to them, and the hold settings.</span></span>

1. <span data-ttu-id="cfc9e-167">Проверка и проверка всех источников данных и параметр удержания, связанных с каждым хранителями в таблице.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-167">Verify and review all the data sources count and the hold setting associated with each custodian in the table.</span></span> <span data-ttu-id="cfc9e-168">При необходимости перейдите на страницу **Определить хранителя** или **параметры удержания,** чтобы внести какие-либо изменения.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-168">If necessary, go back to the **Identify custodian** or **Hold settings** pages to make any changes.</span></span>

2. <span data-ttu-id="cfc9e-169">Щелкните **Отправить,** чтобы добавить хранителей и их расположения данных в дело и применить все параметры хранения.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-169">Click **Submit** to add custodians and their data locations to the case and apply all custodial hold settings.</span></span>

   <span data-ttu-id="cfc9e-170">Новые хранители добавляются в дело и отображаются на вкладке **Источники** данных.</span><span class="sxs-lookup"><span data-stu-id="cfc9e-170">The new custodians are added to the case and displayed on the **Data sources** tab.</span></span>

   <span data-ttu-id="cfc9e-171">[![Хранители, перечисленные на вкладке Источники данных ](../media/DataSourcesTab.png)](../media/DataSourcesTab.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="cfc9e-171">[ ![Custodians listed on the Data sources tab](../media/DataSourcesTab.png) ](../media/DataSourcesTab.png#lightbox)</span></span>
