---
title: Управление интересными людьми при расследовании данных (Предварительная версия)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Узнайте, как управлять интересующими пользователями, чтобы ограничить область поиска или просмотреть такие сведения, как контакты, расположения и журналы действий.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7cab1904731f325f1ec45685ddf122e5ee375a2b
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036072"
---
# <a name="manage-people-of-interest-in-data-investigations-preview"></a><span data-ttu-id="6c687-103">Управление интересными людьми при расследовании данных (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="6c687-103">Manage people of interest in Data Investigations (Preview)</span></span>

<span data-ttu-id="6c687-104">При расследовании данных часто используются люди, представляющие интерес.</span><span class="sxs-lookup"><span data-stu-id="6c687-104">Data investigations often involve people of interest.</span></span> <span data-ttu-id="6c687-105">Обычно это люди, которые владеют неправильной, конфиденциальными или вредоносными данными, которые вы изучаете или ищете.</span><span class="sxs-lookup"><span data-stu-id="6c687-105">Usually they are people who own the misplaced, sensitive or malicious data that you're investigating or looking to remediate.</span></span> <span data-ttu-id="6c687-106">При **расследовании данных (Предварительная версия)** можно добавить их для обнаружения источников данных, чтобы использовать их в области поиска, или просмотреть дополнительные сведения, такие как контакты, расположение и журналы действий.</span><span class="sxs-lookup"><span data-stu-id="6c687-106">In **Data Investigations (Preview)**, you can add them to discover their data sources to use in scoping your search or view additional information such as contact, location and activity logs.</span></span> 


## <a name="add-people-of-interest"></a><span data-ttu-id="6c687-107">Добавление интересующих людей</span><span class="sxs-lookup"><span data-stu-id="6c687-107">Add people of interest</span></span>

<span data-ttu-id="6c687-108">На вкладке **люди по процентам** вы можете добавлять людей и находить свои источники данных, такие как почтовые ящики Exchange или сайт OneDrive для бизнеса, которые можно использовать для определения области поиска.</span><span class="sxs-lookup"><span data-stu-id="6c687-108">In **People of interest** tab, you can add people of interest and discover their data sources such as Exchange mailboxes or OneDrive for Business site that you can use to scope your search.</span></span> <span data-ttu-id="6c687-109">Если область ограничена интересующими пользователями, поиск является более производительным и точным, так как средство повторно обрабатывает любые неиндексированные данные, такие как изображения или неподдерживаемые типы файлов.</span><span class="sxs-lookup"><span data-stu-id="6c687-109">When scoped down by people of interest, searches are more performant and accurate because the tool re-processes any unindexed data such as images or unsupported file types.</span></span> <span data-ttu-id="6c687-110">Вы также можете просмотреть сведения о контакте, сведения о расположении и журналах активности, которые можно использовать для инициации связи или дальнейшего изучения их действий.</span><span class="sxs-lookup"><span data-stu-id="6c687-110">You can also see their contact information, location information and activity logs that you can use to initiate communications or further investigate their activities.</span></span> 

<span data-ttu-id="6c687-111">Чтобы добавить людей для расследования, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="6c687-111">To add people of interest to an investigation:</span></span>

1. <span data-ttu-id="6c687-112">На странице **расследования данных (Предварительная версия)** перейдите к вашему исследованию.</span><span class="sxs-lookup"><span data-stu-id="6c687-112">From the **Data Investigations (Preview)** page, go to your investigation.</span></span>
 
2. <span data-ttu-id="6c687-113">Выбрав нужное исследование, перейдите на вкладку **люди, представляющие интерес** , и нажмите кнопку **+ Добавить интересующих людей**.</span><span class="sxs-lookup"><span data-stu-id="6c687-113">After you have selected a investigation, go to the **People of interest** tab and click **+ Add people of interest**.</span></span> 
 
3. <span data-ttu-id="6c687-114">Выберите пользователей, которых вы хотите добавить к расследованию.</span><span class="sxs-lookup"><span data-stu-id="6c687-114">Choose people that you want to add to the investigation.</span></span> <span data-ttu-id="6c687-115">Для начала введите Поиск и выберите пользователей из Azure Active Directory вашей организации.</span><span class="sxs-lookup"><span data-stu-id="6c687-115">You can start by typing to search and select the users from your organization's Azure Active Directory.</span></span>
 
