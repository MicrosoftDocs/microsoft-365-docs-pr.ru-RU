---
title: Получение доступа к данным бывшего пользователя и создание их резервной копии
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6f7f9ad-e3f5-43de-ade5-e5a0d7531604
description: Сведения о том, как сохранить файлы сотрудника и сообщения электронной почты, когда пользователь покидает организацию.
ms.openlocfilehash: 2bf32aa9e7a3dcc76ae2114240bff07d697ce29d
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387205"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a><span data-ttu-id="e3a30-103">Получение доступа к данным бывшего пользователя и создание их резервной копии</span><span class="sxs-lookup"><span data-stu-id="e3a30-103">Get access to and back up a former user's data</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e3a30-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="e3a30-104">The admin center is changing.</span></span> <span data-ttu-id="e3a30-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="e3a30-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end


<span data-ttu-id="e3a30-106">Когда сотрудник покидает организацию, вам, скорее всего, потребуется получить доступ к своим данным (документам и сообщениям электронной почты) и либо просмотреть, либо создать резервную копию или передать его новому сотруднику.</span><span class="sxs-lookup"><span data-stu-id="e3a30-106">When an employee leaves your organization, you probably want to access their data (documents and emails) and either review it, back it up, or give it to a new employee.</span></span>
  
    
## <a name="access-a-former-users-onedrive-documents"></a><span data-ttu-id="e3a30-107">Доступ к документам OneDrive первого пользователя</span><span class="sxs-lookup"><span data-stu-id="e3a30-107">Access a former user's OneDrive documents</span></span>

<span data-ttu-id="e3a30-108">Если удалить лицензию пользователя, но не удалить учетную запись, вы можете предоставить себе доступ к содержимому в OneDrive пользователя.</span><span class="sxs-lookup"><span data-stu-id="e3a30-108">If you remove a user's license but don't delete the account, you can give yourself access to the content in the user's OneDrive.</span></span> <span data-ttu-id="e3a30-109">При удалении учетной записи пользователя по умолчанию используется 30 дней для доступа к данным первого пользователя в OneDrive.</span><span class="sxs-lookup"><span data-stu-id="e3a30-109">If you delete the user's account, you have 30 days by default to access the former user's OneDrive data.</span></span> <span data-ttu-id="e3a30-110">[Сведения о том, как настроить хранение OneDrive для удаленных пользователей](/onedrive/set-retention).</span><span class="sxs-lookup"><span data-stu-id="e3a30-110">[Learn how to set the OneDrive retention for deleted users](/onedrive/set-retention).</span></span> <span data-ttu-id="e3a30-111">Если вы не [восстановите учетную запись пользователя](/office365/admin/add-users/restore-user) в течение этого времени, его контент OneDrive будет удален.</span><span class="sxs-lookup"><span data-stu-id="e3a30-111">If you don't [restore a user account](/office365/admin/add-users/restore-user) within this time, their OneDrive content is deleted.</span></span> 

<span data-ttu-id="e3a30-112">Чтобы сохранить файлы OneDrive первого пользователя, сначала предоставьте ему доступ к OneDrive, а затем переместите файлы, которые вы хотите сохранить.</span><span class="sxs-lookup"><span data-stu-id="e3a30-112">To preserve a former user's OneDrive files, first give yourself access to their OneDrive, and then move the files you want to keep.</span></span> 

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="e3a30-113">Если вы не используете новый Центр администрирования Microsoft 365, можно включить его с помощью переключателя **Попробовать новый Центр администрирования**, расположенного в верхней части главной страницы.</span><span class="sxs-lookup"><span data-stu-id="e3a30-113">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="e3a30-114">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="e3a30-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="e3a30-115">Выберите пользователя.</span><span class="sxs-lookup"><span data-stu-id="e3a30-115">Select a user.</span></span>

