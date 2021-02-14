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
# <a name="bulk-import-external-contacts-to-exchange-online"></a>Массовый импорт внешних контактов в Exchange Online

**Эта статья для администраторов. Вы пытаетесь импортировать контакты в свой почтовый ящик? См. ["Импорт контактов в Outlook"](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**
   
У вашей компании много существующих бизнес-контактов, которые вы хотите включить в общую адресную книгу (также называемую глобальным списком адресов) в Exchange Online? Вы хотите добавить внешние контакты в качестве членов групп рассылки, как это можно сделать с пользователями в вашей компании? В этом случае вы можете использовать Exchange Online PowerShell и CSV-файл (разделенный запятой) для массового импорта внешних контактов в Exchange Online. Это трехшаговая процедура:
  
[Шаг 1. Создайте CSV-файл, содержащий сведения о внешних контактах](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[Шаг 2. Создание внешних контактов с помощью PowerShell](#step-2-create-the-external-contacts-with-powershell) 

[Шаг 3. Добавление сведений в свойства внешних контактов](#step-3-add-information-to-the-properties-of-the-external-contacts)

После выполнения этих действий по импорту контактов можно выполнить следующие дополнительные задачи:
  
- [Добавление дополнительных внешних контактов](#add-more-external-contacts)
  
- [Скрытие внешних контактов из общей адресной книги](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a>Шаг 1. Создайте CSV-файл, содержащий сведения о внешних контактах

Сначала необходимо создать CSV-файл, содержащий сведения о каждом внешнем контакте, который необходимо импортировать в Exchange Online. 
  
1. Скопируйте следующий текст в текстовый файл в Блокноте и сохраните его на рабочем столе в виде CSV-файла с помощью суффикса CSV- имени файла; например, ExternalContacts.csv.
    
    > [!TIP]
    > Если ваш язык содержит специальные символы (например, **г,** **г** и **ö** на шведских языках), сохраните CSV-файл с кодировки UTF-8 или другой кодировки Юникода при сохранения файла в Блокноте. 
  
    ```text
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park
    ```

    В первой строке (строке с заготами) CSV-файла перечислены свойства контактов, которые можно использовать при импорте в Exchange Online. Имя каждого свойства разделено запятой. Каждая строка под строкой header представляет значения свойств для импорта одного внешнего контакта. 
    
    > [!NOTE]
    > Этот текст содержит примеры данных, которые можно удалить. Но не удаляйте и не изменяйте первую строку (загон). Он содержит все свойства внешних контактов. 
  
2. Откройте CSV-файл в Microsoft Excel, чтобы изменить CSV-файл, так как с помощью Excel намного проще редактировать CSV-файл.
    
3. Создайте строку для каждого контакта, который вы хотите импортировать в Exchange Online. Заполнять как можно больше ячеек. Эти сведения будут отображаться в общей адресной книге для каждого контакта. 
    
    > [!IMPORTANT]
    >  Для создания внешнего контакта необходимы следующие свойства (которые являются первыми четырьмя элементами в строке header) и должны быть заполнены в CSV-файле: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**. Команда PowerShell, которую вы запустите в шаге 2, будет использовать значения этих свойств для создания контактов. 

## <a name="step-2-create-the-external-contacts-with-powershell"></a>Шаг 2. Создание внешних контактов с помощью PowerShell

Следующим шагом является использование CSV-файла, созданного на шаге 1, и PowerShell для массового импорта внешних контактов, перечисленных в CSV-файле, в Exchange Online. 
  
1.  Подключите PowerShell к организации Exchange Online. Пошаговые инструкции см. в статье [Подключение к Exchange Online с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554). При подключении к Exchange Online PowerShell обязательно используйте имя пользователя и пароль для учетной записи глобального администратора. 
    
2. После подключения PowerShell к Exchange Online перейдите в папку рабочего стола, в которой вы сохранили CSV-файл на шаге 1; например. `C:\Users\Administrator\desktop`
    
3. Чтобы создать внешние контакты, запустите следующую команду:

    ```powershell
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    Создание новых контактов может занять некоторое время в зависимости от того, сколько вы импортируете. После завершения работы команды PowerShell отображает список новых созданных контактов. 
    
4. Чтобы просмотреть новые внешние контакты, перейдите в Центр администрирования Exchange (EAC), а затем щелкните **"Контакты** \> **получателей".** 
    
    > [!TIP]
    > Инструкции по подключению к Центру администрирования Exchange см. в Центре администрирования [Exchange в Exchange Online.](https://go.microsoft.com/fwlink/p/?LinkId=328197) 
  
5. При необходимости нажмите **кнопку** "Обновить", чтобы обновить список и увидеть импортируемые внешние контакты. 
    
    Импортируемые контакты будут отображаться в общей адресной книге в Outlook и Outlook в Интернете.
    
    > [!NOTE]
    > Вы также можете просматривать контакты в Центре администрирования Microsoft 365, переходить к **контактам** \> **пользователей.** 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a>Шаг 3. Добавление сведений в свойства внешних контактов

После запуска команды на шаге 2 создаются внешние контакты, но они не содержат контактов или сведений организации, которые являются сведениями из большинства ячеек в CSV-файле. Это происходит потому, что при создании новых внешних контактов заполняются только необходимые свойства. Не волнуйтесь, если в CSV-файле не заполнены все сведения. Если его там нет, он не будет добавлен.
  
1.  Подключите PowerShell к организации Exchange Online. Пошаговые инструкции см. в статье [Подключение к Exchange Online с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. Перейдите в папку рабочего стола, в которой вы сохранили CSV-файл на шаге 1; например, `C:\Users\Administrator\desktop` .
    
3. Запустите следующие две команды, чтобы добавить другие свойства из CSV-файла к внешним контактам, созданным на шаге 2.
    
    ```powershell
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```powershell
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > Параметр  _Manager_ может быть проблематичным. Если ячейка в CSV-файле пуста, вы получите сообщение об ошибке, и никакие сведения о свойстве не будут добавлены в контакт. Если вам не нужно указывать руководителя, просто удалите из предыдущей  ` -Manager $_.Manager ` команды PowerShell. 
  
    Повторим, обновление контактов может занять некоторое время в зависимости от того, сколько вы импортировали в шаге 1. 
    
4. Чтобы убедиться, что свойства были добавлены к контактам: 
    
1. В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**.
    
2. Щелкните контакт и нажмите **значок редактирования,** чтобы отобразить ![ свойства ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) контакта. 
    
Вот и все! Пользователи могут видеть контакты и дополнительные сведения в адресной книге Outlook и Outlook в Интернете.
  
## <a name="add-more-external-contacts"></a>Добавление дополнительных внешних контактов

Вы можете повторить шаги с 1 по 3, чтобы добавить новые внешние контакты в Exchange Online. Вы или пользователи в своей компании можете просто добавить новую строку в CSV-файл для нового контакта. Затем можно выполнить команды PowerShell из шагов 2 и 3, чтобы создать и добавить сведения для новых контактов.
  
> [!NOTE]
> При запуске команды для создания новых контактов может возникнуть ошибка с сообщением о том, что контакты, созданные ранее, уже существуют. Но создается любой новый контакт, добавленный в CSV-файл. 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a>Скрытие внешних контактов из общей адресной книги>

Некоторые компании могут использовать только внешние контакты, чтобы их можно было добавить в качестве членов групп рассылки. В этом сценарии может потребоваться скрыть внешние контакты из общей адресной книги. Вот как это сделать:
  
1.  Подключите PowerShell к организации Exchange Online. Пошаговые инструкции см. в статье [Подключение к Exchange Online с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. Чтобы скрыть один внешний контакт, запустите следующую команду.
    
    ```powershell
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```

    Например, чтобы скрыть Pilar Pinilla из общей адресной книги, запустите команду:

    ```powershell
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```

3. Чтобы скрыть все внешние контакты из общей адресной книги, запустите команду:

    ```powershell
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

После того как вы скрываете их, внешние контакты не отображаются в общей адресной книге, но вы по-прежнему можете добавить их в качестве членов группы рассылки.
