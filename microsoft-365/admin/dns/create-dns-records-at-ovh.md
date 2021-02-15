---
title: Создание записей DNS для Майкрософт на сайте OVH
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at OVH for Microsoft.
ms.openlocfilehash: 14c3796ff6686ae0d98ec32ec6ddf6afc004a3c3
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657783"
---
# <a name="create-dns-records-at-ovh-for-microsoft"></a>Создание записей DNS для Майкрософт на сайте OVH

Если вы не нашли нужную информацию, см. [вопросы и ответы по доменам](../setup/domains-faq.yml). 
  
Если ваш поставщик услуг размещения DNS  OVH, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб.
  
Ниже перечислены основные записи, которые нужно добавить. 
  
- [Создание записей DNS для Майкрософт на сайте OVH](#create-dns-records-at-ovh-for-microsoft)
    
- [Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Добавление записей CNAME, необходимых для продуктов корпорации Майкрософт](#add-the-cname-records-that-are-required-for-microsoft)
    
- [Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт](#add-the-two-srv-records-that-are-required-for-microsoft)
    
После добавления этих записей на сайте OVH ваш домен будет настроен для работы со службами Майкрософт.

  
> [!NOTE]
>  Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Добавление записи TXT для проверки
<a name="bkmk_txt"> </a>

Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.
  
> [!NOTE]
> Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже. 
  
1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте OVH по [этой ссылке](https://www.ovh.com/manager/). Вам потребуется выполнить вход.
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. В **области "Домены"** выберите имя домена, который нужно изменить.
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Выберите **зону DNS.**
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Выберите **"Добавить запись".**
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Select **TXT**
    
    ![OVH select TXT entry](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже. Чтобы назначить значение TTL, выберите **"Персонализированное"** в выпадаемом списке и введите значение в текстовом поле. 
    
    |**Record Type (Тип записи)**|**Sub-domain (Поддомен)**|**TTL**|**Значение**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |(оставьте пустым)  <br/> |3600 (секунд)  <br/> |MS=msxxxxxxxx  <br/> **Примечание.** Это пример. Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.           [Как его найти?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Выберите **Подтвердить**. 
    
    ![OVH confirm TXT for verification](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.
    
Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.
  
Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.
  
1. В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).
    
2. На странице **Domains** (Домены) выберите домен, который нужно проверить. 
    
    
  
3. На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).
    
    
  
4. На странице **Проверка домена** выберите **Проверить**.
    
    
  
> [!NOTE]
>  Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.
<a name="bkmk_mx"> </a>

1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте OVH по [этой ссылке](https://www.ovh.com/manager/). Вам потребуется выполнить вход.
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. В **области "Домены"** выберите имя домена, который нужно изменить.
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Выберите **зону DNS.**
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Выберите **"Добавить запись".**
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Выберите **MX**.
    
    ![OVH MX record type](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. In the boxes for the new record, type or copy and paste the values from the following table. Чтобы назначить значение TTL, выберите **"Персонализированное"** в выпадаемом списке и введите значение в текстовом поле. 
    
    > [!NOTE]
    > По умолчанию OVH использует относительную нотацию для целевого значения, которая добавляет доменное имя в конец целевой записи. Чтобы назначить значение TTL, выберите Personalized (Другое) из раскрывающегося списка, а затем введите значение в текстовом поле. 
  
    |**Примечание.** По умолчанию в OVH используется относительная нотация, при которой в конец целевой записи добавляется доменное имя. Чтобы использовать абсолютную нотацию, добавьте точку в целевую запись, как показано в таблице ниже.|**Sub-domain (Поддомен)**|**Sub-domain (Поддомен)**|**TTL**|**Priority (Приоритет)**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |(оставьте пустым)  <br/> |(Оставьте пустым)  <br/> |10   <br/> Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).    <br/> |\<domain-key\>.mail.protection.outlook.com.  <br/> **Примечание.** Получите свою  *\<domain-key\>*  учетную запись Майкрософт.  [Как его найти?](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![Запись MX OVH для почты](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. Нажмите кнопку **Далее**.
    
    ![OVH MX record select Next](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. Выберите **Подтвердить**.
    
    ![OVH MX record select Confirm](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. If there are any other MX records, delete them all in the list on the **DNS zone** page. Выберите каждую запись, а затем в столбце **"Действия"** выберите значок корзины **"Удалить".** 
    
    ![OVH delete MX record](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. Выберите **Подтвердить**.
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Добавление записей CNAME, необходимых для продуктов корпорации Майкрософт
<a name="bkmk_cname"> </a>

1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте OVH по [этой ссылке](https://www.ovh.com/manager/). Вам потребуется выполнить вход.
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. В **области "Домены"** выберите имя домена, который нужно изменить.
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Выберите **зону DNS.**
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Выберите **"Добавить запись".**
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Выберите **CNAME**.
    
    ![OVH add CNAME record type](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. OVH add CNAME record type
    
    В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки таблицы ниже. Чтобы назначить значение TTL, выберите **"Персонализированное"** в выпадаемом списке и введите значение в текстовом поле. 
    
    |**Record Type (Тип записи)**|**Record Type (Тип записи)**|**Sub-domain (Поддомен)**|**TTL (Срок жизни)**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com.  <br/> |autodiscover.outlook.com.  <br/> |
    |3600 секунд  <br/> |sip  <br/> |sipdir.online.lync.com.  <br/> |sipdir.online.lync.com.  <br/> |
    |3600 секунд  <br/> |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> |webdir.online.lync.com.  <br/> |
    |3600 секунд  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> |enterpriseregistration.windows.net.  <br/> |
    |3600 секунд  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> |enterpriseenrollment.manage.microsoft.com.  <br/> |
   
    ![Запись CNAME OVH](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. Нажмите кнопку **Далее**.
    
    ![OVH Add CNAME values and select Next](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. Выберите **Подтвердить**.
    
9. Повторив эти действия, создайте пять других записей CNAME.
    
    Создайте пять других записей CNAME, как описано выше.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Добавление записи TXT для SPF, предотвращающей рассылку спама
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT. Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама. Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт. Вместо этого добавьте необходимые значения Майкрософт в текущую  запись, чтобы иметь одну запись SPF, которая включает оба набора значений. 
  
1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте OVH по [этой ссылке](https://www.ovh.com/manager/). Вам потребуется выполнить вход.
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. В **области "Домены"** выберите имя домена, который нужно изменить.
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Выберите **зону DNS.**
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Выберите **"Добавить запись".**
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Выберите **TXT**.
    
6. In the boxes for the new record, type or copy and paste the following values.
    
    |**Record type**|**Sub-domain (Поддомен)**|**Sub-domain (Поддомен)**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |(оставьте пустым)  <br/> |3600 (секунд)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.               |
   
    ![OVH Add TXT record for SPF](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. Нажмите кнопку **Далее**.
    
    ![OVH Add TXT record for SPF and select Next](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. Выберите **Подтвердить**.
    
    ![OVH Add TXT record for SPF and Confirm](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт
<a name="bkmk_srv"> </a>

1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте OVH по [этой ссылке](https://www.ovh.com/manager/). Вам потребуется выполнить вход.
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. В **области "Домены"** выберите имя домена, который нужно изменить.
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Выберите **зону DNS.**
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Выберите **"Добавить запись".**
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Выберите **SRV.**
    
    ![OVH select SRV record type](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. Создайте первую запись SRV.
    
    В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы. Чтобы назначить значение TTL, выберите **"Персонализированное"** в выпадаемом списке и введите значение в текстовом поле. 
    
    |**Record Type (Тип записи)**|**Sub-domain (Поддомен)**|**Priority** (Приоритет)|**Weight** (Вес)|**Port** (Порт)|**TTL** (Срок жизни)|**Target (Назначение)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (Service)  <br/> |_sip._tls  <br/> |100  <br/> |1   <br/> |443  <br/> |3600 (секунд)  <br/> |sipdir.online.lync.com.  <br/> |
    |SRV (Service)  <br/> |_sipfederationtls._tcp  <br/> |100  <br/> |1   <br/> |5061  <br/> |3600 (секунд)  <br/> |sipfed.online.lync.com.  <br/> |
       
    ![Запись OVH SRV](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. Нажмите кнопку **Далее**.
    
    ![OVH SRV record select Next](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. Выберите **Подтвердить**.
    
9. Повторите эти действия для другой записи SRV. В поля для второй записи введите (или скопируйте и вставьте) значения из второй строки приведенной выше таблицы.
    
> [!NOTE]
>  Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
