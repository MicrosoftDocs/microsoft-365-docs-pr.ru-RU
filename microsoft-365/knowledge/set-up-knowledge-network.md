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
localization_priority: None
ms.openlocfilehash: ba8cb8ceb3c98019099bfe5438d274c9d2b32280
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612552"
---
# <a name="set-up-knowledge-management-preview"></a><span data-ttu-id="f5731-103">Настройка управления знаниями (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="f5731-103">Set up Knowledge Management (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="f5731-104">Содержимое этой статьи предназначено для Кортексного предварительного просмотра Project.</span><span class="sxs-lookup"><span data-stu-id="f5731-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="f5731-105">[Узнайте больше о Кортекс Project](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="f5731-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="f5731-106">Вы можете использовать центр администрирования Microsoft 365 для установки и настройки [управления знаниями](knowledge-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f5731-106">You can use the Microsoft 365 admin center to set up and configure [Knowledge Management](knowledge-management-overview.md).</span></span> 

> [!Important]
> <span data-ttu-id="f5731-107">Важно спланировать лучший способ установки и настройки управления знаниями в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="f5731-107">It is important to plan the best way to set up and configure Knowledge Management in your environment.</span></span> <span data-ttu-id="f5731-108">Например, необходимо принять во внимание следующее:</span><span class="sxs-lookup"><span data-stu-id="f5731-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="f5731-109">Какие сайты SharePoint вы хотите проанализировать для разделов.</span><span class="sxs-lookup"><span data-stu-id="f5731-109">Which SharePoint sites you want to analyze for topics.</span></span>
- <span data-ttu-id="f5731-110">Сведения о пользователях, которым вы хотите сделать темы видимыми.</span><span class="sxs-lookup"><span data-stu-id="f5731-110">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="f5731-111">Пользователи, которым вы хотите предоставить разрешения на управление разделами в центре разделов.</span><span class="sxs-lookup"><span data-stu-id="f5731-111">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="f5731-112">Пользователи, которым вы хотите предоставить разрешения на создание или Редактирование разделов в центре разделов.</span><span class="sxs-lookup"><span data-stu-id="f5731-112">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="f5731-113">Имя, которое вы хотите присвоить вашему центру справки.</span><span class="sxs-lookup"><span data-stu-id="f5731-113">What name you want to give your topic center.</span></span>

> [!Note]
> <span data-ttu-id="f5731-114">Для назначения пользователям разрешений, необходимых для просмотра разделов, управления темой и создания и редактирования разделов, может потребоваться создать группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="f5731-114">You may find it useful to create security groups to assign your users the permissions needed to view topics, manage topic, and create and edit topics.</span></span>

<span data-ttu-id="f5731-115">Администратор также может [вносить изменения в выбранные параметры в любое время после установки](manage-knowledge-network.md) с помощью параметров управления знаниями в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f5731-115">An admin can also [make changes to your selected settings anytime after setup](manage-knowledge-network.md) through the Knowledge Management settings in the Microsoft 365 admin center.</span></span>

## <a name="requirements"></a><span data-ttu-id="f5731-116">Требования</span><span class="sxs-lookup"><span data-stu-id="f5731-116">Requirements</span></span> 
<span data-ttu-id="f5731-117">Чтобы получить доступ к центру администрирования Microsoft 365 и настроить задачи организационной информации, необходимо иметь разрешения глобального администратора или администратора SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f5731-117">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up Organizational knowledge tasks.</span></span>

## <a name="set-up-your-knowledge-network"></a><span data-ttu-id="f5731-118">Настройка сети знаний</span><span class="sxs-lookup"><span data-stu-id="f5731-118">Set up your knowledge network</span></span>

<span data-ttu-id="f5731-119">Настройка сети знаний поможет вам выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f5731-119">Setting up your knowledge network walks you through the following:</span></span>

- <span data-ttu-id="f5731-120">Обнаружение разделов: выбор источников разделов и разделов, исключаемых из обнаружения.</span><span class="sxs-lookup"><span data-stu-id="f5731-120">Topic discovery: Selecting topic sources and topics to  exclude from discovery.</span></span>
- <span data-ttu-id="f5731-121">Видимость разделов: Выбор пользователей, которые могут просматривать темы в виде выделенных фрагментов, на страницах поиска и разделов.</span><span class="sxs-lookup"><span data-stu-id="f5731-121">Topic visibility: Selecting who can view topics as highlights, in search and topic pages.</span></span>
- <span data-ttu-id="f5731-122">Разрешения для разделов: Выбор пользователей, которые могут создавать, изменять и управлять разделами.</span><span class="sxs-lookup"><span data-stu-id="f5731-122">Topic permissions: Selecting who can create, edit, and manage topics.</span></span>
- <span data-ttu-id="f5731-123">В центре разделов: создание тематического центра.</span><span class="sxs-lookup"><span data-stu-id="f5731-123">Topic center: Create your topic center.</span></span>
- <span data-ttu-id="f5731-124">Проверка: Проверьте и примените свои параметры.</span><span class="sxs-lookup"><span data-stu-id="f5731-124">Review: Check and apply your settings.</span></span>

