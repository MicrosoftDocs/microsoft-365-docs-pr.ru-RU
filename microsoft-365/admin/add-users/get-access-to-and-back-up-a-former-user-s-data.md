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
description: Узнайте, как сохранить файлы и электронные почты сотрудника, когда человек покидает организацию.
ms.openlocfilehash: 17911e4a4551bba07d2c2ad034941bba737dcc1d
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51755610"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a><span data-ttu-id="1ce21-103">Получение доступа к данным бывшего пользователя и создание их резервной копии</span><span class="sxs-lookup"><span data-stu-id="1ce21-103">Get access to and back up a former user's data</span></span>


<span data-ttu-id="1ce21-104">Когда сотрудник покидает организацию, вы, вероятно, захотите получить доступ к своим данным (документам и электронным письмам) и просмотреть их, оторудить или предоставить новому сотруднику.</span><span class="sxs-lookup"><span data-stu-id="1ce21-104">When an employee leaves your organization, you probably want to access their data (documents and emails) and either review it, back it up, or give it to a new employee.</span></span>
  
    
## <a name="access-a-former-users-onedrive-documents"></a><span data-ttu-id="1ce21-105">Доступ к документам OneDrive бывшего пользователя</span><span class="sxs-lookup"><span data-stu-id="1ce21-105">Access a former user's OneDrive documents</span></span>

<span data-ttu-id="1ce21-106">Если вы удалите лицензию пользователя, но не удалите учетную запись, вы можете предоставить себе доступ к содержимому в OneDrive пользователя.</span><span class="sxs-lookup"><span data-stu-id="1ce21-106">If you remove a user's license but don't delete the account, you can give yourself access to the content in the user's OneDrive.</span></span> <span data-ttu-id="1ce21-107">Если вы удалите учетную запись пользователя, у вас есть 30 дней по умолчанию для доступа к данным OneDrive бывшего пользователя.</span><span class="sxs-lookup"><span data-stu-id="1ce21-107">If you delete the user's account, you have 30 days by default to access the former user's OneDrive data.</span></span> <span data-ttu-id="1ce21-108">[Узнайте, как установить хранение OneDrive для удаленных пользователей.](/onedrive/set-retention)</span><span class="sxs-lookup"><span data-stu-id="1ce21-108">[Learn how to set the OneDrive retention for deleted users](/onedrive/set-retention).</span></span> <span data-ttu-id="1ce21-109">Если в течение этого времени [учетная запись](/office365/admin/add-users/restore-user) пользователя не будет восстановлена, содержимое OneDrive будет удалено.</span><span class="sxs-lookup"><span data-stu-id="1ce21-109">If you don't [restore a user account](/office365/admin/add-users/restore-user) within this time, their OneDrive content is deleted.</span></span> 

<span data-ttu-id="1ce21-110">Чтобы сохранить файлы OneDrive бывшего пользователя, сначала предоставьте себе доступ к OneDrive, а затем переместите файлы, которые необходимо сохранить.</span><span class="sxs-lookup"><span data-stu-id="1ce21-110">To preserve a former user's OneDrive files, first give yourself access to their OneDrive, and then move the files you want to keep.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1ce21-111">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="1ce21-111">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="1ce21-112">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="1ce21-112">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="1ce21-113">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="1ce21-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="1ce21-114">Выберите пользователя.</span><span class="sxs-lookup"><span data-stu-id="1ce21-114">Select a user.</span></span>

3. <span data-ttu-id="1ce21-115">В правой области выберите **OneDrive**.</span><span class="sxs-lookup"><span data-stu-id="1ce21-115">In the right pane, select **OneDrive**.</span></span> <span data-ttu-id="1ce21-116">В **статье Получить доступ к файлам** выберите Создать **ссылку на файлы.**</span><span class="sxs-lookup"><span data-stu-id="1ce21-116">Under **Get access to files**, select **Create link to files**.</span></span>