3. <span data-ttu-id="e3a30-116">В правой области выберите **OneDrive**.</span><span class="sxs-lookup"><span data-stu-id="e3a30-116">In the right pane, select **OneDrive**.</span></span> <span data-ttu-id="e3a30-117">В разделе **получить доступ к файлам**выберите команду **создать ссылку на файлы**.</span><span class="sxs-lookup"><span data-stu-id="e3a30-117">Under **Get access to files**, select **Create link to files**.</span></span>

4. <span data-ttu-id="e3a30-118">Выберите ссылку, чтобы открыть расположение файла.</span><span class="sxs-lookup"><span data-stu-id="e3a30-118">Select the link to open the file location.</span></span> <span data-ttu-id="e3a30-119">Скачайте файлы на компьютер или выберите **переместить** или **скопировать, чтобы** переместить или скопировать их в OneDrive или общую библиотеку.</span><span class="sxs-lookup"><span data-stu-id="e3a30-119">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="e3a30-120">Можно переместить или скопировать одновременно до 500 МБ файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="e3a30-120">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="e3a30-121">При перемещении или копировании документов с журналом версий перемещается только последняя версия.</span><span class="sxs-lookup"><span data-stu-id="e3a30-121">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e3a30-122">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="e3a30-122">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="e3a30-123">Выберите пользователя.</span><span class="sxs-lookup"><span data-stu-id="e3a30-123">Select a user.</span></span>

3. <span data-ttu-id="e3a30-124">В правой области разверните узел **Параметры OneDrive**, а затем рядом с пунктом **Access**, выберите пункт **файлы Access**.</span><span class="sxs-lookup"><span data-stu-id="e3a30-124">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="e3a30-125">Выберите ссылку, чтобы открыть расположение файла.</span><span class="sxs-lookup"><span data-stu-id="e3a30-125">Select the link to open the file location.</span></span> <span data-ttu-id="e3a30-126">Скачайте файлы на компьютер или выберите **переместить** или **скопировать, чтобы** переместить или скопировать их в OneDrive или общую библиотеку.</span><span class="sxs-lookup"><span data-stu-id="e3a30-126">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="e3a30-127">Можно переместить или скопировать одновременно до 500 МБ файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="e3a30-127">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="e3a30-128">При перемещении или копировании документов с журналом версий перемещается только последняя версия.</span><span class="sxs-lookup"><span data-stu-id="e3a30-128">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e3a30-129">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="e3a30-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="e3a30-130">Выберите пользователя.</span><span class="sxs-lookup"><span data-stu-id="e3a30-130">Select a user.</span></span>

3. <span data-ttu-id="e3a30-131">В правой области разверните узел **Параметры OneDrive**, а затем рядом с пунктом **Access**, выберите пункт **файлы Access**.</span><span class="sxs-lookup"><span data-stu-id="e3a30-131">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="e3a30-132">Выберите ссылку, чтобы открыть расположение файла.</span><span class="sxs-lookup"><span data-stu-id="e3a30-132">Select the link to open the file location.</span></span> <span data-ttu-id="e3a30-133">Скачайте файлы на компьютер или выберите **переместить** или **скопировать, чтобы** переместить или скопировать их в OneDrive или общую библиотеку.</span><span class="sxs-lookup"><span data-stu-id="e3a30-133">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span>  

> [!NOTE]
> <span data-ttu-id="e3a30-134">Можно переместить или скопировать одновременно до 500 МБ файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="e3a30-134">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="e3a30-135">При перемещении или копировании документов с журналом версий перемещается только последняя версия.</span><span class="sxs-lookup"><span data-stu-id="e3a30-135">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end
    


## <a name="revoke-admin-access-to-a-users-onedrive"></a><span data-ttu-id="e3a30-136">Отзыв административного доступа к OneDrive пользователя</span><span class="sxs-lookup"><span data-stu-id="e3a30-136">Revoke admin access to a user's OneDrive</span></span>

