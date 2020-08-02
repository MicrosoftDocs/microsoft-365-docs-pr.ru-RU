---
title: 'Настройка управления знаниями (Предварительная версия) '
description: Настройка управления знаниями.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: Normal
ms.openlocfilehash: d4bc45bd1c88d4043df661972399dc6740dbed84
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540134"
---
# <a name="set-up-knowledge-management-preview"></a><span data-ttu-id="22c9b-103">Настройка управления знаниями (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="22c9b-103">Set up Knowledge Management (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="22c9b-104">Содержимое этой статьи предназначено для Кортексного предварительного просмотра Project.</span><span class="sxs-lookup"><span data-stu-id="22c9b-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="22c9b-105">[Узнайте больше о Кортекс Project](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="22c9b-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="22c9b-106">Вы можете использовать центр администрирования Microsoft 365 для установки и настройки [управления знаниями](knowledge-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="22c9b-106">You can use the Microsoft 365 admin center to set up and configure [Knowledge Management](knowledge-management-overview.md).</span></span> 

> [!Important]
> <span data-ttu-id="22c9b-107">Важно спланировать лучший способ установки и настройки управления знаниями в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="22c9b-107">It is important to plan the best way to set up and configure Knowledge Management in your environment.</span></span> <span data-ttu-id="22c9b-108">Например, необходимо принять во внимание следующее:</span><span class="sxs-lookup"><span data-stu-id="22c9b-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="22c9b-109">Какие сайты SharePoint вы хотите проанализировать для разделов.</span><span class="sxs-lookup"><span data-stu-id="22c9b-109">Which SharePoint sites you want to analyze for topics.</span></span>
- <span data-ttu-id="22c9b-110">Сведения о пользователях, которым вы хотите сделать темы видимыми.</span><span class="sxs-lookup"><span data-stu-id="22c9b-110">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="22c9b-111">Пользователи, которым вы хотите предоставить разрешения на управление разделами в центре разделов.</span><span class="sxs-lookup"><span data-stu-id="22c9b-111">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="22c9b-112">Пользователи, которым вы хотите предоставить разрешения на создание или Редактирование разделов в центре разделов.</span><span class="sxs-lookup"><span data-stu-id="22c9b-112">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="22c9b-113">Имя, которое вы хотите присвоить вашему центру справки.</span><span class="sxs-lookup"><span data-stu-id="22c9b-113">What name you want to give your topic center.</span></span>

> [!Note]
> <span data-ttu-id="22c9b-114">Для назначения пользователям разрешений, необходимых для просмотра разделов, управления темой и создания и редактирования разделов, может потребоваться создать группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="22c9b-114">You may find it useful to create security groups to assign your users the permissions needed to view topics, manage topic, and create and edit topics.</span></span>

<span data-ttu-id="22c9b-115">Администратор также может [вносить изменения в выбранные параметры в любое время после установки](manage-knowledge-network.md) с помощью параметров управления знаниями в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="22c9b-115">An admin can also [make changes to your selected settings anytime after setup](manage-knowledge-network.md) through the Knowledge Management settings in the Microsoft 365 admin center.</span></span>

## <a name="requirements"></a><span data-ttu-id="22c9b-116">Требования</span><span class="sxs-lookup"><span data-stu-id="22c9b-116">Requirements</span></span> 
<span data-ttu-id="22c9b-117">Чтобы получить доступ к центру администрирования Microsoft 365 и настроить задачи организационной информации, необходимо иметь разрешения глобального администратора или администратора SharePoint.</span><span class="sxs-lookup"><span data-stu-id="22c9b-117">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up Organizational knowledge tasks.</span></span>

## <a name="set-up-your-knowledge-network"></a><span data-ttu-id="22c9b-118">Настройка сети знаний</span><span class="sxs-lookup"><span data-stu-id="22c9b-118">Set up your knowledge network</span></span>

<span data-ttu-id="22c9b-119">Настройка сети знаний поможет вам выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="22c9b-119">Setting up your knowledge network walks you through the following:</span></span>

