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
ms.openlocfilehash: 32f64efb30acb5438e5add8bcb897200951e6362
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780617"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a><span data-ttu-id="cd91a-103">Получение доступа к данным бывшего пользователя и создание их резервной копии</span><span class="sxs-lookup"><span data-stu-id="cd91a-103">Get access to and back up a former user's data</span></span>


<span data-ttu-id="cd91a-104">Когда сотрудник покидает организацию, вам, скорее всего, потребуется получить доступ к своим данным (документам и сообщениям электронной почты) и либо просмотреть, либо создать резервную копию или передать его новому сотруднику.</span><span class="sxs-lookup"><span data-stu-id="cd91a-104">When an employee leaves your organization, you probably want to access their data (documents and emails) and either review it, back it up, or give it to a new employee.</span></span>
  
    
## <a name="access-a-former-users-onedrive-documents"></a><span data-ttu-id="cd91a-105">Доступ к документам OneDrive первого пользователя</span><span class="sxs-lookup"><span data-stu-id="cd91a-105">Access a former user's OneDrive documents</span></span>

<span data-ttu-id="cd91a-106">Если удалить лицензию пользователя, но не удалить учетную запись, вы можете предоставить себе доступ к содержимому в OneDrive пользователя.</span><span class="sxs-lookup"><span data-stu-id="cd91a-106">If you remove a user's license but don't delete the account, you can give yourself access to the content in the user's OneDrive.</span></span> <span data-ttu-id="cd91a-107">При удалении учетной записи пользователя по умолчанию используется 30 дней для доступа к данным первого пользователя в OneDrive.</span><span class="sxs-lookup"><span data-stu-id="cd91a-107">If you delete the user's account, you have 30 days by default to access the former user's OneDrive data.</span></span> <span data-ttu-id="cd91a-108">[Сведения о том, как настроить хранение OneDrive для удаленных пользователей](/onedrive/set-retention).</span><span class="sxs-lookup"><span data-stu-id="cd91a-108">[Learn how to set the OneDrive retention for deleted users](/onedrive/set-retention).</span></span> <span data-ttu-id="cd91a-109">Если вы не [восстановите учетную запись пользователя](/office365/admin/add-users/restore-user) в течение этого времени, его контент OneDrive будет удален.</span><span class="sxs-lookup"><span data-stu-id="cd91a-109">If you don't [restore a user account](/office365/admin/add-users/restore-user) within this time, their OneDrive content is deleted.</span></span> 

<span data-ttu-id="cd91a-110">Чтобы сохранить файлы OneDrive первого пользователя, сначала предоставьте ему доступ к OneDrive, а затем переместите файлы, которые вы хотите сохранить.</span><span class="sxs-lookup"><span data-stu-id="cd91a-110">To preserve a former user's OneDrive files, first give yourself access to their OneDrive, and then move the files you want to keep.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="cd91a-111">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="cd91a-111">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="cd91a-112">Выберите пользователя.</span><span class="sxs-lookup"><span data-stu-id="cd91a-112">Select a user.</span></span>

3. <span data-ttu-id="cd91a-113">В правой области выберите **OneDrive**.</span><span class="sxs-lookup"><span data-stu-id="cd91a-113">In the right pane, select **OneDrive**.</span></span> <span data-ttu-id="cd91a-114">В разделе **получить доступ к файлам**выберите команду **создать ссылку на файлы**.</span><span class="sxs-lookup"><span data-stu-id="cd91a-114">Under **Get access to files**, select **Create link to files**.</span></span>