4. <span data-ttu-id="6c687-116">После завершения работы со списком интересующих людей нажмите кнопку **Далее** , чтобы сопоставить источники данных.</span><span class="sxs-lookup"><span data-stu-id="6c687-116">After you have finalized the list of people of interest, click **Next** to map their data sources.</span></span> 

5. <span data-ttu-id="6c687-117">Необязательно Для каждого пользователя выберите **Exchange** , чтобы добавить основной почтовый ящик Exchange пользователя, и **OneDrive** , чтобы добавить основной сайт onedrive для бизнеса пользователя.</span><span class="sxs-lookup"><span data-stu-id="6c687-117">[Optional] For each person, select **Exchange** to add person's primary Exchange mailbox, and **OneDrive** to add person's primary OneDrive for Business site.</span></span>

6. <span data-ttu-id="6c687-118">Необязательно Нажмите кнопку **Далее** , чтобы добавить дополнительные источники данных, которые нужно связать с интересующими людьми.</span><span class="sxs-lookup"><span data-stu-id="6c687-118">[Optional] Click **Next** to add any additional data sources that you want to associate with your people of interest.</span></span>

7. <span data-ttu-id="6c687-119">Необязательно Выберите **Update (обновить** ), чтобы назначить расположение контента, например почтовые ящики, сайты и команды, для человека.</span><span class="sxs-lookup"><span data-stu-id="6c687-119">[Optional] Select **Update** to assign content locations, like mailboxes, sites, and Teams to a person.</span></span> 

8. <span data-ttu-id="6c687-120">Необязательно В всплывающем меню:</span><span class="sxs-lookup"><span data-stu-id="6c687-120">[Optional] In the flyout:</span></span>
   
    -  <span data-ttu-id="6c687-121">**Почтовые ящики Exchange** — выберите **Пользователи, группы или Teams** , а затем снова нажмите кнопку **выбрать пользователей, группы или Teams** .</span><span class="sxs-lookup"><span data-stu-id="6c687-121">**Exchange Mailboxes** - Click **Choose users, groups, or Teams** and then click **Choose users, groups, or teams** again.</span></span> <span data-ttu-id="6c687-122">Чтобы добавить дополнительные почтовые ящики, используйте поле поиска для поиска почтовых ящиков пользователей и групп рассылки.</span><span class="sxs-lookup"><span data-stu-id="6c687-122">To add more mailboxes, use the search box to find user mailboxes and distribution groups.</span></span> <span data-ttu-id="6c687-123">Вы также можете добавить почтовые ящики, используемые для хранения сведений о группе Microsoft 365 или Microsoft Team.</span><span class="sxs-lookup"><span data-stu-id="6c687-123">You can also add mailboxes used to store an Microsoft 365 Group or a Microsoft Team information.</span></span> <span data-ttu-id="6c687-124">Установите флажок Пользователь, группа, группа, нажмите кнопку **выбрать**, а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="6c687-124">Select the user, group, team check box, click **Choose**, and then click **Done**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="6c687-125">При нажатии кнопки выбрать пользователей, группы или Teams для указания почтовых ящиков, отображается пустое средство выбора почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="6c687-125">When you click Choose users, groups, or teams to specify mailboxes, the mailbox picker that's displayed is empty.</span></span> <span data-ttu-id="6c687-126">Это вызвано мерами по повышению скорости работы.</span><span class="sxs-lookup"><span data-stu-id="6c687-126">This is by design to enhance performance.</span></span> <span data-ttu-id="6c687-127">Чтобы добавить пользователей в этот список, введите в поле поиска имя (не менее 3 символов).</span><span class="sxs-lookup"><span data-stu-id="6c687-127">To add people to this list, type a name (a minimum of 3 characters) in the search box.</span></span>
     
     - <span data-ttu-id="6c687-128">**Сайты SharePoint** — нажмите кнопку **выбрать сайты** , а затем нажмите кнопку **выбрать сайты** еще раз, чтобы указать сайты SharePoint и OneDrive для бизнеса, которые будут добавлены в подсети WWAN для пользователя.</span><span class="sxs-lookup"><span data-stu-id="6c687-128">**SharePoint Sites** - Click **Choose sites** and then click **Choose sites** again to specify additional SharePoint and OneDrive for Business sites that you wwant to add to a person.</span></span> <span data-ttu-id="6c687-129">Вы также можете добавить URL-адрес сайта SharePoint для группы Microsoft 365 или группы Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6c687-129">You can also add the URL for the SharePoint site for an Microsoft 365 Group or a Microsoft Team.</span></span> <span data-ttu-id="6c687-130">Введите URL-адрес для каждого сайта, который необходимо назначить.</span><span class="sxs-lookup"><span data-stu-id="6c687-130">Type the URL for each site that you want to assign.</span></span> <span data-ttu-id="6c687-131">Нажмите кнопку **выбрать**, а затем кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="6c687-131">Click **Choose**, and then click **Done**.</span></span>
     - <span data-ttu-id="6c687-132">**Microsoft** Teams — выберите команду **выбрать Teams** и снова нажмите кнопку **выбрать** Teams, чтобы просмотреть список групп Microsoft Teams, участником которых является данный сотрудник.</span><span class="sxs-lookup"><span data-stu-id="6c687-132">**Microsoft Teams** – Click **Choose Teams** and then click **Choose Teams** again to view a list of Microsoft Team groups that the person is a member of today.</span></span> <span data-ttu-id="6c687-133">Выберите команды, которые вы хотите добавить для пользователя.</span><span class="sxs-lookup"><span data-stu-id="6c687-133">Select the Teams that you want to add to the person.</span></span> <span data-ttu-id="6c687-134">После выбора система автоматически определит & выберите связанный сайт SharePoint и почтовый ящик группы, связанные с этой командой Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6c687-134">Once selected, the system will automatically identify & select the associated SharePoint site and Group Mailbox associated to that Microsoft Team.</span></span> <span data-ttu-id="6c687-135">Нажмите кнопку **выбрать**, а затем кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="6c687-135">Click **Choose**, and then click **Done**.</span></span>
        
      > [!NOTE]
      > <span data-ttu-id="6c687-136">Чтобы добавить дополнительные Microsoft Teams, вам потребуется отдельно добавить почтовый ящик и сайт SharePoint, как показано выше.</span><span class="sxs-lookup"><span data-stu-id="6c687-136">To add additional Microsoft Teams, you will need to separately add the mailbox and SharePoint site as shown above.</span></span>

