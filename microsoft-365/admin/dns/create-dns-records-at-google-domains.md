---
title: Создание записей DNS для Майкрософт на сайте Google Domains
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Узнайте, как проверить свой домен и настроить записи DNS для электронной почты, Lync и других служб корпорации Майкрософт на сайте Google Domains.
ms.openlocfilehash: e6b1dd1eb90957a4e7fe22bd4b66ac87b2a51d09
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400453"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a>Создание записей DNS для Майкрософт на сайте Google Domains

 Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.md)**. 
  
Если ваш поставщик услуг размещения DNS — Google Domains, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Lync и других служб.
  
Когда вы добавите эти записи на сайте Google Domains, ваш домен будет настроен для работы со службами Майкрософт.
  

  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Тем не менее, иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение неполадок после добавления в Майкрософт домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Добавление записи TXT для проверки
<a name="BKMK_verify"> </a>

Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:
    
1. Нажмите **Sign In** (Войти).
    
2. Введите данные для входа и еще раз нажмите кнопку **Sign In** (Войти).
    
2. На странице **My domains** (Мои домены) выберите домен, который вы хотите использовать в Майкрософт, и щелкните ссылку **MANAGE** (УПРАВЛЕНИЕ) рядом с ним. В области навигации слева выберите **DNS**.
    
3. В разделе **Custom resource records** (Настраиваемые записи ресурсов) в полях для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже. 
    
    (Возможно, потребуется прокрутить страницу вниз.)
    
    В раскрывающемся списке выберите значение параметра **Type** (Тип). 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Имя** <br/> |**Type** (Тип) <br/> |**TTL** (Срок жизни) <br/> |**Data** (Данные) <br/> |
    |@  <br/> |TXT  <br/> |1H (1 ч)  <br/> |MS=ms *XXXXXXXX*  <br/> **Примечание.** Это пример. Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы. [Как его найти?](../get-help-with-domains/information-for-dns-records.md)          |
   
4. Нажмите кнопку **Add** (Добавить).
    
5. Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.
    
Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.
  
Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.
  
1. В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.

    
2. На странице **Domains** (Домены) выберите домен, который нужно проверить. 
    
3. На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).
    
4. На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md). 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.
<a name="BKMK_add_MX"> </a>

1. To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:
    
2. Нажмите **Sign In** (Войти).
    
3. Введите данные для входа и еще раз нажмите кнопку **Sign In** (Войти).
4. На странице **Domains** (Домены) в разделе **Domain** (Домен) выберите команду **Configure DNS** (Настроить DNS) для того домена, который вы хотите изменить.
    
    > [!IMPORTANT]
    > Если вы используете учетную запись электронной почты G Suite, сначала необходимо удалить записи MX, которые с ней связаны. Существующие записи MX для G Suite препятствуют добавлению каких-либо других записей MX, включая те, которые требуются для использования служб Майкрософт. Обратите внимание, что при удалении записей для G Suite учетная запись G Suite не удаляется. Чтобы удалить записи MX для G Suite, выполните указанные ниже действия. 
  
