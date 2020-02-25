---
title: Создание записей DNS для Office 365 на сайте Hostgator
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5f0c840e-4140-4571-88ed-cf235ff142d6
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу Hostgator для Office 365.
ms.openlocfilehash: cb0b26081e5946ed2558d090c976847197ed7eb8
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42249144"
---
# <a name="create-dns-records-at-hostgator-for-office-365"></a>Создание записей DNS для Office 365 на сайте Hostgator

 **[Вопросы и ответы по доменам](../setup/domains-faq.md)**. 
  
Если ваш поставщик услуг размещения DNS  Hostgator, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.
  
> [!IMPORTANT]
> Прежде чем добавлять DNS-записи с помощью любой из других процедур, описанных в этой статье, необходимо выполнить первую процедуребелов, [указать домен в учетной записи для хранения](#point-your-domain-to-your-hosting-account). 

Когда вы внесете эти изменения на сайте Hostgator, ваш домен будет настроен для работы со службами Office 365.
  
Дополнительные сведения о веб-хостинге и DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
> Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="point-your-domain-to-your-hosting-account"></a>Настройка домена таким образом, чтобы он указывал на учетную запись размещения
<a name="BKMK_PointDomain"> </a>

> [!IMPORTANT]
> Эту процедуру необходимо выполнить раньше других процедур, описанных в данной статье. 
  
Чтобы связать свой домен с учетными записями размещения, сделайте следующее.
  
1. Прежде всего откройте страницу управления доменами на сайте Hostgator, воспользовавшись [этой ссылкой](https://portal.hostgator.com/). Вам потребуется выполнить вход.
    
2. Выберите **домены** слева.
  
3. На странице " **Управление доменами** " выберите домен, который вы хотите обновить. 
  
4. В раскрывающемся меню слева выберите пункт **серверы имен**.
  
5. На странице **серверы имен** для вашего домена в раскрывающемся списке **автоматически указать этот домен учетной записи размещения** выберите учетную запись размещения, связанную с доменом. 
  
6. Выберите команду **сохранить серверы имен**.
    
  
## <a name="add-a-txt-record-for-verification"></a>Добавление записи TXT для проверки
<a name="BKMK_verify"> </a>

> [!IMPORTANT]
> Перед этой процедурой необходимо выполнить процедуру [Настройка домена таким образом, чтобы он указывал на учетную запись размещения](#point-your-domain-to-your-hosting-account), описанную в первом разделе. 
  
Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете данным доменом.
  
> [!NOTE]
> Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже. 
  
1. To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. Сообщение о регистрации, полученное из Hostgator, будет указывать этот адрес, а ссылка cPanel также доступна на странице **Размещение** .)
    
    > [!IMPORTANT]
    > Чтобы с вашим доменом была связана страница cPanel, вам нужно получить учетную запись размещения от Hostgator. Для начала работы с Office 365 вы можете купить учетную запись размещения у Hostgator или [изменить записи серверов имен таким образом, чтобы они указывали на Office 365](change-nameservers-at-hostgator.md). 
  
2. На странице " **Панель управления** " в разделе **домены** выберите **Расширенный редактор зон**.
    
3. На странице " **Расширенная настройка редактора зоны** " в поля для новой записи в области **Добавление записи** введите (или скопируйте и вставьте) значения из таблицы ниже. 
    
    В раскрывающемся списке выберите значение параметра **Type** (Тип). 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Name (Имя)** <br/> |**TTL (Срок жизни)** <br/> |**Type (Тип)** <br/> |**TXT Data (Данные TXT)** <br/> |
    |Используйте *domain_name*. (for example, fourthcoffee.com.)  <br/> **This value MUST end with a period (.)** <br/> |1,1  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Примечание:** Это пример. Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365. [Как найти это значение?](../get-help-with-domains/information-for-dns-records.md)          |
   
4. Выберите команду **Add Record** (Добавить запись).
    
5. Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. В центре администрирования перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> **параметров** \> ".
    
2. На странице **Domains (домены** ) выберите домен, который вы хотите проверить. 
    
3. На странице **Настройка** выберите пункт **Запуск программы установки**.
    
4. На странице **Проверка домена** нажмите кнопку **проверить**.
    
> [!NOTE]
> Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365
<a name="BKMK_add_MX"> </a>

> [!IMPORTANT]
> Перед этой процедурой необходимо выполнить процедуру [Настройка домена таким образом, чтобы он указывал на учетную запись размещения](#point-your-domain-to-your-hosting-account), описанную в первом разделе. 
  
1. Чтобы приступить к работе, перейдите на свою страницу cPanel на сайте Hostgator. Сначала вам потребуется выполнить вход.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. Сообщение о регистрации, полученное из Hostgator, будет указывать этот адрес, а ссылка cPanel также доступна на странице **Размещение** .)
    
    > [!IMPORTANT]
    > Чтобы с вашим доменом была связана страница cPanel, вам нужно получить учетную запись размещения от Hostgator. Для начала работы с Office 365 вы можете купить учетную запись размещения у Hostgator или [изменить записи серверов имен таким образом, чтобы они указывали на Office 365](change-nameservers-at-hostgator.md). 
  
2. На странице " **Панель управления** " в области **Электронная почта** выберите **запись MX**.
    
 
3. В области **Email Routing** (Маршрутизация электронной почты) выберите параметр **Remote Mail Exchanger** (Удаленный почтовый обменник).

4. Нажмите кнопку **изменить**.
  
5. В поля для новой записи в области **Добавление новой записи** введите (или скопируйте и вставьте) значения из таблицы ниже. 
    
    |**Priority (Приоритет)**|**Destination (Назначение)**|
    |:-----|:-----|
    |нуль  <br/> Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).    <br/> | *\<ключ_домена\>*  .mail.protection.outlook.com  <br/> **Примечание:** \< Получите *ключ* \> домена из учетной записи Office 365.    [Как найти это значение?](../get-help-with-domains/information-for-dns-records.md)          |
  
6. Нажмите кнопку **Добавить новую запись**.
   
 
7. Если в разделе **MX Records** (Записи MX) есть другие записи MX, удалите их. 

    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Добавление шести записей CNAME, необходимых для Office 365
<a name="BKMK_add_CNAME"> </a>

> [!IMPORTANT]
> Перед этой процедурой необходимо выполнить процедуру [Настройка домена таким образом, чтобы он указывал на учетную запись размещения](#point-your-domain-to-your-hosting-account), описанную в первом разделе. 
  
1. Чтобы приступить к работе, перейдите на свою страницу cPanel на сайте Hostgator. Сначала вам потребуется выполнить вход.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. Сообщение о регистрации, полученное из Hostgator, будет указывать этот адрес, а ссылка cPanel также доступна на странице **Размещение** .)
    
    > [!IMPORTANT]
    > Чтобы с вашим доменом была связана страница cPanel, вам нужно получить учетную запись размещения от Hostgator. Для начала работы с Office 365 вы можете купить учетную запись размещения у Hostgator или [изменить записи серверов имен таким образом, чтобы они указывали на Office 365](change-nameservers-at-hostgator.md). 
  
2. На странице " **Панель управления** " в разделе **домены** выберите **Расширенный редактор зон**.
    
3. Добавьте первую из шести записей CNAME.
    
    На странице **расширенного редактора зоны** в поля для **новой записи введите** (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы, а затем введите (или скопируйте и вставьте) значения из первой строки. 
    
    В раскрывающемся списке выберите значение параметра **Type** (Тип). 
    
    |**Name (Имя)**|**TTL (Срок жизни)**|**Type (Тип)**|**CNAME**|
    |:-----|:-----|:-----|:-----|
    |autodiscover. *domain_name*. (Например: autodiscover.fourthcoffee.com.)  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |3600  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip. *domain_name*. (Например: sip.fourthcoffee.com.)  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |3600  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover. *domain_name*. (Например: lyncdiscover.fourthcoffee.com.)  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |3600  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration. *domain_name*. (Например: enterpriseregistration.fourthcoffee.com.)  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |3600  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment. *domain_name*. (Например: enterpriseregistration.fourthcoffee.com.)  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |3600  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |

  
4. Выберите команду **Add Record** (Добавить запись).

5. Добавьте остальные пять записей CNAME.
    
    В разделе **Добавление записи** создайте запись, используя значения из следующей строки таблицы, а затем еще раз выберите **Добавить запись** для завершения этой записи. 
    
    Повторяйте эти действия, пока не будут созданы все шесть записей CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values. Need examples? Ознакомьтесь с этими [сведениями и образцами записей SPF](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords). Проверить запись SPF можно с помощью одного из этих [специальных средств](../setup/domains-faq.md). 
  
> [!IMPORTANT]
> Перед этой процедурой необходимо выполнить процедуру [Настройка домена таким образом, чтобы он указывал на учетную запись размещения](#point-your-domain-to-your-hosting-account), описанную в первом разделе. 
  
1. Чтобы приступить к работе, перейдите на свою страницу cPanel на сайте Hostgator. Сначала вам потребуется выполнить вход.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. Сообщение о регистрации, полученное из Hostgator, будет указывать этот адрес, а ссылка cPanel также доступна на странице **Размещение** .)
    
    > [!IMPORTANT]
    > Чтобы с вашим доменом была связана страница cPanel, вам нужно получить учетную запись размещения от Hostgator. Для начала работы с Office 365 вы можете купить учетную запись размещения у Hostgator или [изменить записи серверов имен таким образом, чтобы они указывали на Office 365](change-nameservers-at-hostgator.md). 
  
2. На странице " **Панель управления** " в разделе **домены** выберите **Расширенный редактор зон**.
    
3. On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    В раскрывающемся списке выберите значение параметра **Type** (Тип). 
    
    |**Name (Имя)**|**TTL (Срок жизни)**|**Type (Тип)**|**TXT Data (Данные TXT)**|
    |:-----|:-----|:-----|:-----|
    |Используйте *domain_name*. (for example, fourthcoffee.com.)  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |3600  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.               |
  
4. Выберите команду **Add Record** (Добавить запись).
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Добавление двух записей SRV, необходимых для Office 365
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Перед этой процедурой необходимо выполнить процедуру [Настройка домена таким образом, чтобы он указывал на учетную запись размещения](#point-your-domain-to-your-hosting-account), описанную в первом разделе. 
  
1. Чтобы приступить к работе, перейдите на свою страницу cPanel на сайте Hostgator. Сначала вам потребуется выполнить вход.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. Сообщение о регистрации, полученное из Hostgator, будет указывать этот адрес, а ссылка cPanel также доступна на странице **Размещение** .)
    
    > [!IMPORTANT]
    > Чтобы с вашим доменом была связана страница cPanel, вам нужно получить учетную запись размещения от Hostgator. Для начала работы с Office 365 вы можете купить учетную запись размещения у Hostgator или [изменить записи серверов имен таким образом, чтобы они указывали на Office 365](change-nameservers-at-hostgator.md). 
  
2. На странице " **Панель управления** " в разделе **домены** выберите **Расширенный редактор зон**.

    
3. Добавьте первую из двух записей SRV.
    
    На странице **Advanced DNS Zone Editor** (Расширенный редактор зон DNS) в поля для новой записи в области **Add a Record** (Добавление записи) введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы. 
    
    В раскрывающемся списке выберите значение параметра **Type** (Тип). 
    
    |**Name (Имя)**|**TTL (Срок жизни)**|**Type (Тип)**|**Priority (Приоритет)**|**Weight (Вес)**|**Port (Порт)**|**Target (Назначение)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip. _tls. *domain_name*. (например, _sip. _tls. fourthcoffee. com).  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1,1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls. _tcp. *domain_name*. (например, _sipfederationtls. _tcp. fourthcoffee. com).  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1,1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   

4. Выберите команду **Add Record** (Добавить запись).

  
5. Добавьте вторую запись SRV.
    
    В разделе **Добавление записи** создайте запись, используя значения из следующей строки таблицы, а затем еще раз выберите **Добавить запись** для завершения этой записи. 
    
> [!NOTE]
> Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md). 
