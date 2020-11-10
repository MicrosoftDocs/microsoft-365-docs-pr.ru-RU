---
title: 'Управление сетью управления знаниями (Предварительная версия) '
description: Настройка управления знаниями.
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 265816a8d3d04b8d10b529f1ea1a0b658aa2931d
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "48989013"
---
# <a name="manage-your-knowledge-management-network-preview"></a><span data-ttu-id="a3e05-103">Управление сетью управления знаниями (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="a3e05-103">Manage your knowledge management network (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="a3e05-104">Содержимое этой статьи предназначено для Кортексного предварительного просмотра Project.</span><span class="sxs-lookup"><span data-stu-id="a3e05-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="a3e05-105">[Узнайте больше о работе с Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="a3e05-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>


<span data-ttu-id="a3e05-106">После [настройки управления знаниями](set-up-topic-experiences.md)в любое время администратор может внести изменения в параметры конфигурации с помощью центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3e05-106">After you [set up knowledge management](set-up-topic-experiences.md), at any time afterwards an admin can make adjustments to your configuration settings through the Microsoft 365 admin center.</span></span>

<span data-ttu-id="a3e05-107">Например, может потребоваться настроить параметры для любой из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="a3e05-107">For example, you may need to adjust your settings for any of the following:</span></span>
- <span data-ttu-id="a3e05-108">Добавление новых источников SharePoint в разделы "мои разделы".</span><span class="sxs-lookup"><span data-stu-id="a3e05-108">Add new SharePoint sources to mine topics.</span></span>
- <span data-ttu-id="a3e05-109">Изменение пользователей, имеющих доступ к разделам.</span><span class="sxs-lookup"><span data-stu-id="a3e05-109">Change which users will have access to topics.</span></span>
- <span data-ttu-id="a3e05-110">Изменение пользователей, у которых есть разрешения на выполнение задач в центре разделов.</span><span class="sxs-lookup"><span data-stu-id="a3e05-110">Change which users have permissions to do tasks on the topic center.</span></span>
- <span data-ttu-id="a3e05-111">Изменение имени центра разделов</span><span class="sxs-lookup"><span data-stu-id="a3e05-111">Change the name of your topic center</span></span>


## <a name="requirements"></a><span data-ttu-id="a3e05-112">Requirements</span><span class="sxs-lookup"><span data-stu-id="a3e05-112">Requirements</span></span> 
<span data-ttu-id="a3e05-113">Чтобы получить доступ к центру администрирования Microsoft 365 и управлять задачами организационных знаний, необходимы разрешения глобального администратора или администратора SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a3e05-113">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and manage Organizational knowledge tasks.</span></span>


## <a name="to-access-knowledge-management-settings"></a><span data-ttu-id="a3e05-114">Чтобы получить доступ к параметрам управления знаниями:</span><span class="sxs-lookup"><span data-stu-id="a3e05-114">To access knowledge management settings:</span></span>