<span data-ttu-id="f5731-125">Чтобы настроить сеть знаний:</span><span class="sxs-lookup"><span data-stu-id="f5731-125">To set up your knowledge network:</span></span>

1. <span data-ttu-id="f5731-126">В центре администрирования Microsoft 365 (admin.microsoft.com) выберите пункт **Настройка**, а затем просмотрите раздел **сведения о организации** .</span><span class="sxs-lookup"><span data-stu-id="f5731-126">In the Microsoft 365 admin center (admin.microsoft.com), select **Setup**, and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="f5731-127">В разделе " **сведения о организации** " щелкните **подключить пользователей к набору знаний**.</span><span class="sxs-lookup"><span data-stu-id="f5731-127">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![Подключение пользователей к базе знаний](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="f5731-129">На странице **подключить людей к сведениям** нажмите кнопку Начало **работы** , чтобы проанализировать процесс установки.</span><span class="sxs-lookup"><span data-stu-id="f5731-129">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![Начало работы](../media/content-understanding/k-get-started.png) </br>

4. <span data-ttu-id="f5731-131">На странице **Выбор способа поиска тем в сети базы знаний** можно настроить обнаружение разделов.</span><span class="sxs-lookup"><span data-stu-id="f5731-131">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="f5731-132">В разделе **Выбор источников разделов SharePoint** выберите сайты SharePoint, которые будут обходиться в качестве источников для разделов во время обнаружения.</span><span class="sxs-lookup"><span data-stu-id="f5731-132">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="f5731-133">К ним относятся:</span><span class="sxs-lookup"><span data-stu-id="f5731-133">This includes:</span></span></br>
    <span data-ttu-id="f5731-134">а.</span><span class="sxs-lookup"><span data-stu-id="f5731-134">a.</span></span> <span data-ttu-id="f5731-135">**Все сайты**: все сайты SharePoint в клиенте.</span><span class="sxs-lookup"><span data-stu-id="f5731-135">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="f5731-136">Это записывает текущие и будущие сайты.</span><span class="sxs-lookup"><span data-stu-id="f5731-136">This captures current and future sites.</span></span></br>
    <span data-ttu-id="f5731-137">б.</span><span class="sxs-lookup"><span data-stu-id="f5731-137">b.</span></span> <span data-ttu-id="f5731-138">**Все, кроме выбранных сайтов**: введите имена сайтов, которые вы хотите исключить.</span><span class="sxs-lookup"><span data-stu-id="f5731-138">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="f5731-139">Вы также можете отправить список сайтов, которые вы хотите отказаться от обнаружения.</span><span class="sxs-lookup"><span data-stu-id="f5731-139">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="f5731-140">Сайты, созданные в будущем, будут включены в качестве источников для обнаружения разделов.</span><span class="sxs-lookup"><span data-stu-id="f5731-140">Sites created in future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="f5731-141">в.</span><span class="sxs-lookup"><span data-stu-id="f5731-141">c.</span></span> <span data-ttu-id="f5731-142">**Только выбранные сайты**: введите имена сайтов, которые необходимо включить в список.</span><span class="sxs-lookup"><span data-stu-id="f5731-142">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="f5731-143">Вы также можете отправить список сайтов.</span><span class="sxs-lookup"><span data-stu-id="f5731-143">You can also upload a list of sites.</span></span> <span data-ttu-id="f5731-144">Сайты, созданные в будущем, не будут включены в качестве источников для обнаружения разделов.</span><span class="sxs-lookup"><span data-stu-id="f5731-144">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![Выбор способа поиска разделов](../media/content-understanding/ksetup1.png) </br>
   
5. <span data-ttu-id="f5731-146">В разделе **исключить темы по имени** можно указать имена тем, которые не должны находиться в обнаруженных результатах.</span><span class="sxs-lookup"><span data-stu-id="f5731-146">In the **Exclude topics by name** section, you can choose to includes names of topics you don't want to be in the discovered results.</span></span> <span data-ttu-id="f5731-147">Используйте этот параметр, чтобы предотвратить включение конфиденциальных разделов в составе сети знаний.</span><span class="sxs-lookup"><span data-stu-id="f5731-147">Use this setting to prevent sensitive topics from being included as part of the knowledge network.</span></span> <span data-ttu-id="f5731-148">Возможные варианты:</span><span class="sxs-lookup"><span data-stu-id="f5731-148">Your options include:</span></span></br>
    <span data-ttu-id="f5731-149">а.</span><span class="sxs-lookup"><span data-stu-id="f5731-149">a.</span></span> <span data-ttu-id="f5731-150">**Не исключите темы**</span><span class="sxs-lookup"><span data-stu-id="f5731-150">**Don't exclude any topics**</span></span> </br>
    <span data-ttu-id="f5731-151">б.</span><span class="sxs-lookup"><span data-stu-id="f5731-151">b.</span></span> <span data-ttu-id="f5731-152">**Исключение раздела, содержащего эти термины**: если у вас есть темы, которые не нужно показывать пользователям как часть сети знаний.</span><span class="sxs-lookup"><span data-stu-id="f5731-152">**Exclude topic that contain these terms**:  If you have topics you don’t want shown to users as part of the knowledge network.</span></span>
   <span data-ttu-id="f5731-153">— Скачайте указанный шаблон.</span><span class="sxs-lookup"><span data-stu-id="f5731-153">- Download the provided template.</span></span>
   <span data-ttu-id="f5731-154">— Введите имена разделов, которые вы хотите исключить.</span><span class="sxs-lookup"><span data-stu-id="f5731-154">- Enter the topic names you want to exclude.</span></span> <span data-ttu-id="f5731-155">Необходимо указать точный или частичный тип совпадения.</span><span class="sxs-lookup"><span data-stu-id="f5731-155">You must indicate the match type as exact or partial.</span></span> <span data-ttu-id="f5731-156">Точное совпадение означает, что разделы, соответствующие точному термину, будут исключены.</span><span class="sxs-lookup"><span data-stu-id="f5731-156">Exact match means that topics that fit the exact term will be excluded.</span></span> <span data-ttu-id="f5731-157">Частичное сравнение является более четким и означает, что разделы, содержащие этот термин, будут исключены.</span><span class="sxs-lookup"><span data-stu-id="f5731-157">Partial match is stricter and means that topics that contain the term will be excluded.</span></span> <span data-ttu-id="f5731-158">Например, если ввести в качестве имени статьи имя *документа* , *Сборка doc* будет исключена, а *закрепление* не будет.</span><span class="sxs-lookup"><span data-stu-id="f5731-158">For example, if you enter *Doc* as the topic name, *Doc assembly* will be excluded while *Docker* won't.</span></span> <span data-ttu-id="f5731-159">В именах тем регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="f5731-159">Topic names are case insensitive.</span></span>  
        <span data-ttu-id="f5731-160">-Выберите  **+**   , чтобы импортировать завершенный CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="f5731-160">- Select **+** to import your completed CSV file.</span></span> <span data-ttu-id="f5731-161">Затем нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="f5731-161">Then select **Upload**.</span></span> <span data-ttu-id="f5731-162">Если файл был обработан успешно, появится зеленая галочка.</span><span class="sxs-lookup"><span data-stu-id="f5731-162">You’ll see a green check mark if your file has been processed successfully.</span></span> <span data-ttu-id="f5731-163">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f5731-163">Select **Next**.</span></span></br>


6. <span data-ttu-id="f5731-164">Сведения о том, **кто может видеть темы и где они могут видеть их** , будут настраивать видимость разделов.</span><span class="sxs-lookup"><span data-stu-id="f5731-164">On the **Who can see topics and where they can see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="f5731-165">В разделе сведения о том, **кто может просматривать разделы в параметрах сети знаний** , вы можете выбрать, кто будет иметь доступ к сведениям о темах, таким как разделы, карточки, темы в поиске и страницы разделов.</span><span class="sxs-lookup"><span data-stu-id="f5731-165">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="f5731-166">Можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="f5731-166">You can select:</span></span></br>
    <span data-ttu-id="f5731-167">а.</span><span class="sxs-lookup"><span data-stu-id="f5731-167">a.</span></span> <span data-ttu-id="f5731-168">**Все в организации**</span><span class="sxs-lookup"><span data-stu-id="f5731-168">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="f5731-169">б.</span><span class="sxs-lookup"><span data-stu-id="f5731-169">b.</span></span> <span data-ttu-id="f5731-170">**Только выбранные пользователи или группы безопасности**</span><span class="sxs-lookup"><span data-stu-id="f5731-170">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="f5731-171">в.</span><span class="sxs-lookup"><span data-stu-id="f5731-171">c.</span></span> <span data-ttu-id="f5731-172">**Никто**</span><span class="sxs-lookup"><span data-stu-id="f5731-172">**No one**</span></span></br>

    ![Кто может просматривать темы](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > <span data-ttu-id="f5731-174">Несмотря на то, что этот параметр позволяет выбрать любого пользователя в Организации, будут доступны только те пользователи, которым назначены лицензии управления знаниями.</span><span class="sxs-lookup"><span data-stu-id="f5731-174">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span> 

7. <span data-ttu-id="f5731-175">На странице " **разрешения для управления** темами" вы можете выбрать, кто будет иметь возможность создавать, изменять и управлять разделами.</span><span class="sxs-lookup"><span data-stu-id="f5731-175">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="f5731-176">В разделе **пользователи могут создавать и изменять разделы** можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="f5731-176">In the **Who can create and edit topics** section, you can select:</span></span></br>
    <span data-ttu-id="f5731-177">а.</span><span class="sxs-lookup"><span data-stu-id="f5731-177">a.</span></span> <span data-ttu-id="f5731-178">**Все в организации**</span><span class="sxs-lookup"><span data-stu-id="f5731-178">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="f5731-179">б.</span><span class="sxs-lookup"><span data-stu-id="f5731-179">b.</span></span> <span data-ttu-id="f5731-180">**Только выбранные пользователи или группы безопасности**</span><span class="sxs-lookup"><span data-stu-id="f5731-180">**Only selected people or security groups**</span></span></br>
8. <span data-ttu-id="f5731-181">В разделе **кто может управлять** разделами можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="f5731-181">In the **Who can manage topics** section, you can select:</span></span></br>
    <span data-ttu-id="f5731-182">а.</span><span class="sxs-lookup"><span data-stu-id="f5731-182">a.</span></span> <span data-ttu-id="f5731-183">**Все в организации**</span><span class="sxs-lookup"><span data-stu-id="f5731-183">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="f5731-184">б.</span><span class="sxs-lookup"><span data-stu-id="f5731-184">b.</span></span> <span data-ttu-id="f5731-185">**Выбранные пользователи или группы безопасности**</span><span class="sxs-lookup"><span data-stu-id="f5731-185">**Selected people or security groups**</span></span></br>

    ![Разрешения для управления разделами](../media/content-understanding/ksetup3.png) </br>

    <span data-ttu-id="f5731-187">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f5731-187">Select **Next**.</span></span></br>
9. <span data-ttu-id="f5731-188">На странице " **Создание центра разделов** " можно создать сайт центра разделов, в котором можно просматривать страницы разделов, а также управлять разделами.</span><span class="sxs-lookup"><span data-stu-id="f5731-188">On the **Create Topic  Center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span>  <span data-ttu-id="f5731-189">В поле **Название центра разделов** введите имя для своего центра справки.</span><span class="sxs-lookup"><span data-stu-id="f5731-189">In the **Topic center name** box, type a name for your Topic center.</span></span> <span data-ttu-id="f5731-190">При необходимости можно ввести краткое описание в поле **Описание сайта** .</span><span class="sxs-lookup"><span data-stu-id="f5731-190">You can optionally type a short description in the **Site description** box.</span></span> </br>

<span data-ttu-id="f5731-191">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f5731-191">Select **Next**.</span></span></br>

   ![Создание центра знаний](../media/content-understanding/ksetup4.png) </br> 

10. <span data-ttu-id="f5731-193">На странице **"Проверка и завершение"** можно просмотреть выбранный параметр и внести изменения.</span><span class="sxs-lookup"><span data-stu-id="f5731-193">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="f5731-194">Если вы удовлетворены выбранными параметрами, нажмите кнопку **активировать**.</span><span class="sxs-lookup"><span data-stu-id="f5731-194">If you are satisfied with your selections, select **Activate**.</span></span>

    ![Завершение и пересмотр](../media/content-understanding/ksetup5.png) </br> 

11. <span data-ttu-id="f5731-196">Откроется страница **базы знаний "активированная сеть** ", в результате чего система начнет анализировать выбранные сайты для разделов и создания сайта центра знаний.</span><span class="sxs-lookup"><span data-stu-id="f5731-196">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="f5731-197">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="f5731-197">Select **Done**.</span></span></br>

    ![Activated](../media/content-understanding/ksetup6.png) </br> 

12. <span data-ttu-id="f5731-199">Вы вернетесь на страницу **Connect People to a Knowledge** .</span><span class="sxs-lookup"><span data-stu-id="f5731-199">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="f5731-200">На этой странице можно выбрать пункт **Управление** , чтобы внести изменения в параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f5731-200">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Примененные параметры](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> <span data-ttu-id="f5731-202">После установки администратор может изменить [Выбранные параметры управления знаниями](manage-knowledge-network.md) в любое время, вернувшись на эту страницу.</span><span class="sxs-lookup"><span data-stu-id="f5731-202">After setup, an admin can [make changes to your selected knowledge management settings](manage-knowledge-network.md) any time by returning to this page.</span></span>


## <a name="see-also"></a><span data-ttu-id="f5731-203">См. также</span><span class="sxs-lookup"><span data-stu-id="f5731-203">See also</span></span>



  






