---
title: Записи DNS для Office 365 GCC High
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: Сводка. Записи DNS для Office 365 GCC High
hideEdit: true
ms.openlocfilehash: 9edcda4616d50d05331db0e2d6c4d89967b02fdc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693160"
---
# <a name="dns-records-for-office-365-gcc-high"></a><span data-ttu-id="b837a-103">Записи DNS для Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="b837a-103">DNS records for Office 365 GCC High</span></span>

<span data-ttu-id="b837a-104">*Эта статья применима к Office 365 GCC high и Microsoft 365 GCC High*</span><span class="sxs-lookup"><span data-stu-id="b837a-104">*This article applies to Office 365 GCC High and Microsoft 365 GCC High*</span></span>

<span data-ttu-id="b837a-105">В рамках onboarding to Office 365 GCC High вам потребуется добавить свои домены SMTP и SIP в клиента Online Services.</span><span class="sxs-lookup"><span data-stu-id="b837a-105">As part of onboarding to Office 365 GCC High, you will need to add your SMTP and SIP domains to your Online Services tenant.</span></span>  <span data-ttu-id="b837a-106">Это можно сделать с помощью New-MsolDomain в Azure AD PowerShell или с помощью портала правительственных служб [Azure](https://portal.azure.us) для запуска процесса добавления домена и доказывания права собственности.</span><span class="sxs-lookup"><span data-stu-id="b837a-106">You’ll do this using the New-MsolDomain cmdlet in Azure AD PowerShell or use the [Azure Government Portal](https://portal.azure.us) to start the process of adding the domain and proving ownership.</span></span>

<span data-ttu-id="b837a-107">После добавления доменов в клиента и проверки используйте следующие рекомендации, чтобы добавить соответствующие записи DNS для служб ниже.</span><span class="sxs-lookup"><span data-stu-id="b837a-107">Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below.</span></span>  <span data-ttu-id="b837a-108">Возможно, вам потребуется изменить приведенную ниже таблицу, чтобы соответствовать потребностям вашей организации в отношении входящие записи MX (s) и любой существующей записи автооткрытия Exchange(ы) у вас есть.</span><span class="sxs-lookup"><span data-stu-id="b837a-108">You may need to modify the below table to fit your organization’s needs with respect to the inbound MX record(s) and any existing Exchange Autodiscover record(s) you have in place.</span></span>  <span data-ttu-id="b837a-109">Мы настоятельно рекомендуем координировать эти записи DNS с вашей командой обмена сообщениями, чтобы избежать каких-либо отключений или неправильной доставки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="b837a-109">We strongly recommend coordinating these DNS records with your messaging team to avoid any outages or mis-delivery of email.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="b837a-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b837a-110">Exchange Online</span></span>

| <span data-ttu-id="b837a-111">Type (Тип)</span><span class="sxs-lookup"><span data-stu-id="b837a-111">Type</span></span> | <span data-ttu-id="b837a-112">Priority (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="b837a-112">Priority</span></span> | <span data-ttu-id="b837a-113">Имя узла</span><span class="sxs-lookup"><span data-stu-id="b837a-113">Host name</span></span> | <span data-ttu-id="b837a-114">Адрес или значение назначения</span><span class="sxs-lookup"><span data-stu-id="b837a-114">Points to address or value</span></span> | <span data-ttu-id="b837a-115">TTL</span><span class="sxs-lookup"><span data-stu-id="b837a-115">TTL</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="b837a-116">MX</span><span class="sxs-lookup"><span data-stu-id="b837a-116">MX</span></span> | <span data-ttu-id="b837a-117">0</span><span class="sxs-lookup"><span data-stu-id="b837a-117">0</span></span> | @ | <span data-ttu-id="b837a-118">*tenant*.mail.protection.office365.us (см. ниже дополнительные сведения)</span><span class="sxs-lookup"><span data-stu-id="b837a-118">*tenant*.mail.protection.office365.us (see below for additional details)</span></span> | <span data-ttu-id="b837a-119">1 Hour</span><span class="sxs-lookup"><span data-stu-id="b837a-119">1 Hour</span></span> |
| <span data-ttu-id="b837a-120">TXT</span><span class="sxs-lookup"><span data-stu-id="b837a-120">TXT</span></span> | - | @ | <span data-ttu-id="b837a-121">v=spf1 include:spf.protection.office365.us -all</span><span class="sxs-lookup"><span data-stu-id="b837a-121">v=spf1 include:spf.protection.office365.us -all</span></span> | <span data-ttu-id="b837a-122">1 час</span><span class="sxs-lookup"><span data-stu-id="b837a-122">1 Hour</span></span> |
| <span data-ttu-id="b837a-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="b837a-123">CNAME</span></span> | - | <span data-ttu-id="b837a-124">autodiscover</span><span class="sxs-lookup"><span data-stu-id="b837a-124">autodiscover</span></span> | <span data-ttu-id="b837a-125">autodiscover.office365.us</span><span class="sxs-lookup"><span data-stu-id="b837a-125">autodiscover.office365.us</span></span> | <span data-ttu-id="b837a-126">1 Hour</span><span class="sxs-lookup"><span data-stu-id="b837a-126">1 Hour</span></span> |

### <a name="exchange-autodiscover-record"></a><span data-ttu-id="b837a-127">Exchange Запись автооткрытия</span><span class="sxs-lookup"><span data-stu-id="b837a-127">Exchange Autodiscover record</span></span>

<span data-ttu-id="b837a-128">Если вы Exchange Server, рекомендуем оставить существующую запись на месте во время миграции в Exchange Online и обновить эту запись после завершения миграции.</span><span class="sxs-lookup"><span data-stu-id="b837a-128">If you have Exchange Server on-premises, we recommend leaving your existing record in place while you migrate to Exchange Online, and update that record once you have completed your migration.</span></span> 

### <a name="exchange-online-mx-record"></a><span data-ttu-id="b837a-129">Exchange Online Запись MX</span><span class="sxs-lookup"><span data-stu-id="b837a-129">Exchange Online MX Record</span></span>

<span data-ttu-id="b837a-130">Значение записи MX для принятых доменов следует стандартному формату, как отмечалось  выше: tenant .mail.protection.office365.us, заменив клиента первой частью имени клиента по умолчанию. </span><span class="sxs-lookup"><span data-stu-id="b837a-130">The MX record value for your accepted domains follows a standard format as noted above: *tenant*.mail.protection.office365.us, replacing *tenant* with the first part of your default tenant name.</span></span>

<span data-ttu-id="b837a-131">Например, если имя клиента contoso.onmicrosoft.us, вы contoso.mail.protection.office365.us значение  для записи MX.</span><span class="sxs-lookup"><span data-stu-id="b837a-131">For example, if your tenant name is contoso.onmicrosoft.us, you’d use **contoso.mail.protection.office365.us** as the value for your MX record.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="b837a-132">Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="b837a-132">Skype for Business Online</span></span>

### <a name="cname-records"></a><span data-ttu-id="b837a-133">Записи CNAME</span><span class="sxs-lookup"><span data-stu-id="b837a-133">CNAME records</span></span>

| <span data-ttu-id="b837a-134">Тип</span><span class="sxs-lookup"><span data-stu-id="b837a-134">Type</span></span> | <span data-ttu-id="b837a-135">Имя узла</span><span class="sxs-lookup"><span data-stu-id="b837a-135">Host name</span></span> | <span data-ttu-id="b837a-136">Адрес или значение назначения</span><span class="sxs-lookup"><span data-stu-id="b837a-136">Points to address or value</span></span> | <span data-ttu-id="b837a-137">TTL</span><span class="sxs-lookup"><span data-stu-id="b837a-137">TTL</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="b837a-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="b837a-138">CNAME</span></span> | <span data-ttu-id="b837a-139">sip</span><span class="sxs-lookup"><span data-stu-id="b837a-139">sip</span></span> | <span data-ttu-id="b837a-140">sipdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="b837a-140">sipdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="b837a-141">1 час</span><span class="sxs-lookup"><span data-stu-id="b837a-141">1 Hour</span></span> |
| <span data-ttu-id="b837a-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="b837a-142">CNAME</span></span> | <span data-ttu-id="b837a-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b837a-143">lyncdiscover</span></span> | <span data-ttu-id="b837a-144">webdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="b837a-144">webdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="b837a-145">1 Hour</span><span class="sxs-lookup"><span data-stu-id="b837a-145">1 Hour</span></span> |

### <a name="srv-records"></a><span data-ttu-id="b837a-146">Записи SRV</span><span class="sxs-lookup"><span data-stu-id="b837a-146">SRV records</span></span>

| <span data-ttu-id="b837a-147">Тип</span><span class="sxs-lookup"><span data-stu-id="b837a-147">Type</span></span> | <span data-ttu-id="b837a-148">Служба</span><span class="sxs-lookup"><span data-stu-id="b837a-148">Service</span></span> | <span data-ttu-id="b837a-149">Протокол</span><span class="sxs-lookup"><span data-stu-id="b837a-149">Protocol</span></span> | <span data-ttu-id="b837a-150">Порт</span><span class="sxs-lookup"><span data-stu-id="b837a-150">Port</span></span> | <span data-ttu-id="b837a-151">Насыщенность</span><span class="sxs-lookup"><span data-stu-id="b837a-151">Weight</span></span> | <span data-ttu-id="b837a-152">Priority</span><span class="sxs-lookup"><span data-stu-id="b837a-152">Priority</span></span> | <span data-ttu-id="b837a-153">Имя</span><span class="sxs-lookup"><span data-stu-id="b837a-153">Name</span></span> | <span data-ttu-id="b837a-154">Target</span><span class="sxs-lookup"><span data-stu-id="b837a-154">Target</span></span> | <span data-ttu-id="b837a-155">TTL</span><span class="sxs-lookup"><span data-stu-id="b837a-155">TTL</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <span data-ttu-id="b837a-156">SRV</span><span class="sxs-lookup"><span data-stu-id="b837a-156">SRV</span></span> | <span data-ttu-id="b837a-157">\_sip</span><span class="sxs-lookup"><span data-stu-id="b837a-157">\_sip</span></span> | <span data-ttu-id="b837a-158">\_tls</span><span class="sxs-lookup"><span data-stu-id="b837a-158">\_tls</span></span> | <span data-ttu-id="b837a-159">443</span><span class="sxs-lookup"><span data-stu-id="b837a-159">443</span></span> | <span data-ttu-id="b837a-160">1</span><span class="sxs-lookup"><span data-stu-id="b837a-160">1</span></span> | <span data-ttu-id="b837a-161">100</span><span class="sxs-lookup"><span data-stu-id="b837a-161">100</span></span> | @ | <span data-ttu-id="b837a-162">sipdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="b837a-162">sipdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="b837a-163">1 час</span><span class="sxs-lookup"><span data-stu-id="b837a-163">1 Hour</span></span> |
| <span data-ttu-id="b837a-164">SRV</span><span class="sxs-lookup"><span data-stu-id="b837a-164">SRV</span></span> | <span data-ttu-id="b837a-165">\_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="b837a-165">\_sipfederationtls</span></span> | <span data-ttu-id="b837a-166">\_tcp</span><span class="sxs-lookup"><span data-stu-id="b837a-166">\_tcp</span></span> | <span data-ttu-id="b837a-167">5061</span><span class="sxs-lookup"><span data-stu-id="b837a-167">5061</span></span> | <span data-ttu-id="b837a-168">1</span><span class="sxs-lookup"><span data-stu-id="b837a-168">1</span></span> | <span data-ttu-id="b837a-169">100</span><span class="sxs-lookup"><span data-stu-id="b837a-169">100</span></span> | @ | <span data-ttu-id="b837a-170">sipfed.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="b837a-170">sipfed.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="b837a-171">1 Hour</span><span class="sxs-lookup"><span data-stu-id="b837a-171">1 Hour</span></span> |

## <a name="additional-dns-records"></a><span data-ttu-id="b837a-172">Дополнительные записи DNS</span><span class="sxs-lookup"><span data-stu-id="b837a-172">Additional DNS records</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b837a-173">Если у вас есть существующая запись CNAME *msoid* в зоне DNS, необходимо удалить запись из DNS в это время. </span><span class="sxs-lookup"><span data-stu-id="b837a-173">If you have an existing *msoid* CNAME record in your DNS zone, you must **remove** the record from DNS at this time.</span></span>  <span data-ttu-id="b837a-174">Запись msoid несовместима с приложениями Microsoft 365 корпоративный *(ранее Office 365 профессиональный плюс)* и предотвратит успешное активацию.</span><span class="sxs-lookup"><span data-stu-id="b837a-174">The msoid record is incompatible with Microsoft 365 Enterprise Apps *(formerly Office 365 ProPlus)* and will prevent activation from succeeding.</span></span>