<span data-ttu-id="e3a30-137">Как глобальный администратор вы можете предоставить себе доступ к содержимому в OneDrive пользователя, но вы можете удалить доступ, когда он больше не нужен.</span><span class="sxs-lookup"><span data-stu-id="e3a30-137">As global admin, you can give yourself access to the content in a user's OneDrive, but you may want to remove your access when you no longer need it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e3a30-138">Войдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">центр администрирования</a> как глобальный администратор или администратор SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e3a30-138">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span> 

    <span data-ttu-id="e3a30-139">Если получено сообщение о том, что у вас нет разрешения на доступ к центру администрирования, у вас нет разрешений администратора в Организации.</span><span class="sxs-lookup"><span data-stu-id="e3a30-139">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e3a30-140">Войдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">центр администрирования</a> как глобальный администратор или администратор SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e3a30-140">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="e3a30-141">Если получено сообщение о том, что у вас нет разрешения на доступ к центру администрирования, у вас нет разрешений администратора в Организации.</span><span class="sxs-lookup"><span data-stu-id="e3a30-141">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e3a30-142">Войдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">центр администрирования</a> как глобальный администратор или администратор SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e3a30-142">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="e3a30-143">Если получено сообщение о том, что у вас нет разрешения на доступ к центру администрирования, у вас нет разрешений администратора в Организации.</span><span class="sxs-lookup"><span data-stu-id="e3a30-143">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

2. <span data-ttu-id="e3a30-144">В левой области выберите **центр администрирования** \> **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="e3a30-144">In the left pane, select **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="e3a30-145">(Возможно, потребуется щелкнуть элемент **Показать все**, чтобы увидеть список центров администрирования.)</span><span class="sxs-lookup"><span data-stu-id="e3a30-145">(You might need to select **Show all** to see the list of admin centers.)</span></span>

3. <span data-ttu-id="e3a30-146">Если откроется классическая версия Центра администрирования SharePoint, нажмите кнопку **Открыть** в верхней части страницы, чтобы открыть новый Центр администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e3a30-146">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

4. <span data-ttu-id="e3a30-147">В области слева выберите пункт **Дополнительные функции**.</span><span class="sxs-lookup"><span data-stu-id="e3a30-147">In the left pane, select **More features**.</span></span>

5. <span data-ttu-id="e3a30-148">В разделе **Профили пользователей**нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="e3a30-148">Under **User profiles**, select **Open**.</span></span>

6. <span data-ttu-id="e3a30-149">В разделе **люди**выберите **Управление профилями пользователей**.</span><span class="sxs-lookup"><span data-stu-id="e3a30-149">Under **People**, select **Manage User Profiles**.</span></span>

7. <span data-ttu-id="e3a30-150">Введите имя пользователя и нажмите кнопку **найти**.</span><span class="sxs-lookup"><span data-stu-id="e3a30-150">Enter the user's name and select **Find**.</span></span>

8. <span data-ttu-id="e3a30-151">Щелкните правой кнопкой мыши пользователя, а затем выберите пункт **Управление владельцами семейства веб-сайтов**.</span><span class="sxs-lookup"><span data-stu-id="e3a30-151">Right-click the user, and then choose **Manage site collection owners**.</span></span>

9. <span data-ttu-id="e3a30-152">Удалите человека, которому больше не нужны доступ к данным пользователя, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e3a30-152">Remove the person who no longer needs access to the user's data, and then select **OK**.</span></span>

    
## <a name="access-the-outlook-data-of-a-former-user"></a><span data-ttu-id="e3a30-153">Доступ к данным Outlook предыдущего пользователя</span><span class="sxs-lookup"><span data-stu-id="e3a30-153">Access the Outlook data of a former user</span></span>

<span data-ttu-id="e3a30-154">Чтобы сохранить сообщения электронной почты, календарь, задачи и контакты прежнего сотрудника, экспортируйте данные в файл данных Outlook (PST).</span><span class="sxs-lookup"><span data-stu-id="e3a30-154">To save the email messages, calendar, tasks, and contacts of the former employee, export the information to an Outlook Data File (.pst).</span></span>
  