4. <span data-ttu-id="cd91a-115">Выберите ссылку, чтобы открыть расположение файла.</span><span class="sxs-lookup"><span data-stu-id="cd91a-115">Select the link to open the file location.</span></span> <span data-ttu-id="cd91a-116">Скачайте файлы на компьютер или выберите **переместить** или **скопировать, чтобы** переместить или скопировать их в OneDrive или общую библиотеку.</span><span class="sxs-lookup"><span data-stu-id="cd91a-116">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="cd91a-117">Можно переместить или скопировать одновременно до 500 МБ файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="cd91a-117">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="cd91a-118">При перемещении или копировании документов с журналом версий перемещается только последняя версия.</span><span class="sxs-lookup"><span data-stu-id="cd91a-118">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="cd91a-119">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="cd91a-119">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="cd91a-120">Выберите пользователя.</span><span class="sxs-lookup"><span data-stu-id="cd91a-120">Select a user.</span></span>

3. <span data-ttu-id="cd91a-121">В правой области разверните узел **Параметры OneDrive**, а затем рядом с пунктом **Access**, выберите пункт **файлы Access**.</span><span class="sxs-lookup"><span data-stu-id="cd91a-121">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="cd91a-122">Выберите ссылку, чтобы открыть расположение файла.</span><span class="sxs-lookup"><span data-stu-id="cd91a-122">Select the link to open the file location.</span></span> <span data-ttu-id="cd91a-123">Скачайте файлы на компьютер или выберите **переместить** или **скопировать, чтобы** переместить или скопировать их в OneDrive или общую библиотеку.</span><span class="sxs-lookup"><span data-stu-id="cd91a-123">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="cd91a-124">Можно переместить или скопировать одновременно до 500 МБ файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="cd91a-124">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="cd91a-125">При перемещении или копировании документов с журналом версий перемещается только последняя версия.</span><span class="sxs-lookup"><span data-stu-id="cd91a-125">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="cd91a-126">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="cd91a-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="cd91a-127">Выберите пользователя.</span><span class="sxs-lookup"><span data-stu-id="cd91a-127">Select a user.</span></span>

3. <span data-ttu-id="cd91a-128">В правой области разверните узел **Параметры OneDrive**, а затем рядом с пунктом **Access**, выберите пункт **файлы Access**.</span><span class="sxs-lookup"><span data-stu-id="cd91a-128">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="cd91a-129">Выберите ссылку, чтобы открыть расположение файла.</span><span class="sxs-lookup"><span data-stu-id="cd91a-129">Select the link to open the file location.</span></span> <span data-ttu-id="cd91a-130">Скачайте файлы на компьютер или выберите **переместить** или **скопировать, чтобы** переместить или скопировать их в OneDrive или общую библиотеку.</span><span class="sxs-lookup"><span data-stu-id="cd91a-130">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span>  

> [!NOTE]
> <span data-ttu-id="cd91a-131">Можно переместить или скопировать одновременно до 500 МБ файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="cd91a-131">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="cd91a-132">При перемещении или копировании документов с журналом версий перемещается только последняя версия.</span><span class="sxs-lookup"><span data-stu-id="cd91a-132">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end
    


## <a name="revoke-admin-access-to-a-users-onedrive"></a><span data-ttu-id="cd91a-133">Отзыв административного доступа к OneDrive пользователя</span><span class="sxs-lookup"><span data-stu-id="cd91a-133">Revoke admin access to a user's OneDrive</span></span>

<span data-ttu-id="cd91a-134">Как глобальный администратор вы можете предоставить себе доступ к содержимому в OneDrive пользователя, но вы можете удалить доступ, когда он больше не нужен.</span><span class="sxs-lookup"><span data-stu-id="cd91a-134">As global admin, you can give yourself access to the content in a user's OneDrive, but you may want to remove your access when you no longer need it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="cd91a-135">Войдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">центр администрирования</a> как глобальный администратор или администратор SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cd91a-135">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span> 

    <span data-ttu-id="cd91a-136">Если получено сообщение о том, что у вас нет разрешения на доступ к центру администрирования, у вас нет разрешений администратора в Организации.</span><span class="sxs-lookup"><span data-stu-id="cd91a-136">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="cd91a-137">Войдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">центр администрирования</a> как глобальный администратор или администратор SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cd91a-137">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="cd91a-138">Если получено сообщение о том, что у вас нет разрешения на доступ к центру администрирования, у вас нет разрешений администратора в Организации.</span><span class="sxs-lookup"><span data-stu-id="cd91a-138">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="cd91a-139">Войдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">центр администрирования</a> как глобальный администратор или администратор SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cd91a-139">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="cd91a-140">Если получено сообщение о том, что у вас нет разрешения на доступ к центру администрирования, у вас нет разрешений администратора в Организации.</span><span class="sxs-lookup"><span data-stu-id="cd91a-140">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

