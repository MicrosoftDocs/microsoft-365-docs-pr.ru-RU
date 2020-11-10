---
title: 'Настройка управления знаниями (Предварительная версия) '
description: Настройка управления знаниями.
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: c7c30c0f8c1ec4cf8836547e2a23e1e2e6f4f783
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "48989003"
---
# <a name="set-up-knowledge-management-preview"></a><span data-ttu-id="d3943-103">Настройка управления знаниями (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="d3943-103">Set up Knowledge Management (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="d3943-104">Содержимое этой статьи предназначено для Кортексного предварительного просмотра Project.</span><span class="sxs-lookup"><span data-stu-id="d3943-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="d3943-105">[Узнайте больше о работе с Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="d3943-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="d3943-106">Вы можете использовать центр администрирования Microsoft 365 для установки и настройки [управления знаниями](knowledge-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d3943-106">You can use the Microsoft 365 admin center to set up and configure [Knowledge Management](knowledge-management-overview.md).</span></span> 

> [!Important]
> <span data-ttu-id="d3943-107">Важно спланировать лучший способ установки и настройки управления знаниями в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="d3943-107">It is important to plan the best way to set up and configure Knowledge Management in your environment.</span></span> <span data-ttu-id="d3943-108">Например, необходимо принять во внимание следующее:</span><span class="sxs-lookup"><span data-stu-id="d3943-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="d3943-109">Какие сайты SharePoint вы хотите проанализировать для разделов.</span><span class="sxs-lookup"><span data-stu-id="d3943-109">Which SharePoint sites you want to analyze for topics.</span></span>
- <span data-ttu-id="d3943-110">Сведения о пользователях, которым вы хотите сделать темы видимыми.</span><span class="sxs-lookup"><span data-stu-id="d3943-110">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="d3943-111">Пользователи, которым вы хотите предоставить разрешения на управление разделами в центре разделов.</span><span class="sxs-lookup"><span data-stu-id="d3943-111">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="d3943-112">Пользователи, которым вы хотите предоставить разрешения на создание или Редактирование разделов в центре разделов.</span><span class="sxs-lookup"><span data-stu-id="d3943-112">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="d3943-113">Имя, которое вы хотите присвоить вашему центру справки.</span><span class="sxs-lookup"><span data-stu-id="d3943-113">What name you want to give your topic center.</span></span>

> [!Note]
> <span data-ttu-id="d3943-114">Для назначения пользователям разрешений, необходимых для просмотра разделов, управления темой и создания и редактирования разделов, может потребоваться создать группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="d3943-114">You may find it useful to create security groups to assign your users the permissions needed to view topics, manage topic, and create and edit topics.</span></span>

<span data-ttu-id="d3943-115">Администратор также может [вносить изменения в выбранные параметры в любое время после установки](topic-experiences-discovery.md) с помощью параметров управления знаниями в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d3943-115">An admin can also [make changes to your selected settings anytime after setup](topic-experiences-discovery.md) through the Knowledge Management settings in the Microsoft 365 admin center.</span></span>

## <a name="requirements"></a><span data-ttu-id="d3943-116">Requirements</span><span class="sxs-lookup"><span data-stu-id="d3943-116">Requirements</span></span> 
<span data-ttu-id="d3943-117">Чтобы получить доступ к центру администрирования Microsoft 365 и настроить задачи организационной информации, необходимо иметь разрешения глобального администратора или администратора SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d3943-117">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up Organizational knowledge tasks.</span></span>

## <a name="set-up-your-knowledge-network"></a><span data-ttu-id="d3943-118">Настройка сети знаний</span><span class="sxs-lookup"><span data-stu-id="d3943-118">Set up your knowledge network</span></span>

<span data-ttu-id="d3943-119">Настройка сети знаний поможет вам выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d3943-119">Setting up your knowledge network walks you through the following:</span></span>

