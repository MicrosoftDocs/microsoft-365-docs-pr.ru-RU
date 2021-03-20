---
title: Создание записей DNS в 123-reg.co.uk microsoft
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб в 123-reg.co.uk Microsoft.
ms.openlocfilehash: d1e4d3d01a5e6b4f72c98fe09cf57374dd2417a0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910430"
---
# <a name="create-dns-records-at-123-regcouk-for-microsoft"></a>Создание записей DNS в 123-reg.co.uk microsoft

 **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**. 
  
Если ваш поставщик услуг размещения DNS  123-reg.co.uk, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.
  
После добавления этих записей в 123-reg.co.uk домен будет настроен для работы с службами Майкрософт.
  
  
> [!NOTE]
> Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Добавление записи TXT для проверки
<a name="BKMK_verify"> </a>

Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.
  
> [!NOTE]
> Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже. 
  
1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте 123-reg.co.uk по [этой ссылке](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Сначала вам потребуется выполнить вход.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. На странице **Управление DNS** выберите вкладку **Advanced DNS.** 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    ||||
    |:-----|:-----|:-----|
    |**Hostname (Имя узла)** <br/> |**Type (Тип)** <br/> |**Destination TXT/SPF** <br/> |
    |@  <br/> |TXT/SPF  <br/> |MS=ms *XXXXXXXX*  <br/> **Примечание.** Это пример. Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы. [Как его найти?](../get-help-with-domains/information-for-dns-records.md)          |
   
6. Нажмите кнопку **Add** (Добавить).
    
7. Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.
    
Теперь, когда вы добавили запись на сайте регистратора домена, вы снова обратились в Корпорацию Майкрософт и запросили поиск записи.
  
Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.
  
1. В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.

    
2. На странице **Domains** (Домены) выберите домен, который нужно проверить. 
    
3. На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).
    
4. На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).
    
> [!NOTE]
> Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.
<a name="BKMK_add_MX"> </a>

1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте 123-reg.co.uk по [этой ссылке](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Сначала вам потребуется выполнить вход.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. На странице **Управление DNS** выберите вкладку **Advanced DNS.** 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Hostname (Имя узла)**|**Type (Тип)**|**Priority (Приоритет)**|**Destination MX (Запись MX назначения)**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1  <br/> Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](../setup/domains-faq.yml).    <br/> | *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> **Примечание.**  Получите свой \<domain-key\> из учетной записи Майкрософт. [Как его найти?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Копирование и вклейка значений из таблицы](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. Нажмите **Добавить**.
    
    ![Снимок экрана диалоговое окно с выбранной кнопкой Добавить](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. Если есть какие-либо другие записи MX, удалите каждую из них, щелкнув соответствующий значок с изображением **корзины**. 
    
    ![Выберите Delete (значок корзины)](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>Добавление пяти записей CNAME, необходимых для продуктов корпорации Майкрософт
<a name="BKMK_add_CNAME"> </a>

1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте 123-reg.co.uk по [этой ссылке](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Сначала вам потребуется выполнить вход.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. На странице **Управление DNS** выберите вкладку **Advanced DNS.** 
    
5. Добавьте первую из пяти записей CNAME.
    
    In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Hostname (Имя узла)**|**Type (Тип)**|**Destination CNAME (Запись CNAME назначения)**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |
   
    ![Снимок экрана с помощью CNAME назначения для копирования и вклейки](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. Нажмите **Добавить**.
    
    ![Снимок экрана для добавления CNAME назначения](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. Добавьте остальные четыре записи CNAME.
    
    В разделе **Расширенный DNS** создайте запись с помощью значений из следующей строки в таблице и снова выберите **Добавить** для завершения этой записи. 
    
    Повторите этот процесс, пока не создайте все пять записей CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Добавление записи TXT для SPF, предотвращающей рассылку спама
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT. Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама. Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт. Вместо этого добавьте необходимые значения Microsoft в текущую  запись, чтобы у вас была одна запись SPF, которая включает оба набора значений. Нужны примеры? Ознакомьтесь с этими [записями системы внешних доменных имен для продуктов корпорации Майкрософт](../../enterprise/external-domain-name-system-records.md#external-dns-records-required-for-spf). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml). 
  
1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте 123-reg.co.uk по [этой ссылке](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Сначала вам потребуется выполнить вход.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. На странице **Управление DNS** выберите вкладку **Advanced DNS.** 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Hostname (Имя узла)**|**Type (Тип)**|**Destination TXT/SPF**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT/SPF  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.               |
   
    ![123Reg-BP-Configure-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. Нажмите **Добавить**.
    
    ![Снимок экрана с помощью destination TXT/SPF](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт
<a name="BKMK_add_SRV"> </a>

1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте 123-reg.co.uk по [этой ссылке](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Сначала вам потребуется выполнить вход.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. На странице **Управление DNS** выберите вкладку **Advanced DNS.** 
    
5. Добавьте первую из двух записей SRV.
    
    In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |Hostname (Имя узла)|Type (Тип)|Priority (Приоритет)|TTL (Срок жизни)|Destination SRV (Запись SRV назначения)|
    |_sip._tls|SRV|100|3600|1 443 sipdir.online.lync.com. **Это значение ДОЛЖНО оканчиваться точкой (.).**<br> **Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.               |
    |_sipfederationtls._tcp|SRV|100|3600|1 5061 sipfed.online.lync.com. **Это значение ДОЛЖНО оканчиваться точкой (.).** <br> **Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.               |
   
    ![Снимок экрана со значениями DNS из таблицы](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. Нажмите **Добавить**.
    
    ![Снимок экрана для добавления SRV назначения](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. Добавьте вторую запись SRV.
    
    В разделе **Расширенный DNS** создайте запись с помощью значений из второй строки в таблице и снова выберите **Добавить** для завершения этой записи. 
    
> [!NOTE]
> Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