4. <span data-ttu-id="1ce21-117">Выберите ссылку для открытия расположения файла.</span><span class="sxs-lookup"><span data-stu-id="1ce21-117">Select the link to open the file location.</span></span> <span data-ttu-id="1ce21-118">Скачайте файлы на компьютер или выберите **Move to** или **Copy,** чтобы переместить или скопировать их в собственную OneDrive или в общую библиотеку.</span><span class="sxs-lookup"><span data-stu-id="1ce21-118">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="1ce21-119">Вы можете переместить или скопировать до 500 МБ файлов и папок одновременно.</span><span class="sxs-lookup"><span data-stu-id="1ce21-119">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="1ce21-120">При перемещении или копировании документов с историей версий перемещается только последняя версия.</span><span class="sxs-lookup"><span data-stu-id="1ce21-120">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

## <a name="revoke-admin-access-to-a-users-onedrive"></a><span data-ttu-id="1ce21-121">Отзовет доступ администратора к OneDrive пользователя</span><span class="sxs-lookup"><span data-stu-id="1ce21-121">Revoke admin access to a user's OneDrive</span></span>

<span data-ttu-id="1ce21-122">В качестве глобального администратора вы можете предоставить себе доступ к содержимому OneDrive пользователя, но при необходимости может потребоваться удалить доступ.</span><span class="sxs-lookup"><span data-stu-id="1ce21-122">As global admin, you can give yourself access to the content in a user's OneDrive, but you may want to remove your access when you no longer need it.</span></span> 

 ::: moniker range="o365-worldwide"

1. <span data-ttu-id="1ce21-123">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="1ce21-123">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="1ce21-124">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.</span><span class="sxs-lookup"><span data-stu-id="1ce21-124">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1ce21-125">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="1ce21-125">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end 

2. <span data-ttu-id="1ce21-126">В левой области выберите **центры администрирования** \> **SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="1ce21-126">In the left pane, select **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="1ce21-127">(Возможно, потребуется щелкнуть элемент **Показать все**, чтобы увидеть список центров администрирования.)</span><span class="sxs-lookup"><span data-stu-id="1ce21-127">(You might need to select **Show all** to see the list of admin centers.)</span></span>

3. <span data-ttu-id="1ce21-128">Если появится классический центр администрирования SharePoint, откройте его в верхней части страницы, чтобы открыть центр администрирования SharePoint. </span><span class="sxs-lookup"><span data-stu-id="1ce21-128">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the SharePoint admin center.</span></span>

4. <span data-ttu-id="1ce21-129">В левой области выберите **Дополнительные функции.**</span><span class="sxs-lookup"><span data-stu-id="1ce21-129">In the left pane, select **More features**.</span></span>

5. <span data-ttu-id="1ce21-130">В **профилях пользователей** выберите **Open**.</span><span class="sxs-lookup"><span data-stu-id="1ce21-130">Under **User profiles**, select **Open**.</span></span>

6. <span data-ttu-id="1ce21-131">В **статье People** выберите Управление **профилями пользователей.**</span><span class="sxs-lookup"><span data-stu-id="1ce21-131">Under **People**, select **Manage User Profiles**.</span></span>

7. <span data-ttu-id="1ce21-132">Введите имя пользователя и выберите **Найти**.</span><span class="sxs-lookup"><span data-stu-id="1ce21-132">Enter the user's name and select **Find**.</span></span>

8. <span data-ttu-id="1ce21-133">Щелкните правой кнопкой мыши пользователя, а затем выберите **управление владельцами коллекции сайтов.**</span><span class="sxs-lookup"><span data-stu-id="1ce21-133">Right-click the user, and then choose **Manage site collection owners**.</span></span>

9. <span data-ttu-id="1ce21-134">Удалите пользователя, которому больше не нужен доступ к данным пользователя, и выберите **ОК.**</span><span class="sxs-lookup"><span data-stu-id="1ce21-134">Remove the person who no longer needs access to the user's data, and then select **OK**.</span></span>

    
## <a name="access-the-outlook-data-of-a-former-user"></a><span data-ttu-id="1ce21-135">Доступ к данным Outlook бывшего пользователя</span><span class="sxs-lookup"><span data-stu-id="1ce21-135">Access the Outlook data of a former user</span></span>

<span data-ttu-id="1ce21-136">Чтобы сохранить сообщения электронной почты, календарь, задачи и контакты прежнего сотрудника, экспортируйте данные в файл данных Outlook (PST).</span><span class="sxs-lookup"><span data-stu-id="1ce21-136">To save the email messages, calendar, tasks, and contacts of the former employee, export the information to an Outlook Data File (.pst).</span></span>
  
