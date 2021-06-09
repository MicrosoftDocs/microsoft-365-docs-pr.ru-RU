---
title: Microsoft Compliance Manager и GDPR
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
description: Microsoft Compliance Manager — это бесплатный инструмент оценки рисков на основе рабочего процесса на портале доверия к службам Майкрософт. Диспетчер соответствия требованиям позволяет отслеживать, назначать и проверять нормативные действия, связанные с облачными службами Майкрософт.
ms.openlocfilehash: 69e6551620fb654cb09d46554e6e3c98b6a2fc60
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595806"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a><span data-ttu-id="b0718-104">Microsoft Compliance Manager и GDPR</span><span class="sxs-lookup"><span data-stu-id="b0718-104">Microsoft Compliance Manager and the GDPR</span></span>

<span data-ttu-id="b0718-105">Общие правила защиты данных (GDPR), принятые Европейским союзом, могут повлиять на вашу стратегию соответствия требованиям и обязыть конкретные действия по управлению пользовательскими и клиентской информацией, используемой в диспетчере соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="b0718-105">The General Data Protection Regulation (GDPR) enacted by the European Union can impact your compliance strategy and mandate specific actions to manage user and customer information used in Compliance Manager.</span></span>

## <a name="user-privacy-settings"></a><span data-ttu-id="b0718-106">Параметры конфиденциальности пользователей</span><span class="sxs-lookup"><span data-stu-id="b0718-106">User Privacy settings</span></span>

<span data-ttu-id="b0718-107">Некоторые правила требуют, чтобы организация смогла удалить данные истории пользователей.</span><span class="sxs-lookup"><span data-stu-id="b0718-107">Certain regulations require that an organization must be able to delete user history data.</span></span> <span data-ttu-id="b0718-108">Диспетчер соответствия требованиям предоставляет **функции Параметры** конфиденциальности пользователей, которые позволяют администраторам:</span><span class="sxs-lookup"><span data-stu-id="b0718-108">Compliance Manager provides **User Privacy Settings** functions that allow administrators to:</span></span>
  