1. <span data-ttu-id="e3a30-155">[Добавьте сообщение электронной почты бывшего сотрудника](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx) в Outlook (при [сбросе пароля пользователя](reset-passwords.md)его можно задать только вам).</span><span class="sxs-lookup"><span data-stu-id="e3a30-155">[Add the former employee's email](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx) to your Outlook (If you [reset the user's password](reset-passwords.md), you can set it to something only you know.)</span></span>
    
2. <span data-ttu-id="e3a30-156">В Outlook выберите пункт **файл**.</span><span class="sxs-lookup"><span data-stu-id="e3a30-156">In Outlook, select **File**.</span></span>
    
    ![Эта лента выглядит так же, как в Outlook 2016.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. <span data-ttu-id="e3a30-158">Выберите **открыть &amp; Экспорт** \> **импорта и экспорта**.</span><span class="sxs-lookup"><span data-stu-id="e3a30-158">Select **Open &amp; Export** \> **Import/Export**.</span></span>
    
    ![Команда "Импорт и экспорт" в представлении Backstage](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. <span data-ttu-id="e3a30-160">Выберите пункт **Экспорт в файл**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e3a30-160">Select **Export to a file**, and then select **Next**.</span></span>
    
    ![Параметр "Экспорт в файл" в мастере импорта и экспорта](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. <span data-ttu-id="e3a30-162">Выберите **файл данных Outlook (PST)**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e3a30-162">Select **Outlook Data File (.pst)**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="e3a30-163">Выберите учетную запись, которую нужно экспортировать, выбрав имя или адрес электронной почты, например Mailbox — Энн Веилер или anne@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e3a30-163">Select the account you want to export by selecting the name or email address, such as Mailbox - Anne Weiler or anne@contoso.com.</span></span> <span data-ttu-id="e3a30-164">Если вы хотите экспортировать все данные вашей учетной записи, в том числе почту, календарь, контакты, задачи и заметки, установите флажок **Включить вложенные папки** .</span><span class="sxs-lookup"><span data-stu-id="e3a30-164">If you want to export everything in your account, including mail, calendar, contacts, tasks, and notes, make sure the **Include subfolders** check box is selected.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e3a30-p109">Одновременно можно экспортировать только одну учетную запись. Если нужно экспортировать несколько учетных записей, экспортируйте сначала одну учетную запись, а затем повторите эти действия для других учетных записей.</span><span class="sxs-lookup"><span data-stu-id="e3a30-p109">You can export one account at a time. If you want to export multiple accounts, after one account is exported, repeat these steps.</span></span> 
  
    ![Диалоговое окно "Экспорт файла данных Outlook", в котором выбрана верхняя папка и установлен флажок "Включить вложенные папки"](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. <span data-ttu-id="e3a30-168">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e3a30-168">Select **Next**.</span></span>
    
8. <span data-ttu-id="e3a30-169">Нажмите кнопку **Обзор** , чтобы выбрать папку для сохранения файла данных Outlook (PST).</span><span class="sxs-lookup"><span data-stu-id="e3a30-169">Select **Browse** to select where to save the Outlook Data File (.pst).</span></span> <span data-ttu-id="e3a30-170">Введите *имя файла*, а затем нажмите кнопку **ОК** , чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="e3a30-170">Type a  *file name*, and then select **OK** to continue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e3a30-171">Если функция экспорта уже использовалась, здесь будут указаны предыдущие папка и имя файла.</span><span class="sxs-lookup"><span data-stu-id="e3a30-171">If you've used export before, the previous folder location and file name appear.</span></span> <span data-ttu-id="e3a30-172">Введите *другое имя файла* , прежде чем нажать **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="e3a30-172">Type a  *different file name*  before selecting **OK**.</span></span> 
  
9. <span data-ttu-id="e3a30-173">Если данные экспортируются в уже существующий Файл данных Outlook (PST), в разделе **Настройка** укажите, что следует делать, если экспортируемые элементы уже содержатся в этом файле.</span><span class="sxs-lookup"><span data-stu-id="e3a30-173">If you are exporting to an existing Outlook Data File (.pst), under **Options**, specify what to do when exporting items that already exist in the file.</span></span>
    
10. <span data-ttu-id="e3a30-174">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e3a30-174">Select **Finish**.</span></span>
    
<span data-ttu-id="e3a30-175">В Outlook сразу начнется экспорт, если только не требуется создать новый Файл данных Outlook (PST) или экспорт не выполняется в файл, защищенный паролем.</span><span class="sxs-lookup"><span data-stu-id="e3a30-175">Outlook begins the export immediately unless a new Outlook Data File (.pst) is created or a password-protected file is used.</span></span>
  
   - <span data-ttu-id="e3a30-176">Создаваемый Файл данных Outlook (PST) можно защитить паролем.</span><span class="sxs-lookup"><span data-stu-id="e3a30-176">If you're creating an Outlook Data File (.pst), an optional password can help protect the file.</span></span> <span data-ttu-id="e3a30-177">В появившемся диалоговом окне **Создание файла данных Outlook** введите *пароль* в поля **пароль** и **Проверьте пароль** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e3a30-177">When the **Create Outlook Data File** dialog box appears, type the  *password*  in the **Password** and **Verify Password** boxes, and then select **OK**.</span></span> <span data-ttu-id="e3a30-178">В диалоговом окне **пароль к файлу данных Outlook** введите *пароль*, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e3a30-178">In the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
  - <span data-ttu-id="e3a30-179">При экспорте в существующий файл данных Outlook (PST), защищенный паролем, в диалоговом окне **пароль к файлу данных Outlook** введите *пароль*и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e3a30-179">If you're exporting to an existing Outlook Data File (.pst) that is password protected, in the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
<span data-ttu-id="e3a30-180">Узнайте, как [экспортировать или архивировать сообщения электронной почты, контакты и календарь в PST-файл Outlook](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx) в Outlook 2010.</span><span class="sxs-lookup"><span data-stu-id="e3a30-180">See how to [Export or backup email, contacts, and calendar to an Outlook .pst file](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx) in Outlook 2010.</span></span> 
  
  
  > [!NOTE]
  > <span data-ttu-id="e3a30-181">По умолчанию ваша электронная почта доступна в автономном режиме в течение 12 месяцев.</span><span class="sxs-lookup"><span data-stu-id="e3a30-181">By default, your email is available offline for a period of 12 months.</span></span> <span data-ttu-id="e3a30-182">Если необходимо, Узнайте, как [увеличить доступность данных в автономном режиме](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span><span class="sxs-lookup"><span data-stu-id="e3a30-182">If required, see how to [increase the data available offline](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span></span>
 
## <a name="give-another-user-access-to-a-former-users-email"></a><span data-ttu-id="e3a30-183">Предоставление другому пользователю доступа к электронной почте первого пользователя</span><span class="sxs-lookup"><span data-stu-id="e3a30-183">Give another user access to a former user's email</span></span> 

<span data-ttu-id="e3a30-184">Чтобы предоставить другому сотруднику доступ к сообщениям электронной почты, календарю, задачам и контактам бывшего сотрудника, импортируйте информацию в папку "Входящие" Outlook другого сотрудника.</span><span class="sxs-lookup"><span data-stu-id="e3a30-184">To give access to the email messages, calendar, tasks, and contacts of the former employee to another employee, import the information to another employee's Outlook inbox.</span></span>

> [!NOTE]
> <span data-ttu-id="e3a30-185">Вы также можете [преобразовать почтовый ящик бывшего пользователя в общий почтовый ящик](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) или [переадресовать сообщения от бывшего сотрудника другому сотруднику](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span><span class="sxs-lookup"><span data-stu-id="e3a30-185">You can also [convert the former user's mailbox to a shared mailbox](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) or [forward a former employee's email to another employee](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span></span>

  
1. <span data-ttu-id="e3a30-186">В Outlook откройте **файл** \> \*\* &amp; Экспорт\*\* \> **импорта и экспорта**.</span><span class="sxs-lookup"><span data-stu-id="e3a30-186">In Outlook, go to **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>
    
    <span data-ttu-id="e3a30-187">Будет запущен мастер импорта и экспорта.</span><span class="sxs-lookup"><span data-stu-id="e3a30-187">This starts the Import and Export Wizard.</span></span>
    
2. <span data-ttu-id="e3a30-188">Выберите пункт **Импорт из другой программы или файла**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e3a30-188">Select **Import from another program or file**, and then select **Next**.</span></span>
    
    ![Мастер импорта и экспорта](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. <span data-ttu-id="e3a30-190">Выберите **файл данных Outlook (PST)** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e3a30-190">Select **Outlook Data File (.pst)**, and select **Next**.</span></span>
    
4. <span data-ttu-id="e3a30-191">Перейдите к PST-файлу, который вы хотите импортировать.</span><span class="sxs-lookup"><span data-stu-id="e3a30-191">Browse to the .pst file you want to import.</span></span>
    
5. <span data-ttu-id="e3a30-192">В разделе **Параметры**, выберите способ работы с дубликатами.</span><span class="sxs-lookup"><span data-stu-id="e3a30-192">Under **Options**, choose how you want to deal with duplicates</span></span>
    
6. <span data-ttu-id="e3a30-193">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e3a30-193">Select **Next**.</span></span>
    
7. <span data-ttu-id="e3a30-194">Если для файла данных Outlook (PST) был назначен пароль, введите пароль и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e3a30-194">If a password was assigned to the Outlook Data File (.pst), enter the password, and then select **OK**.</span></span>
    
8. <span data-ttu-id="e3a30-195">Настройте параметры импорта элементов.</span><span class="sxs-lookup"><span data-stu-id="e3a30-195">Set the options for importing items.</span></span> <span data-ttu-id="e3a30-196">Обычно изменять параметры по умолчанию нет необходимости.</span><span class="sxs-lookup"><span data-stu-id="e3a30-196">The default settings usually don't need to be changed.</span></span>
    
9. <span data-ttu-id="e3a30-197">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e3a30-197">Select **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="e3a30-198">Действия для доступа к данным OneDrive и электронной почты существующего пользователя не изменяются.</span><span class="sxs-lookup"><span data-stu-id="e3a30-198">The steps remain the same for accessing an existing user's OneDrive and email data.</span></span>
    
> [!TIP]
> <span data-ttu-id="e3a30-199">Если требуется импортировать или восстановить только несколько элементов из файла данных Outlook (PST), можно открыть файл данных Outlook.</span><span class="sxs-lookup"><span data-stu-id="e3a30-199">If you want to import or restore only a few items from an Outlook Data File (.pst), you can open the Outlook Data File.</span></span> <span data-ttu-id="e3a30-200">Затем в области навигации перетащите элементы из папок с файлами данных Outlook в существующие папки Outlook.</span><span class="sxs-lookup"><span data-stu-id="e3a30-200">Then, in the navigation pane, drag the items from Outlook Data File folders to your existing Outlook folders.</span></span> 
  
  
## <a name="related-articles"></a><span data-ttu-id="e3a30-201">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e3a30-201">Related articles</span></span>
[<span data-ttu-id="e3a30-202">Удаление бывшего сотрудника из среды Office 365</span><span class="sxs-lookup"><span data-stu-id="e3a30-202">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="e3a30-203">Добавление и удаление администраторов в учетной записи OneDrive</span><span class="sxs-lookup"><span data-stu-id="e3a30-203">Add and remove admins on a OneDrive account</span></span>](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[<span data-ttu-id="e3a30-204">Восстановление удаленного хранилища OneDrive</span><span class="sxs-lookup"><span data-stu-id="e3a30-204">Restore a deleted OneDrive</span></span>](/onedrive/restore-deleted-onedrive)
  
[<span data-ttu-id="e3a30-205">Хранение и удаление OneDrive</span><span class="sxs-lookup"><span data-stu-id="e3a30-205">OneDrive retention and deletion</span></span>](/onedrive/retention-and-deletion)
  
