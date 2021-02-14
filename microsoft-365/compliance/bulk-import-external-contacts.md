---
title: Массовый импорт внешних контактов в Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
description: Узнайте, как администраторы могут использовать Exchange Online PowerShell и CSV-файл для массового импорта внешних контактов в глобальный список адресов.
ms.openlocfilehash: 4d0b1a826583a032fd27c216367e99a6b7f8b371
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636347"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a><span data-ttu-id="55ae2-103">Массовый импорт внешних контактов в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="55ae2-103">Bulk import external contacts to Exchange Online</span></span>

<span data-ttu-id="55ae2-104">**Эта статья для администраторов. Вы пытаетесь импортировать контакты в свой почтовый ящик? См. ["Импорт контактов в Outlook"](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span><span class="sxs-lookup"><span data-stu-id="55ae2-104">**This article is for administrators. Are you trying to import contacts to your own mailbox? See [Import contacts to Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span></span>
   
<span data-ttu-id="55ae2-105">У вашей компании много существующих бизнес-контактов, которые вы хотите включить в общую адресную книгу (также называемую глобальным списком адресов) в Exchange Online?</span><span class="sxs-lookup"><span data-stu-id="55ae2-105">Does your company have lots of existing business contacts that you want to include in the shared address book (also called the global address list) in Exchange Online?</span></span> <span data-ttu-id="55ae2-106">Вы хотите добавить внешние контакты в качестве членов групп рассылки, как это можно сделать с пользователями в вашей компании?</span><span class="sxs-lookup"><span data-stu-id="55ae2-106">Do you want to add external contacts as members of distribution groups, just like you can with users inside your company?</span></span> <span data-ttu-id="55ae2-107">В этом случае вы можете использовать Exchange Online PowerShell и CSV-файл (разделенный запятой) для массового импорта внешних контактов в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="55ae2-107">If so, you can use Exchange Online PowerShell and a CSV (comma-separated value) file to bulk import external contacts into Exchange Online.</span></span> <span data-ttu-id="55ae2-108">Это трехшаговая процедура:</span><span class="sxs-lookup"><span data-stu-id="55ae2-108">It's a three-step process:</span></span>
  
[<span data-ttu-id="55ae2-109">Шаг 1. Создайте CSV-файл, содержащий сведения о внешних контактах</span><span class="sxs-lookup"><span data-stu-id="55ae2-109">Step 1: Create a CSV file that contains information about the external contacts</span></span>](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[<span data-ttu-id="55ae2-110">Шаг 2. Создание внешних контактов с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="55ae2-110">Step 2: Create the external contacts with PowerShell</span></span>](#step-2-create-the-external-contacts-with-powershell) 

[<span data-ttu-id="55ae2-111">Шаг 3. Добавление сведений в свойства внешних контактов</span><span class="sxs-lookup"><span data-stu-id="55ae2-111">Step 3: Add information to the properties of the external contacts</span></span>](#step-3-add-information-to-the-properties-of-the-external-contacts)

<span data-ttu-id="55ae2-112">После выполнения этих действий по импорту контактов можно выполнить следующие дополнительные задачи:</span><span class="sxs-lookup"><span data-stu-id="55ae2-112">After you complete these steps to import contacts, you can perform these additional tasks:</span></span>
  
- [<span data-ttu-id="55ae2-113">Добавление дополнительных внешних контактов</span><span class="sxs-lookup"><span data-stu-id="55ae2-113">Add more external contacts</span></span>](#add-more-external-contacts)
  
- [<span data-ttu-id="55ae2-114">Скрытие внешних контактов из общей адресной книги</span><span class="sxs-lookup"><span data-stu-id="55ae2-114">Hide external contacts from the shared address book</span></span>](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a><span data-ttu-id="55ae2-115">Шаг 1. Создайте CSV-файл, содержащий сведения о внешних контактах</span><span class="sxs-lookup"><span data-stu-id="55ae2-115">Step 1: Create a CSV file that contains information about the external contacts</span></span>

<span data-ttu-id="55ae2-116">Сначала необходимо создать CSV-файл, содержащий сведения о каждом внешнем контакте, который необходимо импортировать в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="55ae2-116">The first step is to create a CSV file that contains information about each external contact that you want to import to Exchange Online.</span></span> 
  
1. <span data-ttu-id="55ae2-117">Скопируйте следующий текст в текстовый файл в Блокноте и сохраните его на рабочем столе в виде CSV-файла с помощью суффикса CSV- имени файла; например, ExternalContacts.csv.</span><span class="sxs-lookup"><span data-stu-id="55ae2-117">Copy the following text to a text file in NotePad, and save it on your desktop as a CSV file by using a filename suffix of .csv; for example, ExternalContacts.csv.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="55ae2-118">Если ваш язык содержит специальные символы (например, **г,** **г** и **ö** на шведских языках), сохраните CSV-файл с кодировки UTF-8 или другой кодировки Юникода при сохранения файла в Блокноте.</span><span class="sxs-lookup"><span data-stu-id="55ae2-118">If your language contains special characters (such as **å**, **ä**, and **ö** in Swedish) save the CSV file with UTF-8 or other Unicode encoding when you save the file in NotePad.</span></span> 
  
    ```text
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park
    ```

    <span data-ttu-id="55ae2-119">В первой строке (строке с заготами) CSV-файла перечислены свойства контактов, которые можно использовать при импорте в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="55ae2-119">The first row, or header row, of the CSV file lists the properties of contacts that can be used when you import them to Exchange Online.</span></span> <span data-ttu-id="55ae2-120">Имя каждого свойства разделено запятой.</span><span class="sxs-lookup"><span data-stu-id="55ae2-120">Each property name is separated by a comma.</span></span> <span data-ttu-id="55ae2-121">Каждая строка под строкой header представляет значения свойств для импорта одного внешнего контакта.</span><span class="sxs-lookup"><span data-stu-id="55ae2-121">Each row under the header row represents the property values for importing a single external contact.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="55ae2-122">Этот текст содержит примеры данных, которые можно удалить.</span><span class="sxs-lookup"><span data-stu-id="55ae2-122">This text includes sample data, which you can delete.</span></span> <span data-ttu-id="55ae2-123">Но не удаляйте и не изменяйте первую строку (загон).</span><span class="sxs-lookup"><span data-stu-id="55ae2-123">But don't delete or change the first (header) row.</span></span> <span data-ttu-id="55ae2-124">Он содержит все свойства внешних контактов.</span><span class="sxs-lookup"><span data-stu-id="55ae2-124">It contains all of the properties for the external contacts.</span></span> 
  
2. <span data-ttu-id="55ae2-125">Откройте CSV-файл в Microsoft Excel, чтобы изменить CSV-файл, так как с помощью Excel намного проще редактировать CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="55ae2-125">Open the CSV file in Microsoft Excel to edit the CSV file because it's much easier to use Excel to edit the CSV file.</span></span>
    
3. <span data-ttu-id="55ae2-126">Создайте строку для каждого контакта, который вы хотите импортировать в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="55ae2-126">Create a row for each contact that you want to import to Exchange Online.</span></span> <span data-ttu-id="55ae2-127">Заполнять как можно больше ячеек.</span><span class="sxs-lookup"><span data-stu-id="55ae2-127">Populate as many of the cells as possible.</span></span> <span data-ttu-id="55ae2-128">Эти сведения будут отображаться в общей адресной книге для каждого контакта.</span><span class="sxs-lookup"><span data-stu-id="55ae2-128">This information will be displayed in the shared address book for each contact.</span></span> 
    
    > [!IMPORTANT]
    >  <span data-ttu-id="55ae2-129">Для создания внешнего контакта необходимы следующие свойства (которые являются первыми четырьмя элементами в строке header) и должны быть заполнены в CSV-файле: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**.</span><span class="sxs-lookup"><span data-stu-id="55ae2-129">The following properties (which are the first four items in the header row) are required to create an external contact and must be populated in the CSV file: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**.</span></span> <span data-ttu-id="55ae2-130">Команда PowerShell, которую вы запустите в шаге 2, будет использовать значения этих свойств для создания контактов.</span><span class="sxs-lookup"><span data-stu-id="55ae2-130">The PowerShell command that you run in Step 2 will use the values for these properties to create the contacts.</span></span> 

## <a name="step-2-create-the-external-contacts-with-powershell"></a><span data-ttu-id="55ae2-131">Шаг 2. Создание внешних контактов с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="55ae2-131">Step 2: Create the external contacts with PowerShell</span></span>

<span data-ttu-id="55ae2-132">Следующим шагом является использование CSV-файла, созданного на шаге 1, и PowerShell для массового импорта внешних контактов, перечисленных в CSV-файле, в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="55ae2-132">The next step is to use the CSV file that you created in Step 1 and PowerShell to bulk import the external contacts listed in the CSV file to Exchange Online.</span></span> 
  
1.  <span data-ttu-id="55ae2-133">Подключите PowerShell к организации Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="55ae2-133">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="55ae2-134">Пошаговые инструкции см. в статье [Подключение к Exchange Online с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="55ae2-134">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span> <span data-ttu-id="55ae2-135">При подключении к Exchange Online PowerShell обязательно используйте имя пользователя и пароль для учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="55ae2-135">Be sure to use the user name and password for your global administrator account when you connect to Exchange Online PowerShell.</span></span> 
    
2. <span data-ttu-id="55ae2-136">После подключения PowerShell к Exchange Online перейдите в папку рабочего стола, в которой вы сохранили CSV-файл на шаге 1; например. `C:\Users\Administrator\desktop`</span><span class="sxs-lookup"><span data-stu-id="55ae2-136">After you connect PowerShell to Exchange Online, go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="55ae2-137">Чтобы создать внешние контакты, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="55ae2-137">Run the following command to create the external contacts:</span></span>

    ```powershell
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    <span data-ttu-id="55ae2-138">Создание новых контактов может занять некоторое время в зависимости от того, сколько вы импортируете.</span><span class="sxs-lookup"><span data-stu-id="55ae2-138">It might take a while to create the new contacts, depending on how many you're importing.</span></span> <span data-ttu-id="55ae2-139">После завершения работы команды PowerShell отображает список новых созданных контактов.</span><span class="sxs-lookup"><span data-stu-id="55ae2-139">When the command is finished running, PowerShell displays a list of the new contacts that were created.</span></span> 
    
4. <span data-ttu-id="55ae2-140">Чтобы просмотреть новые внешние контакты, перейдите в Центр администрирования Exchange (EAC), а затем щелкните **"Контакты** \> **получателей".**</span><span class="sxs-lookup"><span data-stu-id="55ae2-140">To view the new external contacts, go to the Exchange admin center (EAC), and then click **Recipients** \> **Contacts**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="55ae2-141">Инструкции по подключению к Центру администрирования Exchange см. в Центре администрирования [Exchange в Exchange Online.](https://go.microsoft.com/fwlink/p/?LinkId=328197)</span><span class="sxs-lookup"><span data-stu-id="55ae2-141">For instructions for connecting to the EAC, see [Exchange admin center in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197).</span></span> 
  
5. <span data-ttu-id="55ae2-142">При необходимости нажмите **кнопку** "Обновить", чтобы обновить список и увидеть импортируемые внешние контакты.</span><span class="sxs-lookup"><span data-stu-id="55ae2-142">If necessary, click **Refresh** to update the list and see the external contacts that were imported.</span></span> 
    
    <span data-ttu-id="55ae2-143">Импортируемые контакты будут отображаться в общей адресной книге в Outlook и Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="55ae2-143">The imported contacts will appear in the shared address book in Outlook and Outlook on the web.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="55ae2-144">Вы также можете просматривать контакты в Центре администрирования Microsoft 365, переходить к **контактам** \> **пользователей.**</span><span class="sxs-lookup"><span data-stu-id="55ae2-144">You can also view the contacts in the Microsoft 365 admin center by going to **Users** \> **Contacts**.</span></span> 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a><span data-ttu-id="55ae2-145">Шаг 3. Добавление сведений в свойства внешних контактов</span><span class="sxs-lookup"><span data-stu-id="55ae2-145">Step 3: Add information to the properties of the external contacts</span></span>

<span data-ttu-id="55ae2-146">После запуска команды на шаге 2 создаются внешние контакты, но они не содержат контактов или сведений организации, которые являются сведениями из большинства ячеек в CSV-файле.</span><span class="sxs-lookup"><span data-stu-id="55ae2-146">After you run the command in Step 2, the external contacts are created, but they don't contain any of the contact or organization information, which is the information from most of the cells in the CSV file.</span></span> <span data-ttu-id="55ae2-147">Это происходит потому, что при создании новых внешних контактов заполняются только необходимые свойства.</span><span class="sxs-lookup"><span data-stu-id="55ae2-147">This is because when you create new external contacts, only the required properties are populated.</span></span> <span data-ttu-id="55ae2-148">Не волнуйтесь, если в CSV-файле не заполнены все сведения.</span><span class="sxs-lookup"><span data-stu-id="55ae2-148">Don't worry if you don't have all the information populated in the CSV file.</span></span> <span data-ttu-id="55ae2-149">Если его там нет, он не будет добавлен.</span><span class="sxs-lookup"><span data-stu-id="55ae2-149">If it's not there, it won't be added.</span></span>
  
1.  <span data-ttu-id="55ae2-150">Подключите PowerShell к организации Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="55ae2-150">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="55ae2-151">Пошаговые инструкции см. в статье [Подключение к Exchange Online с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="55ae2-151">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="55ae2-152">Перейдите в папку рабочего стола, в которой вы сохранили CSV-файл на шаге 1; например, `C:\Users\Administrator\desktop` .</span><span class="sxs-lookup"><span data-stu-id="55ae2-152">Go to the desktop folder where you saved the CSV file in Step 1; for example, `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="55ae2-153">Запустите следующие две команды, чтобы добавить другие свойства из CSV-файла к внешним контактам, созданным на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="55ae2-153">Run the following two commands to add the other properties from the CSV file to the external contacts that you created in Step 2.</span></span>
    
    ```powershell
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```powershell
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > <span data-ttu-id="55ae2-154">Параметр  _Manager_ может быть проблематичным.</span><span class="sxs-lookup"><span data-stu-id="55ae2-154">The  _Manager_ parameter might be problematic.</span></span> <span data-ttu-id="55ae2-155">Если ячейка в CSV-файле пуста, вы получите сообщение об ошибке, и никакие сведения о свойстве не будут добавлены в контакт.</span><span class="sxs-lookup"><span data-stu-id="55ae2-155">If the cell is blank in the CSV file, you will get an error and none of the property information will be added to the contact.</span></span> <span data-ttu-id="55ae2-156">Если вам не нужно указывать руководителя, просто удалите из предыдущей  ` -Manager $_.Manager ` команды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55ae2-156">If you don't need to specify a manager, then just delete  ` -Manager $_.Manager ` from the previous PowerShell command.</span></span> 
  
    <span data-ttu-id="55ae2-157">Повторим, обновление контактов может занять некоторое время в зависимости от того, сколько вы импортировали в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="55ae2-157">Again, it might take a while to update the contacts, depending on how many you imported in Step 1.</span></span> 
    
4. <span data-ttu-id="55ae2-158">Чтобы убедиться, что свойства были добавлены к контактам:</span><span class="sxs-lookup"><span data-stu-id="55ae2-158">To verify that the properties were added to the contacts:</span></span> 
    
1. <span data-ttu-id="55ae2-159">В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**.</span><span class="sxs-lookup"><span data-stu-id="55ae2-159">In the EAC, go to **Recipients** \> **Contacts**.</span></span>
    
2. <span data-ttu-id="55ae2-160">Щелкните контакт и нажмите **значок редактирования,** чтобы отобразить ![ свойства ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) контакта.</span><span class="sxs-lookup"><span data-stu-id="55ae2-160">Click a contact and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) to display the contact's properties.</span></span> 
    
<span data-ttu-id="55ae2-161">Вот и все!</span><span class="sxs-lookup"><span data-stu-id="55ae2-161">That's it!</span></span> <span data-ttu-id="55ae2-162">Пользователи могут видеть контакты и дополнительные сведения в адресной книге Outlook и Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="55ae2-162">Users can see the contacts and the additional information in the address book Outlook and Outlook on the web.</span></span>
  
## <a name="add-more-external-contacts"></a><span data-ttu-id="55ae2-163">Добавление дополнительных внешних контактов</span><span class="sxs-lookup"><span data-stu-id="55ae2-163">Add more external contacts</span></span>

<span data-ttu-id="55ae2-164">Вы можете повторить шаги с 1 по 3, чтобы добавить новые внешние контакты в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="55ae2-164">You can repeat Steps 1 through Step 3 to add new external contacts in Exchange Online.</span></span> <span data-ttu-id="55ae2-165">Вы или пользователи в своей компании можете просто добавить новую строку в CSV-файл для нового контакта.</span><span class="sxs-lookup"><span data-stu-id="55ae2-165">You or users in your company can just add a new row in the CSV file for the new contact.</span></span> <span data-ttu-id="55ae2-166">Затем можно выполнить команды PowerShell из шагов 2 и 3, чтобы создать и добавить сведения для новых контактов.</span><span class="sxs-lookup"><span data-stu-id="55ae2-166">Then you can run the PowerShell commands from Step 2 and Step 3 to create and add information to the new contacts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="55ae2-167">При запуске команды для создания новых контактов может возникнуть ошибка с сообщением о том, что контакты, созданные ранее, уже существуют.</span><span class="sxs-lookup"><span data-stu-id="55ae2-167">When you run the command to create new contacts, you might get an error saying that the contacts that were created earlier already exist.</span></span> <span data-ttu-id="55ae2-168">Но создается любой новый контакт, добавленный в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="55ae2-168">But any new contact added to the CSV file is created.</span></span> 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a><span data-ttu-id="55ae2-169">Скрытие внешних контактов из общей адресной книги></span><span class="sxs-lookup"><span data-stu-id="55ae2-169">Hide external contacts from the shared address book></span></span>

<span data-ttu-id="55ae2-170">Некоторые компании могут использовать только внешние контакты, чтобы их можно было добавить в качестве членов групп рассылки.</span><span class="sxs-lookup"><span data-stu-id="55ae2-170">Some companies may use external contacts only so they can be added as members of distribution groups.</span></span> <span data-ttu-id="55ae2-171">В этом сценарии может потребоваться скрыть внешние контакты из общей адресной книги.</span><span class="sxs-lookup"><span data-stu-id="55ae2-171">In this scenario, they may want to hide external contacts from the shared address book.</span></span> <span data-ttu-id="55ae2-172">Вот как это сделать:</span><span class="sxs-lookup"><span data-stu-id="55ae2-172">Here's how:</span></span>
  
1.  <span data-ttu-id="55ae2-173">Подключите PowerShell к организации Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="55ae2-173">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="55ae2-174">Пошаговые инструкции см. в статье [Подключение к Exchange Online с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="55ae2-174">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="55ae2-175">Чтобы скрыть один внешний контакт, запустите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="55ae2-175">To hide a single external contact, run the following command.</span></span>
    
    ```powershell
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```

    <span data-ttu-id="55ae2-176">Например, чтобы скрыть Pilar Pinilla из общей адресной книги, запустите команду:</span><span class="sxs-lookup"><span data-stu-id="55ae2-176">For example, to hide Pilar Pinilla from the shared address book, run this command:</span></span>

    ```powershell
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```

3. <span data-ttu-id="55ae2-177">Чтобы скрыть все внешние контакты из общей адресной книги, запустите команду:</span><span class="sxs-lookup"><span data-stu-id="55ae2-177">To hide all external contacts from the shared address book, run this command:</span></span>

    ```powershell
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

<span data-ttu-id="55ae2-178">После того как вы скрываете их, внешние контакты не отображаются в общей адресной книге, но вы по-прежнему можете добавить их в качестве членов группы рассылки.</span><span class="sxs-lookup"><span data-stu-id="55ae2-178">After you hide them, external contacts aren't displayed in the shared address book, but you can still add them as members of a distribution group.</span></span>
