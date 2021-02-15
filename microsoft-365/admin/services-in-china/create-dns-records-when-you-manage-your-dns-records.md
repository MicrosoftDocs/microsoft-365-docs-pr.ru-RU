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
description: 'Узнайте, как создавать записи DNS для Службы Office 365, управляемой компанией 21Vianet, при управлении записями DNS. '
monikerRange: o365-21vianet
ms.openlocfilehash: 8f252ba47fbd72f5a628a23567addcc84604fb3c
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644823"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a>Создание записей DNS для Office 365 при управлении записями DNS

Подробные инструкции по созданию записей DNS для службы Office 365, под управлением 21Vianet, включая запись MX, необходимую для маршрутизации почты, см. в описании создания записей DNS у любого поставщика услуг размещения DNS для [Office 365.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) 
  
  
Дополнительные параметры и некоторые из них, о чем следует помнить:
      
-  Если вы не знаете, какой поставщик услуг размещения DNS или регистратор используется для домена, см. статью [Определение регистратора домена или поставщика услуг размещения DNS](../get-help-with-domains/find-your-domain-registrar.md).     Описание того, что делают записи DNS, см. в [описании основ DNS.](../get-help-with-domains/dns-basics.md)
    
-  Некоторые поставщики услуг размещения DNS не могут создавать все необходимые типы записей, что приводит к ограничениям служб, если поставщик услуг размещения не поддерживает [SRV, CNAME, TXT](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)или перенаправление. Если поставщик не поддерживает записи SRV, TXT или CNAME, [](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/buy-a-domain-name) рекомендуется передать домен поставщику, который поддерживает все необходимые типы [записей.](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77) 
    
- Чтобы узнать, какие записи DNS необходимы, и найти значения для каждой записи, включая запись MX для электронной почты, см. сведения, необходимые для создания записей [DNS для Office 365.](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records) Описание того, что делают записи DNS, см. в [описании основ DNS.](../get-help-with-domains/dns-basics.md)
    

