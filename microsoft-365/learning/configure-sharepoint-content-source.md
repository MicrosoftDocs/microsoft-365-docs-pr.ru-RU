---
title: 'Скоро: настройте SharePoint как источник учебного контента для Microsoft Viva Learning (Preview)'
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/12/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Узнайте, как настроить SharePoint как источник обучающего контента для Microsoft Viva Learning (Preview).
ms.openlocfilehash: 2bed3a42d62e2aab2165ee38379eb07503807e6e
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333582"
---
# <a name="coming-soon-configure-sharepoint-as-a-learning-content-source-for-microsoft-viva-learning-preview"></a><span data-ttu-id="84e63-103">Скоро: настройте SharePoint как источник учебного контента для Microsoft Viva Learning (Preview)</span><span class="sxs-lookup"><span data-stu-id="84e63-103">Coming soon: Configure SharePoint as a learning content source for Microsoft Viva Learning (Preview)</span></span>

> [!NOTE]
> <span data-ttu-id="84e63-104">Сведения в этой статье относятся к продукту предварительного просмотра, который может быть существенно изменен до его коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="84e63-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="84e63-105">Вы можете настроить SharePoint как источник контента для обучения, чтобы сделать собственный контент организации доступным в Viva Learning (Preview).</span><span class="sxs-lookup"><span data-stu-id="84e63-105">You can configure SharePoint as a learning content source to make your organization's own content available in Viva Learning (Preview).</span></span>

## <a name="overview"></a><span data-ttu-id="84e63-106">Обзор</span><span class="sxs-lookup"><span data-stu-id="84e63-106">Overview</span></span>

<span data-ttu-id="84e63-107">Администратор знаний (или глобальный администратор) предоставляет URL-адрес сайта, на котором служба обучения может создать пустое централизованное расположение — репозиторий контента обучающих приложений — в виде структурированного списка SharePoint.</span><span class="sxs-lookup"><span data-stu-id="84e63-107">The knowledge admin (or global administrator) provides a site URL to where the Learning Service can create an empty centralized location—the Learning App Content Repository—in the form of a structured SharePoint list.</span></span> <span data-ttu-id="84e63-108">Этот список может использоваться организацией для использования ссылок на межкомпанийные SharePoint, содержащие обучающий контент.</span><span class="sxs-lookup"><span data-stu-id="84e63-108">This list can be used by your organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="84e63-109">Администраторы отвечают за сбор и кураторирование списка URL-адресов для папок.</span><span class="sxs-lookup"><span data-stu-id="84e63-109">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="84e63-110">Эти папки должны включать только содержимое, которое можно сделать доступным в Viva Learning (Preview).</span><span class="sxs-lookup"><span data-stu-id="84e63-110">These folders should only include content that can be made available in Viva Learning (Preview).</span></span>

<span data-ttu-id="84e63-111">Viva Learning (Preview) поддерживает следующие типы документов:</span><span class="sxs-lookup"><span data-stu-id="84e63-111">Viva Learning (Preview) supports the following document types:</span></span>

- <span data-ttu-id="84e63-112">Word, PowerPoint, Excel, PDF</span><span class="sxs-lookup"><span data-stu-id="84e63-112">Word, PowerPoint, Excel, PDF</span></span>
- <span data-ttu-id="84e63-113">Аудио (.m4a)</span><span class="sxs-lookup"><span data-stu-id="84e63-113">Audio (.m4a)</span></span>
- <span data-ttu-id="84e63-114">Видео (.mov, .mp4, .avi)</span><span class="sxs-lookup"><span data-stu-id="84e63-114">Video (.mov, .mp4, .avi)</span></span>

