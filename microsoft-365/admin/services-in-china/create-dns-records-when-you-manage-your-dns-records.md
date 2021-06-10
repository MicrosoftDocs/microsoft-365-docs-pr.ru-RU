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
description: 'Научитесь создавать записи DNS для Office 365 21Vianet при управлении записями DNS. '
monikerRange: o365-21vianet
ms.openlocfilehash: 1eaa2bcc7263eaa12e53131246abd591006b0536
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914358"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a><span data-ttu-id="cb04d-103">Создание записей DNS для Office 365 при управлении записями DNS</span><span class="sxs-lookup"><span data-stu-id="cb04d-103">Create DNS records for Office 365 when you manage your DNS records</span></span>

<span data-ttu-id="cb04d-104">Подробные инструкции по созданию записей DNS для Office 365, управляемых 21Vianet, включая запись MX, необходимую для маршрутизации почты, см. в этой ссылке [Create DNS records at any DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="cb04d-104">For detailed instructions about how to create DNS records for Office 365 operated by 21Vianet, including the MX record required for mail routing, see [Create DNS records at any DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> 
  
  
<span data-ttu-id="cb04d-105">Дополнительные параметры и некоторые вещи, которые следует знать:</span><span class="sxs-lookup"><span data-stu-id="cb04d-105">More options and some things to be aware of:</span></span>
      
-  <span data-ttu-id="cb04d-106">Если вы не знаете, какой поставщик услуг размещения DNS или регистратор используется для домена, см. статью [Определение регистратора домена или поставщика услуг размещения DNS](../get-help-with-domains/find-your-domain-registrar.md).    </span><span class="sxs-lookup"><span data-stu-id="cb04d-106">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span> <span data-ttu-id="cb04d-107">Описание того, что делают записи DNS, см. в описании [основ DNS.](../get-help-with-domains/dns-basics.md)</span><span class="sxs-lookup"><span data-stu-id="cb04d-107">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    
-  <span data-ttu-id="cb04d-108">Некоторые поставщики хостинга DNS не могут создавать все необходимые типы записей, что вызывает ограничения службы, когда поставщик хостинга не поддерживает [SRV, CNAME, TXT](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)или перенаправление.</span><span class="sxs-lookup"><span data-stu-id="cb04d-108">Some DNS hosting providers don't let you create all the required record types, which causes [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> <span data-ttu-id="cb04d-109">Если ваш поставщик не поддерживает записи SRV, TXT или CNAME, рекомендуется передать домен поставщику, который поддерживает все необходимые [типы записей.](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77) [](../get-help-with-domains/buy-a-domain-name.md)</span><span class="sxs-lookup"><span data-stu-id="cb04d-109">If your provider doesn't support SRV, TXT, or CNAME records, we recommend that you [transfer your domain](../get-help-with-domains/buy-a-domain-name.md) to a [provider that supports all required record types](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> 
    
- <span data-ttu-id="cb04d-110">Чтобы узнать, какие записи DNS необходимы, и найти значения, которые необходимо использовать для каждой записи, включая запись MX для электронной почты, см. в этой ссылке Сбор сведений, необходимых для создания Office 365 [записей DNS.](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="cb04d-110">To see which DNS records are required and find the values to use for each record, including the MX record for email, see [Gather the information you need to create Office 365 DNS records](../get-help-with-domains/information-for-dns-records.md).</span></span> <span data-ttu-id="cb04d-111">Описание того, что делают записи DNS, см. в описании [основ DNS.](../get-help-with-domains/dns-basics.md)</span><span class="sxs-lookup"><span data-stu-id="cb04d-111">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
