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
ms.openlocfilehash: de7534ce58a7888ac822826ef4ef1b4934ed8cb1
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583116"
---
# <a name="plan-for-microsoft-viva-topics"></a><span data-ttu-id="e1639-103">Планирование тем Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="e1639-103">Plan for Microsoft Viva Topics</span></span>

<span data-ttu-id="e1639-104">Вы управляете темами в организации.</span><span class="sxs-lookup"><span data-stu-id="e1639-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="e1639-105">Ваши решения по планированию для Topics гарантируют, что для пользователей будут показаны высококачественные темы, и они будут иметь правильные разрешения на потребление и вклад знаний.</span><span class="sxs-lookup"><span data-stu-id="e1639-105">Your planning decisions for Topics ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="e1639-106">В этой статье мы рассмотрим эти решения по планированию:</span><span class="sxs-lookup"><span data-stu-id="e1639-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="e1639-107">Какие SharePoint для обхода тем</span><span class="sxs-lookup"><span data-stu-id="e1639-107">Which SharePoint sites you want to crawl for topics</span></span>
- <span data-ttu-id="e1639-108">Какие темы, если таково, необходимо исключить из опытом темы</span><span class="sxs-lookup"><span data-stu-id="e1639-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="e1639-109">Какие пользователи нужно сделать темы видимыми</span><span class="sxs-lookup"><span data-stu-id="e1639-109">Which users you want to make topics visible to</span></span>
- <span data-ttu-id="e1639-110">Какие пользователи вы хотите предоставить разрешения на управление темами в центре тем</span><span class="sxs-lookup"><span data-stu-id="e1639-110">Which users you want to give permissions to manage topics in the topic center</span></span>
- <span data-ttu-id="e1639-111">Какие пользователи вы хотите предоставить разрешения на создание или редактирование тем в центре тем</span><span class="sxs-lookup"><span data-stu-id="e1639-111">Which users you want to give permissions to create or edit topics in the topic center</span></span>
- <span data-ttu-id="e1639-112">Какое имя нужно дать центру тем</span><span class="sxs-lookup"><span data-stu-id="e1639-112">What name you want to give your topic center</span></span>

<span data-ttu-id="e1639-113">Безопасность и конфиденциальность данных соблюдаются, а опыт темы не предоставляет пользователям дополнительный доступ к файлам, на которые они не имеют прав.</span><span class="sxs-lookup"><span data-stu-id="e1639-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="e1639-114">В процессе планирования рекомендуется также ознакомиться с безопасностью и конфиденциальностью [Microsoft Viva Topics.](topic-experiences-security-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="e1639-114">We recommend you also read [Microsoft Viva Topics security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

