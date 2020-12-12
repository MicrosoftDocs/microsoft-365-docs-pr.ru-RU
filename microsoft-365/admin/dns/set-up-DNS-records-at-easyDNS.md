---
title: Создание записей DNS для Майкрософт на сайте easyDNS
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
description: Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at easyDNS for Microsoft.
ms.openlocfilehash: a971a722f071ef5df9ce0fba387cfacfeb409f5b
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656823"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a>Создание записей DNS для Майкрософт на сайте easyDNS

Если вы не нашли нужную информацию, см. статью [Вопросы и ответы о доменах](../setup/domains-faq.yml). 
  
Вам потребуется добавить все следующие записи DNS на веб-сайте регистратора, чтобы маршрутировать почту в Корпорацию Майкрософт, использовать свой домен для Teams и Skype для бизнеса и так далее.
  
ПРИМЕЧАНИЕ. В настоящее время записи SRV доступны НЕ во всех пакетах службы EasyDNS. Может потребоваться обновление до более высокого уровня обслуживания с помощью easyDNS, чтобы добавить записи SRV, необходимые для Skype для бизнеса.
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a>Проверка владения доменом с записью TXT

1. Войдите [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) в систему с помощью своих учетных данных. 
    
2. Под **заголовком "Все домены"** выберите **DNS.**
    
3. Под **заголовком записей TXT** выберите кнопку редактирования (значок wrench). 
    
4. Введите следующие записи в текстовые поля:
    
    |**Host**|**Text**|
    |:-----|:-----|
    |@  <br/> |MS=msXXXXXXXXXX (используйте значение, предоставленное на странице "Домены Центра администрирования")  <br/> |
   
5. Выберите **"ДАЛЕе".** 
    
6. Проверьте правильность записи и выберите **"ПОДТВЕРДИТЬ".** 
    
7. Подождите несколько минут, прежде чем продолжить, чтобы созданная вами запись распространялась по Интернету и обнаруживалась корпорацией Майкрософт.
    
8. Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.
    
9. В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).
    
10. На странице **Domains** (Домены) выберите домен, который нужно проверить. 
    
11. На странице **"Установка"** выберите **"Начать установку".**
    
12. На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить). 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a>Добавление записи MX для маршрутки электронной почты в корпорацию Майкрософт

1. Войдите [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) в систему с помощью своих учетных данных. 
    
2. Под **заголовком "Все домены"** выберите **DNS.**
    
3. Под **заголовком записей MX** выберите кнопку редактирования (значок wrench). 
    
4. Введите следующие записи в текстовые поля:
    
    |**ПОЧТА ДЛЯ ЗОНЫ**|**ПОЧТОВЫЙ СЕРВЕР**|**PREF**|
    |:-----|:-----|:-----|
    |@  <br/> |\<domain-key\>.mail.protection.outlook.com (Получите \<domain-key\> значение со страницы "Домены Центра администрирования")  <br/> |0  <br/> |
   
2. Если вы хотите сохранить другие записи MX для резервного копирования, скопируйте их в другое место. Прежде чем двигаться дальше, удалите здесь все остальные записи MX.
    
5. Выберите **"ДАЛЕе".** 
    
6. Проверьте правильность записи и выберите **"ПОДТВЕРДИТЬ".** 
    
## <a name="add-the-required-cname-records"></a>Добавление необходимых записей CNAME

1. Войдите [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) в систему с помощью своих учетных данных. 
    
2. Под **заголовком "Все домены"** выберите **DNS.**
    
3. В **заголовке записей CNAME/Alias** выберите кнопку редактирования (значок wrench). 
    
4. Введите следующие записи в текстовые поля:


    |**HOST (УЗЕЛ)**|**Address (Must end with a ".")**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com.  <br/> |
    |sip  <br/> |sipdir.online.lync.com.  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> |
   
5. Выберите **"ДАЛЕе".** 
    
6. Проверьте правильность записи и выберите **"ПОДТВЕРДИТЬ".** 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Добавление записи TXT для SPF, предотвращающей рассылку спама

1. Войдите [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) в систему с помощью своих учетных данных. 
    
2. Под **заголовком "Все домены"** выберите **DNS.**
    
3. Под **заголовком записей TXT** выберите кнопку редактирования (значок wrench). 
    
4. Введите следующие записи в текстовые поля:
    
    |**Host**|**Text**|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> |
   
5. Выберите **"ДАЛЕе".** 
    
6. Проверьте правильность записи и выберите **"ПОДТВЕРДИТЬ".** 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт

ПРИМЕЧАНИЕ. В настоящее время записи SRV НЕДОСТУПНЫ на уровне службы easyDNS "Домен плюс". Для добавления записей SRV может потребоваться обновление до более высокого уровня обслуживания с помощью easyDNS 
  
1. Войдите [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) в систему с помощью своих учетных данных. 
    
2. Под **заголовком "Все домены"** выберите **DNS.**
    
3. Под **заголовком записей SRV** выберите кнопку редактирования (значок wrench). 
    
4. Введите следующие записи в текстовые поля:
    
    |**SERVICE (СЛУЖБА)**|**PROTO**|**HOST (УЗЕЛ)**|**PRI**|**WGT**|**PORT (ПОРТ)**|**TARGET(Must end with a ".")**|**TTL (Срок жизни)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |TLS  <br/> |@  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com.  <br/> |1800  <br/> |
    |_sipfederationtls  <br/> |TCP  <br/> |@  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> |1800  <br/> |
   
5. Выберите **"ДАЛЕе".** 
    
6. Проверьте правильность записи и выберите **"ПОДТВЕРДИТЬ".** 
    

