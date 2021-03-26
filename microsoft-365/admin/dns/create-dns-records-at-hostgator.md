---
title: Создание записей DNS в Hostgator для Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5f0c840e-4140-4571-88ed-cf235ff142d6
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб в Hostgator для Microsoft.
ms.openlocfilehash: 7f12b407254ff4146f77090da07d98db63e47305
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2021
ms.locfileid: "51221887"
---
# <a name="create-dns-records-at-hostgator-for-microsoft"></a>Создание записей DNS в Hostgator для Microsoft

 **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**. 
  
Если ваш поставщик услуг размещения DNS  Hostgator, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.
  
> [!IMPORTANT]
> Прежде чем добавлять записи DNS с помощью других процедур в этой [статье,](#point-your-domain-to-your-hosting-account)необходимо выполнить первую процедуру, указать домен на учетную запись хостинга. 

После внесения всех этих изменений в Hostgator домен будет настроен на работу с службами Майкрософт.
  

  
> [!NOTE]
> Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="point-your-domain-to-your-hosting-account"></a>Настройка домена таким образом, чтобы он указывал на учетную запись размещения
<a name="BKMK_PointDomain"> </a>

> [!IMPORTANT]
> Эту процедуру необходимо выполнить раньше других процедур, описанных в данной статье. 
  
Чтобы связать свой домен с учетными записями размещения, сделайте следующее.
  
1. Прежде всего откройте страницу управления доменами на сайте Hostgator, воспользовавшись [этой ссылкой](https://portal.hostgator.com/). Вам потребуется выполнить вход.
    
2. Выберите **домены** слева.
  
3. На странице **Управление доменами** выберите домен, который необходимо обновить. 
  
4. В всплывающее меню слева выберите **Name Servers**.
  
5. На странице **Name Servers** для вашего  домена в домене автоматически указать этот домен на выпадаемом списке учетной записи хостинга выберите учетную запись хостинга, связанную с вашим доменом. 
  
6. Выберите **сохранить серверы имен**.
    
  
## <a name="add-a-txt-record-for-verification"></a>Добавление записи TXT для проверки
<a name="BKMK_verify"> </a>

> [!IMPORTANT]
> Перед этой процедурой необходимо выполнить процедуру [Настройка домена таким образом, чтобы он указывал на учетную запись размещения](#point-your-domain-to-your-hosting-account), описанную в первом разделе. 
  
Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.
  
> [!NOTE]
> Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже. 
  
1. Чтобы приступить к работе, перейдите на свою страницу cPanel на сайте Hostgator. Сначала вам потребуется выполнить вход.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. В электронной почте регистрации, полученной от hostgator, будет указан этот  адрес, а на странице Хостинга также доступна ссылка cPanel.)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Чтобы начать работу с Корпорацией Майкрософт, вы можете приобрести учетную запись хостинга у Hostgator или перенаселить имена, чтобы указать [на Microsoft.](change-nameservers-at-hostgator.md) 
  
2. На странице **Панель управления** в области **Домены** выберите **редактор advanced Zone**.
    
3. На странице **Advanced Zone Editor** в области **Добавление** записи в полях для новой записи введите или скопируйте и введите значения из следующей таблицы. 
    
    В раскрывающемся списке выберите значение параметра **Type** (Тип). 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Имя** <br/> |**TTL (Срок жизни)** <br/> |**Type (Тип)** <br/> |**TXT Data (Данные TXT)** <br/> |
    |Используйте  *domain_name*. (for example, fourthcoffee.com.)  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |1  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Примечание.** Это пример. Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы. [Как его найти?](../get-help-with-domains/information-for-dns-records.md)          |
   
4. Выберите команду **Add Record** (Добавить запись).
    
5. Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.
    
Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.
  
Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.
  
1. В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).
    
2. На странице **Domains** (Домены) выберите домен, который нужно проверить. 
    
3. На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).
    
4. На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).
    
> [!NOTE]
> Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.
<a name="BKMK_add_MX"> </a>

> [!IMPORTANT]
> Перед этой процедурой необходимо выполнить процедуру [Настройка домена таким образом, чтобы он указывал на учетную запись размещения](#point-your-domain-to-your-hosting-account), описанную в первом разделе. 
  
1. Чтобы приступить к работе, перейдите на свою страницу cPanel на сайте Hostgator. Сначала вам потребуется выполнить вход.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. В электронной почте регистрации, полученной от hostgator, будет указан этот  адрес, а на странице Хостинга также доступна ссылка cPanel.)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Чтобы начать работу с Корпорацией Майкрософт, вы можете приобрести учетную запись хостинга у Hostgator или перенаселить имена, чтобы указать [на Microsoft.](change-nameservers-at-hostgator.md) 
  
2. На странице **Панель управления** в области **электронной почты** выберите **запись MX .**
    
 
3. В области **Email Routing** (Маршрутизация электронной почты) выберите параметр **Remote Mail Exchanger** (Удаленный почтовый обменник).

4. Выберите **Изменить**.
  
5. В области **Добавить новую** запись в полях для новой записи введите или скопируйте и введите значения из следующей таблицы. 
    
    |**Priority (Приоритет)**|**Destination (Назначение)**|
    |:-----|:-----|
    |0  <br/> Дополнительные сведения о приоритете см. в статье [Что такое приоритет записей MX?](../setup/domains-faq.yml). <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Примечание.**  Получите свой \< *domain-key*  \> из учетной записи Майкрософт.  [Как его найти?](../get-help-with-domains/information-for-dns-records.md)          |
  
6. Выберите **Добавить новую запись**.
   
 
7. Если в разделе **MX Records** (Записи MX) есть другие записи MX, удалите их. 

    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Добавление шести записей CNAME, необходимых для Корпорации Майкрософт