- <span data-ttu-id="d3943-120">Обнаружение разделов: выбор источников разделов и разделов, исключаемых из обнаружения.</span><span class="sxs-lookup"><span data-stu-id="d3943-120">Topic discovery: Selecting topic sources and topics to  exclude from discovery.</span></span>
- <span data-ttu-id="d3943-121">Видимость разделов: Выбор пользователей, которые могут просматривать темы в виде выделенных фрагментов, на страницах поиска и разделов.</span><span class="sxs-lookup"><span data-stu-id="d3943-121">Topic visibility: Selecting who can view topics as highlights, in search and topic pages.</span></span>
- <span data-ttu-id="d3943-122">Разрешения для разделов: Выбор пользователей, которые могут создавать, изменять и управлять разделами.</span><span class="sxs-lookup"><span data-stu-id="d3943-122">Topic permissions: Selecting who can create, edit, and manage topics.</span></span>
- <span data-ttu-id="d3943-123">В центре разделов: создание тематического центра.</span><span class="sxs-lookup"><span data-stu-id="d3943-123">Topic center: Create your topic center.</span></span>
- <span data-ttu-id="d3943-124">Проверка: Проверьте и примените свои параметры.</span><span class="sxs-lookup"><span data-stu-id="d3943-124">Review: Check and apply your settings.</span></span>

<span data-ttu-id="d3943-125">Чтобы настроить сеть знаний:</span><span class="sxs-lookup"><span data-stu-id="d3943-125">To set up your knowledge network:</span></span>