1. <span data-ttu-id="1ce21-137">[Добавьте электронную почту](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) бывшего сотрудника в Outlook (Если сбросить пароль [пользователя,](reset-passwords.md)вы можете настроить его на что-то только известное.)</span><span class="sxs-lookup"><span data-stu-id="1ce21-137">[Add the former employee's email](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) to your Outlook (If you [reset the user's password](reset-passwords.md), you can set it to something only you know.)</span></span>
    
2. <span data-ttu-id="1ce21-138">В Outlook выберите **Файл**.</span><span class="sxs-lookup"><span data-stu-id="1ce21-138">In Outlook, select **File**.</span></span>
    
    ![Так выглядит лента в Outlook 2016.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. <span data-ttu-id="1ce21-140">Выберите **Open &amp; Export** \> **Import/Export**.</span><span class="sxs-lookup"><span data-stu-id="1ce21-140">Select **Open &amp; Export** \> **Import/Export**.</span></span>
    
    ![Команда "Импорт и экспорт" в представлении Backstage](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. <span data-ttu-id="1ce21-142">Выберите **Экспорт в файл,** а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1ce21-142">Select **Export to a file**, and then select **Next**.</span></span>
    
    ![Параметр "Экспорт в файл" в мастере импорта и экспорта](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. <span data-ttu-id="1ce21-144">Выберите **файл данных Outlook (.pst)** и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1ce21-144">Select **Outlook Data File (.pst)**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="1ce21-145">Выберите учетную запись, которая будет экспортироваться, выбрав имя или адрес электронной почты, например почтовый ящик — Anne Weiler или anne@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="1ce21-145">Select the account you want to export by selecting the name or email address, such as Mailbox - Anne Weiler or anne@contoso.com.</span></span> <span data-ttu-id="1ce21-146">Если вы хотите экспортировать все, что содержится в вашей учетной записи, включая почту, календарь, контакты, задачи и заметки, убедитесь, что выбрано поле **Включить** подмостки.</span><span class="sxs-lookup"><span data-stu-id="1ce21-146">If you want to export everything in your account, including mail, calendar, contacts, tasks, and notes, make sure the **Include subfolders** check box is selected.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="1ce21-p106">Одновременно можно экспортировать только одну учетную запись. Если нужно экспортировать несколько учетных записей, экспортируйте сначала одну учетную запись, а затем повторите эти действия для других учетных записей.</span><span class="sxs-lookup"><span data-stu-id="1ce21-p106">You can export one account at a time. If you want to export multiple accounts, after one account is exported, repeat these steps.</span></span> 
  
    ![Диалоговое окно "Экспорт файла данных Outlook", в котором выбрана верхняя папка и установлен флажок "Включить вложенные папки"](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. <span data-ttu-id="1ce21-150">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1ce21-150">Select **Next**.</span></span>
    
8. <span data-ttu-id="1ce21-151">Выберите **Просмотр,** чтобы выбрать, где сохранить файл данных Outlook (.pst).</span><span class="sxs-lookup"><span data-stu-id="1ce21-151">Select **Browse** to select where to save the Outlook Data File (.pst).</span></span> <span data-ttu-id="1ce21-152">Введите  *имя файла* и выберите **ОК** для продолжения.</span><span class="sxs-lookup"><span data-stu-id="1ce21-152">Type a  *file name*, and then select **OK** to continue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="1ce21-153">Если функция экспорта уже использовалась, здесь будут указаны предыдущие папка и имя файла.</span><span class="sxs-lookup"><span data-stu-id="1ce21-153">If you've used export before, the previous folder location and file name appear.</span></span> <span data-ttu-id="1ce21-154">Введите *другое имя файла перед* выбором **ОК.**</span><span class="sxs-lookup"><span data-stu-id="1ce21-154">Type a  *different file name*  before selecting **OK**.</span></span> 
  
9. <span data-ttu-id="1ce21-155">Если данные экспортируются в уже существующий Файл данных Outlook (PST), в разделе **Настройка** укажите, что следует делать, если экспортируемые элементы уже содержатся в этом файле.</span><span class="sxs-lookup"><span data-stu-id="1ce21-155">If you are exporting to an existing Outlook Data File (.pst), under **Options**, specify what to do when exporting items that already exist in the file.</span></span>
    
10. <span data-ttu-id="1ce21-156">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="1ce21-156">Select **Finish**.</span></span>
    
<span data-ttu-id="1ce21-157">В Outlook сразу начнется экспорт, если только не требуется создать новый Файл данных Outlook (PST) или экспорт не выполняется в файл, защищенный паролем.</span><span class="sxs-lookup"><span data-stu-id="1ce21-157">Outlook begins the export immediately unless a new Outlook Data File (.pst) is created or a password-protected file is used.</span></span>
  
   - <span data-ttu-id="1ce21-158">Создаваемый Файл данных Outlook (PST) можно защитить паролем.</span><span class="sxs-lookup"><span data-stu-id="1ce21-158">If you're creating an Outlook Data File (.pst), an optional password can help protect the file.</span></span> <span data-ttu-id="1ce21-159">Когда **появится диалоговое** окно Create Outlook  Data File, введите пароль в **полях Пароль** и **Проверьте** пароль, а затем выберите **ОК.**</span><span class="sxs-lookup"><span data-stu-id="1ce21-159">When the **Create Outlook Data File** dialog box appears, type the  *password*  in the **Password** and **Verify Password** boxes, and then select **OK**.</span></span> <span data-ttu-id="1ce21-160">В **диалоговом окне Пароль** файла данных Outlook введите *пароль* и выберите **ОК.**</span><span class="sxs-lookup"><span data-stu-id="1ce21-160">In the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
  - <span data-ttu-id="1ce21-161">Если вы экспортируете в существующий файл данных Outlook (PST), защищенный паролем, в диалоговом окне Пароль файла данных **Outlook** введите пароль *и* выберите **ОК.**</span><span class="sxs-lookup"><span data-stu-id="1ce21-161">If you're exporting to an existing Outlook Data File (.pst) that is password protected, in the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
<span data-ttu-id="1ce21-162">Узнайте, как [экспортировать или резервное копирование электронной почты, контактов](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) и календаря в файл Outlook .pst в Outlook 2010.</span><span class="sxs-lookup"><span data-stu-id="1ce21-162">See how to [Export or backup email, contacts, and calendar to an Outlook .pst file](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) in Outlook 2010.</span></span> 
  
  
  > [!NOTE]
  > <span data-ttu-id="1ce21-163">По умолчанию электронная почта доступна в автономном режиме в течение 12 месяцев.</span><span class="sxs-lookup"><span data-stu-id="1ce21-163">By default, your email is available offline for a period of 12 months.</span></span> <span data-ttu-id="1ce21-164">При необходимости см., как [увеличить доступ к данным в автономном режиме.](/outlook/troubleshoot/mailboxes/only-subset-items-synchronized)</span><span class="sxs-lookup"><span data-stu-id="1ce21-164">If required, see how to [increase the data available offline](/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span></span>
 
## <a name="give-another-user-access-to-a-former-users-email"></a><span data-ttu-id="1ce21-165">Предоставить другому пользователю доступ к электронной почте бывшего пользователя</span><span class="sxs-lookup"><span data-stu-id="1ce21-165">Give another user access to a former user's email</span></span> 

<span data-ttu-id="1ce21-166">Чтобы предоставить доступ к электронным сообщениям, календарю, задачам и контактам бывшего сотрудника другому сотруднику, импортировать сведения в почтовый ящик Outlook другого сотрудника.</span><span class="sxs-lookup"><span data-stu-id="1ce21-166">To give access to the email messages, calendar, tasks, and contacts of the former employee to another employee, import the information to another employee's Outlook inbox.</span></span>

> [!NOTE]
> <span data-ttu-id="1ce21-167">Кроме [того, можно преобразовать](/office365/admin/email/convert-user-mailbox-to-shared-mailbox) почтовый ящик бывшего пользователя в общий почтовый ящик или отправить электронной почте бывшего сотрудника [другому сотруднику.](/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox)</span><span class="sxs-lookup"><span data-stu-id="1ce21-167">You can also [convert the former user's mailbox to a shared mailbox](/office365/admin/email/convert-user-mailbox-to-shared-mailbox) or [forward a former employee's email to another employee](/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span></span>

  
1. <span data-ttu-id="1ce21-168">В Outlook перейдите к **файлу** \> **Open Export &amp;** \> **Import/Export**.</span><span class="sxs-lookup"><span data-stu-id="1ce21-168">In Outlook, go to **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>
    
    <span data-ttu-id="1ce21-169">Будет запущен мастер импорта и экспорта.</span><span class="sxs-lookup"><span data-stu-id="1ce21-169">This starts the Import and Export Wizard.</span></span>
    
2. <span data-ttu-id="1ce21-170">Выберите **Импорт из другой программы или файла,** а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1ce21-170">Select **Import from another program or file**, and then select **Next**.</span></span>
    
    ![Мастер импорта и экспорта](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. <span data-ttu-id="1ce21-172">Выберите **файл данных Outlook (.pst)** и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1ce21-172">Select **Outlook Data File (.pst)**, and select **Next**.</span></span>
    
4. <span data-ttu-id="1ce21-173">Перейдите к PST-файлу, который вы хотите импортировать.</span><span class="sxs-lookup"><span data-stu-id="1ce21-173">Browse to the .pst file you want to import.</span></span>
    
5. <span data-ttu-id="1ce21-174">В разделе **Параметры**, выберите способ работы с дубликатами.</span><span class="sxs-lookup"><span data-stu-id="1ce21-174">Under **Options**, choose how you want to deal with duplicates</span></span>
    
6. <span data-ttu-id="1ce21-175">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1ce21-175">Select **Next**.</span></span>
    
7. <span data-ttu-id="1ce21-176">Если пароль был назначен файлу данных Outlook (.pst), введите пароль и выберите **ОК.**</span><span class="sxs-lookup"><span data-stu-id="1ce21-176">If a password was assigned to the Outlook Data File (.pst), enter the password, and then select **OK**.</span></span>
    
8. <span data-ttu-id="1ce21-177">Настройте параметры импорта элементов.</span><span class="sxs-lookup"><span data-stu-id="1ce21-177">Set the options for importing items.</span></span> <span data-ttu-id="1ce21-178">Обычно изменять параметры по умолчанию нет необходимости.</span><span class="sxs-lookup"><span data-stu-id="1ce21-178">The default settings usually don't need to be changed.</span></span>
    
9. <span data-ttu-id="1ce21-179">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="1ce21-179">Select **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="1ce21-180">Действия остаются одинаковыми для доступа к данным OneDrive и электронной почты существующего пользователя.</span><span class="sxs-lookup"><span data-stu-id="1ce21-180">The steps remain the same for accessing an existing user's OneDrive and email data.</span></span>
    
> [!TIP]
> <span data-ttu-id="1ce21-181">Если вы хотите импортировать или восстанавливать только несколько элементов из файла данных Outlook (PST), вы можете открыть файл данных Outlook.</span><span class="sxs-lookup"><span data-stu-id="1ce21-181">If you want to import or restore only a few items from an Outlook Data File (.pst), you can open the Outlook Data File.</span></span> <span data-ttu-id="1ce21-182">Затем в области навигации перетащите элементы из папки Outlook Data File в существующие папки Outlook.</span><span class="sxs-lookup"><span data-stu-id="1ce21-182">Then, in the navigation pane, drag the items from Outlook Data File folders to your existing Outlook folders.</span></span> 
  
  
## <a name="related-articles"></a><span data-ttu-id="1ce21-183">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="1ce21-183">Related articles</span></span>
[<span data-ttu-id="1ce21-184">Удаление бывшего сотрудника из среды Office 365</span><span class="sxs-lookup"><span data-stu-id="1ce21-184">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="1ce21-185">Добавление и удаление администраторов в учетной записи OneDrive</span><span class="sxs-lookup"><span data-stu-id="1ce21-185">Add and remove admins on a OneDrive account</span></span>](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[<span data-ttu-id="1ce21-186">Восстановление удаленного хранилища OneDrive</span><span class="sxs-lookup"><span data-stu-id="1ce21-186">Restore a deleted OneDrive</span></span>](/onedrive/restore-deleted-onedrive)
  
[<span data-ttu-id="1ce21-187">Хранение и удаление OneDrive</span><span class="sxs-lookup"><span data-stu-id="1ce21-187">OneDrive retention and deletion</span></span>](/onedrive/retention-and-deletion)
