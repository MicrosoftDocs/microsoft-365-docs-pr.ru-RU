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
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a><span data-ttu-id="82b0a-103">Создание записей DNS для Office 365 при управлении записями DNS</span><span class="sxs-lookup"><span data-stu-id="82b0a-103">Create DNS records for Office 365 when you manage your DNS records</span></span>

<span data-ttu-id="82b0a-104">Подробные инструкции по созданию записей DNS для службы Office 365, под управлением 21Vianet, включая запись MX, необходимую для маршрутизации почты, см. в описании создания записей DNS у любого поставщика услуг размещения DNS для [Office 365.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="82b0a-104">For detailed instructions about how to create DNS records for Office 365 operated by 21Vianet, including the MX record required for mail routing, see [Create DNS records at any DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> 
  
  
<span data-ttu-id="82b0a-105">Дополнительные параметры и некоторые из них, о чем следует помнить:</span><span class="sxs-lookup"><span data-stu-id="82b0a-105">More options and some things to be aware of:</span></span>
      
-  <span data-ttu-id="82b0a-106">Если вы не знаете, какой поставщик услуг размещения DNS или регистратор используется для домена, см. статью [Определение регистратора домена или поставщика услуг размещения DNS](../get-help-with-domains/find-your-domain-registrar.md).    </span><span class="sxs-lookup"><span data-stu-id="82b0a-106">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span> <span data-ttu-id="82b0a-107">Описание того, что делают записи DNS, см. в [описании основ DNS.](../get-help-with-domains/dns-basics.md)</span><span class="sxs-lookup"><span data-stu-id="82b0a-107">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    
-  <span data-ttu-id="82b0a-108">Некоторые поставщики услуг размещения DNS не могут создавать все необходимые типы записей, что приводит к ограничениям служб, если поставщик услуг размещения не поддерживает [SRV, CNAME, TXT](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)или перенаправление.</span><span class="sxs-lookup"><span data-stu-id="82b0a-108">Some DNS hosting providers don't let you create all the required record types, which causes [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> <span data-ttu-id="82b0a-109">Если поставщик не поддерживает записи SRV, TXT или CNAME, [](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/buy-a-domain-name) рекомендуется передать домен поставщику, который поддерживает все необходимые типы [записей.](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)</span><span class="sxs-lookup"><span data-stu-id="82b0a-109">If your provider doesn't support SRV, TXT, or CNAME records, we recommend that you [transfer your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/buy-a-domain-name) to a [provider that supports all required record types](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> 
    
- <span data-ttu-id="82b0a-110">Чтобы узнать, какие записи DNS необходимы, и найти значения для каждой записи, включая запись MX для электронной почты, см. сведения, необходимые для создания записей [DNS для Office 365.](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records)</span><span class="sxs-lookup"><span data-stu-id="82b0a-110">To see which DNS records are required and find the values to use for each record, including the MX record for email, see [Gather the information you need to create Office 365 DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records).</span></span> <span data-ttu-id="82b0a-111">Описание того, что делают записи DNS, см. в [описании основ DNS.](../get-help-with-domains/dns-basics.md)</span><span class="sxs-lookup"><span data-stu-id="82b0a-111">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    