- <span data-ttu-id="22c9b-120">Обнаружение разделов: выбор источников разделов и разделов, исключаемых из обнаружения.</span><span class="sxs-lookup"><span data-stu-id="22c9b-120">Topic discovery: Selecting topic sources and topics to  exclude from discovery.</span></span>
- <span data-ttu-id="22c9b-121">Видимость разделов: Выбор пользователей, которые могут просматривать темы в виде выделенных фрагментов, на страницах поиска и разделов.</span><span class="sxs-lookup"><span data-stu-id="22c9b-121">Topic visibility: Selecting who can view topics as highlights, in search and topic pages.</span></span>
- <span data-ttu-id="22c9b-122">Разрешения для разделов: Выбор пользователей, которые могут создавать, изменять и управлять разделами.</span><span class="sxs-lookup"><span data-stu-id="22c9b-122">Topic permissions: Selecting who can create, edit, and manage topics.</span></span>
- <span data-ttu-id="22c9b-123">В центре разделов: создание тематического центра.</span><span class="sxs-lookup"><span data-stu-id="22c9b-123">Topic center: Create your topic center.</span></span>
- <span data-ttu-id="22c9b-124">Проверка: Проверьте и примените свои параметры.</span><span class="sxs-lookup"><span data-stu-id="22c9b-124">Review: Check and apply your settings.</span></span>

<span data-ttu-id="22c9b-125">Чтобы настроить сеть знаний:</span><span class="sxs-lookup"><span data-stu-id="22c9b-125">To set up your knowledge network:</span></span>

1. <span data-ttu-id="22c9b-126">В центре администрирования Microsoft 365 (admin.microsoft.com) выберите пункт **Настройка**, а затем просмотрите раздел **сведения о организации** .</span><span class="sxs-lookup"><span data-stu-id="22c9b-126">In the Microsoft 365 admin center (admin.microsoft.com), select **Setup**, and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="22c9b-127">В разделе " **сведения о организации** " щелкните **подключить пользователей к набору знаний**.</span><span class="sxs-lookup"><span data-stu-id="22c9b-127">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![Подключение пользователей к базе знаний](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="22c9b-129">На странице **подключить людей к сведениям** нажмите кнопку Начало **работы** , чтобы проанализировать процесс установки.</span><span class="sxs-lookup"><span data-stu-id="22c9b-129">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![Начало работы](../media/content-understanding/k-get-started.png) </br>

4. <span data-ttu-id="22c9b-131">На странице **Выбор способа поиска тем в сети базы знаний** можно настроить обнаружение разделов.</span><span class="sxs-lookup"><span data-stu-id="22c9b-131">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="22c9b-132">В разделе **Выбор источников разделов SharePoint** выберите сайты SharePoint, которые будут обходиться в качестве источников для разделов во время обнаружения.</span><span class="sxs-lookup"><span data-stu-id="22c9b-132">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="22c9b-133">К ним относятся:</span><span class="sxs-lookup"><span data-stu-id="22c9b-133">This includes:</span></span></br>
    <span data-ttu-id="22c9b-134">а)</span><span class="sxs-lookup"><span data-stu-id="22c9b-134">a.</span></span> <span data-ttu-id="22c9b-135">**Все сайты**: все сайты SharePoint в клиенте.</span><span class="sxs-lookup"><span data-stu-id="22c9b-135">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="22c9b-136">Это записывает текущие и будущие сайты.</span><span class="sxs-lookup"><span data-stu-id="22c9b-136">This captures current and future sites.</span></span></br>
    <span data-ttu-id="22c9b-137">б)</span><span class="sxs-lookup"><span data-stu-id="22c9b-137">b.</span></span> <span data-ttu-id="22c9b-138">**Все, кроме выбранных сайтов**: введите имена сайтов, которые вы хотите исключить.</span><span class="sxs-lookup"><span data-stu-id="22c9b-138">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="22c9b-139">Вы также можете отправить список сайтов, которые вы хотите отказаться от обнаружения.</span><span class="sxs-lookup"><span data-stu-id="22c9b-139">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="22c9b-140">Сайты, созданные в будущем, будут включены в качестве источников для обнаружения разделов.</span><span class="sxs-lookup"><span data-stu-id="22c9b-140">Sites created in future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="22c9b-141">в.</span><span class="sxs-lookup"><span data-stu-id="22c9b-141">c.</span></span> <span data-ttu-id="22c9b-142">**Только выбранные сайты**: введите имена сайтов, которые необходимо включить в список.</span><span class="sxs-lookup"><span data-stu-id="22c9b-142">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="22c9b-143">Вы также можете отправить список сайтов.</span><span class="sxs-lookup"><span data-stu-id="22c9b-143">You can also upload a list of sites.</span></span> <span data-ttu-id="22c9b-144">Сайты, созданные в будущем, не будут включены в качестве источников для обнаружения разделов.</span><span class="sxs-lookup"><span data-stu-id="22c9b-144">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![Выбор способа поиска разделов](../media/content-understanding/ksetup1.png) </br>
   
