---
title: Вопросы и ответы о доменах
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
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: Дополнительные сведения о доменах можно найти в ответах на часто задаваемые вопросы.
ms.openlocfilehash: 093125d1652355fbd9b624e1f15b5858fd586301
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049740"
---
# <a name="domains-faq"></a><span data-ttu-id="31bae-103">Вопросы и ответы о доменах</span><span class="sxs-lookup"><span data-stu-id="31bae-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="31bae-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="31bae-104">The admin center is changing.</span></span> <span data-ttu-id="31bae-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="31bae-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="31bae-106">В этой статье приведены ответы на часто задаваемые вопросы о доменах в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31bae-106">This article contains answers to frequently asked questions about domains in Microsoft 365.</span></span>

<span data-ttu-id="31bae-107">Если вы не нашли ответ на свой вопрос, оставьте комментарий и мы добавим его в список.</span><span class="sxs-lookup"><span data-stu-id="31bae-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>

<span data-ttu-id="31bae-108">В этой статье</span><span class="sxs-lookup"><span data-stu-id="31bae-108">In this article</span></span>

<span data-ttu-id="31bae-109">[Что такое приоритет MX?](#what-is-mx-priority) 
 [Как проверить записи SPF для домена?](#how-can-i-validate-spf-records-for-my-domain) 
 [Что такое доменное имя?](#what-is-a-domain-name) 
 [Что произойдет, если поставщик DNS не поддерживает некоторые типы записей?](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types) 
 [Как задать или изменить домен по умолчанию в Microsoft 365?](#how-do-i-set-or-change-the-default-domain-in-microsoft-365) 
 [Можно ли добавить настраиваемые поддомены или несколько доменов в Microsoft 365?](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365) 
 [Почему у меня есть домен "onmicrosoft.com"?](#why-do-i-have-an-onmicrosoftcom-domain) 
 [Почему у меня есть домен "onmicrosoft.de"?](#why-do-i-have-an-onmicrosoftde-domain) 
 [Как проверить статус некоммерческой или образования?](#how-do-i-verify-my-nonprofit-or-education-status)</span><span class="sxs-lookup"><span data-stu-id="31bae-109">[What is MX priority?](#what-is-mx-priority)
[How can I validate SPF records for my domain?](#how-can-i-validate-spf-records-for-my-domain)
[What is a domain name?](#what-is-a-domain-name)
[What happens if my DNS provider doesn't support certain record types?](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
[How do I set or change the default domain in Microsoft 365?](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
[Can I add custom subdomains or multiple domains to Microsoft 365?](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
[Why do I have an "onmicrosoft.com" domain?](#why-do-i-have-an-onmicrosoftcom-domain)
[Why do I have an "onmicrosoft.de" domain?](#why-do-i-have-an-onmicrosoftde-domain)
[How do I verify my nonprofit or education status?](#how-do-i-verify-my-nonprofit-or-education-status)</span></span>
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="31bae-110">Что такое приоритет записей MX?</span><span class="sxs-lookup"><span data-stu-id="31bae-110">What is MX priority?</span></span>

<span data-ttu-id="31bae-111">Почта доставляется на сервер почтового обменника, который имеет наименьший номер предпочтения (наивысший приоритет), поэтому у записи MX, которая используется для маршрутизации, должен быть наименьший номер предпочтения (обычно 0) или  *высокий*  приоритет.</span><span class="sxs-lookup"><span data-stu-id="31bae-111">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="31bae-112">При создании записи MX большинство поставщиков услуг размещения DNS требуют указать номер предпочтения.</span><span class="sxs-lookup"><span data-stu-id="31bae-112">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="31bae-113">В некоторых службах соответствующий параметр называется  *предпочтением*  , а в некоторых   *приоритетом*  .</span><span class="sxs-lookup"><span data-stu-id="31bae-113">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="31bae-114">В некоторых требуется указать число, а в некоторых  выбрать значение  *Низкий*  ,  *Средний*  или  *Высокий*  .</span><span class="sxs-lookup"><span data-stu-id="31bae-114">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="31bae-115">Если у вас только одна запись MX, подойдет любое значение.</span><span class="sxs-lookup"><span data-stu-id="31bae-115">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="31bae-116">Если у вас есть несколько таких записей, убедитесь, что запись MX, используемая для маршрутизации почты, имеет более высокий приоритет, чем та, которая применяется для подтверждения владения доменом.</span><span class="sxs-lookup"><span data-stu-id="31bae-116">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="31bae-117">Как проверить записи SPF для домена?</span><span class="sxs-lookup"><span data-stu-id="31bae-117">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="31bae-118">Важно иметь или создать **только одну запись TXT для SPF**.</span><span class="sxs-lookup"><span data-stu-id="31bae-118">It's important that you have or create  **only one TXT record for SPF**.</span></span> <span data-ttu-id="31bae-119">Если у вас уже есть запись SPF, добавьте к ней новые значения Microsoft 365, а не создайте новую.</span><span class="sxs-lookup"><span data-stu-id="31bae-119">If you already have an SPF record, you should append the new Microsoft 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="31bae-120">После добавления или обновления записи SPF для электронной почты Майкрософт необходимо убедиться в правильности синтаксиса с помощью одного из следующих средств:</span><span class="sxs-lookup"><span data-stu-id="31bae-120">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="31bae-121">Инструменты для тестирования записей SPF</span><span class="sxs-lookup"><span data-stu-id="31bae-121">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="31bae-122">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="31bae-122">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="31bae-123">Веб-интерфейс Dig</span><span class="sxs-lookup"><span data-stu-id="31bae-123">Dig web interface</span></span>](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a><span data-ttu-id="31bae-124">Что такое доменное имя?</span><span class="sxs-lookup"><span data-stu-id="31bae-124">What is a domain name?</span></span>

<span data-ttu-id="31bae-125">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span><span class="sxs-lookup"><span data-stu-id="31bae-125">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span></span> <span data-ttu-id="31bae-126">in web addresses.</span><span class="sxs-lookup"><span data-stu-id="31bae-126">in web addresses.</span></span> <span data-ttu-id="31bae-127">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span><span class="sxs-lookup"><span data-stu-id="31bae-127">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="31bae-128">Использование собственного домена, например "**роб \@ contoso.com**" с Microsoft 365, поможет вам создавать сведения о доходе и распознавание для вашей фирменной символики.</span><span class="sxs-lookup"><span data-stu-id="31bae-128">Using a custom domain like "**rob\@contoso.com**" with Microsoft 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="31bae-129">Вы можете [приобрести домен в Microsoft 365, а также настроить его автоматически](../get-help-with-domains/buy-a-domain-name.md)или приобрести у регистратора доменных имен, которым вы уже владеете.</span><span class="sxs-lookup"><span data-stu-id="31bae-129">You can [buy a domain in Microsoft 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="31bae-130">Что произойдет, если поставщик DNS не поддерживает некоторые типы записей?</span><span class="sxs-lookup"><span data-stu-id="31bae-130">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="31bae-131">Если вы управляете собственными DNS-записями, а узел DNS не поддерживает все записи DNS, необходимые для Microsoft 365, некоторые функции Microsoft 365 не будут работать.</span><span class="sxs-lookup"><span data-stu-id="31bae-131">If you manage your own DNS records and your DNS host does not support all the DNS records that Microsoft 365 needs, some Microsoft 365 features won't work.</span></span> <span data-ttu-id="31bae-132">Мы рекомендуем передать домен регистратору, который поддерживает все необходимые записи DNS.</span><span class="sxs-lookup"><span data-stu-id="31bae-132">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="31bae-133">Поставщики, поддерживающие все необходимые записи DNS:</span><span class="sxs-lookup"><span data-stu-id="31bae-133">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="31bae-134">Dynadot</span><span class="sxs-lookup"><span data-stu-id="31bae-134">Dynadot</span></span>
    
- <span data-ttu-id="31bae-135">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="31bae-135">eNomCentral</span></span>
    
- <span data-ttu-id="31bae-136">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="31bae-136">Europe Registry</span></span>
    
- <span data-ttu-id="31bae-137">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="31bae-137">GoDaddy</span></span>
    
- <span data-ttu-id="31bae-138">Hover</span><span class="sxs-lookup"><span data-stu-id="31bae-138">Hover</span></span>
    
- <span data-ttu-id="31bae-139">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="31bae-139">MyHosting.com</span></span>
    
- <span data-ttu-id="31bae-140">Name.com</span><span class="sxs-lookup"><span data-stu-id="31bae-140">Name.com</span></span>
    
- <span data-ttu-id="31bae-141">Nearly Free Speech</span><span class="sxs-lookup"><span data-stu-id="31bae-141">Nearly Free Speech</span></span>
    
- <span data-ttu-id="31bae-142">Nettica</span><span class="sxs-lookup"><span data-stu-id="31bae-142">Nettica</span></span>
    
- <span data-ttu-id="31bae-143">Network Information Center (NIC)</span><span class="sxs-lookup"><span data-stu-id="31bae-143">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="31bae-144">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="31bae-144">Network Solutions</span></span>
    
- <span data-ttu-id="31bae-145">Register.com</span><span class="sxs-lookup"><span data-stu-id="31bae-145">Register.com</span></span>
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a><span data-ttu-id="31bae-146">Как задать или изменить домен по умолчанию в Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="31bae-146">How do I set or change the default domain in Microsoft 365?</span></span>

<span data-ttu-id="31bae-147">Вы должны иметь по крайней мере один личный домен, добавленный в Microsoft 365, прежде чем вы сможете выбрать домен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="31bae-147">You must have at least one custom domain that you've added to Microsoft 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="31bae-148">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="31bae-148">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="31bae-149">В Центре администрирования перейдите на страницу **Settings** (Параметры) > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="31bae-149">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="31bae-150">В Центре администрирования перейдите на страницу **Settings** (Параметры) > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="31bae-150">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="31bae-151">На странице **Domains (домены** ) выберите домен, который требуется установить в качестве значения по умолчанию для новых адресов электронной почты.</span><span class="sxs-lookup"><span data-stu-id="31bae-151">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="31bae-152">Нажмите кнопку **По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="31bae-152">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="31bae-153">Изменить имя первоначального домена  *.onmicrosoft.com*  невозможно.</span><span class="sxs-lookup"><span data-stu-id="31bae-153">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="31bae-154">Имя начального домена *onmicrosoft.de* нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="31bae-154">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="31bae-155">Имя начального домена *Partner.onmschina.CN* нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="31bae-155">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a><span data-ttu-id="31bae-156">Можно ли добавить настраиваемые поддомены или несколько доменов в Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="31bae-156">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="31bae-157">Да.</span><span class="sxs-lookup"><span data-stu-id="31bae-157">Yes.</span></span> <span data-ttu-id="31bae-158">Чтобы добавить поддомены, необходимо управлять собственными параметрами DNS на веб-сайте регистратора.</span><span class="sxs-lookup"><span data-stu-id="31bae-158">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="31bae-159">Если вы разработаны Майкрософт для управления параметрами DNS с записями NS или если вы приобрели домен от корпорации Майкрософт, вы не сможете добавить поддомены.</span><span class="sxs-lookup"><span data-stu-id="31bae-159">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="31bae-160">Нет!</span><span class="sxs-lookup"><span data-stu-id="31bae-160">Yes!</span></span> <span data-ttu-id="31bae-161">Чтобы добавить поддомены, необходимо управлять собственными параметрами DNS на веб-сайте регистратора.</span><span class="sxs-lookup"><span data-stu-id="31bae-161">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="31bae-162">Если вы разработаны Майкрософт для управления параметрами DNS с записями NS или если вы приобрели домен от корпорации Майкрософт, вы не сможете добавить поддомены.</span><span class="sxs-lookup"><span data-stu-id="31bae-162">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="31bae-163">Нет!</span><span class="sxs-lookup"><span data-stu-id="31bae-163">Yes!</span></span> <span data-ttu-id="31bae-164">Чтобы добавить поддомены, необходимо управлять собственными параметрами DNS на веб-сайте регистратора.</span><span class="sxs-lookup"><span data-stu-id="31bae-164">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="31bae-165">Если вы разпозволяете 21Vianet управлять параметрами DNS с записями NS, вы не можете добавлять поддомены.</span><span class="sxs-lookup"><span data-stu-id="31bae-165">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="31bae-166">Как правило, в подписку Microsoft 365 можно добавить до 900 доменов.</span><span class="sxs-lookup"><span data-stu-id="31bae-166">Typically, you can add up to 900 domains to your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="31bae-167">Например, вы можете добавить домены contoso.com и contosomarketing.com, а затем  поддомены www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com и т. д.</span><span class="sxs-lookup"><span data-stu-id="31bae-167">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="31bae-168">При добавлении дочернего домена он автоматически проверяется в соответствии с проверяемым родительским доменом.</span><span class="sxs-lookup"><span data-stu-id="31bae-168">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="31bae-169">При добавлении нескольких доменов в Microsoft 365 можно разместить любую службу (например, электронную почту) для всех добавленных доменов.</span><span class="sxs-lookup"><span data-stu-id="31bae-169">When you add multiple domains to Microsoft 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="31bae-170">*Когда вы изменяете электронную почту на Microsoft 365, обновляя запись MX в домене, все сообщения, отправленные на этот домен, начнут приходить в Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="31bae-170">*When you change your email to Microsoft 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Microsoft 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="31bae-171">Если вы добавили домен contoso.com в подписку на Microsoft 365, вы также можете добавить xyz.contoso.com дочернего домена в другую организацию Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31bae-171">If you added a contoso.com domain to a Microsoft 365 subscription, you can also add the subdomain xyz.contoso.com to another Microsoft 365 organization.</span></span> <span data-ttu-id="31bae-172">При добавлении поддомена вам будет предложено добавить запись TXT в поставщик услуг хостинга DNS.</span><span class="sxs-lookup"><span data-stu-id="31bae-172">When adding the subdomain, you are prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="31bae-173">Почему у меня есть домен onmicrosoft.com?</span><span class="sxs-lookup"><span data-stu-id="31bae-173">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="31bae-174">Microsoft 365 создает домен, например *contoso.onmicrosoft.com*, при регистрации в службе.</span><span class="sxs-lookup"><span data-stu-id="31bae-174">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="31bae-175">Идентификатор пользователя, который вы создаете при регистрации, включает домен, например *Alan@contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="31bae-175">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="31bae-176">**Если вы хотите, чтобы ваша электронная почта выглядела как *Сергей \@ contoso.com*:** [купите домен](../get-help-with-domains/buy-a-domain-name.md) или просто выполните действия, описанные в статье [Добавление пользователей и доменов в Microsoft 365](add-domain.md) , если у вас уже есть.</span><span class="sxs-lookup"><span data-stu-id="31bae-176">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="31bae-177">**Домен onmicrosoft невозможно переименовать после регистрации.**</span><span class="sxs-lookup"><span data-stu-id="31bae-177">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="31bae-178">Например, если первоначально вы выбрали домен fourthcoffee.onmicrosoft.com, его не удастся переименовать в fabrikam.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="31bae-178">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="31bae-179">Чтобы использовать другой домен onmicrosoft.com, вам потребуется начать новую подписку с помощью Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31bae-179">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="31bae-180">**Вы не можете переименовать URL-адрес сайта группы.**</span><span class="sxs-lookup"><span data-stu-id="31bae-180">**You can't rename your team site URL.**</span></span> <span data-ttu-id="31bae-181">URL-адрес сайта группы основан на вашем доменном имени onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="31bae-181">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="31bae-182">К сожалению, из-за способа работы архитектуры SharePoint Online нельзя переименовать сайт группы.</span><span class="sxs-lookup"><span data-stu-id="31bae-182">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="31bae-183">**Домен onmicrosoft невозможно удалить.**</span><span class="sxs-lookup"><span data-stu-id="31bae-183">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="31bae-184">Microsoft 365 необходимо обойти, так как она используется в фоновом режиме для вашей подписки.</span><span class="sxs-lookup"><span data-stu-id="31bae-184">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="31bae-185">Несмотря на это, вы можете им не пользоваться, если добавите личный домен.</span><span class="sxs-lookup"><span data-stu-id="31bae-185">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="31bae-186">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span><span class="sxs-lookup"><span data-stu-id="31bae-186">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span></span> <span data-ttu-id="31bae-187">It still works for email and other services, so it's your choice.</span><span class="sxs-lookup"><span data-stu-id="31bae-187">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="31bae-188">Почему у меня есть домен "onmicrosoft.de"?</span><span class="sxs-lookup"><span data-stu-id="31bae-188">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="31bae-189">Microsoft 365 создает домен, например *contoso.onmicrosoft.de*, при регистрации в службе.</span><span class="sxs-lookup"><span data-stu-id="31bae-189">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="31bae-190">Идентификатор пользователя, который вы создаете при регистрации, включает домен, например *Alan@contoso.onmicrosoft.de*.</span><span class="sxs-lookup"><span data-stu-id="31bae-190">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="31bae-191">**Если вы хотите, чтобы ваша электронная почта выглядела как *Alan@contoso.de*:** [купите домен](../get-help-with-domains/buy-a-domain-name.md) или просто выполните действия, описанные в [статье Добавление пользователей и доменов в Microsoft 365](add-domain.md) , если вы уже являетесь ее владельцем.</span><span class="sxs-lookup"><span data-stu-id="31bae-191">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="31bae-192">**Домен onmicrosoft невозможно переименовать после регистрации.**</span><span class="sxs-lookup"><span data-stu-id="31bae-192">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="31bae-193">Например, если исходный домен, который вы выбрали, был fourthcoffee.onmicrosoft.de, его нельзя изменить на fabrikam.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="31bae-193">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="31bae-194">Чтобы использовать другой домен onmicrosoft.de, вам потребуется начать новую подписку с помощью Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31bae-194">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="31bae-195">**Вы не можете переименовать URL-адрес сайта группы.**</span><span class="sxs-lookup"><span data-stu-id="31bae-195">**You can't rename your team site URL.**</span></span> <span data-ttu-id="31bae-196">URL-адрес сайта группы основан на вашем доменном имени onmicrosoft.de. К сожалению, из-за способа работы архитектуры SharePoint Online нельзя переименовать сайт группы.</span><span class="sxs-lookup"><span data-stu-id="31bae-196">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="31bae-197">**Домен onmicrosoft невозможно удалить.**</span><span class="sxs-lookup"><span data-stu-id="31bae-197">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="31bae-198">Microsoft 365 необходимо обойти, так как она используется в фоновом режиме для вашей подписки.</span><span class="sxs-lookup"><span data-stu-id="31bae-198">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="31bae-199">Несмотря на это, вы можете им не пользоваться, если добавите личный домен.</span><span class="sxs-lookup"><span data-stu-id="31bae-199">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="31bae-200">Вы можете продолжить работу с исходным доменом onmicrosoft.de, даже после добавления домена.</span><span class="sxs-lookup"><span data-stu-id="31bae-200">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="31bae-201">Он будет поддерживаться в электронной почте и других службах.</span><span class="sxs-lookup"><span data-stu-id="31bae-201">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="31bae-202">Как проверить статус некоммерческой или образования?</span><span class="sxs-lookup"><span data-stu-id="31bae-202">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="31bae-203">В [центре администрирования](https://docs.microsoft.com/microsoft-365/admin/admin-home) выберите пункт **Настройка** , чтобы запустить мастер.</span><span class="sxs-lookup"><span data-stu-id="31bae-203">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="31bae-204">(Сначала войдите в Microsoft 365.)</span><span class="sxs-lookup"><span data-stu-id="31bae-204">(Be sure to sign in to Microsoft 365 first.)</span></span> 
    
2. <span data-ttu-id="31bae-205">Чтобы стать администратором учебного заведения, выберите параметр **становится** администратором в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31bae-205">To become the admin for your school, select the  **Become an admin** option in Microsoft 365.</span></span> 
    
3. <span data-ttu-id="31bae-206">Вам будет предложено добавить запись DNS в формате TXT на веб-сайт узла DNS для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="31bae-206">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="31bae-207">Почему?</span><span class="sxs-lookup"><span data-stu-id="31bae-207">Why?</span></span> <span data-ttu-id="31bae-208">Так как при входе на узел DNS и добавлении записи в домен вы подтверждаете в Microsoft 365, что вы владеете доменным именем.</span><span class="sxs-lookup"><span data-stu-id="31bae-208">Because by signing in at the DNS host and adding a record for your domain, you prove to Microsoft 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="31bae-209">После добавления записи вы вернетесь на портал Microsoft 365 и подтвердите, что она добавлена, поэтому Microsoft 365 может проверить.</span><span class="sxs-lookup"><span data-stu-id="31bae-209">After you add the record, you'll go back to the Microsoft 365 portal and confirm that you've added it, so Microsoft 365 can check.</span></span>
    
<span data-ttu-id="31bae-210">У вас есть некоммерческие и хотите получить Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="31bae-210">Have a nonprofit and want to get Microsoft 365?</span></span> <span data-ttu-id="31bae-211">[Убедитесь, что ваша организация](https://www.microsoft.com/en-us/nonprofits/eligibility) поддается уточнению и зарегистрируйте ее.</span><span class="sxs-lookup"><span data-stu-id="31bae-211">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="31bae-212">Хотите узнать больше о том, как стать администратором учебного заведения?</span><span class="sxs-lookup"><span data-stu-id="31bae-212">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="31bae-213">[Узнайте больше об этом](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span><span class="sxs-lookup"><span data-stu-id="31bae-213">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>