<span data-ttu-id="6c687-137">После того как вы намерены сопоставление источников данных с интересующими пользователями, вы увидите сводку всех добавленных почтовых ящиков, сайтов и команд.</span><span class="sxs-lookup"><span data-stu-id="6c687-137">After you have finished mapping data sources to people of interest, you can see the summary of total mailboxes, sites, and Teams that you just added.</span></span> <span data-ttu-id="6c687-138">Если вы созначите какие-либо дополнительные источники данных для интересующих людей и выведете Поиск по интересующим людям, то сопоставление документа с интересующими пользователями не сохранится на протяжении расследования, что упрощает организацию доказательств или создание отчета по интересующим людям.</span><span class="sxs-lookup"><span data-stu-id="6c687-138">If you map any additional data sources to people of interest and scope your search by people of interest, the mapping of document to people of interest persist throughout the investigation, making it easier to organize evidence or generate report by people of interest.</span></span> 

## <a name="view-additional-people-of-interest-information"></a><span data-ttu-id="6c687-139">Просмотр дополнительных сведений о людях</span><span class="sxs-lookup"><span data-stu-id="6c687-139">View additional people of interest information</span></span>

<span data-ttu-id="6c687-140">На вкладке **люди процентов** щелкните человека, которого вы адиде.</span><span class="sxs-lookup"><span data-stu-id="6c687-140">In **People of interest** tab, click on a person that you adeed.</span></span> <span data-ttu-id="6c687-141">В всплывающем меню вы увидите следующее:</span><span class="sxs-lookup"><span data-stu-id="6c687-141">In a flyout, you'll see:</span></span>