5. <span data-ttu-id="22c9b-146">В разделе **исключить темы по имени** можно указать имена тем, которые не должны находиться в обнаруженных результатах.</span><span class="sxs-lookup"><span data-stu-id="22c9b-146">In the **Exclude topics by name** section, you can choose to includes names of topics you don't want to be in the discovered results.</span></span> <span data-ttu-id="22c9b-147">Используйте этот параметр, чтобы предотвратить включение конфиденциальных разделов в составе сети знаний.</span><span class="sxs-lookup"><span data-stu-id="22c9b-147">Use this setting to prevent sensitive topics from being included as part of the knowledge network.</span></span> <span data-ttu-id="22c9b-148">Возможные варианты:</span><span class="sxs-lookup"><span data-stu-id="22c9b-148">Your options include:</span></span></br>
    <span data-ttu-id="22c9b-149">а)</span><span class="sxs-lookup"><span data-stu-id="22c9b-149">a.</span></span> <span data-ttu-id="22c9b-150">**Не исключите темы**</span><span class="sxs-lookup"><span data-stu-id="22c9b-150">**Don't exclude any topics**</span></span> </br>
    <span data-ttu-id="22c9b-151">б)</span><span class="sxs-lookup"><span data-stu-id="22c9b-151">b.</span></span> <span data-ttu-id="22c9b-152">**Исключение раздела, содержащего эти термины**: если у вас есть темы, которые не нужно показывать пользователям как часть сети знаний.</span><span class="sxs-lookup"><span data-stu-id="22c9b-152">**Exclude topic that contain these terms**:  If you have topics you don’t want shown to users as part of the knowledge network.</span></span>
   <span data-ttu-id="22c9b-153">— Скачайте указанный шаблон.</span><span class="sxs-lookup"><span data-stu-id="22c9b-153">- Download the provided template.</span></span>
   <span data-ttu-id="22c9b-154">— Введите имена разделов, которые вы хотите исключить.</span><span class="sxs-lookup"><span data-stu-id="22c9b-154">- Enter the topic names you want to exclude.</span></span> <span data-ttu-id="22c9b-155">Необходимо указать точный или частичный тип совпадения.</span><span class="sxs-lookup"><span data-stu-id="22c9b-155">You must indicate the match type as exact or partial.</span></span> <span data-ttu-id="22c9b-156">Точное совпадение означает, что разделы, соответствующие точному термину, будут исключены.</span><span class="sxs-lookup"><span data-stu-id="22c9b-156">Exact match means that topics that fit the exact term will be excluded.</span></span> <span data-ttu-id="22c9b-157">Частичное сравнение является более четким и означает, что разделы, содержащие этот термин, будут исключены.</span><span class="sxs-lookup"><span data-stu-id="22c9b-157">Partial match is stricter and means that topics that contain the term will be excluded.</span></span> <span data-ttu-id="22c9b-158">Например, если ввести в качестве имени статьи имя *документа* , *Сборка doc* будет исключена, а *закрепление* не будет.</span><span class="sxs-lookup"><span data-stu-id="22c9b-158">For example, if you enter *Doc* as the topic name, *Doc assembly* will be excluded while *Docker* won't.</span></span> <span data-ttu-id="22c9b-159">В именах тем регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="22c9b-159">Topic names are case insensitive.</span></span>  
        <span data-ttu-id="22c9b-160">-Выберите  **+**   , чтобы импортировать завершенный CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="22c9b-160">- Select **+** to import your completed CSV file.</span></span> <span data-ttu-id="22c9b-161">Затем нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="22c9b-161">Then select **Upload**.</span></span> <span data-ttu-id="22c9b-162">Если файл был обработан успешно, появится зеленая галочка.</span><span class="sxs-lookup"><span data-stu-id="22c9b-162">You’ll see a green check mark if your file has been processed successfully.</span></span> <span data-ttu-id="22c9b-163">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="22c9b-163">Select **Next**.</span></span></br>


