---
title: Одновременное добавление нескольких пользователей в Microsoft 365 — Справка для администраторов
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_AddUsersCSV
- O365M_AddUsersCSV
- O365E_AddUsersCSV
search.appverid:
- MET150
- MOP150
- MOE150
- MED150
- GMA150
- MBS150
- GEA150
- BCS160
ms.assetid: 1f5767ed-e717-4f24-969c-6ea9d412ca88
description: 'Узнайте, как добавить нескольких пользователей в Microsoft 365 для бизнеса из списка в электронной таблице или другом отформатированном CSV-файле. Просмотрите видео на YouTube, в котором рассказывается, как добавлять учетные записи в Microsoft 365. В конце этого процесса у каждого пользователя с учетной записью будет почтовый ящик Microsoft 365. '
ms.openlocfilehash: a970fbfa28214543e34011f1310742c6fb811d09
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071517"
---
# <a name="add-several-users-at-the-same-time-to-microsoft-365---admin-help"></a><span data-ttu-id="8b18f-105">Одновременное добавление нескольких пользователей в Microsoft 365 — Справка для администраторов</span><span class="sxs-lookup"><span data-stu-id="8b18f-105">Add several users at the same time to Microsoft 365 - Admin Help</span></span>

<span data-ttu-id="8b18f-p102">Каждому участнику команды требуется учетная запись пользователя, прежде чем она сможет войти в систему и получить доступ к службам Microsoft 365, таким как электронная почта и Office. Если у вас много людей, вы можете добавить свои учетные записи одновременно из электронной таблицы Excel или другого файла, сохраненного в формате CSV. [Не знаете, какой формат CSV-файла?](add-several-users-at-the-same-time.md#__toc316652088)</span><span class="sxs-lookup"><span data-stu-id="8b18f-p102">Each person on your team needs a user account before they can sign in and access Microsoft 365 services, such as email and Office. If you have a lot of people, you can add their accounts all at once from an Excel spreadsheet or other file saved in CSV format. [Not sure what CSV format is?](add-several-users-at-the-same-time.md#__toc316652088)</span></span>
  
> [!NOTE] 
> <span data-ttu-id="8b18f-109">Если вы не используете новый Центр администрирования Microsoft 365, можно включить его с помощью переключателя **Попробовать новый Центр администрирования** , расположенного в верхней части главной страницы.</span><span class="sxs-lookup"><span data-stu-id="8b18f-109">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

## <a name="add-multiple-users-in-the-microsoft-365-admin-center"></a><span data-ttu-id="8b18f-110">Добавление нескольких пользователей в центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8b18f-110">Add multiple users in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="8b18f-111">Войдите в Microsoft 365, используя свою рабочую или учебную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="8b18f-111">Sign in to Microsoft 365 with your work or school account.</span></span> 
    
2. <span data-ttu-id="8b18f-112">В Центре администрирования выберите **Пользователи** \> **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="8b18f-112">In the admin center, choose **Users** \> **Active users**.</span></span>

3. <span data-ttu-id="8b18f-113">Выберите **Добавить нескольких пользователей**.</span><span class="sxs-lookup"><span data-stu-id="8b18f-113">Select **Add multiple users**.</span></span>

4. <span data-ttu-id="8b18f-114">В области **Импорт нескольких пользователей** вы можете скачать шаблон CSV-файла с образцом сведений о пользователях или без него.</span><span class="sxs-lookup"><span data-stu-id="8b18f-114">On the **Import multiple users** panel, you can optionally download a sample CSV file with or without sample data filled in.</span></span> 
    
    <span data-ttu-id="8b18f-115">Электронная таблица должна содержать те **же заголовки столбцов** , что и один образец (имя пользователя, имя и т. д.).</span><span class="sxs-lookup"><span data-stu-id="8b18f-115">Your spreadsheet needs to include the **exact same column headings** as the sample one (User Name, First Name, and so on).</span></span> <span data-ttu-id="8b18f-116">Если вы используете шаблон, откройте его в средстве редактирования текста, например в блокноте, и рассмотрите все данные только в строке 1 и вводите данные в строки 2 и ниже.</span><span class="sxs-lookup"><span data-stu-id="8b18f-116">If you use the template, open it in a text editing tool, like Notepad, and consider leaving all the data in row 1 alone, and only entering data in rows 2 and below.</span></span> 
    
    <span data-ttu-id="8b18f-117">Для каждого человека в таблице также следует указать имя пользователя (например, ivan@contoso.com) и отображаемое имя (например, Иван Воронков).</span><span class="sxs-lookup"><span data-stu-id="8b18f-117">Your spreadsheet also needs to include values for the user name (like bob@contoso.com) and a display name (like Bob Kelly) for each user.</span></span> 
    
  ```
  User Name,First Name,Last Name,Display Name,Job Title,Department,Office Number,Office Phone,Mobile Phone,Address,City,State or Province,ZIP or Postal Code,Country or Region
  chris@contoso.com,Chris,Green,Chris Green,IT Manager,Information Technology,123451,123-555-1211,123-555-6641,1 Microsoft way,Redmond,Wa,98052,United States
  ben@contoso.com,Ben,Andrews,Ben Andrews,IT Manager,Information Technology,123452,123-555-1212,123-555-6642,1 Microsoft way,Redmond,Wa,98052,United States
  david@contoso.com,David,Longmuir,David Longmuir,IT Manager,Information Technology,123453,123-555-1213,123-555-6643,1 Microsoft way,Redmond,Wa,98052,United States
  cynthia@contoso.com,Cynthia,Carey,Cynthia Carey,IT Manager,Information Technology,123454,123-555-1214,123-555-6644,1 Microsoft way,Redmond,Wa,98052,United States
  melissa@contoso.com,Melissa,MacBeth,Melissa MacBeth,IT Manager,Information Technology,123455,123-555-1215,123-555-6645,1 Microsoft way,Redmond,Wa,98052,United States
  
  ```

5. <span data-ttu-id="8b18f-118">Укажите путь к CSV-файлу в специальном поле или нажмите кнопку **Обзор** и выберите его, а затем нажмите кнопку **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="8b18f-118">Enter a file path into the box, or choose **Browse** to browse to the CSV file location, then choose **Verify**.</span></span>
  
    <span data-ttu-id="8b18f-p104">Если при добавлении файла возникнут проблемы, их причины будут указаны в области импорта. Вы также можете скачать файл журнала.</span><span class="sxs-lookup"><span data-stu-id="8b18f-p104">If there are problems with the file, the problem is displayed in the panel. You can also download a log file.</span></span>
    
5. <span data-ttu-id="8b18f-121">В диалоговом окне **Настройка параметров пользователей** вы можете изменить состояние при входе в систему, а также лицензию продукта, которая будет назначена всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="8b18f-121">On the **Set user options** dialog you can set the sign-in status and choose the product license that will be assigned to all users.</span></span> 
    
6. <span data-ttu-id="8b18f-122">В диалоговом окне **просмотра результатов** вы можете отправить их себе или другим пользователям (при этом пароли будут указаны в виде обычного текста), проверить число созданных пользователей и при необходимости приобрести лицензии, чтобы назначить их новым пользователям.</span><span class="sxs-lookup"><span data-stu-id="8b18f-122">On the **View your result** dialog you can choose to send the results to either yourself or other users (passwords will be in plain text) and you can see how many users were created, and if you need to purchase more licenses to assign to some of the new users.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="8b18f-123">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="8b18f-123">Next steps</span></span>
<span data-ttu-id="8b18f-124"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="8b18f-124"><a name="bk_preview"> </a></span></span>

- <span data-ttu-id="8b18f-125">Теперь, когда у этих пользователей есть учетные записи, им нужно [скачать и установить или переустановить Microsoft 365 или Office 2016 на ПК или Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658).</span><span class="sxs-lookup"><span data-stu-id="8b18f-125">Now that these people have accounts, they need to [Download and install or reinstall Microsoft 365 or Office 2016 on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658).</span></span> <span data-ttu-id="8b18f-126">Каждый участник команды может установить Microsoft 365 на более чем 5 компьютерах или компьютерах Макинтош.</span><span class="sxs-lookup"><span data-stu-id="8b18f-126">Each person on your team can install Microsoft 365 on up to 5 PCs or Macs.</span></span> 
    
- <span data-ttu-id="8b18f-127">Кроме того, каждый пользователь может [настроить приложения Office и электронную почту на мобильных устройствах](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f), используя до пяти планшетов и пяти смартфонов, таких как iPhone, iPad и устройства с Android.</span><span class="sxs-lookup"><span data-stu-id="8b18f-127">Each person can also [Set up Office apps and email on a mobile device](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) on up to 5 tablets and 5 phones, such as iPhones, iPads, and Android phones and tablets.</span></span> <span data-ttu-id="8b18f-128">Таким образом, они смогут редактировать файлы Office где угодно.</span><span class="sxs-lookup"><span data-stu-id="8b18f-128">This way they can edit Office files from anywhere.</span></span> 
    
    <span data-ttu-id="8b18f-129">Полный список шагов по настройке представлен в [статье Настройка Microsoft 365 для бизнеса](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) .</span><span class="sxs-lookup"><span data-stu-id="8b18f-129">See [Set up Microsoft 365 for business](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) for an end-to-end list of the setup steps.</span></span> 
    
## <a name="more-information-about-how-to-add-users-to-microsoft-365"></a><span data-ttu-id="8b18f-130">Дополнительные сведения о добавлении пользователей в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8b18f-130">More information about how to add users to Microsoft 365</span></span>
<span data-ttu-id="8b18f-131"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="8b18f-131"><a name="bk_preview"> </a></span></span>

### <a name="not-sure-what-csv-format-is"></a><span data-ttu-id="8b18f-132">Общие сведения о формате CSV</span><span class="sxs-lookup"><span data-stu-id="8b18f-132">Not sure what CSV format is?</span></span>
<span data-ttu-id="8b18f-133"><a name="__toc316652088"> </a></span><span class="sxs-lookup"><span data-stu-id="8b18f-133"><a name="__toc316652088"> </a></span></span>

<span data-ttu-id="8b18f-p107">CSV-файл содержит значения, разделенные запятыми. Такие файлы создаются и редактируются с помощью обычного текстового редактора или программы для работы с таблицами, например Excel.</span><span class="sxs-lookup"><span data-stu-id="8b18f-p107">A CSV file is a file with comma separated values. You can create or edit a file like this with any text editor or spreadsheet program, such as Excel.</span></span>
  
<span data-ttu-id="8b18f-136">Для начала вы можете загрузить и использовать [этот пример электронной таблицы](https://www.microsoft.com/download/details.aspx?id=45485).</span><span class="sxs-lookup"><span data-stu-id="8b18f-136">You can download [this sample spreadsheet](https://www.microsoft.com/download/details.aspx?id=45485) as a starting point.</span></span> <span data-ttu-id="8b18f-137">Помните, что в Microsoft 365 в первой строке требуется заголовков столбцов, поэтому не заменяйте их другими.</span><span class="sxs-lookup"><span data-stu-id="8b18f-137">Remember that Microsoft 365 requires column headings in the first row so don't replace them with something else.</span></span> 
  
<span data-ttu-id="8b18f-138">Сохраните файл в формате CSV под другим именем.</span><span class="sxs-lookup"><span data-stu-id="8b18f-138">Save the file with a new name, and specify CSV format.</span></span>
  
![Как сохранить файл в формате CSV в Excel](../media/35a86ebe-63ab-4b4d-9a92-e177de33ebae.png)
  
<span data-ttu-id="8b18f-p109">При сохранении вы, скорее всего, увидите сообщение о том, что в случае сохранения файла в формате CSV некоторые функции в книге будут потеряны. Это нормально. Нажмите кнопку **Да** , чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="8b18f-p109">When you save the file, you'll probably get a prompt that some features in your workbook will be lost if you save the file in CSV format. This is okay. Click **Yes** to continue.</span></span> 
  
![Изображение приглашения от Excel с вопросом о том, хотите ли вы сохранить файл в формате CSV](../media/51032a81-690c-45ef-bfc5-09ea7f790e98.png)
  
### <a name="tips-for-formatting-your-spreadsheet"></a><span data-ttu-id="8b18f-144">Советы по форматированию электронной таблицы</span><span class="sxs-lookup"><span data-stu-id="8b18f-144">Tips for formatting your spreadsheet</span></span>
<span data-ttu-id="8b18f-145"><a name="__toc314595848"> </a></span><span class="sxs-lookup"><span data-stu-id="8b18f-145"><a name="__toc314595848"> </a></span></span>

- <span data-ttu-id="8b18f-146">**Обязательно ли использовать такие же заголовки столбцов, как в примере электронной таблицы?**</span><span class="sxs-lookup"><span data-stu-id="8b18f-146">**Do I need the same column headings as in the sample spreadsheet?**</span></span> <span data-ttu-id="8b18f-147">Да.</span><span class="sxs-lookup"><span data-stu-id="8b18f-147">Yes.</span></span> <span data-ttu-id="8b18f-148">Первая строка в примере таблицы содержит заголовки столбцов.</span><span class="sxs-lookup"><span data-stu-id="8b18f-148">The sample spreadsheet contains column headings in the first row.</span></span> <span data-ttu-id="8b18f-149">Эти заголовки являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="8b18f-149">These headings are required.</span></span> <span data-ttu-id="8b18f-150">Для каждого пользователя, который требуется добавить в Microsoft 365, создайте строку под заголовком.</span><span class="sxs-lookup"><span data-stu-id="8b18f-150">For each user you want to add to Microsoft 365, create a row under the heading.</span></span> <span data-ttu-id="8b18f-151">Если вы добавляете, изменяете или удаляете заголовки столбцов, Microsoft 365 может не иметь возможность создавать пользователей на основе информации в файле.</span><span class="sxs-lookup"><span data-stu-id="8b18f-151">If you add, change, or delete any of the column headings, Microsoft 365 might not be able to create users from the information in the file.</span></span> 
    
- <span data-ttu-id="8b18f-p111">**Что делать, если сведения о пользователе неполны?** Имя пользователя и отображаемое имя обязательны: не указав их, вы не сможете добавить учетную запись. Если у вас нет других сведений, таких как факс, вы можете ввести вместо них пробел и запятую, чтобы оставить соответствующее поле пустым.</span><span class="sxs-lookup"><span data-stu-id="8b18f-p111">**What if I don't have all the information required for each user?** The user name and display name are required, and you cannot add a new user without this information. If you don't have some of the other information, such as the fax, you can use a space plus a comma to indicate that the field should remain blank.</span></span> 
    
- <span data-ttu-id="8b18f-155">**Насколько велика и может быть электронная таблица?**</span><span class="sxs-lookup"><span data-stu-id="8b18f-155">**How small or large can the spreadsheet be?**</span></span> <span data-ttu-id="8b18f-156">Электронная таблица должна содержать по крайней мере две строки.</span><span class="sxs-lookup"><span data-stu-id="8b18f-156">The spreadsheet must have at least two rows.</span></span> <span data-ttu-id="8b18f-157">One is for the column headings (the user data column label) and one for the user.</span><span class="sxs-lookup"><span data-stu-id="8b18f-157">One is for the column headings (the user data column label) and one for the user.</span></span> <span data-ttu-id="8b18f-158">You cannot have more than 251 rows.</span><span class="sxs-lookup"><span data-stu-id="8b18f-158">You cannot have more than 251 rows.</span></span> <span data-ttu-id="8b18f-159">If you need to import more than 250 users, you can create more than one spreadsheet.</span><span class="sxs-lookup"><span data-stu-id="8b18f-159">If you need to import more than 250 users, you can create more than one spreadsheet.</span></span> 
    
- <span data-ttu-id="8b18f-160">**Какие языки можно использовать?**</span><span class="sxs-lookup"><span data-stu-id="8b18f-160">**What languages can I use?**</span></span> <span data-ttu-id="8b18f-161">Когда вы создаете электронную таблицу, вы можете вводить подписи столбцов пользовательских данных на любом языке или символах, но не следует изменять порядок меток, как показано в примере.</span><span class="sxs-lookup"><span data-stu-id="8b18f-161">When you create your spreadsheet, you can enter user data column labels in any language or characters, but you must not change the order of the labels, as shown in the sample.</span></span> <span data-ttu-id="8b18f-162">You can then make entries into the fields, using any language or characters, and save your file in a Unicode or UTF-8 format.</span><span class="sxs-lookup"><span data-stu-id="8b18f-162">You can then make entries into the fields, using any language or characters, and save your file in a Unicode or UTF-8 format.</span></span> 
    
- <span data-ttu-id="8b18f-p114">**Как добавить пользователей из разных стран или регионов?** Создайте отдельную таблицу для каждой области. Вам потребуется выполнить мастер массового добавления для каждой таблицы, указав одинаковое расположение для всех пользователей в текущем файле.</span><span class="sxs-lookup"><span data-stu-id="8b18f-p114">**What if I'm adding users from different countries or regions?** Create a separate spreadsheet for each area. You'll need to step through the Bulk add users wizard which each spreadsheet, giving a single location of all users included in the file that you're working with.</span></span> 
    
- <span data-ttu-id="8b18f-p115">**Ограничено ли количество символов?** Максимальное количество знаков для значений в столбцах данных пользователя указано в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="8b18f-p115">**Is there a limit to the number of characters I can use?** The following table shows the user data column labels and the maximum character length for each in the sample spreadsheet.</span></span> 
    
|<span data-ttu-id="8b18f-168">**Столбец данных пользователя**</span><span class="sxs-lookup"><span data-stu-id="8b18f-168">**User data column label**</span></span>|<span data-ttu-id="8b18f-169">**Максимальная длина в знаках**</span><span class="sxs-lookup"><span data-stu-id="8b18f-169">**Maximum character length**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8b18f-170">Имя пользователя (обязательно)</span><span class="sxs-lookup"><span data-stu-id="8b18f-170">User Name (Required)</span></span>  <br/> |<span data-ttu-id="8b18f-171">79, включая знак @, в формате name@domain. \<extension\> .</span><span class="sxs-lookup"><span data-stu-id="8b18f-171">79 including the at sign (@), in the format name@domain.\<extension\>.</span></span> <span data-ttu-id="8b18f-172">Длина псевдонима пользователя не может превышать 50 символов, а имя домена не может превышать 48 символов.</span><span class="sxs-lookup"><span data-stu-id="8b18f-172">The user's alias cannot exceed 50 characters, and the domain name cannot exceed 48 characters.</span></span>  <br/> |
|<span data-ttu-id="8b18f-173">Имя</span><span class="sxs-lookup"><span data-stu-id="8b18f-173">First Name</span></span>  <br/> |<span data-ttu-id="8b18f-174">64</span><span class="sxs-lookup"><span data-stu-id="8b18f-174">64</span></span>  <br/> |
|<span data-ttu-id="8b18f-175">Фамилия</span><span class="sxs-lookup"><span data-stu-id="8b18f-175">Last Name</span></span>  <br/> |<span data-ttu-id="8b18f-176">64</span><span class="sxs-lookup"><span data-stu-id="8b18f-176">64</span></span>  <br/> |
|<span data-ttu-id="8b18f-177">Отображаемое имя (обязательно)</span><span class="sxs-lookup"><span data-stu-id="8b18f-177">Display Name (required)</span></span>  <br/> |<span data-ttu-id="8b18f-178">256</span><span class="sxs-lookup"><span data-stu-id="8b18f-178">256</span></span>  <br/> |
|<span data-ttu-id="8b18f-179">Должность</span><span class="sxs-lookup"><span data-stu-id="8b18f-179">Job Title</span></span>  <br/> |<span data-ttu-id="8b18f-180">64</span><span class="sxs-lookup"><span data-stu-id="8b18f-180">64</span></span>  <br/> |
|<span data-ttu-id="8b18f-181">Отдел</span><span class="sxs-lookup"><span data-stu-id="8b18f-181">Department</span></span>  <br/> |<span data-ttu-id="8b18f-182">64</span><span class="sxs-lookup"><span data-stu-id="8b18f-182">64</span></span>  <br/> |
|<span data-ttu-id="8b18f-183">Номер офиса</span><span class="sxs-lookup"><span data-stu-id="8b18f-183">Office Number</span></span>  <br/> |<span data-ttu-id="8b18f-184">128</span><span class="sxs-lookup"><span data-stu-id="8b18f-184">128</span></span>  <br/> |
|<span data-ttu-id="8b18f-185">Рабочий телефон</span><span class="sxs-lookup"><span data-stu-id="8b18f-185">Office Phone</span></span>  <br/> |<span data-ttu-id="8b18f-186">64</span><span class="sxs-lookup"><span data-stu-id="8b18f-186">64</span></span>  <br/> |
|<span data-ttu-id="8b18f-187">Мобильный телефон</span><span class="sxs-lookup"><span data-stu-id="8b18f-187">Mobile Phone</span></span>  <br/> |<span data-ttu-id="8b18f-188">64</span><span class="sxs-lookup"><span data-stu-id="8b18f-188">64</span></span>  <br/> |
|<span data-ttu-id="8b18f-189">Факс</span><span class="sxs-lookup"><span data-stu-id="8b18f-189">Fax</span></span>  <br/> |<span data-ttu-id="8b18f-190">64</span><span class="sxs-lookup"><span data-stu-id="8b18f-190">64</span></span>  <br/> |
|<span data-ttu-id="8b18f-191">Адрес</span><span class="sxs-lookup"><span data-stu-id="8b18f-191">Address</span></span>  <br/> |<span data-ttu-id="8b18f-192">1023</span><span class="sxs-lookup"><span data-stu-id="8b18f-192">1023</span></span>  <br/> |
|<span data-ttu-id="8b18f-193">Город</span><span class="sxs-lookup"><span data-stu-id="8b18f-193">City</span></span>  <br/> |<span data-ttu-id="8b18f-194">128</span><span class="sxs-lookup"><span data-stu-id="8b18f-194">128</span></span>  <br/> |
|<span data-ttu-id="8b18f-195">Область или край</span><span class="sxs-lookup"><span data-stu-id="8b18f-195">State or Province</span></span>  <br/> |<span data-ttu-id="8b18f-196">128</span><span class="sxs-lookup"><span data-stu-id="8b18f-196">128</span></span>  <br/> |
|<span data-ttu-id="8b18f-197">Почтовый индекс</span><span class="sxs-lookup"><span data-stu-id="8b18f-197">ZIP or Postal Code</span></span>  <br/> |<span data-ttu-id="8b18f-198">40</span><span class="sxs-lookup"><span data-stu-id="8b18f-198">40</span></span>  <br/> |
|<span data-ttu-id="8b18f-199">Страна</span><span class="sxs-lookup"><span data-stu-id="8b18f-199">Country or Region</span></span>  <br/> |<span data-ttu-id="8b18f-200">128</span><span class="sxs-lookup"><span data-stu-id="8b18f-200">128</span></span>  <br/> |
   
### <a name="still-having-problems-when-adding-users-to-microsoft-365"></a><span data-ttu-id="8b18f-201">Все еще возникают проблемы при добавлении пользователей в Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="8b18f-201">Still having problems when adding users to Microsoft 365?</span></span>

- <span data-ttu-id="8b18f-p117">**Убедитесь, что электронная таблица отформатирована правильно.** Проверьте соответствие заголовков столбцов заголовкам в примере файла. Убедитесь, что соблюдены ограничения на длину полей и что все поля разделены запятыми.</span><span class="sxs-lookup"><span data-stu-id="8b18f-p117">**Double-check that the spreadsheet is formatted correctly.** Check the column headings to make sure they match the headings in the sample file. Make sure you're following the rules for character lengths and that each field is separated by a comma.</span></span> 
    
- <span data-ttu-id="8b18f-205">**Если вы не видите новых пользователей в Microsoft 365, подождите несколько минут.**</span><span class="sxs-lookup"><span data-stu-id="8b18f-205">**If you don't see the new users in Microsoft 365 right away, wait a few minutes.**</span></span> <span data-ttu-id="8b18f-206">Изменение всех служб в Microsoft 365 может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="8b18f-206">It can take a little while for changes to go across all the services in Microsoft 365.</span></span> 
    
## <a name="related-articles"></a><span data-ttu-id="8b18f-207">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8b18f-207">Related articles</span></span>

[<span data-ttu-id="8b18f-208">Добавление пользователей по отдельности или с пакетом в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8b18f-208">Add users individually or in bulk to Microsoft 365</span></span>](https://docs.microsoft.com/office365/admin/add-users/add-users)