- [<span data-ttu-id="b0718-109">искать пользователей;</span><span class="sxs-lookup"><span data-stu-id="b0718-109">Search for a user</span></span>](#search-for-a-user)
- [<span data-ttu-id="b0718-110">экспортировать отчет о журнале данных учетных записей;</span><span class="sxs-lookup"><span data-stu-id="b0718-110">Export a report of account data history</span></span>](#export-a-report-of-account-data-history)
- [<span data-ttu-id="b0718-111">удалять журналы данных пользователей.</span><span class="sxs-lookup"><span data-stu-id="b0718-111">Delete user data history</span></span>](#delete-user-data-history)
  
## <a name="search-for-a-user"></a><span data-ttu-id="b0718-112">Поиск пользователя</span><span class="sxs-lookup"><span data-stu-id="b0718-112">Search for a user</span></span>

<span data-ttu-id="b0718-113">Чтобы найти учетную запись, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="b0718-113">To search for a user account:</span></span>
  
1. <span data-ttu-id="b0718-114">Введите псевдоним электронной почты пользователя (сведения слева от символа @) и выберите доменное имя из списка суффикса домена справа.</span><span class="sxs-lookup"><span data-stu-id="b0718-114">Enter the user email alias (the information to the left of the @ symbol) and choose the domain name from the  domain suffix list on the right.</span></span> <span data-ttu-id="b0718-115">Для организаций с несколькими зарегистрированными доменами дважды проверьте суффикс доменного имени, чтобы убедиться, что это правильно.</span><span class="sxs-lookup"><span data-stu-id="b0718-115">For organizations with multiple registered domains, double check the domain name suffix to ensure that it is correct.</span></span>

2. <span data-ttu-id="b0718-116">Если имя пользователя правильно вписано, выберите **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="b0718-116">When you have the username correctly entered, select **Search**.</span></span>

3. <span data-ttu-id="b0718-117">Для учетных записей пользователей, не возвращенных, на странице отображается **пользователь, не найденный**.</span><span class="sxs-lookup"><span data-stu-id="b0718-117">For user accounts not returned, the page displays **User not found**.</span></span> <span data-ttu-id="b0718-118">Проверьте сведения о адресе электронной почты пользователя и внести необходимые исправления.</span><span class="sxs-lookup"><span data-stu-id="b0718-118">Check the user's email address information and make corrections as necessary.</span></span> <span data-ttu-id="b0718-119">Чтобы повторить, выберите **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="b0718-119">To retry, select **Search**.</span></span>

4. <span data-ttu-id="b0718-120">Для возвращенных учетных записей пользователей текст кнопки изменяется с **"Поиск"** на **"Очистить".**</span><span class="sxs-lookup"><span data-stu-id="b0718-120">For user accounts returned, the text of the button changes from **Search** to **Clear**.</span></span> <span data-ttu-id="b0718-121">Это означает, что возвращенная учетная запись пользователя является операционным контекстом для дополнительных функций и эти функции применяются к этой учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="b0718-121">This indicates that the returned user account is the operating context for the additional functions and that these functions apply to this user account.</span></span>

5. <span data-ttu-id="b0718-122">Чтобы очистить результаты поиска и найти другого пользователя, выберите **Clear**.</span><span class="sxs-lookup"><span data-stu-id="b0718-122">To clear search results and search for a different user, select **Clear**.</span></span>

## <a name="export-a-report-of-account-data-history"></a><span data-ttu-id="b0718-123">Экспорт отчета о журнале данных учетной записи</span><span class="sxs-lookup"><span data-stu-id="b0718-123">Export a report of account data history</span></span>

<span data-ttu-id="b0718-124">Для каждой идентифицированной учетной записи пользователя можно создать отчет о зависимостей, связанных с учетной записью.</span><span class="sxs-lookup"><span data-stu-id="b0718-124">For each user account identified, you can generate a report of dependencies linked to the account.</span></span> <span data-ttu-id="b0718-125">Эта информация позволяет перенаназывают открытые элементы действий или обеспечивают доступ к ранее загруженным доказательствам.</span><span class="sxs-lookup"><span data-stu-id="b0718-125">This information allows you to reassign open Action Items or ensure access to previously uploaded evidence.</span></span>
  
 <span data-ttu-id="b0718-126">Чтобы создать и экспортировать отчет, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="b0718-126">To generate and export a report:</span></span>
  
1. <span data-ttu-id="b0718-127">Выберите **Экспорт** для создания и загрузки отчета элементов действий диспетчера соответствия требованиям, которые в настоящее время назначены возвращенной учетной записи пользователя, и списка документов, загруженных этим пользователем.</span><span class="sxs-lookup"><span data-stu-id="b0718-127">Select **Export** to generate and download a report of the Compliance Manager control Action Items currently assigned to the returned user account, and the list of documents uploaded by that user.</span></span> <span data-ttu-id="b0718-128">Если не назначены действия или загружены документы, в сообщении об ошибке содержится сообщение "Нет данных для этого пользователя".</span><span class="sxs-lookup"><span data-stu-id="b0718-128">If there are no assigned actions or uploaded documents, an error message states "No data for this user".</span></span>

2. <span data-ttu-id="b0718-129">Отчет загружается в фоновом режиме окна активного браузера, если вы не видите всплывающее окно загрузки, которое необходимо проверить в истории загрузки браузера.</span><span class="sxs-lookup"><span data-stu-id="b0718-129">The report downloads in the background of the active browser window — if you don't see a download popup that you want to check your browser download history.</span></span>

3. <span data-ttu-id="b0718-130">Откройте документ, чтобы просмотреть данные отчета.</span><span class="sxs-lookup"><span data-stu-id="b0718-130">Open the document to review the report data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b0718-131">Данные отчета не являются историческим списком, который сохраняет и отображает изменения состояния в истории назначения элемента действия.</span><span class="sxs-lookup"><span data-stu-id="b0718-131">The report data is not a historical list that retains and displays state changes to Action Item assignment history.</span></span> <span data-ttu-id="b0718-132">Созданный отчет — это снимок элементов элементов управления, присвоенных во время запуска отчета (дата и отметка времени, записанная в отчете).</span><span class="sxs-lookup"><span data-stu-id="b0718-132">The generated report is a snapshot of the control Action Items assigned at the time that the report is run (date and time stamp written into the report).</span></span> <span data-ttu-id="b0718-133">Например, любое последующее перенанаменование элементов действия приводит к различным данным отчетов о моментальных снимках, если отчет снова создается для того же пользователя.</span><span class="sxs-lookup"><span data-stu-id="b0718-133">For example, any subsequent reassignment of Action Items result in different snapshot report data if the report is generated again for the same user.</span></span>
  
## <a name="delete-user-data-history"></a><span data-ttu-id="b0718-134">Удаление журнала данных пользователя</span><span class="sxs-lookup"><span data-stu-id="b0718-134">Delete user data history</span></span>

<span data-ttu-id="b0718-135">Задает все элементы управления, задав возвращаемой пользователю "не назначенную".</span><span class="sxs-lookup"><span data-stu-id="b0718-135">Sets all control Action Items assigned to the returned user to 'unassigned'.</span></span> <span data-ttu-id="b0718-136">Задает **загруженные по значению** для любых документов, загруженных возвращенным пользователем, на "удалено пользователем".</span><span class="sxs-lookup"><span data-stu-id="b0718-136">Sets the **uploaded by** value for any documents uploaded by the returned user to 'user removed'.</span></span>
  
<span data-ttu-id="b0718-137">Удаление элемента действия учетной записи пользователя и истории загрузки документов:</span><span class="sxs-lookup"><span data-stu-id="b0718-137">To delete the user account Action Item and document upload history:</span></span>
  
1. <span data-ttu-id="b0718-138">Нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="b0718-138">Select **Delete**.</span></span>

    <span data-ttu-id="b0718-139">Отображается диалоговое окно подтверждения: "Это удаляет все назначения элемента управления и историю отправки документов для *выбранного пользователя. Это действие является постоянным. Вы уверены, что хотите продолжить?*"</span><span class="sxs-lookup"><span data-stu-id="b0718-139">A confirmation dialog is displayed: "*This removes all control Action Item assignments and the document upload history for the selected user. This action is permanent. Are you sure you want to continue?*"</span></span>

2. <span data-ttu-id="b0718-140">Чтобы продолжить выбор **ОК,** в противном случае выберите **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="b0718-140">To continue select **OK**, otherwise select **Cancel**.</span></span>