6. <span data-ttu-id="22c9b-164">Сведения о том, **кто может видеть темы и где они могут видеть их** , будут настраивать видимость разделов.</span><span class="sxs-lookup"><span data-stu-id="22c9b-164">On the **Who can see topics and where they can see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="22c9b-165">В разделе сведения о том, **кто может просматривать разделы в параметрах сети знаний** , вы можете выбрать, кто будет иметь доступ к сведениям о темах, таким как разделы, карточки, темы в поиске и страницы разделов.</span><span class="sxs-lookup"><span data-stu-id="22c9b-165">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="22c9b-166">Можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="22c9b-166">You can select:</span></span></br>
    <span data-ttu-id="22c9b-167">а)</span><span class="sxs-lookup"><span data-stu-id="22c9b-167">a.</span></span> <span data-ttu-id="22c9b-168">**Все в организации**</span><span class="sxs-lookup"><span data-stu-id="22c9b-168">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="22c9b-169">б)</span><span class="sxs-lookup"><span data-stu-id="22c9b-169">b.</span></span> <span data-ttu-id="22c9b-170">**Только выбранные пользователи или группы безопасности**</span><span class="sxs-lookup"><span data-stu-id="22c9b-170">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="22c9b-171">в.</span><span class="sxs-lookup"><span data-stu-id="22c9b-171">c.</span></span> <span data-ttu-id="22c9b-172">**Никто**</span><span class="sxs-lookup"><span data-stu-id="22c9b-172">**No one**</span></span></br>

    ![Кто может просматривать темы](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > <span data-ttu-id="22c9b-174">Несмотря на то, что этот параметр позволяет выбрать любого пользователя в Организации, будут доступны только те пользователи, которым назначены лицензии управления знаниями.</span><span class="sxs-lookup"><span data-stu-id="22c9b-174">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span> 

7. <span data-ttu-id="22c9b-175">На странице " **разрешения для управления** темами" вы можете выбрать, кто будет иметь возможность создавать, изменять и управлять разделами.</span><span class="sxs-lookup"><span data-stu-id="22c9b-175">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="22c9b-176">В разделе **пользователи могут создавать и изменять разделы** можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="22c9b-176">In the **Who can create and edit topics** section, you can select:</span></span></br>
    <span data-ttu-id="22c9b-177">а)</span><span class="sxs-lookup"><span data-stu-id="22c9b-177">a.</span></span> <span data-ttu-id="22c9b-178">**Все в организации**</span><span class="sxs-lookup"><span data-stu-id="22c9b-178">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="22c9b-179">б)</span><span class="sxs-lookup"><span data-stu-id="22c9b-179">b.</span></span> <span data-ttu-id="22c9b-180">**Только выбранные пользователи или группы безопасности**</span><span class="sxs-lookup"><span data-stu-id="22c9b-180">**Only selected people or security groups**</span></span></br>
