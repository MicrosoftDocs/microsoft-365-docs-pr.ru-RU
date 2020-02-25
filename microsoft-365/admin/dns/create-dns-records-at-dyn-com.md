---
title: Создание записей DNS для Office 365 в Dyn.com
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу Dyn.com для Office 365.
ms.openlocfilehash: d4471ec84555efb349cc1e42d5048ebf044735e5
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42248880"
---
# <a name="create-dns-records-at-dyncom-for-office-365"></a>Создание записей DNS для Office 365 в Dyn.com

 Если вы не нашли то, что вы ищете, обратитесь к разделу **[Вопросы и ответы по доменам](../setup/domains-faq.md)**. 
  
Если Dyn.com является поставщиком услуг хостинга DNS, выполните действия, описанные в этой статье, чтобы проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и т. д.
 
Дополнительные сведения о веб-хостинге и DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
>  Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Добавление записи TXT для проверки
<a name="BKMK_verify"> </a>

1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте Dyn.com по [этой ссылке](https://account.dyn.com/dns/). Сначала вам потребуется выполнить вход.
    
    ![Dyn-BP-Configure-1-1](../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. На странице " **службы уровня зоны** " выберите **Дин стандартная служба DNS** для домена, который требуется изменить. 
    
3. На странице **DNS** для вашего домена выберите **предпочтения**.
    
4. Выберите **включить экспертный интерфейс**.
    
5. In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host (Узел)**|**TTL (Срок жизни)**|**Type (Тип)**|**Data (Данные)**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |600  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Примечание.** Это пример. Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.           [Где это находится?](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Дин — BP — Verify – 1-1](../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. Выберите **создать запись**.
    
    ![Dyn-BP-Verify-1-2](../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.
    
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

1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте Dyn.com по [этой ссылке](https://account.dyn.com/dns/). Сначала вам потребуется выполнить вход.
    
    ![Dyn-BP-Configure-1-1](../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. На странице " **службы уровня зоны** " выберите **Дин стандартная служба DNS** для домена, который требуется изменить. 
    
3. На странице DNS для вашего домена выберите **предпочтения**.
    
4. Выберите **включить экспертный интерфейс**.
    
5. In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host (Узел)**|**TTL (Срок жизни)**|**Type (Тип)**|**Data (Данные)**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |600  <br/> |MX  <br/> |10  *\<ключ_домена\>*  .mail.protection.outlook.com.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> **10**  значение приоритета MX. Добавьте его в начало значения MX, отделив от остальной части пробелом.  <br/> **Примечание:** Получите * \<ключ\> домена* из учетной записи Office 365.           [Как найти это значение?](../get-help-with-domains/information-for-dns-records.md)      <br>    Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).    <br/> |
   
    ![Дин — BP — configure – 2-1](../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. Выберите **создать запись**.
    
    ![Дин — BP — configure – 2-2](../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. Если существуют какие-либо другие записи MX, удалите их, установив флажок для каждого из них в столбце **Delete (удалить** ). 
    
    ![Дин — BP — configure – 2-3](../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. Выберите **Apply Changes (применить изменения**).
    
    ![Дин — BP — configure – 2-4](../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Добавление шести записей CNAME, необходимых для Office 365
<a name="BKMK_add_CNAME"> </a>

1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте Dyn.com по [этой ссылке](https://account.dyn.com/dns/). Сначала вам потребуется выполнить вход.
    
    ![Dyn-BP-Configure-1-1](../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. На странице " **службы уровня зоны** " выберите **Дин стандартная служба DNS** для домена, который требуется изменить. 
    
3. На странице **DNS** для вашего домена выберите **предпочтения**.
    
4. Выберите **включить экспертный интерфейс**.
    
5. Добавьте первую из шести записей CNAME.
    
    В поля для новой записи в разделе **Добавление DNS-записи** введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы. 
    
    В раскрывающемся списке выберите значение параметра **Type** (Тип). 
    
    |**Host (Узел)**|**TTL (Срок жизни)**|**Type (Тип)**|**Data (Данные)**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |600  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |sip  <br/> |600  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |lyncdiscover  <br/> |600  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseregistration  <br/> |600  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |
    |enterpriseenrollment  <br/> |600  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **This value MUST end with a period (.)** <br/> |
   
    ![Дин — BP — configure – 3-1](../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. Выберите **создать запись**.
    
    ![Дин — BP — configure – 3-2](../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. Добавьте оставшиеся пять записей CNAME.
    
    В разделе **Добавление записи DNS** создайте запись, используя значения из следующей строки таблицы, а затем еще раз выберите **создать запись** , чтобы завершить эту запись. 
    
    Повторяйте эти действия, пока не будут созданы все шесть записей CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Вместо этого добавьте необходимые значения Office 365 к текущей записи, чтобы иметь *одну* запись SPF, включающую оба набора значений.
  
1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте Dyn.com по [этой ссылке](https://account.dyn.com/dns/). Сначала вам потребуется выполнить вход.
    
    ![Dyn-BP-Configure-1-1](../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. На странице " **службы уровня зоны** " выберите **Дин стандартная служба DNS** для домена, который требуется изменить. 
    
3. На странице **DNS** для вашего домена выберите **предпочтения**.
    
4. Выберите **включить экспертный интерфейс**.
    
5. In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host (Узел)**|**TTL (Срок жизни)**|**Type (Тип)**|**Data (Данные)**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |600  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.               |
   
    ![Дин — BP — configure – 4-1](../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. Выберите **создать запись**.
    
    ![Дин — BP — configure – 4-2](../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Добавление двух записей SRV, необходимых для Office 365
<a name="BKMK_add_SRV"> </a>

1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте Dyn.com по [этой ссылке](https://account.dyn.com/dns/). Сначала вам будет предложено выполнить вход. 
    
    ![Dyn-BP-Configure-1-1](../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. На странице " **службы уровня зоны** " выберите **Дин стандартная служба DNS** для домена, который требуется изменить. 
    
3. На странице **DNS** для вашего домена выберите **предпочтения**.
    
4. Выберите **включить экспертный интерфейс**.
    
5. Добавьте первую из двух записей SRV.
    
    В поля для новой записи в разделе **Добавление DNS-записи** введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы. 
    
    В раскрывающемся списке выберите значение параметра **Type** (Тип). 
    
    |**Host (Узел)**|**TTL (Срок жизни)**|**Type (Тип)**|**Data (Данные)**|
    |:-----|:-----|:-----|:-----|
    |_sip. _tls|600|SRV|100 1 443 sipdir.online.lync.com. **This value MUST end with a period (.)**<br>**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.               |
    |_sipfederationtls. _tcp|600|SRV|100 1 5061 sipfed.online.lync.com. **This value MUST end with a period (.)**<br> **Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.               |
   
    ![Дин — BP — configure – 5-1](../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. Выберите **создать запись**.
    
    ![Дин — BP — configure – 5-2](../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. Добавьте вторую запись SRV.
    
    В разделе **Добавление записи DNS** создайте запись, используя значения из второй строки таблицы, а затем еще раз выберите **создать запись** , чтобы завершить эту запись. 
    
> [!NOTE]
>  Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
