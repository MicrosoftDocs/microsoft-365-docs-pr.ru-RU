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
ms.openlocfilehash: 1b82fd40556b1bf828f9f367aa1175f21723cc8c
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399888"
---
# <a name="set-up-your-domain-host-specific-instructions"></a><span data-ttu-id="1f294-103">Настройка домена (инструкции для конкретных узлов)</span><span class="sxs-lookup"><span data-stu-id="1f294-103">Set up your domain (host-specific instructions)</span></span>

<span data-ttu-id="1f294-104">Чтобы приступить к работе с пользовательским доменом (contoso.com) с Office 365, необходимо проверить домен и настроить записи DNS вашего домена.</span><span class="sxs-lookup"><span data-stu-id="1f294-104">To start using a custom domain (contoso.com) with Office 365, you need to verify your domain and configure your domain's DNS records.</span></span> 
  
<span data-ttu-id="1f294-105">Вы можете добавлять DNS-записи и управлять ими с помощью средств администрирования на узле домена, а также предоставлять Майкрософт управление записями домена, а также настроить их для вас.</span><span class="sxs-lookup"><span data-stu-id="1f294-105">You can add and manage DNS records using the administrative tools at your domain host, or give Microsoft control of your domain records and we'll set them up for you.</span></span>
  
<span data-ttu-id="1f294-106">Выберите узел домена ниже, чтобы выполнить точные действия.</span><span class="sxs-lookup"><span data-stu-id="1f294-106">Select your domain host below for the exact steps.</span></span> <span data-ttu-id="1f294-107">Если вы не знаете, что такое ваш узел, ознакомьтесь со статьей [Поиск регистратора доменных](find-your-domain-registrar.md)имен.</span><span class="sxs-lookup"><span data-stu-id="1f294-107">If you're not sure who your host is, see [Find your domain registrar](find-your-domain-registrar.md).</span></span>
  

## <a name="let-office-365-manage-your-dns-records"></a><span data-ttu-id="1f294-108">Разрешите Office 365 управлять записями DNS</span><span class="sxs-lookup"><span data-stu-id="1f294-108">Let Office 365 manage your DNS records</span></span>

||
|---|---|
|[<span data-ttu-id="1f294-109">1&1 ИОНОС</span><span class="sxs-lookup"><span data-stu-id="1f294-109">1&1 IONOS</span></span>](../dns/change-nameservers-at-1-1-internet.md) |
|[<span data-ttu-id="1f294-110">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="1f294-110">Amazon Web Services (AWS)</span></span>](../dns/change-nameservers-at-aws.md) |
 [<span data-ttu-id="1f294-111">Bluehost</span><span class="sxs-lookup"><span data-stu-id="1f294-111">Bluehost</span></span>](../dns/change-nameservers-at-bluehost.md)|
|[<span data-ttu-id="1f294-112">Домены Google</span><span class="sxs-lookup"><span data-stu-id="1f294-112">Google   Domains</span></span>](../dns/change-nameservers-at-google-domains.md) |
|[<span data-ttu-id="1f294-113">Hostgator</span><span class="sxs-lookup"><span data-stu-id="1f294-113">Hostgator   </span></span>](../dns/change-nameservers-at-hostgator.md)  |  
|[<span data-ttu-id="1f294-114">MyDomain</span><span class="sxs-lookup"><span data-stu-id="1f294-114">MyDomain</span></span>](../dns/change-nameservers-at-mydomain.md) | 
|[<span data-ttu-id="1f294-115">Namecheap</span><span class="sxs-lookup"><span data-stu-id="1f294-115">Namecheap</span></span>](../dns/change-nameservers-at-namecheap.md)|
|[<span data-ttu-id="1f294-116">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="1f294-116">Network Solutions</span></span>](../dns/change-nameservers-at-network-solutions.md) |  

<span data-ttu-id="1f294-117">Или Узнайте, как [изменить серверов доменных имен, чтобы настроить Office 365 с помощью любого регистратора доменных](change-nameservers-at-any-domain-registrar.md)имен.</span><span class="sxs-lookup"><span data-stu-id="1f294-117">Or, learn how to [change nameservers to set up Office 365 with any domain registrar](change-nameservers-at-any-domain-registrar.md).</span></span>

## <a name="manage-your-own-dns-records"></a><span data-ttu-id="1f294-118">Управление собственными записями DNS</span><span class="sxs-lookup"><span data-stu-id="1f294-118">Manage your own DNS records</span></span>