8. <span data-ttu-id="22c9b-181">В разделе **кто может управлять** разделами можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="22c9b-181">In the **Who can manage topics** section, you can select:</span></span></br>
    <span data-ttu-id="22c9b-182">а)</span><span class="sxs-lookup"><span data-stu-id="22c9b-182">a.</span></span> <span data-ttu-id="22c9b-183">**Все в организации**</span><span class="sxs-lookup"><span data-stu-id="22c9b-183">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="22c9b-184">б)</span><span class="sxs-lookup"><span data-stu-id="22c9b-184">b.</span></span> <span data-ttu-id="22c9b-185">**Выбранные пользователи или группы безопасности**</span><span class="sxs-lookup"><span data-stu-id="22c9b-185">**Selected people or security groups**</span></span></br>

    ![Разрешения для управления разделами](../media/content-understanding/ksetup3.png) </br>

    <span data-ttu-id="22c9b-187">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="22c9b-187">Select **Next**.</span></span></br>
9. <span data-ttu-id="22c9b-188">На странице " **Создание центра разделов** " можно создать сайт центра разделов, в котором можно просматривать страницы разделов, а также управлять разделами.</span><span class="sxs-lookup"><span data-stu-id="22c9b-188">On the **Create Topic  Center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span>  <span data-ttu-id="22c9b-189">В поле **Название центра разделов** введите имя для своего центра справки.</span><span class="sxs-lookup"><span data-stu-id="22c9b-189">In the **Topic center name** box, type a name for your Topic center.</span></span> <span data-ttu-id="22c9b-190">При необходимости можно ввести краткое описание в поле **Описание сайта** .</span><span class="sxs-lookup"><span data-stu-id="22c9b-190">You can optionally type a short description in the **Site description** box.</span></span> </br>

<span data-ttu-id="22c9b-191">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="22c9b-191">Select **Next**.</span></span></br>

   ![Создание центра знаний](../media/content-understanding/ksetup4.png) </br> 

10. <span data-ttu-id="22c9b-193">На странице **"Проверка и завершение"** можно просмотреть выбранный параметр и внести изменения.</span><span class="sxs-lookup"><span data-stu-id="22c9b-193">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="22c9b-194">Если вы удовлетворены выбранными параметрами, нажмите кнопку **активировать**.</span><span class="sxs-lookup"><span data-stu-id="22c9b-194">If you are satisfied with your selections, select **Activate**.</span></span>

    ![Завершение и пересмотр](../media/content-understanding/ksetup5.png) </br> 

11. <span data-ttu-id="22c9b-196">Откроется страница **базы знаний "активированная сеть** ", в результате чего система начнет анализировать выбранные сайты для разделов и создания сайта центра знаний.</span><span class="sxs-lookup"><span data-stu-id="22c9b-196">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="22c9b-197">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="22c9b-197">Select **Done**.</span></span></br>

    ![Activated](../media/content-understanding/ksetup6.png) </br> 

12. <span data-ttu-id="22c9b-199">Вы вернетесь на страницу **Connect People to a Knowledge** .</span><span class="sxs-lookup"><span data-stu-id="22c9b-199">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="22c9b-200">На этой странице можно выбрать пункт **Управление** , чтобы внести изменения в параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="22c9b-200">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Примененные параметры](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> <span data-ttu-id="22c9b-202">После установки администратор может изменить [Выбранные параметры управления знаниями](manage-knowledge-network.md) в любое время, вернувшись на эту страницу.</span><span class="sxs-lookup"><span data-stu-id="22c9b-202">After setup, an admin can [make changes to your selected knowledge management settings](manage-knowledge-network.md) any time by returning to this page.</span></span>


## <a name="see-also"></a><span data-ttu-id="22c9b-203">См. также</span><span class="sxs-lookup"><span data-stu-id="22c9b-203">See also</span></span>



  






