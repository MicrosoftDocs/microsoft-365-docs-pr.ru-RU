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
ms.openlocfilehash: 475afc3b0622c404b50ebe5549bb5be85af80c5e
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423256"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a>Массовый импорт внешних контактов в Exchange Online

**Эта статья для администраторов. Вы пытаетесь импортировать контакты в собственный почтовый ящик? См. [в обзоре Импорт контактов в Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**
   
Имеет ли ваша компания множество существующих бизнес-контактов, которые необходимо включить в общую адресную книгу (также называемую глобальным адресным списком) в Exchange Online? Вы хотите добавить внешние контакты в качестве членов групп рассылки, как это можно сделать с пользователями внутри вашей компании? Если это так, вы можете использовать Exchange Online PowerShell и CSV (разделенное запятой значение) для массового импорта внешних контактов в Exchange Online. Это трехшаговая процедура:
  
[Шаг 1. Создание CSV-файла, содержаного сведения о внешних контактах](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[Шаг 2. Создание внешних контактов с PowerShell](#step-2-create-the-external-contacts-with-powershell) 

[Шаг 3. Добавление сведений о свойствах внешних контактов](#step-3-add-information-to-the-properties-of-the-external-contacts)

После выполнения этих действий по импорту контактов можно выполнить следующие дополнительные задачи:
  
- [Добавление дополнительных внешних контактов](#add-more-external-contacts)
  
- [Сокрытие внешних контактов из общей адресной книги](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a>Шаг 1. Создание CSV-файла, содержаного сведения о внешних контактах

На первом этапе необходимо создать CSV-файл, содержащий сведения о каждом внешнем контакте, который необходимо импортировать в Exchange Online. 
  
1. Скопируйте следующий текст в текстовый файл в NotePad и сохраните его на рабочем столе в виде CSV-файла с помощью суффикса файла .csv; например, ExternalContacts.csv.
    
    > [!TIP]
    > Если язык содержит специальные символы **(например, å,** **ä** и **ö** на шведском языке), сохраните CSV-файл с кодом UTF-8 или другим кодом единой кодировки при сохранения файла в NotePad. 
  
    ```text
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park
    ```

    В первой строке или строке заглавной строки файла CSV перечислены свойства контактов, которые можно использовать при импорте в Exchange Online. Каждое имя свойства разделено запятой. Каждая строка в строке загона представляет значения свойств для импорта одного внешнего контакта. 
    
    > [!NOTE]
    > Этот текст содержит пример данных, которые можно удалить. Но не удаляйте и не измените первую строку (заглавную строку). Он содержит все свойства внешних контактов. 
  
2. Откройте CSV-файл в Microsoft Excel, чтобы изменить CSV-файл, так как для редактирования CSV-файла проще использовать Excel.
    
3. Создайте строку для каждого контакта, который необходимо импортировать в Exchange Online. Заполнять как можно больше ячеек. Эти сведения будут отображаться в общей адресной книге для каждого контакта. 
    
    > [!IMPORTANT]
    >  Для создания внешнего контакта необходимы следующие свойства (которые являются первыми четырьмя элементами в строке заголовки) и должны быть заполнены в CSV-файле: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**. Команда PowerShell, которую вы запустите в шаге 2, будет использовать значения для этих свойств для создания контактов. 

## <a name="step-2-create-the-external-contacts-with-powershell"></a>Шаг 2. Создание внешних контактов с PowerShell

Следующим шагом является использование CSV-файла, созданного в шаге 1 и PowerShell, для массового импорта внешних контактов, перечисленных в CSV-файле, в Exchange Online. 
  
1.  Подключение PowerShell к организации Exchange Online. Пошаговые инструкции см. в статье [Подключение к Exchange Online с помощью удаленной оболочки PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Не забудьте использовать имя пользователя и пароль для глобальной учетной записи администратора при подключении к Exchange Online PowerShell. 
    
2. После подключения PowerShell к Exchange Online перейдите к настольной папке, в которой сохранен файл CSV в шаге 1; например `C:\Users\Administrator\desktop` .
    
3. Запустите следующую команду для создания внешних контактов:

    ```powershell
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    Создание новых контактов может занять некоторое время в зависимости от того, сколько вы импортируете. После завершения работы команды PowerShell отображает список созданных новых контактов. 
    
4. Чтобы просмотреть новые внешние контакты, перейдите в центр администрирования Exchange (EAC), а затем щелкните **Контакты** \> **получателей.** 
    
    > [!TIP]
    > Инструкции по подключению к EAC см. в центре администрирования [Exchange в Exchange Online.](https://go.microsoft.com/fwlink/p/?LinkId=328197) 
  
5. При необходимости **щелкните Обновление,** чтобы обновить список и увидеть внешние контакты, импортируемые. 
    
    Импортируемые контакты будут отображаться в общей адресной книге в Outlook и Outlook в Интернете.
    
    > [!NOTE]
    > Вы также можете просмотреть контакты в центре администрирования Microsoft 365, переехав к **контактам** \> **пользователей.** 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a>Шаг 3. Добавление сведений о свойствах внешних контактов

После запуска команды в шаге 2 создаются внешние контакты, но они не содержат никакой информации о контактах или организации, которая является информацией из большинства ячеек в CSV-файле. Это происходит потому, что при создании новых внешних контактов заполняются только необходимые свойства. Не волнуйтесь, если у вас нет всей информации, заполненной в CSV-файле. Если ее нет, она не будет добавлена.
  
1.  Подключение PowerShell к организации Exchange Online. Пошаговые инструкции см. в статье [Подключение к Exchange Online с помощью удаленной оболочки PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).
    
2. Перейдите к настольной папке, в которой сохранен файл CSV в шаге 1; например, `C:\Users\Administrator\desktop` .
    
3. Запустите следующие две команды, чтобы добавить другие свойства из CSV-файла в внешние контакты, созданные в шаге 2.
    
    ```powershell
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```powershell
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > Параметр  _Manager_ может быть проблематичным. Если ячейка является пустой в CSV-файле, вы получите ошибку, и ни одна из сведений о свойстве не будет добавлена в контакт. Если вам не нужно указать диспетчера, просто удалите из предыдущей  ` -Manager $_.Manager ` команды PowerShell. 
  
    Опять же, может потребоваться некоторое время для обновления контактов в зависимости от того, сколько вы импортировали в шаге 1. 
    
4. Чтобы убедиться, что свойства были добавлены в контакты: 
    
1. В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**.
    
2. Щелкните контакт, а затем **нажмите кнопку Изменить** изменить значок, чтобы отобразить ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) свойства контакта. 
    
Вот и все! Пользователи могут видеть контакты и дополнительные сведения в адресной книге Outlook и Outlook в Интернете.
  
## <a name="add-more-external-contacts"></a>Добавление дополнительных внешних контактов

Для добавления новых внешних контактов в Exchange Online можно повторить действия с 1 по шагу 3. Вы или пользователи в вашей компании можете просто добавить новую строку в CSV-файл для нового контакта. Затем можно запустить команды PowerShell из шаг 2 и шаг 3 для создания и добавления сведений в новые контакты.
  
> [!NOTE]
> При запуске команды для создания новых контактов может возникнуть ошибка, которая говорит, что контакты, созданные ранее, уже существуют. Но создается любой новый контакт, добавленный в CSV-файл. 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a>Скрыть внешние контакты из общей адресной книги>

Некоторые компании могут использовать внешние контакты только для того, чтобы они могли быть добавлены в группы рассылки. В этом случае может потребоваться скрыть внешние контакты из общей адресной книги. Вот как это сделать:
  
1.  Подключение PowerShell к организации Exchange Online. Пошаговые инструкции см. в статье [Подключение к Exchange Online с помощью удаленной оболочки PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).
    
2. Чтобы скрыть один внешний контакт, запустите следующую команду.
    
    ```powershell
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```

    Например, чтобы скрыть Pilar Pinilla из общей адресной книги, запустите эту команду:

    ```powershell
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```

3. Чтобы скрыть все внешние контакты из общей адресной книги, запустите эту команду:

    ```powershell
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

После их сокрытия внешние контакты не отображаются в общей адресной книге, но их можно добавить в качестве членов группы рассылки.
