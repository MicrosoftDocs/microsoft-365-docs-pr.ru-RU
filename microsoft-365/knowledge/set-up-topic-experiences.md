---
title: Настройка Microsoft Viva Topics
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Узнайте, как настроить Microsoft Viva Topics
ms.openlocfilehash: 6bd0d3eca653ae44e46b410ef3ac55fe11629a6b
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150504"
---
# <a name="set-up-microsoft-viva-topics"></a><span data-ttu-id="cc1ee-103">Настройка Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="cc1ee-103">Set up Microsoft Viva Topics</span></span>

<span data-ttu-id="cc1ee-104">Для настройки и настройки разделов можно использовать Центр администрирования [Microsoft](topic-experiences-overview.md)365.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-104">You can use the Microsoft 365 admin center to set up and configure [Topics](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="cc1ee-105">Важно спланировать лучший способ настройки тем в среде.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="cc1ee-106">Прежде чем приступить к процедурам из этой статьи, ознакомьтесь с разделами "Планирование microsoft [Viva".](plan-topic-experiences.md)</span><span class="sxs-lookup"><span data-stu-id="cc1ee-106">Be sure to read [Plan for Microsoft Viva Topics](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="cc1ee-107">Чтобы получить доступ к Центру администрирования Microsoft 365 и настроить разделы, необходимо подписаться на [Viva Topics](https://www.microsoft.com/microsoft-viva/topics) и быть глобальным администратором или администратором SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-107">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="cc1ee-108">Видеодемонстрация</span><span class="sxs-lookup"><span data-stu-id="cc1ee-108">Video demonstration</span></span>

<span data-ttu-id="cc1ee-109">В этом видео показан процесс настройки разделов в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-109">This video shows the process for setting up Topics in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="set-up-topics"></a><span data-ttu-id="cc1ee-110">Настройка тем</span><span class="sxs-lookup"><span data-stu-id="cc1ee-110">Set up Topics</span></span>

<span data-ttu-id="cc1ee-111">Настройка разделов</span><span class="sxs-lookup"><span data-stu-id="cc1ee-111">To set up Topics</span></span>

1. <span data-ttu-id="cc1ee-112">В Центре [администрирования Microsoft 365](https://admin.microsoft.com)выберите "Программа установки" **и** выберите раздел "Файлы **и содержимое".**</span><span class="sxs-lookup"><span data-stu-id="cc1ee-112">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="cc1ee-113">В разделе **"Файлы и содержимое"** щелкните **"Подключить людей к знаниям".**</span><span class="sxs-lookup"><span data-stu-id="cc1ee-113">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Подключение людей к знаниям](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="cc1ee-115">На странице **"Подключение людей к знаниям"** нажмите кнопку **"Начало** работы", чтобы начать настройку.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-115">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![Начало работы](../media/k-get-started.png) 

4. <span data-ttu-id="cc1ee-117">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-117">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="cc1ee-118">В разделе **"Выбор источников тем SharePoint"** выберите, какие сайты SharePoint будут обходиться в качестве источников для разделов во время обнаружения.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-118">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="cc1ee-119">Варианты:</span><span class="sxs-lookup"><span data-stu-id="cc1ee-119">Choose from:</span></span>
    - <span data-ttu-id="cc1ee-120">**Все сайты**: все сайты SharePoint в организации.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-120">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="cc1ee-121">К ним относятся текущие и будущие сайты.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-121">This includes current and future sites.</span></span>
    - <span data-ttu-id="cc1ee-122">**Все, кроме выбранных сайтов:** введите имена сайтов, которые нужно исключить.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-122">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="cc1ee-123">Вы также можете отправить список сайтов, от обнаружения на которые вы хотите отказаться.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-123">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="cc1ee-124">Сайты, созданные в будущем, будут включены в качестве источников для обнаружения тем.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-124">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="cc1ee-125">**Только выбранные сайты:** введите имена сайтов, которые вы хотите включить.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-125">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="cc1ee-126">Вы также можете отправить список сайтов.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-126">You can also upload a list of sites.</span></span> <span data-ttu-id="cc1ee-127">Сайты, созданные в будущем, не будут включены в качестве источников для обнаружения тем.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-127">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="cc1ee-128">**Нет сайтов:** не включать сайты SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-128">**No sites**: Do not include any SharePoint sites.</span></span>

    ![Выбор способов поиска тем](../media/ksetup1.png) 
   
5. <span data-ttu-id="cc1ee-130">В разделе **"Исключить разделы** по имени" можно добавить имена разделов, которые нужно исключить из обнаружения тем.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-130">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="cc1ee-131">Используйте этот параметр, чтобы не включать конфиденциальную информацию в качестве разделов.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-131">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="cc1ee-132">Доступны следующие варианты:</span><span class="sxs-lookup"><span data-stu-id="cc1ee-132">The options are:</span></span>
    - <span data-ttu-id="cc1ee-133">**Не исключать темы**</span><span class="sxs-lookup"><span data-stu-id="cc1ee-133">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="cc1ee-134">**Исключение разделов по имени**</span><span class="sxs-lookup"><span data-stu-id="cc1ee-134">**Exclude topics by name**</span></span>

    ![Исключить разделы](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="cc1ee-136">(Менеджеры по знаниям также могут исключать темы в центре тем после обнаружения.)</span><span class="sxs-lookup"><span data-stu-id="cc1ee-136">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="cc1ee-137">Как исключить темы по имени</span><span class="sxs-lookup"><span data-stu-id="cc1ee-137">How to exclude topics by name</span></span>    

    <span data-ttu-id="cc1ee-138">Если нужно исключить темы, после выбора разделов "Исключить" по имени скачайте шаблон CSV и обновите его, выбрав список тем, которые нужно исключить из результатов обнаружения.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-138">If you need to exclude topics, after selecting **Exclude topics by name**, download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![Исключение разделов в шаблоне CSV](../media/exclude-topics-csv.png) 

    <span data-ttu-id="cc1ee-140">В шаблоне CSV введите следующие сведения о темах, которые необходимо исключить:</span><span class="sxs-lookup"><span data-stu-id="cc1ee-140">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="cc1ee-141">**Name**: Type the name of the topic you want to exclude.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-141">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="cc1ee-142">Это можно сделать двумя способами:</span><span class="sxs-lookup"><span data-stu-id="cc1ee-142">There are two ways to do this:</span></span>
        - <span data-ttu-id="cc1ee-143">Точное совпадение: можно включить точное имя или аббревиатуру (например, *Contoso* или *ATL).*</span><span class="sxs-lookup"><span data-stu-id="cc1ee-143">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="cc1ee-144">Частичное совпадение: можно исключить все темы, в них есть определенное слово.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-144">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="cc1ee-145">Например,  arc исключит все темы со словом *arc* в нем, такие как "Arc *circle",* *"Arc arc welding"* или *"Training arc".* Обратите внимание, что он не будет исключать темы, в которых текст включается как часть слова, например *"Архитектура".*</span><span class="sxs-lookup"><span data-stu-id="cc1ee-145">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="cc1ee-146">**Означает (необязательно).** Если вы хотите исключить аббревиатуру, введите слова, за которые стоит аббревиатура.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-146">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="cc1ee-147">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-147">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="cc1ee-148">После завершения и с сохранения CSV-файла выберите  "Обзор", чтобы найти и выбрать его.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-148">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="cc1ee-149">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-149">Select **Next**.</span></span>

6. <span data-ttu-id="cc1ee-150">На странице **"Кто может видеть разделы и** где они могут их видеть", вы настроите видимость темы.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-150">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="cc1ee-151">В разделе **"Кто может** видеть разделы" вы выбираете, кто будет иметь доступ к сведениям о темах, таким как разделы, карточки тем, ответы на темы в поиске и страницы тем.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-151">In the **Who can see topics** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="cc1ee-152">Можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="cc1ee-152">You can select:</span></span>
    - <span data-ttu-id="cc1ee-153">**Все в моей организации**</span><span class="sxs-lookup"><span data-stu-id="cc1ee-153">**Everyone in my organization**</span></span>
    - <span data-ttu-id="cc1ee-154">**Только выбранные люди или группы безопасности**</span><span class="sxs-lookup"><span data-stu-id="cc1ee-154">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="cc1ee-155">**Никто**</span><span class="sxs-lookup"><span data-stu-id="cc1ee-155">**No one**</span></span>

    ![Кто может видеть разделы](../media/ksetup2.png)  

    > [!Note] 
    > <span data-ttu-id="cc1ee-157">Хотя этот параметр позволяет выбрать любого пользователя в организации, только пользователи, которым назначены лицензии на возможности работы с разделами, смогут просматривать разделы.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-157">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="cc1ee-158">На странице **"Разрешения для управления** темами" выберите, кто сможет создавать, редактировать и управлять темами.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-158">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="cc1ee-159">В разделе **"Кто может создавать и редактировать разделы"** можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="cc1ee-159">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="cc1ee-160">**Все в моей организации**</span><span class="sxs-lookup"><span data-stu-id="cc1ee-160">**Everyone in my organization**</span></span>
    - <span data-ttu-id="cc1ee-161">**Только выбранные люди или группы безопасности**</span><span class="sxs-lookup"><span data-stu-id="cc1ee-161">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="cc1ee-162">**Никто**</span><span class="sxs-lookup"><span data-stu-id="cc1ee-162">**No one**</span></span>

    ![Разрешения для управления темами, кто может создавать и редактировать разделы](../media/ksetup3.png) 

8. <span data-ttu-id="cc1ee-164">В разделе **"Кто может управлять темами"** можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="cc1ee-164">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="cc1ee-165">**Все в моей организации**</span><span class="sxs-lookup"><span data-stu-id="cc1ee-165">**Everyone in my organization**</span></span>
    - <span data-ttu-id="cc1ee-166">**Только выбранные люди или группы безопасности**</span><span class="sxs-lookup"><span data-stu-id="cc1ee-166">**Only selected people or security groups**</span></span>

    ![Разрешения для управления темами](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="cc1ee-168">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-168">Select **Next**.</span></span>

9. <span data-ttu-id="cc1ee-169">На странице **"Создание центра тем"** можно создать сайт центра тем, на котором можно просматривать страницы тем и управлять темами.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-169">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="cc1ee-170">В поле **"Имя сайта"** введите имя центра тем.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-170">In the **Site name** box, type a name for your topic center.</span></span> <span data-ttu-id="cc1ee-171">При желании можно ввести краткое описание в **поле "Описание".**</span><span class="sxs-lookup"><span data-stu-id="cc1ee-171">You can optionally type a short description in the **Description** box.</span></span> 

   <span data-ttu-id="cc1ee-172">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-172">Select **Next**.</span></span>

   ![Создание центра знаний](../media/ksetup4.png)  

10. <span data-ttu-id="cc1ee-174">На странице **Проверка и завершение** можно просмотреть выбранный параметр и внести в него изменения.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-174">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="cc1ee-175">Если выбор вас устраивает, нажмите кнопку **Активировать**.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-175">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="cc1ee-176">Отобразит активированную страницу **Viva Topics,** подтверждая, что система начнет анализировать выбранные сайты для разделов и создавать сайт центра тем.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-176">The **Viva Topics activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the topic center site.</span></span> <span data-ttu-id="cc1ee-177">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-177">Select **Done**.</span></span>

12. <span data-ttu-id="cc1ee-178">You'll be returned to your **Connect people to knowledge** page.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-178">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="cc1ee-179">На этой странице можно выбрать **Управлять**, чтобы внести изменения в параметры настройки.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-179">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Применены параметры](../media/ksetup7.png)    

## <a name="assign-licenses"></a><span data-ttu-id="cc1ee-181">Назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="cc1ee-181">Assign licenses</span></span>

<span data-ttu-id="cc1ee-182">После настройки тем необходимо назначить лицензии пользователям, которые будут использовать разделы.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-182">Once you have configured topic experiences, you must assign licenses for the users who will be using Topics.</span></span> <span data-ttu-id="cc1ee-183">Только пользователи с лицензией могут видеть информацию по темам, включая выделения, карточки тем, страницы тем и центр тем.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-183">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="cc1ee-184">Чтобы назначить лицензии, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="cc1ee-184">To assign licenses:</span></span>

1. <span data-ttu-id="cc1ee-185">В Центре администрирования Microsoft 365 в разделе **Пользователи**, щелкните **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-185">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="cc1ee-186">Выберите пользователей, которые вы хотите лицензировать, и щелкните **"Лицензии и приложения".**</span><span class="sxs-lookup"><span data-stu-id="cc1ee-186">Select the users that you want to license, and click **Licenses and apps**.</span></span>

3. <span data-ttu-id="cc1ee-187">В **разделе "Приложения"** убедитесь, что **выбраны соединители Graph Search с помощью index** и Topic **Experiences.**</span><span class="sxs-lookup"><span data-stu-id="cc1ee-187">Under **Apps**, make sure **Graph Connectors Search with Index** and **Topic Experiences** are both selected.</span></span>

4. <span data-ttu-id="cc1ee-188">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-188">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="cc1ee-189">Управление темами</span><span class="sxs-lookup"><span data-stu-id="cc1ee-189">Manage topic experiences</span></span>

<span data-ttu-id="cc1ee-190">Настроив разделы, вы можете изменить параметры, выбранные во время настройки в Центре администрирования [Microsoft 365.](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)</span><span class="sxs-lookup"><span data-stu-id="cc1ee-190">Once you have set up Topics, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="cc1ee-191">См. следующие ссылки:</span><span class="sxs-lookup"><span data-stu-id="cc1ee-191">See the following references:</span></span>

- [<span data-ttu-id="cc1ee-192">Управление обнаружением тем в Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="cc1ee-192">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="cc1ee-193">Управление видимостью тем в microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="cc1ee-193">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="cc1ee-194">Управление разрешениями тем в microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="cc1ee-194">Manage topic permissions in Microsoft Viva Topics</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="cc1ee-195">Изменение имени центра тем в Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="cc1ee-195">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="cc1ee-196">См. также</span><span class="sxs-lookup"><span data-stu-id="cc1ee-196">See also</span></span>

[<span data-ttu-id="cc1ee-197">Обзор работы с разделами</span><span class="sxs-lookup"><span data-stu-id="cc1ee-197">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