2. <span data-ttu-id="cd91a-141">В левой области выберите **центр администрирования** \> **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="cd91a-141">In the left pane, select **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="cd91a-142">(Возможно, потребуется щелкнуть элемент **Показать все**, чтобы увидеть список центров администрирования.)</span><span class="sxs-lookup"><span data-stu-id="cd91a-142">(You might need to select **Show all** to see the list of admin centers.)</span></span>

3. <span data-ttu-id="cd91a-143">Если отображается классический центр администрирования SharePoint, выберите **открыть его сейчас** в верхней части страницы, чтобы открыть центр администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cd91a-143">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the SharePoint admin center.</span></span>

4. <span data-ttu-id="cd91a-144">В области слева выберите пункт **Дополнительные функции**.</span><span class="sxs-lookup"><span data-stu-id="cd91a-144">In the left pane, select **More features**.</span></span>

5. <span data-ttu-id="cd91a-145">В разделе **Профили пользователей**нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="cd91a-145">Under **User profiles**, select **Open**.</span></span>

6. <span data-ttu-id="cd91a-146">В разделе **люди**выберите **Управление профилями пользователей**.</span><span class="sxs-lookup"><span data-stu-id="cd91a-146">Under **People**, select **Manage User Profiles**.</span></span>

7. <span data-ttu-id="cd91a-147">Введите имя пользователя и нажмите кнопку **найти**.</span><span class="sxs-lookup"><span data-stu-id="cd91a-147">Enter the user's name and select **Find**.</span></span>

8. <span data-ttu-id="cd91a-148">Щелкните правой кнопкой мыши пользователя, а затем выберите пункт **Управление владельцами семейства веб-сайтов**.</span><span class="sxs-lookup"><span data-stu-id="cd91a-148">Right-click the user, and then choose **Manage site collection owners**.</span></span>

9. <span data-ttu-id="cd91a-149">Удалите человека, которому больше не нужны доступ к данным пользователя, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cd91a-149">Remove the person who no longer needs access to the user's data, and then select **OK**.</span></span>

    
## <a name="access-the-outlook-data-of-a-former-user"></a><span data-ttu-id="cd91a-150">Доступ к данным Outlook предыдущего пользователя</span><span class="sxs-lookup"><span data-stu-id="cd91a-150">Access the Outlook data of a former user</span></span>

<span data-ttu-id="cd91a-151">Чтобы сохранить сообщения электронной почты, календарь, задачи и контакты прежнего сотрудника, экспортируйте данные в файл данных Outlook (PST).</span><span class="sxs-lookup"><span data-stu-id="cd91a-151">To save the email messages, calendar, tasks, and contacts of the former employee, export the information to an Outlook Data File (.pst).</span></span>
  
1. <span data-ttu-id="cd91a-152">[Добавьте сообщение электронной почты бывшего сотрудника](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) в Outlook (при [сбросе пароля пользователя](reset-passwords.md)его можно задать только вам).</span><span class="sxs-lookup"><span data-stu-id="cd91a-152">[Add the former employee's email](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) to your Outlook (If you [reset the user's password](reset-passwords.md), you can set it to something only you know.)</span></span>
    
