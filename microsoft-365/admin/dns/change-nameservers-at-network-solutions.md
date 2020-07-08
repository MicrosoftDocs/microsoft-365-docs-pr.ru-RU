---
title: Изменение серверов доменных имен для настройки Microsoft с помощью сетевых решений
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
ms.assetid: d4ba60f3-4e1c-4180-99bd-250b8955be2a
description: 'Узнайте, как настроить личный домен Майкрософт с сетевыми решениями, если вы хотите, чтобы корпорация Майкрософт управляла своими записями DNS. '
ms.openlocfilehash: 502699cf3760460a13ee067b07737037f31fa4ee
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2020
ms.locfileid: "45079881"
---
# <a name="change-nameservers-to-set-up-microsoft-with-network-solutions"></a>Изменение серверов доменных имен для настройки Microsoft с помощью сетевых решений

 Если вы не нашли то, что вы ищете, обратитесь к разделу **[вопросы и ответы по доменам](../setup/domains-faq.md)**.
  
Если вы хотите, чтобы корпорация Майкрософт управляла своими записями DNS, следуйте приведенным ниже инструкциям. (При желании вы можете [управлять всеми своими записями DNS Microsoft в сетевых решениях](create-dns-records-at-network-solutions.md).)
  
    
## <a name="add-a-txt-record-at-network-solutions-to-verify-that-you-own-the-domain"></a>Добавление записи TXT на сайте Network Solutions для подтверждения права собственности на домен

Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 0:47)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261).
  
