---
title: Диспетчер соответствия требованиям (Майкрософт) и GDPR
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Диспетчер соответствия требованиям (Майкрософт) — это бесплатное средство оценки рисков на основе рабочего процесса на портале Microsoft Service Trust Portal. Диспетчер соответствия требованиям позволяет отслеживать, назначать и проверять действия по обеспечению соответствия нормативным требованиям, связанные с облачными службами Майкрософт.
ms.openlocfilehash: 69e6551620fb654cb09d46554e6e3c98b6a2fc60
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595806"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a><span data-ttu-id="15b69-104">Диспетчер соответствия требованиям (Майкрософт) и GDPR</span><span class="sxs-lookup"><span data-stu-id="15b69-104">Microsoft Compliance Manager and the GDPR</span></span>

<span data-ttu-id="15b69-105">Общий регламент по защите данных (GDPR), принятый в Европейском союзе, может повлиять на стратегию соответствия требованиям и нацавить определенные действия по управлению сведениями о пользователях и клиентах, используемых в диспетчере соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="15b69-105">The General Data Protection Regulation (GDPR) enacted by the European Union can impact your compliance strategy and mandate specific actions to manage user and customer information used in Compliance Manager.</span></span>

## <a name="user-privacy-settings"></a><span data-ttu-id="15b69-106">Параметры конфиденциальности пользователей</span><span class="sxs-lookup"><span data-stu-id="15b69-106">User Privacy settings</span></span>

<span data-ttu-id="15b69-107">Некоторые нормативные акты требуют, чтобы организация смогла удалять данные истории пользователей.</span><span class="sxs-lookup"><span data-stu-id="15b69-107">Certain regulations require that an organization must be able to delete user history data.</span></span> <span data-ttu-id="15b69-108">Диспетчер соответствия требованиям предоставляет **функции параметров конфиденциальности** пользователей, позволяющие администраторам:</span><span class="sxs-lookup"><span data-stu-id="15b69-108">Compliance Manager provides **User Privacy Settings** functions that allow administrators to:</span></span>
  