- <span data-ttu-id="6c687-142">Контактные данные</span><span class="sxs-lookup"><span data-stu-id="6c687-142">Contact information</span></span>

  - <span data-ttu-id="6c687-143">**Отображаемое имя**: имя Перон, отображаемое в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="6c687-143">**Display Name**: The peron's name displayed in the address book.</span></span> <span data-ttu-id="6c687-144">Обычно это сочетание имени, инициала и фамилии.</span><span class="sxs-lookup"><span data-stu-id="6c687-144">This is usually the combination of first name, middle initial and last name.</span></span>
  - <span data-ttu-id="6c687-145">**Mail/SMTP**: SMTP-адрес пользователя, например Jeff@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="6c687-145">**Mail/SMTP**: The SMTP address of the person, for example, jeff@contoso.onmicrosoft.com.</span></span>  
  - <span data-ttu-id="6c687-146">**Заголовок**: должность.</span><span class="sxs-lookup"><span data-stu-id="6c687-146">**Title**: Job title.</span></span>
  - <span data-ttu-id="6c687-147">**Отдел**: имя отдела, в котором работает пользователь.</span><span class="sxs-lookup"><span data-stu-id="6c687-147">**Department**: The name of the department in which the person works.</span></span>
  - <span data-ttu-id="6c687-148">**Руководитель**: руководитель сотрудника.</span><span class="sxs-lookup"><span data-stu-id="6c687-148">**Manager**: The person's manager.</span></span> <span data-ttu-id="6c687-149">Manager получает сведения о эскалации для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="6c687-149">Manager receives any escalation communications for this person.</span></span>
  
- <span data-ttu-id="6c687-150">Сведения о расположении</span><span class="sxs-lookup"><span data-stu-id="6c687-150">Location information</span></span>

  - <span data-ttu-id="6c687-151">**City**: город, в котором находится пользователь.</span><span class="sxs-lookup"><span data-stu-id="6c687-151">**City**: The city in which the person is located.</span></span>
  - <span data-ttu-id="6c687-152">**State**: область или край, где находится пользователь.</span><span class="sxs-lookup"><span data-stu-id="6c687-152">**State**: The state or province in which the person is located.</span></span>
  - <span data-ttu-id="6c687-153">**Страна или регион**: страна или регион, где находится пользователь; Например, "US" или "Великобритания".</span><span class="sxs-lookup"><span data-stu-id="6c687-153">**Country/Region**: The country/region in which the person is located; for example, "US" or "UK".</span></span>
  - <span data-ttu-id="6c687-154">**Office**: расположение офиса пользователя.</span><span class="sxs-lookup"><span data-stu-id="6c687-154">**Office**: The office location of the person.</span></span>

- <span data-ttu-id="6c687-155">Состояние обработки</span><span class="sxs-lookup"><span data-stu-id="6c687-155">Processing status</span></span>

  - <span data-ttu-id="6c687-156">**Состояние индексирования**: состояние глубокого индексирования источников данных</span><span class="sxs-lookup"><span data-stu-id="6c687-156">**Indexing status**: Status of deep indexing the data sources</span></span>
  - <span data-ttu-id="6c687-157">**Время последнего обновления индексации**: метка времени последнего запуска задания глубокого индексирования.</span><span class="sxs-lookup"><span data-stu-id="6c687-157">**Indexing Last Updated Time**: Timestamp of when the deep indexing job was last triggered.</span></span>
  - <span data-ttu-id="6c687-158">**Источники данных**: показывает количество почтовых ящиков, сайтов и команд, сопоставленных с пользователем.</span><span class="sxs-lookup"><span data-stu-id="6c687-158">**Data sources**: Shows the count of mailboxes, sites, and Teams mapped to the person</span></span>

- <span data-ttu-id="6c687-159">Обновление индекса</span><span class="sxs-lookup"><span data-stu-id="6c687-159">Update index</span></span>
    - <span data-ttu-id="6c687-160">Вы можете повторно индексировать источники данных этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="6c687-160">You can re-index this person's data sources.</span></span> 

- <span data-ttu-id="6c687-161">Просмотр действий</span><span class="sxs-lookup"><span data-stu-id="6c687-161">View activity</span></span> 

    - <span data-ttu-id="6c687-162">Вы можете просматривать журналы активности пользователя и искать их.</span><span class="sxs-lookup"><span data-stu-id="6c687-162">You can view and search user's activity logs.</span></span> <span data-ttu-id="6c687-163">Дополнительную информацию можно узнать в статье [Просмотр сведений о действиях по интересам](view-people-of-interest-activity.md)</span><span class="sxs-lookup"><span data-stu-id="6c687-163">For more information, see [View people of interest activity](view-people-of-interest-activity.md)</span></span> 
