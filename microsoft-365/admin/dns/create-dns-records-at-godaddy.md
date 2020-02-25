---
title: Создание записей DNS на веб-сайте GoDaddy для Office 365
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
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу GoDaddy для Office 365.
ms.custom: okr_smb
ms.openlocfilehash: 4a67ef090c2b91c4cf1fdde376ab35e3a4ed4e20
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42245372"
---
# <a name="create-dns-records-at-godaddy-for-office-365"></a>Создание записей DNS на веб-сайте GoDaddy для Office 365

 **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.

Если ваш поставщик услуг размещения DNS  GoDaddy, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.

Когда вы добавите эти записи на сайте GoDaddy, ваш домен будет настроен для работы со службами Office 365.

Дополнительные сведения о веб-хостинге и DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).

> [!NOTE]
> Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-a-txt-record-for-verification"></a>Добавление записи TXT для проверки
<a name="BKMK_verify"> </a>

Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете данным доменом.

> [!NOTE]
> Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.

Выполните указанные ниже действия.

1. Чтобы приступить к работе, перейдите на свою страницу доменов на сайте GoDaddy по [этой ссылке](https://account.godaddy.com/products/?go_redirect=disabled). Сперва вам потребуется выполнить вход.

    ![GoDaddy — BP — configure – 1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. В разделе **домены**выберите DNS в домене, который требуется изменить.

    ![GoDaddy — BP — configure – 1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Нажмите кнопку **Добавить**.

    ![GoDaddy — BP — configure – 1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. В раскрывающемся списке выберите значение **TXT (Text)** (Текст). In the boxes for the new record, type or copy and paste the values from the following table.

    |**Record Type (Тип записи)** |**Host (Узел)**|**TXT Value (Значение TXT)**|**TTL (Срок жизни)** |
    |:-----|:-----|:-----|:-----|
    |TXT (Text) (TXT (Текст))|@|MS=ms *XXXXXXXX*<br>**Примечание**: это пример. Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365. [Как найти это значение?](../get-help-with-domains/information-for-dns-records.md)|1 час  <br>(Выберите значение из раскрывающегося списка.)|

      ![GoDaddy — BP — Verify – 1-0](../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. Нажмите кнопку **Сохранить**.

6. Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.

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

Выполните указанные ниже действия.

1. Чтобы приступить к работе, перейдите на свою страницу доменов на сайте GoDaddy по [этой ссылке](https://account.godaddy.com/products/?go_redirect=disabled). Сперва вам потребуется выполнить вход.

    ![GoDaddy — BP — configure – 1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. В разделе **домены**выберите DNS в домене, который требуется изменить.

    ![GoDaddy — BP — configure – 1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Нажмите кнопку **Добавить**.

    ![GoDaddy — BP — configure – 1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. В раскрывающемся списке выберите значение **MX (Mail Exchanger)** (почтовый обменник).

    ![GoDaddy — BP — configure – 2-0](../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.

    В раскрывающемся списке выберите значение **TTL (срок жизни** ).

    |**Record Type (Тип записи)**|**Host (Узел)**|**Points to (Указывает на)**|**Priority (Приоритет)**|**TTL** (Срок жизни)|
    |:-----|:-----|:-----|:-----|:-----|
    |MX (Mail Exchanger) (Почтовый обменник)  <br/> |@  <br/> | *\<ключ_домена\>*  .mail.protection.outlook.com  <br/> **Примечание:** Получите * \<ключ\> домена* из учетной записи Office 365.           [Где это находится?](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).    <br/> |1 hour  <br/> |

6. Нажмите кнопку **Сохранить**.

## <a name="add-the-cname-records-that-are-required-for-office-365"></a>Добавление записей CNAME, необходимых для Office 365
<a name="BKMK_add_CNAME"> </a>

Выполните указанные ниже действия.

1. Чтобы приступить к работе, перейдите на свою страницу доменов на сайте GoDaddy по [этой ссылке](https://account.godaddy.com/products/?go_redirect=disabled). Сперва вам потребуется выполнить вход.

    ![GoDaddy — BP — configure – 1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. В разделе **домены**выберите DNS в домене, который требуется изменить.

    ![GoDaddy — BP — configure – 1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Нажмите кнопку **Добавить**.

    ![GoDaddy — BP — configure – 1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. В раскрывающемся списке выберите значение **CNAME (Alias)** (Псевдоним CNAME).

    ![GoDaddy — BP — configure – 3-0](../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. Создайте первую запись CNAME.

    В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.

    В раскрывающемся списке выберите значение **TTL (срок жизни** ).

    |**Record Type (Тип записи)**|**Host (Узел)**|**Points to (Указывает на)**|**TTL (Срок жизни)**|
    |:-----|:-----|:-----|:-----|
    |CNAME (Alias)  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 hour  <br/> |
    |CNAME (Alias)  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |1 час  <br/> |
    |CNAME (Alias)  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |1 час  <br/> |
    |CNAME (Alias)  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 час  <br/> |
    |CNAME (Alias)  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |1 hour  <br/> |



6. Повторите эти действия, чтобы добавить следующую запись CNAME, пока не будут созданы все шесть записей CNAME.

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Вместо этого добавьте необходимые значения Office 365 к текущей записи, чтобы иметь *одну* запись SPF, включающую оба набора значений.

Выполните указанные ниже действия.

1. Чтобы приступить к работе, перейдите на свою страницу доменов на сайте GoDaddy по [этой ссылке](https://account.godaddy.com/products/?go_redirect=disabled). Сперва вам потребуется выполнить вход.

    ![GoDaddy — BP — configure – 1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. В разделе **домены**выберите DNS в домене, который требуется изменить.

    ![GoDaddy — BP — configure – 1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Нажмите кнопку **Добавить**.

    ![GoDaddy — BP — configure – 1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. В раскрывающемся списке выберите значение **TXT (Text)** (Текст).

    ![GoDaddy — BP — configure – 4-0](../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. В поля для новой записи введите (или скопируйте и вставьте) указанные ниже значения.

    (Выберите значение **TTL** в раскрывающихся списках.)

    |**Record Type (Тип записи)**|**Host (Узел)**|**TXT Value (Значение TXT)**|**TTL (Срок жизни)**|
    |:-----|:-----|:-----|:-----|
    |TXT (Text) (TXT (Текст))  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.               |1 hour  <br/> |

    ![GoDaddy — BP — configure – 4-1](../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. Нажмите кнопку **Сохранить**.


## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Добавление двух записей SRV, необходимых для Office 365
<a name="BKMK_add_SRV"> </a>

Выполните указанные ниже действия.

1. Чтобы приступить к работе, перейдите на свою страницу доменов на сайте GoDaddy по [этой ссылке](https://account.godaddy.com/products/?go_redirect=disabled). Сперва вам потребуется выполнить вход.

    ![GoDaddy — BP — configure – 1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. В разделе **домены**выберите DNS в домене, который требуется изменить.

    ![GoDaddy — BP — configure – 1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Нажмите кнопку **Добавить**.

    ![GoDaddy — BP — configure – 1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. В раскрывающемся списке выберите значение **SRV (Service)** (Служба).

    ![GoDaddy — BP — configure – 5-0](../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. Создайте первую запись SRV.

    В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.

    В раскрывающихся списках выберите **тип записи** и значения **срока жизни (TTL** ).

    |**Record Type (Тип записи)**|**Имя**|**Target**|**Протокол**|**Служба**|**Priority (Приоритет)**|**Weight (Вес)**|**Port (Порт)**|**TTL (Срок жизни)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (Service)  <br/> |@  <br/> |sipdir.online.lync.com  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1,1  <br/> |443  <br/> |1 час  <br/> |
    |SRV (Service)  <br/> |@  <br/> |sipfed.online.lync.com  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1,1  <br/> |5061  <br/> |1 час  <br/> |

    ![GoDaddy — BP — configure – 5-1](../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. Повторите **Шаг 5** , чтобы создать другую запись SRV.

7. Нажмите кнопку **Сохранить**.

> [!NOTE]
> Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).