<span data-ttu-id="84e63-115">Дополнительные сведения см. [в SharePoint ограничения.](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)</span><span class="sxs-lookup"><span data-stu-id="84e63-115">For more information, see [SharePoint limits](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span> 

## <a name="permissions"></a><span data-ttu-id="84e63-116">Разрешения</span><span class="sxs-lookup"><span data-stu-id="84e63-116">Permissions</span></span>

<span data-ttu-id="84e63-117">URL-адреса папок библиотеки документов можно собирать с любого SharePoint сайта в организации.</span><span class="sxs-lookup"><span data-stu-id="84e63-117">Document library folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="84e63-118">Viva Learning (Preview) следует всем существующим разрешениям на контент.</span><span class="sxs-lookup"><span data-stu-id="84e63-118">Viva Learning (Preview) follows all existing content permissions.</span></span> <span data-ttu-id="84e63-119">Поэтому только контент, к которому пользователь имеет разрешение на доступ, можно искать и просматривать в Viva Learning (Preview).</span><span class="sxs-lookup"><span data-stu-id="84e63-119">Therefore, only content for which a user has permission to access is searchable and visible within Viva Learning (Preview).</span></span> <span data-ttu-id="84e63-120">Любой контент в этих папках будет искаться, но можно использовать только контент, к которому у отдельного сотрудника есть разрешения.</span><span class="sxs-lookup"><span data-stu-id="84e63-120">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>

<span data-ttu-id="84e63-121">Удаление контента из репозитория организации в настоящее время не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="84e63-121">Content deletion from your organization’s repository is not currently supported.</span></span>

<span data-ttu-id="84e63-122">Чтобы удалить непреднамеренно всплыть содержимое, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="84e63-122">To remove unintentionally surfaced content, follow these steps:</span></span>

1.  <span data-ttu-id="84e63-123">Чтобы ограничить доступ к библиотеке документов, выберите параметр **Показать** действия, а затем выберите **Управление доступом.**</span><span class="sxs-lookup"><span data-stu-id="84e63-123">To restrict access to the document library, select the **Show actions** option, and then select **Manage access**.</span></span>
     
     ![Страница библиотеки документов в SharePoint показывает параметр Show actions with Manage access highligted.](../media/learning/learning-sharepoint-permissions2.png)

2.  <span data-ttu-id="84e63-125">Удаление исходного документа в библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="84e63-125">Delete the original document within the document library.</span></span>

<span data-ttu-id="84e63-126">Дополнительные сведения см. в разделе Общий доступ и разрешения в [SharePoint опытом.](/sharepoint/modern-experience-sharing-permissions)</span><span class="sxs-lookup"><span data-stu-id="84e63-126">For more information, see [Sharing and permissions in the SharePoint modern experience](/sharepoint/modern-experience-sharing-permissions).</span></span> 

## <a name="learning-service"></a><span data-ttu-id="84e63-127">Служба обучения</span><span class="sxs-lookup"><span data-stu-id="84e63-127">Learning Service</span></span>

<span data-ttu-id="84e63-128">Служба обучения использует предоставленные URL-адреса папок для получения метаданных из всего контента, хранимом в этих папках.</span><span class="sxs-lookup"><span data-stu-id="84e63-128">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="84e63-129">В течение 24 часов после поставки URL-адреса папки в централизованном репозитории сотрудники могут искать и использовать содержимое организации в Viva Learning (Preview).</span><span class="sxs-lookup"><span data-stu-id="84e63-129">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use your organization’s content within Viva Learning (Preview).</span></span> <span data-ttu-id="84e63-130">Все изменения контента, включая обновленные метаданные и разрешения, также будут применены в службе обучения в течение 24 часов.</span><span class="sxs-lookup"><span data-stu-id="84e63-130">All changes to content, including updated metadata and permissions, will also be applied in the Learning Service within 24 hours.</span></span>

## <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="84e63-131">Настройка SharePoint как источника</span><span class="sxs-lookup"><span data-stu-id="84e63-131">Configure SharePoint as a source</span></span>

<span data-ttu-id="84e63-132">Вы должны быть глобальным администратором Microsoft 365, администратором SharePoint или администратором знаний для выполнения этих задач.</span><span class="sxs-lookup"><span data-stu-id="84e63-132">You must be a Microsoft 365 global administrator, SharePoint administrator, or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="84e63-133">Чтобы настроить SharePoint как источники учебного контента для Viva Learning (Preview), выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="84e63-133">To configure SharePoint as a learning content sources in for Viva Learning (Preview), follow these steps:</span></span>

1.  <span data-ttu-id="84e63-134">В левой навигации центра администрирования Microsoft 365 перейдите к **Параметры**  >  **параметров Org.**</span><span class="sxs-lookup"><span data-stu-id="84e63-134">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>
 
2.  <span data-ttu-id="84e63-135">На странице **Параметры Org** на вкладке **Services** выберите **Viva Learning (Preview).**</span><span class="sxs-lookup"><span data-stu-id="84e63-135">On the **Org settings** page, on the **Services** tab, select **Viva Learning (Preview)**.</span></span>

     ![Параметры в центре администрирования Microsoft 365 viva Learning в списке.](../media/learning/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="84e63-137">На панели **Viva Learning (Preview)** SharePoint url-адрес сайта на сайте SharePoint, где необходимо создать централизованный репозиторий Viva Learning (Preview).</span><span class="sxs-lookup"><span data-stu-id="84e63-137">On the **Viva Learning (Preview)** panel, under SharePoint, provides the site URL to the SharePoint site where you want Viva Learning (Preview) to create a centralized repository.</span></span>

     ![Панель обучения в центре администрирования Microsoft 365, SharePoint выбрана.](../media/learning/learning-sharepoint-configure2.png)

4.  <span data-ttu-id="84e63-139">Список SharePoint создается автоматически в пределах предоставленного SharePoint сайта.</span><span class="sxs-lookup"><span data-stu-id="84e63-139">A SharePoint list is created automatically within the provided SharePoint site.</span></span>

     ![Недавно созданный SharePoint в SharePoint сайте.](../media/learning/learning-sharepoint-configure3.png)

     <span data-ttu-id="84e63-141">В левой навигации сайта SharePoint выберите репозиторий контента  >  **обучающего приложения.**</span><span class="sxs-lookup"><span data-stu-id="84e63-141">In the left navigation of the SharePoint site, select **Site contents** > **Learning App Content Repository**.</span></span> 

     ![SharePoint с навигацией по содержимому сайта и разделом Репозиторий контента обучающего приложения.](../media/learning/learning-sharepoint-configure4.png) 

5. <span data-ttu-id="84e63-143">На странице **Репозиторий** контента обучающих приложений заполняем список SharePoint URL-адресами в папки обучающего контента.</span><span class="sxs-lookup"><span data-stu-id="84e63-143">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1. <span data-ttu-id="84e63-144">Выберите **New** для просмотра **панели New item.**</span><span class="sxs-lookup"><span data-stu-id="84e63-144">Select **New** to view the **New item** panel.</span></span> 

       ![Страница Репозиторий контента в SharePoint с указанием нового параметра.](../media/learning/learning-sharepoint-configure5.png)
 
   2. <span data-ttu-id="84e63-146">На панели **New item** в поле **Title** добавьте имя каталога по вашему выбору.</span><span class="sxs-lookup"><span data-stu-id="84e63-146">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="84e63-147">В поле **URL-адрес папки** добавьте URL-адрес в папку обучающего контента.</span><span class="sxs-lookup"><span data-stu-id="84e63-147">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="84e63-148">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="84e63-148">Select **Save**.</span></span>

       ![Новая панель элементов SharePoint полей URL-адресов Title и Folder.](../media/learning/learning-sharepoint-configure6.png)

   3. <span data-ttu-id="84e63-150">Страница **Репозиторий** контента обучающих приложений обновляется новым учебным контентом.</span><span class="sxs-lookup"><span data-stu-id="84e63-150">The **Learning App Content Repository** page is updated with the new learning content.</span></span>

       ![Страница Репозиторий контента SharePoint с обновленной информацией.](../media/learning/learning-sharepoint-configure7.png)

> [!NOTE]
> <span data-ttu-id="84e63-152">Чтобы обеспечить более широкий доступ к репозиторию контента обучающих приложений, в интерфейсе Viva Learning (Preview) будет доступна ссылка на список, где пользователи могут запрашивать доступ и в конечном итоге помочь заполнить список.</span><span class="sxs-lookup"><span data-stu-id="84e63-152">To allow for broader access to the Learning App Content Repository, a link to the list soon will be available in the Viva Learning (Preview) interface where users can request access and ultimately help populate the list.</span></span> <span data-ttu-id="84e63-153">Владельцы сайтов и глобальные администраторы должны предоставить доступ к списку.</span><span class="sxs-lookup"><span data-stu-id="84e63-153">Site owners and global administrators will be required to grant access to the list.</span></span> <span data-ttu-id="84e63-154">Доступ относится только к списку и не применяется к сайту, на котором хранится список.</span><span class="sxs-lookup"><span data-stu-id="84e63-154">Access is specific to the list only and does not apply to the site where the list is stored.</span></span> <span data-ttu-id="84e63-155">Дополнительные сведения см. в [статье Provide your own organization's content](#provide-your-own-organizations-content) later in this article.</span><span class="sxs-lookup"><span data-stu-id="84e63-155">For more information, see [Provide your own organization's content](#provide-your-own-organizations-content) later in this article.</span></span>

### <a name="folder-url-document-library-curation"></a><span data-ttu-id="84e63-156">Куратор библиотеки url-адресов папок</span><span class="sxs-lookup"><span data-stu-id="84e63-156">Folder URL document library curation</span></span>

<span data-ttu-id="84e63-157">Метаданные по умолчанию (например, измененная дата, созданная именем документа, типом контента и именем организации) автоматически втягивается в Viva Learning (Preview) API Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="84e63-157">Default metadata (such as modified date, created by, document name, content type, and organization name) is automatically pulled into Viva Learning (Preview) by the Microsoft Graph API.</span></span>
 
<span data-ttu-id="84e63-158">Для улучшения общей релевантности поиска и обнаружения контента рекомендуется добавить столбец **Description.**</span><span class="sxs-lookup"><span data-stu-id="84e63-158">To improve overall discovery and search relevance of the content, we recommend adding a **Description** column.</span></span>

<span data-ttu-id="84e63-159">Чтобы добавить **столбец Описание** на страницу библиотеки документов, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="84e63-159">To add a **Description** column to the document library page, follow these steps:</span></span>

1.  <span data-ttu-id="84e63-160">На странице **Документы выберите** **столбец Добавить**.</span><span class="sxs-lookup"><span data-stu-id="84e63-160">On the **Documents** page, select **Add column**.</span></span>

2. <span data-ttu-id="84e63-161">Выберите параметр **Показать действия,** а затем выберите **одну строку текста.**</span><span class="sxs-lookup"><span data-stu-id="84e63-161">Select the **Show actions** option, and then select **Single line of text**.</span></span>

     ![На странице Документы SharePoint показаны параметры действий Show с выделенной отдельной строкой текста.](../media/learning/learning-sharepoint-curation1.png)

3. <span data-ttu-id="84e63-163">На панели **Создание панели столбцов** в поле **Имя** добавьте описательное имя столбца.</span><span class="sxs-lookup"><span data-stu-id="84e63-163">On the **Create a column** panel, in the **Name** field, add a descriptive name for the column.</span></span> <span data-ttu-id="84e63-164">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="84e63-164">Select **Save**.</span></span>

     ![Создайте панель столбцов в SharePoint с указанием имени и других полей.](../media/learning/learning-sharepoint-curation2.png)
 
4. <span data-ttu-id="84e63-166">На странице **Документы в** столбце **Описание** добавьте настраиваемые описания для каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="84e63-166">On the **Documents** page, in the **Description** column, add custom descriptions for each item.</span></span> <span data-ttu-id="84e63-167">Если описание не предоставлено, Viva Learning (Preview) предоставит сообщение по умолчанию, в которое будет выделено содержимое из SharePoint библиотеки.</span><span class="sxs-lookup"><span data-stu-id="84e63-167">If no description is supplied, Viva Learning (Preview) will provide a default message that highlights the content as being from your own SharePoint library.</span></span> 

     ![На странице документы в SharePoint показаны описания в столбце Описание.](../media/learning/learning-sharepoint-curation3.png)
 
### <a name="provide-your-own-organizations-content"></a><span data-ttu-id="84e63-169">Предоставление контента вашей организации</span><span class="sxs-lookup"><span data-stu-id="84e63-169">Provide your own organization's content</span></span>

<span data-ttu-id="84e63-170">Администраторы знаний могут получить доступ к репозиторию контента обучающих приложений своей организации в SharePoint, где они могут предоставлять ссылки на меж организации библиотек документов.</span><span class="sxs-lookup"><span data-stu-id="84e63-170">Knowledge admins can access their organization’s Learning App Content Repository in SharePoint, where they can provide references to cross-organization document libraries.</span></span> <span data-ttu-id="84e63-171">Содержимое в этих библиотеках будет затем всплыть в качестве обучающего контента в Viva Learning (Preview).</span><span class="sxs-lookup"><span data-stu-id="84e63-171">Content within these libraries will be then surfaced as learning content in Viva Learning (Preview).</span></span>

1. <span data-ttu-id="84e63-172">В Viva Learning (Preview) выберите **дополнительные параметры** **(...),** а затем **выберите Параметры**.</span><span class="sxs-lookup"><span data-stu-id="84e63-172">In Viva Learning (Preview), select **More options** (**...**), and then select **Settings**.</span></span>

     ![SharePoint на странице библиотеки с указанием параметра More и Параметры.](../media/learning/learning-sharepoint-library-1.png)
     
2. <span data-ttu-id="84e63-174">В **Параметры** выберите **Разрешения**.</span><span class="sxs-lookup"><span data-stu-id="84e63-174">Under **Settings**, select **Permissions**.</span></span>

     ![Параметры на странице SharePoint с указанием параметров разрешений и проверки доступа.](../media/learning/learning-sharepoint-library-2.png)

3. <span data-ttu-id="84e63-176">Выберите **контрольный** доступ для подключения к централизованной библиотеке организации.</span><span class="sxs-lookup"><span data-stu-id="84e63-176">Select **Check access** to connect to your organization’s centralized library.</span></span>
     