<span data-ttu-id="e1639-115">Дополнительные сведения о технологии ИИ в Viva Topics читайте в материале Александрия в Microsoft Viva Topics: от больших данных [до больших знаний.](https://www.microsoft.com/research/blog/alexandria-in-microsoft-viva-topics-from-big-data-to-big-knowledge)</span><span class="sxs-lookup"><span data-stu-id="e1639-115">To learn more about the AI technology behind Viva Topics, read [Alexandria in Microsoft Viva Topics: from big data to big knowledge](https://www.microsoft.com/research/blog/alexandria-in-microsoft-viva-topics-from-big-data-to-big-knowledge).</span></span>

## <a name="requirements"></a><span data-ttu-id="e1639-116">Требования</span><span class="sxs-lookup"><span data-stu-id="e1639-116">Requirements</span></span>

<span data-ttu-id="e1639-117">Вы должны быть подписаны на [Viva Topics](https://www.microsoft.com/microsoft-viva/topics) и быть глобальным администратором или администратором SharePoint, чтобы получить доступ к центру администрирования Microsoft 365 и настроить Разделы.</span><span class="sxs-lookup"><span data-stu-id="e1639-117">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="e1639-118">Всем пользователям, которые собираются использовать Разделы, требуется **лицензия "Опыты по** темам".</span><span class="sxs-lookup"><span data-stu-id="e1639-118">All users who are going to use Topics require a **Topic Experiences** license.</span></span> <span data-ttu-id="e1639-119">Назначение лицензий распространяется на [раздел Настройка Microsoft Viva Topics](set-up-topic-experiences.md).</span><span class="sxs-lookup"><span data-stu-id="e1639-119">Assigning licenses is covered in [Set up Microsoft Viva Topics](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="e1639-120">Обнаружение темы</span><span class="sxs-lookup"><span data-stu-id="e1639-120">Topic discovery</span></span>

<span data-ttu-id="e1639-121">Параметры обнаружения тем указывают, какие сайты SharePoint используются в качестве источников для тем.</span><span class="sxs-lookup"><span data-stu-id="e1639-121">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="e1639-122">Можно включить все сайты SharePoint, определенный их список или не включать вовсе.</span><span class="sxs-lookup"><span data-stu-id="e1639-122">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="e1639-123">Мы рекомендуем выбрать все сайты, чтобы в разделе было обнаружено большое количество хороших тем для пользователей.</span><span class="sxs-lookup"><span data-stu-id="e1639-123">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="e1639-124">При настройке тем можно выбрать один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="e1639-124">When you set up Topics, you can choose from the following options:</span></span>

- <span data-ttu-id="e1639-125">**Все сайты**: все сайты SharePoint в организации.</span><span class="sxs-lookup"><span data-stu-id="e1639-125">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="e1639-126">К ним относятся существующие и будущие сайты.</span><span class="sxs-lookup"><span data-stu-id="e1639-126">This includes current and future sites.</span></span>
- <span data-ttu-id="e1639-127">**Все, кроме выбранных сайтов**: все сайты, кроме указанных.</span><span class="sxs-lookup"><span data-stu-id="e1639-127">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="e1639-128">Сайты, созданные в будущем, будут включены в качестве источников для обнаружения тем.</span><span class="sxs-lookup"><span data-stu-id="e1639-128">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="e1639-129">**Только выбранные сайты:** Только сайты, которые вы указываете.</span><span class="sxs-lookup"><span data-stu-id="e1639-129">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="e1639-130">Сайты, созданные в будущем, не будут включены в качестве источников для обнаружения тем.</span><span class="sxs-lookup"><span data-stu-id="e1639-130">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="e1639-131">**Без сайтов**: сайты SharePoint включены не будут.</span><span class="sxs-lookup"><span data-stu-id="e1639-131">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="e1639-132">Если вы выбираете **все,** кроме выбранных сайтов или только выбранных **сайтов,** вы можете загрузить .csv файл со списком сайтов.</span><span class="sxs-lookup"><span data-stu-id="e1639-132">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="e1639-133">Эти параметры полезны, если вы делаете пилотный проект и хотите включить ограниченное число сайтов для запуска.</span><span class="sxs-lookup"><span data-stu-id="e1639-133">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="e1639-134">Вы можете скопировать .csv ниже:</span><span class="sxs-lookup"><span data-stu-id="e1639-134">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="e1639-135">Мы не рекомендуем выбирать  "Нет сайтов", так как это не позволяет автоматически создавать или обновлять темы.</span><span class="sxs-lookup"><span data-stu-id="e1639-135">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="e1639-136">Однако этот параметр можно выбрать, если необходимо настроить Разделы, а затем добавить сайты позже.</span><span class="sxs-lookup"><span data-stu-id="e1639-136">However, you can choose this option if you want to set up Topics and then add sites later.</span></span>

<span data-ttu-id="e1639-137">Рекомендуется создать процесс для пользователей или руководителей знаний, чтобы при необходимости в организации удалить отдельные сайты из-под обнаружения темы.</span><span class="sxs-lookup"><span data-stu-id="e1639-137">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

### <a name="multi-geo"></a><span data-ttu-id="e1639-138">Поддержка нескольких регионов</span><span class="sxs-lookup"><span data-stu-id="e1639-138">Multi-geo</span></span>

<span data-ttu-id="e1639-139">Если ваша организация развернула [Microsoft 365-Geo,](/microsoft-365/enterprise/microsoft-365-multi-geo)центр темы будет размещен в центре расположения, и только SharePoint в центральном расположении доступны для использования в качестве источников для тем.</span><span class="sxs-lookup"><span data-stu-id="e1639-139">If your organization has deployed [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo), the topic center is provisioned in the central location and only SharePoint sites in the central location are available to use as sources for topics.</span></span> <span data-ttu-id="e1639-140">(Если выбрать **все сайты,** Viva Topics будет использовать все сайты в центре расположения.)</span><span class="sxs-lookup"><span data-stu-id="e1639-140">(If you select **All sites**, Viva Topics will use all site in the central location.)</span></span>

<span data-ttu-id="e1639-141">Вся обработка и хранение контента в центре.</span><span class="sxs-lookup"><span data-stu-id="e1639-141">All processing and storage of content is done in the central location.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="e1639-142">Разрешения пользователей</span><span class="sxs-lookup"><span data-stu-id="e1639-142">User permissions</span></span>

<span data-ttu-id="e1639-143">Разрешения пользователей, которые вы указываете, определяют, какие пользователи в организации взаимодействуют с темами и что они могут сделать.</span><span class="sxs-lookup"><span data-stu-id="e1639-143">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

> [!Note] 
> <span data-ttu-id="e1639-144">В настоящее время Viva Topics не поддерживает предоставление лицензий или разрешений пользователей для гостевых (внешних) пользователей.</span><span class="sxs-lookup"><span data-stu-id="e1639-144">At this time, Viva Topics doesn't support providing licenses or user permissions for Guest (External) users.</span></span> 

<span data-ttu-id="e1639-145">*Управление темами*</span><span class="sxs-lookup"><span data-stu-id="e1639-145">*Manage topics*</span></span>

<span data-ttu-id="e1639-146">Руководители знаний следит за качеством информации, ее структурой и другими лучшими практиками в организации.</span><span class="sxs-lookup"><span data-stu-id="e1639-146">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="e1639-147">Они могут подтвердить и отклонить темы.</span><span class="sxs-lookup"><span data-stu-id="e1639-147">They can confirm and reject topics.</span></span>

<span data-ttu-id="e1639-148">В то время как вы можете указать отдельных руководителей тем, мы рекомендуем создать группу безопасности (или использовать существующую), которая содержит людей, которые вы хотите быть менеджерами знаний.</span><span class="sxs-lookup"><span data-stu-id="e1639-148">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="e1639-149">Эту группу безопасности можно указать во время процесса настройки.</span><span class="sxs-lookup"><span data-stu-id="e1639-149">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="e1639-150">*Создание и изменение тем*</span><span class="sxs-lookup"><span data-stu-id="e1639-150">*Create and edit topics*</span></span>

<span data-ttu-id="e1639-151">Участники темы — это эксперты по темам и чемпионам в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e1639-151">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="e1639-152">Они могут создавать и редактировать темы.</span><span class="sxs-lookup"><span data-stu-id="e1639-152">They can create and edit topics.</span></span> 

<span data-ttu-id="e1639-153">Мы рекомендуем разрешить всем пользователям в организации создавать и редактировать темы, так как опыт работы с темой лучше всего работает, когда все пользователи могут обмениваться информацией.</span><span class="sxs-lookup"><span data-stu-id="e1639-153">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="e1639-154">Если вы хотите ограничить создание и редактирование тем определенными людьми или группами, создайте группу безопасности для них и укажите ее в процессе настройки.</span><span class="sxs-lookup"><span data-stu-id="e1639-154">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="e1639-155">Вы можете не разрешать никому вносить свой вклад в темы, однако это не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="e1639-155">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="e1639-156">Менеджеры знаний по-прежнему смогут редактировать и создавать темы, если вы выберете этот параметр.</span><span class="sxs-lookup"><span data-stu-id="e1639-156">Knowledge managers will still be able to edit and create topics if you choose this option.</span></span>

<span data-ttu-id="e1639-157">*Средства просмотра тем*</span><span class="sxs-lookup"><span data-stu-id="e1639-157">*Topic viewers*</span></span>

<span data-ttu-id="e1639-158">Зрители темы могут видеть сведения на страницах тем, в результатах поиска и когда темы выделены в контенте, SharePoint страницах.</span><span class="sxs-lookup"><span data-stu-id="e1639-158">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="e1639-159">Пользователи могут видеть обнаруженные темы только при доступе к файлам и страницам, в которые была обнаружена тема.</span><span class="sxs-lookup"><span data-stu-id="e1639-159">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="e1639-160">При настройке просмотра темы можно выбрать из:</span><span class="sxs-lookup"><span data-stu-id="e1639-160">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="e1639-161">**Все в моей организации**</span><span class="sxs-lookup"><span data-stu-id="e1639-161">**Everyone in my organization**</span></span>
- <span data-ttu-id="e1639-162">**Только выбранные люди или группы безопасности**</span><span class="sxs-lookup"><span data-stu-id="e1639-162">**Only selected people or security groups**</span></span>
- <span data-ttu-id="e1639-163">**Никто**</span><span class="sxs-lookup"><span data-stu-id="e1639-163">**No one**</span></span>

<span data-ttu-id="e1639-164">Мы рекомендуем **всем в моей** организации, но если вы делаете пилот, вы можете выбрать только выбранные люди или группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="e1639-164">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="e1639-165">Вы также можете выбрать **No one,** если вы хотите настроить Разделы, но пока не разрешаете пользователям видеть темы.</span><span class="sxs-lookup"><span data-stu-id="e1639-165">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span></span> <span data-ttu-id="e1639-166">(Менеджеры знаний по-прежнему будут иметь доступ, чтобы разрешить им просматривать темы и помогать в принятии решения о широкой доступности тем.)</span><span class="sxs-lookup"><span data-stu-id="e1639-166">(Knowledge managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="e1639-167">Правила знаний</span><span class="sxs-lookup"><span data-stu-id="e1639-167">Knowledge rules</span></span>

<span data-ttu-id="e1639-168">Как администратор вы можете исключить некоторые темы из опытом темы.</span><span class="sxs-lookup"><span data-stu-id="e1639-168">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="e1639-169">Это полезно, если вы хотите, чтобы конфиденциальные данные не появлялись в темах.</span><span class="sxs-lookup"><span data-stu-id="e1639-169">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="e1639-170">Хотя руководители знаний могут исключать темы в центре тем, темы, исключенные администратором, даже не видны руководителям знаний.</span><span class="sxs-lookup"><span data-stu-id="e1639-170">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="e1639-171">(Менеджеры знаний также могут удалять темы в центре тем после обнаружения.)</span><span class="sxs-lookup"><span data-stu-id="e1639-171">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="e1639-172">Если вы хотите исключить темы на уровне администратора, необходимо добавить их .csv файл и загрузить файл.</span><span class="sxs-lookup"><span data-stu-id="e1639-172">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="e1639-173">Это можно сделать во время установки или позже.</span><span class="sxs-lookup"><span data-stu-id="e1639-173">You can do this during setup or later.</span></span>

<span data-ttu-id="e1639-174">Файл .csv должен содержать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e1639-174">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="e1639-175">**Имя**: введите имя темы, которую хотите исключить.</span><span class="sxs-lookup"><span data-stu-id="e1639-175">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="e1639-176">Это можно сделать двумя способами:</span><span class="sxs-lookup"><span data-stu-id="e1639-176">There are two ways to do this:</span></span>
- <span data-ttu-id="e1639-177">**MatchType-Exact/Partial**. Введите, было ли вписано имя *точным* или *частичным типом* совпадения.</span><span class="sxs-lookup"><span data-stu-id="e1639-177">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="e1639-178">Точное совпадение. Вы можете включить точное имя или аббревиатура (например, *Contoso* или *ATL).*</span><span class="sxs-lookup"><span data-stu-id="e1639-178">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="e1639-179">Частичное совпадение. Вы можете исключить все темы, в них есть определенное слово.</span><span class="sxs-lookup"><span data-stu-id="e1639-179">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="e1639-180">Например, *дуга* исключает все темы со *словом* дуга в нем, такие как круг *дуги,* сварка плазменной дуги или *дуга обучения.* Обратите внимание, что не исключены темы, в которые текст включен как часть слова, например *Архитектура.*</span><span class="sxs-lookup"><span data-stu-id="e1639-180">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="e1639-181">**Означает (необязательно)**: (Также известный как *расширение)* Если вы хотите исключить аббревиатура, введите слова, которые обозначает аббревиатура.</span><span class="sxs-lookup"><span data-stu-id="e1639-181">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![Исключение тем в шаблоне CSV](../media/exclude-topics-csv.png) 

<span data-ttu-id="e1639-183">Вы можете скопировать шаблон csv ниже:</span><span class="sxs-lookup"><span data-stu-id="e1639-183">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="e1639-184">Администрирование</span><span class="sxs-lookup"><span data-stu-id="e1639-184">Administration</span></span>

<span data-ttu-id="e1639-185">При настройке Разделы в рамках процесса настройки автоматически создается центр тем.</span><span class="sxs-lookup"><span data-stu-id="e1639-185">When you set up Topics, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="e1639-186">Подумайте, как назвать центр темы и каким должен быть URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="e1639-186">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="e1639-187">В процессе настройки можно установить имя и URL-адрес, а затем изменить имя (но не URL-адрес) в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e1639-187">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="e1639-188">Вы можете иметь только один центр темы.</span><span class="sxs-lookup"><span data-stu-id="e1639-188">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="e1639-189">Контрольный список установки</span><span class="sxs-lookup"><span data-stu-id="e1639-189">Setup checklist</span></span>

<span data-ttu-id="e1639-190">При настройке опытом работы с темами вам будут необходимы следующие элементы при пройме мастера настройки:</span><span class="sxs-lookup"><span data-stu-id="e1639-190">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="e1639-191">список включенных и исключенных сайтов, если в поиск тем включены не все сайты;</span><span class="sxs-lookup"><span data-stu-id="e1639-191">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="e1639-192">группа безопасности для просматривающих темы, если не всем пользователям разрешено их просматривать;</span><span class="sxs-lookup"><span data-stu-id="e1639-192">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="e1639-193">группа безопасности для участников темы, если не всем пользователям разрешено создавать и редактировать темы;</span><span class="sxs-lookup"><span data-stu-id="e1639-193">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="e1639-194">группа безопасности для управляющих тематическим базам знаний, если не всем пользователям разрешено управлять темами;</span><span class="sxs-lookup"><span data-stu-id="e1639-194">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="e1639-195">Список конфиденциальных тем, которые необходимо исключить из обнаружения темы</span><span class="sxs-lookup"><span data-stu-id="e1639-195">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="e1639-196">Имя сайта центра темы</span><span class="sxs-lookup"><span data-stu-id="e1639-196">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="e1639-197">См. также</span><span class="sxs-lookup"><span data-stu-id="e1639-197">See also</span></span>

[<span data-ttu-id="e1639-198">Настройка тем</span><span class="sxs-lookup"><span data-stu-id="e1639-198">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="e1639-199">Управление обнаружением темы в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e1639-199">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="e1639-200">Управление обзором тем в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e1639-200">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="e1639-201">Управление разрешениями тем в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e1639-201">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="e1639-202">Измените имя центра темы в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e1639-202">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
