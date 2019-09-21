---
title: Вопросы и ответы об импорте PST-файлов в Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 2fe71b05-f5a2-4182-ade7-4dc5cabdfd51
description: 'Часто задаваемые вопросы для администраторов об использовании службы импорта Office 365 для импорта PST-файлов организаитон в почтовые ящики Office 365. '
ms.openlocfilehash: 632b82a99f1be5d38db3fb50a4b2b4d7a6369186
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090233"
---
# <a name="faq-about-importing-pst-files-to-office-365"></a>Вопросы и ответы об импорте PST-файлов в Office 365

**Эта статья предназначена для администраторов. Вы хотите импортировать PST-файлы в свой почтовый ящик? [В разделе Импорт электронной почты, контактов и календаря из PST-файла Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|
   
Ниже приведены часто задаваемые вопросы об использовании службы импорта Office 365 для массового импорта PST-файлов в почтовые ящики Office 365. Для получения дополнительных сведений об импорте PST-файлов ознакомьтесь [со статьей Обзор импорта PST-файлов в Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84).
  
## <a name="using-network-upload-to-import-pst-files"></a>Использование отправки по сети для импорта PST-файлов

Пошаговые инструкции приведены [в разделе Использование отправки по сети для импорта PST-файлов в Office 365](use-network-upload-to-import-pst-files.md).
  
 **Какие разрешения необходимы для создания заданий импорта в службе импорта Office 365?**
  
Необходимо назначить роль экспорта для импорта почтовых ящиков в Exchange Online, чтобы импортировать PST-файлы в почтовые ящики Office 365. По умолчанию эта роль не назначается ни одной группе ролей в Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. Дополнительные сведения можно найти в разделах "Добавление роли в группу ролей" или "Создание группы ролей" в разделе [Управление группами ролей в Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Кроме того, для создания заданий импорта в центре безопасности & соответствия требованиям необходимо выполнить одно из следующих условий:
  
- Вы должны быть назначены роли получателей почты в Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    или
    
- Вам необходимо быть глобальным администратором в организации Office 365.
    
> [!TIP]
> Рассмотрите возможность создания новой группы ролей в Exchange Online, специально предназначенной для импорта PST-файлов в Office 365. Для доступа к минимальному уровню привилегий, необходимых для импорта PST-файлов, назначьте роли "Импорт импорта почтового ящика" и "Получатели почты" новой группе ролей, а затем добавьте участников. 
  
 **Где доступна отправка по сети?**
  
В настоящее время доступна сетевая отправка в США, Канаде, Бразилии, Великобритании, Франции, Европе, Индии, Восточной Азии, Юго-Восточной Азии, Японии, Республика Корея и Австралии. Network upload will be available in more regions soon.
  
 **What is the pricing for importing PST files by using network upload?**
  
Using network upload to import PST files is free.
  
Это также означает, что после удаления PST-файлов из области хранилища Azure они больше не отображаются в списке файлов для завершенного задания импорта в центре администрирования Microsoft 365. Несмотря на то, что задание импорта по-прежнему может отображаться на странице **Импорт данных в Office 365** , список PST-файлов может быть пустым при просмотре сведений о старых заданиях импорта. 
  
 **What version of the PST file format is supported for importing to Office 365?**
  
There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. Тем не менее файлы, в которых используется формат PST-файлов в формате ANSI (например, для языков, использующих двухбайтовую кодировку (DBCS)), также можно импортировать в Office 365. Для получения дополнительных сведений об импорте PST-файлов в формате ANSI, выполните шаг 4 в разделе [Использование отправки по сети для импорта PST-файлов Организации в Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file).
  
Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.
  
 **Когда я отправил PST-файлы в область хранилища Azure, как долго они хранятся в Azure, прежде чем они будут удалены?**
  
При импорте PST-файлов с помощью метода отправки в сети вы отправляете их в контейнер BLOB-объектов Azure с именем **ingestiondata**. Если на странице **Импорт** в центре безопасности & соответствия требованиям нет заданий импорта, все PST-файлы в контейнере **ingestiondata** в Azure удаляются через 30 дней после создания последнего задания импорта в & безопасности Центр соответствия требованиям. Это также означает, что необходимо создать новое задание импорта в центре безопасности & соответствия требованиям (описанном в шаге 5 в инструкциях по отправке в сети) в течение 30 дней с момента отправки PST-файлов в Azure. 
  
Это также означает, что после удаления PST-файлов из области хранилища Azure они больше не отображаются в списке файлов для завершенного задания импорта в центре безопасности & соответствия требованиям. Несмотря на то, что задание импорта по-прежнему может отображаться на странице **Импорт** в центре безопасности & соответствия требованиям, список PST-файлов может быть пустым при просмотре сведений о старых заданиях импорта. 
  
 **Сколько времени требуется для импорта PST-файла в почтовый ящик?**
  
It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure storage area for your organization. После того как PST-файлы будут скопированы в область хранилища Azure, PST-файл будет импортирован в почтовый ящик Office 365 по крайней мере 24 ГБ в день. Если это значение не соответствует вашим потребностям, вы можете рассмотреть другие способы переноса данных электронной почты в Office 365. Дополнительные сведения см. [в статье способы переноса нескольких учетных записей электронной почты в Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Аналогично, если несколько PST-файлов импортируются в один почтовый ящик, они будут импортированы одновременно.
  
 **Is there a message size limit when importing PST files?**
  
Да. Если PST-файл содержит элемент почтового ящика размером более 150 МБ, он будет пропущен во время процесса импорта.
  
 **— Это свойства сообщений, например, когда сообщение было отправлено или получено, список получателей и другие свойства сохраняются при импорте PST-файлов в почтовый ящик Office 365.**
  
Да. Исходные метаданные сообщения не изменяются во время процесса импорта.
  
 **Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**
  
Yes. You can't import a PST file that has 300 or more levels of nested folders.
  
 **Can I use network upload to import PST files to an inactive mailbox in Office 365?**
  
Yes, this capability is now available. 
  
 **Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**
  
Yes, this capability is now available. 
  
 **Можно ли использовать отправку по сети для импорта PST-файлов в общедоступные папки в Exchange Online?**
  
Нет, вы не можете импортировать PST-файлы в общедоступные папки.
  
## <a name="using-drive-shipping-to-import-pst-files"></a>Использование доставки дисков для импорта PST-файлов

Пошаговые инструкции приведены [в разделе Использование доставки дисков для импорта PST-файлов в Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md).
  
 **Какие разрешения необходимы для создания заданий импорта в службе импорта Office 365?**
  
Необходимо назначить роль экспорта для импорта почтового ящика для импорта PST-файлов в почтовые ящики Office 365. По умолчанию эта роль не назначается ни одной группе ролей в Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. Дополнительные сведения можно найти в разделах "Добавление роли в группу ролей" или "Создание группы ролей" в разделе [Управление группами ролей в Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Кроме того, для создания заданий импорта в центре безопасности & соответствия требованиям необходимо выполнить одно из следующих условий:
  
- Вы должны быть назначены роли получателей почты в Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    или
    
- Вам необходимо быть глобальным администратором в организации Office 365.
    
> [!TIP]
> Рассмотрите возможность создания новой группы ролей в Exchange Online, специально предназначенной для импорта PST-файлов в Office 365. Для доступа к минимальному уровню привилегий, необходимых для импорта PST-файлов, назначьте роли "Импорт импорта почтового ящика" и "Получатели почты" новой группе ролей, а затем добавьте участников. 
  
 **Где доступна доставка накопителей?**
  
В настоящее время доставка дисков доступна в США, Канаде, Бразилии, Великобритании, Европе, Индии, Восточной Азии, Юго-Восточной Азии, Японии, Республика Корея и Австралии. Drive shipping will be available in more regions soon.
  
 **What commercial licensing agreements support drive shipping?**
  
Доставка дисков для импорта PST-файлов в Office 365 доступна через соглашение Майкрософт Enterprise Agreement (EA). Доставка дисков недоступна через соглашение о продуктах и службах Майкрософт (МПСА).
  
 **Каковы цены на использование доставки дисков для импорта PST-файлов в Office 365?**
  
The cost to use drive shipping to import PST files to Office 365 mailboxes is $2 USD per GB of data. For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD. You can work with a partner to pay the import fee. Сведения о том, как найти партнера, можно [найти в статье Find Your партнер или торговый посредник Office 365](https://go.microsoft.com/fwlink/p/?LinkId=785197).
  
 **What kind of hard drives are supported for drive shipping?**
  
Для службы импорта Office 365 поддерживаются только диски с твердотельными накопителями 2,5 дюймов (SSDs) или 2,5 или 3,5 дюймов для жестких дисков SATA II/III. You can use hard drives up to 10 TB. Для заданий импорта будет обработано только первый том данных на жестком диске. The data volume must be formatted with NTFS. При копировании данных на жесткий диск вы можете присоединить его непосредственно с помощью соединителя SATA II 2,5 или 2,5 или 3,5 дюйма или с 2,5 помощью разъема SATA II/III или с внешним подключением с помощью USB-адаптера SATA II/III или 2,5 с SATA II/III.
  
> [!IMPORTANT]
> Внешние жесткие диски, которые поставляются со встроенным USB-адаптером, не поддерживаются службой импорта Office 365. Additionally, the disk inside the casing of an external hard drive can't be used. Please don't ship external hard drives. 
  
 **How many hard drives can I ship for a single import job?**
  
You can ship a maximum of 10 hard drives for a single import job.
  
 **After I ship my hard drive, how long does it take to get to the Microsoft data center?**
  
That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.
  
 **Когда мой жесткий диск поступает в центр обработки данных Майкрософт, сколько времени займет отправка личных PST-файлов в Azure?**
  
После получения жесткого диска в центре обработки данных Майкрософт для отправки PST-файлов в область хранилища Microsoft Azure для Организации потребуется от 7 до 10 рабочих дней. PST-файлы будут отправлены в контейнер BLOB-объектов Azure с именем **ingestiondata**. 
  
 **Сколько времени требуется для импорта PST-файла в почтовый ящик?**
  
После того как PST-файлы будут отправлены в область хранилища Azure, Office 365 анализирует данные в PST-файлах (безопасным и безопасным способом), чтобы определить возраст элементов и типы сообщений, включенные в PST-файлы. После завершения анализа можно будет импортировать все данные в PST-файлы или установить фильтры для этого элемента управления, какие данные будут импортированы. После запуска задания импорта PST-файл импортируется в почтовый ящик Office 365 с частотой не менее 24 ГБ в день. Если это значение не соответствует вашим потребностям, вы можете рассмотреть другие методы импорта данных электронной почты в Office 365. Дополнительные сведения см. [в статье способы переноса нескольких учетных записей электронной почты в Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Аналогично, если несколько PST-файлов импортируются в один почтовый ящик, они будут импортированы одновременно.
  
 **Когда корпорация Майкрософт отправляет PST-файлы в Azure, как долго они хранятся в Azure, прежде чем они будут удалены?**
  
Все PST-файлы в расположении хранилища Azure для организации (в контейнере BLOB-объектов с именем **ingestiondata** ) удаляются через 30 дней после создания последнего задания импорта на странице " **Импорт** " центра безопасности & соответствия требованиям. 
  
Это также означает, что после удаления PST-файлов из области хранилища Azure они больше не отображаются в списке файлов для завершенного задания импорта в центре безопасности & соответствия требованиям. Несмотря на то, что задание импорта по-прежнему может отображаться на странице **Импорт** в центре безопасности & соответствия требованиям, список PST-файлов может быть пустым при просмотре сведений о старых заданиях импорта. 
  
 **What version of the PST file format is supported for importing to Office 365?**
  
There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. Тем не менее файлы, в которых используется формат PST-файлов в формате ANSI (например, для языков, использующих двухбайтовую кодировку (DBCS)), также можно импортировать в Office 365. Дополнительные сведения об импорте PST-файлов в формате ANSI приведены в разделе Шаг 3 в разделе [Использование доставки дисков для импорта PST-файлов в Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).
  
Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.
  
 **Is there a message size limit when importing PST files?**
  
Да. Если PST-файл содержит элемент почтового ящика размером более 150 МБ, он будет пропущен во время процесса импорта.
  
 **— Это свойства сообщений, например, когда сообщение было отправлено или получено, список получателей и другие свойства сохраняются при импорте PST-файлов в почтовый ящик Office 365.**
  
Да. Исходные метаданные сообщения не изменяются во время процесса импорта
  
 **Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**
  
Yes. You can't import a PST file that has 300 or more levels of nested folders.
  
 **Can I use drive shipping to import PST files to an inactive mailbox in Office 365?**
  
Yes, this capability is now available.
  
 **Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**
  
Yes, this capability is now available. 
  
 **Можно ли использовать доставку дисков для импорта PST-файлов в общедоступные папки в Exchange Online?**
  
Нет, вы не можете импортировать PST-файлы в общедоступные папки.
  
 **Can Microsoft wipe my hard drive before they ship it back to me?**
  
No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.
  
 **Можно ли Майкрософт разложить жесткий диск вместо того, чтобы отгрузить его?**
  
No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.
  
 **Какие службы курьеров поддерживаются для отгрузки возврата?**
  
If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.
  
 **Каковы затраты на поставку возврата?**
  
Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.
  
 **Можно ли использовать пользовательскую службу доставки курьеров, например Федекс настраиваемую отгрузку, для доставки жесткого диска в корпорацию Майкрософт?**
  
Да.
  
 **If I have to ship my hard drive to another country, is there anything I need to do?**
  
The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.
