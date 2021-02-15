---
title: Создание записей DNS для Майкрософт на сайте Namecheap
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
ms.assetid: 54ae2002-b38e-43a1-82fa-3e49d78fda56
description: Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Namecheap for Microsoft.
ms.openlocfilehash: 1e0fa8839e4ceae5074059d6ae05e3c7456611c2
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657843"
---
# <a name="create-dns-records-at-namecheap-for-microsoft"></a>Создание записей DNS для Майкрософт на сайте Namecheap

 Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**. 
  
Если ваш поставщик услуг размещения DNS  Namecheap, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб.
  
После добавления этих записей на сайте Namecheap ваш домен будет настроен для работы со службами Майкрософт.
  
> [!NOTE]
> Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Добавление записи TXT для проверки
<a name="BKMK_verify"> </a>

Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.
  
> [!NOTE]
> Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже. 
  
Выполните указанные ниже действия.
  
1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте Namecheap по [этой ссылке](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Вам потребуется войти в службу.
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. On the **Landing** page, under **Account,** choose **Domain List** from the drop-down list. 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. На странице **"Список доменов"** найдите имя домена, который нужно изменить, и выберите **"Управление".**
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. Выберите **"Advanced DNS" (Расширенный DNS).**
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. В разделе **"ЗАПИСИ ХОСТА"** выберите **"ДОБАВИТЬ НОВУЮ ЗАПИСЬ".**
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. В раскрывающемся списке **Type** (Тип) выберите **TXT Record** (Запись TXT).
    
    > [!NOTE]
    > При **выборе** "ADD NEW RECORD" автоматически появляется выпадайка **"Тип".** 
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.
    
    (Выберите значение **TTL** в выпадаемом списке.) 
    
    |**Type (Тип)**|**Host (Узел)**|**Value** (Значение)|**TTL** (Срок жизни)|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |MS=ms *XXXXXXXX*  <br/>**Примечание.** Это пример. Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.  [Как его найти?](../get-help-with-domains/information-for-dns-records.md)          |30 мин  <br/> |
       
    ![Namecheap-BP-Verify-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. Выберите **контрольный знак** "Сохранить изменения". 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.
    
Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.
  
Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.
  
1. В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).
    
2. На странице **Domains** (Домены) выберите домен, который нужно проверить. 
    
    
  
3. На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).
    
    
  
4. На странице **Проверка домена** выберите **Проверить**.
    
    
  
> [!NOTE]
> Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.
<a name="BKMK_add_MX"> </a>

Выполните указанные ниже действия.
  
