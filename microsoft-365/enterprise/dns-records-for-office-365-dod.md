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
description: 'Сводка: записи DNS для Office 365 DoD'
hideEdit: true
ms.openlocfilehash: 656fb5aff3365dfb5f975f7d3ad1c222b36e1e56
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693171"
---
# <a name="dns-records-for-office-365-dod"></a><span data-ttu-id="21670-103">Записи DNS для Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="21670-103">DNS records for Office 365 DoD</span></span>

<span data-ttu-id="21670-104">*Эта статья относится к Office 365 DoD и Microsoft 365 DoD*</span><span class="sxs-lookup"><span data-stu-id="21670-104">*This article applies to Office 365 DoD and Microsoft 365 DoD*</span></span>

<span data-ttu-id="21670-105">В процессе входящей миграции в Office 365 DoD необходимо добавить домены SMTP и SIP в клиент Интернет-служб.</span><span class="sxs-lookup"><span data-stu-id="21670-105">As part of onboarding to Office 365 DoD, you will need to add your SMTP and SIP domains to your Online Services tenant.</span></span>  <span data-ttu-id="21670-106">Это можно сделать с помощью командлета New – Мсолдомаин в Azure AD PowerShell или на [портале для государственных учреждений Azure](https://portal.azure.us) , чтобы начать процесс добавления домена и подтверждения владения.</span><span class="sxs-lookup"><span data-stu-id="21670-106">You’ll do this using the New-MsolDomain cmdlet in Azure AD PowerShell or use the [Azure Government Portal](https://portal.azure.us) to start the process of adding the domain and proving ownership.</span></span>

<span data-ttu-id="21670-107">После добавления доменов к клиенту и проверки подлинности добавьте соответствующие записи DNS для служб ниже, следуя приведенным ниже рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="21670-107">Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below.</span></span>  <span data-ttu-id="21670-108">Возможно, вам потребуется изменить приведенную ниже таблицу в соответствии с потребностями Организации относительно входящих записей MX и всех имеющихся записей автообнаружения Exchange.</span><span class="sxs-lookup"><span data-stu-id="21670-108">You may need to modify the below table to fit your organization’s needs with respect to the inbound MX record(s) and any existing Exchange Autodiscover record(s) you have in place.</span></span>  <span data-ttu-id="21670-109">Мы настоятельно рекомендуем координировать эти записи DNS с помощью команды обмена сообщениями, чтобы избежать каких-либо непростостей или неправильной доставки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="21670-109">We strongly recommend coordinating these DNS records with your messaging team to avoid any outages or mis-delivery of email.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="21670-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="21670-110">Exchange Online</span></span>

| <span data-ttu-id="21670-111">Type (Тип)</span><span class="sxs-lookup"><span data-stu-id="21670-111">Type</span></span> | <span data-ttu-id="21670-112">Priority (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="21670-112">Priority</span></span> | <span data-ttu-id="21670-113">Имя узла</span><span class="sxs-lookup"><span data-stu-id="21670-113">Host name</span></span> | <span data-ttu-id="21670-114">Указывает на адрес или значение</span><span class="sxs-lookup"><span data-stu-id="21670-114">Points to address or value</span></span> | <span data-ttu-id="21670-115">TTL</span><span class="sxs-lookup"><span data-stu-id="21670-115">TTL</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="21670-116">MX</span><span class="sxs-lookup"><span data-stu-id="21670-116">MX</span></span> | <span data-ttu-id="21670-117">нуль</span><span class="sxs-lookup"><span data-stu-id="21670-117">0</span></span> | @ | <span data-ttu-id="21670-118">*клиент*. mail.Protection.Office365.US (Дополнительные сведения см. ниже)</span><span class="sxs-lookup"><span data-stu-id="21670-118">*tenant*.mail.protection.office365.us (see below for additional details)</span></span> | <span data-ttu-id="21670-119">1 Hour</span><span class="sxs-lookup"><span data-stu-id="21670-119">1 Hour</span></span> |
| <span data-ttu-id="21670-120">TXT</span><span class="sxs-lookup"><span data-stu-id="21670-120">TXT</span></span> | - | @ | <span data-ttu-id="21670-121">v = spf1 включение:SPF. Protection. Office365. US — ALL</span><span class="sxs-lookup"><span data-stu-id="21670-121">v=spf1 include:spf.protection.office365.us -all</span></span> | <span data-ttu-id="21670-122">1 час</span><span class="sxs-lookup"><span data-stu-id="21670-122">1 Hour</span></span> |
| <span data-ttu-id="21670-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="21670-123">CNAME</span></span> | - | <span data-ttu-id="21670-124">autodiscover</span><span class="sxs-lookup"><span data-stu-id="21670-124">autodiscover</span></span> | <span data-ttu-id="21670-125">autodiscover-dod.office365.us</span><span class="sxs-lookup"><span data-stu-id="21670-125">autodiscover-dod.office365.us</span></span> | <span data-ttu-id="21670-126">1 Hour</span><span class="sxs-lookup"><span data-stu-id="21670-126">1 Hour</span></span> |

### <a name="exchange-autodiscover-record"></a><span data-ttu-id="21670-127">Запись автообнаружения Exchange</span><span class="sxs-lookup"><span data-stu-id="21670-127">Exchange Autodiscover record</span></span>

<span data-ttu-id="21670-128">При наличии локального сервера Exchange Server мы рекомендуем оставить существующую запись на месте во время миграции в Exchange Online и обновить эту запись после завершения миграции.</span><span class="sxs-lookup"><span data-stu-id="21670-128">If you have Exchange Server on-premises, we recommend leaving your existing record in place while you migrate to Exchange Online, and update that record once you have completed your migration.</span></span>

### <a name="exchange-online-mx-record"></a><span data-ttu-id="21670-129">Запись MX Exchange Online</span><span class="sxs-lookup"><span data-stu-id="21670-129">Exchange Online MX Record</span></span>

<span data-ttu-id="21670-130">Значение записи MX для обслуживаемых доменов соответствует стандартному формату, как указано выше: *клиент*. mail.Protection.Office365.US, заменяя *клиент* первой частью имени клиента по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="21670-130">The MX record value for your accepted domains follows a standard format as noted above: *tenant*.mail.protection.office365.us, replacing *tenant* with the first part of your default tenant name.</span></span>

<span data-ttu-id="21670-131">Например, если имя клиента — contoso.onmicrosoft.us, вы бы использовали **contoso.mail.Protection.Office365.US** в качестве значения для записи MX.</span><span class="sxs-lookup"><span data-stu-id="21670-131">For example, if your tenant name is contoso.onmicrosoft.us, you’d use **contoso.mail.protection.office365.us** as the value for your MX record.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="21670-132">Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="21670-132">Skype for Business Online</span></span>

### <a name="cname-records"></a><span data-ttu-id="21670-133">Записи CNAME</span><span class="sxs-lookup"><span data-stu-id="21670-133">CNAME records</span></span>

| <span data-ttu-id="21670-134">Тип</span><span class="sxs-lookup"><span data-stu-id="21670-134">Type</span></span> | <span data-ttu-id="21670-135">Имя узла</span><span class="sxs-lookup"><span data-stu-id="21670-135">Host name</span></span> | <span data-ttu-id="21670-136">Указывает на адрес или значение</span><span class="sxs-lookup"><span data-stu-id="21670-136">Points to address or value</span></span> | <span data-ttu-id="21670-137">TTL</span><span class="sxs-lookup"><span data-stu-id="21670-137">TTL</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="21670-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="21670-138">CNAME</span></span> | <span data-ttu-id="21670-139">sip</span><span class="sxs-lookup"><span data-stu-id="21670-139">sip</span></span> | <span data-ttu-id="21670-140">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="21670-140">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="21670-141">1 час</span><span class="sxs-lookup"><span data-stu-id="21670-141">1 Hour</span></span> |
| <span data-ttu-id="21670-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="21670-142">CNAME</span></span> | <span data-ttu-id="21670-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="21670-143">lyncdiscover</span></span> | <span data-ttu-id="21670-144">webdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="21670-144">webdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="21670-145">1 Hour</span><span class="sxs-lookup"><span data-stu-id="21670-145">1 Hour</span></span> | 

### <a name="srv-records"></a><span data-ttu-id="21670-146">Записи SRV</span><span class="sxs-lookup"><span data-stu-id="21670-146">SRV records</span></span>

| <span data-ttu-id="21670-147">Тип</span><span class="sxs-lookup"><span data-stu-id="21670-147">Type</span></span> | <span data-ttu-id="21670-148">Служба</span><span class="sxs-lookup"><span data-stu-id="21670-148">Service</span></span> | <span data-ttu-id="21670-149">Протокол</span><span class="sxs-lookup"><span data-stu-id="21670-149">Protocol</span></span> | <span data-ttu-id="21670-150">Порт</span><span class="sxs-lookup"><span data-stu-id="21670-150">Port</span></span> | <span data-ttu-id="21670-151">Насыщенность</span><span class="sxs-lookup"><span data-stu-id="21670-151">Weight</span></span> | <span data-ttu-id="21670-152">Priority</span><span class="sxs-lookup"><span data-stu-id="21670-152">Priority</span></span> | <span data-ttu-id="21670-153">Имя</span><span class="sxs-lookup"><span data-stu-id="21670-153">Name</span></span> | <span data-ttu-id="21670-154">Target</span><span class="sxs-lookup"><span data-stu-id="21670-154">Target</span></span> | <span data-ttu-id="21670-155">TTL</span><span class="sxs-lookup"><span data-stu-id="21670-155">TTL</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <span data-ttu-id="21670-156">SRV</span><span class="sxs-lookup"><span data-stu-id="21670-156">SRV</span></span> | <span data-ttu-id="21670-157">\_sip</span><span class="sxs-lookup"><span data-stu-id="21670-157">\_sip</span></span> | <span data-ttu-id="21670-158">\_аутентифицирован</span><span class="sxs-lookup"><span data-stu-id="21670-158">\_tls</span></span> | <span data-ttu-id="21670-159">443</span><span class="sxs-lookup"><span data-stu-id="21670-159">443</span></span> | <span data-ttu-id="21670-160">1,1</span><span class="sxs-lookup"><span data-stu-id="21670-160">1</span></span> | <span data-ttu-id="21670-161">100</span><span class="sxs-lookup"><span data-stu-id="21670-161">100</span></span> | @ | <span data-ttu-id="21670-162">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="21670-162">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="21670-163">1 час</span><span class="sxs-lookup"><span data-stu-id="21670-163">1 Hour</span></span> |
| <span data-ttu-id="21670-164">SRV</span><span class="sxs-lookup"><span data-stu-id="21670-164">SRV</span></span> | <span data-ttu-id="21670-165">\_сипфедератионтлс</span><span class="sxs-lookup"><span data-stu-id="21670-165">\_sipfederationtls</span></span> | <span data-ttu-id="21670-166">\_семейства</span><span class="sxs-lookup"><span data-stu-id="21670-166">\_tcp</span></span> | <span data-ttu-id="21670-167">5061</span><span class="sxs-lookup"><span data-stu-id="21670-167">5061</span></span> | <span data-ttu-id="21670-168">1,1</span><span class="sxs-lookup"><span data-stu-id="21670-168">1</span></span> | <span data-ttu-id="21670-169">100</span><span class="sxs-lookup"><span data-stu-id="21670-169">100</span></span> | @ | <span data-ttu-id="21670-170">sipfed.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="21670-170">sipfed.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="21670-171">1 Hour</span><span class="sxs-lookup"><span data-stu-id="21670-171">1 Hour</span></span> |

## <a name="additional-dns-records"></a><span data-ttu-id="21670-172">Дополнительные записи DNS</span><span class="sxs-lookup"><span data-stu-id="21670-172">Additional DNS records</span></span>

> [!IMPORTANT]
> <span data-ttu-id="21670-173">Если у вас есть запись CNAME *msoID* в зоне DNS, в настоящее время необходимо **Удалить** эту запись из DNS.</span><span class="sxs-lookup"><span data-stu-id="21670-173">If you have an existing *msoid* CNAME record in your DNS zone, you must **remove** the record from DNS at this time.</span></span>  <span data-ttu-id="21670-174">Запись msoID несовместима с Microsoft 365 Enterprise Apps *(прежнее название — Office 365 профессиональный плюс)* и не позволит выполнить активацию.</span><span class="sxs-lookup"><span data-stu-id="21670-174">The msoid record is incompatible with Microsoft 365 Enterprise Apps *(formerly Office 365 ProPlus)* and will prevent activation from succeeding.</span></span>
