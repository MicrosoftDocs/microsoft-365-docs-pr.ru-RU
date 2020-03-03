---
title: Создание DNS-записей для Office 365 на сайте MyDomain
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9982191d-ed79-46a9-b2e7-317d1a3a9867
description: Узнайте, как проверить свой домен и настроить DNS-записи для электронной почты, Skype для бизнеса Online и других служб в My Domain для Office 365.
ms.openlocfilehash: c85c04d369add95d3aaa815229257fe90a24fb28
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2020
ms.locfileid: "42349873"
---
# <a name="create-dns-records-at-mydomain-for-office-365"></a>Создание DNS-записей для Office 365 на сайте MyDomain


  
 Если вы не нашли то, что вы ищете, обратитесь к разделу **[Вопросы и ответы по доменам](../setup/domains-faq.md)**. 
  
> [!CAUTION]
> На веб-сайте MyDomain не поддерживаются записи SRV, поэтому некоторые функции Skype для бизнеса online и Outlook Web App не будут работать. Если вы управляете своими записями DNS на сайте MyDomain, то независимо от вашего плана Office 365 на доступные службы накладываются [существенные ограничения](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx). В этом случае, возможно, стоит задуматься о переходе к другому поставщику услуг размещения DNS. 
  
Если вы хотите управлять своими записями DNS для Office 365 на сайте MyDomain несмотря на ограничения служб, выполните действия, описанные в этой статье, чтобы настроить записи DNS для электронной почты, Skype для бизнеса online и т. д.
    
Когда вы добавите эти записи на сайте MyDomain, ваш домен будет настроен для работы со службами Office 365.
  
Дополнительные сведения о веб-хостинге и DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
> Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Добавление записи TXT для проверки
<a name="BKMK_verify"> </a>

Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете доменом.
  
> [!NOTE]
> Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже. 
  
1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте MyDomain по предоставленной ссылке. Сначала вам потребуется [выполнить вход](https://www.mydomain.com/controlpanel).
    
2. В разделе **My Favorites** (Избранное) выберите **Domain Central** (Центральный домен).
    
3. В поле **Domain** (Домен) выберите доменное имя, которое хотите изменить.
    
4. В строке **Overview** (Обзор) выберите **DNS**.
    
5. В раскрывающемся списке **Modify** (Изменить) выберите **TXT/SPF Record** (Запись TXT/SPF).
    
6. В разделе **Content** (Контент) в поле для новой записи введите (или скопируйте и вставьте) значение из приведенной ниже таблицы.
    
    ||
    |:-----|
    |**Контент** <br/> |
    |MS=ms *XXXXXXXX*  <br/> **Примечание.** Это пример. Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365. [Как его найти?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Нажмите кнопку **Add** (Добавить).
    
8. Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.
    
Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Office 365 и подайте запрос на ее поиск.
  
Если Office 365 обнаружит правильную запись TXT, это значит, что домен проверен.
  
1. В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).
    
2. На странице **Domains** (Домены) выберите домен, который нужно проверить. 
    
3. На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).
    
4. На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).
    
> [!NOTE]
> Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365
<a name="BKMK_add_MX"> </a>

1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте MyDomain по предоставленной ссылке. Сначала вам потребуется [выполнить вход](https://www.mydomain.com/controlpanel).
    
2. В разделе **My Favorites** (Избранное) выберите **Domain Central** (Центральный домен).
    
3. В поле **Domain** (Домен) выберите доменное имя, которое хотите изменить.
    
4. В строке **Overview** (Обзор) выберите **DNS**.
    
5. В раскрывающемся списке **Modify** (Изменить) выберите **MX Record** (Запись MX).
    
    ![MyDomain-BP-Configure-2-1](../../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.
    
    |**Priority**|**Host**|**Points To** (Указывает на)|
    |:-----|:-----|:-----|
    |0  <br/> Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx). <br/> |@  <br/> | *\<ключ_домена\>*  .mail.protection.outlook.com  <br/> **Примечание.**  Получите свой \<*ключ-домена*\> из учетной записи Office 365. > [Как его найти?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![MyDomain-BP-Configure-2-2](../../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. Нажмите кнопку **Add** (Добавить).
    
    ![MyDomain-BP-Configure-2-3](../../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. Если в списке указаны другие существующие записи MX, для каждой из них выберите команду **Remove** (Удалить) в столбце **Action** (Действие). 
    
    ![MyDomain-BP-Configure-2-4](../../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. Нажмите кнопку **ОК**.
    
    ![MyDomain-BP-Configure-2-5](../../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a>Добавление записей CNAME, необходимых для Office 365
<a name="BKMK_add_CNAME"> </a>

1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте MyDomain по предоставленной ссылке. Сначала вам потребуется [выполнить вход](https://www.mydomain.com/controlpanel).
    
2. В разделе **My Favorites** (Избранное) выберите **Domain Central** (Центральный домен).
    
3. В поле **Domain** (Домен) выберите доменное имя, которое хотите изменить.
    
4. В строке **Overview** (Обзор) выберите **DNS**.
    
5. В раскрывающемся списке **Modify** (Изменить) выберите **CNAME Alias** (Псевдоним CNAME).
    
    ![MyDomain-BP-Configure-3-1](../../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. Добавьте первую запись CNAME.
    
    В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.
    
    |**Host**|**Points To** (Указывает на)|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. Нажмите **Add** (Добавить), чтобы добавить первую запись. 
    
    ![MyDomain-BP-Configure-3-3](../../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. Добавьте вторую запись CNAME.
    
    Введите значения из второй строки приведенной выше таблицы, а затем нажмите кнопку **Add** (Добавить), чтобы создать вторую запись. 
    
    Точно так же добавьте остальные записи, используя значения из третьей, четвертой, пятой и шестой строк таблицы.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Добавление записи TXT для SPF, предотвращающей рассылку спама
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT. Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values. Нужны примеры? Ознакомьтесь с этими [сведениями и образцами записей SPF](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте MyDomain по предоставленной ссылке. Сначала вам потребуется [выполнить вход](https://www.mydomain.com/controlpanel).
    
2. В разделе **My Favorites** (Избранное) выберите **Domain Central** (Центральный домен).
    
3. В поле **Domain** (Домен) выберите доменное имя, которое хотите изменить.
    
4. В строке **Overview** (Обзор) выберите **DNS**.
    
5. В раскрывающемся списке **Modify** (Изменить) выберите **TXT/SPF Record** (Запись TXT/SPF).
    
    ![MyDomain-BP-Configure-4-1](../../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. В разделе **Content** (Контент) в поле для новой записи введите (или скопируйте и вставьте) значение из приведенной ниже таблицы.
    
    |**Контент**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> **Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.               |
   
    ![MyDomain-BP-Configure-4-2](../../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. Нажмите кнопку **Add** (Добавить).
    
    ![MyDomain-BP-Configure-4-3](../../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Добавление двух записей SRV, необходимых для Office 365
<a name="BKMK_add_SRV"> </a>

> [!CAUTION]
> На веб-сайте MyDomain не поддерживаются записи SRV, поэтому некоторые функции Skype для бизнеса online и Outlook Web App не будут работать. Если вы управляете своими записями DNS на сайте MyDomain, то независимо от вашего плана Office 365 на доступные службы накладываются [существенные ограничения](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx). В этом случае, возможно, стоит задуматься о переходе к другому поставщику услуг размещения DNS. 
  
> [!NOTE]
> Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