|                           |                          |
|---------------------------|--------------------------|
| [<span data-ttu-id="1f294-119">1&1 ИОНОС</span><span class="sxs-lookup"><span data-stu-id="1f294-119">1&1 IONOS</span></span>](../dns/create-dns-records-at-1-1-internet.md) | [<span data-ttu-id="1f294-120">Hover</span><span class="sxs-lookup"><span data-stu-id="1f294-120">Hover</span></span>](../dns/create-dns-records-at-hover.md) |
| [<span data-ttu-id="1f294-121">123-reg.co.uk</span><span class="sxs-lookup"><span data-stu-id="1f294-121">123-reg.co.uk</span></span>](../dns/create-dns-records-at-123-reg-co-uk.md) | [<span data-ttu-id="1f294-122">Управляется Google (eNom Central)</span><span class="sxs-lookup"><span data-stu-id="1f294-122">Managed   by Google (eNom)</span></span>](../dns/create-dns-records-for-domain-managed-by-google-enom.md)|
| [<span data-ttu-id="1f294-123">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="1f294-123">Amazon Web Services (AWS)</span></span>](../dns/create-dns-records-at-aws.md) | [<span data-ttu-id="1f294-124">MyDomain</span><span class="sxs-lookup"><span data-stu-id="1f294-124">MyDomain</span></span>](../dns/create-dns-records-at-mydomain.md) |
| [<span data-ttu-id="1f294-125">Зоны DNS Azure</span><span class="sxs-lookup"><span data-stu-id="1f294-125">Azure DNS zones</span></span>](../dns/create-dns-records-for-azure-dns-zones.md) | [<span data-ttu-id="1f294-126">name.com</span><span class="sxs-lookup"><span data-stu-id="1f294-126">name.com</span></span>](../dns/create-dns-records-at-name-com.md) |
| [<span data-ttu-id="1f294-127">Bluehost</span><span class="sxs-lookup"><span data-stu-id="1f294-127">Bluehost</span></span>](../dns/create-dns-records-at-bluehost.md) | [<span data-ttu-id="1f294-128">Namecheap</span><span class="sxs-lookup"><span data-stu-id="1f294-128">Namecheap</span></span>](../dns/create-dns-records-at-namecheap.md)|
| [<span data-ttu-id="1f294-129">CloudFlare</span><span class="sxs-lookup"><span data-stu-id="1f294-129">Cloudflare</span></span>](../dns/create-dns-records-at-cloudflare.md)| [<span data-ttu-id="1f294-130">Names.co.uk</span><span class="sxs-lookup"><span data-stu-id="1f294-130">Names.co.uk</span></span>](../dns/create-dns-records-at-names-co-uk.md) |
|  [<span data-ttu-id="1f294-131">Crazy Domains</span><span class="sxs-lookup"><span data-stu-id="1f294-131">Crazy Domains</span></span>](../dns/create-dns-records-at-crazy-domains.md)| [<span data-ttu-id="1f294-132">Netregistry</span><span class="sxs-lookup"><span data-stu-id="1f294-132">Netregistry</span></span>](../dns/create-dns-records-at-netregistry.md) |
|[<span data-ttu-id="1f294-133">DNSMadeEasy</span><span class="sxs-lookup"><span data-stu-id="1f294-133">DNSMadeEasy</span></span>](../dns/create-dns-records-at-dnsmadeeasy.md) | [<span data-ttu-id="1f294-134">Сетевые решения</span><span class="sxs-lookup"><span data-stu-id="1f294-134">Network   Solutions</span></span>](../dns/create-dns-records-at-network-solutions.md) |
|[<span data-ttu-id="1f294-135">Dreamhost</span><span class="sxs-lookup"><span data-stu-id="1f294-135">Dreamhost</span></span>](../dns/create-dns-records-at-dreamhost.md)  | [<span data-ttu-id="1f294-136">OVH</span><span class="sxs-lookup"><span data-stu-id="1f294-136">OVH</span></span>](../dns/create-dns-records-at-ovh.md) |
|  [<span data-ttu-id="1f294-137">Dyn.com</span><span class="sxs-lookup"><span data-stu-id="1f294-137">Dyn.com</span></span>](../dns/create-dns-records-at-dyn-com.md) | [<span data-ttu-id="1f294-138">Register.com</span><span class="sxs-lookup"><span data-stu-id="1f294-138">Register.com</span></span>](../dns/create-dns-records-at-register-com.md) |
| [<span data-ttu-id="1f294-139">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="1f294-139">eNomCentral</span></span>](../dns/create-dns-records-at-enomcentral.md)| [<span data-ttu-id="1f294-140">Register365 для Office 365</span><span class="sxs-lookup"><span data-stu-id="1f294-140">Register365 for Office 365</span></span>](../dns/create-dns-records-at-register365.md)  |
| [<span data-ttu-id="1f294-141">Freenom</span><span class="sxs-lookup"><span data-stu-id="1f294-141">Freenom</span></span>](../dns/create-dns-records-at-freenom.md) | [<span data-ttu-id="1f294-142">web.com</span><span class="sxs-lookup"><span data-stu-id="1f294-142"> web.com </span></span>](../dns/create-dns-records-at-web-com.md)|
|[<span data-ttu-id="1f294-143">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="1f294-143">GoDaddy</span></span>](../dns/create-dns-records-at-godaddy.md)|[<span data-ttu-id="1f294-144">DNS-сервер под управлением Windows</span><span class="sxs-lookup"><span data-stu-id="1f294-144"> Windows-based DNS</span></span>](../dns/create-dns-records-using-windows-based-dns.md)   |
| [<span data-ttu-id="1f294-145">Google Domains</span><span class="sxs-lookup"><span data-stu-id="1f294-145">Google Domains</span></span>](../dns/create-dns-records-at-google-domains.md) |[<span data-ttu-id="1f294-146">Технологии</span><span class="sxs-lookup"><span data-stu-id="1f294-146">Wix</span></span>](../dns/create-dns-records-at-wix.md) |
|[<span data-ttu-id="1f294-147">Hostgator</span><span class="sxs-lookup"><span data-stu-id="1f294-147">Hostgator</span></span>](../dns/create-dns-records-at-hostgator.md)  | [<span data-ttu-id="1f294-148">Yahoo!   Малый бизнес</span><span class="sxs-lookup"><span data-stu-id="1f294-148">Yahoo!   Small Business</span></span>](../dns/create-dns-records-at-yahoo-small-business.md)  |

[<span data-ttu-id="1f294-149">Мне нужны общие инструкции, так как узел домена не включен в этот список.</span><span class="sxs-lookup"><span data-stu-id="1f294-149">I need general instructions, because my domain host isn't on this list. </span></span>](create-dns-records-at-any-dns-hosting-provider.md)
   
