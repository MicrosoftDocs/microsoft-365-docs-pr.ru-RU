---
title: Планирование тем Microsoft Viva
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Узнайте, как планировать планирование для Microsoft Viva Topics
ms.openlocfilehash: 19baf8bdcfdd1fe38d64e3c2f259ace1ceab5a4b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925980"
---
# <a name="plan-for-microsoft-viva-topics"></a><span data-ttu-id="dc7a1-103">Планирование тем Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="dc7a1-103">Plan for Microsoft Viva Topics</span></span>

<span data-ttu-id="dc7a1-104">Вы управляете темами в организации.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="dc7a1-105">Ваши решения по планированию для Topics гарантируют, что для пользователей будут показаны высококачественные темы, и они будут иметь правильные разрешения на потребление и вклад знаний.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-105">Your planning decisions for Topics ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="dc7a1-106">В этой статье мы рассмотрим эти решения по планированию:</span><span class="sxs-lookup"><span data-stu-id="dc7a1-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="dc7a1-107">Какие сайты SharePoint нужно обходить по темам</span><span class="sxs-lookup"><span data-stu-id="dc7a1-107">Which SharePoint sites you want to crawl for topics</span></span>
- <span data-ttu-id="dc7a1-108">Какие темы, если таково, необходимо исключить из опытом темы</span><span class="sxs-lookup"><span data-stu-id="dc7a1-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="dc7a1-109">Какие пользователи нужно сделать темы видимыми</span><span class="sxs-lookup"><span data-stu-id="dc7a1-109">Which users you want to make topics visible to</span></span>
- <span data-ttu-id="dc7a1-110">Какие пользователи вы хотите предоставить разрешения на управление темами в центре тем</span><span class="sxs-lookup"><span data-stu-id="dc7a1-110">Which users you want to give permissions to manage topics in the topic center</span></span>
- <span data-ttu-id="dc7a1-111">Какие пользователи вы хотите предоставить разрешения на создание или редактирование тем в центре тем</span><span class="sxs-lookup"><span data-stu-id="dc7a1-111">Which users you want to give permissions to create or edit topics in the topic center</span></span>
- <span data-ttu-id="dc7a1-112">Какое имя нужно дать центру тем</span><span class="sxs-lookup"><span data-stu-id="dc7a1-112">What name you want to give your topic center</span></span>

