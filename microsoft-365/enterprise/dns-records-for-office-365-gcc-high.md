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
# <a name="dns-records-for-office-365-gcc-high"></a><span data-ttu-id="d1bea-103">Записи DNS для Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="d1bea-103">DNS records for Office 365 GCC High</span></span>

<span data-ttu-id="d1bea-104">*Эта статья относится к Office 365 GCC High и Microsoft 365 GCC High*</span><span class="sxs-lookup"><span data-stu-id="d1bea-104">*This article applies to Office 365 GCC High and Microsoft 365 GCC High*</span></span>

<span data-ttu-id="d1bea-105">В рамках пользования Office 365 GCC High вам потребуется добавить домены SMTP и SIP в клиент Online Services.</span><span class="sxs-lookup"><span data-stu-id="d1bea-105">As part of onboarding to Office 365 GCC High, you will need to add your SMTP and SIP domains to your Online Services tenant.</span></span>  <span data-ttu-id="d1bea-106">Это можно сделать с помощью New-MsolDomain в Azure AD PowerShell или с помощью портала [Azure для](https://portal.azure.us) государственных служб, чтобы начать процесс добавления домена и доказательства владения.</span><span class="sxs-lookup"><span data-stu-id="d1bea-106">You’ll do this using the New-MsolDomain cmdlet in Azure AD PowerShell or use the [Azure Government Portal](https://portal.azure.us) to start the process of adding the domain and proving ownership.</span></span>

<span data-ttu-id="d1bea-107">После добавления доменов в клиент и проверки воспользуйтесь следующими рекомендациями, чтобы добавить соответствующие записи DNS для служб ниже.</span><span class="sxs-lookup"><span data-stu-id="d1bea-107">Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below.</span></span>  <span data-ttu-id="d1bea-108">Возможно, потребуется изменить приведенную ниже таблицу в учете потребностей организации в отношении входящие записи MX и существующих записей автообнаружия Exchange.</span><span class="sxs-lookup"><span data-stu-id="d1bea-108">You may need to modify the below table to fit your organization’s needs with respect to the inbound MX record(s) and any existing Exchange Autodiscover record(s) you have in place.</span></span>  <span data-ttu-id="d1bea-109">Мы настоятельно рекомендуем координировать эти записи DNS с вашей командой обмена сообщениями, чтобы избежать сставок или неправильной доставки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d1bea-109">We strongly recommend coordinating these DNS records with your messaging team to avoid any outages or mis-delivery of email.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="d1bea-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d1bea-110">Exchange Online</span></span>

| <span data-ttu-id="d1bea-111">Type (Тип)</span><span class="sxs-lookup"><span data-stu-id="d1bea-111">Type</span></span> | <span data-ttu-id="d1bea-112">Priority (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="d1bea-112">Priority</span></span> | <span data-ttu-id="d1bea-113">Имя узла</span><span class="sxs-lookup"><span data-stu-id="d1bea-113">Host name</span></span> | <span data-ttu-id="d1bea-114">Указывает на адрес или значение</span><span class="sxs-lookup"><span data-stu-id="d1bea-114">Points to address or value</span></span> | <span data-ttu-id="d1bea-115">TTL</span><span class="sxs-lookup"><span data-stu-id="d1bea-115">TTL</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="d1bea-116">MX</span><span class="sxs-lookup"><span data-stu-id="d1bea-116">MX</span></span> | <span data-ttu-id="d1bea-117">0</span><span class="sxs-lookup"><span data-stu-id="d1bea-117">0</span></span> | @ | <span data-ttu-id="d1bea-118">*tenant*.mail.protection.office365.us (дополнительные сведения см. ниже)</span><span class="sxs-lookup"><span data-stu-id="d1bea-118">*tenant*.mail.protection.office365.us (see below for additional details)</span></span> | <span data-ttu-id="d1bea-119">1 Hour</span><span class="sxs-lookup"><span data-stu-id="d1bea-119">1 Hour</span></span> |
| <span data-ttu-id="d1bea-120">TXT</span><span class="sxs-lookup"><span data-stu-id="d1bea-120">TXT</span></span> | - | @ | <span data-ttu-id="d1bea-121">v=spf1 include:spf.protection.office365.us -all</span><span class="sxs-lookup"><span data-stu-id="d1bea-121">v=spf1 include:spf.protection.office365.us -all</span></span> | <span data-ttu-id="d1bea-122">1 час</span><span class="sxs-lookup"><span data-stu-id="d1bea-122">1 Hour</span></span> |
| <span data-ttu-id="d1bea-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="d1bea-123">CNAME</span></span> | - | <span data-ttu-id="d1bea-124">autodiscover</span><span class="sxs-lookup"><span data-stu-id="d1bea-124">autodiscover</span></span> | <span data-ttu-id="d1bea-125">autodiscover.office365.us</span><span class="sxs-lookup"><span data-stu-id="d1bea-125">autodiscover.office365.us</span></span> | <span data-ttu-id="d1bea-126">1 Hour</span><span class="sxs-lookup"><span data-stu-id="d1bea-126">1 Hour</span></span> |

### <a name="exchange-autodiscover-record"></a><span data-ttu-id="d1bea-127">Запись автообнаружия Exchange</span><span class="sxs-lookup"><span data-stu-id="d1bea-127">Exchange Autodiscover record</span></span>

<span data-ttu-id="d1bea-128">Если вы Exchange Server локально, рекомендуем оставить существующую запись на месте при миграции в Exchange Online и обновить ее после завершения миграции.</span><span class="sxs-lookup"><span data-stu-id="d1bea-128">If you have Exchange Server on-premises, we recommend leaving your existing record in place while you migrate to Exchange Online, and update that record once you have completed your migration.</span></span> 

### <a name="exchange-online-mx-record"></a><span data-ttu-id="d1bea-129">Запись MX в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d1bea-129">Exchange Online MX Record</span></span>

<span data-ttu-id="d1bea-130">Значение записи MX для ваших принятых доменов следует стандартному формату, как  было отмечено выше: *tenant*.mail.protection.office365.us, заменив клиент первой частью имени клиента по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d1bea-130">The MX record value for your accepted domains follows a standard format as noted above: *tenant*.mail.protection.office365.us, replacing *tenant* with the first part of your default tenant name.</span></span>

<span data-ttu-id="d1bea-131">Например, если имя клиента contoso.onmicrosoft.us, необходимо использовать contoso.mail.protection.office365.us  в качестве значения для записи MX.</span><span class="sxs-lookup"><span data-stu-id="d1bea-131">For example, if your tenant name is contoso.onmicrosoft.us, you’d use **contoso.mail.protection.office365.us** as the value for your MX record.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="d1bea-132">Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="d1bea-132">Skype for Business Online</span></span>

### <a name="cname-records"></a><span data-ttu-id="d1bea-133">Записи CNAME</span><span class="sxs-lookup"><span data-stu-id="d1bea-133">CNAME records</span></span>

| <span data-ttu-id="d1bea-134">Type</span><span class="sxs-lookup"><span data-stu-id="d1bea-134">Type</span></span> | <span data-ttu-id="d1bea-135">Имя узла</span><span class="sxs-lookup"><span data-stu-id="d1bea-135">Host name</span></span> | <span data-ttu-id="d1bea-136">Указывает на адрес или значение</span><span class="sxs-lookup"><span data-stu-id="d1bea-136">Points to address or value</span></span> | <span data-ttu-id="d1bea-137">TTL</span><span class="sxs-lookup"><span data-stu-id="d1bea-137">TTL</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="d1bea-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="d1bea-138">CNAME</span></span> | <span data-ttu-id="d1bea-139">sip</span><span class="sxs-lookup"><span data-stu-id="d1bea-139">sip</span></span> | <span data-ttu-id="d1bea-140">sipdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="d1bea-140">sipdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="d1bea-141">1 час</span><span class="sxs-lookup"><span data-stu-id="d1bea-141">1 Hour</span></span> |
| <span data-ttu-id="d1bea-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="d1bea-142">CNAME</span></span> | <span data-ttu-id="d1bea-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d1bea-143">lyncdiscover</span></span> | <span data-ttu-id="d1bea-144">webdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="d1bea-144">webdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="d1bea-145">1 Hour</span><span class="sxs-lookup"><span data-stu-id="d1bea-145">1 Hour</span></span> |

### <a name="srv-records"></a><span data-ttu-id="d1bea-146">Записи SRV</span><span class="sxs-lookup"><span data-stu-id="d1bea-146">SRV records</span></span>

| <span data-ttu-id="d1bea-147">Type</span><span class="sxs-lookup"><span data-stu-id="d1bea-147">Type</span></span> | <span data-ttu-id="d1bea-148">Служба</span><span class="sxs-lookup"><span data-stu-id="d1bea-148">Service</span></span> | <span data-ttu-id="d1bea-149">Протокол</span><span class="sxs-lookup"><span data-stu-id="d1bea-149">Protocol</span></span> | <span data-ttu-id="d1bea-150">Порт</span><span class="sxs-lookup"><span data-stu-id="d1bea-150">Port</span></span> | <span data-ttu-id="d1bea-151">Насыщенность</span><span class="sxs-lookup"><span data-stu-id="d1bea-151">Weight</span></span> | <span data-ttu-id="d1bea-152">Priority</span><span class="sxs-lookup"><span data-stu-id="d1bea-152">Priority</span></span> | <span data-ttu-id="d1bea-153">Имя</span><span class="sxs-lookup"><span data-stu-id="d1bea-153">Name</span></span> | <span data-ttu-id="d1bea-154">Target</span><span class="sxs-lookup"><span data-stu-id="d1bea-154">Target</span></span> | <span data-ttu-id="d1bea-155">TTL</span><span class="sxs-lookup"><span data-stu-id="d1bea-155">TTL</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <span data-ttu-id="d1bea-156">SRV</span><span class="sxs-lookup"><span data-stu-id="d1bea-156">SRV</span></span> | <span data-ttu-id="d1bea-157">\_sip</span><span class="sxs-lookup"><span data-stu-id="d1bea-157">\_sip</span></span> | <span data-ttu-id="d1bea-158">\_tls</span><span class="sxs-lookup"><span data-stu-id="d1bea-158">\_tls</span></span> | <span data-ttu-id="d1bea-159">443</span><span class="sxs-lookup"><span data-stu-id="d1bea-159">443</span></span> | <span data-ttu-id="d1bea-160">1 </span><span class="sxs-lookup"><span data-stu-id="d1bea-160">1</span></span> | <span data-ttu-id="d1bea-161">100</span><span class="sxs-lookup"><span data-stu-id="d1bea-161">100</span></span> | @ | <span data-ttu-id="d1bea-162">sipdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="d1bea-162">sipdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="d1bea-163">1 час</span><span class="sxs-lookup"><span data-stu-id="d1bea-163">1 Hour</span></span> |
| <span data-ttu-id="d1bea-164">SRV</span><span class="sxs-lookup"><span data-stu-id="d1bea-164">SRV</span></span> | <span data-ttu-id="d1bea-165">\_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="d1bea-165">\_sipfederationtls</span></span> | <span data-ttu-id="d1bea-166">\_tcp</span><span class="sxs-lookup"><span data-stu-id="d1bea-166">\_tcp</span></span> | <span data-ttu-id="d1bea-167">5061</span><span class="sxs-lookup"><span data-stu-id="d1bea-167">5061</span></span> | <span data-ttu-id="d1bea-168">1 </span><span class="sxs-lookup"><span data-stu-id="d1bea-168">1</span></span> | <span data-ttu-id="d1bea-169">100</span><span class="sxs-lookup"><span data-stu-id="d1bea-169">100</span></span> | @ | <span data-ttu-id="d1bea-170">sipfed.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="d1bea-170">sipfed.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="d1bea-171">1 Hour</span><span class="sxs-lookup"><span data-stu-id="d1bea-171">1 Hour</span></span> |

## <a name="additional-dns-records"></a><span data-ttu-id="d1bea-172">Дополнительные записи DNS</span><span class="sxs-lookup"><span data-stu-id="d1bea-172">Additional DNS records</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1bea-173">Если в зоне DNS есть существующая запись *MSOID* CNAME, ее необходимо удалить из DNS. </span><span class="sxs-lookup"><span data-stu-id="d1bea-173">If you have an existing *msoid* CNAME record in your DNS zone, you must **remove** the record from DNS at this time.</span></span>  <span data-ttu-id="d1bea-174">Запись msoid несовместима с Microsoft 365 корпоративные приложения *(ранее Office 365 профессиональныйplus)* и предотвратит успешное активацию.</span><span class="sxs-lookup"><span data-stu-id="d1bea-174">The msoid record is incompatible with Microsoft 365 Enterprise Apps *(formerly Office 365 ProPlus)* and will prevent activation from succeeding.</span></span>
