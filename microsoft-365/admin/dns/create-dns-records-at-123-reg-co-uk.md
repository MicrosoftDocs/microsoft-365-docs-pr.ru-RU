---
title: Создание записей DNS на сайте 123-reg.co.uk для Майкрософт
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу 123-reg.co.uk для Майкрософт.
ms.openlocfilehash: 0c9a6a144a38398e7664f7f2bb317a96b627b640
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049135"
---
# <a name="create-dns-records-at-123-regcouk-for-microsoft"></a>Создание записей DNS на сайте 123-reg.co.uk для Майкрософт

 **[Вопросы и ответы по доменам](../setup/domains-faq.md)**. 
  
Если ваш поставщик услуг размещения DNS  123-reg.co.uk, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.
  
Когда вы добавите эти записи на сайте 123-reg.co.uk, ваш домен будет настроен для работы со службами Майкрософт.
  
  
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
    
4. На странице " **Управление DNS** " перейдите на вкладку **Advanced DNS (дополнительно** ). 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    ||||
    |:-----|:-----|:-----|
    |**Hostname (Имя узла)** <br/> |**Type (Тип)** <br/> |**Destination TXT/SPF** <br/> |
    |@  <br/> |TXT/SPF  <br/> |MS=ms *XXXXXXXX*  <br/> **Примечание.** Это пример. Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы. [Как его найти?](../get-help-with-domains/information-for-dns-records.md)          |
   
6. Нажмите кнопку **Add** (Добавить).
    
7. Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.
    
Теперь, когда вы добавили запись на сайт регистратора доменных имен, вернитесь в корпорацию Майкрософт и запросите Поиск записи.
  
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
    
4. На странице " **Управление DNS** " перейдите на вкладку **Advanced DNS (дополнительно** ). 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Hostname (Имя узла)**|**Type (Тип)**|**Priority (Приоритет)**|**Destination MX (Запись MX назначения)**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1,1  <br/> Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).    <br/> | *\<ключ_домена\>*  .mail.protection.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> **Примечание.**  Получите свой \<domain-key\> (ключ домена) из учетной записи Майкрософт. [Как его найти?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Копирование и вставка значений из таблицы](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. Нажмите кнопку **Добавить**.
    
    ![Нажмите кнопку Добавить](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. Если есть какие-либо другие записи MX, удалите каждую из них, щелкнув соответствующий значок с изображением **корзины**. 
    
    ![Нажмите кнопку Удалить (значок корзины).](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Добавление шести записей CNAME, необходимых для Майкрософт
<a name="BKMK_add_CNAME"> </a>

1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте 123-reg.co.uk по [этой ссылке](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Сначала вам потребуется выполнить вход.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. На странице " **Управление DNS** " перейдите на вкладку **Advanced DNS (дополнительно** ). 
    
5. Добавьте первую из шести записей CNAME.
    
    In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Hostname (Имя узла)**|**Type (Тип)**|**Destination CNAME (Запись CNAME назначения)**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |
   
    ![Скопируйте и вставьте значения из таблицы](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. Нажмите кнопку **Добавить**.
    
    ![Нажмите кнопку Добавить](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. Добавьте пять других записей CNAME.
    
    В разделе **Advanced DNS (Расширенный DNS** ) создайте запись, используя значения из следующей строки таблицы, а затем еще раз нажмите кнопку **Добавить** , чтобы завершить эту запись. 
    
    Повторяйте эти действия, пока не будут созданы все шесть записей CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Добавление записи TXT для SPF, предотвращающей рассылку спама
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT. Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама. Если у вас уже есть запись SPF для вашего домена, не создавайте ее для Микросфот. Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь *одну* запись SPF, включающую оба набора значений. Нужны примеры? Ознакомьтесь с этими [записями системы внешних доменных имен для продуктов корпорации Майкрософт](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте 123-reg.co.uk по [этой ссылке](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Сначала вам потребуется выполнить вход.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. На странице " **Управление DNS** " перейдите на вкладку **Advanced DNS (дополнительно** ). 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Hostname (Имя узла)**|**Type (Тип)**|**Destination TXT/SPF**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT/SPF  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.               |
   
    ![123Reg — BP — configure – 4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. Нажмите кнопку **Добавить**.
    
    ![Нажмите кнопку Добавить](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт
<a name="BKMK_add_SRV"> </a>

1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте 123-reg.co.uk по [этой ссылке](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Сначала вам потребуется выполнить вход.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. На странице " **Управление DNS** " перейдите на вкладку **Advanced DNS (дополнительно** ). 
    
5. Добавьте первую из двух записей SRV.
    
    In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |Hostname (Имя узла)|Type (Тип)|Priority (Приоритет)|TTL (Срок жизни)|Destination SRV (Запись SRV назначения)|
    |_sip. _tls|SRV|100|3600|1 443 sipdir.online.lync.com. **This value MUST end with a period (.)**<br> **Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.               |
    |_sipfederationtls. _tcp|SRV|100|3600|1 5061 sipfed.online.lync.com. **This value MUST end with a period (.)** <br> **Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.               |
   
    ![Скопируйте и вставьте значения из таблицы](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. Нажмите кнопку **Добавить**.
    
    ![Нажмите кнопку Добавить](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. Добавьте вторую запись SRV.
    
    В разделе **Advanced DNS (Расширенный DNS** ) создайте запись, используя значения из второй строки таблицы, а затем еще раз нажмите кнопку **Добавить** , чтобы завершить эту запись. 
    
> [!NOTE]
> Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
