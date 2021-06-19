---
title: Поддержка протокола IPv6 в службах Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/10/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c08786fb-298e-437c-8222-dab7625fc815
description: Сводка. Описывает поддержку IPv6 в 365 компонентах Microsoft Office 365 и в предложениях правительства Office 365.
ms.openlocfilehash: a509b19711092bddf153a677c41860e7a4e5277a
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028911"
---
# <a name="ipv6-support-in-office-365-services"></a><span data-ttu-id="f2070-103">Поддержка протокола IPv6 в службах Office 365</span><span class="sxs-lookup"><span data-stu-id="f2070-103">IPv6 support in Office 365 services</span></span>

<span data-ttu-id="f2070-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="f2070-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f2070-105">Office 365 поддерживает IPv6 и IPv4; однако не все функции Office 365 полностью включены с помощью IPv6.</span><span class="sxs-lookup"><span data-stu-id="f2070-105">Office 365 supports both IPv6 and IPv4; however, not all Office 365 features are fully enabled with IPv6.</span></span> <span data-ttu-id="f2070-106">Это означает, что для подключения к Office 365 необходимо использовать IPv4 и IPv6.</span><span class="sxs-lookup"><span data-stu-id="f2070-106">This means that you must use both IPv4 and IPv6 to connect to Office 365.</span></span> <span data-ttu-id="f2070-107">Если вы фильтруете исходящие потоки в Office 365, полный список адресов IPv6, поддерживаемых Office 365, можно найти в статье [URL-адреса Office 365](urls-and-ip-address-ranges.md)и диапазоны IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="f2070-107">If you are filtering your outbound traffic to Office 365, the full list of IPv6 addresses that are supported by Office 365 can be found in the article [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span> <span data-ttu-id="f2070-108">После настройки сети и разрешены соответствующие адреса IPv6, вы можете скачать тестовый план [Office 365 IPv6](https://go.microsoft.com/fwlink/?LinkId=293447) из Центра загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f2070-108">After your network is configured and the appropriate IPv6 addresses are allowed, you can download the [Office 365 IPv6 test plan](https://go.microsoft.com/fwlink/?LinkId=293447) from the Microsoft Download Center.</span></span>
  
## <a name="ipv6-support-in-office-365-subscription-service"></a><span data-ttu-id="f2070-109">Поддержка IPv6 в службе подписки Office 365</span><span class="sxs-lookup"><span data-stu-id="f2070-109">IPv6 support in Office 365 subscription service</span></span>

### <a name="exchange-online-and-ipv6"></a><span data-ttu-id="f2070-110">Exchange Online и IPv6</span><span class="sxs-lookup"><span data-stu-id="f2070-110">Exchange Online and IPv6</span></span>

<span data-ttu-id="f2070-111">Если программа, используемая для подключения к Exchange Online, поддерживает IPv6, она по умолчанию будет использовать IPv6 как в проводных, так и в беспроводных сетях.</span><span class="sxs-lookup"><span data-stu-id="f2070-111">If the program that you use to connect to Exchange Online supports IPv6, it will use IPv6 by default on both wired and wireless networks.</span></span> <span data-ttu-id="f2070-112">Если вы хотите управлять связью с Exchange Online, используйте диапазоны IP-адресов в [URL-адресах Office 365 и ДИАПАЗОНАх IP-адресов.](urls-and-ip-address-ranges.md)</span><span class="sxs-lookup"><span data-stu-id="f2070-112">If you want to control communications to Exchange Online, use the IP address ranges in [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
### <a name="sharepoint-online-and-ipv6"></a><span data-ttu-id="f2070-113">SharePoint Online и IPv6</span><span class="sxs-lookup"><span data-stu-id="f2070-113">SharePoint Online and IPv6</span></span>

 <span data-ttu-id="f2070-114">**Office 365 Government G1/G3/G4/K1** Если программа, используемая для подключения к SharePoint Online, поддерживает IPv6, она по умолчанию будет пытаться использовать IPv6.</span><span class="sxs-lookup"><span data-stu-id="f2070-114">**Office 365 Government G1/G3/G4/K1** If the program that you use to connect to SharePoint Online supports IPv6, it will attempt to use IPv6 by default.</span></span>
  
 <span data-ttu-id="f2070-115">**Общедоступные облачные платформы с несколькими клиентами** Корпорация Майкрософт включает IPv6 SharePoint Online по вашему запросу.</span><span class="sxs-lookup"><span data-stu-id="f2070-115">**Public multi-tenant cloud** Microsoft enables SharePoint Online IPv6 at your request.</span></span> <span data-ttu-id="f2070-116">Для DNS-инфраструктуры организации необходимо предоставить IP-адреса CIDR, замещенные нотами.</span><span class="sxs-lookup"><span data-stu-id="f2070-116">You need to provide the CIDR notated IP addresses for your organization's DNS infrastructure.</span></span> <span data-ttu-id="f2070-117">Имейте в виду, что эта инфраструктура DNS не может быть совместной другими организациями для включения IPv6 для клиента.</span><span class="sxs-lookup"><span data-stu-id="f2070-117">Keep in mind that this DNS infrastructure can't be shared by other organizations for IPv6 to be enabled for your tenant.</span></span> <span data-ttu-id="f2070-118">После включения IPv6 программа, используемая для подключения к SharePoint Online, поддерживает IPv6, по умолчанию использует IPv6.</span><span class="sxs-lookup"><span data-stu-id="f2070-118">After IPv6 is enabled, if the program that you use to connect to SharePoint Online supports IPv6, it uses IPv6 by default.</span></span>
  
<span data-ttu-id="f2070-119">Если программа, используемая для подключения к SharePoint Online, поддерживает IPv6, она по умолчанию будет использовать IPv6 как в проводных, так и в беспроводных сетях.</span><span class="sxs-lookup"><span data-stu-id="f2070-119">If the program that you use to connect to SharePoint Online supports IPv6, it will use IPv6 by default on both wired and wireless networks.</span></span> <span data-ttu-id="f2070-120">Если вы хотите управлять связью с SharePoint Online, используйте диапазоны IP-адресов в [URL-адресах Office 365 и IP-адресах.](urls-and-ip-address-ranges.md)</span><span class="sxs-lookup"><span data-stu-id="f2070-120">If you want to control communications to SharePoint Online, use the IP address ranges in [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
 
  
### <a name="skype-for-business-and-ipv6"></a><span data-ttu-id="f2070-121">Skype для бизнеса и IPv6</span><span class="sxs-lookup"><span data-stu-id="f2070-121">Skype for Business and IPv6</span></span>

<span data-ttu-id="f2070-122">Обратите внимание, что IPv6 не поддерживается в Skype для бизнеса и больше не может быть включена.</span><span class="sxs-lookup"><span data-stu-id="f2070-122">Please be aware IPv6 is not supported in Skype for Business and can no longer be enabled.</span></span>

### <a name="microsoft-teams-and-ipv6"></a><span data-ttu-id="f2070-123">Microsoft Teams и IPV6</span><span class="sxs-lookup"><span data-stu-id="f2070-123">Microsoft Teams and IPV6</span></span>

<span data-ttu-id="f2070-124">Прямая маршрутная маршрутия Microsoft Teams поддерживает только IPv4.</span><span class="sxs-lookup"><span data-stu-id="f2070-124">Microsoft Teams Direct Routing only supports IPv4.</span></span> <span data-ttu-id="f2070-125">Служба Microsoft Teams и клиентская поддержка IPv4 и IPv6.</span><span class="sxs-lookup"><span data-stu-id="f2070-125">The Microsoft Teams service and client support both IPv4 and IPv6.</span></span> <span data-ttu-id="f2070-126">Чтобы управлять связью с Microsoft Teams, используйте диапазоны IP-адресов в [URL-адресах Office 365 и IP-адресах.](urls-and-ip-address-ranges.md)</span><span class="sxs-lookup"><span data-stu-id="f2070-126">If you want to control communications to Microsoft Teams, use the IP address ranges in [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
### <a name="exchange-online-protection-and-ipv6"></a><span data-ttu-id="f2070-127">Exchange Online Protection и IPv6</span><span class="sxs-lookup"><span data-stu-id="f2070-127">Exchange Online Protection and IPv6</span></span>

<span data-ttu-id="f2070-128">Exchange Online Protection (EOP) поддерживает IPv6, если передача происходит по протоколу безопасности транспортного слоя.</span><span class="sxs-lookup"><span data-stu-id="f2070-128">Exchange Online Protection (EOP) supports IPv6 if the transmission occurs over Transport Layer Security Protocol.</span></span> <span data-ttu-id="f2070-129">Для диапазона EOP используйте [URL-адреса Office 365 и диапазоны IP-адресов.](urls-and-ip-address-ranges.md)</span><span class="sxs-lookup"><span data-stu-id="f2070-129">For the EOP range, use [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
### <a name="ipv6-support-for-office-365-government-offerings"></a><span data-ttu-id="f2070-130">Поддержка IPv6 для государственных предложений Office 365</span><span class="sxs-lookup"><span data-stu-id="f2070-130">IPv6 support for Office 365 government offerings</span></span>

<span data-ttu-id="f2070-131">Поддержка правительственных предложений Office 365 IPv6 соответствует меморандуму Office of Management and Budget (OMB) для главных должностных лиц по информационным вопросам исполнительных департаментов и учреждений, а также меморандуму о принятии федеральным правительством протокола Интернета Версии 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="f2070-131">Office 365 IPv6 support for government offerings conforms to the Office of Management and Budget (OMB) Memorandum for Chief Information Officers of Executive Departments and Agencies, as well as the Federal Government Adoption of Internet Protocol Version 6 (IPv6) memorandum.</span></span> <span data-ttu-id="f2070-132">[Microsoft Office 365 для](https://go.microsoft.com/fwlink/p/?LinkId=325414) правительства — это служба с несколькими клиентами, которая хранит данные правительства США в изолированном облаке сообщества.</span><span class="sxs-lookup"><span data-stu-id="f2070-132">[Microsoft Office 365 for Government](https://go.microsoft.com/fwlink/p/?LinkId=325414) is a multi-tenant service that stores US government data in a segregated community cloud.</span></span> <span data-ttu-id="f2070-133">Как и другие предложения Office 365, он предоставляет службы производительности и совместной работы, в том числе Exchange Online, Skype для бизнеса, SharePoint Online и Microsoft 365 Apps для предприятия.</span><span class="sxs-lookup"><span data-stu-id="f2070-133">Like other Office 365 offerings, it provides productivity and collaboration services, including Exchange Online, Skype for Business, SharePoint Online, and Microsoft 365 Apps for enterprise.</span></span> 

<span data-ttu-id="f2070-134">Предложения Microsoft Office 365 государственных услуг применяются только в 2013 году и более позднем.</span><span class="sxs-lookup"><span data-stu-id="f2070-134">The Microsoft Office 365 government offerings apply only for 2013 and later.</span></span> <span data-ttu-id="f2070-135">Дополнительные сведения о предложениях для правительства Office 365 см. в анонсе [Office 365 для правительства: облако](https://go.microsoft.com/fwlink/p/?LinkId=325414)сообщества правительства США.</span><span class="sxs-lookup"><span data-stu-id="f2070-135">For more information about the Office 365 government offerings, see [Announcing Office 365 for Government: A US Government Community Cloud](https://go.microsoft.com/fwlink/p/?LinkId=325414).</span></span> <span data-ttu-id="f2070-136">International Traffic in Arms Regulations (ITAR) — это набор правительственных правил США, которые контролируют экспорт и импорт статей и служб, связанных с обороной, в списке боеприпасов США [(USML).](https://go.microsoft.com/fwlink/p/?LinkId=325415)</span><span class="sxs-lookup"><span data-stu-id="f2070-136">International Traffic in Arms Regulations (ITAR) is a set of US government regulations that control the export and import of defense-related articles and services on the [United States Munitions List (USML)](https://go.microsoft.com/fwlink/p/?LinkId=325415).</span></span> 

<span data-ttu-id="f2070-137">Microsoft Office 365 для предприятий предоставляет специализированные службы хостинга для решений по производительности Майкрософт, которые поддерживают требования к безопасности, конфиденциальности и нормативным требованиям для федеральных учреждений США, требующих сертификации Федеральной службы управления информационной безопасностью (FISMA) и коммерческих субъектов, подчиняющихся ИТАР.</span><span class="sxs-lookup"><span data-stu-id="f2070-137">Microsoft Office 365 for Enterprises provides dedicated hosting services for Microsoft productivity solutions that support the security, privacy, and regulatory compliance requirements for US federal agencies requiring Federal Information Security Management (FISMA) certification and commercial entities subject to ITAR.</span></span>
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a><span data-ttu-id="f2070-138">Что следует учитывать при использовании IPv6 и Office 365</span><span class="sxs-lookup"><span data-stu-id="f2070-138">Things to consider when using IPv6 and Office 365</span></span>

<span data-ttu-id="f2070-139">Рекомендуется не отключать IPv6.</span><span class="sxs-lookup"><span data-stu-id="f2070-139">We recommend that you do not disable IPv6.</span></span> <span data-ttu-id="f2070-140">Дополнительные сведения см. в статье [руководство](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users).</span><span class="sxs-lookup"><span data-stu-id="f2070-140">For more information, see this [guidance article](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users).</span></span> <span data-ttu-id="f2070-141">Чтобы определить, какие IP-версии используются в сети, рассмотрим следующее:</span><span class="sxs-lookup"><span data-stu-id="f2070-141">To determine what IP versions are being used on your network, consider the following:</span></span>
  
- <span data-ttu-id="f2070-142">Если отображение команды **IPConfig** в командной строке содержит строки с именем "адрес IPv6" или "Временный адрес IPv6", в вашей среде есть IPv6.</span><span class="sxs-lookup"><span data-stu-id="f2070-142">If the display of the **IPConfig** command at the command prompt contains rows named "IPv6 Address" or "Temporary IPv6 Address," you have IPv6 in your environment.</span></span>

- <span data-ttu-id="f2070-143">Если все адреса IPv6 начинаются с "fe80" и соответствуют строкам с именем "Link-Local IPv6 Address", у вас нет IPv6 в среде.</span><span class="sxs-lookup"><span data-stu-id="f2070-143">If all the IPv6 addresses begin with "fe80" and correspond to rows named "Link-Local IPv6 Address," you don't have IPv6 in your environment.</span></span>

<span data-ttu-id="f2070-144">Эти соображения могут применяться к вашей сети:</span><span class="sxs-lookup"><span data-stu-id="f2070-144">These considerations might apply to your network:</span></span>
  
- <span data-ttu-id="f2070-145">Государственная служба подписки не поддерживает покупку с помощью кредитной карты через IPv6.</span><span class="sxs-lookup"><span data-stu-id="f2070-145">The public subscription service does not support purchase by credit card over IPv6.</span></span> <span data-ttu-id="f2070-146">Это не относится к облаку правительственных сообществ (GCC), так как у Соглашение Enterprise (EA) лицензирование.</span><span class="sxs-lookup"><span data-stu-id="f2070-146">This does not apply to the Government Community Cloud (GCC) because governments have Enterprise Agreement (EA) licensing.</span></span>

- <span data-ttu-id="f2070-147">IPv6 не поддерживает некоторые сценарии служб управления правами (RMS).</span><span class="sxs-lookup"><span data-stu-id="f2070-147">IPv6 does not support some Rights Management Services (RMS) scenarios.</span></span>

- <span data-ttu-id="f2070-148">IPv6 не поддерживает Сервер ® (BES), так как BlackBerry не поддерживает IPv6.</span><span class="sxs-lookup"><span data-stu-id="f2070-148">IPv6 does not support BlackBerry® Enterprise Server (BES) because BlackBerry doesn't support IPv6.</span></span>

- <span data-ttu-id="f2070-149">Если вы используете службы Федерации Active Directory (AD FS) с Office 365, реклама конечной точки сети AD FS в Office 365 с помощью IPv6 не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f2070-149">If you use Active Directory Federation Services (AD FS) with Office 365, advertising your AD FS network endpoint to Office 365 using IPv6 is not supported.</span></span> <span data-ttu-id="f2070-150">Не следует включать записи AAAA в запись DNS AD FS при использовании Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f2070-150">You should not include AAAA records in the AD FS DNS entry when using Exchange Online.</span></span> 

<span data-ttu-id="f2070-151">Вы можете быстро вернуться сюда с помощью этой короткой ссылки: [https://aka.ms/o365ip6]()</span><span class="sxs-lookup"><span data-stu-id="f2070-151">Here's a short link you can use to come back: [https://aka.ms/o365ip6]()</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f2070-152">См. также</span><span class="sxs-lookup"><span data-stu-id="f2070-152">See also</span></span>

<span data-ttu-id="f2070-153">[Дорожная карта обучения IPv6](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))</span><span class="sxs-lookup"><span data-stu-id="f2070-153">[IPv6 Learning Roadmap](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))</span></span>
  
[<span data-ttu-id="f2070-154">Руководство по выживанию IPv6</span><span class="sxs-lookup"><span data-stu-id="f2070-154">IPv6 Survival Guide</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)
