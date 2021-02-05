---
title: Приобретение имени домена
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1561140a-16a9-4a02-822d-a989250e479d
description: Узнайте, как приобрести доменное имя в Microsoft 365.
ms.openlocfilehash: 40fc44dfa3bc3e608b590157b7db423302af748d
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2021
ms.locfileid: "50113967"
---
# <a name="buy-a-domain-name"></a>Приобретение имени домена

::: moniker range="o365-21vianet"

> [!NOTE]
> Изменяется Центр администрирования. Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

 *Для добавления, изменения или удаления доменов **необходимо быть** глобальным администратором плана предприятия или [предприятия.](https://products.office.com/business/office)  Эти изменения влияют на весь *клиент,* настроенные администраторы или обычные пользователи не смогут вносить эти изменения.*  

 Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**. 
  
### <a name="sign-in-and-go-to-settings--domains--buy-a-domain"></a>Войдите и перейдите в "Параметры" \> \> "Купить домен"

1. В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).
    
3. На странице **"Домены"** выберите **"Купить домен".**
    
Вы можете выбрать один из следующих доменов верхнего уровня:
  
- .biz
    
- .com
    
- .info
    
- .me
    
- .mobi
    
- .net
    
- .org
    
- .tv
    
- .co.uk
    
- org.uk
    

> [!NOTE]
> При выборе **покупки домена** вы можете перенаправить вас на веб-сайт партнера Майкрософт, если клиент приобретен или управляется через партнера Майкрософт.

### <a name="domain-privacy"></a>Конфиденциальность домена
Мы предлагаем бесплатную подписку на конфиденциальность домена с покупкой домена. При этом ваши контактные данные будут прикрепляться к регистрации домена с помощью ЛИЧНЫХ сведений. [Подробнее.](https://whois.icann.org/en/privacy-and-proxy-services)
  
### <a name="buy-a-domain-from-another-domain-registrar"></a>Приобретение домена у другого регистратора доменных имен
Если вы хотите приобрести домен у регистратора доменных имен, кроме [GoDaddy,](https://www.godaddy.com)мы рекомендуем использовать один из ниже, который поддерживает автоматическую настройку (Domain Connect). 
  
- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [WordPress](https://www.wordpress.com) 

   
### <a name="transfer-your-domain-to-a-different-domain-registrar"></a>Передача домена другому регистратору

Если вашим доменом управляет поставщик, который не поддерживает все необходимые записи DNS, вы можете передать его другому регистратору. При передаче домена необходимо изменить получателя платежей за продление доменного имени.
  
Отправьте запрос на передачу регистратору, которому хотите передать домен. Найдите на его веб-сайте соответствующую услугу, например **Transfer DNS** (Передача DNS). На то, чтобы после внесения изменений они вступили в силу в Интернете, может потребоваться несколько дней.
 



::: moniker range="o365-21vianet"
## <a name="how-to-buy-a-domain-for-office-365-operated-by-21vianet"></a>Приобретение домена для службы Office 365, предоставляемой 21Vianet



Если у вас еще нет домена, его легко можно приобрести в Интернете у регистратора доменных имен, посредника или даже у вашего поставщика услуг Интернета. При регистрации в службе Office 365, предоставляемой 21Vianet, вы получаете доменное имя, например contoso.partner.onmschina.cn. Однако при желании можно использовать собственное доменное имя, например fourthcoffee.com.
  
Чтобы настроить домен в Microsoft 365, необходимо владеть доменом и изменить некоторые записи DNS для своего домена.
  
> [!CAUTION]
> Некоторые регистраторы доменных имен или поставщики услуг размещения DNS не позволяют создавать все записи DNS, необходимые для Microsoft 365. Указанные ниже регистраторы поддерживают все необходимые записи. Если вы планируете воспользоваться услугами другого поставщика услуг размещения, [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77). 
  
После регистрации домена (у регистратора доменных имен) необходимо войти в Microsoft 365 от имени администратора и настроить домен, чтобы использовать его с адресом электронной почты и другими службами.
  
> [!NOTE]
> Сведения об общедоступных веб-сайтах SharePoint Online в этой статье применимы только в том случае, если ваша организация приобрела Microsoft 365 до 9 марта 2015 г. 

## <a name="domain-registrars-that-support-all-dns-records-required-for-microsoft-365"></a>Регистраторы доменных имен, которые поддерживают все записи DNS, необходимые для Microsoft 365

- [Oray](https://oray.com/)
    
- [HiChina](https://www.hichina.com/)
    
- [east.net](http://www.east.net/)
    
- [BIZCN](https://www.bizcn.com/)
    
::: moniker-end

## <a name="related-articles"></a>Статьи по теме

[Добавление домена в Microsoft 365](../setup/add-domain.md)

[Вопросы и ответы о доменах](../setup/domains-faq.yml)

[Обновите записи DNS, чтобы сохранить веб-сайт у текущего поставщика услуг размещения.](https://docs.microsoft.com/microsoft-365/admin/dns/update-dns-records-to-retain-current-hosting-provider)