1. <span data-ttu-id="d3943-126">В центре администрирования Microsoft 365 (admin.microsoft.com) выберите пункт **Настройка** , а затем просмотрите раздел **сведения о организации** .</span><span class="sxs-lookup"><span data-stu-id="d3943-126">In the Microsoft 365 admin center (admin.microsoft.com), select **Setup** , and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="d3943-127">В разделе " **сведения о организации** " щелкните **подключить пользователей к набору знаний**.</span><span class="sxs-lookup"><span data-stu-id="d3943-127">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![Подключение пользователей к базе знаний](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="d3943-129">На странице **подключить людей к сведениям** нажмите кнопку Начало **работы** , чтобы проанализировать процесс установки.</span><span class="sxs-lookup"><span data-stu-id="d3943-129">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![Начало работы](../media/content-understanding/k-get-started.png) </br>

4. <span data-ttu-id="d3943-131">На странице **Выбор способа поиска тем в сети базы знаний** можно настроить обнаружение разделов.</span><span class="sxs-lookup"><span data-stu-id="d3943-131">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="d3943-132">В разделе **Выбор источников разделов SharePoint** выберите сайты SharePoint, которые будут обходиться в качестве источников для разделов во время обнаружения.</span><span class="sxs-lookup"><span data-stu-id="d3943-132">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="d3943-133">К ним относятся:</span><span class="sxs-lookup"><span data-stu-id="d3943-133">This includes:</span></span></br>
    <span data-ttu-id="d3943-134">а.</span><span class="sxs-lookup"><span data-stu-id="d3943-134">a.</span></span> <span data-ttu-id="d3943-135">**Все сайты** : все сайты SharePoint в клиенте.</span><span class="sxs-lookup"><span data-stu-id="d3943-135">**All sites** : All SharePoint sites in your tenant.</span></span> <span data-ttu-id="d3943-136">Это записывает текущие и будущие сайты.</span><span class="sxs-lookup"><span data-stu-id="d3943-136">This captures current and future sites.</span></span></br>
    <span data-ttu-id="d3943-137">б.</span><span class="sxs-lookup"><span data-stu-id="d3943-137">b.</span></span> <span data-ttu-id="d3943-138">**Все, кроме выбранных сайтов** : введите имена сайтов, которые вы хотите исключить.</span><span class="sxs-lookup"><span data-stu-id="d3943-138">**All, except selected sites** : Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="d3943-139">Вы также можете отправить список сайтов, которые вы хотите отказаться от обнаружения.</span><span class="sxs-lookup"><span data-stu-id="d3943-139">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="d3943-140">Сайты, созданные в будущем, будут включены в качестве источников для обнаружения разделов.</span><span class="sxs-lookup"><span data-stu-id="d3943-140">Sites created in future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="d3943-141">в.</span><span class="sxs-lookup"><span data-stu-id="d3943-141">c.</span></span> <span data-ttu-id="d3943-142">**Только выбранные сайты** : введите имена сайтов, которые необходимо включить в список.</span><span class="sxs-lookup"><span data-stu-id="d3943-142">**Only selected sites** : Type the names of the sites you want to include.</span></span> <span data-ttu-id="d3943-143">Вы также можете отправить список сайтов.</span><span class="sxs-lookup"><span data-stu-id="d3943-143">You can also upload a list of sites.</span></span> <span data-ttu-id="d3943-144">Сайты, созданные в будущем, не будут включены в качестве источников для обнаружения разделов.</span><span class="sxs-lookup"><span data-stu-id="d3943-144">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![Выбор способа поиска разделов](../media/content-understanding/ksetup1.png) </br>
   
5. <span data-ttu-id="d3943-146">В разделе **исключить темы по имени** можно указать имена тем, которые не должны находиться в обнаруженных результатах.</span><span class="sxs-lookup"><span data-stu-id="d3943-146">In the **Exclude topics by name** section, you can choose to includes names of topics you don't want to be in the discovered results.</span></span> <span data-ttu-id="d3943-147">Используйте этот параметр, чтобы предотвратить включение конфиденциальных разделов в составе сети знаний.</span><span class="sxs-lookup"><span data-stu-id="d3943-147">Use this setting to prevent sensitive topics from being included as part of the knowledge network.</span></span> <span data-ttu-id="d3943-148">Возможные варианты:</span><span class="sxs-lookup"><span data-stu-id="d3943-148">Your options include:</span></span></br>
    <span data-ttu-id="d3943-149">а.</span><span class="sxs-lookup"><span data-stu-id="d3943-149">a.</span></span> <span data-ttu-id="d3943-150">**Не исключите темы**</span><span class="sxs-lookup"><span data-stu-id="d3943-150">**Don't exclude any topics**</span></span> </br>
    <span data-ttu-id="d3943-151">б.</span><span class="sxs-lookup"><span data-stu-id="d3943-151">b.</span></span> <span data-ttu-id="d3943-152">**Исключите темы по имени** : если у вас есть темы, которые не нужно показывать пользователям как часть сети знаний.</span><span class="sxs-lookup"><span data-stu-id="d3943-152">**Exclude topics by name** :  If you have topics you don’t want shown to users as part of the knowledge network.</span></span></br>

    ![Исключение тем](../media/content-understanding/topics-excluded-by-name.png) </br>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="d3943-154">Как исключить темы по имени</span><span class="sxs-lookup"><span data-stu-id="d3943-154">How to exclude topics by name</span></span>    

    <span data-ttu-id="d3943-155">Если необходимо исключить темы, после выбора **исключения разделов по имени** выберите **скачать шаблон. csv**.</span><span class="sxs-lookup"><span data-stu-id="d3943-155">If you need to exclude topics, after selecting **Exclude topics by name** , select **Download the .csv template**.</span></span> <span data-ttu-id="d3943-156">Используйте Excel. CSV-шаблон, чтобы включить список тем, которые необходимо исключить из результатов обнаружения.</span><span class="sxs-lookup"><span data-stu-id="d3943-156">Use the Excel .CSV template to include a list of topics that you want to exclude from your discovery results.</span></span>

    ![Исключение разделов в шаблоне CSV](../media/content-understanding/csv1.png) </br>

    <span data-ttu-id="d3943-158">В шаблоне CSV введите следующие сведения о подразделах, которые вы хотите исключить:</span><span class="sxs-lookup"><span data-stu-id="d3943-158">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="d3943-159">**Name** : введите имя раздела, который требуется исключить.</span><span class="sxs-lookup"><span data-stu-id="d3943-159">**Name** : Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="d3943-160">Это можно сделать двумя способами:</span><span class="sxs-lookup"><span data-stu-id="d3943-160">There are two ways to do this:</span></span></br>
        - <span data-ttu-id="d3943-161">Точное совпадение: вы можете включить точное имя или аббревиатуру (например, *contoso* или *ATL* ).</span><span class="sxs-lookup"><span data-stu-id="d3943-161">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL* ).</span></span></br>
        - <span data-ttu-id="d3943-162">Частичное сравнение: вы можете исключить все темы, содержащие определенное слово.</span><span class="sxs-lookup"><span data-stu-id="d3943-162">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="d3943-163">Например, *Arc* будет исключать все темы со сведениями в его *дуге* , такими как *дуги окружности* , *плазменная дуга Велдинг* или *учебная дуга*. Обратите внимание, что он не будет исключать темы, в которых текст включается в составе слова, например для *архитектуры*.</span><span class="sxs-lookup"><span data-stu-id="d3943-163">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle* , *Plasma arc welding* , or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span></br>
    - <span data-ttu-id="d3943-164">**Расширение (необязательно)** : Если вы хотите исключить акроним, введите слова аббревиатуры.</span><span class="sxs-lookup"><span data-stu-id="d3943-164">**Expansion (optional)** : If you want to exclude an acronym, type the words the acronym stands for.</span></span></br>
    - <span data-ttu-id="d3943-165">**MatchType — СОВПАД/partial** : введите, является ли введенное имя *точным* или *частичным* .</span><span class="sxs-lookup"><span data-stu-id="d3943-165">**MatchType-Exact/Partial** : Type whether the name you entered was an *exact* or *partial* match type.</span></span></br>

    <span data-ttu-id="d3943-166">Завершив и сохраните CSV-файл шаблона, нажмите кнопку **Обзор** , чтобы найти и выбрать его.</span><span class="sxs-lookup"><span data-stu-id="d3943-166">After you've completed and saved your CSV template file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="d3943-167">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d3943-167">Select **Next**.</span></span></br>

