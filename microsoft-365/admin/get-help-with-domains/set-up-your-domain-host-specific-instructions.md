---
title: Настройка домена (инструкции для конкретных узлов)
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: ae950c9e-e8d9-4108-b0cb-449156998580
description: Узнайте, как управлять собственными DNS-записями или управлять записями DNS в Майкрософт.
ms.openlocfilehash: ac026ce0dba4eefff2c837da71c18b08aca12ea6
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2020
ms.locfileid: "45079777"
---
# <a name="set-up-your-domain-host-specific-instructions"></a><span data-ttu-id="5de3c-103">Настройка домена (инструкции для конкретных узлов)</span><span class="sxs-lookup"><span data-stu-id="5de3c-103">Set up your domain (host-specific instructions)</span></span>

<span data-ttu-id="5de3c-104">Чтобы приступить к использованию настраиваемого домена (contoso.com) с Microsoft 365, необходимо проверить домен и настроить записи DNS вашего домена.</span><span class="sxs-lookup"><span data-stu-id="5de3c-104">To start using a custom domain (contoso.com) with Microsoft 365, you need to verify your domain and configure your domain's DNS records.</span></span> 
  
<span data-ttu-id="5de3c-105">Вы можете добавлять DNS-записи и управлять ими с помощью средств администрирования на узле домена, а также предоставлять Майкрософт управление записями домена, а также настроить их для вас.</span><span class="sxs-lookup"><span data-stu-id="5de3c-105">You can add and manage DNS records using the administrative tools at your domain host, or give Microsoft control of your domain records and we'll set them up for you.</span></span>
  
<span data-ttu-id="5de3c-106">Выберите узел домена ниже, чтобы выполнить точные действия.</span><span class="sxs-lookup"><span data-stu-id="5de3c-106">Select your domain host below for the exact steps.</span></span> <span data-ttu-id="5de3c-107">Если вы не знаете, что такое ваш узел, ознакомьтесь со статьей [Поиск регистратора доменных](find-your-domain-registrar.md)имен.</span><span class="sxs-lookup"><span data-stu-id="5de3c-107">If you're not sure who your host is, see [Find your domain registrar](find-your-domain-registrar.md).</span></span>
  

## <a name="let-microsoft-365-manage-your-dns-records"></a><span data-ttu-id="5de3c-108">Разрешить Microsoft 365 управлять записями DNS</span><span class="sxs-lookup"><span data-stu-id="5de3c-108">Let Microsoft 365 manage your DNS records</span></span>

||
|---|---|
|[<span data-ttu-id="5de3c-109">1&1 ИОНОС</span><span class="sxs-lookup"><span data-stu-id="5de3c-109">1&1 IONOS</span></span>](../dns/change-nameservers-at-1-1-internet.md) |
|[<span data-ttu-id="5de3c-110">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="5de3c-110">Amazon Web Services (AWS)</span></span>](../dns/change-nameservers-at-aws.md) |
 [<span data-ttu-id="5de3c-111">Bluehost</span><span class="sxs-lookup"><span data-stu-id="5de3c-111">Bluehost</span></span>](../dns/change-nameservers-at-bluehost.md)|
|[<span data-ttu-id="5de3c-112">Домены Google</span><span class="sxs-lookup"><span data-stu-id="5de3c-112">Google   Domains</span></span>](../dns/change-nameservers-at-google-domains.md) |
|[<span data-ttu-id="5de3c-113">Hostgator</span><span class="sxs-lookup"><span data-stu-id="5de3c-113">Hostgator   </span></span>](../dns/change-nameservers-at-hostgator.md)  |  
|[<span data-ttu-id="5de3c-114">MyDomain</span><span class="sxs-lookup"><span data-stu-id="5de3c-114">MyDomain</span></span>](../dns/change-nameservers-at-mydomain.md) | 
|[<span data-ttu-id="5de3c-115">Namecheap</span><span class="sxs-lookup"><span data-stu-id="5de3c-115">Namecheap</span></span>](../dns/change-nameservers-at-namecheap.md)|
|[<span data-ttu-id="5de3c-116">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="5de3c-116">Network Solutions</span></span>](../dns/change-nameservers-at-network-solutions.md) |  

