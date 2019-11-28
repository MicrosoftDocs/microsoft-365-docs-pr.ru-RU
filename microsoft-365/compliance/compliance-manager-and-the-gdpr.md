---
title: Диспетчер соответствия требованиям (Майкрософт) и GDPR
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
description: Диспетчер соответствия требованиям Майкрософт — бесплатное средство оценки рисков на основе рабочих процессов на портале доверия службы Майкрософт. Диспетчер соответствия требованиям позволяет отслеживать, назначать и проверять нормативные действия, связанные с облачными службами Майкрософт.
ms.openlocfilehash: 0d2edb2f7362fa8e8bea6ae82c417f61072bccff
ms.sourcegitcommit: e386037c9cc335c86896dc153344850735afbccd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/27/2019
ms.locfileid: "39633618"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a><span data-ttu-id="fe4b3-104">Диспетчер соответствия требованиям (Майкрософт) и GDPR</span><span class="sxs-lookup"><span data-stu-id="fe4b3-104">Microsoft Compliance Manager and the GDPR</span></span>

<span data-ttu-id="fe4b3-105">Общие требования к защите данных (GDPR), включенные в Европейский союз, могут повлиять на стратегию соответствия требованиям и выполнять определенные действия для управления сведениями о пользователях и клиентах, используемых в диспетчере соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="fe4b3-105">The General Data Protection Regulation (GDPR) enacted by the European Union can impact your compliance strategy and mandate specific actions to manage user and customer information used in Compliance Manager.</span></span>

## <a name="user-privacy-settings"></a><span data-ttu-id="fe4b3-106">Параметры конфиденциальности пользователей</span><span class="sxs-lookup"><span data-stu-id="fe4b3-106">User Privacy settings</span></span>

<span data-ttu-id="fe4b3-107">Для определенных нормативных требований необходимо, чтобы Организация могла удалять данные журнала пользователей.</span><span class="sxs-lookup"><span data-stu-id="fe4b3-107">Certain regulations require that an organization must be able to delete user history data.</span></span> <span data-ttu-id="fe4b3-108">Диспетчер соответствия требованиям предоставляет функции **параметров конфиденциальности пользователей** , позволяющие администраторам выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="fe4b3-108">Compliance Manager provides **User Privacy Settings** functions that allow administrators to:</span></span>
  
