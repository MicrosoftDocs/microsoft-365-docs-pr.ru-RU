---
title: Создание записей DNS для Office 365 при управлении записями DNS
f1.keywords:
- CSH
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
search.appverid:
- MET150
- GEA150
ms.assetid: 0669bf14-414d-4f51-8231-6b710ce7980b
ROBOTS: NOINDEX
description: 'Узнайте, как создавать записи DNS для Office 365 под управлением 21Vianet при управлении записями DNS. '
monikerRange: o365-21vianet
ms.openlocfilehash: 1f7b8330b45d6704d2d56b2c68cfcd37de84207a
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42257092"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a>Создание записей DNS для Office 365 при управлении записями DNS

Подробные инструкции по созданию записей DNS для Office 365 под управлением 21Vianet, в том числе записи MX, необходимой для маршрутизации почты, можно найти [в статье Создание DNS-записей на любом поставщике услуг хостинга DNS для Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md). 
  
  
Дополнительные параметры и некоторые моменты, которые следует учитывать:
      
-  Если вы не знаете, какой поставщик услуг размещения DNS или регистратор используется для домена, см. статью [Определение регистратора домена или поставщика услуг размещения DNS](../get-help-with-domains/find-your-domain-registrar.md).     Описание действий, выполняемых DNS-записями, можно узнать в статье [основы DNS](../get-help-with-domains/dns-basics.md).
    
-  Некоторые поставщики услуг хостинга DNS не позволяют создавать все необходимые типы записей, что приводит к [ограничениям службы, когда поставщик услуг хостинга не поддерживает SRV, CNAME, txt или перенаправление](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77). Если ваш поставщик не поддерживает записи SRV, TXT или CNAME, рекомендуется [передать домен](https://support.office.com/article/a6689b24-eeca-41f1-afe6-19917936b73c.aspx) [поставщику, который поддерживает все необходимые типы записей](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77). 
    
- Чтобы узнать, какие записи DNS необходимы, и найти значения, которые необходимо использовать для каждой записи, включая запись MX для электронной почты, ознакомьтесь со статьей [сбор сведений, необходимых для создания записей DNS для Office 365](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e). Описание действий, выполняемых DNS-записями, можно узнать в статье [основы DNS](../get-help-with-domains/dns-basics.md).
    

