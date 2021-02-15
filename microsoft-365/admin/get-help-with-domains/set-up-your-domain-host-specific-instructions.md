---
title: Настройка домена (инструкции для конкретных узлов)
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
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: ae950c9e-e8d9-4108-b0cb-449156998580
description: Узнайте, как управлять своими записями DNS или позволить Корпорации Майкрософт самостоятельно управлять вашими записями DNS.
ms.openlocfilehash: ddf3b7faf7ac336b2d7caf3b7d35d9a4f101b122
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126363"
---
# <a name="set-up-your-domain-host-specific-instructions"></a><span data-ttu-id="135f4-103">Настройка домена (инструкции для конкретных узлов)</span><span class="sxs-lookup"><span data-stu-id="135f4-103">Set up your domain (host-specific instructions)</span></span>

<span data-ttu-id="135f4-104">Чтобы начать использовать пользовательский домен (contoso.com) с Microsoft 365, необходимо проверить свой домен и настроить записи DNS вашего домена.</span><span class="sxs-lookup"><span data-stu-id="135f4-104">To start using a custom domain (contoso.com) with Microsoft 365, you need to verify your domain and configure your domain's DNS records.</span></span> 
  
<span data-ttu-id="135f4-105">Вы можете добавлять записи DNS и управлять ими с помощью средств администрирования на вашем сайте домена или предоставить корпорации Майкрософт контроль над вашими записями домена, и мы настроим их для вас.</span><span class="sxs-lookup"><span data-stu-id="135f4-105">You can add and manage DNS records using the administrative tools at your domain host, or give Microsoft control of your domain records and we'll set them up for you.</span></span>
  
<span data-ttu-id="135f4-106">Выберите ваш доменный хост ниже для точных действий.</span><span class="sxs-lookup"><span data-stu-id="135f4-106">Select your domain host below for the exact steps.</span></span> <span data-ttu-id="135f4-107">Если вы не знаете, кто ваш хост, см. ["Поиск регистратора доменных имен".](find-your-domain-registrar.md)</span><span class="sxs-lookup"><span data-stu-id="135f4-107">If you're not sure who your host is, see [Find your domain registrar](find-your-domain-registrar.md).</span></span>
  

## <a name="let-microsoft-365-manage-your-dns-records"></a><span data-ttu-id="135f4-108">Разрешите Microsoft 365 управлять своими записями DNS</span><span class="sxs-lookup"><span data-stu-id="135f4-108">Let Microsoft 365 manage your DNS records</span></span>

||
|---|---|
|[<span data-ttu-id="135f4-109">1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="135f4-109">1&1 IONOS</span></span>](../dns/change-nameservers-at-1-1-internet.md) |
|[<span data-ttu-id="135f4-110">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="135f4-110">Amazon Web Services (AWS)</span></span>](../dns/change-nameservers-at-aws.md) |
 [<span data-ttu-id="135f4-111">Bluehost</span><span class="sxs-lookup"><span data-stu-id="135f4-111">Bluehost</span></span>](../dns/change-nameservers-at-bluehost.md)|
|[<span data-ttu-id="135f4-112">Домены Google</span><span class="sxs-lookup"><span data-stu-id="135f4-112">Google   Domains</span></span>](../dns/change-nameservers-at-google-domains.md) |
|[<span data-ttu-id="135f4-113">Hostgator   </span><span class="sxs-lookup"><span data-stu-id="135f4-113">Hostgator   </span></span>](../dns/change-nameservers-at-hostgator.md)  |  
|[<span data-ttu-id="135f4-114">MyDomain</span><span class="sxs-lookup"><span data-stu-id="135f4-114">MyDomain</span></span>](../dns/change-nameservers-at-mydomain.md) | 
|[<span data-ttu-id="135f4-115">Namecheap</span><span class="sxs-lookup"><span data-stu-id="135f4-115">Namecheap</span></span>](../dns/change-nameservers-at-namecheap.md)|
|[<span data-ttu-id="135f4-116">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="135f4-116">Network Solutions</span></span>](../dns/change-nameservers-at-network-solutions.md) |  

<span data-ttu-id="135f4-117">Или узнайте, как изменить доменные имена, чтобы настроить Microsoft 365 у любого [регистратора доменных имен.](change-nameservers-at-any-domain-registrar.md)</span><span class="sxs-lookup"><span data-stu-id="135f4-117">Or, learn how to [change nameservers to set up Microsoft 365 with any domain registrar](change-nameservers-at-any-domain-registrar.md).</span></span>

## <a name="manage-your-own-dns-records"></a><span data-ttu-id="135f4-118">Управление своими записями DNS</span><span class="sxs-lookup"><span data-stu-id="135f4-118">Manage your own DNS records</span></span>

