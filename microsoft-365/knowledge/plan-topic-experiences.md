---
title: Планирование тем в Microsoft 365
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
description: Узнайте, как планировать темы в Microsoft 365
ms.openlocfilehash: 153937cf6bc4a12f0a27866204b2286c343ddf55
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668229"
---
# <a name="plan-topic-experiences-in-microsoft-365"></a><span data-ttu-id="73809-103">Планирование тем в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="73809-103">Plan topic experiences in Microsoft 365</span></span>

<span data-ttu-id="73809-104">Вы управляете темами работы в организации.</span><span class="sxs-lookup"><span data-stu-id="73809-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="73809-105">Решения по планированию для работы с темами гарантируют, что для пользователей будут показаны темы высокого качества и у них есть необходимые разрешения на использование и вклад знаний.</span><span class="sxs-lookup"><span data-stu-id="73809-105">Your planning decisions for topic experiences ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="73809-106">В этой статье мы рассмотрим эти решения по планированию:</span><span class="sxs-lookup"><span data-stu-id="73809-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="73809-107">Какие сайты SharePoint необходимо обходить для разделов.</span><span class="sxs-lookup"><span data-stu-id="73809-107">Which SharePoint sites you want to crawl for topics.</span></span>
- <span data-ttu-id="73809-108">Какие темы нужно исключить из тем</span><span class="sxs-lookup"><span data-stu-id="73809-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="73809-109">Для каких пользователей нужно сделать темы видимыми.</span><span class="sxs-lookup"><span data-stu-id="73809-109">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="73809-110">Какие пользователи вы хотите предоставить разрешения на управление темами в центре тем.</span><span class="sxs-lookup"><span data-stu-id="73809-110">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="73809-111">Какие пользователи вы хотите предоставить разрешения на создание или редактирование разделов в центре тем.</span><span class="sxs-lookup"><span data-stu-id="73809-111">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="73809-112">Имя центра тем.</span><span class="sxs-lookup"><span data-stu-id="73809-112">What name you want to give your topic center.</span></span>

<span data-ttu-id="73809-113">Безопасность и конфиденциальность ваших данных соблюдаются, а темы не предоставляет пользователям дополнительный доступ к файлам, на которые у них нет прав.</span><span class="sxs-lookup"><span data-stu-id="73809-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="73809-114">Мы также рекомендуем ознакомиться с [разделом "Вопросы безопасности и конфиденциальности"](topic-experiences-security-privacy.md) в процессе планирования.</span><span class="sxs-lookup"><span data-stu-id="73809-114">We recommend you also read [Topic experiences security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

## <a name="requirements"></a><span data-ttu-id="73809-115">Требования</span><span class="sxs-lookup"><span data-stu-id="73809-115">Requirements</span></span>

<span data-ttu-id="73809-116">Чтобы получить доступ к Центру администрирования Microsoft 365 и настроить темы, необходимо быть глобальным администратором или администратором SharePoint.</span><span class="sxs-lookup"><span data-stu-id="73809-116">You must be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up topic experiences.</span></span>