2. <span data-ttu-id="cd91a-153">В Outlook выберите пункт **файл**.</span><span class="sxs-lookup"><span data-stu-id="cd91a-153">In Outlook, select **File**.</span></span>
    
    ![Эта лента выглядит так же, как в Outlook 2016.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. <span data-ttu-id="cd91a-155">Выберите **открыть &amp; Экспорт** \> **импорта и экспорта**.</span><span class="sxs-lookup"><span data-stu-id="cd91a-155">Select **Open &amp; Export** \> **Import/Export**.</span></span>
    
    ![Команда "Импорт и экспорт" в представлении Backstage](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. <span data-ttu-id="cd91a-157">Выберите пункт **Экспорт в файл**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cd91a-157">Select **Export to a file**, and then select **Next**.</span></span>
    
    ![Параметр "Экспорт в файл" в мастере импорта и экспорта](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. <span data-ttu-id="cd91a-159">Выберите **файл данных Outlook (PST)**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cd91a-159">Select **Outlook Data File (.pst)**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="cd91a-160">Выберите учетную запись, которую нужно экспортировать, выбрав имя или адрес электронной почты, например Mailbox — Энн Веилер или anne@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cd91a-160">Select the account you want to export by selecting the name or email address, such as Mailbox - Anne Weiler or anne@contoso.com.</span></span> <span data-ttu-id="cd91a-161">Если вы хотите экспортировать все данные вашей учетной записи, в том числе почту, календарь, контакты, задачи и заметки, установите флажок **Включить вложенные папки** .</span><span class="sxs-lookup"><span data-stu-id="cd91a-161">If you want to export everything in your account, including mail, calendar, contacts, tasks, and notes, make sure the **Include subfolders** check box is selected.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="cd91a-162">You can export one account at a time.</span><span class="sxs-lookup"><span data-stu-id="cd91a-162">You can export one account at a time.</span></span> <span data-ttu-id="cd91a-163">If you want to export multiple accounts, after one account is exported, repeat these steps.</span><span class="sxs-lookup"><span data-stu-id="cd91a-163">If you want to export multiple accounts, after one account is exported, repeat these steps.</span></span> 
  
    ![Диалоговое окно "Экспорт файла данных Outlook", в котором выбрана верхняя папка и установлен флажок "Включить вложенные папки"](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. <span data-ttu-id="cd91a-165">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cd91a-165">Select **Next**.</span></span>
    
8. <span data-ttu-id="cd91a-166">Нажмите кнопку **Обзор** , чтобы выбрать папку для сохранения файла данных Outlook (PST).</span><span class="sxs-lookup"><span data-stu-id="cd91a-166">Select **Browse** to select where to save the Outlook Data File (.pst).</span></span> <span data-ttu-id="cd91a-167">Введите *имя файла*, а затем нажмите кнопку **ОК** , чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="cd91a-167">Type a  *file name*, and then select **OK** to continue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="cd91a-168">Если функция экспорта уже использовалась, здесь будут указаны предыдущие папка и имя файла.</span><span class="sxs-lookup"><span data-stu-id="cd91a-168">If you've used export before, the previous folder location and file name appear.</span></span> <span data-ttu-id="cd91a-169">Введите *другое имя файла* , прежде чем нажать **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="cd91a-169">Type a  *different file name*  before selecting **OK**.</span></span> 
  
9. <span data-ttu-id="cd91a-170">Если данные экспортируются в уже существующий Файл данных Outlook (PST), в разделе **Настройка** укажите, что следует делать, если экспортируемые элементы уже содержатся в этом файле.</span><span class="sxs-lookup"><span data-stu-id="cd91a-170">If you are exporting to an existing Outlook Data File (.pst), under **Options**, specify what to do when exporting items that already exist in the file.</span></span>
    
10. <span data-ttu-id="cd91a-171">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="cd91a-171">Select **Finish**.</span></span>
    
<span data-ttu-id="cd91a-172">В Outlook сразу начнется экспорт, если только не требуется создать новый Файл данных Outlook (PST) или экспорт не выполняется в файл, защищенный паролем.</span><span class="sxs-lookup"><span data-stu-id="cd91a-172">Outlook begins the export immediately unless a new Outlook Data File (.pst) is created or a password-protected file is used.</span></span>
  
   - <span data-ttu-id="cd91a-173">Создаваемый Файл данных Outlook (PST) можно защитить паролем.</span><span class="sxs-lookup"><span data-stu-id="cd91a-173">If you're creating an Outlook Data File (.pst), an optional password can help protect the file.</span></span> <span data-ttu-id="cd91a-174">В появившемся диалоговом окне **Создание файла данных Outlook** введите *пароль* в поля **пароль** и **Проверьте пароль** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cd91a-174">When the **Create Outlook Data File** dialog box appears, type the  *password*  in the **Password** and **Verify Password** boxes, and then select **OK**.</span></span> <span data-ttu-id="cd91a-175">В диалоговом окне **пароль к файлу данных Outlook** введите *пароль*, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cd91a-175">In the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
  - <span data-ttu-id="cd91a-176">При экспорте в существующий файл данных Outlook (PST), защищенный паролем, в диалоговом окне **пароль к файлу данных Outlook** введите *пароль*и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cd91a-176">If you're exporting to an existing Outlook Data File (.pst) that is password protected, in the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
<span data-ttu-id="cd91a-177">Узнайте, как [экспортировать или архивировать сообщения электронной почты, контакты и календарь в PST-файл Outlook](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) в Outlook 2010.</span><span class="sxs-lookup"><span data-stu-id="cd91a-177">See how to [Export or backup email, contacts, and calendar to an Outlook .pst file](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) in Outlook 2010.</span></span> 
  
  
  > [!NOTE]
  > <span data-ttu-id="cd91a-178">По умолчанию ваша электронная почта доступна в автономном режиме в течение 12 месяцев.</span><span class="sxs-lookup"><span data-stu-id="cd91a-178">By default, your email is available offline for a period of 12 months.</span></span> <span data-ttu-id="cd91a-179">Если необходимо, Узнайте, как [увеличить доступность данных в автономном режиме](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span><span class="sxs-lookup"><span data-stu-id="cd91a-179">If required, see how to [increase the data available offline](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span></span>
 
## <a name="give-another-user-access-to-a-former-users-email"></a><span data-ttu-id="cd91a-180">Предоставление другому пользователю доступа к электронной почте первого пользователя</span><span class="sxs-lookup"><span data-stu-id="cd91a-180">Give another user access to a former user's email</span></span> 

<span data-ttu-id="cd91a-181">Чтобы предоставить другому сотруднику доступ к сообщениям электронной почты, календарю, задачам и контактам бывшего сотрудника, импортируйте информацию в папку "Входящие" Outlook другого сотрудника.</span><span class="sxs-lookup"><span data-stu-id="cd91a-181">To give access to the email messages, calendar, tasks, and contacts of the former employee to another employee, import the information to another employee's Outlook inbox.</span></span>

> [!NOTE]
> <span data-ttu-id="cd91a-182">Вы также можете [преобразовать почтовый ящик бывшего пользователя в общий почтовый ящик](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) или [переадресовать сообщения от бывшего сотрудника другому сотруднику](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span><span class="sxs-lookup"><span data-stu-id="cd91a-182">You can also [convert the former user's mailbox to a shared mailbox](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) or [forward a former employee's email to another employee](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span></span>

  
1. <span data-ttu-id="cd91a-183">В Outlook откройте **файл** \> \*\* &amp; Экспорт\*\* \> **импорта и экспорта**.</span><span class="sxs-lookup"><span data-stu-id="cd91a-183">In Outlook, go to **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>
    
    <span data-ttu-id="cd91a-184">Будет запущен мастер импорта и экспорта.</span><span class="sxs-lookup"><span data-stu-id="cd91a-184">This starts the Import and Export Wizard.</span></span>
    
2. <span data-ttu-id="cd91a-185">Выберите пункт **Импорт из другой программы или файла**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cd91a-185">Select **Import from another program or file**, and then select **Next**.</span></span>
    
    ![Мастер импорта и экспорта](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. <span data-ttu-id="cd91a-187">Выберите **файл данных Outlook (PST)** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cd91a-187">Select **Outlook Data File (.pst)**, and select **Next**.</span></span>
    
4. <span data-ttu-id="cd91a-188">Перейдите к PST-файлу, который вы хотите импортировать.</span><span class="sxs-lookup"><span data-stu-id="cd91a-188">Browse to the .pst file you want to import.</span></span>
    
5. <span data-ttu-id="cd91a-189">В разделе **Параметры**, выберите способ работы с дубликатами.</span><span class="sxs-lookup"><span data-stu-id="cd91a-189">Under **Options**, choose how you want to deal with duplicates</span></span>
    
6. <span data-ttu-id="cd91a-190">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cd91a-190">Select **Next**.</span></span>
    
7. <span data-ttu-id="cd91a-191">Если для файла данных Outlook (PST) был назначен пароль, введите пароль и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cd91a-191">If a password was assigned to the Outlook Data File (.pst), enter the password, and then select **OK**.</span></span>
    
8. <span data-ttu-id="cd91a-192">Настройте параметры импорта элементов.</span><span class="sxs-lookup"><span data-stu-id="cd91a-192">Set the options for importing items.</span></span> <span data-ttu-id="cd91a-193">Обычно изменять параметры по умолчанию нет необходимости.</span><span class="sxs-lookup"><span data-stu-id="cd91a-193">The default settings usually don't need to be changed.</span></span>
    
9. <span data-ttu-id="cd91a-194">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="cd91a-194">Select **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="cd91a-195">Действия для доступа к данным OneDrive и электронной почты существующего пользователя не изменяются.</span><span class="sxs-lookup"><span data-stu-id="cd91a-195">The steps remain the same for accessing an existing user's OneDrive and email data.</span></span>
    
> [!TIP]
> <span data-ttu-id="cd91a-196">Если требуется импортировать или восстановить только несколько элементов из файла данных Outlook (PST), можно открыть файл данных Outlook.</span><span class="sxs-lookup"><span data-stu-id="cd91a-196">If you want to import or restore only a few items from an Outlook Data File (.pst), you can open the Outlook Data File.</span></span> <span data-ttu-id="cd91a-197">Затем в области навигации перетащите элементы из папок с файлами данных Outlook в существующие папки Outlook.</span><span class="sxs-lookup"><span data-stu-id="cd91a-197">Then, in the navigation pane, drag the items from Outlook Data File folders to your existing Outlook folders.</span></span> 
  
  
## <a name="related-articles"></a><span data-ttu-id="cd91a-198">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="cd91a-198">Related articles</span></span>
[<span data-ttu-id="cd91a-199">Удаление бывшего сотрудника из среды Office 365</span><span class="sxs-lookup"><span data-stu-id="cd91a-199">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="cd91a-200">Добавление и удаление администраторов в учетной записи OneDrive</span><span class="sxs-lookup"><span data-stu-id="cd91a-200">Add and remove admins on a OneDrive account</span></span>](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[<span data-ttu-id="cd91a-201">Восстановление удаленного хранилища OneDrive</span><span class="sxs-lookup"><span data-stu-id="cd91a-201">Restore a deleted OneDrive</span></span>](/onedrive/restore-deleted-onedrive)
  
[<span data-ttu-id="cd91a-202">Хранение и удаление OneDrive</span><span class="sxs-lookup"><span data-stu-id="cd91a-202">OneDrive retention and deletion</span></span>](/onedrive/retention-and-deletion)
  