<span data-ttu-id="5de3c-117">Или Узнайте, как [изменить серверов доменных имен, чтобы настроить Microsoft 365 с помощью любого регистратора доменных](change-nameservers-at-any-domain-registrar.md)имен.</span><span class="sxs-lookup"><span data-stu-id="5de3c-117">Or, learn how to [change nameservers to set up Microsoft 365 with any domain registrar](change-nameservers-at-any-domain-registrar.md).</span></span>

## <a name="manage-your-own-dns-records"></a><span data-ttu-id="5de3c-118">Управление собственными записями DNS</span><span class="sxs-lookup"><span data-stu-id="5de3c-118">Manage your own DNS records</span></span>

|                           |                          |
|---------------------------|--------------------------|
| [<span data-ttu-id="5de3c-119">1&1 ИОНОС</span><span class="sxs-lookup"><span data-stu-id="5de3c-119">1&1 IONOS</span></span>](../dns/create-dns-records-at-1-1-internet.md) | [<span data-ttu-id="5de3c-120">Hover</span><span class="sxs-lookup"><span data-stu-id="5de3c-120">Hover</span></span>](../dns/create-dns-records-at-hover.md) |
| [<span data-ttu-id="5de3c-121">123-reg.co.uk</span><span class="sxs-lookup"><span data-stu-id="5de3c-121">123-reg.co.uk</span></span>](../dns/create-dns-records-at-123-reg-co-uk.md) | [<span data-ttu-id="5de3c-122">Управляется Google (eNom Central)</span><span class="sxs-lookup"><span data-stu-id="5de3c-122">Managed   by Google (eNom)</span></span>](../dns/create-dns-records-for-domain-managed-by-google-enom.md)|
| [<span data-ttu-id="5de3c-123">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="5de3c-123">Amazon Web Services (AWS)</span></span>](../dns/create-dns-records-at-aws.md) | [<span data-ttu-id="5de3c-124">MyDomain</span><span class="sxs-lookup"><span data-stu-id="5de3c-124">MyDomain</span></span>](../dns/create-dns-records-at-mydomain.md) |
| [<span data-ttu-id="5de3c-125">Зоны DNS Azure</span><span class="sxs-lookup"><span data-stu-id="5de3c-125">Azure DNS zones</span></span>](../dns/create-dns-records-for-azure-dns-zones.md) | [<span data-ttu-id="5de3c-126">name.com</span><span class="sxs-lookup"><span data-stu-id="5de3c-126">name.com</span></span>](../dns/create-dns-records-at-name-com.md) |
| [<span data-ttu-id="5de3c-127">Bluehost</span><span class="sxs-lookup"><span data-stu-id="5de3c-127">Bluehost</span></span>](../dns/create-dns-records-at-bluehost.md) | [<span data-ttu-id="5de3c-128">Namecheap</span><span class="sxs-lookup"><span data-stu-id="5de3c-128">Namecheap</span></span>](../dns/create-dns-records-at-namecheap.md)|
| [<span data-ttu-id="5de3c-129">CloudFlare</span><span class="sxs-lookup"><span data-stu-id="5de3c-129">Cloudflare</span></span>](../dns/create-dns-records-at-cloudflare.md)| [<span data-ttu-id="5de3c-130">Names.co.uk</span><span class="sxs-lookup"><span data-stu-id="5de3c-130">Names.co.uk</span></span>](../dns/create-dns-records-at-names-co-uk.md) |
|  [<span data-ttu-id="5de3c-131">Crazy Domains</span><span class="sxs-lookup"><span data-stu-id="5de3c-131">Crazy Domains</span></span>](../dns/create-dns-records-at-crazy-domains.md)| [<span data-ttu-id="5de3c-132">Netregistry</span><span class="sxs-lookup"><span data-stu-id="5de3c-132">Netregistry</span></span>](../dns/create-dns-records-at-netregistry.md) |
|[<span data-ttu-id="5de3c-133">DNSMadeEasy</span><span class="sxs-lookup"><span data-stu-id="5de3c-133">DNSMadeEasy</span></span>](../dns/create-dns-records-at-dnsmadeeasy.md) | [<span data-ttu-id="5de3c-134">Сетевые решения</span><span class="sxs-lookup"><span data-stu-id="5de3c-134">Network   Solutions</span></span>](../dns/create-dns-records-at-network-solutions.md) |
|[<span data-ttu-id="5de3c-135">Dreamhost</span><span class="sxs-lookup"><span data-stu-id="5de3c-135">Dreamhost</span></span>](../dns/create-dns-records-at-dreamhost.md)  | [<span data-ttu-id="5de3c-136">OVH</span><span class="sxs-lookup"><span data-stu-id="5de3c-136">OVH</span></span>](../dns/create-dns-records-at-ovh.md) |
|  [<span data-ttu-id="5de3c-137">Dyn.com</span><span class="sxs-lookup"><span data-stu-id="5de3c-137">Dyn.com</span></span>](../dns/create-dns-records-at-dyn-com.md) | [<span data-ttu-id="5de3c-138">Register.com</span><span class="sxs-lookup"><span data-stu-id="5de3c-138">Register.com</span></span>](../dns/create-dns-records-at-register-com.md) |
| [<span data-ttu-id="5de3c-139">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="5de3c-139">eNomCentral</span></span>](../dns/create-dns-records-at-enomcentral.md)| [<span data-ttu-id="5de3c-140">Register365 для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5de3c-140">Register365 for Microsoft 365</span></span>](../dns/create-dns-records-at-register365.md)  |
| [<span data-ttu-id="5de3c-141">Freenom</span><span class="sxs-lookup"><span data-stu-id="5de3c-141">Freenom</span></span>](../dns/create-dns-records-at-freenom.md) | [<span data-ttu-id="5de3c-142">web.com</span><span class="sxs-lookup"><span data-stu-id="5de3c-142"> web.com </span></span>](../dns/create-dns-records-at-web-com.md)|
|[<span data-ttu-id="5de3c-143">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="5de3c-143">GoDaddy</span></span>](../dns/create-dns-records-at-godaddy.md)|[<span data-ttu-id="5de3c-144">DNS-сервер под управлением Windows</span><span class="sxs-lookup"><span data-stu-id="5de3c-144"> Windows-based DNS</span></span>](../dns/create-dns-records-using-windows-based-dns.md)   |
| [<span data-ttu-id="5de3c-145">Google Domains</span><span class="sxs-lookup"><span data-stu-id="5de3c-145">Google Domains</span></span>](../dns/create-dns-records-at-google-domains.md) |[<span data-ttu-id="5de3c-146">Технологии</span><span class="sxs-lookup"><span data-stu-id="5de3c-146">Wix</span></span>](../dns/create-dns-records-at-wix.md) |
|[<span data-ttu-id="5de3c-147">Hostgator</span><span class="sxs-lookup"><span data-stu-id="5de3c-147">Hostgator</span></span>](../dns/create-dns-records-at-hostgator.md)  | [<span data-ttu-id="5de3c-148">Yahoo!   Малый бизнес</span><span class="sxs-lookup"><span data-stu-id="5de3c-148">Yahoo!   Small Business</span></span>](../dns/create-dns-records-at-yahoo-small-business.md)  |

[<span data-ttu-id="5de3c-149">Мне нужны общие инструкции, так как узел домена не включен в этот список.</span><span class="sxs-lookup"><span data-stu-id="5de3c-149">I need general instructions, because my domain host isn't on this list. </span></span>](create-dns-records-at-any-dns-hosting-provider.md)
   
