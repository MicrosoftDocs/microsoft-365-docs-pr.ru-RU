---
title: Создание записей DNS для Office 365 на сайте Freenom
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу Freenom для Office 365.
ms.openlocfilehash: 16348eb03a6507e15d31d5c183bd91125d0236f6
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2020
ms.locfileid: "42350670"
---
# <a name="create-dns-records-at-freenom-for-office-365"></a>Создание записей DNS для Office 365 на сайте Freenom

Если вы не нашли нужную информацию, см. статью [Вопросы и ответы о доменах](../setup/domains-faq.md). 
  
> [!CAUTION]
> На веб-сайте Freenom не поддерживаются записи SRV, поэтому некоторые функции Skype для бизнеса Online и Outlook Web App не будут работать. Независимо от того, какой план Office 365 вы используете, на веб-сайте Freenom могут действовать существенные ограничения служб, поэтому стоит задуматься о переходе на другого поставщика услуг размещения DNS. 
  
Если несмотря на ограничения службы, вы решили управлять собственными записями DNS для Office 365 по адресу Freenom, выполнив действия, описанные в этой статье, чтобы проверить домен и настроить записи DNS для электронной почты и других служб.
  
Дополнительные сведения о веб-хостинге и DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
> Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Добавление записи TXT для проверки
<a name="bkmk_txt"> </a>

Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете доменом.
  
> [!NOTE]
> Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже. 
  
1. Чтобы приступить к работе, откройте страницу со своими доменами в Freenom с помощью [этой ссылки](https://my.freenom.com/). Вам потребуется выполнить вход.
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Выберите **службы**, а затем выберите пункт **Мои домены**.
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Для домена, который требуется изменить, выберите пункт **Управление доменом**.
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Выберите **Управление FREENOM DNS**.
    
    ![Freenom Manage Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. В разделе **Add Record** (Добавление записи) в столбце **Type** (Тип) выберите **TXT** в списке. 
    
    ![Freenom Add Record type TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже. 
    
    |**Имя**|**Тип**|**TTL**|**Target (Назначение)**|
    |:-----|:-----|:-----|:-----|
    |(Оставьте пустым)  <br/> |TXT  <br/> |3600 (секунд)  <br/> |MS = Мскскскскскскскскс  <br/> **Примечание.** Это пример. Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.           [Где это находится?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Freenom TXT values for verification](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. Нажмите кнопку **сохранить изменения**.
    
    ![Freenom TXT record Save Changes](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.
    
Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Office 365 и подайте запрос на ее поиск.
  
Если Office 365 обнаружит правильную запись TXT, это значит, что домен проверен.
  
1. В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).

    
2. На странице **Domains** (Домены) выберите домен, который нужно проверить. 
    
    
  
3. На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).
    
    
  
4. На странице **Проверка домена** выберите **Проверить**.
    
    
  
> [!NOTE]
>  Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365
<a name="bkmk_mx"> </a>

1. Чтобы приступить к работе, откройте страницу со своими доменами в Freenom с помощью [этой ссылки](https://my.freenom.com/). Вам потребуется выполнить вход.
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Выберите **службы**, а затем выберите пункт **Мои домены**.
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Для домена, который требуется изменить, выберите пункт **Управление доменом**.
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Задайте для домена имя сервера Freenom по умолчанию. Выберите **средства управления**, а затем выберите **серверов доменных имен**.
    
    ![Freenom Nameservers setting](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. Убедитесь, что установлен флажок **использовать серверов доменных имен по умолчанию** , и нажмите кнопку **изменить серверов доменных имен**.
    
    ![Freenom Change Nameservers](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. Выберите **Управление FREENOM DNS**.
    
    ![Freenom выбор управления Freenom DNS](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. В разделе **Add Record** (Добавление записи) в столбце **Type** (Тип) выберите **MX** в списке. 
    
    ![Freenom Add Record type MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки таблицы ниже. 
    
    |**Имя**|**Тип**|**TTL**|**Target (Назначение)**|**Priority (Приоритет)**|
    |:-----|:-----|:-----|:-----|:-----|
    |(оставьте пустым)  <br/> |MX (почтовый обменник)  <br/> |3600 (секунд)  <br/> |\<Domain — key\>. mail.Protection.Outlook.com  <br/> **Примечание:** Получите * \<ключ\> домена* из учетной записи Office 365.   [Где это находится?](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> Дополнительные сведения о приоритете см. в статье [What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9).    <br/> |
   
   ![Freenom MX record](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. Нажмите кнопку **сохранить изменения**.
    
    ![Freenom MX record Save Changes](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. Если существуют какие-либо другие записи MX, удалите их все. Для каждой записи нажмите кнопку **Удалить**. Когда **вы действительно хотите удалить эту запись?** откроется сообщение, нажмите кнопку **ОК**.
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a>Добавление записей CNAME, необходимых для Office 365
<a name="bkmk_cname"> </a>

1. Чтобы приступить к работе, откройте страницу со своими доменами в Freenom с помощью [этой ссылки](https://my.freenom.com/). Вам потребуется выполнить вход.
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Выберите **службы**, а затем выберите пункт **Мои домены**.
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Для домена, который требуется изменить, выберите пункт **Управление доменом**.
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Выберите **Управление FREENOM DNS**.
    
    ![Freenom выбор управления Freenom DNS](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. В разделе **Add Record** (Добавление записи) в столбце **Type** (Тип) выберите **CNAME** в списке. 
    
    ![Freenom Add Record type CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. Создайте первую запись CNAME. В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки таблицы ниже. 
    
    |**Name (Имя)**|**Record Type (Тип записи)**|**TTL (Срок жизни)**|**Target (Назначение)**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |3600 (секунд)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |3600 (секунд)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |3600 (секунд)  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |3600 (секунд)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |3600 (секунд)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Freenom CNAME values](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. Нажмите кнопку **сохранить изменения**.
    
    ![Freenom CNAME Save Changes](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. Повторив эти действия, создайте пять других записей CNAME. 
    
    Создайте пять других записей CNAME, как описано выше.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Добавление записи TXT для SPF, предотвращающей рассылку спама
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT. Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама. If you already have an SPF record for your domain, don't create a new one for Office 365. Вместо этого добавьте необходимые значения Office 365 в текущую запись. Таким образом, в *одной* записи SPF будут указаны оба набора значений. 

1. Чтобы приступить к работе, откройте страницу со своими доменами в Freenom с помощью [этой ссылки](https://my.freenom.com/). Вам потребуется выполнить вход.
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Выберите **службы**, а затем выберите пункт **Мои домены**.
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Для домена, который требуется изменить, выберите пункт **Управление доменом**.
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Выберите **Управление FREENOM DNS**.
    
    ![Freenom выбор управления Freenom DNS](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. В разделе **Add Record** (Добавление записи) в столбце **Type** (Тип) выберите **TXT** в списке. 
    
    ![Freenom Add Record type TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. В поля для новой записи введите (или скопируйте и вставьте) указанные ниже значения. 
    
    |**Name (Имя)**|**Record Type (Тип записи)**|**TTL (Срок жизни)**|**Target (Назначение)**|
    |:-----|:-----|:-----|:-----|
    |(оставьте пустым)  <br/> |TXT  <br/> |3600 (секунд)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.               |
   
    ![Freenom TXT values for SPF](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. Нажмите кнопку **сохранить изменения**.
    
    ![Freenom TXT record for SPF Save Changes](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

