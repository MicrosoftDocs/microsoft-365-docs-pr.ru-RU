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
# <a name="bulk-import-external-contacts-to-exchange-online"></a>Массовый импорт внешних контактов в Exchange Online

**Эта статья предназначена для администраторов. Вы пытаетесь импортировать контакты в свой почтовый ящик? Просмотр [контактов для импорта в Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**
   
Есть ли у вашей компании множество существующих бизнес-контактов, которые вы хотите включить в общую адресную книгу (также называемую глобальным списком адресов) в Exchange Online? Вы хотите добавить внешних контактов в качестве участников групп рассылки, как и для пользователей внутри вашей компании? В этом случае можно использовать Exchange Online PowerShell и CSV-файл (значение с разделителями-запятыми) для массового импорта внешних контактов в Exchange Online. Это процесс из трех этапов:
  
[Шаг 1: создание CSV-файла, содержащего сведения о внешних контактах](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[Шаг 2: создание внешних контактов с помощью PowerShell](#step-2-create-the-external-contacts-with-powershell) 

[Шаг 3: Добавление сведений в свойства внешних контактов](#step-3-add-information-to-the-properties-of-the-external-contacts)

После выполнения этих действий для импорта контактов можно выполнить следующие дополнительные задачи:
  
- [Добавление дополнительных внешних контактов](#add-more-external-contacts)
  
- [Скрытие внешних контактов из общей адресной книги](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a>Шаг 1: создание CSV-файла, содержащего сведения о внешних контактах

Первым шагом является создание CSV-файла, который содержит сведения о каждом внешнем контакте, который вы хотите импортировать в Exchange Online. 
  
1. Скопируйте приведенный ниже текст в текстовый файл в блокноте и сохраните его на рабочем столе в виде CSV-файла с помощью суффикса имени файла. CSV; Например, Екстерналконтактс. csv.
    
    > [!TIP]
    > Если в вашем языке есть специальные символы (например, **å**, **ä**и **ö** в шведском языке), сохраните CSV-файл в кодировке UTF-8 или другой кодировке Юникод при сохранении файла в блокноте. 
  
    ```text
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park
    ```

    В первой строке (строке заголовков) CSV-файла перечислены свойства контактов, которые можно использовать при импорте в Exchange Online. Каждое имя свойства отделяется запятыми. Каждая строка под строкой заголовков представляет значения свойств для импорта одного внешнего контакта. 
    
    > [!NOTE]
    > Этот текст содержит примеры данных, которые можно удалить. Но не удаляйте и не изменяйте первую строку (заголовок). Он содержит все свойства внешних контактов. 
  
2. Откройте CSV-файл в Microsoft Excel, чтобы изменить CSV-файл, так как он значительно упрощает редактирование CSV-файла с помощью Excel.
    
3. Создайте строку для каждого контакта, который необходимо импортировать в Exchange Online. Заполните как можно больше ячеек. Эти сведения будут отображаться в общей адресной книге для каждого контакта. 
    
    > [!IMPORTANT]
    >  Следующие свойства (первые четыре элемента в строке заголовков) необходимы для создания внешнего контакта и должны быть заполнены в CSV-файле: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**. Команда PowerShell, выполняемая в действии 2, будет использовать значения этих свойств для создания контактов. 

## <a name="step-2-create-the-external-contacts-with-powershell"></a>Шаг 2: создание внешних контактов с помощью PowerShell

Следующий шаг — использование CSV-файла, созданного в шаге 1, и PowerShell для массового импорта внешних контактов, указанных в CSV-файле, в Exchange Online. 
  
1.  Подключите PowerShell к организации Exchange Online. Пошаговые инструкции приведены [в статье подключение к Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554). При подключении к Exchange Online PowerShell обязательно используйте имя пользователя и пароль для учетной записи глобального администратора Office 365. 
    
2. После подключения PowerShell к Exchange Online перейдите в папку рабочего стола, в которой был сохранен CSV-файл на шаге 1. например `C:\Users\Administrator\desktop`:.
    
3. Выполните следующую команду, чтобы создать внешние контакты:

    ```powershell
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    Создание новых контактов может занять некоторое время, в зависимости от того, сколько вы импортируете. По завершении выполнения команды в PowerShell отображается список новых контактов, которые были созданы. 
    
4. Чтобы просмотреть новые внешние контакты, перейдите в центр администрирования Exchange, а затем щелкните **Контакты** **получателей** \> . 
    
    > [!TIP]
    > Инструкции по подключению к [центру администрирования Exchange находятся в центре администрирования Exchange в Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197). 
  
5. При необходимости нажмите кнопку **Обновить** , чтобы обновить список и просмотреть внешние контакты, которые были импортированы. 
    
    Импортированные контакты будут отображаться в общей адресной книге Outlook и Outlook в Интернете.
    
    > [!NOTE]
    > Вы также можете просмотреть контакты в центре администрирования Microsoft 365, перейдя к **списку контактов** **пользователей** \> . 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a>Шаг 3: Добавление сведений в свойства внешних контактов

После выполнения команды, описанной в шаге 2, создаются внешние контакты, но они не содержат сведений о контакте или организации, которые представляют собой сведения из большинства ячеек в CSV-файле. Это связано с тем, что при создании новых внешних контактов заполняются только обязательные свойства. Не беспокойтесь, если у вас нет всех данных в CSV-файле. Если это не так, он не будет добавлен.
  
1.  Подключите PowerShell к организации Exchange Online. Пошаговые инструкции приведены [в статье подключение к Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. Перейдите в папку рабочего стола, в которой вы сохранили CSV-файл на этапе 1; Пример: `C:\Users\Administrator\desktop`.
    
3. Выполните две следующие команды, чтобы добавить другие свойства из CSV-файла во внешние контакты, созданные в шаге 2.
    
    ```powershell
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```powershell
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > Параметр _Manager_ может вызывать проблемы. Если ячейка в CSV-файле пуста, возникнет ошибка, и в него не будет добавлено никакой информации о свойстве. Если вам не нужно указывать руководителя, просто удалите ` -Manager $_.Manager ` его из предыдущей команды PowerShell. 
  
    Опять же, может потребоваться время на обновление контактов, в зависимости от количества, импортированного в шаге 1. 
    
4. Чтобы убедиться в том, что свойства добавлены в контакты: 
    
1. В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**.
    
2. Щелкните контакт, а затем щелкните **изменить** ![значок](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) редактирования, чтобы отобразить свойства контакта. 
    
Вот и все! Пользователи могут просматривать контакты и дополнительные сведения в адресной книге Outlook и Outlook в Интернете.
  
## <a name="add-more-external-contacts"></a>Добавление дополнительных внешних контактов

Вы можете повторить шаги 1 – 3, чтобы добавить новые внешние контакты в Exchange Online. Вы или пользователи вашей компании могут просто добавить новую строку в CSV-файл для нового контакта. Затем вы можете выполнить команды PowerShell из шага 2 и 3, чтобы создать и добавить сведения в новые контакты.
  
> [!NOTE]
> При выполнении команды для создания новых контактов может возникать ошибка, сообщающая, что созданные ранее контакты уже существуют. Все новые контакты, добавленные в CSV-файл, создаются. 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a>Скрытие внешних контактов из общей адресной книги>

Некоторые компании могут использовать только внешние контакты, чтобы их можно было добавить в качестве членов групп рассылки. В этом сценарии может потребоваться скрыть внешние контакты из общей адресной книги. Вот как это сделать:
  
1.  Подключите PowerShell к организации Exchange Online. Пошаговые инструкции приведены [в статье подключение к Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. Чтобы скрыть один внешний контакт, выполните следующую команду.
    
    ```powershell
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```

    Например, чтобы скрыть Pilar Pinilla из общей адресной книги, выполните следующую команду:

    ```powershell
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```

3. Чтобы скрыть все внешние контакты из общей адресной книги, выполните следующую команду:

    ```powershell
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

После их скрытия внешние контакты не будут отображаться в общей адресной книге, но их можно добавить в качестве членов группы рассылки.
