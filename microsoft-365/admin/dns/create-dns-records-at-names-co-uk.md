---
title: Создание записей DNS на сайте Names.co.uk для Майкрософт
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
ms.assetid: b6c15128-b456-49b4-8b5e-5b823c700f26
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу Names.co.uk для Майкрософт.
ms.openlocfilehash: d3a3e68558efc3857d343b3298c3c01f0e8d8802
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645867"
---
# <a name="create-dns-records-at-namescouk-for-microsoft"></a>Создание записей DNS на сайте Names.co.uk для Майкрософт

 **[Вопросы и ответы по доменам](../setup/domains-faq.md)**. 
  
Если ваш поставщик услуг размещения DNS  Names.co.uk, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.
    
Когда вы добавите эти записи на сайте Names.co.uk, ваш домен будет настроен для работы со службами Майкрософт.
  

  
> [!NOTE]
>  Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Добавление записи TXT для проверки
<a name="BKMK_verify"> </a>

Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.
  
> [!NOTE]
> Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже. 
  
1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте Names.co.uk по [этой ссылке](https://account.names.co.uk/dashboard#/). Сначала вам потребуется выполнить вход.
    
    ![Намесук — BP — configure – 1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list. 
    
    (You may have to scroll down.)
    
    ![Намесук — BP — configure – 1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    В раскрывающемся списке выберите значение параметра **Type** (Тип). 
    
    (Если необходимо добавить строку, выберите **добавить записи a/CNAME (+)**.)
    
    (Возможно, потребуется прокрутить страницу вниз.)
        
    |**Host Name (Имя узла)**|**Type (Тип)**|**Result (Результат)**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Примечание.** Это пример. Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.           [Как его найти?](../get-help-with-domains/information-for-dns-records.md)    |
       
    ![Намесук — BP — Verify – 1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. Нажмите кнопку **Сохранить**.
    
    (Возможно, потребуется прокрутить страницу вниз.)
    
    ![Намесук — BP — Verify – 1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.
    
Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.
  
Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.
  
1. В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).
    
2. На странице **Domains** (Домены) выберите домен, который нужно проверить. 
    
    
  
3. На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).
    
    
  
4. На странице **Проверка домена** выберите **Проверить**.
    
    
  
> [!NOTE]
>  Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.
<a name="BKMK_add_MX"> </a>

1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте Names.co.uk по [этой ссылке](https://account.names.co.uk/dashboard#/). Сначала вам потребуется выполнить вход.
    
    ![Намесук — BP — configure – 1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list. 
    
    (You may have to scroll down.)
    
    ![Намесук — BP — configure – 1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. На странице **Add/Modify DNS Zone** (Добавить/изменить зону DNS) в разделе **Mail exchange records** (Записи обмена электронной почтой) в поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже. 
    
    (Возможно, потребуется прокрутить страницу вниз.)
    
    |**Host Name (Имя узла)**|**Priority (Приоритет)**|**Result (Результат)**|
    |:-----|:-----|:-----|
    |(Оставьте это поле пустым.)  <br/> |1,1  <br/> Дополнительные сведения о приоритете см. в статье [Что такое приоритет записей MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq). <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> > [!NOTE]> получить свою  *\<domain-key\>*  учетную запись Майкрософт.           [Как его найти?](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![Намесук — BP — configure – 2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. Нажмите кнопку **Сохранить**.
    
    (Возможно, потребуется прокрутить страницу вниз.)
    
    ![Намесук — BP — configure – 2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. Если в разделе **Mail exchange records** (Записи обмена электронной почтой) есть какие-либо другие записи MX, удалите каждую из них, выделив ее и нажав на клавиатуре клавишу **DELETE**. 
    
    ![Намесук — BP — configure – 2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. Нажмите кнопку **Сохранить**.
    
    (Возможно, потребуется прокрутить страницу вниз.)
    
    ![Намесук — BP — configure – 2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Добавление шести записей CNAME, необходимых для Майкрософт
<a name="BKMK_add_CNAME"> </a>

1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте Names.co.uk по [этой ссылке](https://account.names.co.uk/dashboard#/). Сначала вам потребуется выполнить вход.
    
    ![Намесук — BP — configure – 1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list. 
    
    (You may have to scroll down.)
    
    ![Намесук — BP — configure – 1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    В раскрывающемся списке выберите значение параметра **Type** (Тип). 
    
    (Если необходимо добавить строку, выберите **добавить записи a/CNAME (+)**.)
    
    (Возможно, потребуется прокрутить страницу вниз.)
    
    |**Host Name (Имя узла)**|**Type (Тип)**|**Result (Результат)**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
       
    ![Намесук — BP — configure – 3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. Нажмите кнопку **Сохранить**.
    
    ![Намесук — BP — configure – 3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Добавление записи TXT для SPF, предотвращающей рассылку спама
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT. Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама. Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт. Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь  *одну*  запись SPF, включающую оба набора значений.
  
1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте Names.co.uk по [этой ссылке](https://account.names.co.uk/dashboard#/). Сначала вам потребуется выполнить вход.
    
    ![Намесук — BP — configure – 1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list. 
    
    (You may have to scroll down.)
    
    ![Намесук — BP — configure – 1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. На странице " **зоны DNS в учетной записи** " в столбце **доменное имя** выберите доменное имя, которое вы хотите обновить. 
    
    ![Намесук — BP — configure – 1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    В раскрывающемся списке выберите значение параметра **Type** (Тип). 
    
    (Если необходимо добавить строку, выберите **добавить записи a/CNAME (+)**.)
    
    (Возможно, потребуется прокрутить страницу вниз.)
    
    |**Host Name (Имя узла)**|**Type (Тип)**|**Result (Результат)**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.               |
       
    ![Намесук — BP — configure – 4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. Нажмите кнопку **Сохранить**.
    
    (Возможно, потребуется прокрутить страницу вниз.)
    
    ![Намесук — BP — configure – 4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт
<a name="BKMK_add_SRV"> </a>

1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте Names.co.uk по [этой ссылке](https://account.names.co.uk/dashboard#/). Сначала вам потребуется выполнить вход.
    
    ![Намесук — BP — configure – 1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list. 
    
    (You may have to scroll down.)
    
    ![Намесук — BP — configure – 1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. На странице **Add/Modify DNS Zone** (Добавить/изменить зону DNS) в разделе **Service records** (Записи службы) в поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже. 
    
    (Возможно, потребуется прокрутить страницу вниз.)
    
    |**Name (Имя)**|**Priority** (Приоритет)|**Weight** (Вес)|**Port** (Порт)|**Result (Результат)**|
    |:-----|:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |100  <br/> |1,1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls._tcp  <br/> |100  <br/> |1,1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
       
    ![Намесук — BP — configure – 5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. Нажмите кнопку **Сохранить**.
    
    (Возможно, потребуется прокрутить страницу вниз.)
    
    ![Намесук — BP — configure – 5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