6. <span data-ttu-id="d3943-168">Сведения о том, **кто может видеть темы и где они могут видеть их** , будут настраивать видимость разделов.</span><span class="sxs-lookup"><span data-stu-id="d3943-168">On the **Who can see topics and where they can see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="d3943-169">В разделе сведения о том, **кто может просматривать разделы в параметрах сети знаний** , вы можете выбрать, кто будет иметь доступ к сведениям о темах, таким как разделы, карточки, темы в поиске и страницы разделов.</span><span class="sxs-lookup"><span data-stu-id="d3943-169">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="d3943-170">Можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="d3943-170">You can select:</span></span></br>
    <span data-ttu-id="d3943-171">а.</span><span class="sxs-lookup"><span data-stu-id="d3943-171">a.</span></span> <span data-ttu-id="d3943-172">**Все в организации**</span><span class="sxs-lookup"><span data-stu-id="d3943-172">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="d3943-173">б.</span><span class="sxs-lookup"><span data-stu-id="d3943-173">b.</span></span> <span data-ttu-id="d3943-174">**Только выбранные пользователи или группы безопасности**</span><span class="sxs-lookup"><span data-stu-id="d3943-174">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="d3943-175">в.</span><span class="sxs-lookup"><span data-stu-id="d3943-175">c.</span></span> <span data-ttu-id="d3943-176">**Никто**</span><span class="sxs-lookup"><span data-stu-id="d3943-176">**No one**</span></span></br>

    ![Кто может просматривать темы](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > <span data-ttu-id="d3943-178">Несмотря на то, что этот параметр позволяет выбрать любого пользователя в Организации, будут доступны только те пользователи, которым назначены лицензии управления знаниями.</span><span class="sxs-lookup"><span data-stu-id="d3943-178">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span> 

7. <span data-ttu-id="d3943-179">На странице " **разрешения для управления** темами" вы можете выбрать, кто будет иметь возможность создавать, изменять и управлять разделами.</span><span class="sxs-lookup"><span data-stu-id="d3943-179">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="d3943-180">В разделе **пользователи могут создавать и изменять разделы** можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="d3943-180">In the **Who can create and edit topics** section, you can select:</span></span></br>
    <span data-ttu-id="d3943-181">а.</span><span class="sxs-lookup"><span data-stu-id="d3943-181">a.</span></span> <span data-ttu-id="d3943-182">**Все в организации**</span><span class="sxs-lookup"><span data-stu-id="d3943-182">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="d3943-183">б.</span><span class="sxs-lookup"><span data-stu-id="d3943-183">b.</span></span> <span data-ttu-id="d3943-184">**Только выбранные пользователи или группы безопасности**</span><span class="sxs-lookup"><span data-stu-id="d3943-184">**Only selected people or security groups**</span></span></br>
8. <span data-ttu-id="d3943-185">В разделе **кто может управлять** разделами можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="d3943-185">In the **Who can manage topics** section, you can select:</span></span></br>
    <span data-ttu-id="d3943-186">а.</span><span class="sxs-lookup"><span data-stu-id="d3943-186">a.</span></span> <span data-ttu-id="d3943-187">**Все в организации**</span><span class="sxs-lookup"><span data-stu-id="d3943-187">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="d3943-188">б.</span><span class="sxs-lookup"><span data-stu-id="d3943-188">b.</span></span> <span data-ttu-id="d3943-189">**Выбранные пользователи или группы безопасности**</span><span class="sxs-lookup"><span data-stu-id="d3943-189">**Selected people or security groups**</span></span></br>

    ![Разрешения для управления разделами](../media/content-understanding/ksetup3.png) </br>

    <span data-ttu-id="d3943-191">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d3943-191">Select **Next**.</span></span></br>
9. <span data-ttu-id="d3943-192">На странице " **Создание центра разделов** " можно создать сайт центра разделов, в котором можно просматривать страницы разделов, а также управлять разделами.</span><span class="sxs-lookup"><span data-stu-id="d3943-192">On the **Create Topic  Center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span>  <span data-ttu-id="d3943-193">В поле **Название центра разделов** введите имя для своего центра справки.</span><span class="sxs-lookup"><span data-stu-id="d3943-193">In the **Topic center name** box, type a name for your Topic center.</span></span> <span data-ttu-id="d3943-194">При необходимости можно ввести краткое описание в поле **Описание сайта** .</span><span class="sxs-lookup"><span data-stu-id="d3943-194">You can optionally type a short description in the **Site description** box.</span></span> </br>

<span data-ttu-id="d3943-195">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d3943-195">Select **Next**.</span></span></br>

   ![Создание центра знаний](../media/content-understanding/ksetup4.png) </br> 

10. <span data-ttu-id="d3943-197">На странице **Проверка и завершение** можно просмотреть выбранный параметр и внести в него изменения.</span><span class="sxs-lookup"><span data-stu-id="d3943-197">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="d3943-198">Если выбор вас устраивает, нажмите кнопку **Активировать**.</span><span class="sxs-lookup"><span data-stu-id="d3943-198">If you are satisfied with your selections, select **Activate**.</span></span>

    ![Завершение и пересмотр](../media/content-understanding/ksetup5.png) </br> 

11. <span data-ttu-id="d3943-200">Откроется страница **базы знаний "активированная сеть** ", в результате чего система начнет анализировать выбранные сайты для разделов и создания сайта центра знаний.</span><span class="sxs-lookup"><span data-stu-id="d3943-200">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="d3943-201">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d3943-201">Select **Done**.</span></span></br>

    ![Activated](../media/content-understanding/ksetup6.png) </br> 

12. <span data-ttu-id="d3943-203">Вы вернетесь на страницу **Connect People to a Knowledge** .</span><span class="sxs-lookup"><span data-stu-id="d3943-203">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="d3943-204">На этой странице можно выбрать **Управлять** , чтобы внести изменения в параметры настройки.</span><span class="sxs-lookup"><span data-stu-id="d3943-204">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Примененные параметры](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> <span data-ttu-id="d3943-206">После установки администратор может изменить [Выбранные параметры управления знаниями](topic-experiences-discovery.md) в любое время, вернувшись на эту страницу.</span><span class="sxs-lookup"><span data-stu-id="d3943-206">After setup, an admin can [make changes to your selected knowledge management settings](topic-experiences-discovery.md) any time by returning to this page.</span></span>


## <a name="see-also"></a><span data-ttu-id="d3943-207">См. также</span><span class="sxs-lookup"><span data-stu-id="d3943-207">See also</span></span>



  






