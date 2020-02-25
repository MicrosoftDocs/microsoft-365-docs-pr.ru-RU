---
title: Создание записей DNS для Office 365 на сайте Crazy Domains
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
ms.assetid: 6386d63e-b78f-4736-90e7-b99a2c116a9f
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб в доменах Crazy для Office 365.
ms.openlocfilehash: 5b344ebdc4a4608c27c0a84299ea171391c09ba0
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42248160"
---
# <a name="create-dns-records-at-crazy-domains-for-office-365"></a>Создание записей DNS для Office 365 на сайте Crazy Domains

 **[Вопросы и ответы по доменам](../setup/domains-faq.md)**. 
  
Если ваш поставщик услуг размещения DNS  Crazy Domains, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.
  
Когда вы добавите эти записи на сайте Crazy Domains, ваш домен будет настроен для работы со службами Office 365.
  
Дополнительные сведения о веб-хостинге и DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
> Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Добавление записи TXT для проверки
<a name="BKMK_verify"> </a>

Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете данным доменом.
  
> [!NOTE]
> Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже. 
  
1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте Crazy Domains по [этой ссылке](https://manage.crazydomains.com/members/domains/). Сначала вам потребуется выполнить вход.
    
    ![Кразидомаинс — BP — configure – 1-1](../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. В разделе " **Моя учетная запись** " выберите пункт **домены**.
    
    ![Кразидомаинс — BP — configure – 1-2](../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. На странице **Domain Names** (доменные имена) в разделе **Domain (домен** ) выберите имя обновляемого домена. 
    
    ![Кразидомаинс — BP — configure – 1-3](../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. В разделе **параметры DNS** выберите значок раскрывающегося списка. 
    
    ![Кразидомаинс — BP — configure – 1-4-1](../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. Выберите команду **Add Record** (Добавить запись).
    
    ![Кразидомаинс — BP — configure – 1-4-2](../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. В раскрывающемся списке **Add Record** (Добавить запись) выберите пункт **TXT Record** (Запись TXT). 
    
    ![Кразидомаинс — BP — Verify – 1-1](../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. Нажмите кнопку **Добавить**.
    
    ![Кразидомаинс — BP — Verify – 1-2](../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.
    
    |**Sub Domain (Поддомен)**|**Text Record (Текстовая запись)**|
    |:-----|:-----|
    |(Leave this field empty.)  <br/> |MS=ms *XXXXXXXX*  <br/> **Примечание.** Это пример. Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.           [Где это находится?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Кразидомаинс — BP — Verify – 1-3](../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. Нажмите кнопку **Обновить**.
    
    ![Кразидомаинс — BP — Verify – 1-4](../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. В центре администрирования перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> **параметров** \> ".

    
2. На странице **Domains (домены** ) выберите домен, который вы хотите проверить. 
    
    
  
3. На странице **Настройка** выберите пункт **Запуск программы установки**.
    
    
  
4. На странице **Проверка домена** нажмите кнопку **проверить**.
    
    
  
> [!NOTE]
>  Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365
<a name="BKMK_add_MX"> </a>

1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте Crazy Domains по [этой ссылке](https://manage.crazydomains.com/members/domains/). Сначала вам потребуется выполнить вход.
    
    ![Кразидомаинс — BP — configure – 1-1](../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. В разделе " **Моя учетная запись** " выберите пункт **домены**.
    
    ![Кразидомаинс — BP — configure – 1-2](../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. На странице **Domain Names** (доменные имена) в разделе **Domain (домен** ) выберите имя обновляемого домена. 
    
    ![Кразидомаинс — BP — configure – 1-3](../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. В разделе **параметры DNS** выберите значок раскрывающегося списка. 
    
    ![Кразидомаинс — BP — configure – 1-4-1](../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. Выберите команду **Add Record** (Добавить запись).
    
    ![Кразидомаинс — BP — configure – 1-4-2](../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. В раскрывающемся списке **Add Record:** (Добавить запись) выберите пункт **MX Record** (Запись MX). 
    
    ![Кразидомаинс — BP — configure – 2-1](../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. Нажмите кнопку **Добавить**.
    
    ![Кразидомаинс — BP — configure – 2-2](../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.
    
    В раскрывающемся списке выберите значение **Priority (приоритет** ). 
    
    |**Mail For Zone (Почта для зоны)**|**Priority (Приоритет)**|**Assigned To Server (Назначено серверу)**|
    |:-----|:-----|:-----|
    |(Оставьте это поле пустым.)  <br/> |1,1  <br/> Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).    <br/> | *\<ключ_домена\>*  .mail.protection.outlook.com  <br/> **Примечание:** Получите * \<ключ\> домена* из учетной записи Office 365.           [Как найти это значение?](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Кразидомаинс — BP — configure – 2-3](../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. Нажмите кнопку **Обновить**.
    
    ![Кразидомаинс — BP — configure – 2-4](../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. Если в разделе **MX Record (запись MX** ) указаны другие записи MX, выберите **изменить** для одной из этих записей. 
    
    ![Кразидомаинс — BP — configure – 2-5](../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. Нажмите кнопку **Удалить**.
    
    ![Кразидомаинс — BP — configure – 2-6](../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. Нажмите кнопку **Обновить** , чтобы подтвердить удаление. 
    
    ![Кразидомаинс — BP — configure – 2-7](../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. Повторите эти действия для удаления из списка всех остальных записей MX, кроме той, которую вы добавили на предыдущих шагах.
    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Добавление шести записей CNAME, необходимых для Office 365
<a name="BKMK_add_CNAME"> </a>

1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте Crazy Domains по [этой ссылке](https://manage.crazydomains.com/members/domains/). Сначала вам потребуется выполнить вход.
    
    ![Кразидомаинс — BP — configure – 1-1](../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. В разделе " **Моя учетная запись** " выберите пункт **домены**.
    
    ![Кразидомаинс — BP — configure – 1-2](../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. На странице **Domain Names** (доменные имена) в разделе **Domain (домен** ) выберите имя обновляемого домена. 
    
    ![Кразидомаинс — BP — configure – 1-3](../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. В разделе **параметры DNS** выберите значок раскрывающегося списка. 
    
    ![Кразидомаинс — BP — configure – 1-4-1](../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. Выберите команду **Add Record** (Добавить запись).
    
    ![Кразидомаинс — BP — configure – 1-4-2](../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. В раскрывающемся списке **Add Record:** (Добавить запись) выберите пункт **CNAME Record** (Запись CNAME). 
    
    ![Кразидомаинс — BP — configure – 3-1](../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. Нажмите кнопку **Добавить**.
    
    ![Кразидомаинс — BP — configure – 3-2](../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. Добавьте первую из шести записей CNAME.
    
    В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.
    
    |**Sub Domain (Поддомен)**|**Alias for (Псевдоним для)**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Кразидомаинс — BP — configure – 3-3](../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. Выберите **Добавить запись CNAME**.
    
    ![Кразидомаинс — BP — configure – 3-4](../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. Добавьте вторую запись CNAME.
    
    В поля для новой записи используйте значения из следующей строки таблицы, а затем снова выберите **Добавить запись CNAME**.
    
    Повторяйте эти действия, пока не будут созданы все шесть записей CNAME.
    
11. Нажмите кнопку **Обновить** , чтобы сохранить изменения. 
    
    ![Кразидомаинс — BP — configure – 3-5](../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Вместо этого добавьте необходимые значения Office 365 к текущей записи, чтобы иметь *одну* запись SPF, включающую оба набора значений. 
  
1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте Crazy Domains по [этой ссылке](https://manage.crazydomains.com/members/domains/). Сначала вам потребуется выполнить вход.
    
    ![Кразидомаинс — BP — configure – 1-1](../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. В разделе " **Моя учетная запись** " выберите пункт **домены**.
    
    ![Кразидомаинс — BP — configure – 1-2](../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. На странице **Domain Names** (доменные имена) в разделе **Domain (домен** ) выберите имя обновляемого домена. 
    
    ![Кразидомаинс — BP — configure – 1-3](../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. В разделе **параметры DNS** выберите значок раскрывающегося списка. 
    
    ![Кразидомаинс — BP — configure – 1-4-1](../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. Выберите команду **Add Record** (Добавить запись).
    
    ![Кразидомаинс — BP — configure – 1-4-2](../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. В раскрывающемся списке **Add Record:** (Добавить запись) выберите пункт **TXT Record** (Запись TXT). 
    
    ![Кразидомаинс — BP — configure – 4-1](../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. Нажмите кнопку **Добавить**.
    
    ![Кразидомаинс — BP — configure – 4-2](../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. В поля для новой записи введите или вставьте значения из таблицы ниже.
    
    |**Sub Domain (Поддомен)**|**Text Record (Текстовая запись)**|
    |:-----|:-----|
    |(Оставьте это поле пустым.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.               |
   
    ![Кразидомаинс — BP — configure – 4-3](../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. Нажмите кнопку **Обновить**.
    
    ![Кразидомаинс — BP — configure – 4-4](../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Добавление двух записей SRV, необходимых для Office 365
<a name="BKMK_add_SRV"> </a>

1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте Crazy Domains по [этой ссылке](https://manage.crazydomains.com/members/domains/). Сначала вам потребуется выполнить вход.
    
    ![Кразидомаинс — BP — configure – 1-1](../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. В разделе " **Моя учетная запись** " выберите пункт **домены**.
    
    ![Кразидомаинс — BP — configure – 1-2](../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. На странице **Domain Names** (доменные имена) в разделе **Domain (домен** ) выберите имя обновляемого домена. 
    
    ![Кразидомаинс — BP — configure – 1-3](../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. В разделе **параметры DNS** выберите значок раскрывающегося списка. 
    
    ![Кразидомаинс — BP — configure – 1-4-1](../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. Выберите команду **Add Record** (Добавить запись).
    
    ![Кразидомаинс — BP — configure – 1-4-2](../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. В раскрывающемся списке **Add Record:** (Добавить запись) выберите пункт **SRV Record** (Запись SRV). 
    
    ![Кразидомаинс — BP — configure – 5-1](../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. Нажмите кнопку **Добавить**.
    
    ![Кразидомаинс — BP — configure – 5-2](../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. Добавьте первую из двух записей SRV.
    
    В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.
    
    |**Record Type (Тип записи)**|**Sub Domain (Поддомен)**|**Priority (Приоритет)**|**Weight (Вес)**|**Port (Порт)**|**Target (Назначение)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV Record (Запись SRV)  <br/> |_sip. _tls  <br/> |100  <br/> |1,1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |SRV Record (Запись SRV)  <br/> |_sipfederationtls. _tcp  <br/> |100  <br/> |1,1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![Кразидомаинс — BP — configure – 5-3](../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. Выберите **Добавить запись SRV**.
    
    ![Кразидомаинс — BP — configure – 5-4](../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. Добавьте вторую запись SRV.
    
    В поля для новой записи введите значения из второй строки таблицы.
    
11. Нажмите кнопку **Обновить** , чтобы сохранить изменения. 
    
    ![Кразидомаинс — BP — configure – 5-5](../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
