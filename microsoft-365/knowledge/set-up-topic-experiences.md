---
title: Настройка тем в Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Узнайте, как настроить темы в Microsoft 365
ms.openlocfilehash: e11f0b75556a4a8ac0ffa40269d7166258128daf
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698559"
---
# <a name="set-up-topic-experiences-in-microsoft-365"></a><span data-ttu-id="7b27e-103">Настройка тем в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b27e-103">Set up topic experiences in Microsoft 365</span></span>

<span data-ttu-id="7b27e-104">Вы можете использовать Центр администрирования Microsoft 365 для настройки и настройки [тем.](topic-experiences-overview.md)</span><span class="sxs-lookup"><span data-stu-id="7b27e-104">You can use the Microsoft 365 admin center to set up and configure [topic experiences](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="7b27e-105">Важно спланировать лучший способ настройки тем в среде.</span><span class="sxs-lookup"><span data-stu-id="7b27e-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="7b27e-106">Прежде чем [](plan-topic-experiences.md) приступить к процедурам из этой статьи, ознакомьтесь с разделом "Планирование".</span><span class="sxs-lookup"><span data-stu-id="7b27e-106">Be sure to read [Plan topic experiences](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="7b27e-107">Чтобы получить доступ к Центру администрирования Microsoft 365 и настроить темы, необходимо быть глобальным администратором или администратором SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7b27e-107">You must be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up topic experiences.</span></span>

## <a name="set-up-topic-experiences"></a><span data-ttu-id="7b27e-108">Настройка тем</span><span class="sxs-lookup"><span data-stu-id="7b27e-108">Set up topic experiences</span></span>

<span data-ttu-id="7b27e-109">Настройка тем в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b27e-109">To set up topic experiences in Microsoft 365</span></span>

1. <span data-ttu-id="7b27e-110">В Центре [администрирования Microsoft 365](https://admin.microsoft.com)выберите "Программа установки" **и** выберите раздел "Файлы **и содержимое".**</span><span class="sxs-lookup"><span data-stu-id="7b27e-110">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="7b27e-111">В разделе **"Файлы и содержимое"** щелкните **"Подключить людей к знаниям".**</span><span class="sxs-lookup"><span data-stu-id="7b27e-111">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Подключение людей к знаниям](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="7b27e-113">На странице **"Подключение людей к знаниям"** нажмите кнопку **"Начало** работы", чтобы начать настройку.</span><span class="sxs-lookup"><span data-stu-id="7b27e-113">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![Начало работы](../media/k-get-started.png) 

4. <span data-ttu-id="7b27e-115">На странице **"Выбор способов поиска** разделов в сети знаний" будет настроено обнаружение тем.</span><span class="sxs-lookup"><span data-stu-id="7b27e-115">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="7b27e-116">В разделе **"Выбор источников тем SharePoint"** выберите, какие сайты SharePoint будут обходиться в качестве источников для разделов во время обнаружения.</span><span class="sxs-lookup"><span data-stu-id="7b27e-116">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="7b27e-117">Варианты:</span><span class="sxs-lookup"><span data-stu-id="7b27e-117">Choose from:</span></span>
    - <span data-ttu-id="7b27e-118">**Все сайты**: все сайты SharePoint в организации.</span><span class="sxs-lookup"><span data-stu-id="7b27e-118">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="7b27e-119">К ним относятся текущие и будущие сайты.</span><span class="sxs-lookup"><span data-stu-id="7b27e-119">This includes current and future sites.</span></span>
    - <span data-ttu-id="7b27e-120">**Все, кроме выбранных сайтов:** введите имена сайтов, которые нужно исключить.</span><span class="sxs-lookup"><span data-stu-id="7b27e-120">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="7b27e-121">Вы также можете отправить список сайтов, от обнаружения на которые вы хотите отказаться.</span><span class="sxs-lookup"><span data-stu-id="7b27e-121">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="7b27e-122">Сайты, созданные в будущем, будут включены в качестве источников для обнаружения тем.</span><span class="sxs-lookup"><span data-stu-id="7b27e-122">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="7b27e-123">**Только выбранные сайты:** введите имена сайтов, которые вы хотите включить.</span><span class="sxs-lookup"><span data-stu-id="7b27e-123">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="7b27e-124">Вы также можете отправить список сайтов.</span><span class="sxs-lookup"><span data-stu-id="7b27e-124">You can also upload a list of sites.</span></span> <span data-ttu-id="7b27e-125">Сайты, созданные в будущем, не будут включены в качестве источников для обнаружения тем.</span><span class="sxs-lookup"><span data-stu-id="7b27e-125">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="7b27e-126">**Нет сайтов:** не включать сайты SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7b27e-126">**No sites**: Do not include any SharePoint sites.</span></span>

    ![Выбор способов поиска тем](../media/ksetup1.png) 
   
5. <span data-ttu-id="7b27e-128">В разделе **"Исключить разделы** по имени" можно добавить имена разделов, которые нужно исключить из обнаружения тем.</span><span class="sxs-lookup"><span data-stu-id="7b27e-128">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="7b27e-129">Используйте этот параметр, чтобы не включать конфиденциальную информацию в качестве разделов.</span><span class="sxs-lookup"><span data-stu-id="7b27e-129">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="7b27e-130">Доступны следующие варианты:</span><span class="sxs-lookup"><span data-stu-id="7b27e-130">The options are:</span></span>
    - <span data-ttu-id="7b27e-131">**Не исключать темы**</span><span class="sxs-lookup"><span data-stu-id="7b27e-131">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="7b27e-132">**Исключение разделов по имени**</span><span class="sxs-lookup"><span data-stu-id="7b27e-132">**Exclude topics by name**</span></span>

    ![Исключить разделы](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="7b27e-134">(Менеджеры по знаниям также могут исключать темы в центре тем после обнаружения.)</span><span class="sxs-lookup"><span data-stu-id="7b27e-134">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="7b27e-135">Как исключить темы по имени</span><span class="sxs-lookup"><span data-stu-id="7b27e-135">How to exclude topics by name</span></span>    

    <span data-ttu-id="7b27e-136">Если нужно исключить темы, после выбора разделов "Исключить" по имени выберите шаблон CSV и обновите его, выбрав список тем, которые нужно исключить из результатов обнаружения.</span><span class="sxs-lookup"><span data-stu-id="7b27e-136">If you need to exclude topics, after selecting **Exclude topics by name**, select download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![Исключение разделов в шаблоне CSV](../media/exclude-topics-csv.png) 

    <span data-ttu-id="7b27e-138">В шаблоне CSV введите следующие сведения о темах, которые необходимо исключить:</span><span class="sxs-lookup"><span data-stu-id="7b27e-138">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="7b27e-139">**Name**: Type the name of the topic you want to exclude.</span><span class="sxs-lookup"><span data-stu-id="7b27e-139">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="7b27e-140">Это можно сделать двумя способами:</span><span class="sxs-lookup"><span data-stu-id="7b27e-140">There are two ways to do this:</span></span>
        - <span data-ttu-id="7b27e-141">Точное совпадение: можно включить точное имя или аббревиатуру (например, *Contoso* или *ATL).*</span><span class="sxs-lookup"><span data-stu-id="7b27e-141">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="7b27e-142">Частичное совпадение: можно исключить все темы, в них есть определенное слово.</span><span class="sxs-lookup"><span data-stu-id="7b27e-142">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="7b27e-143">Например,  arc исключит все темы с словом *arc* в нем, такие как "Arc *circle",* *"Arc arc welding"* или *"Training arc".* Обратите внимание, что он не будет исключать темы, в которых текст включается как часть слова, например *"Архитектура".*</span><span class="sxs-lookup"><span data-stu-id="7b27e-143">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="7b27e-144">**Означает (необязательно).** Если вы хотите исключить аббревиатуру, введите слова, за которые стоит аббревиатура.</span><span class="sxs-lookup"><span data-stu-id="7b27e-144">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="7b27e-145">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span><span class="sxs-lookup"><span data-stu-id="7b27e-145">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="7b27e-146">После завершения и с сохранения CSV-файла выберите  "Обзор", чтобы найти и выбрать его.</span><span class="sxs-lookup"><span data-stu-id="7b27e-146">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="7b27e-147">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7b27e-147">Select **Next**.</span></span>

6. <span data-ttu-id="7b27e-148">На странице **"Кто может видеть разделы** и где они могут их видеть", вы настроите видимость темы.</span><span class="sxs-lookup"><span data-stu-id="7b27e-148">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="7b27e-149">В разделе **"Кто может** видеть разделы в параметре сети знаний" вы выбираете, кто будет иметь доступ к сведениям о темах, например к темам, карточкам тем, ответам на вопросы в поиске и страницам тем.</span><span class="sxs-lookup"><span data-stu-id="7b27e-149">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="7b27e-150">Можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="7b27e-150">You can select:</span></span>
    - <span data-ttu-id="7b27e-151">**Все в моей организации**</span><span class="sxs-lookup"><span data-stu-id="7b27e-151">**Everyone in my organization**</span></span>
    - <span data-ttu-id="7b27e-152">**Только выбранные люди или группы безопасности**</span><span class="sxs-lookup"><span data-stu-id="7b27e-152">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="7b27e-153">**Никто**</span><span class="sxs-lookup"><span data-stu-id="7b27e-153">**No one**</span></span>

    ![Кто может видеть разделы](../media/ksetup2.png)  

 > [!Note] 
 > <span data-ttu-id="7b27e-155">Хотя этот параметр позволяет выбрать любого пользователя в организации, только пользователи, которым назначены лицензии на возможности работы с разделами, смогут просматривать разделы.</span><span class="sxs-lookup"><span data-stu-id="7b27e-155">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="7b27e-156">На странице **"Разрешения для управления** темами" выберите, кто сможет создавать, редактировать и управлять темами.</span><span class="sxs-lookup"><span data-stu-id="7b27e-156">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="7b27e-157">В разделе **"Кто может создавать и редактировать разделы"** можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="7b27e-157">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="7b27e-158">**Все в моей организации**</span><span class="sxs-lookup"><span data-stu-id="7b27e-158">**Everyone in my organization**</span></span>
    - <span data-ttu-id="7b27e-159">**Только выбранные люди или группы безопасности**</span><span class="sxs-lookup"><span data-stu-id="7b27e-159">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="7b27e-160">**Никто**</span><span class="sxs-lookup"><span data-stu-id="7b27e-160">**No one**</span></span>

    ![Разрешения для управления темами, кто может создавать и редактировать разделы](../media/ksetup3.png) 

8. <span data-ttu-id="7b27e-162">В разделе **"Кто может управлять темами"** можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="7b27e-162">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="7b27e-163">**Все в моей организации**</span><span class="sxs-lookup"><span data-stu-id="7b27e-163">**Everyone in my organization**</span></span>
    - <span data-ttu-id="7b27e-164">**Только выбранные люди или группы безопасности**</span><span class="sxs-lookup"><span data-stu-id="7b27e-164">**Only selected people or security groups**</span></span>

    ![Разрешения для управления темами](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="7b27e-166">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7b27e-166">Select **Next**.</span></span>

9. <span data-ttu-id="7b27e-167">На странице **"Создание центра тем"** можно создать сайт центра тем, на котором можно просматривать страницы тем и управлять темами.</span><span class="sxs-lookup"><span data-stu-id="7b27e-167">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="7b27e-168">В поле **"Имя сайта"** введите имя центра тем.</span><span class="sxs-lookup"><span data-stu-id="7b27e-168">In the **Site name** box, type a name for your Topic center.</span></span> <span data-ttu-id="7b27e-169">При желании можно ввести краткое описание в **поле "Описание".**</span><span class="sxs-lookup"><span data-stu-id="7b27e-169">You can optionally type a short description in the **Description** box.</span></span> 

<span data-ttu-id="7b27e-170">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7b27e-170">Select **Next**.</span></span>

   ![Создание центра знаний](../media/ksetup4.png)  

10. <span data-ttu-id="7b27e-172">На странице **Проверка и завершение** можно просмотреть выбранный параметр и внести в него изменения.</span><span class="sxs-lookup"><span data-stu-id="7b27e-172">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="7b27e-173">Если выбор вас устраивает, нажмите кнопку **Активировать**.</span><span class="sxs-lookup"><span data-stu-id="7b27e-173">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="7b27e-174">**Отобразит** активированную страницу сети знаний, подтверждая, что система начнет анализировать выбранные сайты для тем и создавать сайт центра знаний.</span><span class="sxs-lookup"><span data-stu-id="7b27e-174">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="7b27e-175">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="7b27e-175">Select **Done**.</span></span>

12. <span data-ttu-id="7b27e-176">Вы будете возвращены на страницу **"Подключение людей к знаниям".**</span><span class="sxs-lookup"><span data-stu-id="7b27e-176">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="7b27e-177">На этой странице можно выбрать **Управлять**, чтобы внести изменения в параметры настройки.</span><span class="sxs-lookup"><span data-stu-id="7b27e-177">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Применены параметры](../media/ksetup7.png)    

## <a name="assign-licenses"></a><span data-ttu-id="7b27e-179">Назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="7b27e-179">Assign licenses</span></span>

<span data-ttu-id="7b27e-180">После настройки тем необходимо назначить лицензии пользователям, которые будут использовать эти темы.</span><span class="sxs-lookup"><span data-stu-id="7b27e-180">Once you have configured topic experiences, you must assign licenses for the users who will be using topic experiences.</span></span> <span data-ttu-id="7b27e-181">Только пользователи с лицензией могут видеть информацию по темам, включая выделения, карточки тем, страницы тем и центр тем.</span><span class="sxs-lookup"><span data-stu-id="7b27e-181">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="7b27e-182">Чтобы назначить лицензии, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="7b27e-182">To assign licenses:</span></span>

1. <span data-ttu-id="7b27e-183">В Центре администрирования Microsoft 365 в разделе **Пользователи**, щелкните **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="7b27e-183">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="7b27e-184">Выберите пользователей, которых вы хотите лицензировать, и щелкните **Управление лицензиями продуктов**.</span><span class="sxs-lookup"><span data-stu-id="7b27e-184">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="7b27e-185">Щелкните **Назначить еще**.</span><span class="sxs-lookup"><span data-stu-id="7b27e-185">Select **Assign more**.</span></span>

4. <span data-ttu-id="7b27e-186">Under **Licenses**, select **Topic Experiences**.</span><span class="sxs-lookup"><span data-stu-id="7b27e-186">Under **Licenses**, select **Topic Experiences**.</span></span>

5. <span data-ttu-id="7b27e-187">В **разделе "Приложения"** убедитесь, что выбраны **соединители Graph Search с помощью index** и Topic **Experiences.**</span><span class="sxs-lookup"><span data-stu-id="7b27e-187">Under **Apps**, make sure **Graph Connectors Search with Index** and **Topic Experiences** are both selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7b27e-188">![Лицензии SharePoint Syntex в Центре администрирования Microsoft 365](../media/topic-experiences-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="7b27e-188">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/topic-experiences-licenses.png)</span></span>

6. <span data-ttu-id="7b27e-189">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="7b27e-189">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="7b27e-190">Управление темами</span><span class="sxs-lookup"><span data-stu-id="7b27e-190">Manage topic experiences</span></span>

<span data-ttu-id="7b27e-191">Настроив темы, вы можете изменить параметры, выбранные во время настройки в Центре администрирования [Microsoft 365.](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)</span><span class="sxs-lookup"><span data-stu-id="7b27e-191">Once you have set up topic experiences, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="7b27e-192">См. следующие ссылки:</span><span class="sxs-lookup"><span data-stu-id="7b27e-192">See the following references:</span></span>

- [<span data-ttu-id="7b27e-193">Управление обнаружением тем в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b27e-193">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="7b27e-194">Управление видимостью тем в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b27e-194">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="7b27e-195">Управление разрешениями тем в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b27e-195">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="7b27e-196">Изменение имени центра тем в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b27e-196">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="7b27e-197">См. также</span><span class="sxs-lookup"><span data-stu-id="7b27e-197">See also</span></span>

[<span data-ttu-id="7b27e-198">Обзор работы с разделами</span><span class="sxs-lookup"><span data-stu-id="7b27e-198">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
