---
title: Приобретение доменного имени в Office 365
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
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1561140a-16a9-4a02-822d-a989250e479d
description: Узнайте, как приобрести доменное имя в Office 365.
ms.custom: okr_smb
ms.openlocfilehash: 1982ac054ca64f2442e108b457553a58ebcb234c
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857443"
---
# <a name="buy-a-domain-name-in-office-365"></a>Приобретение доменного имени в Office 365

 *Чтобы добавить, изменить или удалить домены, **необходимо** быть **глобальным администратором** [плана бизнеса или предприятия](https://products.office.com/business/office). Эти изменения затрагивают весь клиент, *Администраторы* или *обычные пользователи* не смогут вносить эти изменения.*  

 Если вы не нашли то, что вы ищете, обратитесь к разделу **[Вопросы и ответы по доменам](../setup/domains-faq.md)**. 
  
### <a name="sign-in-and-go-to-settings--domains--buy-a-domain"></a>Вход и переход к разделу \> " \> домены параметров" Покупка домена

1. В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).
    
3. На странице **Domains (домены** ) выберите пункт **купить домен**.
    
Вы можете выбрать один из следующих доменов верхнего уровня:
  
- . BIZ
    
- . com
    
- . info
    
- . Me
    
- . Моби
    
- среды
    
- . org
    
- . TV
    
- . co.uk
    
- org.uk
    

> [!NOTE]
> Если вы выбрали **приобрести домен**, вы можете переадресовать на свой веб-сайт партнера Майкрософт, если клиент приобрел/управляет через партнера корпорации Майкрософт.

### <a name="domain-privacy"></a>Конфиденциальность домена
Мы предлагаем бесплатную подписку на заявление о конфиденциальности домена, в которой вы приобрели домен. В этом случае контактные данные, прикрепленные к регистрации домена, сохраняются в ИКАНН Private. [Подробнее.](https://whois.icann.org/en/privacy-and-proxy-services)
  
### <a name="buy-a-domain-from-another-domain-registrar"></a>Приобретение домена у другого регистратора доменных имен
Если вы хотите приобрести домен у регистратора доменных имен, отличного от [GoDaddy](https://www.godaddy.com), мы рекомендуем использовать один из следующих способов, поддерживающих автоматическую установку (подключение к домену). 
  
- [1&amp;1 ионос](https://www.1and1.com/)
- [WordPress](https://www.wordpress.com) 

   
### <a name="transfer-your-domain-to-a-different-domain-registrar"></a>Передача домена другому регистратору

Если вашим доменом управляет поставщик, который не поддерживает все необходимые записи DNS, вы можете передать его другому регистратору. При передаче домена необходимо изменить получателя платежей за продление доменного имени.
  
Отправьте запрос на передачу регистратору, которому хотите передать домен. Найдите на его веб-сайте соответствующую услугу, например **Transfer DNS** (Передача DNS). На то, чтобы после внесения изменений они вступили в силу в Интернете, может потребоваться несколько дней.
 



::: moniker range="o365-21vianet"
## <a name="how-to-buy-a-domain-for-office-365-operated-by-21vianet"></a>Приобретение домена для службы Office 365, предоставляемой 21Vianet



Если у вас еще нет домена, его легко можно приобрести в Интернете у регистратора доменных имен, посредника или даже у вашего поставщика услуг Интернета. При регистрации в службе Office 365, предоставляемой 21Vianet, вы получаете доменное имя, например contoso.partner.onmschina.cn. Однако при желании можно использовать собственное доменное имя, например fourthcoffee.com.
  
Чтобы настроить домен в Office 365, необходимо быть владельцем домена и изменить некоторые записи DNS для него.
  
> [!CAUTION]
> Некоторые регистраторы доменных имен и поставщики услуг размещения DNS не позволяют создать все записи DNS, необходимые для Office 365. Указанные ниже регистраторы поддерживают все необходимые записи. Если вы планируете воспользоваться услугами другого поставщика услуг размещения, [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77). 
  
После регистрации домена (на сайте регистратора доменных имен) можно войти в Office 365 с правами администратора и настроить этот домен, чтобы использовать его в адресе электронной почты и с другими службами.
  
> [!NOTE]
> The SharePoint Online Public Website information in this article only applies if your organization purchased Office 365 prior to March 9, 2015. 

## <a name="domain-registrars-that-support-all-dns-records-required-for-office-365"></a>Регистраторы доменных имен, которые поддерживают все записи DNS, необходимые для Office 365

- [Oray](https://oray.com/)
    
- [HiChina](https://www.hichina.com/)
    
- [east.net](http://www.east.net/)
    
- [BIZCN](https://www.bizcn.com/)
    
::: moniker-end

## <a name="related-articles"></a>Связанные статьи

[Добавление домена в Office 365](../setup/add-domain.md)

[Вопросы и ответы о доменах](../setup/domains-faq.md)

[Получение справки по доменам Office 365](get-help-with-domains.yml)