<span data-ttu-id="dc7a1-113">Безопасность и конфиденциальность данных соблюдаются, а опыт темы не предоставляет пользователям дополнительный доступ к файлам, на которые они не имеют прав.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="dc7a1-114">В процессе планирования рекомендуется также ознакомиться с безопасностью и конфиденциальностью [Microsoft Viva Topics.](topic-experiences-security-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="dc7a1-114">We recommend you also read [Microsoft Viva Topics security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

## <a name="requirements"></a><span data-ttu-id="dc7a1-115">Требования</span><span class="sxs-lookup"><span data-stu-id="dc7a1-115">Requirements</span></span>

<span data-ttu-id="dc7a1-116">Вы должны [подписаться на Viva Topics](https://www.microsoft.com/microsoft-viva/topics) и быть глобальным администратором или администратором SharePoint, чтобы получить доступ к центру администрирования Microsoft 365 и настроить Разделы.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-116">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="dc7a1-117">Всем пользователям, которые собираются использовать Разделы, требуется **лицензия "Опыты по** темам".</span><span class="sxs-lookup"><span data-stu-id="dc7a1-117">All users who are going to use Topics require a **Topic Experiences** license.</span></span> <span data-ttu-id="dc7a1-118">Назначение лицензий распространяется на [раздел Настройка Microsoft Viva Topics](set-up-topic-experiences.md).</span><span class="sxs-lookup"><span data-stu-id="dc7a1-118">Assigning licenses is covered in [Set up Microsoft Viva Topics](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="dc7a1-119">Обнаружение темы</span><span class="sxs-lookup"><span data-stu-id="dc7a1-119">Topic discovery</span></span>

<span data-ttu-id="dc7a1-120">Параметры обнаружения тем указывают, какие сайты SharePoint используются в качестве источников для тем.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-120">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="dc7a1-121">Вы можете включить все сайты SharePoint, определенный список сайтов или нет сайтов.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-121">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="dc7a1-122">Мы рекомендуем выбрать все сайты, чтобы в разделе было обнаружено большое количество хороших тем для пользователей.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-122">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="dc7a1-123">При настройках Разделы можно выбрать из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="dc7a1-123">When you set up Topics, you can choose from the following options:</span></span>

- <span data-ttu-id="dc7a1-124">**Все сайты.** Все сайты SharePoint в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-124">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="dc7a1-125">Это включает текущие и будущие сайты.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-125">This includes current and future sites.</span></span>
- <span data-ttu-id="dc7a1-126">**Все, кроме выбранных сайтов:** все сайты, за исключением тех, которые вы указываете.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-126">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="dc7a1-127">Сайты, созданные в будущем, будут включены в качестве источников для обнаружения тем.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-127">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="dc7a1-128">**Только выбранные сайты:** Только сайты, которые вы указываете.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-128">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="dc7a1-129">Сайты, созданные в будущем, не будут включены в качестве источников для обнаружения тем.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="dc7a1-130">**Нет сайтов.** Не включай сайты SharePoint.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-130">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="dc7a1-131">Если вы выбираете **все,** кроме выбранных сайтов или только выбранных **сайтов,** вы можете загрузить файл csv со списком сайтов.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-131">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="dc7a1-132">Эти параметры полезны, если вы делаете пилотный проект и хотите включить ограниченное число сайтов для запуска.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-132">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="dc7a1-133">Вы можете скопировать шаблон CSV ниже:</span><span class="sxs-lookup"><span data-stu-id="dc7a1-133">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="dc7a1-134">Мы не рекомендуем выбирать  "Нет сайтов", так как это не позволяет автоматически создавать или обновлять темы.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-134">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="dc7a1-135">Однако этот параметр можно выбрать, если необходимо настроить Разделы, а затем добавить сайты позже.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-135">However, you can choose this option if you want to set up Topics and then add sites later.</span></span>

<span data-ttu-id="dc7a1-136">Рекомендуется создать процесс для пользователей или руководителей знаний, чтобы при необходимости в организации удалить отдельные сайты из-под обнаружения темы.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-136">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

### <a name="multi-geo"></a><span data-ttu-id="dc7a1-137">Поддержка нескольких регионов</span><span class="sxs-lookup"><span data-stu-id="dc7a1-137">Multi-geo</span></span>

<span data-ttu-id="dc7a1-138">Если ваша организация развернула [Microsoft 365 Multi-Geo,](/microsoft-365/enterprise/microsoft-365-multi-geo)центр темы размещен в центре расположения, и в качестве источников для тем доступны только сайты SharePoint в центральном расположении.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-138">If your organization has deployed [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo), the topic center is provisioned in the central location and only SharePoint sites in the central location are available to use as sources for topics.</span></span> <span data-ttu-id="dc7a1-139">(Если выбрать **все сайты,** Viva Topics будет использовать все сайты в центре расположения.)</span><span class="sxs-lookup"><span data-stu-id="dc7a1-139">(If you select **All sites**, Viva Topics will use all site in the central location.)</span></span>

<span data-ttu-id="dc7a1-140">Вся обработка и хранение контента в центре.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-140">All processing and storage of content is done in the central location.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="dc7a1-141">Разрешения пользователей</span><span class="sxs-lookup"><span data-stu-id="dc7a1-141">User permissions</span></span>

<span data-ttu-id="dc7a1-142">Разрешения пользователей, которые вы указываете, определяют, какие пользователи в организации взаимодействуют с темами и что они могут сделать.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-142">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

<span data-ttu-id="dc7a1-143">*Управление темами*</span><span class="sxs-lookup"><span data-stu-id="dc7a1-143">*Manage topics*</span></span>

<span data-ttu-id="dc7a1-144">Руководители знаний следит за качеством информации, ее структурой и другими лучшими практиками в организации.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-144">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="dc7a1-145">Они могут подтвердить и отклонить темы.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-145">They can confirm and reject topics.</span></span>

<span data-ttu-id="dc7a1-146">В то время как вы можете указать отдельных руководителей тем, мы рекомендуем создать группу безопасности (или использовать существующую), которая содержит людей, которые вы хотите быть менеджерами знаний.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-146">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="dc7a1-147">Эту группу безопасности можно указать во время процесса настройки.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-147">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="dc7a1-148">*Создание и редактирование тем*</span><span class="sxs-lookup"><span data-stu-id="dc7a1-148">*Create and edit topics*</span></span>

<span data-ttu-id="dc7a1-149">Участники темы — это эксперты по темам и чемпионам в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-149">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="dc7a1-150">Они могут создавать и редактировать темы.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-150">They can create and edit topics.</span></span> 

<span data-ttu-id="dc7a1-151">Мы рекомендуем разрешить всем пользователям в организации создавать и редактировать темы, так как опыт работы с темой лучше всего работает, когда все пользователи могут обмениваться информацией.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-151">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="dc7a1-152">Если вы хотите ограничить создание и редактирование тем определенными людьми или группами, создайте группу безопасности для них и укажите ее в процессе настройки.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-152">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="dc7a1-153">Вы можете не разрешать никому вносить свой вклад в темы, однако это не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-153">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="dc7a1-154">Менеджеры знаний по-прежнему смогут редактировать и создавать темы, если вы выберете этот параметр.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-154">Knowledge managers will still be able to edit and create topics if you choose this option.</span></span>

<span data-ttu-id="dc7a1-155">*Зрители темы*</span><span class="sxs-lookup"><span data-stu-id="dc7a1-155">*Topic viewers*</span></span>

<span data-ttu-id="dc7a1-156">Зрители темы могут видеть сведения о страницах тем, результатах поиска и о выделении тем в контенте, например на страницах SharePoint.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-156">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="dc7a1-157">Пользователи могут видеть обнаруженные темы только при доступе к файлам и страницам, в которые была обнаружена тема.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-157">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="dc7a1-158">При настройке просмотра темы можно выбрать из:</span><span class="sxs-lookup"><span data-stu-id="dc7a1-158">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="dc7a1-159">**Все в моей организации**</span><span class="sxs-lookup"><span data-stu-id="dc7a1-159">**Everyone in my organization**</span></span>
- <span data-ttu-id="dc7a1-160">**Только выбранные люди или группы безопасности**</span><span class="sxs-lookup"><span data-stu-id="dc7a1-160">**Only selected people or security groups**</span></span>
- <span data-ttu-id="dc7a1-161">**Никто**</span><span class="sxs-lookup"><span data-stu-id="dc7a1-161">**No one**</span></span>

<span data-ttu-id="dc7a1-162">Мы рекомендуем **всем в моей** организации, но если вы делаете пилот, вы можете выбрать только выбранные люди или группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-162">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="dc7a1-163">Вы также можете выбрать **No one,** если вы хотите настроить Разделы, но пока не разрешаете пользователям видеть темы.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-163">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span></span> <span data-ttu-id="dc7a1-164">(Менеджеры знаний по-прежнему будут иметь доступ, чтобы разрешить им просматривать темы и помогать в принятии решения о широкой доступности тем.)</span><span class="sxs-lookup"><span data-stu-id="dc7a1-164">(Knowledge managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="dc7a1-165">Правила знаний</span><span class="sxs-lookup"><span data-stu-id="dc7a1-165">Knowledge rules</span></span>

<span data-ttu-id="dc7a1-166">Как администратор вы можете исключить некоторые темы из опытом темы.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-166">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="dc7a1-167">Это полезно, если вы хотите, чтобы конфиденциальные данные не появлялись в темах.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-167">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="dc7a1-168">Хотя руководители знаний могут исключать темы в центре тем, темы, исключенные администратором, даже не видны руководителям знаний.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-168">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="dc7a1-169">(Менеджеры знаний также могут удалять темы в центре тем после обнаружения.)</span><span class="sxs-lookup"><span data-stu-id="dc7a1-169">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="dc7a1-170">Если вы хотите исключить темы на уровне администратора, необходимо добавить их в файл csv и загрузить файл.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-170">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="dc7a1-171">Это можно сделать во время установки или позже.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-171">You can do this during setup or later.</span></span>

<span data-ttu-id="dc7a1-172">Файл .csv должен содержать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="dc7a1-172">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="dc7a1-173">**Имя.** Введите имя темы, которая вы хотите исключить.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-173">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="dc7a1-174">Это можно сделать двумя способами:</span><span class="sxs-lookup"><span data-stu-id="dc7a1-174">There are two ways to do this:</span></span>
- <span data-ttu-id="dc7a1-175">**MatchType-Exact/Partial**. Введите, было ли вписано имя *точным* или *частичным типом* совпадения.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-175">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="dc7a1-176">Точное совпадение. Вы можете включить точное имя или аббревиатура (например, *Contoso* или *ATL).*</span><span class="sxs-lookup"><span data-stu-id="dc7a1-176">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="dc7a1-177">Частичное совпадение. Вы можете исключить все темы, в них есть определенное слово.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-177">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="dc7a1-178">Например, *дуга* исключает все темы со *словом* дуга в нем, такие как круг *дуги,* сварка плазменной дуги или *дуга обучения.* Обратите внимание, что не исключены темы, в которые текст включен как часть слова, например *Архитектура.*</span><span class="sxs-lookup"><span data-stu-id="dc7a1-178">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="dc7a1-179">**Означает (необязательно)**: (Также известный как *расширение)* Если вы хотите исключить аббревиатура, введите слова, которые обозначает аббревиатура.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-179">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![Исключение тем в шаблоне CSV](../media/exclude-topics-csv.png) 

<span data-ttu-id="dc7a1-181">Вы можете скопировать шаблон csv ниже:</span><span class="sxs-lookup"><span data-stu-id="dc7a1-181">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="dc7a1-182">Администрирование</span><span class="sxs-lookup"><span data-stu-id="dc7a1-182">Administration</span></span>

<span data-ttu-id="dc7a1-183">При настройке Разделы в рамках процесса настройки автоматически создается центр тем.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-183">When you set up Topics, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="dc7a1-184">Подумайте, как назвать центр темы и каким должен быть URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-184">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="dc7a1-185">В процессе настройки можно установить имя и URL-адрес, а затем изменить имя (но не URL-адрес) в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-185">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="dc7a1-186">Вы можете иметь только один центр темы.</span><span class="sxs-lookup"><span data-stu-id="dc7a1-186">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="dc7a1-187">Контрольный список установки</span><span class="sxs-lookup"><span data-stu-id="dc7a1-187">Setup checklist</span></span>

<span data-ttu-id="dc7a1-188">При настройке опытом работы с темами вам будут необходимы следующие элементы при пройме мастера настройки:</span><span class="sxs-lookup"><span data-stu-id="dc7a1-188">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="dc7a1-189">Список сайтов, которые необходимо включить или исключить, если не включать все сайты для обнаружения темы</span><span class="sxs-lookup"><span data-stu-id="dc7a1-189">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="dc7a1-190">Группа безопасности для зрителей тем, если не позволяет всем пользователям просматривать темы</span><span class="sxs-lookup"><span data-stu-id="dc7a1-190">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="dc7a1-191">Группа безопасности для участников темы, если не позволяет всем пользователям создавать и редактировать темы</span><span class="sxs-lookup"><span data-stu-id="dc7a1-191">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="dc7a1-192">Группа безопасности для руководителей тематических знаний, если не позволяет всем пользователям управлять темами</span><span class="sxs-lookup"><span data-stu-id="dc7a1-192">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="dc7a1-193">Список конфиденциальных тем, которые необходимо исключить из обнаружения темы</span><span class="sxs-lookup"><span data-stu-id="dc7a1-193">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="dc7a1-194">Имя сайта центра темы</span><span class="sxs-lookup"><span data-stu-id="dc7a1-194">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="dc7a1-195">См. также</span><span class="sxs-lookup"><span data-stu-id="dc7a1-195">See also</span></span>

[<span data-ttu-id="dc7a1-196">Настройка тем</span><span class="sxs-lookup"><span data-stu-id="dc7a1-196">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="dc7a1-197">Управление обнаружением тем в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dc7a1-197">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="dc7a1-198">Управление обзором тем в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dc7a1-198">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="dc7a1-199">Управление разрешениями тем в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dc7a1-199">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="dc7a1-200">Изменение имени центра темы в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dc7a1-200">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