1. To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.
    
    > [!IMPORTANT]
    > Перед нажатием кнопки **Вход** сначала выберите пункт **Управление именами доменов** в раскрывающемся списке **Вход в:** .
  
    ![Выберите Manage My Domain Names (Управление доменными именами) и войдите в систему Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Установите флажок для доменного имени, которое вы хотите изменить.
    
    ![Установите флажок для своего домена](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Выберите **изменить DNS**.
    
    ![Выберите изменить DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Выберите **Управление расширенными записями DNS**.
    
    (You may have to scroll down.)
    
    ![Выберите Управление расширенными записями DNS](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Прокрутите список вниз до раздела **текст (записи TXT)** и выберите команду **изменить записи TXT**.
    
    ![Выберите команду Изменить записи TXT](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.
    
|**Host (Узел)**|**TTL (Срок жизни)**|**Text (Текст)**|
|:-----|:-----|:-----|
|@  <br/> (The system will change this value to **@ (None)** when you save the record.)  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> **Примечание**: это пример. Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Microsoft 365.           [Как его найти?](../get-help-with-domains/information-for-dns-records.md)
   
    
   ![Введите или вставьте значения в поля для новой записи](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. Нажмите кнопку **продолжить**.
    
    ![Нажмите кнопку продолжить.](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. Нажмите кнопку **сохранить изменения**.
    
    ![Нажмите кнопку Сохранить изменения](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.
    
Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Microsoft 365 и подайте запрос на ее поиск.
  
Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.
  
1. В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.

    
2. На странице **Domains** (Домены) выберите домен, который нужно проверить. 
    
    
  
3. На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).
    
    
  
4. На странице **Проверка домена** выберите **Проверить**.
    
    
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Изменение записей сервера доменных имен

Чтобы завершить настройку домена с помощью корпорации Майкрософт, измените записи NS своего домена в регистраторе доменных имен, чтобы они ссылались на основной и дополнительный серверы имен Майкрософт. Эта настройка позволяет настроить Microsoft для обновления записей DNS домена. Мы добавим все записи, так что электронная почта, Skype для бизнеса online и общедоступный веб-сайт будут работать в вашем домене и вам больше не придется ничего настраивать.
  
> [!CAUTION]
> Когда вы изменяете записи NS домена так, чтобы они ссылались на серверы имен Майкрософт, затрагиваются все службы, связанные с вашим доменом. Например, все сообщения электронной почты, отправленные в ваш домен (например, rob@ *your_domain* . com), появятся в корпорацию Майкрософт после внесения этого изменения.
  
Готовы изменить записи сервера доменных имен, чтобы корпорация Майкрософт могла настроить ваш домен? Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 2:23)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261).
  
> [!IMPORTANT]
>  После выполнения действий, описанных в этом разделе, *единственным* серверов доменных имен, которые должны быть указаны, являются следующие четыре: **NS1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**и **NS4.BDM.microsoftonline.com**. В приведенной ниже процедуре показано, как удалить из списка все остальные, нежелательные серверы имен, а также как добавить  *правильные*  серверы имен, если их еще нет в данном списке. 
  
1. Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Network Solutions по [этой ссылке](https://www.networksolutions.com/manage-it). Сначала вам потребуется выполнить вход.
    
    > [!IMPORTANT]
    > Перед нажатием кнопки **Вход** сначала выберите пункт **Управление именами доменов** в раскрывающемся списке **Вход в:** . 
  
    ![Выберите Manage My Domain Names (Управление доменными именами) и войдите в систему Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Установите флажок для доменного имени, которое вы хотите изменить.
    
    ![Установите флажок для своего домена](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Выберите **изменить DNS**.
    
    ![Выберите изменить DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Нажмите кнопку **Move DNS (переместить DNS**).
    
    ![Нетворксолутионсбп — redelegate — 1-1](../../media/e57a30f3-63d5-4bcb-84c6-c8be21c261a2.png)
  
5. В зависимости от того, указаны ли уже серверы доменных имен на странице, которая отображается на экране, воспользуйтесь одной из двух процедур.
    
  - Если на странице **НЕ УКАЗАНЫ** серверы доменных имен, [На странице НЕ УКАЗАНЫ серверы доменных имен](#if-there-are-no-nameservers-already-listed).
    
  - Если на странице **УКАЗАНЫ** серверы доменных имен, [На странице УКАЗАНЫ серверы доменных имен](#if-there-are-nameservers-already-listed).
    
### <a name="if-there-are-no-nameservers-already-listed"></a>На странице НЕ УКАЗАНЫ серверы доменных имен

1. На странице **домены** в разделе **укажите серверы доменных имен** выберите **Добавить серверы имен**.
    
    ![Нетворксолутионсбп — redelegate — 1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
2. На странице **Domain Names** (Доменные имена) введите (или скопируйте и вставьте) значения серверов из таблицы ниже. 
    
|||
|:-----|:-----|
|**Name Server 1** (Сервер доменных имен 1) <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2** (Сервер доменных имен 2) <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 2** (Сервер доменных имен 2) <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 2** (Сервер доменных имен 2) <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    
![Нетворксолутионсбп — redelegate — 1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
3. Нажмите кнопку **Move DNS (переместить DNS**).
    
    ![Нетворксолутионсбп — redelegate — 1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
4. Нажмите кнопку **сохранить изменения**.
    
    ![Нетворксолутионсбп — redelegate — 1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов. После этого ваша электронная почта Майкрософт и другие службы будут настроены для работы с вашим доменом. 
  
### <a name="if-there-are-nameservers-already-listed"></a>На странице УКАЗАНЫ серверы доменных имен

> [!CAUTION]
> Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)
  
1. Если на странице указаны другие серверы доменных имен, удалите их, выбирая каждый из них и нажимая клавишу **DELETE**.
    
    ![Нетворксолутионс — BP — redelegate — 1-5](../../media/eeb8ad22-bf4a-43a8-b97a-f09c3654d89b.png)
  
2. Выберите **добавить дополнительные серверы имен**.
    
    ![Нетворксолутионсбп — redelegate — 1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
3. На странице **Domain Names** (Доменные имена) введите (или скопируйте и вставьте) значения серверов из таблицы ниже. 
    
|||
|:-----|:-----|
|**Name Server 1** (Сервер доменных имен 1) <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2** (Сервер доменных имен 2) <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 3** (Сервер доменных имен 3) <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 4** (Сервер доменных имен 4) <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    
![Нетворксолутионсбп — redelegate — 1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
4. Нажмите кнопку **Move DNS (переместить DNS**).
    
    ![Нетворксолутионсбп — redelegate — 1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
5. Нажмите кнопку **сохранить изменения.**
    
    ![Нетворксолутионсбп — redelegate — 1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов. После этого ваша электронная почта Майкрософт и другие службы будут настроены для работы с вашим доменом.