1. <span data-ttu-id="a3e05-115">В центре администрирования Microsoft 365 выберите пункт **Настройка** , а затем просмотрите раздел **сведения о организации** .</span><span class="sxs-lookup"><span data-stu-id="a3e05-115">In the Microsoft 365 admin center, select **Setup** , and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="a3e05-116">В разделе " **сведения о организации** " щелкните **подключить пользователей к набору знаний**.</span><span class="sxs-lookup"><span data-stu-id="a3e05-116">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![Подключение пользователей к базе знаний](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="a3e05-118">На странице **подключить людей к сведениям** выберите **Управление** , чтобы открыть область **Параметры сети базы знаний** .</span><span class="sxs-lookup"><span data-stu-id="a3e05-118">On the **Connect people to knowledge** page, select **Manage** to open the **Knowledge network settings** pane.</span></span><br/>

    ![Knowledge – Network — параметры](../media/content-understanding/knowledge-network-settings.png) </br>

## <a name="change-how-the-knowledge-network-can-find-topics"></a><span data-ttu-id="a3e05-120">Изменение сведений о том, как сеть может находить темы</span><span class="sxs-lookup"><span data-stu-id="a3e05-120">Change how the knowledge network can find topics</span></span>

<span data-ttu-id="a3e05-121">Перейдите на вкладку **Обнаружение разделов** , если хотите обновить выбранные варианты для источников разделов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a3e05-121">Select the **Topic discovery** tab if you want to update your choices for  for SharePoint topic sources.</span></span> <span data-ttu-id="a3e05-122">Этот параметр позволяет выбрать сайты SharePoint в клиенте, для которых будет выполняться обход и mined для разделов.</span><span class="sxs-lookup"><span data-stu-id="a3e05-122">This setting let you select the SharePoint sites in your tenant that will be crawled and mined for topics.</span></span>

1. <span data-ttu-id="a3e05-123">На вкладке **Обнаружение разделов** в разделе **Выбор источников разделов SharePoint** нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="a3e05-123">On the **Topic discovery** tab, under **Select SharePoint topic sources** , select **Edit**.</span></span>
2. <span data-ttu-id="a3e05-124">На странице " **Выбор источников разделов SharePoint** " выберите сайты SharePoint, которые будут обходиться в качестве источников для разделов во время обнаружения.</span><span class="sxs-lookup"><span data-stu-id="a3e05-124">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="a3e05-125">К ним относятся:</span><span class="sxs-lookup"><span data-stu-id="a3e05-125">This includes:</span></span></br>
    <span data-ttu-id="a3e05-126">а.</span><span class="sxs-lookup"><span data-stu-id="a3e05-126">a.</span></span> <span data-ttu-id="a3e05-127">**Все сайты** : все сайты SharePoint в клиенте.</span><span class="sxs-lookup"><span data-stu-id="a3e05-127">**All sites** : All SharePoint sites in your tenant.</span></span> <span data-ttu-id="a3e05-128">Это записывает текущие и будущие сайты.</span><span class="sxs-lookup"><span data-stu-id="a3e05-128">This captures current and future sites.</span></span></br>
    <span data-ttu-id="a3e05-129">б.</span><span class="sxs-lookup"><span data-stu-id="a3e05-129">b.</span></span> <span data-ttu-id="a3e05-130">**Все, кроме выбранных сайтов** : введите имена сайтов, которые вы хотите исключить.</span><span class="sxs-lookup"><span data-stu-id="a3e05-130">**All, except selected sites** : Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="a3e05-131">Вы также можете отправить список сайтов, которые вы хотите отказаться от обнаружения.</span><span class="sxs-lookup"><span data-stu-id="a3e05-131">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="a3e05-132">Сайты, созданные в будущем, будут включены в качестве источников для обнаружения разделов.</span><span class="sxs-lookup"><span data-stu-id="a3e05-132">Sites created in the future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="a3e05-133">в.</span><span class="sxs-lookup"><span data-stu-id="a3e05-133">c.</span></span> <span data-ttu-id="a3e05-134">**Только выбранные сайты** : введите имена сайтов, которые необходимо включить в список.</span><span class="sxs-lookup"><span data-stu-id="a3e05-134">**Only selected sites** : Type the names of the sites you want to include.</span></span> <span data-ttu-id="a3e05-135">Вы также можете отправить список сайтов.</span><span class="sxs-lookup"><span data-stu-id="a3e05-135">You can also upload a list of sites.</span></span> <span data-ttu-id="a3e05-136">Сайты, созданные в будущем, не будут включены в качестве источников для обнаружения разделов.</span><span class="sxs-lookup"><span data-stu-id="a3e05-136">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![Выбор способа поиска разделов](../media/content-understanding/k-manage-select-topic-source.png) </br>
   
    <span data-ttu-id="a3e05-138">Если вы хотите исключить несколько сайтов (если выбрать **все, кроме выбранных сайтов** ) или включить (если выбрано **только выбранные сайты** ), можно отправить CSV-файл с именами и URL-адресами сайтов.</span><span class="sxs-lookup"><span data-stu-id="a3e05-138">If you have a number of sites that you want to exclude (if you select **All, except selected sites** ) or include (if you selected **Only selected sites** ), you can choose to upload a CSV file with the site names and URLs.</span></span> <span data-ttu-id="a3e05-139">Вы можете выбрать **скачать шаблон сайта Template. csv** , если вы хотите использовать CSV-файл шаблона.</span><span class="sxs-lookup"><span data-stu-id="a3e05-139">You can select **Download site template .csv** if you want to use the CSV template file.</span></span>

3. <span data-ttu-id="a3e05-140">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a3e05-140">Select **Save**.</span></span>

##  <a name="change-who-can-see-topics-in-your-organization"></a><span data-ttu-id="a3e05-141">Изменение пользователей, которые могут просматривать темы в Организации</span><span class="sxs-lookup"><span data-stu-id="a3e05-141">Change who can see topics in your organization</span></span>

<span data-ttu-id="a3e05-142">Перейдите на вкладку **Обнаружение разделов** , чтобы обновить сведения о том, кто в вашей организации может видеть найденные темы в результатах поиска и когда темы выделяются в контенте, например на страницах SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a3e05-142">Select the **Topic discovery** tab if you want to update who in your organization can see discovered topics in search results and when topics are highlighted in content like SharePoint pages.</span></span>

1. <span data-ttu-id="a3e05-143">На вкладке **Обнаружение разделов** в разделе **Пользователи, которые могут видеть разделы в сети знаний** нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="a3e05-143">On the **Topic discovery** tab, under **Who can see topics in the knowledge network** , select **Edit**.</span></span>
2. <span data-ttu-id="a3e05-144">Сведения о том, **кто может просматривать разделы** на странице сведения о сети, можно выбрать, кто будет иметь доступ к сведениям о теме, например подразделам, карточкам разделов, темам в поиске и страницам темы.</span><span class="sxs-lookup"><span data-stu-id="a3e05-144">On the **Who can see topics in the knowledge network** page, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="a3e05-145">Можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="a3e05-145">You can select:</span></span></br>
    <span data-ttu-id="a3e05-146">а.</span><span class="sxs-lookup"><span data-stu-id="a3e05-146">a.</span></span> <span data-ttu-id="a3e05-147">**Все в организации**</span><span class="sxs-lookup"><span data-stu-id="a3e05-147">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="a3e05-148">б.</span><span class="sxs-lookup"><span data-stu-id="a3e05-148">b.</span></span> <span data-ttu-id="a3e05-149">**Только выбранные пользователи или группы безопасности**</span><span class="sxs-lookup"><span data-stu-id="a3e05-149">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="a3e05-150">в.</span><span class="sxs-lookup"><span data-stu-id="a3e05-150">c.</span></span> <span data-ttu-id="a3e05-151">**Никто**</span><span class="sxs-lookup"><span data-stu-id="a3e05-151">**No one**</span></span></br>

    ![Кто может просматривать темы](../media/content-understanding/k-manage-who-can-see-topics.png) </br> 
3. <span data-ttu-id="a3e05-153">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a3e05-153">Select **Save**.</span></span>  
 
> [!Note] 
> <span data-ttu-id="a3e05-154">Несмотря на то, что этот параметр позволяет выбрать любого пользователя в Организации, будут доступны только те пользователи, которым назначены лицензии управления знаниями.</span><span class="sxs-lookup"><span data-stu-id="a3e05-154">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span>

## <a name="change-who-has-permissions-to-do-tasks-on-the-topic-center"></a><span data-ttu-id="a3e05-155">Изменение разрешений на выполнение задач в центре разделов</span><span class="sxs-lookup"><span data-stu-id="a3e05-155">Change who has permissions to do tasks on the topic center</span></span>

<span data-ttu-id="a3e05-156">Перейдите на вкладку **разрешения раздела** , если вы хотите обновить разрешения на выполнение следующих действий на странице "центр разделов":</span><span class="sxs-lookup"><span data-stu-id="a3e05-156">Select the **Topic permissions** tab if you want to update who has permissions to do the following in the topic center page:</span></span>

- <span data-ttu-id="a3e05-157">Какие пользователи могут создавать и изменять разделы: создание новых тем, которые не были найдены во время обнаружения или редактирования существующих сведений о странице темы.</span><span class="sxs-lookup"><span data-stu-id="a3e05-157">Which users can create and edit topics: Create new topics that were not found during discovery or edit existing topic page details.</span></span>
- <span data-ttu-id="a3e05-158">Какие пользователи могут управлять разделами: подтверждение или отклонение обнаруженных разделов.</span><span class="sxs-lookup"><span data-stu-id="a3e05-158">Which users can manage topics: Confirm or reject discovered topics.</span></span>

<span data-ttu-id="a3e05-159">Чтобы обновить разделы, у которых есть разрешения на создание и редактирование разделов:</span><span class="sxs-lookup"><span data-stu-id="a3e05-159">To update who has permissions to create and edit topics:</span></span>

1. <span data-ttu-id="a3e05-160">На вкладке **разрешения раздела** в разделе **Пользователи, которые могут создавать и редактировать разделы** нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="a3e05-160">On the **Topic permissions** tab, under **Who can create and edit topics** , select **Edit**.</span></span></br>
2. <span data-ttu-id="a3e05-161">На странице **пользователи могут создавать и редактировать темы** можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="a3e05-161">On the **Who can create and edit topics** page, you can select:</span></span></br>
    <span data-ttu-id="a3e05-162">а.</span><span class="sxs-lookup"><span data-stu-id="a3e05-162">a.</span></span> <span data-ttu-id="a3e05-163">**Все в организации**</span><span class="sxs-lookup"><span data-stu-id="a3e05-163">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="a3e05-164">б.</span><span class="sxs-lookup"><span data-stu-id="a3e05-164">b.</span></span> <span data-ttu-id="a3e05-165">**Только выбранные пользователи или группы безопасности**</span><span class="sxs-lookup"><span data-stu-id="a3e05-165">**Only selected people or security groups**</span></span></br>

    ![Создание и редактирование разделов](../media/content-understanding/k-manage-who-can-create-and-edit.png) </br> 

3. <span data-ttu-id="a3e05-167">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a3e05-167">Select **Save**.</span></span></br>

<span data-ttu-id="a3e05-168">Чтобы обновить разрешения для управления разделами, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a3e05-168">To update who has permissions to manage topics:</span></span>

1. <span data-ttu-id="a3e05-169">На вкладке **разрешения раздела** в разделе **Пользователи, которые могут управлять разделами** нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="a3e05-169">On the **Topic permissions** tab, under **Who can manage topics** , select **Edit**.</span></span></br>
2. <span data-ttu-id="a3e05-170">На странице **пользователи могут управлять разделами** можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="a3e05-170">On the **Who can manage topics** page, you can select:</span></span></br>
    <span data-ttu-id="a3e05-171">а.</span><span class="sxs-lookup"><span data-stu-id="a3e05-171">a.</span></span> <span data-ttu-id="a3e05-172">**Все в организации**</span><span class="sxs-lookup"><span data-stu-id="a3e05-172">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="a3e05-173">б.</span><span class="sxs-lookup"><span data-stu-id="a3e05-173">b.</span></span> <span data-ttu-id="a3e05-174">**Выбранные пользователи или группы безопасности**</span><span class="sxs-lookup"><span data-stu-id="a3e05-174">**Selected people or security groups**</span></span></br>

    ![Управление разделами](../media/content-understanding/k-manage-who-can-manage-topics.png) </br> 

3. <span data-ttu-id="a3e05-176">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a3e05-176">Select **Save**.</span></span></br>


##  <a name="update-your-topic-center-name"></a><span data-ttu-id="a3e05-177">Обновление названия центра справки</span><span class="sxs-lookup"><span data-stu-id="a3e05-177">Update your topic center name</span></span>

<span data-ttu-id="a3e05-178">Перейдите на вкладку **центр разделов** , если хотите обновить название центра.</span><span class="sxs-lookup"><span data-stu-id="a3e05-178">Select the **Topic center** tab if you want to update the name of your topic center.</span></span> 

1. <span data-ttu-id="a3e05-179">На вкладке **центр разделов** в разделе **Название центра разделов** выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="a3e05-179">On the **Topic center** tab, under **Topic center name** , select **Edit**.</span></span>
2. <span data-ttu-id="a3e05-180">На странице **изменение имени раздела** введите в поле **Название центра разделов** новое имя для своего центра справки.</span><span class="sxs-lookup"><span data-stu-id="a3e05-180">On the **Edit topic center name** page, in the **Topic center name** box, type the new name for your topic center.</span></span>
3. <span data-ttu-id="a3e05-181">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a3e05-181">Select **Save**</span></span>

    ![Изменение названия центра разделов](../media/content-understanding/manage-topic-center-name.png) </br> 











## <a name="see-also"></a><span data-ttu-id="a3e05-183">См. также</span><span class="sxs-lookup"><span data-stu-id="a3e05-183">See also</span></span>



  






