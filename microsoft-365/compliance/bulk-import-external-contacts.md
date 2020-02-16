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
ms.openlocfilehash: c74e8932f7ed2feeca472848c88bdddbc740fe28
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078956"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a><span data-ttu-id="4a6fb-103">Массовый импорт внешних контактов в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4a6fb-103">Bulk import external contacts to Exchange Online</span></span>

<span data-ttu-id="4a6fb-104">**Эта статья предназначена для администраторов. Вы пытаетесь импортировать контакты в свой почтовый ящик? Просмотр [контактов для импорта в Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span><span class="sxs-lookup"><span data-stu-id="4a6fb-104">**This article is for administrators. Are you trying to import contacts to your own mailbox? See [Import contacts to Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span></span>
   
<span data-ttu-id="4a6fb-105">Есть ли у вашей компании множество существующих бизнес-контактов, которые вы хотите включить в общую адресную книгу (также называемую глобальным списком адресов) в Exchange Online?</span><span class="sxs-lookup"><span data-stu-id="4a6fb-105">Does your company have lots of existing business contacts that you want to include in the shared address book (also called the global address list) in Exchange Online?</span></span> <span data-ttu-id="4a6fb-106">Вы хотите добавить внешних контактов в качестве участников групп рассылки, как и для пользователей внутри вашей компании?</span><span class="sxs-lookup"><span data-stu-id="4a6fb-106">Do you want to add external contacts as members of distribution groups, just like you can with users inside your company?</span></span> <span data-ttu-id="4a6fb-107">В этом случае можно использовать Exchange Online PowerShell и CSV-файл (значение с разделителями-запятыми) для массового импорта внешних контактов в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-107">If so, you can use Exchange Online PowerShell and a CSV (comma-separated value) file to bulk import external contacts into Exchange Online.</span></span> <span data-ttu-id="4a6fb-108">Это процесс из трех этапов:</span><span class="sxs-lookup"><span data-stu-id="4a6fb-108">It's a three-step process:</span></span>
  
[<span data-ttu-id="4a6fb-109">Шаг 1: создание CSV-файла, содержащего сведения о внешних контактах</span><span class="sxs-lookup"><span data-stu-id="4a6fb-109">Step 1: Create a CSV file that contains information about the external contacts</span></span>](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[<span data-ttu-id="4a6fb-110">Шаг 2: создание внешних контактов с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a6fb-110">Step 2: Create the external contacts with PowerShell</span></span>](#step-2-create-the-external-contacts-with-powershell) 

[<span data-ttu-id="4a6fb-111">Шаг 3: Добавление сведений в свойства внешних контактов</span><span class="sxs-lookup"><span data-stu-id="4a6fb-111">Step 3: Add information to the properties of the external contacts</span></span>](#step-3-add-information-to-the-properties-of-the-external-contacts)

<span data-ttu-id="4a6fb-112">После выполнения этих действий для импорта контактов можно выполнить следующие дополнительные задачи:</span><span class="sxs-lookup"><span data-stu-id="4a6fb-112">After you complete these steps to import contacts, you can perform these additional tasks:</span></span>
  
- [<span data-ttu-id="4a6fb-113">Добавление дополнительных внешних контактов</span><span class="sxs-lookup"><span data-stu-id="4a6fb-113">Add more external contacts</span></span>](#add-more-external-contacts)
  
- [<span data-ttu-id="4a6fb-114">Скрытие внешних контактов из общей адресной книги</span><span class="sxs-lookup"><span data-stu-id="4a6fb-114">Hide external contacts from the shared address book</span></span>](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a><span data-ttu-id="4a6fb-115">Шаг 1: создание CSV-файла, содержащего сведения о внешних контактах</span><span class="sxs-lookup"><span data-stu-id="4a6fb-115">Step 1: Create a CSV file that contains information about the external contacts</span></span>

<span data-ttu-id="4a6fb-116">Первым шагом является создание CSV-файла, который содержит сведения о каждом внешнем контакте, который вы хотите импортировать в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-116">The first step is to create a CSV file that contains information about each external contact that you want to import to Exchange Online.</span></span> 
  
1. <span data-ttu-id="4a6fb-117">Скопируйте приведенный ниже текст в текстовый файл в блокноте и сохраните его на рабочем столе в виде CSV-файла с помощью суффикса имени файла. CSV; Например, Екстерналконтактс. csv.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-117">Copy the following text to a text file in NotePad, and save it on your desktop as a CSV file by using a filename suffix of .csv; for example, ExternalContacts.csv.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="4a6fb-118">Если в вашем языке есть специальные символы (например, **å**, **ä**и **ö** в шведском языке), сохраните CSV-файл в кодировке UTF-8 или другой кодировке Юникод при сохранении файла в блокноте.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-118">If your language contains special characters (such as **å**, **ä**, and **ö** in Swedish) save the CSV file with UTF-8 or other Unicode encoding when you save the file in NotePad.</span></span> 
  
    ```text
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park
    ```

    <span data-ttu-id="4a6fb-119">В первой строке (строке заголовков) CSV-файла перечислены свойства контактов, которые можно использовать при импорте в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-119">The first row, or header row, of the CSV file lists the properties of contacts that can be used when you import them to Exchange Online.</span></span> <span data-ttu-id="4a6fb-120">Каждое имя свойства отделяется запятыми.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-120">Each property name is separated by a comma.</span></span> <span data-ttu-id="4a6fb-121">Каждая строка под строкой заголовков представляет значения свойств для импорта одного внешнего контакта.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-121">Each row under the header row represents the property values for importing a single external contact.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="4a6fb-122">Этот текст содержит примеры данных, которые можно удалить.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-122">This text includes sample data, which you can delete.</span></span> <span data-ttu-id="4a6fb-123">Но не удаляйте и не изменяйте первую строку (заголовок).</span><span class="sxs-lookup"><span data-stu-id="4a6fb-123">But don't delete or change the first (header) row.</span></span> <span data-ttu-id="4a6fb-124">Он содержит все свойства внешних контактов.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-124">It contains all of the properties for the external contacts.</span></span> 
  
2. <span data-ttu-id="4a6fb-125">Откройте CSV-файл в Microsoft Excel, чтобы изменить CSV-файл, так как он значительно упрощает редактирование CSV-файла с помощью Excel.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-125">Open the CSV file in Microsoft Excel to edit the CSV file because it's much easier to use Excel to edit the CSV file.</span></span>
    
3. <span data-ttu-id="4a6fb-126">Создайте строку для каждого контакта, который необходимо импортировать в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-126">Create a row for each contact that you want to import to Exchange Online.</span></span> <span data-ttu-id="4a6fb-127">Заполните как можно больше ячеек.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-127">Populate as many of the cells as possible.</span></span> <span data-ttu-id="4a6fb-128">Эти сведения будут отображаться в общей адресной книге для каждого контакта.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-128">This information will be displayed in the shared address book for each contact.</span></span> 
    
    > [!IMPORTANT]
    >  <span data-ttu-id="4a6fb-129">Следующие свойства (первые четыре элемента в строке заголовков) необходимы для создания внешнего контакта и должны быть заполнены в CSV-файле: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-129">The following properties (which are the first four items in the header row) are required to create an external contact and must be populated in the CSV file: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**.</span></span> <span data-ttu-id="4a6fb-130">Команда PowerShell, выполняемая в действии 2, будет использовать значения этих свойств для создания контактов.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-130">The PowerShell command that you run in Step 2 will use the values for these properties to create the contacts.</span></span> 

## <a name="step-2-create-the-external-contacts-with-powershell"></a><span data-ttu-id="4a6fb-131">Шаг 2: создание внешних контактов с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a6fb-131">Step 2: Create the external contacts with PowerShell</span></span>

<span data-ttu-id="4a6fb-132">Следующий шаг — использование CSV-файла, созданного в шаге 1, и PowerShell для массового импорта внешних контактов, указанных в CSV-файле, в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-132">The next step is to use the CSV file that you created in Step 1 and PowerShell to bulk import the external contacts listed in the CSV file to Exchange Online.</span></span> 
  
1.  <span data-ttu-id="4a6fb-133">Подключите PowerShell к организации Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-133">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="4a6fb-134">Пошаговые инструкции приведены [в статье подключение к Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="4a6fb-134">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span> <span data-ttu-id="4a6fb-135">При подключении к Exchange Online PowerShell обязательно используйте имя пользователя и пароль для учетной записи глобального администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-135">Be sure to use the user name and password for your Office 365 global administrator account when you connect to Exchange Online PowerShell.</span></span> 
    
2. <span data-ttu-id="4a6fb-136">После подключения PowerShell к Exchange Online перейдите в папку рабочего стола, в которой был сохранен CSV-файл на шаге 1. например `C:\Users\Administrator\desktop`:.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-136">After you connect PowerShell to Exchange Online, go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="4a6fb-137">Выполните следующую команду, чтобы создать внешние контакты:</span><span class="sxs-lookup"><span data-stu-id="4a6fb-137">Run the following command to create the external contacts:</span></span>

    ```powershell
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    <span data-ttu-id="4a6fb-138">Создание новых контактов может занять некоторое время, в зависимости от того, сколько вы импортируете.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-138">It might take a while to create the new contacts, depending on how many you're importing.</span></span> <span data-ttu-id="4a6fb-139">По завершении выполнения команды в PowerShell отображается список новых контактов, которые были созданы.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-139">When the command is finished running, PowerShell displays a list of the new contacts that were created.</span></span> 
    
4. <span data-ttu-id="4a6fb-140">Чтобы просмотреть новые внешние контакты, перейдите в центр администрирования Exchange, а затем щелкните **Контакты** **получателей** \> .</span><span class="sxs-lookup"><span data-stu-id="4a6fb-140">To view the new external contacts, go to the Exchange admin center (EAC), and then click **Recipients** \> **Contacts**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="4a6fb-141">Инструкции по подключению к [центру администрирования Exchange находятся в центре администрирования Exchange в Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197).</span><span class="sxs-lookup"><span data-stu-id="4a6fb-141">For instructions for connecting to the EAC, see [Exchange admin center in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197).</span></span> 
  
5. <span data-ttu-id="4a6fb-142">При необходимости нажмите кнопку **Обновить** , чтобы обновить список и просмотреть внешние контакты, которые были импортированы.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-142">If necessary, click **Refresh** to update the list and see the external contacts that were imported.</span></span> 
    
    <span data-ttu-id="4a6fb-143">Импортированные контакты будут отображаться в общей адресной книге Outlook и Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-143">The imported contacts will appear in the shared address book in Outlook and Outlook on the web.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4a6fb-144">Вы также можете просмотреть контакты в центре администрирования Microsoft 365, перейдя к **списку контактов** **пользователей** \> .</span><span class="sxs-lookup"><span data-stu-id="4a6fb-144">You can also view the contacts in the Microsoft 365 admin center by going to **Users** \> **Contacts**.</span></span> 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a><span data-ttu-id="4a6fb-145">Шаг 3: Добавление сведений в свойства внешних контактов</span><span class="sxs-lookup"><span data-stu-id="4a6fb-145">Step 3: Add information to the properties of the external contacts</span></span>

<span data-ttu-id="4a6fb-146">После выполнения команды, описанной в шаге 2, создаются внешние контакты, но они не содержат сведений о контакте или организации, которые представляют собой сведения из большинства ячеек в CSV-файле.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-146">After you run the command in Step 2, the external contacts are created, but they don't contain any of the contact or organization information, which is the information from most of the cells in the CSV file.</span></span> <span data-ttu-id="4a6fb-147">Это связано с тем, что при создании новых внешних контактов заполняются только обязательные свойства.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-147">This is because when you create new external contacts, only the required properties are populated.</span></span> <span data-ttu-id="4a6fb-148">Не беспокойтесь, если у вас нет всех данных в CSV-файле.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-148">Don't worry if you don't have all the information populated in the CSV file.</span></span> <span data-ttu-id="4a6fb-149">Если это не так, он не будет добавлен.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-149">If it's not there, it won't be added.</span></span>
  
1.  <span data-ttu-id="4a6fb-150">Подключите PowerShell к организации Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-150">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="4a6fb-151">Пошаговые инструкции приведены [в статье подключение к Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="4a6fb-151">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="4a6fb-152">Перейдите в папку рабочего стола, в которой вы сохранили CSV-файл на этапе 1; Пример: `C:\Users\Administrator\desktop`.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-152">Go to the desktop folder where you saved the CSV file in Step 1; for example, `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="4a6fb-153">Выполните две следующие команды, чтобы добавить другие свойства из CSV-файла во внешние контакты, созданные в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-153">Run the following two commands to add the other properties from the CSV file to the external contacts that you created in Step 2.</span></span>
    
    ```powershell
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```powershell
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > <span data-ttu-id="4a6fb-154">Параметр _Manager_ может вызывать проблемы.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-154">The  _Manager_ parameter might be problematic.</span></span> <span data-ttu-id="4a6fb-155">Если ячейка в CSV-файле пуста, возникнет ошибка, и в него не будет добавлено никакой информации о свойстве.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-155">If the cell is blank in the CSV file, you will get an error and none of the property information will be added to the contact.</span></span> <span data-ttu-id="4a6fb-156">Если вам не нужно указывать руководителя, просто удалите ` -Manager $_.Manager ` его из предыдущей команды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-156">If you don't need to specify a manager, then just delete  ` -Manager $_.Manager ` from the previous PowerShell command.</span></span> 
  
    <span data-ttu-id="4a6fb-157">Опять же, может потребоваться время на обновление контактов, в зависимости от количества, импортированного в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-157">Again, it might take a while to update the contacts, depending on how many you imported in Step 1.</span></span> 
    
4. <span data-ttu-id="4a6fb-158">Чтобы убедиться в том, что свойства добавлены в контакты:</span><span class="sxs-lookup"><span data-stu-id="4a6fb-158">To verify that the properties were added to the contacts:</span></span> 
    
1. <span data-ttu-id="4a6fb-159">В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-159">In the EAC, go to **Recipients** \> **Contacts**.</span></span>
    
2. <span data-ttu-id="4a6fb-160">Щелкните контакт, а затем щелкните **изменить** ![значок](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) редактирования, чтобы отобразить свойства контакта.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-160">Click a contact and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) to display the contact's properties.</span></span> 
    
<span data-ttu-id="4a6fb-161">Вот и все!</span><span class="sxs-lookup"><span data-stu-id="4a6fb-161">That's it!</span></span> <span data-ttu-id="4a6fb-162">Пользователи могут просматривать контакты и дополнительные сведения в адресной книге Outlook и Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-162">Users can see the contacts and the additional information in the address book Outlook and Outlook on the web.</span></span>
  
## <a name="add-more-external-contacts"></a><span data-ttu-id="4a6fb-163">Добавление дополнительных внешних контактов</span><span class="sxs-lookup"><span data-stu-id="4a6fb-163">Add more external contacts</span></span>

<span data-ttu-id="4a6fb-164">Вы можете повторить шаги 1 – 3, чтобы добавить новые внешние контакты в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-164">You can repeat Steps 1 through Step 3 to add new external contacts in Exchange Online.</span></span> <span data-ttu-id="4a6fb-165">Вы или пользователи вашей компании могут просто добавить новую строку в CSV-файл для нового контакта.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-165">You or users in your company can just add a new row in the CSV file for the new contact.</span></span> <span data-ttu-id="4a6fb-166">Затем вы можете выполнить команды PowerShell из шага 2 и 3, чтобы создать и добавить сведения в новые контакты.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-166">Then you can run the PowerShell commands from Step 2 and Step 3 to create and add information to the new contacts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4a6fb-167">При выполнении команды для создания новых контактов может возникать ошибка, сообщающая, что созданные ранее контакты уже существуют.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-167">When you run the command to create new contacts, you might get an error saying that the contacts that were created earlier already exist.</span></span> <span data-ttu-id="4a6fb-168">Все новые контакты, добавленные в CSV-файл, создаются.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-168">But any new contact added to the CSV file is created.</span></span> 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a><span data-ttu-id="4a6fb-169">Скрытие внешних контактов из общей адресной книги></span><span class="sxs-lookup"><span data-stu-id="4a6fb-169">Hide external contacts from the shared address book></span></span>

<span data-ttu-id="4a6fb-170">Некоторые компании могут использовать только внешние контакты, чтобы их можно было добавить в качестве членов групп рассылки.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-170">Some companies may use external contacts only so they can be added as members of distribution groups.</span></span> <span data-ttu-id="4a6fb-171">В этом сценарии может потребоваться скрыть внешние контакты из общей адресной книги.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-171">In this scenario, they may want to hide external contacts from the shared address book.</span></span> <span data-ttu-id="4a6fb-172">Вот как это сделать:</span><span class="sxs-lookup"><span data-stu-id="4a6fb-172">Here's how:</span></span>
  
1.  <span data-ttu-id="4a6fb-173">Подключите PowerShell к организации Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-173">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="4a6fb-174">Пошаговые инструкции приведены [в статье подключение к Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="4a6fb-174">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="4a6fb-175">Чтобы скрыть один внешний контакт, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-175">To hide a single external contact, run the following command.</span></span>
    
    ```powershell
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```

    <span data-ttu-id="4a6fb-176">Например, чтобы скрыть Pilar Pinilla из общей адресной книги, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4a6fb-176">For example, to hide Pilar Pinilla from the shared address book, run this command:</span></span>

    ```powershell
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```

3. <span data-ttu-id="4a6fb-177">Чтобы скрыть все внешние контакты из общей адресной книги, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4a6fb-177">To hide all external contacts from the shared address book, run this command:</span></span>

    ```powershell
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

<span data-ttu-id="4a6fb-178">После их скрытия внешние контакты не будут отображаться в общей адресной книге, но их можно добавить в качестве членов группы рассылки.</span><span class="sxs-lookup"><span data-stu-id="4a6fb-178">After you hide them, external contacts aren't displayed in the shared address book, but you can still add them as members of a distribution group.</span></span>
