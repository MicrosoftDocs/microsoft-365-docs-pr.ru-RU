---
title: Записи DNS для Office 365 DoD
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
description: Сводка. Записи DNS для Office 365 DoD
hideEdit: true
ms.openlocfilehash: 656fb5aff3365dfb5f975f7d3ad1c222b36e1e56
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693171"
---
# <a name="dns-records-for-office-365-dod"></a><span data-ttu-id="4c66c-103">Записи DNS для Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="4c66c-103">DNS records for Office 365 DoD</span></span>

<span data-ttu-id="4c66c-104">*Эта статья применяется к Office 365 и Microsoft 365 DoD*</span><span class="sxs-lookup"><span data-stu-id="4c66c-104">*This article applies to Office 365 DoD and Microsoft 365 DoD*</span></span>

<span data-ttu-id="4c66c-105">В рамках onboarding Office 365 DoD необходимо добавить свои домены SMTP и SIP в клиента Online Services.</span><span class="sxs-lookup"><span data-stu-id="4c66c-105">As part of onboarding to Office 365 DoD, you will need to add your SMTP and SIP domains to your Online Services tenant.</span></span>  <span data-ttu-id="4c66c-106">Это можно сделать с помощью New-MsolDomain в Azure AD PowerShell или с помощью портала правительственных служб [Azure](https://portal.azure.us) для запуска процесса добавления домена и доказывания права собственности.</span><span class="sxs-lookup"><span data-stu-id="4c66c-106">You’ll do this using the New-MsolDomain cmdlet in Azure AD PowerShell or use the [Azure Government Portal](https://portal.azure.us) to start the process of adding the domain and proving ownership.</span></span>

<span data-ttu-id="4c66c-107">После добавления доменов в клиента и проверки используйте следующие рекомендации, чтобы добавить соответствующие записи DNS для служб ниже.</span><span class="sxs-lookup"><span data-stu-id="4c66c-107">Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below.</span></span>  <span data-ttu-id="4c66c-108">Возможно, вам потребуется изменить приведенную ниже таблицу, чтобы соответствовать потребностям вашей организации в отношении входящие записи MX (s) и любой существующей записи автооткрытия Exchange(ы) у вас есть.</span><span class="sxs-lookup"><span data-stu-id="4c66c-108">You may need to modify the below table to fit your organization’s needs with respect to the inbound MX record(s) and any existing Exchange Autodiscover record(s) you have in place.</span></span>  <span data-ttu-id="4c66c-109">Мы настоятельно рекомендуем координировать эти записи DNS с вашей командой обмена сообщениями, чтобы избежать каких-либо отключений или неправильной доставки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4c66c-109">We strongly recommend coordinating these DNS records with your messaging team to avoid any outages or mis-delivery of email.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="4c66c-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4c66c-110">Exchange Online</span></span>

| <span data-ttu-id="4c66c-111">Type (Тип)</span><span class="sxs-lookup"><span data-stu-id="4c66c-111">Type</span></span> | <span data-ttu-id="4c66c-112">Priority (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="4c66c-112">Priority</span></span> | <span data-ttu-id="4c66c-113">Имя узла</span><span class="sxs-lookup"><span data-stu-id="4c66c-113">Host name</span></span> | <span data-ttu-id="4c66c-114">Адрес или значение назначения</span><span class="sxs-lookup"><span data-stu-id="4c66c-114">Points to address or value</span></span> | <span data-ttu-id="4c66c-115">TTL</span><span class="sxs-lookup"><span data-stu-id="4c66c-115">TTL</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="4c66c-116">MX</span><span class="sxs-lookup"><span data-stu-id="4c66c-116">MX</span></span> | <span data-ttu-id="4c66c-117">0</span><span class="sxs-lookup"><span data-stu-id="4c66c-117">0</span></span> | @ | <span data-ttu-id="4c66c-118">*tenant*.mail.protection.office365.us (см. ниже дополнительные сведения)</span><span class="sxs-lookup"><span data-stu-id="4c66c-118">*tenant*.mail.protection.office365.us (see below for additional details)</span></span> | <span data-ttu-id="4c66c-119">1 Hour</span><span class="sxs-lookup"><span data-stu-id="4c66c-119">1 Hour</span></span> |
| <span data-ttu-id="4c66c-120">TXT</span><span class="sxs-lookup"><span data-stu-id="4c66c-120">TXT</span></span> | - | @ | <span data-ttu-id="4c66c-121">v=spf1 include:spf.protection.office365.us -all</span><span class="sxs-lookup"><span data-stu-id="4c66c-121">v=spf1 include:spf.protection.office365.us -all</span></span> | <span data-ttu-id="4c66c-122">1 час</span><span class="sxs-lookup"><span data-stu-id="4c66c-122">1 Hour</span></span> |
| <span data-ttu-id="4c66c-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="4c66c-123">CNAME</span></span> | - | <span data-ttu-id="4c66c-124">autodiscover</span><span class="sxs-lookup"><span data-stu-id="4c66c-124">autodiscover</span></span> | <span data-ttu-id="4c66c-125">autodiscover-dod.office365.us</span><span class="sxs-lookup"><span data-stu-id="4c66c-125">autodiscover-dod.office365.us</span></span> | <span data-ttu-id="4c66c-126">1 Hour</span><span class="sxs-lookup"><span data-stu-id="4c66c-126">1 Hour</span></span> |

### <a name="exchange-autodiscover-record"></a><span data-ttu-id="4c66c-127">Exchange Запись автооткрытия</span><span class="sxs-lookup"><span data-stu-id="4c66c-127">Exchange Autodiscover record</span></span>

<span data-ttu-id="4c66c-128">Если вы Exchange Server, рекомендуем оставить существующую запись на месте во время миграции в Exchange Online и обновить эту запись после завершения миграции.</span><span class="sxs-lookup"><span data-stu-id="4c66c-128">If you have Exchange Server on-premises, we recommend leaving your existing record in place while you migrate to Exchange Online, and update that record once you have completed your migration.</span></span>

### <a name="exchange-online-mx-record"></a><span data-ttu-id="4c66c-129">Exchange Online Запись MX</span><span class="sxs-lookup"><span data-stu-id="4c66c-129">Exchange Online MX Record</span></span>

<span data-ttu-id="4c66c-130">Значение записи MX для принятых доменов следует стандартному формату, как отмечалось  выше: tenant .mail.protection.office365.us, заменив клиента первой частью имени клиента по умолчанию. </span><span class="sxs-lookup"><span data-stu-id="4c66c-130">The MX record value for your accepted domains follows a standard format as noted above: *tenant*.mail.protection.office365.us, replacing *tenant* with the first part of your default tenant name.</span></span>

<span data-ttu-id="4c66c-131">Например, если имя клиента contoso.onmicrosoft.us, вы contoso.mail.protection.office365.us значение  для записи MX.</span><span class="sxs-lookup"><span data-stu-id="4c66c-131">For example, if your tenant name is contoso.onmicrosoft.us, you’d use **contoso.mail.protection.office365.us** as the value for your MX record.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="4c66c-132">Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="4c66c-132">Skype for Business Online</span></span>

### <a name="cname-records"></a><span data-ttu-id="4c66c-133">Записи CNAME</span><span class="sxs-lookup"><span data-stu-id="4c66c-133">CNAME records</span></span>

| <span data-ttu-id="4c66c-134">Тип</span><span class="sxs-lookup"><span data-stu-id="4c66c-134">Type</span></span> | <span data-ttu-id="4c66c-135">Имя узла</span><span class="sxs-lookup"><span data-stu-id="4c66c-135">Host name</span></span> | <span data-ttu-id="4c66c-136">Адрес или значение назначения</span><span class="sxs-lookup"><span data-stu-id="4c66c-136">Points to address or value</span></span> | <span data-ttu-id="4c66c-137">TTL</span><span class="sxs-lookup"><span data-stu-id="4c66c-137">TTL</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="4c66c-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="4c66c-138">CNAME</span></span> | <span data-ttu-id="4c66c-139">sip</span><span class="sxs-lookup"><span data-stu-id="4c66c-139">sip</span></span> | <span data-ttu-id="4c66c-140">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="4c66c-140">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="4c66c-141">1 час</span><span class="sxs-lookup"><span data-stu-id="4c66c-141">1 Hour</span></span> |
| <span data-ttu-id="4c66c-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="4c66c-142">CNAME</span></span> | <span data-ttu-id="4c66c-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="4c66c-143">lyncdiscover</span></span> | <span data-ttu-id="4c66c-144">webdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="4c66c-144">webdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="4c66c-145">1 Hour</span><span class="sxs-lookup"><span data-stu-id="4c66c-145">1 Hour</span></span> | 

### <a name="srv-records"></a><span data-ttu-id="4c66c-146">Записи SRV</span><span class="sxs-lookup"><span data-stu-id="4c66c-146">SRV records</span></span>

| <span data-ttu-id="4c66c-147">Тип</span><span class="sxs-lookup"><span data-stu-id="4c66c-147">Type</span></span> | <span data-ttu-id="4c66c-148">Служба</span><span class="sxs-lookup"><span data-stu-id="4c66c-148">Service</span></span> | <span data-ttu-id="4c66c-149">Протокол</span><span class="sxs-lookup"><span data-stu-id="4c66c-149">Protocol</span></span> | <span data-ttu-id="4c66c-150">Порт</span><span class="sxs-lookup"><span data-stu-id="4c66c-150">Port</span></span> | <span data-ttu-id="4c66c-151">Насыщенность</span><span class="sxs-lookup"><span data-stu-id="4c66c-151">Weight</span></span> | <span data-ttu-id="4c66c-152">Priority</span><span class="sxs-lookup"><span data-stu-id="4c66c-152">Priority</span></span> | <span data-ttu-id="4c66c-153">Имя</span><span class="sxs-lookup"><span data-stu-id="4c66c-153">Name</span></span> | <span data-ttu-id="4c66c-154">Target</span><span class="sxs-lookup"><span data-stu-id="4c66c-154">Target</span></span> | <span data-ttu-id="4c66c-155">TTL</span><span class="sxs-lookup"><span data-stu-id="4c66c-155">TTL</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <span data-ttu-id="4c66c-156">SRV</span><span class="sxs-lookup"><span data-stu-id="4c66c-156">SRV</span></span> | <span data-ttu-id="4c66c-157">\_sip</span><span class="sxs-lookup"><span data-stu-id="4c66c-157">\_sip</span></span> | <span data-ttu-id="4c66c-158">\_tls</span><span class="sxs-lookup"><span data-stu-id="4c66c-158">\_tls</span></span> | <span data-ttu-id="4c66c-159">443</span><span class="sxs-lookup"><span data-stu-id="4c66c-159">443</span></span> | <span data-ttu-id="4c66c-160">1</span><span class="sxs-lookup"><span data-stu-id="4c66c-160">1</span></span> | <span data-ttu-id="4c66c-161">100</span><span class="sxs-lookup"><span data-stu-id="4c66c-161">100</span></span> | @ | <span data-ttu-id="4c66c-162">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="4c66c-162">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="4c66c-163">1 час</span><span class="sxs-lookup"><span data-stu-id="4c66c-163">1 Hour</span></span> |
| <span data-ttu-id="4c66c-164">SRV</span><span class="sxs-lookup"><span data-stu-id="4c66c-164">SRV</span></span> | <span data-ttu-id="4c66c-165">\_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="4c66c-165">\_sipfederationtls</span></span> | <span data-ttu-id="4c66c-166">\_tcp</span><span class="sxs-lookup"><span data-stu-id="4c66c-166">\_tcp</span></span> | <span data-ttu-id="4c66c-167">5061</span><span class="sxs-lookup"><span data-stu-id="4c66c-167">5061</span></span> | <span data-ttu-id="4c66c-168">1</span><span class="sxs-lookup"><span data-stu-id="4c66c-168">1</span></span> | <span data-ttu-id="4c66c-169">100</span><span class="sxs-lookup"><span data-stu-id="4c66c-169">100</span></span> | @ | <span data-ttu-id="4c66c-170">sipfed.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="4c66c-170">sipfed.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="4c66c-171">1 Hour</span><span class="sxs-lookup"><span data-stu-id="4c66c-171">1 Hour</span></span> |

## <a name="additional-dns-records"></a><span data-ttu-id="4c66c-172">Дополнительные записи DNS</span><span class="sxs-lookup"><span data-stu-id="4c66c-172">Additional DNS records</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c66c-173">Если у вас есть существующая запись CNAME *msoid* в зоне DNS, необходимо удалить запись из DNS в это время. </span><span class="sxs-lookup"><span data-stu-id="4c66c-173">If you have an existing *msoid* CNAME record in your DNS zone, you must **remove** the record from DNS at this time.</span></span>  <span data-ttu-id="4c66c-174">Запись msoid несовместима с приложениями Microsoft 365 корпоративный *(ранее Office 365 профессиональный плюс)* и предотвратит успешное активацию.</span><span class="sxs-lookup"><span data-stu-id="4c66c-174">The msoid record is incompatible with Microsoft 365 Enterprise Apps *(formerly Office 365 ProPlus)* and will prevent activation from succeeding.</span></span>
