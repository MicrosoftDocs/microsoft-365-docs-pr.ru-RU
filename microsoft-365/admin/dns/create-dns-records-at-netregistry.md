---
title: Создание записей DNS для Майкрософт на сайте Netregistry
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
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Netregistry for Microsoft.
ms.openlocfilehash: 857645c685cce946b39a7c3dcadb0a45b43686cf
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657807"
---
# <a name="create-dns-records-at-netregistry-for-microsoft"></a>Создание записей DNS для Майкрософт на сайте Netregistry

Если вы не нашли нужную информацию, см. статью [Вопросы и ответы о доменах](../setup/domains-faq.yml). 
  
Если ваш поставщик услуг размещения DNS  Netregistry, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб.
  
Ниже перечислены основные записи, которые нужно добавить.
  
- [Добавление записи TXT для проверки](#add-a-txt-record-for-verification)
    
- [Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)

- [Добавление записей CNAME, необходимых для продуктов корпорации Майкрософт](#add-the-cname-records-that-are-required-for-microsoft)
    
- [Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт](#add-the-two-srv-records-that-are-required-for-microsoft)
    
После добавления этих записей на сайте Netregistry ваш домен будет настроен для работы со службами Майкрософт.
  
  
> [!NOTE]
> Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Добавление записи TXT для проверки
<a name="bkmk_txt"> </a>

Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.
  
> [!NOTE]
> Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже. 
  
1. Чтобы приступить к работе, откройте страницу со своими доменами на веб-сайте Netregistry по [этой ссылке](https://theconsole.netregistry.com.au/). Вам потребуется выполнить вход.
    
    ![Netregistry_login](../../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. Рядом с нужным доменом щелкните ссылку **Manage** (Управление).
    
    ![Netregistry_Manage](../../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. Выберите пункт **Zone Manager** (Диспетчер зон).
    
    ![Netregistry_selectZoneManager](../../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. В **списке "Добавить запись зоны"** выберите запись **TXT,** а затем выберите **"Создать новую запись".**
    
    ![Netregistry_TXT_select](../../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > Необходимо использовать кавычках до и после записи в поле TXT. 
  
    В форме **New TXT Record** (Новая запись типа TXT) введите (или скопируйте и вставьте) значения из следующей таблицы: 
    
    |**Name (Имя)**|**TTL (SEC) (Срок жизни в секундах)**|**TXT (Адрес "указывает на" или значение)**|
    |:-----|:-----|:-----|
    |(оставьте пустым)  <br/> |3600 (секунд)  <br/> |"MS=msXXXXXXXXX"  <br/> **Примечание.** Это пример. Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы. [Как его найти?](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. Выберите **"Добавить запись"**.
    
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

1. Чтобы приступить к работе, откройте страницу со своими доменами на веб-сайте Netregistry по [этой ссылке](https://theconsole.netregistry.com.au/). Вам потребуется выполнить вход.
    
    ![Netregistry_login](../../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. Рядом с нужным доменом щелкните ссылку **Manage** (Управление).
    
    ![Netregistry_Manage](../../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. Выберите пункт **Zone Manager** (Диспетчер зон).
    
    ![Netregistry_selectZoneManager](../../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. В **записях текущей зоны** удалите записи  MX по умолчанию, выбрав "Удалить" рядом с каждой записью MX в списке. 
    
    ![Netregistry_MX_remove](../../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. В **списке "Добавить запись зоны"** выберите запись **MX,** а затем выберите **"Создать новую запись".**
    
    ![Netregistry_MX_select](../../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. В форме **"Новая запись MX"** введите (или скопируйте и введите) значения из таблицы ниже. 
    
    |**Name (Имя)**|**TTL (SEC) (Срок жизни в секундах)**|**Exchange (указывает на адрес или значение)**|**Является ли хост-диск полностью завершенным?**|**Приоритет (приоритет)**|
    |:-----|:-----|:-----|:-----|:-----|
    |(оставьте пустым)  <br/> |3600 (секунд)  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Примечание.** Получите свою  *\<domain-key\>*  учетную запись Майкрософт.  [Как его найти?](../get-help-with-domains/information-for-dns-records.md)      |(select the checkbox)  <br/> |10   <br/> For more information about priority, see What is MX priority?  <br/> |
       
    ![Netregistry_MX_values](../../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. Выберите команду **Add Record** (Добавить запись).
    
    ![Netregistry_MX_values_AddRecord](../../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Добавление записей CNAME, необходимых для продуктов корпорации Майкрософт
<a name="bkmk_cname"> </a>

1. Чтобы приступить к работе, откройте страницу со своими доменами на веб-сайте Netregistry по [этой ссылке](https://theconsole.netregistry.com.au/). Вам потребуется выполнить вход.
    
    ![Netregistry_login](../../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. Рядом с нужным доменом щелкните ссылку **Manage** (Управление).
    
    ![Netregistry_Manage](../../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. Выберите пункт **Zone Manager** (Диспетчер зон).
    
    ![Netregistry_selectZoneManager](../../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. В **списке "Добавить запись зоны"** выберите **запись CNAME,** а затем выберите **"Создать новую запись".**
    
    ![Netregistry_CNAME_CreateNewRecord](../../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.
    
    |**Имя**|**Type** (Тип)|**TTL** (Срок жизни)|**HOST (указывает на или значение адреса)**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |3600 (секунд)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |3600 (секунд)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |3600 (секунд)  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |3600 (секунд)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |3600 (секунд)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
       
    ![Netregistry_CNAME_values](../../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. Выберите **"Добавить запись"**.
    
    ![Netregistry_CNAME_values_AddRecord](../../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. Повторив эти действия, создайте пять других записей CNAME.
    
    Создайте пять других записей CNAME, как описано выше.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Добавление записи TXT для SPF, предотвращающей рассылку спама
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT. Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама. Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт. Вместо этого добавьте необходимые значения Майкрософт в текущую  запись, чтобы иметь одну запись SPF, которая включает оба набора значений.
  
1. Чтобы приступить к работе, откройте страницу со своими доменами на веб-сайте Netregistry по [этой ссылке](https://theconsole.netregistry.com.au/). Вам потребуется выполнить вход.
    
    ![Netregistry_login](../../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. Рядом с нужным доменом щелкните ссылку **Manage** (Управление).
    
    ![Netregistry_Manage](../../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. Выберите пункт **Zone Manager** (Диспетчер зон).
    
    ![Netregistry_selectZoneManager](../../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. В **списке "Добавить запись зоны"** выберите запись **TXT,** а затем выберите **"Создать новую запись".**
    
    ![Netregistry_TXT_select](../../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже. 
    
    > [!NOTE]
    > Необходимо использовать кавычках до и после записи в поле TXT. 
  
    |**Имя**|**Type** (Тип)|**TTL** (Срок жизни)|**TXT Data (Target)**|
    |:-----|:-----|:-----|:-----|
    |(оставьте пустым)  <br/> |TXT  <br/> |3600 (секунд)  <br/> |"v=spf1 include:spf.protection.outlook.com -all"  <br/> **Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.               |
   
    ![Netregistry_SPF-TXTvalues](../../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. Выберите команду **Add Record** (Добавить запись).
    
    ![Netregistry_SPF-TXTvalues_AddRecord](../../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт
<a name="bkmk_srv"> </a>

1. Чтобы приступить к работе, откройте страницу со своими доменами на веб-сайте Netregistry по [этой ссылке](https://theconsole.netregistry.com.au/). Вам потребуется выполнить вход.
    
    ![Netregistry_login](../../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. Рядом с доменом, который вы хотите управлять, выберите **"Управление".**
    
    ![Netregistry_Manage](../../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. Выберите пункт **Zone Manager** (Диспетчер зон).
    
    ![Netregistry_selectZoneManager](../../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. В **списке "Добавить запись зоны"** выберите **запись SRV,** а затем выберите **"Создать новую запись".**
    
    ![Netregistry_SRV_select](../../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.
    
    > [!NOTE]
    > Поле Name — это сочетание службы (например, _sip) и протокола (например, _tls). 
  
    |**Тип**|**Name (Имя)**|**TTL (SEC) (Срок жизни в секундах)**|**Priority** (Приоритет)|**Weight** (Вес)|**Port** (Порт)|**Target (Назначение)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (служба)  <br/> |_sip._tls  <br/> |3600 (секунд)  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |SRV (служба)  <br/> |_sipfederationtls._tcp  <br/> |3600 (секунд)  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
       
    ![Netregistry_SRV_values](../../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. Выберите команду **Add Record** (Добавить запись).
    
    ![Netregistry_SRV_values_AddRecord](../../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. Повторите эти действия для другой записи SRV.
    
    В поля для второй записи введите (или скопируйте и вставьте) значения из второй строки приведенной выше таблицы.
    
> [!NOTE]
> Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  