1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте Namecheap по [этой ссылке](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Вам потребуется войти в службу.
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. On the **Landing** page, under **Account,** choose **Domain List** from the drop-down list. 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. На странице **"Список доменов"** найдите имя домена, который нужно изменить, и выберите **"Управление".**
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. Выберите **"Advanced DNS" (Расширенный DNS).**
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. В разделе **MAIL SETTINGS** (Параметры почты) выберите **Custom MX** (Настраиваемая запись MX) в раскрывающемся списке **Email Forwarding** (Переадресация электронной почты). 
    
    (Возможно, потребуется прокрутить страницу вниз.)
    
    ![Namecheap-BP-Configure-2-1](../../media/40199e2c-42cf-4c3f-9936-3cbe5d4e81a4.png)
  
6. Выберите **"Добавить новую запись"**.
    
    ![Namecheap-BP-Configure-2-2-1](../../media/8d169b81-ba48-4d51-84ea-a08fa1616457.png)
  
7. В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.
    
    (Поле **Priority** (Приоритет)  это поле без названия справа от поля **Value** (Значение). Выберите значение **TTL** в выпадаемом списке.) 
    
    |**Type (Тип)**|**Host (Узел)**|**Value** (Значение)|**Priority** (Приоритет)|**TTL** (Срок жизни)|
    |:-----|:-----|:-----|:-----|:-----|
    |MX Record (Запись MX)  <br/> |@  <br/> |\<*domain-key*\>.mail.protection.outlook.com.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> **Примечание.** Получите свою  *\<domain-key\>*  учетную запись Майкрософт.  [Как его найти?](../get-help-with-domains/information-for-dns-records.md)          |0  <br/> Дополнительные сведения о приоритете см. в статье [Что такое приоритет записей MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq). <br/> |30 мин  <br/> |
       
    ![Namecheap-BP-Configure-2-2-2](../../media/f3b76d62-5022-48c1-901b-8615a8571309.png)
  
8. Выберите **контрольный знак** "Сохранить изменения". 
    
    ![Namecheap-BP-Configure-2-3](../../media/ef4e3112-36d2-47c8-a478-136a565dd71d.png)
  
9. Если есть какие-либо другие записи MX, удалите каждую из них, выполнив двухшаговую процедуру.
    
    Сначала выберите значок **"Удалить"** (корзину) для записи, которую нужно удалить. 
    
    ![Namecheap-BP-Configure-2-4](../../media/7a7a751f-29c2-495f-8f55-98ca37ce555a.png)
  
    Затем выберите **"Да",** чтобы подтвердить удаление. 
    
    ![Namecheap-BP-Configure-2-5](../../media/85ebc0c7-8787-43ee-9e7b-647375b3345c.png)
  
    Удалите все записи MX, кроме той, которую вы добавили ранее в этой процедуре.

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Добавление шести записей CNAME, необходимых для Корпорации Майкрософт
<a name="BKMK_add_CNAME"> </a>

Выполните указанные ниже действия.
  
1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте Namecheap по [этой ссылке](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Вам потребуется войти в службу.
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. On the **Landing** page, under **Account,** choose **Domain List** from the drop-down list. 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. На странице **"Список доменов"** найдите имя домена, который нужно изменить, и выберите **"Управление".**
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. Выберите **"Advanced DNS" (Расширенный DNS).**
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. В разделе **"ЗАПИСИ ХОСТА"** выберите **"ДОБАВИТЬ НОВУЮ ЗАПИСЬ".**
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. В раскрывающемся списке **Type** (Тип) выберите **CNAME Record** (Запись CNAME).
    
    > [!NOTE]
    > При **выборе** "ADD NEW RECORD" автоматически появляется выпадайка **"Тип".** 
  
    ![Namecheap-BP-Configure-3-1](../../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png)
  
7. В пустых полях для новой записи выберите значение **CNAME** для параметра **Record Type** (Тип записи) и введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.
    
    |**Type (Тип)**|**Host (Узел)**|**Value** (Значение)|**TTL** (Срок жизни)|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |3600  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |3600  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |3600  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |3600  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |3600  <br/> |
       
    ![Namecheap-BP-Configure-3-2](../../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png)
  
8. Выберите **контрольный знак** "Сохранить изменения". 
    
    ![Namecheap-BP-Configure-3-3](../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png)
  
9. Используя четыре предыдущих шага и значения из пяти других строк таблицы, добавьте каждую из остальных пяти записей CNAME.

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Добавление записи TXT для SPF, предотвращающей рассылку спама
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT. Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама. Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт. Вместо этого добавьте необходимые значения Майкрософт в текущую  запись, чтобы иметь одну запись SPF, которая включает оба набора значений. 

Выполните указанные ниже действия.
  
1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте Namecheap по [этой ссылке](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Вам потребуется войти в службу.
    
2. On the **Landing** page, under **Account,** choose **Domain List** from the drop-down list. 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. На странице **"Список доменов"** найдите имя домена, который нужно изменить, и выберите **"Управление".**
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. Выберите **"Advanced DNS" (Расширенный DNS).**
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. В разделе **"ЗАПИСИ ХОСТА"** выберите **"ДОБАВИТЬ НОВУЮ ЗАПИСЬ".**
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. В раскрывающемся списке **Type** (Тип) выберите **TXT Record** (Запись TXT).
    
    > [!NOTE]
    > При **выборе** "ADD NEW RECORD" автоматически появляется выпадайка **"Тип".** 
  
    ![Namecheap-BP-Configure-4-1](../../media/c5d1fddb-28b5-48ec-91c9-3e5d3955ac80.png)
  
7. В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.
    
    (Выберите значение **TTL** в выпадаемом списке.) 
    
    |**Type (Тип)**|**Host (Узел)**|**Value** (Значение)|**TTL** (Срок жизни)|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.               |30 мин  <br/> |
       
    ![Namecheap-BP-Configure-4-2](../../media/ea0829f1-990b-424b-b26e-9859468318dd.png)
  
8. Выберите **контрольный знак** "Сохранить изменения". 
    
    ![Namecheap-BP-Configure-4-3](../../media/f2846c36-ace3-43d8-be5d-a65e2c267619.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт
<a name="BKMK_add_SRV"> </a>

1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте Namecheap по [этой ссылке](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Вам потребуется войти в службу.
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. On the **Landing** page, under **Account,** choose **Domain List** from the drop-down list. 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. На странице **"Список доменов"** найдите имя домена, который нужно изменить, и выберите **"Управление".**
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. Выберите **"Advanced DNS" (Расширенный DNS).**
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. В разделе **"ЗАПИСИ ХОСТА"** выберите **"ДОБАВИТЬ НОВУЮ ЗАПИСЬ".**
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. В раскрывающемся списке **Type** (Тип) выберите **SRV Record** (Запись SRV).
    
    > [!NOTE]
    > При **выборе** "ADD NEW RECORD" автоматически появляется выпадайка **"Тип".** 
  
    ![Namecheap-BP-Configure-5-1](../../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png)
  
7. В пустые поля для новых записей введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.
    
    |**Служба**|**Protocol (Протокол)**|**Priority** (Приоритет)|**Weight** (Вес)|**Port** (Порт)|**Target (Назначение)**|**TTL (Срок жизни)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |30 мин  <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |30 мин  <br/> |
       
    ![Namecheap-BP-Configure-5-2](../../media/ff9566ea-0096-4b7f-873c-027080a23b56.png)
  
8. Выберите **контрольный знак** "Сохранить изменения". 
    
    ![Namecheap-BP-Configure-5-3](../../media/48a8dee4-c66d-449d-8759-9e9784c82b13.png)
  
9. Повторите четыре описанных выше шага, используя значения из второй строки таблицы, чтобы добавить еще одну запись SRV.
    
> [!NOTE]
> Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  

  
