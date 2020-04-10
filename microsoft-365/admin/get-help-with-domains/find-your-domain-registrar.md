---
title: Поиск регистратора доменных имен для Office 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: Узнайте, как найти регистратора доменных имен и поставщика услуг размещения DNS с помощью поиска InterNIC.
ms.openlocfilehash: 71af74a0f94f2cdc251dab78fd59e9bdd90da5ce
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210396"
---
# <a name="find-your-domain-registrar-for-office-365"></a>Поиск регистратора доменных имен для Office 365

 Если вы не нашли то, что вы ищете, обратитесь к разделу **[Вопросы и ответы по доменам](../setup/domains-faq.md)**. 
  
## <a name="domain-registrar"></a>Регистратор доменных имен
  
### <a name="find-your-domain-name-registrar"></a>Поиск регистратора доменных имен

>[!NOTE]
> С этим средством работают только домены, заканчивающиеся на *.COM*, *.NET* и *.EDU*.
  
1. На [странице поиска InterNIC](https://go.microsoft.com/fwlink/p/?LinkId=402770) в поле **Whois Search** (Поиск в Whois) введите имя своего домена, например, *contoso.com*. 
    
2. Установите переключатель в положение **Domain** (Домен) и нажмите кнопку **Submit** (Отправить).
    
3. На странице **Whois Search Results** (Результаты поиска Whois) найдите запись **Registrar** (Регистратор). Эта запись соответствует организации, предоставляющей услуги регистрации для вашего домена. 
    
## <a name="dns-hosting-provider"></a>Поставщик услуг размещения DNS
  
### <a name="find-your-dns-hosting-provider"></a>Поиск поставщика услуг размещения DNS

>[!NOTE]
> С этим средством работают только домены, заканчивающиеся на *.COM*, *.NET* и *.EDU*.
  
1. На [странице поиска InterNIC]( https://go.microsoft.com/fwlink/p/?LinkId=402770) в поле **Whois Search** (Поиск в Whois) введите имя своего домена, например, contoso.com. 
    
2. Установите переключатель в положение **Domain** (Домен) и нажмите кнопку **Submit** (Отправить).
    
3. На странице **Whois Search Results** (Результаты поиска Whois) найдите первую запись **Name Server** (Сервер доменных имен). 
    
4. Скопируйте сведения о сервере доменных имен после двоеточия (:) и вставьте их в поле **Search** (Поиск) вверху страницы. Установите переключатель в положение **Nameserver** (Сервер доменных имен) и нажмите кнопку **Submit** (Отправить).
    
5. На странице **Whois Search Results** (Результаты поиска Whois) найдите запись **Registrar** (Регистратор). В этой записи содержится название поставщика услуг размещения DNS, которому принадлежит сервер имен для вашего домена. 
    
---

