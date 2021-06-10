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
ms.openlocfilehash: 19395cf3a9ecc991f08f375425803cb81a2a1d35
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51930225"
---
# <a name="set-up-microsoft-viva-topics"></a><span data-ttu-id="975c2-103">Настройка тем Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="975c2-103">Set up Microsoft Viva Topics</span></span>

<span data-ttu-id="975c2-104">Вы можете использовать центр администрирования Microsoft 365 для настройки и настройки [Разделы.](topic-experiences-overview.md)</span><span class="sxs-lookup"><span data-stu-id="975c2-104">You can use the Microsoft 365 admin center to set up and configure [Topics](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="975c2-105">Важно спланировать оптимальный способ настройки и настройки тем в среде.</span><span class="sxs-lookup"><span data-stu-id="975c2-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="975c2-106">Прежде чем приступить к процедурам в этой статье, ознакомьтесь с разделом [Plan for Microsoft Viva Topics.](plan-topic-experiences.md)</span><span class="sxs-lookup"><span data-stu-id="975c2-106">Be sure to read [Plan for Microsoft Viva Topics](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="975c2-107">Вы должны быть подписаны на [Viva Topics](https://www.microsoft.com/microsoft-viva/topics) и быть глобальным администратором или администратором SharePoint, чтобы получить доступ к центру администрирования Microsoft 365 и настроить Разделы.</span><span class="sxs-lookup"><span data-stu-id="975c2-107">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="975c2-108">Если вы настроили SharePoint для [управляемых устройств,](/sharepoint/control-access-from-unmanaged-devices)не забудьте настроить Разделы с управляемого устройства.</span><span class="sxs-lookup"><span data-stu-id="975c2-108">If you have configured SharePoint to [require managed devices](/sharepoint/control-access-from-unmanaged-devices), be sure to set up Topics from a managed device.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="975c2-109">Видеодемонстрация</span><span class="sxs-lookup"><span data-stu-id="975c2-109">Video demonstration</span></span>

<span data-ttu-id="975c2-110">В этом видео показан процесс настройки разделов в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="975c2-110">This video shows the process for setting up Topics in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="assign-licenses"></a><span data-ttu-id="975c2-111">Назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="975c2-111">Assign licenses</span></span>

<span data-ttu-id="975c2-112">Необходимо назначить лицензии пользователям, которые будут использовать Разделы.</span><span class="sxs-lookup"><span data-stu-id="975c2-112">You must assign licenses for the users who will be using Topics.</span></span> <span data-ttu-id="975c2-113">Только пользователи с лицензией могут видеть сведения по темам, включая основные моменты, карточки темы, страницы темы и центр тем.</span><span class="sxs-lookup"><span data-stu-id="975c2-113">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="975c2-114">Чтобы назначить лицензии, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="975c2-114">To assign licenses:</span></span>

1. <span data-ttu-id="975c2-115">В Центре администрирования Microsoft 365 в разделе **Пользователи**, щелкните **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="975c2-115">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="975c2-116">Выберите пользователей, которые необходимо лицензировать, и нажмите **кнопку Лицензии и приложения.**</span><span class="sxs-lookup"><span data-stu-id="975c2-116">Select the users that you want to license, and click **Licenses and apps**.</span></span>

3. <span data-ttu-id="975c2-117">В **соответствии с лицензиями** выберите **Разделы Viva**.</span><span class="sxs-lookup"><span data-stu-id="975c2-117">Under **Licenses**, select **Viva Topics**.</span></span>

4. <span data-ttu-id="975c2-118">В **приложениях** убедитесь, что Graph соединители поиск с **помощью Index (Viva Topics)** и **Viva Topics.**</span><span class="sxs-lookup"><span data-stu-id="975c2-118">Under **Apps**, make sure **Graph Connectors Search with Index (Viva Topics)** and **Viva Topics** are both selected.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="975c2-119">![Лицензии Microsoft Viva Topics в центре Microsoft 365 администрирования](../media/topic-experiences-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="975c2-119">![Microsoft Viva Topics licenses in the Microsoft 365 admin center](../media/topic-experiences-licenses.png)</span></span>

5. <span data-ttu-id="975c2-120">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="975c2-120">Click **Save changes**.</span></span>

<span data-ttu-id="975c2-121">После присвоения лицензий пользователям может потребоваться до часа.</span><span class="sxs-lookup"><span data-stu-id="975c2-121">It may take up to an hour for users to get access to Topics after the licenses are assigned.</span></span>

## <a name="set-up-topics"></a><span data-ttu-id="975c2-122">Настройка тем</span><span class="sxs-lookup"><span data-stu-id="975c2-122">Set up Topics</span></span>

<span data-ttu-id="975c2-123">Настройка Разделов</span><span class="sxs-lookup"><span data-stu-id="975c2-123">To set up Topics</span></span>

1. <span data-ttu-id="975c2-124">В центре [администрирования Microsoft 365](https://admin.microsoft.com) **настройка,** а затем просмотреть раздел Файлы **и контент.**</span><span class="sxs-lookup"><span data-stu-id="975c2-124">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="975c2-125">В разделе **Файлы и контент** нажмите **кнопку Подключение для получения знаний.**</span><span class="sxs-lookup"><span data-stu-id="975c2-125">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Подключение к знаниям](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="975c2-127">На странице **Подключение людей к знаниям** нажмите кнопку **Начало** ходить по процессу установки.</span><span class="sxs-lookup"><span data-stu-id="975c2-127">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![Начало работы](../media/k-get-started.png) 

4. <span data-ttu-id="975c2-129">На странице **Выбор способов поиска тем Viva Topics** вы настроите обнаружение темы.</span><span class="sxs-lookup"><span data-stu-id="975c2-129">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="975c2-130">В разделе **Выбор SharePoint** темы выберите, какие SharePoint будут обхода в качестве источников для ваших тем во время обнаружения.</span><span class="sxs-lookup"><span data-stu-id="975c2-130">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="975c2-131">Варианты:</span><span class="sxs-lookup"><span data-stu-id="975c2-131">Choose from:</span></span>
    - <span data-ttu-id="975c2-132">**Все сайты**: все сайты SharePoint в организации.</span><span class="sxs-lookup"><span data-stu-id="975c2-132">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="975c2-133">К ним относятся существующие и будущие сайты.</span><span class="sxs-lookup"><span data-stu-id="975c2-133">This includes current and future sites.</span></span>
    - <span data-ttu-id="975c2-134">**Все, кроме выбранных сайтов:** введите имена сайтов, которые необходимо исключить.</span><span class="sxs-lookup"><span data-stu-id="975c2-134">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="975c2-135">Вы также можете загрузить список сайтов, которые вы хотите отказаться от обнаружения.</span><span class="sxs-lookup"><span data-stu-id="975c2-135">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="975c2-136">Сайты, созданные в будущем, будут включены в качестве источников для обнаружения тем.</span><span class="sxs-lookup"><span data-stu-id="975c2-136">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="975c2-137">**Только выбранные сайты:** введите имена сайтов, которые вы хотите включить.</span><span class="sxs-lookup"><span data-stu-id="975c2-137">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="975c2-138">Вы также можете загрузить список сайтов.</span><span class="sxs-lookup"><span data-stu-id="975c2-138">You can also upload a list of sites.</span></span> <span data-ttu-id="975c2-139">Сайты, созданные в будущем, не будут включены в качестве источников для обнаружения тем.</span><span class="sxs-lookup"><span data-stu-id="975c2-139">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="975c2-140">**Без сайтов**: сайты SharePoint включены не будут.</span><span class="sxs-lookup"><span data-stu-id="975c2-140">**No sites**: Do not include any SharePoint sites.</span></span>

    ![Выбор способов поиска тем](../media/ksetup1.png) 
   
5. <span data-ttu-id="975c2-142">В разделе **Исключить темы по имени** можно добавить имена тем, которые необходимо исключить из обнаружения тем.</span><span class="sxs-lookup"><span data-stu-id="975c2-142">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="975c2-143">Используйте этот параметр, чтобы предотвратить включение конфиденциальной информации в качестве тем.</span><span class="sxs-lookup"><span data-stu-id="975c2-143">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="975c2-144">Доступны следующие варианты.</span><span class="sxs-lookup"><span data-stu-id="975c2-144">The options are:</span></span>
    - <span data-ttu-id="975c2-145">**Не исключайте любые темы**</span><span class="sxs-lookup"><span data-stu-id="975c2-145">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="975c2-146">**Исключить темы по имени**</span><span class="sxs-lookup"><span data-stu-id="975c2-146">**Exclude topics by name**</span></span>

    ![Исключение тем](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="975c2-148">(Руководители знаний также могут исключать темы в центре тем после обнаружения.)</span><span class="sxs-lookup"><span data-stu-id="975c2-148">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="975c2-149">Как исключить темы по имени</span><span class="sxs-lookup"><span data-stu-id="975c2-149">How to exclude topics by name</span></span>    

    <span data-ttu-id="975c2-150">Если необходимо исключить темы, после выбора разделов Exclude по имени скачайте шаблон .csv и обновите его списком тем, которые необходимо исключить из результатов обнаружения.</span><span class="sxs-lookup"><span data-stu-id="975c2-150">If you need to exclude topics, after selecting **Exclude topics by name**, download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![Исключение тем в шаблоне CSV](../media/exclude-topics-csv.png) 

    <span data-ttu-id="975c2-152">В шаблоне CSV введите следующие сведения о темах, которые хотите исключить:</span><span class="sxs-lookup"><span data-stu-id="975c2-152">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="975c2-153">**Имя**: введите имя темы, которую хотите исключить.</span><span class="sxs-lookup"><span data-stu-id="975c2-153">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="975c2-154">Это можно сделать двумя способами:</span><span class="sxs-lookup"><span data-stu-id="975c2-154">There are two ways to do this:</span></span>
        - <span data-ttu-id="975c2-155">Точное совпадение. Вы можете включить точное имя или аббревиатура (например, *Contoso* или *ATL).*</span><span class="sxs-lookup"><span data-stu-id="975c2-155">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="975c2-156">Частичное совпадение. Вы можете исключить все темы, в них есть определенное слово.</span><span class="sxs-lookup"><span data-stu-id="975c2-156">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="975c2-157">Например, *дуга* исключает все темы со *словом* дуга в нем, такие как круг *дуги,* сварка плазменной дуги или *дуга обучения.* Обратите внимание, что не исключены темы, в которые текст включен как часть слова, например *Архитектура.*</span><span class="sxs-lookup"><span data-stu-id="975c2-157">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="975c2-158">**Означает (необязательно).** Если вы хотите исключить аббревиатура, введите слова, которые обозначает аббревиатура.</span><span class="sxs-lookup"><span data-stu-id="975c2-158">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="975c2-159">**MatchType-Exact/Partial**. Введите, было ли вписано имя *точным* или *частичным типом* совпадения.</span><span class="sxs-lookup"><span data-stu-id="975c2-159">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="975c2-160">После завершения и сэкономленного файла .csv выберите **Просмотр,** чтобы найти и выбрать его.</span><span class="sxs-lookup"><span data-stu-id="975c2-160">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="975c2-161">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="975c2-161">Select **Next**.</span></span>

6. <span data-ttu-id="975c2-162">На Кто **можно увидеть темы** и где они могут видеть их страницу, вы настроите видимость темы.</span><span class="sxs-lookup"><span data-stu-id="975c2-162">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="975c2-163">В **Кто** можно увидеть параметры тем, вы выбираете, у кого будет доступ к деталям темы, например к выделенным темам, карточкам тем, ответам на темы в поиске и страницам тем.</span><span class="sxs-lookup"><span data-stu-id="975c2-163">In the **Who can see topics** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="975c2-164">Можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="975c2-164">You can select:</span></span>
    - <span data-ttu-id="975c2-165">**Все в моей организации**</span><span class="sxs-lookup"><span data-stu-id="975c2-165">**Everyone in my organization**</span></span>
    - <span data-ttu-id="975c2-166">**Только выбранные люди или группы безопасности**</span><span class="sxs-lookup"><span data-stu-id="975c2-166">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="975c2-167">**Никто**</span><span class="sxs-lookup"><span data-stu-id="975c2-167">**No one**</span></span>

    ![Кто см. разделы](../media/ksetup2.png)  

    > [!Note] 
    > <span data-ttu-id="975c2-169">Хотя этот параметр позволяет выбрать любого пользователя в организации, просматривать темы смогут только пользователи, которым назначены лицензии на раздел Experiences.</span><span class="sxs-lookup"><span data-stu-id="975c2-169">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="975c2-170">На странице **Разрешения для управления темами** вы выбираете, кто сможет создавать, редактировать или управлять темами.</span><span class="sxs-lookup"><span data-stu-id="975c2-170">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="975c2-171">В разделе Кто можно создавать и **редактировать** разделы, можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="975c2-171">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="975c2-172">**Все в моей организации**</span><span class="sxs-lookup"><span data-stu-id="975c2-172">**Everyone in my organization**</span></span>
    - <span data-ttu-id="975c2-173">**Только выбранные люди или группы безопасности**</span><span class="sxs-lookup"><span data-stu-id="975c2-173">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="975c2-174">**Никто**</span><span class="sxs-lookup"><span data-stu-id="975c2-174">**No one**</span></span>

    ![Разрешения для управления темами, которые могут создавать и редактировать темы](../media/ksetup3.png) 

8. <span data-ttu-id="975c2-176">В разделе **Кто тем можно** выбрать:</span><span class="sxs-lookup"><span data-stu-id="975c2-176">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="975c2-177">**Все в моей организации**</span><span class="sxs-lookup"><span data-stu-id="975c2-177">**Everyone in my organization**</span></span>
    - <span data-ttu-id="975c2-178">**Только выбранные люди или группы безопасности**</span><span class="sxs-lookup"><span data-stu-id="975c2-178">**Only selected people or security groups**</span></span>

    ![Разрешения для управления темами](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="975c2-180">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="975c2-180">Select **Next**.</span></span>

9. <span data-ttu-id="975c2-181">На странице **Создание центра тем** можно создать сайт центра тем, на котором можно просматривать страницы тем и управлять темами.</span><span class="sxs-lookup"><span data-stu-id="975c2-181">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="975c2-182">В поле **имя сайта** введите имя для центра темы.</span><span class="sxs-lookup"><span data-stu-id="975c2-182">In the **Site name** box, type a name for your topic center.</span></span> <span data-ttu-id="975c2-183">Вы можете дополнительно ввести краткое описание в поле **Описание.**</span><span class="sxs-lookup"><span data-stu-id="975c2-183">You can optionally type a short description in the **Description** box.</span></span> 

   <span data-ttu-id="975c2-184">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="975c2-184">Select **Next**.</span></span>

   ![Создание Центра знаний](../media/ksetup4.png)  

10. <span data-ttu-id="975c2-186">На странице **Проверка и завершение** можно просмотреть выбранный параметр и внести в него изменения.</span><span class="sxs-lookup"><span data-stu-id="975c2-186">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="975c2-187">Если выбор вас устраивает, нажмите кнопку **Активировать**.</span><span class="sxs-lookup"><span data-stu-id="975c2-187">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="975c2-188">**Активированная страница Viva Topics** будет отображаться, что подтверждает, что система теперь начнет анализировать выбранные сайты для тем и создавать сайт центра тем.</span><span class="sxs-lookup"><span data-stu-id="975c2-188">The **Viva Topics activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the topic center site.</span></span> <span data-ttu-id="975c2-189">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="975c2-189">Select **Done**.</span></span>

12. <span data-ttu-id="975c2-190">Вы будете возвращены на страницу Подключение **на страницу знаний.**</span><span class="sxs-lookup"><span data-stu-id="975c2-190">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="975c2-191">На этой странице можно выбрать **Управлять**, чтобы внести изменения в параметры настройки.</span><span class="sxs-lookup"><span data-stu-id="975c2-191">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Параметры применяется](../media/ksetup7.png)    

<span data-ttu-id="975c2-193">Обратите внимание, что при первом открытии темы может потребоваться до двух недель, чтобы все предложенные темы появились в представлении Manage Topics.</span><span class="sxs-lookup"><span data-stu-id="975c2-193">Note that the first time topic discovery is enabled, it may take up to two weeks for all suggested topics to appear in the Manage Topics view.</span></span> <span data-ttu-id="975c2-194">Обнаружение темы продолжается по мере того, как будут сделаны новые материалы или обновления контента.</span><span class="sxs-lookup"><span data-stu-id="975c2-194">Topic discovery continues as new content or updates to content are made.</span></span> <span data-ttu-id="975c2-195">В вашей организации обычно имеются колебания числа предлагаемых тем, поскольку Viva Topics оценивает новые сведения.</span><span class="sxs-lookup"><span data-stu-id="975c2-195">It is normal to have fluctuations in the number of suggested topics in your organization as Viva Topics evaluates new information.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="975c2-196">Управление опытом темы</span><span class="sxs-lookup"><span data-stu-id="975c2-196">Manage topic experiences</span></span>

<span data-ttu-id="975c2-197">После настройки Разделы можно изменить параметры, выбранные во время установки в [центре администрирования Microsoft 365.](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)</span><span class="sxs-lookup"><span data-stu-id="975c2-197">Once you have set up Topics, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="975c2-198">См. следующие справочные материалы:</span><span class="sxs-lookup"><span data-stu-id="975c2-198">See the following references:</span></span>

- [<span data-ttu-id="975c2-199">Управление обнаружением тем в Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="975c2-199">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="975c2-200">Управление обзором тем в Разделах Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="975c2-200">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="975c2-201">Управление разрешениями тем в Разделах Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="975c2-201">Manage topic permissions in Microsoft Viva Topics</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="975c2-202">Изменение имени центра темы в Разделе Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="975c2-202">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="975c2-203">См. также</span><span class="sxs-lookup"><span data-stu-id="975c2-203">See also</span></span>

[<span data-ttu-id="975c2-204">Обзор опытом темы</span><span class="sxs-lookup"><span data-stu-id="975c2-204">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
