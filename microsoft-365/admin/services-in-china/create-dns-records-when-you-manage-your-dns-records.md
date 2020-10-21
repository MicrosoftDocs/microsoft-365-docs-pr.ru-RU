---
title: Создание записей DNS для Office 365 при управлении записями DNS
f1.keywords:
- CSH
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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEA150
ms.assetid: 0669bf14-414d-4f51-8231-6b710ce7980b
ROBOTS: NOINDEX
description: 'Узнайте, как создавать записи DNS для Office 365 под управлением 21Vianet при управлении записями DNS. '
monikerRange: o365-21vianet
ms.openlocfilehash: 8f252ba47fbd72f5a628a23567addcc84604fb3c
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644823"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a>Создание записей DNS для Office 365 при управлении записями DNS

Подробные инструкции по созданию записей DNS для Office 365 под управлением 21Vianet, в том числе записи MX, необходимой для маршрутизации почты, можно найти [в статье Создание DNS-записей на любом поставщике услуг хостинга DNS для Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md). 
  
  
Дополнительные параметры и некоторые моменты, которые следует учитывать:
      
-  Если вы не знаете, какой поставщик услуг размещения DNS или регистратор используется для домена, см. статью [Определение регистратора домена или поставщика услуг размещения DNS](../get-help-with-domains/find-your-domain-registrar.md).     Описание действий, выполняемых DNS-записями, можно узнать в статье [основы DNS](../get-help-with-domains/dns-basics.md).
    
-  Некоторые поставщики услуг хостинга DNS не позволяют создавать все необходимые типы записей, что приводит к [ограничениям службы, когда поставщик услуг хостинга не поддерживает SRV, CNAME, txt или перенаправление](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77). Если ваш поставщик не поддерживает записи SRV, TXT или CNAME, рекомендуется [передать домен](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/buy-a-domain-name) [поставщику, который поддерживает все необходимые типы записей](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77). 
    
- Чтобы узнать, какие записи DNS необходимы, и найти значения, которые необходимо использовать для каждой записи, включая запись MX для электронной почты, ознакомьтесь со статьей [сбор сведений, необходимых для создания записей DNS для Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records). Описание действий, выполняемых DNS-записями, можно узнать в статье [основы DNS](../get-help-with-domains/dns-basics.md).
    

