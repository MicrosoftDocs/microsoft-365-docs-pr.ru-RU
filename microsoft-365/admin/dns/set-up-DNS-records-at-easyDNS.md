---
title: Создание записей DNS на сайте easyDNS для Майкрософт
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу easyDNS для Майкрософт.
ms.openlocfilehash: 4909a02ec56fc9720a2636e822da0339e89bccf8
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645555"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a>Создание записей DNS на сайте easyDNS для Майкрософт

Если вы не нашли нужную информацию, см. статью [Вопросы и ответы о доменах](../setup/domains-faq.md). 
  
Вам потребуется добавить все следующие записи DNS на веб-сайте регистратора, чтобы маршрутизировать почту в корпорацию Майкрософт, использовать домен для Teams и Skype для бизнеса и т. д.
  
NOTE: записи SRV в настоящее время недоступны в пакетах службы easyDNS. Для добавления записей SRV, необходимых для Skype для бизнеса, вам может потребоваться выполнить обновление до более высокого уровня обслуживания с easyDNS.
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a>Проверка принадлежности домена к записи TXT

1. Перейдите на страницу [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) и войдите с помощью учетных данных. 
    
2. В заголовке **все домены** выберите **DNS.**
    
3. В разделе **txt Records (записи TXT** ) нажмите кнопку Edit (значок вренч). 
    
4. Введите в текстовые поля следующие записи:
    
    |**Host**|**Text**|
    |:-----|:-----|
    |@  <br/> |MS = Мскскскскскскскскс (используйте значение, указанное на странице "домены центра администрирования")  <br/> |
   
5. Нажмите кнопку **Далее**. 
    
6. Убедитесь, что запись верна, а затем нажмите кнопку **подтвердить**. 
    
7. Подождите несколько минут, прежде чем продолжить, чтобы созданная запись могла передаваться через Интернет и распознаются корпорацией Майкрософт.
    
8. Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.
    
9. В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).
    
10. На странице **Domains** (Домены) выберите домен, который нужно проверить. 
    
11. На странице **Настройка** выберите пункт **Запуск программы установки.**
    
12. На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить). 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a>Добавление записи MX для маршрутизации электронной почты в корпорацию Майкрософт

1. Перейдите на страницу [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) и войдите с помощью учетных данных. 
    
2. В заголовке **все домены** выберите **DNS.**
    
3. В заголовке **MX Record (запись MX** ) нажмите кнопку Edit (значок вренч). 
    
4. Введите в текстовые поля следующие записи:
    
    |**ПОЧТА ДЛЯ ЗОНЫ**|**ПОЧТОВЫЙ СЕРВЕР**|**преф**|
    |:-----|:-----|:-----|
    |@  <br/> |\<domain-key\>. mail.protection.outlook.com (получите \<domain-key\> значение на странице "домены центра администрирования")  <br/> |нуль  <br/> |
   
2. Если вы хотите сохранить другие записи MX для целей резервного копирования, скопируйте их в любое место. Перед перемещением удалите все остальные записи MX здесь.
    
5. Нажмите кнопку **Далее**. 
    
6. Убедитесь, что запись верна, а затем нажмите кнопку **подтвердить**. 
    
## <a name="add-the-required-cname-records"></a>Добавление необходимых записей CNAME

1. Перейдите на страницу [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) и войдите с помощью учетных данных. 
    
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
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Добавление записи TXT для SPF, предотвращающей рассылку спама

1. Перейдите на страницу [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) и войдите с помощью учетных данных. 
    
2. В заголовке **все домены** выберите **DNS.**
    
3. В разделе **txt Records (записи TXT** ) нажмите кнопку Edit (значок вренч). 
    
4. Введите в текстовые поля следующие записи:
    
    |**Host**|**Text**|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> |
   
5. Нажмите кнопку **Далее**. 
    
6. Убедитесь, что запись верна, а затем нажмите кнопку **подтвердить**. 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт

NOTE: записи SRV в настоящее время недоступны в easyDNS "домен и служба". Для добавления записей SRV может потребоваться выполнить обновление до более высокого уровня обслуживания с easyDNS 
  
1. Перейдите на страницу [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) и войдите с помощью учетных данных. 
    
2. В заголовке **все домены** выберите **DNS.**
    
3. В разделе **SRV Records (записи SRV** ) нажмите кнопку Edit (значок вренч). 
    
4. Введите в текстовые поля следующие записи:
    
    |**SERVICE (СЛУЖБА)**|**ЗАДАННОЕ**|**HOST (УЗЕЛ)**|**ОСНОВНОЙ**|**вгт**|**PORT (ПОРТ)**|**TARGET (должно оканчиваться на ".")**|**TTL (Срок жизни)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |TLS  <br/> |@  <br/> |100  <br/> |1,1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> |1800  <br/> |
    |_sipfederationtls  <br/> |TCP  <br/> |@  <br/> |100  <br/> |1,1  <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> |1800  <br/> |
   
5. Нажмите кнопку **Далее**. 
    
6. Убедитесь, что запись верна, а затем нажмите кнопку **подтвердить**. 
    

