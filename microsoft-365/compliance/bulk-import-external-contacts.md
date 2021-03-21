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
description: Узнайте, как администраторы могут использовать Exchange Online PowerShell и CSV-файл для массового импорта внешних контактов в глобальный адресный список.
ms.openlocfilehash: 178e3676f8dc5fb59cdad9cc46d7ecbd9dddb90e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918215"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a><span data-ttu-id="93b72-103">Массовый импорт внешних контактов в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="93b72-103">Bulk import external contacts to Exchange Online</span></span>

<span data-ttu-id="93b72-104">**Эта статья для администраторов. Вы пытаетесь импортировать контакты в собственный почтовый ящик? См. [в обзоре Импорт контактов в Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span><span class="sxs-lookup"><span data-stu-id="93b72-104">**This article is for administrators. Are you trying to import contacts to your own mailbox? See [Import contacts to Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span></span>
   
<span data-ttu-id="93b72-105">Имеет ли ваша компания множество существующих бизнес-контактов, которые необходимо включить в общую адресную книгу (также называемую глобальным адресным списком) в Exchange Online?</span><span class="sxs-lookup"><span data-stu-id="93b72-105">Does your company have lots of existing business contacts that you want to include in the shared address book (also called the global address list) in Exchange Online?</span></span> <span data-ttu-id="93b72-106">Вы хотите добавить внешние контакты в качестве членов групп рассылки, как это можно сделать с пользователями внутри вашей компании?</span><span class="sxs-lookup"><span data-stu-id="93b72-106">Do you want to add external contacts as members of distribution groups, just like you can with users inside your company?</span></span> <span data-ttu-id="93b72-107">Если это так, вы можете использовать Exchange Online PowerShell и CSV (разделенное запятой значение) для массового импорта внешних контактов в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="93b72-107">If so, you can use Exchange Online PowerShell and a CSV (comma-separated value) file to bulk import external contacts into Exchange Online.</span></span> <span data-ttu-id="93b72-108">Это трехшаговая процедура:</span><span class="sxs-lookup"><span data-stu-id="93b72-108">It's a three-step process:</span></span>
  
[<span data-ttu-id="93b72-109">Шаг 1. Создание CSV-файла, содержаного сведения о внешних контактах</span><span class="sxs-lookup"><span data-stu-id="93b72-109">Step 1: Create a CSV file that contains information about the external contacts</span></span>](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[<span data-ttu-id="93b72-110">Шаг 2. Создание внешних контактов с PowerShell</span><span class="sxs-lookup"><span data-stu-id="93b72-110">Step 2: Create the external contacts with PowerShell</span></span>](#step-2-create-the-external-contacts-with-powershell) 

[<span data-ttu-id="93b72-111">Шаг 3. Добавление сведений о свойствах внешних контактов</span><span class="sxs-lookup"><span data-stu-id="93b72-111">Step 3: Add information to the properties of the external contacts</span></span>](#step-3-add-information-to-the-properties-of-the-external-contacts)

<span data-ttu-id="93b72-112">После выполнения этих действий по импорту контактов можно выполнить следующие дополнительные задачи:</span><span class="sxs-lookup"><span data-stu-id="93b72-112">After you complete these steps to import contacts, you can perform these additional tasks:</span></span>
  
- [<span data-ttu-id="93b72-113">Добавление дополнительных внешних контактов</span><span class="sxs-lookup"><span data-stu-id="93b72-113">Add more external contacts</span></span>](#add-more-external-contacts)
  
- [<span data-ttu-id="93b72-114">Сокрытие внешних контактов из общей адресной книги</span><span class="sxs-lookup"><span data-stu-id="93b72-114">Hide external contacts from the shared address book</span></span>](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a><span data-ttu-id="93b72-115">Шаг 1. Создание CSV-файла, содержаного сведения о внешних контактах</span><span class="sxs-lookup"><span data-stu-id="93b72-115">Step 1: Create a CSV file that contains information about the external contacts</span></span>

<span data-ttu-id="93b72-116">На первом этапе необходимо создать CSV-файл, содержащий сведения о каждом внешнем контакте, который необходимо импортировать в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="93b72-116">The first step is to create a CSV file that contains information about each external contact that you want to import to Exchange Online.</span></span> 
  
1. <span data-ttu-id="93b72-117">Скопируйте следующий текст в текстовый файл в NotePad и сохраните его на рабочем столе в виде CSV-файла с помощью суффикса файла .csv; например, ExternalContacts.csv.</span><span class="sxs-lookup"><span data-stu-id="93b72-117">Copy the following text to a text file in NotePad, and save it on your desktop as a CSV file by using a filename suffix of .csv; for example, ExternalContacts.csv.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="93b72-118">Если язык содержит специальные символы **(например, å,** **ä** и **ö** на шведском языке), сохраните CSV-файл с кодом UTF-8 или другим кодом единой кодировки при сохранения файла в NotePad.</span><span class="sxs-lookup"><span data-stu-id="93b72-118">If your language contains special characters (such as **å**, **ä**, and **ö** in Swedish) save the CSV file with UTF-8 or other Unicode encoding when you save the file in NotePad.</span></span> 
  
    ```text
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park
    ```

    <span data-ttu-id="93b72-119">В первой строке или строке заглавной строки файла CSV перечислены свойства контактов, которые можно использовать при импорте в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="93b72-119">The first row, or header row, of the CSV file lists the properties of contacts that can be used when you import them to Exchange Online.</span></span> <span data-ttu-id="93b72-120">Каждое имя свойства разделено запятой.</span><span class="sxs-lookup"><span data-stu-id="93b72-120">Each property name is separated by a comma.</span></span> <span data-ttu-id="93b72-121">Каждая строка в строке загона представляет значения свойств для импорта одного внешнего контакта.</span><span class="sxs-lookup"><span data-stu-id="93b72-121">Each row under the header row represents the property values for importing a single external contact.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="93b72-122">Этот текст содержит пример данных, которые можно удалить.</span><span class="sxs-lookup"><span data-stu-id="93b72-122">This text includes sample data, which you can delete.</span></span> <span data-ttu-id="93b72-123">Но не удаляйте и не измените первую строку (заглавную строку).</span><span class="sxs-lookup"><span data-stu-id="93b72-123">But don't delete or change the first (header) row.</span></span> <span data-ttu-id="93b72-124">Он содержит все свойства внешних контактов.</span><span class="sxs-lookup"><span data-stu-id="93b72-124">It contains all of the properties for the external contacts.</span></span> 
  
2. <span data-ttu-id="93b72-125">Откройте CSV-файл в Microsoft Excel, чтобы изменить CSV-файл, так как для редактирования CSV-файла проще использовать Excel.</span><span class="sxs-lookup"><span data-stu-id="93b72-125">Open the CSV file in Microsoft Excel to edit the CSV file because it's much easier to use Excel to edit the CSV file.</span></span>
    
3. <span data-ttu-id="93b72-126">Создайте строку для каждого контакта, который необходимо импортировать в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="93b72-126">Create a row for each contact that you want to import to Exchange Online.</span></span> <span data-ttu-id="93b72-127">Заполнять как можно больше ячеек.</span><span class="sxs-lookup"><span data-stu-id="93b72-127">Populate as many of the cells as possible.</span></span> <span data-ttu-id="93b72-128">Эти сведения будут отображаться в общей адресной книге для каждого контакта.</span><span class="sxs-lookup"><span data-stu-id="93b72-128">This information will be displayed in the shared address book for each contact.</span></span> 
    
    > [!IMPORTANT]
    >  <span data-ttu-id="93b72-129">Для создания внешнего контакта необходимы следующие свойства (которые являются первыми четырьмя элементами в строке заголовки) и должны быть заполнены в CSV-файле: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**.</span><span class="sxs-lookup"><span data-stu-id="93b72-129">The following properties (which are the first four items in the header row) are required to create an external contact and must be populated in the CSV file: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**.</span></span> <span data-ttu-id="93b72-130">Команда PowerShell, которую вы запустите в шаге 2, будет использовать значения для этих свойств для создания контактов.</span><span class="sxs-lookup"><span data-stu-id="93b72-130">The PowerShell command that you run in Step 2 will use the values for these properties to create the contacts.</span></span> 

## <a name="step-2-create-the-external-contacts-with-powershell"></a><span data-ttu-id="93b72-131">Шаг 2. Создание внешних контактов с PowerShell</span><span class="sxs-lookup"><span data-stu-id="93b72-131">Step 2: Create the external contacts with PowerShell</span></span>

<span data-ttu-id="93b72-132">Следующим шагом является использование CSV-файла, созданного в шаге 1 и PowerShell, для массового импорта внешних контактов, перечисленных в CSV-файле, в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="93b72-132">The next step is to use the CSV file that you created in Step 1 and PowerShell to bulk import the external contacts listed in the CSV file to Exchange Online.</span></span> 
  
1.  <span data-ttu-id="93b72-133">Подключение PowerShell к организации Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="93b72-133">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="93b72-134">Пошаговые инструкции см. в статье [Подключение к Exchange Online с помощью удаленной оболочки PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="93b72-134">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="93b72-135">Не забудьте использовать имя пользователя и пароль для глобальной учетной записи администратора при подключении к Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93b72-135">Be sure to use the user name and password for your global administrator account when you connect to Exchange Online PowerShell.</span></span> 
    
2. <span data-ttu-id="93b72-136">После подключения PowerShell к Exchange Online перейдите к настольной папке, в которой сохранен файл CSV в шаге 1; например `C:\Users\Administrator\desktop` .</span><span class="sxs-lookup"><span data-stu-id="93b72-136">After you connect PowerShell to Exchange Online, go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="93b72-137">Запустите следующую команду для создания внешних контактов:</span><span class="sxs-lookup"><span data-stu-id="93b72-137">Run the following command to create the external contacts:</span></span>

    ```powershell
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    <span data-ttu-id="93b72-138">Создание новых контактов может занять некоторое время в зависимости от того, сколько вы импортируете.</span><span class="sxs-lookup"><span data-stu-id="93b72-138">It might take a while to create the new contacts, depending on how many you're importing.</span></span> <span data-ttu-id="93b72-139">После завершения работы команды PowerShell отображает список созданных новых контактов.</span><span class="sxs-lookup"><span data-stu-id="93b72-139">When the command is finished running, PowerShell displays a list of the new contacts that were created.</span></span> 
    
4. <span data-ttu-id="93b72-140">Чтобы просмотреть новые внешние контакты, перейдите в центр администрирования Exchange (EAC), а затем щелкните **Контакты** \> **получателей.**</span><span class="sxs-lookup"><span data-stu-id="93b72-140">To view the new external contacts, go to the Exchange admin center (EAC), and then click **Recipients** \> **Contacts**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="93b72-141">Инструкции по подключению к EAC см. в центре администрирования [Exchange в Exchange Online.](/exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="93b72-141">For instructions for connecting to the EAC, see [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span></span> 
  
5. <span data-ttu-id="93b72-142">При необходимости **щелкните Обновление,** чтобы обновить список и увидеть внешние контакты, импортируемые.</span><span class="sxs-lookup"><span data-stu-id="93b72-142">If necessary, click **Refresh** to update the list and see the external contacts that were imported.</span></span> 
    
    <span data-ttu-id="93b72-143">Импортируемые контакты будут отображаться в общей адресной книге в Outlook и Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="93b72-143">The imported contacts will appear in the shared address book in Outlook and Outlook on the web.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="93b72-144">Вы также можете просмотреть контакты в центре администрирования Microsoft 365, переехав к **контактам** \> **пользователей.**</span><span class="sxs-lookup"><span data-stu-id="93b72-144">You can also view the contacts in the Microsoft 365 admin center by going to **Users** \> **Contacts**.</span></span> 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a><span data-ttu-id="93b72-145">Шаг 3. Добавление сведений о свойствах внешних контактов</span><span class="sxs-lookup"><span data-stu-id="93b72-145">Step 3: Add information to the properties of the external contacts</span></span>

<span data-ttu-id="93b72-146">После запуска команды в шаге 2 создаются внешние контакты, но они не содержат никакой информации о контактах или организации, которая является информацией из большинства ячеек в CSV-файле.</span><span class="sxs-lookup"><span data-stu-id="93b72-146">After you run the command in Step 2, the external contacts are created, but they don't contain any of the contact or organization information, which is the information from most of the cells in the CSV file.</span></span> <span data-ttu-id="93b72-147">Это происходит потому, что при создании новых внешних контактов заполняются только необходимые свойства.</span><span class="sxs-lookup"><span data-stu-id="93b72-147">This is because when you create new external contacts, only the required properties are populated.</span></span> <span data-ttu-id="93b72-148">Не волнуйтесь, если у вас нет всей информации, заполненной в CSV-файле.</span><span class="sxs-lookup"><span data-stu-id="93b72-148">Don't worry if you don't have all the information populated in the CSV file.</span></span> <span data-ttu-id="93b72-149">Если ее нет, она не будет добавлена.</span><span class="sxs-lookup"><span data-stu-id="93b72-149">If it's not there, it won't be added.</span></span>
  
1.  <span data-ttu-id="93b72-150">Подключение PowerShell к организации Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="93b72-150">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="93b72-151">Пошаговые инструкции см. в статье [Подключение к Exchange Online с помощью удаленной оболочки PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="93b72-151">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="93b72-152">Перейдите к настольной папке, в которой сохранен файл CSV в шаге 1; например, `C:\Users\Administrator\desktop` .</span><span class="sxs-lookup"><span data-stu-id="93b72-152">Go to the desktop folder where you saved the CSV file in Step 1; for example, `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="93b72-153">Запустите следующие две команды, чтобы добавить другие свойства из CSV-файла в внешние контакты, созданные в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="93b72-153">Run the following two commands to add the other properties from the CSV file to the external contacts that you created in Step 2.</span></span>
    
    ```powershell
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```powershell
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > <span data-ttu-id="93b72-154">Параметр  _Manager_ может быть проблематичным.</span><span class="sxs-lookup"><span data-stu-id="93b72-154">The  _Manager_ parameter might be problematic.</span></span> <span data-ttu-id="93b72-155">Если ячейка является пустой в CSV-файле, вы получите ошибку, и ни одна из сведений о свойстве не будет добавлена в контакт.</span><span class="sxs-lookup"><span data-stu-id="93b72-155">If the cell is blank in the CSV file, you will get an error and none of the property information will be added to the contact.</span></span> <span data-ttu-id="93b72-156">Если вам не нужно указать диспетчера, просто удалите из предыдущей  ` -Manager $_.Manager ` команды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93b72-156">If you don't need to specify a manager, then just delete  ` -Manager $_.Manager ` from the previous PowerShell command.</span></span> 
  
    <span data-ttu-id="93b72-157">Опять же, может потребоваться некоторое время для обновления контактов в зависимости от того, сколько вы импортировали в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="93b72-157">Again, it might take a while to update the contacts, depending on how many you imported in Step 1.</span></span> 
    
4. <span data-ttu-id="93b72-158">Чтобы убедиться, что свойства были добавлены в контакты:</span><span class="sxs-lookup"><span data-stu-id="93b72-158">To verify that the properties were added to the contacts:</span></span> 
    
1. <span data-ttu-id="93b72-159">В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**.</span><span class="sxs-lookup"><span data-stu-id="93b72-159">In the EAC, go to **Recipients** \> **Contacts**.</span></span>
    
2. <span data-ttu-id="93b72-160">Щелкните контакт, а затем **нажмите кнопку Изменить** изменить значок, чтобы отобразить ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) свойства контакта.</span><span class="sxs-lookup"><span data-stu-id="93b72-160">Click a contact and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) to display the contact's properties.</span></span> 
    
<span data-ttu-id="93b72-161">Вот и все!</span><span class="sxs-lookup"><span data-stu-id="93b72-161">That's it!</span></span> <span data-ttu-id="93b72-162">Пользователи могут видеть контакты и дополнительные сведения в адресной книге Outlook и Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="93b72-162">Users can see the contacts and the additional information in the address book Outlook and Outlook on the web.</span></span>
  
## <a name="add-more-external-contacts"></a><span data-ttu-id="93b72-163">Добавление дополнительных внешних контактов</span><span class="sxs-lookup"><span data-stu-id="93b72-163">Add more external contacts</span></span>

<span data-ttu-id="93b72-164">Для добавления новых внешних контактов в Exchange Online можно повторить действия с 1 по шагу 3.</span><span class="sxs-lookup"><span data-stu-id="93b72-164">You can repeat Steps 1 through Step 3 to add new external contacts in Exchange Online.</span></span> <span data-ttu-id="93b72-165">Вы или пользователи в вашей компании можете просто добавить новую строку в CSV-файл для нового контакта.</span><span class="sxs-lookup"><span data-stu-id="93b72-165">You or users in your company can just add a new row in the CSV file for the new contact.</span></span> <span data-ttu-id="93b72-166">Затем можно запустить команды PowerShell из шаг 2 и шаг 3 для создания и добавления сведений в новые контакты.</span><span class="sxs-lookup"><span data-stu-id="93b72-166">Then you can run the PowerShell commands from Step 2 and Step 3 to create and add information to the new contacts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="93b72-167">При запуске команды для создания новых контактов может возникнуть ошибка, которая говорит, что контакты, созданные ранее, уже существуют.</span><span class="sxs-lookup"><span data-stu-id="93b72-167">When you run the command to create new contacts, you might get an error saying that the contacts that were created earlier already exist.</span></span> <span data-ttu-id="93b72-168">Но создается любой новый контакт, добавленный в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="93b72-168">But any new contact added to the CSV file is created.</span></span> 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a><span data-ttu-id="93b72-169">Скрыть внешние контакты из общей адресной книги></span><span class="sxs-lookup"><span data-stu-id="93b72-169">Hide external contacts from the shared address book></span></span>

<span data-ttu-id="93b72-170">Некоторые компании могут использовать внешние контакты только для того, чтобы они могли быть добавлены в группы рассылки.</span><span class="sxs-lookup"><span data-stu-id="93b72-170">Some companies may use external contacts only so they can be added as members of distribution groups.</span></span> <span data-ttu-id="93b72-171">В этом случае может потребоваться скрыть внешние контакты из общей адресной книги.</span><span class="sxs-lookup"><span data-stu-id="93b72-171">In this scenario, they may want to hide external contacts from the shared address book.</span></span> <span data-ttu-id="93b72-172">Вот как это сделать:</span><span class="sxs-lookup"><span data-stu-id="93b72-172">Here's how:</span></span>
  
1.  <span data-ttu-id="93b72-173">Подключение PowerShell к организации Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="93b72-173">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="93b72-174">Пошаговые инструкции см. в статье [Подключение к Exchange Online с помощью удаленной оболочки PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="93b72-174">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="93b72-175">Чтобы скрыть один внешний контакт, запустите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="93b72-175">To hide a single external contact, run the following command.</span></span>
    
    ```powershell
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```

    <span data-ttu-id="93b72-176">Например, чтобы скрыть Pilar Pinilla из общей адресной книги, запустите эту команду:</span><span class="sxs-lookup"><span data-stu-id="93b72-176">For example, to hide Pilar Pinilla from the shared address book, run this command:</span></span>

    ```powershell
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```

3. <span data-ttu-id="93b72-177">Чтобы скрыть все внешние контакты из общей адресной книги, запустите эту команду:</span><span class="sxs-lookup"><span data-stu-id="93b72-177">To hide all external contacts from the shared address book, run this command:</span></span>

    ```powershell
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

<span data-ttu-id="93b72-178">После их сокрытия внешние контакты не отображаются в общей адресной книге, но их можно добавить в качестве членов группы рассылки.</span><span class="sxs-lookup"><span data-stu-id="93b72-178">After you hide them, external contacts aren't displayed in the shared address book, but you can still add them as members of a distribution group.</span></span>