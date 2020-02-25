---
title: Изменение серверов доменных имен для настройки Office 365 у регистратора MyDomain
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
ms.assetid: c5f6140a-4a12-401b-9bbd-7dfb0d6b0ba3
description: Узнайте, как настроить Office 365 для управления записями DNS в пользовательском домене на MyDomain.
ms.openlocfilehash: 05681fb48cc4c06aa44421029739a71ef6e59871
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42246623"
---
# <a name="change-nameservers-to-set-up-office-365-with-mydomain"></a>Изменение серверов доменных имен для настройки Office 365 у регистратора MyDomain

 **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.
  
Следуя этим инструкциям, вы можете передать управление своими записями DNS для Office 365 в Office 365. (При желании вы можете самостоятельно [управлять всеми своими записями DNS для Office 365 на сайте MyDomain](create-dns-records-at-mydomain.md).)
  
## <a name="add-a-txt-record-for-verification"></a>Добавление записи TXT для проверки

Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете данным доменом.
  
> [!NOTE]
> Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже. 
  
1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте MyDomain по предоставленной ссылке. Сначала вам потребуется [выполнить вход](https://www.mydomain.com/controlpanel).
    
2. В разделе **Мое избранное** выберите пункт **домен в центре**.
    
3. В разделе **Domain (домен**) выберите имя домена, который требуется изменить.
    
4. В строке **Обзор** выберите **DNS**.
    
5. From the **Modify** drop-down list, choose **TXT/SPF Record**.
    
6. Under **Content**, in the box for the new record, type or copy and paste the value from the following table.
    
||
|:-----|
|**Content (Контент)** <br/> |
|MS=ms *XXXXXXXX*  <br/> **Примечание**: это пример. Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365. [Как найти это значение?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Нажмите кнопку **Добавить**.
    
8. Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. В центре администрирования перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> **параметров** \> ".

    
2. На странице **Domains (домены** ) выберите домен, который вы хотите проверить. 
    
3. На странице **Настройка** выберите пункт **Запуск программы установки**.
    
4. На странице **Проверка домена** нажмите кнопку **проверить**.
    
> [!NOTE]
> Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Изменение записей сервера доменных имен

Чтобы завершить настройку домена для использования в Office 365, измените для него записи серверов имен на сайте вашего регистратора доменных имен таким образом, чтобы они указывали на основной и дополнительный DNS-серверы Office 365. После этого Office 365 обновит записи DNS для вашего домена. Мы добавим все записи, так что электронная почта, Skype для бизнеса online и общедоступный веб-сайт будут работать в вашем домене и вам больше не придется ничего настраивать.
  
> [!CAUTION]
> Когда вы изменяете записи серверов имен своего домена, чтобы они указывали на DNS-серверы Office 365, это оказывает влияние на все службы, которые в настоящий момент связаны с доменом. Например, все сообщения электронной почты, отправленные в ваш домен (например, rob@ *your_domain.* com) будет начинаться с Office 365 после внесения этого изменения. 
  
> [!IMPORTANT]
> В приведенной ниже процедуре показано, как удалить из списка все остальные, нежелательные серверы имен, а также как добавить правильные серверы имен, если их еще нет в данном списке.<br/> When you have completed the steps in this section, the only nameservers that should be listed are these four:
  
1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте MyDomain по предоставленной ссылке. Сначала вам потребуется выполнить вход.
    
2. В разделе **Мое избранное** выберите пункт **домен в центре**.
    
3. В разделе **Domain (домен**) выберите имя домена, который требуется изменить.
    
4. В строке **Overview (обзор** ) выберите **серверов доменных имен**.
    
    ![MyDomain — BP — redelegate — 1-1](../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. В разделе **Update Name Servers** (Обновление серверов доменных имен) выберите **Use different name servers** (Использовать другие серверы доменных имен).
    
    ![MyDomain — BP — redelegate — 1-2-1](../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. В зависимости от того, есть ли у вас уже серверов доменных имен на отображаемой странице, перейдите к одной из двух указанных ниже процедур.
    
### <a name="if-the-correct-nameservers-are-already-listed"></a>Если указаны правильные серверы доменных имен

- Если правильные серверы доменных имен уже указаны, пропустите этот шаг.
    
    ![MyDomain — BP — redelegate — 1-2-2](../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a>Если правильные серверы доменных имен не указаны

> [!CAUTION]
> Follow these steps only if you have existing nameservers other than the four correct nameservers. (То есть удалите только те текущие серверов доменных имен, которые *не* называются **NS1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**или **NS4.BDM.microsoftonline.com**.) 
  
1. Удалите существующие серверы доменных имен, выбирая соответствующие записи в поле **Nameserver:** (Сервер доменных имен:) и нажимая на клавиатуре клавишу **DELETE**. 
    
    ![MyDomain — BP — redelegate — 1-3-1](../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. Дважды нажмите кнопку **Добавить** , чтобы добавить две новые строки серверов доменных имен. 
    
    ![MyDomain — BP — redelegate — 1-3-2](../media/19307893-2f73-4e4d-9221-a5870e09ab48.png)
  
3. В поля для записей введите (или скопируйте и вставьте) значения для серверов доменных имен из таблицы ниже.
    
|||
|:-----|:-----|
|**Nameserver 1** (Сервер доменных имен 1) <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Nameserver 2** (Сервер доменных имен 2) <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Nameserver 3** (Сервер доменных имен 3) <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Nameserver 4** (Сервер доменных имен 4) <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![MyDomain — BP — redelegate — 1-4](../media/7427e99c-49c7-4a2e-a5bf-66fc46900cd1.png)
  
4. Нажмите кнопку **Сохранить**.
    
    ![MyDomain — BP — redelegate — 1-5](../media/48473816-b881-47f0-9344-74622efa3bf8.png)
  
> [!NOTE]
> На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов. После этого ваша электронная почта и все остальные службы Office 365 будут настроены на работу с новым доменом. 
