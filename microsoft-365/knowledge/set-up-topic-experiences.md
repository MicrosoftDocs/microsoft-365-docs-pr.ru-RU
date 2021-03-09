---
title: Настройка тем Microsoft Viva
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
ms.openlocfilehash: cc420a0631f5b861341116abcd50cfe90e15450e
ms.sourcegitcommit: 6e260f5f5842debe1098138eecea9068330dc17f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2021
ms.locfileid: "50551895"
---
# <a name="set-up-microsoft-viva-topics"></a><span data-ttu-id="d1202-103">Настройка тем Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="d1202-103">Set up Microsoft Viva Topics</span></span>

<span data-ttu-id="d1202-104">Вы можете использовать центр администрирования Microsoft 365 для настройки и настройки [Темы.](topic-experiences-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d1202-104">You can use the Microsoft 365 admin center to set up and configure [Topics](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="d1202-105">Важно спланировать оптимальный способ настройки и настройки тем в среде.</span><span class="sxs-lookup"><span data-stu-id="d1202-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="d1202-106">Прежде чем приступить к процедурам в этой статье, ознакомьтесь с разделом [Plan for Microsoft Viva Topics.](plan-topic-experiences.md)</span><span class="sxs-lookup"><span data-stu-id="d1202-106">Be sure to read [Plan for Microsoft Viva Topics](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="d1202-107">Вы должны [подписаться на Viva Topics](https://www.microsoft.com/microsoft-viva/topics) и быть глобальным администратором или администратором SharePoint, чтобы получить доступ к центру администрирования Microsoft 365 и настроить Разделы.</span><span class="sxs-lookup"><span data-stu-id="d1202-107">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="d1202-108">Если вы настроили SharePoint на управляемые [устройства,](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)не забудьте настроить Разделы с управляемого устройства.</span><span class="sxs-lookup"><span data-stu-id="d1202-108">If you have configured SharePoint to [require managed devices](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices), be sure to set up Topics from a managed device.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="d1202-109">Видеодемонстрация</span><span class="sxs-lookup"><span data-stu-id="d1202-109">Video demonstration</span></span>

<span data-ttu-id="d1202-110">В этом видео показан процесс настройки Разделы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d1202-110">This video shows the process for setting up Topics in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="set-up-topics"></a><span data-ttu-id="d1202-111">Настройка тем</span><span class="sxs-lookup"><span data-stu-id="d1202-111">Set up Topics</span></span>

<span data-ttu-id="d1202-112">Настройка Разделов</span><span class="sxs-lookup"><span data-stu-id="d1202-112">To set up Topics</span></span>

1. <span data-ttu-id="d1202-113">В центре [администрирования Microsoft 365](https://admin.microsoft.com)выберите **установку,** а затем просмотреть **раздел Файлы и контент.**</span><span class="sxs-lookup"><span data-stu-id="d1202-113">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="d1202-114">В разделе **Файлы и контент** нажмите кнопку Подключение людей к **знаниям.**</span><span class="sxs-lookup"><span data-stu-id="d1202-114">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Подключение людей к знаниям](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="d1202-116">На странице **Подключение людей к знаниям** нажмите **кнопку Начало** ходить вас через процесс установки.</span><span class="sxs-lookup"><span data-stu-id="d1202-116">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![Начало работы](../media/k-get-started.png) 

4. <span data-ttu-id="d1202-118">На странице **Выбор способов поиска тем Viva Topics** вы настроите обнаружение темы.</span><span class="sxs-lookup"><span data-stu-id="d1202-118">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="d1202-119">В разделе **Выбор источников темы SharePoint** выберите, какие сайты SharePoint будут обходиться в качестве источников для ваших тем во время обнаружения.</span><span class="sxs-lookup"><span data-stu-id="d1202-119">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="d1202-120">Варианты:</span><span class="sxs-lookup"><span data-stu-id="d1202-120">Choose from:</span></span>
    - <span data-ttu-id="d1202-121">**Все сайты.** Все сайты SharePoint в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d1202-121">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="d1202-122">Это включает текущие и будущие сайты.</span><span class="sxs-lookup"><span data-stu-id="d1202-122">This includes current and future sites.</span></span>
    - <span data-ttu-id="d1202-123">**Все, кроме выбранных сайтов:** введите имена сайтов, которые необходимо исключить.</span><span class="sxs-lookup"><span data-stu-id="d1202-123">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="d1202-124">Вы также можете загрузить список сайтов, которые вы хотите отказаться от обнаружения.</span><span class="sxs-lookup"><span data-stu-id="d1202-124">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="d1202-125">Сайты, созданные в будущем, будут включены в качестве источников для обнаружения тем.</span><span class="sxs-lookup"><span data-stu-id="d1202-125">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="d1202-126">**Только выбранные сайты:** введите имена сайтов, которые вы хотите включить.</span><span class="sxs-lookup"><span data-stu-id="d1202-126">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="d1202-127">Вы также можете загрузить список сайтов.</span><span class="sxs-lookup"><span data-stu-id="d1202-127">You can also upload a list of sites.</span></span> <span data-ttu-id="d1202-128">Сайты, созданные в будущем, не будут включены в качестве источников для обнаружения тем.</span><span class="sxs-lookup"><span data-stu-id="d1202-128">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="d1202-129">**Нет сайтов.** Не включай сайты SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d1202-129">**No sites**: Do not include any SharePoint sites.</span></span>

    ![Выбор способов поиска тем](../media/ksetup1.png) 
   
5. <span data-ttu-id="d1202-131">В разделе **Исключить темы по имени** можно добавить имена тем, которые необходимо исключить из обнаружения тем.</span><span class="sxs-lookup"><span data-stu-id="d1202-131">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="d1202-132">Используйте этот параметр, чтобы предотвратить включение конфиденциальной информации в качестве тем.</span><span class="sxs-lookup"><span data-stu-id="d1202-132">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="d1202-133">Доступны следующие варианты:</span><span class="sxs-lookup"><span data-stu-id="d1202-133">The options are:</span></span>
    - <span data-ttu-id="d1202-134">**Не исключайте любые темы**</span><span class="sxs-lookup"><span data-stu-id="d1202-134">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="d1202-135">**Исключение тем по имени**</span><span class="sxs-lookup"><span data-stu-id="d1202-135">**Exclude topics by name**</span></span>

    ![Исключение тем](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="d1202-137">(Руководители знаний также могут исключать темы в центре тем после обнаружения.)</span><span class="sxs-lookup"><span data-stu-id="d1202-137">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="d1202-138">Как исключить темы по имени</span><span class="sxs-lookup"><span data-stu-id="d1202-138">How to exclude topics by name</span></span>    

    <span data-ttu-id="d1202-139">Если необходимо исключить темы, после выбора разделов **Exclude** по имени скачайте шаблон csv и обновите его списком тем, которые необходимо исключить из результатов обнаружения.</span><span class="sxs-lookup"><span data-stu-id="d1202-139">If you need to exclude topics, after selecting **Exclude topics by name**, download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![Исключение тем в шаблоне CSV](../media/exclude-topics-csv.png) 

    <span data-ttu-id="d1202-141">В шаблоне CSV введите следующую информацию о темах, которые необходимо исключить:</span><span class="sxs-lookup"><span data-stu-id="d1202-141">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="d1202-142">**Имя.** Введите имя темы, которая вы хотите исключить.</span><span class="sxs-lookup"><span data-stu-id="d1202-142">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="d1202-143">Это можно сделать двумя способами:</span><span class="sxs-lookup"><span data-stu-id="d1202-143">There are two ways to do this:</span></span>
        - <span data-ttu-id="d1202-144">Точное совпадение. Вы можете включить точное имя или аббревиатура (например, *Contoso* или *ATL).*</span><span class="sxs-lookup"><span data-stu-id="d1202-144">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="d1202-145">Частичное совпадение. Вы можете исключить все темы, в них есть определенное слово.</span><span class="sxs-lookup"><span data-stu-id="d1202-145">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="d1202-146">Например, *дуга* исключает все темы со *словом* дуга в нем, такие как круг *дуги,* сварка плазменной дуги или *дуга обучения.* Обратите внимание, что не исключены темы, в которые текст включен как часть слова, например *Архитектура.*</span><span class="sxs-lookup"><span data-stu-id="d1202-146">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="d1202-147">**Означает (необязательно).** Если вы хотите исключить аббревиатура, введите слова, которые обозначает аббревиатура.</span><span class="sxs-lookup"><span data-stu-id="d1202-147">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="d1202-148">**MatchType-Exact/Partial**. Введите, было ли вписано имя *точным* или *частичным типом* совпадения.</span><span class="sxs-lookup"><span data-stu-id="d1202-148">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="d1202-149">После завершения и сэкономленного файла .csv выберите **Просмотр,** чтобы найти и выбрать его.</span><span class="sxs-lookup"><span data-stu-id="d1202-149">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="d1202-150">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d1202-150">Select **Next**.</span></span>

6. <span data-ttu-id="d1202-151">На странице **Кто может видеть темы** и где они могут их видеть, будет настроена видимость темы.</span><span class="sxs-lookup"><span data-stu-id="d1202-151">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="d1202-152">В разделе **Кто может** видеть разделы, вы выбираете, у кого будет доступ к деталям темы, например к выделенным темам, карточкам тем, ответам на темы в поиске и страницам тем.</span><span class="sxs-lookup"><span data-stu-id="d1202-152">In the **Who can see topics** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="d1202-153">Можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="d1202-153">You can select:</span></span>
    - <span data-ttu-id="d1202-154">**Все в моей организации**</span><span class="sxs-lookup"><span data-stu-id="d1202-154">**Everyone in my organization**</span></span>
    - <span data-ttu-id="d1202-155">**Только выбранные люди или группы безопасности**</span><span class="sxs-lookup"><span data-stu-id="d1202-155">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="d1202-156">**Никто**</span><span class="sxs-lookup"><span data-stu-id="d1202-156">**No one**</span></span>

    ![Кто может видеть темы](../media/ksetup2.png)  

    > [!Note] 
    > <span data-ttu-id="d1202-158">Хотя этот параметр позволяет выбрать любого пользователя в организации, просматривать темы смогут только пользователи, которым назначены лицензии на раздел Experiences.</span><span class="sxs-lookup"><span data-stu-id="d1202-158">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="d1202-159">На странице **Разрешения для управления темами** вы выбираете, кто сможет создавать, редактировать или управлять темами.</span><span class="sxs-lookup"><span data-stu-id="d1202-159">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="d1202-160">В разделе **Кто может создавать и редактировать темы,** можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="d1202-160">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="d1202-161">**Все в моей организации**</span><span class="sxs-lookup"><span data-stu-id="d1202-161">**Everyone in my organization**</span></span>
    - <span data-ttu-id="d1202-162">**Только выбранные люди или группы безопасности**</span><span class="sxs-lookup"><span data-stu-id="d1202-162">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="d1202-163">**Никто**</span><span class="sxs-lookup"><span data-stu-id="d1202-163">**No one**</span></span>

    ![Разрешения для управления темами, которые могут создавать и редактировать темы](../media/ksetup3.png) 

8. <span data-ttu-id="d1202-165">В разделе **Кто может управлять темами,** можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="d1202-165">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="d1202-166">**Все в моей организации**</span><span class="sxs-lookup"><span data-stu-id="d1202-166">**Everyone in my organization**</span></span>
    - <span data-ttu-id="d1202-167">**Только выбранные люди или группы безопасности**</span><span class="sxs-lookup"><span data-stu-id="d1202-167">**Only selected people or security groups**</span></span>

    ![Разрешения для управления темами](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="d1202-169">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d1202-169">Select **Next**.</span></span>

9. <span data-ttu-id="d1202-170">На странице **Создание центра тем** можно создать сайт центра тем, на котором можно просматривать страницы тем и управлять темами.</span><span class="sxs-lookup"><span data-stu-id="d1202-170">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="d1202-171">В поле **имя сайта** введите имя для центра темы.</span><span class="sxs-lookup"><span data-stu-id="d1202-171">In the **Site name** box, type a name for your topic center.</span></span> <span data-ttu-id="d1202-172">Вы можете дополнительно ввести краткое описание в поле **Описание.**</span><span class="sxs-lookup"><span data-stu-id="d1202-172">You can optionally type a short description in the **Description** box.</span></span> 

   <span data-ttu-id="d1202-173">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d1202-173">Select **Next**.</span></span>

   ![Создание Центра знаний](../media/ksetup4.png)  

10. <span data-ttu-id="d1202-175">На странице **Проверка и завершение** можно просмотреть выбранный параметр и внести в него изменения.</span><span class="sxs-lookup"><span data-stu-id="d1202-175">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="d1202-176">Если выбор вас устраивает, нажмите кнопку **Активировать**.</span><span class="sxs-lookup"><span data-stu-id="d1202-176">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="d1202-177">**Активированная страница Viva Topics** будет отображаться, что подтверждает, что система теперь начнет анализировать выбранные сайты для тем и создавать сайт центра тем.</span><span class="sxs-lookup"><span data-stu-id="d1202-177">The **Viva Topics activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the topic center site.</span></span> <span data-ttu-id="d1202-178">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d1202-178">Select **Done**.</span></span>

12. <span data-ttu-id="d1202-179">Вы будете возвращены на страницу **Подключение людей к знаниям.**</span><span class="sxs-lookup"><span data-stu-id="d1202-179">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="d1202-180">На этой странице можно выбрать **Управлять**, чтобы внести изменения в параметры настройки.</span><span class="sxs-lookup"><span data-stu-id="d1202-180">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Применены параметры](../media/ksetup7.png)    

## <a name="assign-licenses"></a><span data-ttu-id="d1202-182">Назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="d1202-182">Assign licenses</span></span>

<span data-ttu-id="d1202-183">После настройки темы необходимо назначить лицензии пользователям, которые будут использовать Разделы.</span><span class="sxs-lookup"><span data-stu-id="d1202-183">Once you have configured topic experiences, you must assign licenses for the users who will be using Topics.</span></span> <span data-ttu-id="d1202-184">Только пользователи с лицензией могут видеть сведения по темам, включая основные моменты, карточки темы, страницы темы и центр тем.</span><span class="sxs-lookup"><span data-stu-id="d1202-184">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="d1202-185">Чтобы назначить лицензии, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d1202-185">To assign licenses:</span></span>

1. <span data-ttu-id="d1202-186">В Центре администрирования Microsoft 365 в разделе **Пользователи**, щелкните **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="d1202-186">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="d1202-187">Выберите пользователей, которые необходимо лицензировать, и нажмите **кнопку Лицензии и приложения.**</span><span class="sxs-lookup"><span data-stu-id="d1202-187">Select the users that you want to license, and click **Licenses and apps**.</span></span>

3. <span data-ttu-id="d1202-188">В **соответствии с лицензиями** выберите **Разделы Viva**.</span><span class="sxs-lookup"><span data-stu-id="d1202-188">Under **Licenses**, select **Viva Topics**.</span></span>

4. <span data-ttu-id="d1202-189">В **приложениях** убедитесь, что **выбраны графовые соединители с помощью Index (Viva Topics)** и **Viva Topics.**</span><span class="sxs-lookup"><span data-stu-id="d1202-189">Under **Apps**, make sure **Graph Connectors Search with Index (Viva Topics)** and **Viva Topics** are both selected.</span></span>

    ![Лицензии Microsoft Viva Topics в центре администрирования Microsoft 365](../media/topic-experiences-licenses.png)

5. <span data-ttu-id="d1202-191">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="d1202-191">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="d1202-192">Управление опытом темы</span><span class="sxs-lookup"><span data-stu-id="d1202-192">Manage topic experiences</span></span>

<span data-ttu-id="d1202-193">После настройки Разделы можно изменить параметры, выбранные во время установки в [центре администрирования Microsoft 365.](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)</span><span class="sxs-lookup"><span data-stu-id="d1202-193">Once you have set up Topics, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="d1202-194">См. следующие справочные материалы:</span><span class="sxs-lookup"><span data-stu-id="d1202-194">See the following references:</span></span>

- [<span data-ttu-id="d1202-195">Управление обнаружением тем в Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="d1202-195">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="d1202-196">Управление обзором тем в Разделах Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="d1202-196">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="d1202-197">Управление разрешениями тем в Разделах Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="d1202-197">Manage topic permissions in Microsoft Viva Topics</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="d1202-198">Изменение имени центра темы в Разделе Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="d1202-198">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="d1202-199">См. также</span><span class="sxs-lookup"><span data-stu-id="d1202-199">See also</span></span>

[<span data-ttu-id="d1202-200">Обзор опытом темы</span><span class="sxs-lookup"><span data-stu-id="d1202-200">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
