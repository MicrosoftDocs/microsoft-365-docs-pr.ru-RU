---
title: Создание записей DNS для Office 365 в easyDNS
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу easyDNS для Office 365.
ms.openlocfilehash: f55f39f36b8abaee2d500c87ccf1e0089caecc9d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255370"
---
# <a name="create-dns-records-at-easydns-for-office-365"></a>Создание записей DNS для Office 365 в easyDNS

Если вы не нашли нужную информацию, см. статью [Вопросы и ответы о доменах](../setup/domains-faq.md). 
  
Вам потребуется добавить все указанные ниже записи DNS на веб-сайте регистратора для маршрутизации почты в Office 365, использовать домен для Teams и Skype для бизнеса и т. д.
  
NOTE: записи SRV в настоящее время недоступны в пакетах службы easyDNS. Для добавления записей SRV, необходимых для Office 365 Skype для бизнеса, вам может потребоваться выполнить обновление до более высокого уровня обслуживания с easyDNS.
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a>Проверка принадлежности домена к записи TXT

1. Перейдите на [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) страницу и войдите с помощью учетных данных. 
    
2. В заголовке **все домены** выберите **DNS.**
    
3. В разделе **txt Records (записи TXT** ) нажмите кнопку Edit (значок вренч). 
    
4. Введите в текстовые поля следующие записи:
    
    |**Host (Узел)**|**Text**|
    |:-----|:-----|
    |@  <br/> |MS = Мскскскскскскскскс (используйте значение, указанное на странице "домены центра администрирования")  <br/> |
   
5. Нажмите кнопку **Далее**. 
    
6. Убедитесь, что запись верна, а затем нажмите кнопку **подтвердить**. 
    
7. Подождите несколько минут, прежде чем продолжить, чтобы созданная запись могла быть передана через Интернет и обнаружена в Office 365.
    
8. Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
    
9. В центре администрирования перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> **параметров** \> ".
    
10. На странице **Domains (домены** ) выберите домен, который вы хотите проверить. 
    
11. На странице **Настройка** выберите пункт **Запуск программы установки.**
    
12. На странице **Проверка домена** нажмите кнопку **проверить**. 
    
## <a name="add-an-mx-record-to-route-email-to-office-365"></a>Добавление записи MX для маршрутизации электронной почты в Office 365

1. Перейдите на [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) страницу и войдите с помощью учетных данных. 
    
2. В заголовке **все домены** выберите **DNS.**
    
3. В заголовке **MX Record (запись MX** ) нажмите кнопку Edit (значок вренч). 
    
4. Введите в текстовые поля следующие записи:
    
    |**ПОЧТА ДЛЯ ЗОНЫ**|**ПОЧТОВЫЙ СЕРВЕР**|**преф**|
    |:-----|:-----|:-----|
    |@  <br/> |\<Domain-key\>. mail.Protection.Outlook.com (получение значения \<ключа\> домена из страницы "домены центра администрирования")  <br/> |нуль  <br/> |
   
2. Если вы хотите сохранить другие записи MX для целей резервного копирования, скопируйте их в любое место. Перед перемещением удалите все остальные записи MX здесь.
    
5. Нажмите кнопку **Далее**. 
    
6. Убедитесь, что запись верна, а затем нажмите кнопку **подтвердить**. 
    
## <a name="add-the-required-cname-records"></a>Добавление необходимых записей CNAME

1. Перейдите на [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) страницу и войдите с помощью учетных данных. 
    
2. В заголовке **все домены** выберите **DNS.**
    
3. В разделе **записи CNAME/Alias** нажмите кнопку Изменить (значок вренч). 
    
4. Введите в текстовые поля следующие записи:


    |**HOST (УЗЕЛ)**|**Address (должен заканчиваться на ".")**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com.  <br/> |
    |sip  <br/> |sipdir.online.lync.com.  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> |
   
5. Нажмите кнопку **Далее**. 
    
6. Убедитесь, что запись верна, а затем нажмите кнопку **подтвердить**. 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты

1. Перейдите на [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) страницу и войдите с помощью учетных данных. 
    
2. В заголовке **все домены** выберите **DNS.**
    
3. В разделе **txt Records (записи TXT** ) нажмите кнопку Edit (значок вренч). 
    
4. Введите в текстовые поля следующие записи:
    
    |**Host (Узел)**|**Text**|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> |
   
5. Нажмите кнопку **Далее**. 
    
6. Убедитесь, что запись верна, а затем нажмите кнопку **подтвердить**. 
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Добавьте две записи SRV, необходимые для Office 365

NOTE: записи SRV в настоящее время недоступны в easyDNS "домен и служба". Для добавления записей SRV может потребоваться выполнить обновление до более высокого уровня обслуживания с easyDNS 
  
1. Перейдите на [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) страницу и войдите с помощью учетных данных. 
    
2. В заголовке **все домены** выберите **DNS.**
    
3. В разделе **SRV Records (записи SRV** ) нажмите кнопку Edit (значок вренч). 
    
4. Введите в текстовые поля следующие записи:
    
    |**SERVICE (СЛУЖБА)**|**ЗАДАННОЕ**|**HOST (УЗЕЛ)**|**ОСНОВНОЙ**|**вгт**|**PORT (ПОРТ)**|**TARGET (должно оканчиваться на ".")**|**TTL (Срок жизни)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |TLS  <br/> |@  <br/> |100  <br/> |1,1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> |1800  <br/> |
    |_sipfederationtls  <br/> |TCP  <br/> |@  <br/> |100  <br/> |1,1  <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> |1800  <br/> |
   
5. Нажмите кнопку **Далее**. 
    
6. Убедитесь, что запись верна, а затем нажмите кнопку **подтвердить**. 
    