<a name="BKMK_add_CNAME"> </a>

> [!IMPORTANT]
> Перед этой процедурой необходимо выполнить процедуру [Настройка домена таким образом, чтобы он указывал на учетную запись размещения](#point-your-domain-to-your-hosting-account), описанную в первом разделе. 
  
1. Чтобы приступить к работе, перейдите на свою страницу cPanel на сайте Hostgator. Сначала вам потребуется выполнить вход.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. В электронной почте регистрации, полученной от hostgator, будет указан этот  адрес, а на странице Хостинга также доступна ссылка cPanel.)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Чтобы начать работу с Корпорацией Майкрософт, вы можете приобрести учетную запись хостинга у Hostgator или перенаселить имена, чтобы указать [на Microsoft.](change-nameservers-at-hostgator.md) 
  
2. На странице **Панель управления** в области **Домены** выберите **редактор advanced Zone**.
    
3. Добавьте первую из шести записей CNAME.
    
    На странице **Advanced Zone Editor** в области **Добавление** записи в полях для новой записи введите или скопируйте и введите значения из первой строки в следующей таблице. 
    
    В раскрывающемся списке выберите значение параметра **Type** (Тип). 
    
    |**Имя**|**TTL (Срок жизни)**|**Type (Тип)**|**CNAME**|
    |:-----|:-----|:-----|:-----|
    |autodiscover. *domain_name*. (Например: autodiscover.fourthcoffee.com.)  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |3600  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip. *domain_name*. (Например: sip.fourthcoffee.com.)  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |3600  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover. *domain_name*. (Например: lyncdiscover.fourthcoffee.com.)  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |3600  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration. *domain_name*. (Например: enterpriseregistration.fourthcoffee.com.)  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |3600  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment. *domain_name*. (Например: enterpriseregistration.fourthcoffee.com.)  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |3600  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |

  
4. Выберите команду **Add Record** (Добавить запись).

5. Добавьте остальные пять записей CNAME.
    
    В разделе **Добавить** запись создайте запись с помощью значений из следующей строки в таблице, а затем снова выберите **Добавить** запись для завершения этой записи. 
    
    Повторяйте эти действия, пока не будут созданы все шесть записей CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Добавление записи TXT для SPF, предотвращающей рассылку спама
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT. Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама. Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт. Вместо этого добавьте необходимые значения для продуктов корпорации Майкрософт в текущую запись. Таким образом, в одной записи SPF будут указаны оба набора значений. Нужны примеры? Ознакомьтесь с этими [записями системы внешних доменных имен для продуктов корпорации Майкрософт](../../enterprise/external-domain-name-system-records.md). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml). 
  
> [!IMPORTANT]
> Перед этой процедурой необходимо выполнить процедуру [Настройка домена таким образом, чтобы он указывал на учетную запись размещения](#point-your-domain-to-your-hosting-account), описанную в первом разделе. 
  
1. Чтобы приступить к работе, перейдите на свою страницу cPanel на сайте Hostgator. Сначала вам потребуется выполнить вход.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. В электронной почте регистрации, полученной от hostgator, будет указан этот  адрес, а на странице Хостинга также доступна ссылка cPanel.)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Чтобы начать работу с Корпорацией Майкрософт, вы можете приобрести учетную запись хостинга у Hostgator или перенаселить имена, чтобы указать [на Microsoft.](change-nameservers-at-hostgator.md) 
  
2. На странице **Панель управления** в области **Домены** выберите **редактор advanced Zone**.
    
3. On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    В раскрывающемся списке выберите значение параметра **Type** (Тип). 
    
    |**Имя**|**TTL (Срок жизни)**|**Type (Тип)**|**TXT Data (Данные TXT)**|
    |:-----|:-----|:-----|:-----|
    |Используйте  *domain_name*. (for example, fourthcoffee.com.)  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |3600  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.               |
  
4. Выберите команду **Add Record** (Добавить запись).
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Перед этой процедурой необходимо выполнить процедуру [Настройка домена таким образом, чтобы он указывал на учетную запись размещения](#point-your-domain-to-your-hosting-account), описанную в первом разделе. 
  
1. Чтобы приступить к работе, перейдите на свою страницу cPanel на сайте Hostgator. Сначала вам потребуется выполнить вход.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. В электронной почте регистрации, полученной от hostgator, будет указан этот  адрес, а на странице Хостинга также доступна ссылка cPanel.)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Чтобы начать работу с Корпорацией Майкрософт, вы можете приобрести учетную запись хостинга у Hostgator или перенаселить имена, чтобы указать [на Microsoft.](change-nameservers-at-hostgator.md) 
  
2. На странице **Панель управления** в области **Домены** выберите **редактор advanced Zone**.

    
3. Добавьте первую из двух записей SRV.
    
    На странице **Advanced DNS Zone Editor** (Расширенный редактор зон DNS) в поля для новой записи в области **Add a Record** (Добавление записи) введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы. 
    
    В раскрывающемся списке выберите значение параметра **Type** (Тип). 
    
    |**Имя**|**TTL (Срок жизни)**|**Type (Тип)**|**Priority** (Приоритет)|**Weight** (Вес)|**Port** (Порт)|**Target (Назначение)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip._tls. *domain_name*. (например, _sip._tls.fourthcoffee.com.)  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls._tcp. *domain_name*. (например, _sipfederationtls._tcp.fourthcoffee.com.)  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   

4. Выберите команду **Add Record** (Добавить запись).

  
5. Добавьте вторую запись SRV.
    
    В разделе **Добавить** запись создайте запись с помощью значений из следующей строки в таблице, а затем снова выберите **Добавить** запись для завершения этой записи. 
    
> [!NOTE]
> Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).