|                           |                          |
|---------------------------|--------------------------|
| [<span data-ttu-id="135f4-119">1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="135f4-119">1&1 IONOS</span></span>](../dns/create-dns-records-at-1-1-internet.md) | [<span data-ttu-id="135f4-120">Hover</span><span class="sxs-lookup"><span data-stu-id="135f4-120">Hover</span></span>](../dns/create-dns-records-at-hover.md) |
| [<span data-ttu-id="135f4-121">123-reg.co.uk</span><span class="sxs-lookup"><span data-stu-id="135f4-121">123-reg.co.uk</span></span>](../dns/create-dns-records-at-123-reg-co-uk.md) | [<span data-ttu-id="135f4-122">Управляется Google (eNom)</span><span class="sxs-lookup"><span data-stu-id="135f4-122">Managed   by Google (eNom)</span></span>](../dns/create-dns-records-for-domain-managed-by-google-enom.md)|
| [<span data-ttu-id="135f4-123">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="135f4-123">Amazon Web Services (AWS)</span></span>](../dns/create-dns-records-at-aws.md) | [<span data-ttu-id="135f4-124">MyDomain</span><span class="sxs-lookup"><span data-stu-id="135f4-124">MyDomain</span></span>](../dns/create-dns-records-at-mydomain.md) |
| [<span data-ttu-id="135f4-125">Зоны DNS Azure</span><span class="sxs-lookup"><span data-stu-id="135f4-125">Azure DNS zones</span></span>](../dns/create-dns-records-for-azure-dns-zones.md) | [<span data-ttu-id="135f4-126">name.com</span><span class="sxs-lookup"><span data-stu-id="135f4-126">name.com</span></span>](../dns/create-dns-records-at-name-com.md) |
| [<span data-ttu-id="135f4-127">Bluehost</span><span class="sxs-lookup"><span data-stu-id="135f4-127">Bluehost</span></span>](../dns/create-dns-records-at-bluehost.md) | [<span data-ttu-id="135f4-128">Namecheap</span><span class="sxs-lookup"><span data-stu-id="135f4-128">Namecheap</span></span>](../dns/create-dns-records-at-namecheap.md)|
| [<span data-ttu-id="135f4-129">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="135f4-129">Cloudflare</span></span>](../dns/create-dns-records-at-cloudflare.md)| [<span data-ttu-id="135f4-130">Names.co.uk</span><span class="sxs-lookup"><span data-stu-id="135f4-130">Names.co.uk</span></span>](../dns/create-dns-records-at-names-co-uk.md) |
|  [<span data-ttu-id="135f4-131">Crazy Domains</span><span class="sxs-lookup"><span data-stu-id="135f4-131">Crazy Domains</span></span>](../dns/create-dns-records-at-crazy-domains.md)| [<span data-ttu-id="135f4-132">Netregistry</span><span class="sxs-lookup"><span data-stu-id="135f4-132">Netregistry</span></span>](../dns/create-dns-records-at-netregistry.md) |
|[<span data-ttu-id="135f4-133">DNSMadeEasy</span><span class="sxs-lookup"><span data-stu-id="135f4-133">DNSMadeEasy</span></span>](../dns/create-dns-records-at-dnsmadeeasy.md) | [<span data-ttu-id="135f4-134">Сетевые решения</span><span class="sxs-lookup"><span data-stu-id="135f4-134">Network   Solutions</span></span>](../dns/create-dns-records-at-network-solutions.md) |
|[<span data-ttu-id="135f4-135">Dreamhost</span><span class="sxs-lookup"><span data-stu-id="135f4-135">Dreamhost</span></span>](../dns/create-dns-records-at-dreamhost.md)  | [<span data-ttu-id="135f4-136">OVH</span><span class="sxs-lookup"><span data-stu-id="135f4-136">OVH</span></span>](../dns/create-dns-records-at-ovh.md) |
|  [<span data-ttu-id="135f4-137">Dyn.com</span><span class="sxs-lookup"><span data-stu-id="135f4-137">Dyn.com</span></span>](../dns/create-dns-records-at-dyn-com.md) | [<span data-ttu-id="135f4-138">Register.com</span><span class="sxs-lookup"><span data-stu-id="135f4-138">Register.com</span></span>](../dns/create-dns-records-at-register-com.md) |
| [<span data-ttu-id="135f4-139">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="135f4-139">eNomCentral</span></span>](../dns/create-dns-records-at-enomcentral.md)| [<span data-ttu-id="135f4-140">Register365 для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="135f4-140">Register365 for Microsoft 365</span></span>](../dns/create-dns-records-at-register365.md)  |
| [<span data-ttu-id="135f4-141">Freenom</span><span class="sxs-lookup"><span data-stu-id="135f4-141">Freenom</span></span>](../dns/create-dns-records-at-freenom.md) | [<span data-ttu-id="135f4-142"> web.com </span><span class="sxs-lookup"><span data-stu-id="135f4-142"> web.com </span></span>](../dns/create-dns-records-at-web-com.md)|
|[<span data-ttu-id="135f4-143">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="135f4-143">GoDaddy</span></span>](../dns/create-dns-records-at-godaddy.md)|[<span data-ttu-id="135f4-144"> DNS на основе Windows</span><span class="sxs-lookup"><span data-stu-id="135f4-144"> Windows-based DNS</span></span>](../dns/create-dns-records-using-windows-based-dns.md)   |
| [<span data-ttu-id="135f4-145">Google Domains</span><span class="sxs-lookup"><span data-stu-id="135f4-145">Google Domains</span></span>](../dns/create-dns-records-at-google-domains.md) |[<span data-ttu-id="135f4-146">Wix</span><span class="sxs-lookup"><span data-stu-id="135f4-146">Wix</span></span>](../dns/create-dns-records-at-wix.md) |
|[<span data-ttu-id="135f4-147">Hostgator</span><span class="sxs-lookup"><span data-stu-id="135f4-147">Hostgator</span></span>](../dns/create-dns-records-at-hostgator.md)  | [<span data-ttu-id="135f4-148">Yahoo!   Малый бизнес</span><span class="sxs-lookup"><span data-stu-id="135f4-148">Yahoo!   Small Business</span></span>](../dns/create-dns-records-at-yahoo-small-business.md)  |

[<span data-ttu-id="135f4-149">Мне нужны общие инструкции, так как мой доменный сайт не указан в этом списке. </span><span class="sxs-lookup"><span data-stu-id="135f4-149">I need general instructions, because my domain host isn't on this list. </span></span>](create-dns-records-at-any-dns-hosting-provider.md)
   