5. В разделе **Synthetic records** (Синтетические записи) в области **G Suite** нажмите кнопку **Delete** (Удалить).
    
    (Возможно, потребуется прокрутить страницу вниз.)
    
    ![Нажатие кнопки Delete (Удалить) в разделе Synthetic records (Синтетические записи)](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. Выберите **Delete** (Удалить).
    
    ![Выберите Delete (Удалить)](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. В разделе **Custom resource records** (Настраиваемые записи ресурсов) в полях для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже. 
    
    (Возможно, потребуется прокрутить страницу вниз.)
    
    В раскрывающемся списке выберите значение параметра **Type** (Тип). 
    
    |**Имя**|**Type** (Тип)|**TTL** (Срок жизни)|**Data** (Данные)|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1H (1 ч)  <br/> |0  *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  <br/> **Примечание.**  Получите свой \<*domain-key*\> из учетной записи Майкрософт.  [Как его найти?](../get-help-with-domains/information-for-dns-records.md)          Дополнительные сведения о приоритете см. в статье [Что такое приоритет записей MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> |
   
    ![Введите или вставьте значения в разделе Custom resource records (Настраиваемые записи ресурсов)](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. Нажмите кнопку **Add** (Добавить).
    
    ![Нажмите кнопку Add (Добавить)](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. Если есть другие настраиваемые записи MX, удалите их.
    
1. В строке записи MX нажмите **Edit** (Изменить). 
    
    ![В строке записи MX нажмите Edit (Изменить)](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. Для каждой из прочих настраиваемых записей MX выделите содержимое поля **Data** (Данные) и нажмите на клавиатуре клавишу **DELETE**, чтобы удалить его. 
    
    Повторяйте эти действия, чтобы удалить содержимое поля **Data** каждой из лишних записей MX. 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. Когда содержимое поля **Data** (Данные) каждой записи MX будет удалено, нажмите кнопку **Save** (Сохранить), чтобы сохранить изменения. 
    
    ![Нажмите Save (Сохранить)](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>Добавление пяти записей CNAME, необходимых для продуктов корпорации Майкрософт

1. Чтобы приступить к работе, перейдите на страницу [страница Google Domains] (https://domains.google.com/registrar) и выполните вход.
    
2. На странице **Domains** (Домены) в разделе **Domain** (Домен) выберите команду **Configure DNS** (Настроить DNS) для того домена, который вы хотите изменить. 
    
3. Добавьте первую запись CNAME.
    
    В разделе **Custom resource records** (Настраиваемые записи ресурсов) в полях для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы. 
    
    (Возможно, потребуется прокрутить страницу вниз.)
    
    В раскрывающемся списке выберите значение параметра **Type** (Тип). 
    
    |**Имя**|**Type** (Тип)|**TTL** (Срок жизни)|**Data** (Данные)|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |1H (1 ч)  <br/> |autodiscover.outlook.com.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |
    |sip  <br/> |CNAME  <br/> |1H (1 ч)  <br/> |sipdir.online.lync.com.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |1H (1 ч)  <br/> |webdir.online.lync.com.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |1H (1 ч)  <br/> |enterpriseregistration.windows.net.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |1H (1 ч)  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |
   
    ![Введите или вставьте значения в разделе Custom resource records (Настраиваемые записи ресурсов)](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. Нажмите кнопку **Add** (Добавить).
    
    ![Нажмите кнопку Add (Добавить)](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. Добавьте остальные четыре записи CNAME.
    
    В разделе **Custom resource records** (Настраиваемые записи ресурсов) создайте запись, используя значения из следующей строки таблицы, и снова нажмите **Add** (Добавить), чтобы завершить ввод этой записи. 
    
    Повторяйте эти действия, пока не будут созданы все требуемые записи CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама

> [!IMPORTANT]
> Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT. Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама. Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт. Вместо этого добавьте необходимые значения для продуктов корпорации Майкрософт в текущую запись. Таким образом, в одной записи SPF будут указаны оба набора значений. Нужны примеры? Ознакомьтесь с этими [записями системы внешних доменных имен для продуктов корпорации Майкрософт](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
1. To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:
    
1. Нажмите **Sign In** (Войти).
    
2. Введите данные для входа и еще раз нажмите кнопку **Sign In** (Войти).
    
3. На странице **Domains** (Домены) в разделе **Domain** (Домен) выберите команду **Configure DNS** (Настроить DNS) для того домена, который вы хотите изменить. 
    
4. В разделе **Custom resource records** (Настраиваемые записи ресурсов) в строке записи TXT нажмите кнопку **Edit** (Изменить). 
    
    > [!IMPORTANT]
    > Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message. 
  
    ![В строке записи TXT нажмите Edit (Изменить)](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. Щелкните элемент управления **(+)**. 
    
    ![Щелкните элемент управления "плюс"](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.
    
    (Возможно, потребуется прокрутить страницу вниз.)
    
    |**Данные**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> 

    > [!NOTE]
    > Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.           
   
   ![Введите или вставьте значения в разделе Custom resource records (Настраиваемые записи ресурсов)](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. Нажмите **Save** (Сохранить).
    
    ![Нажмите Save (Сохранить)](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт
<a name="BKMK_add_SRV"> </a>

1. To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:
    
2. Нажмите **Sign In** (Войти).
    
3. Введите данные для входа и еще раз нажмите кнопку **Sign In** (Войти).
    
4. На странице **Domains** (Домены) в разделе **Domain** (Домен) выберите команду **Configure DNS** (Настроить DNS) для того домена, который вы хотите изменить. 
    
5. Добавьте первую запись SRV.
    
    В разделе **Custom resource records** (Настраиваемые записи ресурсов) в полях для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже. 
    
    (Возможно, потребуется прокрутить страницу вниз.)
    
    В раскрывающемся списке выберите значение параметра **Type** (Тип). 
    
    |**Имя**|**Type** (Тип)|**TTL** (Срок жизни)|**Данные**|
    |:-----|:-----|:-----|:-----|
    |_sip._tls|SRV|1H (1 ч)|100 1 443 sipdir.online.lync.com. **Это значение ДОЛЖНО оканчиваться точкой (.).** **Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.           |
    |_sipfederationtls._tcp|SRV|1H (1 ч)|100 1 5061 sipfed.online.lync.com. **Это значение ДОЛЖНО оканчиваться точкой (.).**

    Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.       
   
    ![Введите или вставьте значения в разделе Custom resource records (Настраиваемые записи ресурсов)](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. Нажмите кнопку **Add** (Добавить).
    
    ![Нажмите кнопку Add (Добавить)](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. Добавьте вторую запись SRV.
    
    В разделе **Custom resource records** (Настраиваемые записи ресурсов) создайте запись, используя значения из второй строки таблицы, и снова нажмите **Add** (Добавить), чтобы завершить ввод этой записи. 
    
    > [!NOTE]
    > Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