<span data-ttu-id="73809-117">Всем пользователям, которые будут использовать тематические опытом, требуется **лицензия "Опыт работы с** разделами".</span><span class="sxs-lookup"><span data-stu-id="73809-117">All users who are going to use topic experiences require a **Topic Experiences** license.</span></span> <span data-ttu-id="73809-118">Назначение лицензий освещается в разделе ["Настройка тем".](set-up-topic-experiences.md)</span><span class="sxs-lookup"><span data-stu-id="73809-118">Assigning licenses is covered in [Set up topic experiences](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="73809-119">Обнаружение тем</span><span class="sxs-lookup"><span data-stu-id="73809-119">Topic discovery</span></span>

<span data-ttu-id="73809-120">Параметры обнаружения тем указывают, какие сайты SharePoint используются в качестве источников для тем.</span><span class="sxs-lookup"><span data-stu-id="73809-120">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="73809-121">Вы можете включить все сайты SharePoint, определенный список сайтов или нет сайтов.</span><span class="sxs-lookup"><span data-stu-id="73809-121">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="73809-122">Рекомендуется выбрать все сайты, чтобы в темах можно было найти большое количество интересных тем для пользователей.</span><span class="sxs-lookup"><span data-stu-id="73809-122">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="73809-123">При настройках тем можно выбрать один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="73809-123">When you set up topic experiences, you can choose from the following options:</span></span>

- <span data-ttu-id="73809-124">**Все сайты**: все сайты SharePoint в организации.</span><span class="sxs-lookup"><span data-stu-id="73809-124">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="73809-125">Это относится к текущим и будущим сайтам.</span><span class="sxs-lookup"><span data-stu-id="73809-125">This includes current and future sites.</span></span>
- <span data-ttu-id="73809-126">**Все, кроме выбранных сайтов:** все сайты, кроме тех, которые вы указали.</span><span class="sxs-lookup"><span data-stu-id="73809-126">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="73809-127">Сайты, созданные в будущем, будут включены в качестве источников для обнаружения тем.</span><span class="sxs-lookup"><span data-stu-id="73809-127">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="73809-128">**Только выбранные сайты:** только сайты, которые вы указали.</span><span class="sxs-lookup"><span data-stu-id="73809-128">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="73809-129">Сайты, созданные в будущем, не будут включены в качестве источников для обнаружения тем.</span><span class="sxs-lookup"><span data-stu-id="73809-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="73809-130">**Нет сайтов:** не включать сайты SharePoint.</span><span class="sxs-lookup"><span data-stu-id="73809-130">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="73809-131">Если выбран вариант **"Все",** за исключением выбранных сайтов или только выбранных **сайтов,** можно отправить CSV-файл со списком сайтов.</span><span class="sxs-lookup"><span data-stu-id="73809-131">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="73809-132">Эти параметры полезны, если вы делаете пилотный проект и хотите включить ограниченное количество сайтов для запуска.</span><span class="sxs-lookup"><span data-stu-id="73809-132">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="73809-133">Шаблон CSV можно скопировать ниже:</span><span class="sxs-lookup"><span data-stu-id="73809-133">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="73809-134">Мы не рекомендуем выбирать "Нет **сайтов",** так как это предотвращает автоматическое создания или обновления тем.</span><span class="sxs-lookup"><span data-stu-id="73809-134">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="73809-135">Однако этот параметр можно выбрать, если вы хотите настроить возможности тем, а затем добавить сайты позже.</span><span class="sxs-lookup"><span data-stu-id="73809-135">However, you can choose this option if you want to set up topic experiences and then add sites later.</span></span>

<span data-ttu-id="73809-136">Мы рекомендуем создать процесс для пользователей или менеджеров знаний, чтобы запросить удаление отдельных сайтов из обнаружения тем, если это необходимо в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="73809-136">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="73809-137">Разрешения пользователей</span><span class="sxs-lookup"><span data-stu-id="73809-137">User permissions</span></span>

<span data-ttu-id="73809-138">Разрешения пользователей, которые вы указываете, определяют, какие пользователи в организации взаимодействуют с темами и что они могут делать.</span><span class="sxs-lookup"><span data-stu-id="73809-138">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

<span data-ttu-id="73809-139">*Управление темами*</span><span class="sxs-lookup"><span data-stu-id="73809-139">*Manage topics*</span></span>

<span data-ttu-id="73809-140">Менеджеры по знаниям следит за качеством информации, ее структурой и другими лучшими методиками в организации.</span><span class="sxs-lookup"><span data-stu-id="73809-140">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="73809-141">Они могут подтверждать и отклонить разделы.</span><span class="sxs-lookup"><span data-stu-id="73809-141">They can confirm and reject topics.</span></span>

<span data-ttu-id="73809-142">Вы можете указать отдельных руководителей тем, но мы рекомендуем создать группу безопасности (или использовать существующую), в которую входят люди, которые вы хотите быть менеджерами знаний.</span><span class="sxs-lookup"><span data-stu-id="73809-142">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="73809-143">Эту группу безопасности можно указать в процессе установки.</span><span class="sxs-lookup"><span data-stu-id="73809-143">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="73809-144">*Создание и редактирование разделов*</span><span class="sxs-lookup"><span data-stu-id="73809-144">*Create and edit topics*</span></span>

<span data-ttu-id="73809-145">Участники темы — это специалисты по темам и эксперты по темам в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="73809-145">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="73809-146">Они могут создавать и редактировать разделы.</span><span class="sxs-lookup"><span data-stu-id="73809-146">They can create and edit topics.</span></span> 

<span data-ttu-id="73809-147">Мы рекомендуем разрешить всем пользователям в организации создавать и редактировать разделы, так как темы лучше всего работают, когда все пользователи могут обмениваться информацией.</span><span class="sxs-lookup"><span data-stu-id="73809-147">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="73809-148">Если вы хотите ограничить создание и редактирование тем определенными людьми или группами, создайте группу безопасности для них и укажите ее в процессе настройки.</span><span class="sxs-lookup"><span data-stu-id="73809-148">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="73809-149">Вы можете не разрешать кому-либо вносить свой вклад в темы, но это не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="73809-149">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="73809-150">Менеджеры по знаниям по-прежнему смогут редактировать и создавать темы.</span><span class="sxs-lookup"><span data-stu-id="73809-150">Knowledge managers will still be able to edit and create topics.</span></span>

<span data-ttu-id="73809-151">*Посетители тем*</span><span class="sxs-lookup"><span data-stu-id="73809-151">*Topic viewers*</span></span>

<span data-ttu-id="73809-152">Посетители тем могут видеть информацию на страницах тем, в результатах поиска и при выделении тем в содержимом, например на страницах SharePoint.</span><span class="sxs-lookup"><span data-stu-id="73809-152">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="73809-153">Пользователи могут видеть обнаруженные темы, только если у них есть доступ к файлам и страницам, в которые была обнаружена тема.</span><span class="sxs-lookup"><span data-stu-id="73809-153">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="73809-154">При настройке пользователей тем можно выбрать один из вариантов:</span><span class="sxs-lookup"><span data-stu-id="73809-154">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="73809-155">**Все в моей организации**</span><span class="sxs-lookup"><span data-stu-id="73809-155">**Everyone in my organization**</span></span>
- <span data-ttu-id="73809-156">**Только выбранные люди или группы безопасности**</span><span class="sxs-lookup"><span data-stu-id="73809-156">**Only selected people or security groups**</span></span>
- <span data-ttu-id="73809-157">**Никто**</span><span class="sxs-lookup"><span data-stu-id="73809-157">**No one**</span></span>

<span data-ttu-id="73809-158">Мы рекомендуем **всем в моей организации,** но при пилотном проекте вы можете выбрать только выбранных людей или группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="73809-158">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="73809-159">Вы также можете выбрать **"Нет",** если вы хотите настроить темы, но пока не разрешаете пользователям видеть разделы.</span><span class="sxs-lookup"><span data-stu-id="73809-159">You can also choose **No one** if you want to set up topic experiences, but not allow people to see topics yet.</span></span> <span data-ttu-id="73809-160">(Руководители знаний по-прежнему смогут просматривать разделы и принимать решения о широкой доступности тем.)</span><span class="sxs-lookup"><span data-stu-id="73809-160">(Knowledge managers will still have access to allow them view the topics and help with the decision to make topic experiences broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="73809-161">Правила знаний</span><span class="sxs-lookup"><span data-stu-id="73809-161">Knowledge rules</span></span>

<span data-ttu-id="73809-162">Администратор может исключить определенные темы из тем.</span><span class="sxs-lookup"><span data-stu-id="73809-162">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="73809-163">Это полезно, если вы хотите, чтобы конфиденциальные данные не появлялись в темах.</span><span class="sxs-lookup"><span data-stu-id="73809-163">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="73809-164">Менеджеры по знаниям могут исключать темы в центре тем, но темы, исключенные администратором, даже не видны руководителям знаний.</span><span class="sxs-lookup"><span data-stu-id="73809-164">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="73809-165">(Менеджеры по знаниям также могут удалять разделы в центре тем после обнаружения.)</span><span class="sxs-lookup"><span data-stu-id="73809-165">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="73809-166">Чтобы исключить разделы на уровне администратора, необходимо добавить их в CSV-файл и отправить файл.</span><span class="sxs-lookup"><span data-stu-id="73809-166">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="73809-167">Это можно сделать во время установки или позднее.</span><span class="sxs-lookup"><span data-stu-id="73809-167">You can do this during setup or later.</span></span>

<span data-ttu-id="73809-168">CSV-файл должен содержать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="73809-168">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="73809-169">**Name**: Type the name of the topic you want to exclude.</span><span class="sxs-lookup"><span data-stu-id="73809-169">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="73809-170">Это можно сделать двумя способами:</span><span class="sxs-lookup"><span data-stu-id="73809-170">There are two ways to do this:</span></span>
- <span data-ttu-id="73809-171">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span><span class="sxs-lookup"><span data-stu-id="73809-171">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="73809-172">Точное совпадение: можно включить точное имя или аббревиатуру (например, *Contoso* или *ATL).*</span><span class="sxs-lookup"><span data-stu-id="73809-172">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="73809-173">Частичное совпадение: можно исключить все темы, в них есть определенное слово.</span><span class="sxs-lookup"><span data-stu-id="73809-173">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="73809-174">Например,  arc исключит все темы со словом *arc* в нем, такие как "Arc *circle",* *"Arc arc welding"* или *"Training arc".* Обратите внимание, что он не будет исключать темы, в которых текст включается как часть слова, например *"Архитектура".*</span><span class="sxs-lookup"><span data-stu-id="73809-174">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="73809-175">**Означает (необязательно)**: (также известное как *расширение).* Если вы хотите исключить акроним, введите слова, за которые стоит аббревиатура.</span><span class="sxs-lookup"><span data-stu-id="73809-175">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![Исключение разделов в шаблоне CSV](../media/exclude-topics-csv.png) 

<span data-ttu-id="73809-177">Шаблон CSV можно скопировать ниже:</span><span class="sxs-lookup"><span data-stu-id="73809-177">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="73809-178">Администрирование</span><span class="sxs-lookup"><span data-stu-id="73809-178">Administration</span></span>

<span data-ttu-id="73809-179">При настройке тем в процессе установки автоматически создается центр тем.</span><span class="sxs-lookup"><span data-stu-id="73809-179">When you set up topic experiences, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="73809-180">Подумайте о том, как вы хотите назвать центр темы и каким должен быть URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="73809-180">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="73809-181">В процессе настройки вы можете настроить имя и URL-адрес, а также изменить имя (но не URL-адрес) позже в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="73809-181">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="73809-182">У вас может быть только один центр тем.</span><span class="sxs-lookup"><span data-stu-id="73809-182">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="73809-183">Контрольный список программы установки</span><span class="sxs-lookup"><span data-stu-id="73809-183">Setup checklist</span></span>

<span data-ttu-id="73809-184">При настройке тем вам потребуется следующее:</span><span class="sxs-lookup"><span data-stu-id="73809-184">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="73809-185">Список сайтов, которые необходимо включить или исключить, если не включить все сайты для обнаружения тем</span><span class="sxs-lookup"><span data-stu-id="73809-185">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="73809-186">Группа безопасности для пользователей, просматривающих разделы, если не разрешается всем пользователям просматривать разделы</span><span class="sxs-lookup"><span data-stu-id="73809-186">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="73809-187">Группа безопасности для участников тем, если не разрешается всем пользователям создавать и редактировать разделы</span><span class="sxs-lookup"><span data-stu-id="73809-187">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="73809-188">Группа безопасности для руководителей знаний по теме, если не разрешает всем пользователям управлять темами</span><span class="sxs-lookup"><span data-stu-id="73809-188">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="73809-189">Список конфиденциальных разделов, которые необходимо исключить из обнаружения тем</span><span class="sxs-lookup"><span data-stu-id="73809-189">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="73809-190">Имя сайта центра тем</span><span class="sxs-lookup"><span data-stu-id="73809-190">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="73809-191">См. также</span><span class="sxs-lookup"><span data-stu-id="73809-191">See also</span></span>

[<span data-ttu-id="73809-192">Настройка тем</span><span class="sxs-lookup"><span data-stu-id="73809-192">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="73809-193">Управление обнаружением тем в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="73809-193">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="73809-194">Управление видимостью тем в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="73809-194">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="73809-195">Управление разрешениями тем в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="73809-195">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="73809-196">Изменение имени центра тем в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="73809-196">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