- [<span data-ttu-id="15b69-109">искать пользователей;</span><span class="sxs-lookup"><span data-stu-id="15b69-109">Search for a user</span></span>](#search-for-a-user)
- [<span data-ttu-id="15b69-110">экспортировать отчет о журнале данных учетных записей;</span><span class="sxs-lookup"><span data-stu-id="15b69-110">Export a report of account data history</span></span>](#export-a-report-of-account-data-history)
- [<span data-ttu-id="15b69-111">удалять журналы данных пользователей.</span><span class="sxs-lookup"><span data-stu-id="15b69-111">Delete user data history</span></span>](#delete-user-data-history)
  
## <a name="search-for-a-user"></a><span data-ttu-id="15b69-112">Поиск пользователя</span><span class="sxs-lookup"><span data-stu-id="15b69-112">Search for a user</span></span>

<span data-ttu-id="15b69-113">Чтобы найти учетную запись, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="15b69-113">To search for a user account:</span></span>
  
1. <span data-ttu-id="15b69-114">Введите псевдоним электронной почты пользователя (сведения слева от символа @) и выберите доменное имя в списке суффиксов домена справа.</span><span class="sxs-lookup"><span data-stu-id="15b69-114">Enter the user email alias (the information to the left of the @ symbol) and choose the domain name from the  domain suffix list on the right.</span></span> <span data-ttu-id="15b69-115">Для организаций с несколькими зарегистрированными доменами дважды проверьте суффикс имени домена, чтобы убедиться, что он правильный.</span><span class="sxs-lookup"><span data-stu-id="15b69-115">For organizations with multiple registered domains, double check the domain name suffix to ensure that it is correct.</span></span>

2. <span data-ttu-id="15b69-116">После правильного введенного имени пользователя выберите **"Поиск".**</span><span class="sxs-lookup"><span data-stu-id="15b69-116">When you have the username correctly entered, select **Search**.</span></span>

3. <span data-ttu-id="15b69-117">Если учетные записи пользователей не возвращаются, на странице отображается **"Пользователь не найден".**</span><span class="sxs-lookup"><span data-stu-id="15b69-117">For user accounts not returned, the page displays **User not found**.</span></span> <span data-ttu-id="15b69-118">Проверьте сведения об электронном адресе пользователя и внести необходимые изменения.</span><span class="sxs-lookup"><span data-stu-id="15b69-118">Check the user's email address information and make corrections as necessary.</span></span> <span data-ttu-id="15b69-119">Чтобы повторить попытку, выберите **"Поиск".**</span><span class="sxs-lookup"><span data-stu-id="15b69-119">To retry, select **Search**.</span></span>

4. <span data-ttu-id="15b69-120">Для возвращенных учетных записей пользователей текст кнопки меняется с **"Поиск"** на **"Очистить".**</span><span class="sxs-lookup"><span data-stu-id="15b69-120">For user accounts returned, the text of the button changes from **Search** to **Clear**.</span></span> <span data-ttu-id="15b69-121">Это означает, что возвращенная учетная запись пользователя является операционным контекстом для дополнительных функций и что эти функции применяются к этой учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="15b69-121">This indicates that the returned user account is the operating context for the additional functions and that these functions apply to this user account.</span></span>

5. <span data-ttu-id="15b69-122">Чтобы очистить результаты поиска и найти другого пользователя, выберите **"Очистить".**</span><span class="sxs-lookup"><span data-stu-id="15b69-122">To clear search results and search for a different user, select **Clear**.</span></span>

## <a name="export-a-report-of-account-data-history"></a><span data-ttu-id="15b69-123">Экспорт отчета о журнале данных учетной записи</span><span class="sxs-lookup"><span data-stu-id="15b69-123">Export a report of account data history</span></span>

<span data-ttu-id="15b69-124">Для каждой идентифицированной учетной записи пользователя можно создать отчет о зависимостей, связанных с этой учетной записью.</span><span class="sxs-lookup"><span data-stu-id="15b69-124">For each user account identified, you can generate a report of dependencies linked to the account.</span></span> <span data-ttu-id="15b69-125">Эти сведения позволяют перенаназывают открытые элементы действий или обеспечивают доступ к ранее загруженным свидетельствам.</span><span class="sxs-lookup"><span data-stu-id="15b69-125">This information allows you to reassign open Action Items or ensure access to previously uploaded evidence.</span></span>
  
 <span data-ttu-id="15b69-126">Чтобы создать и экспортировать отчет, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="15b69-126">To generate and export a report:</span></span>
  
1. <span data-ttu-id="15b69-127">Выберите **"Экспорт",** чтобы создать и скачать отчет об поруправлении диспетчера соответствия требованиям, который в настоящее время назначен возвращенной учетной записи пользователя, и список документов, загруженных этим пользователем.</span><span class="sxs-lookup"><span data-stu-id="15b69-127">Select **Export** to generate and download a report of the Compliance Manager control Action Items currently assigned to the returned user account, and the list of documents uploaded by that user.</span></span> <span data-ttu-id="15b69-128">Если действия или загруженные документы не назначены, в сообщении об ошибке будет отобрано сообщение "Нет данных для этого пользователя".</span><span class="sxs-lookup"><span data-stu-id="15b69-128">If there are no assigned actions or uploaded documents, an error message states "No data for this user".</span></span>

2. <span data-ttu-id="15b69-129">Отчет загружается в фоновом режиме активного окна браузера, если вы не видите всплывающее окно загрузки, которое вы хотите проверить в истории загрузки браузера.</span><span class="sxs-lookup"><span data-stu-id="15b69-129">The report downloads in the background of the active browser window — if you don't see a download popup that you want to check your browser download history.</span></span>

3. <span data-ttu-id="15b69-130">Откройте документ, чтобы просмотреть данные отчета.</span><span class="sxs-lookup"><span data-stu-id="15b69-130">Open the document to review the report data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="15b69-131">Данные отчета не являются историческим списком, который сохраняет и отображает изменения состояния в истории назначений элементов действий.</span><span class="sxs-lookup"><span data-stu-id="15b69-131">The report data is not a historical list that retains and displays state changes to Action Item assignment history.</span></span> <span data-ttu-id="15b69-132">Созданный отчет — это снимок поручек элементов управления, которые были назначены во время его запуска (отметка даты и времени, записанная в отчет).</span><span class="sxs-lookup"><span data-stu-id="15b69-132">The generated report is a snapshot of the control Action Items assigned at the time that the report is run (date and time stamp written into the report).</span></span> <span data-ttu-id="15b69-133">Например, любое последующее перенаназание элементов действия приводит к разным данным моментального снимка отчета, если отчет создается снова для того же пользователя.</span><span class="sxs-lookup"><span data-stu-id="15b69-133">For example, any subsequent reassignment of Action Items result in different snapshot report data if the report is generated again for the same user.</span></span>
  
## <a name="delete-user-data-history"></a><span data-ttu-id="15b69-134">Удаление журнала данных пользователя</span><span class="sxs-lookup"><span data-stu-id="15b69-134">Delete user data history</span></span>

<span data-ttu-id="15b69-135">Устанавливает для всех порученных элементов управления, которые назначены возвращенным пользователем, "не назначено".</span><span class="sxs-lookup"><span data-stu-id="15b69-135">Sets all control Action Items assigned to the returned user to 'unassigned'.</span></span> <span data-ttu-id="15b69-136">Задает **для всех** документов, отложенных возвращенным пользователем, значение "пользователь удален".</span><span class="sxs-lookup"><span data-stu-id="15b69-136">Sets the **uploaded by** value for any documents uploaded by the returned user to 'user removed'.</span></span>
  
<span data-ttu-id="15b69-137">Чтобы удалить элемент действия учетной записи пользователя и историю отправки документов:</span><span class="sxs-lookup"><span data-stu-id="15b69-137">To delete the user account Action Item and document upload history:</span></span>
  
1. <span data-ttu-id="15b69-138">Выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="15b69-138">Select **Delete**.</span></span>

    <span data-ttu-id="15b69-139">Отобразилось диалоговое окно подтверждения: "Это удаляет все назначения элементов управления и историю отправки документов для *выбранного пользователя. Это действие является постоянным. Вы уверены, что хотите продолжить?*</span><span class="sxs-lookup"><span data-stu-id="15b69-139">A confirmation dialog is displayed: "*This removes all control Action Item assignments and the document upload history for the selected user. This action is permanent. Are you sure you want to continue?*"</span></span>

2. <span data-ttu-id="15b69-140">Чтобы продолжить, выберите **"ОК",** в противном случае выберите **"Отмена".**</span><span class="sxs-lookup"><span data-stu-id="15b69-140">To continue select **OK**, otherwise select **Cancel**.</span></span>