- [<span data-ttu-id="fe4b3-109">искать пользователей;</span><span class="sxs-lookup"><span data-stu-id="fe4b3-109">Search for a user</span></span>](#search-for-a-user)
- [<span data-ttu-id="fe4b3-110">экспортировать отчет о журнале данных учетных записей;</span><span class="sxs-lookup"><span data-stu-id="fe4b3-110">Export a report of account data history</span></span>](#export-a-report-of-account-data-history)
- [<span data-ttu-id="fe4b3-111">удалять журналы данных пользователей.</span><span class="sxs-lookup"><span data-stu-id="fe4b3-111">Delete user data history</span></span>](#delete-user-data-history)
  
## <a name="search-for-a-user"></a><span data-ttu-id="fe4b3-112">Поиск пользователя</span><span class="sxs-lookup"><span data-stu-id="fe4b3-112">Search for a user</span></span>

<span data-ttu-id="fe4b3-113">Чтобы найти учетную запись, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="fe4b3-113">To search for a user account:</span></span>
  
1. <span data-ttu-id="fe4b3-114">Введите псевдоним электронной почты пользователя (сведения слева от символа @) и выберите имя домена в списке суффикс домена справа.</span><span class="sxs-lookup"><span data-stu-id="fe4b3-114">Enter the user email alias (the information to the left of the @ symbol) and choose the domain name from the  domain suffix list on the right.</span></span> <span data-ttu-id="fe4b3-115">Для организаций с несколькими зарегистрированными доменами дважды проверьте суффикс доменных имен, чтобы убедиться в их правильности.</span><span class="sxs-lookup"><span data-stu-id="fe4b3-115">For organizations with multiple registered domains, double check the domain name suffix to ensure that it is correct.</span></span>

2. <span data-ttu-id="fe4b3-116">Когда введено правильное имя пользователя, выберите **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="fe4b3-116">When you have the username correctly entered, select **Search**.</span></span>

3. <span data-ttu-id="fe4b3-117">Если учетные записи пользователей не возвращаются, на странице отображается значение " **пользователь не найден**".</span><span class="sxs-lookup"><span data-stu-id="fe4b3-117">For user accounts not returned, the page displays **User not found**.</span></span> <span data-ttu-id="fe4b3-118">Проверьте сведения об адресе электронной почты пользователя и внесите необходимые исправления.</span><span class="sxs-lookup"><span data-stu-id="fe4b3-118">Check the user's email address information and make corrections as necessary.</span></span> <span data-ttu-id="fe4b3-119">Чтобы повторить попытку, нажмите кнопку **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="fe4b3-119">To retry, select **Search**.</span></span>

4. <span data-ttu-id="fe4b3-120">Для возвращенных учетных записей пользователей текст кнопки меняется с " **Поиск** " на " **очистить**".</span><span class="sxs-lookup"><span data-stu-id="fe4b3-120">For user accounts returned, the text of the button changes from **Search** to **Clear**.</span></span> <span data-ttu-id="fe4b3-121">Это означает, что Возвращенная учетная запись пользователя является рабочим контекстом для дополнительных функций, и эти функции применяются к этой учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="fe4b3-121">This indicates that the returned user account is the operating context for the additional functions and that these functions apply to this user account.</span></span>

5. <span data-ttu-id="fe4b3-122">Чтобы очистить результаты поиска и выполнить поиск другого пользователя, нажмите кнопку **очистить**.</span><span class="sxs-lookup"><span data-stu-id="fe4b3-122">To clear search results and search for a different user, select **Clear**.</span></span>

## <a name="export-a-report-of-account-data-history"></a><span data-ttu-id="fe4b3-123">Экспорт отчета о журнале данных учетной записи</span><span class="sxs-lookup"><span data-stu-id="fe4b3-123">Export a report of account data history</span></span>

<span data-ttu-id="fe4b3-124">Для каждой определенной учетной записи пользователя можно создать отчет о зависимостях, связанных с учетной записью.</span><span class="sxs-lookup"><span data-stu-id="fe4b3-124">For each user account identified, you can generate a report of dependencies linked to the account.</span></span> <span data-ttu-id="fe4b3-125">Эта информация позволяет переназначить открытые элементы действий или обеспечить доступ к ранее загруженным доказательствам.</span><span class="sxs-lookup"><span data-stu-id="fe4b3-125">This information allows you to reassign open Action Items or ensure access to previously uploaded evidence.</span></span>
  
 <span data-ttu-id="fe4b3-126">Чтобы создать и экспортировать отчет, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="fe4b3-126">To generate and export a report:</span></span>
  
1. <span data-ttu-id="fe4b3-127">Выберите пункт **Экспорт** , чтобы создать и скачать отчет о элементах действий управления диспетчера соответствия требованиям, назначенных для возвращенной учетной записи пользователя, и список документов, отправленных этим пользователем.</span><span class="sxs-lookup"><span data-stu-id="fe4b3-127">Select **Export** to generate and download a report of the Compliance Manager control Action Items currently assigned to the returned user account, and the list of documents uploaded by that user.</span></span> <span data-ttu-id="fe4b3-128">Если нет назначенных действий или отправленных документов, в сообщении об ошибке указывается "нет данных для этого пользователя".</span><span class="sxs-lookup"><span data-stu-id="fe4b3-128">If there are no assigned actions or uploaded documents, an error message states "No data for this user".</span></span>

2. <span data-ttu-id="fe4b3-129">Отчет загружается в фоновом окне активного браузера, если вы не видите всплывающее окно загрузки, которое вы хотите проверить в журнале скачивания браузера.</span><span class="sxs-lookup"><span data-stu-id="fe4b3-129">The report downloads in the background of the active browser window — if you don't see a download popup that you want to check your browser download history.</span></span>

3. <span data-ttu-id="fe4b3-130">Откройте документ, чтобы просмотреть данные отчета.</span><span class="sxs-lookup"><span data-stu-id="fe4b3-130">Open the document to review the report data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fe4b3-131">Данные отчета не являются архивным списком, который сохраняет и отображает изменения состояния журнала назначения элементов действий.</span><span class="sxs-lookup"><span data-stu-id="fe4b3-131">The report data is not a historical list that retains and displays state changes to Action Item assignment history.</span></span> <span data-ttu-id="fe4b3-132">Созданный отчет — это снимок элементов управления, назначенных во время запуска отчета (Дата и отметка времени, записанные в отчет).</span><span class="sxs-lookup"><span data-stu-id="fe4b3-132">The generated report is a snapshot of the control Action Items assigned at the time that the report is run (date and time stamp written into the report).</span></span> <span data-ttu-id="fe4b3-133">Например, любое последующее переопределение элементов Action приводит к различным данным отчета о моментальном снимке, если отчет создается для одного и того же пользователя.</span><span class="sxs-lookup"><span data-stu-id="fe4b3-133">For example, any subsequent reassignment of Action Items result in different snapshot report data if the report is generated again for the same user.</span></span>
  
## <a name="delete-user-data-history"></a><span data-ttu-id="fe4b3-134">Удаление журнала данных пользователя</span><span class="sxs-lookup"><span data-stu-id="fe4b3-134">Delete user data history</span></span>

<span data-ttu-id="fe4b3-135">Задает для всех элементов управления, назначенных для возвращенного пользователя, значение "не назначено".</span><span class="sxs-lookup"><span data-stu-id="fe4b3-135">Sets all control Action Items assigned to the returned user to 'unassigned'.</span></span> <span data-ttu-id="fe4b3-136">Задает значение, переданное **по** значению для всех документов, отправленных возвращенным пользователем, в папку "пользователь удален".</span><span class="sxs-lookup"><span data-stu-id="fe4b3-136">Sets the **uploaded by** value for any documents uploaded by the returned user to 'user removed'.</span></span>
  
<span data-ttu-id="fe4b3-137">Удаление элемента действия учетной записи пользователя и журнала отправки документов:</span><span class="sxs-lookup"><span data-stu-id="fe4b3-137">To delete the user account Action Item and document upload history:</span></span>
  
1. <span data-ttu-id="fe4b3-138">Нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="fe4b3-138">Select **Delete**.</span></span>

    <span data-ttu-id="fe4b3-139">Откроется диалоговое окно подтверждения: "*это приведет к удалению всех назначенных элементов действий управления и журнала отправки документов для выбранного пользователя. Это действие необратимо. Вы действительно хотите продолжить?*"</span><span class="sxs-lookup"><span data-stu-id="fe4b3-139">A confirmation dialog is displayed: "*This removes all control Action Item assignments and the document upload history for the selected user. This action is permanent. Are you sure you want to continue?*"</span></span>

2. <span data-ttu-id="fe4b3-140">Чтобы продолжить, нажмите кнопку **ОК**, в противном случае нажмите **кнопку Отмена**.</span><span class="sxs-lookup"><span data-stu-id="fe4b3-140">To continue select **OK**, otherwise select **Cancel**.</span></span>
