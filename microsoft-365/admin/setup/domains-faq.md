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
ms.openlocfilehash: bb949dbd4e32bb62f10dfd0323df70697fdc5404
ms.sourcegitcommit: 5c16d270c7651c2080a5043d273d979a6fcc75c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804200"
---
# <a name="domains-faq"></a><span data-ttu-id="bd216-103">Вопросы и ответы о доменах</span><span class="sxs-lookup"><span data-stu-id="bd216-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="bd216-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="bd216-104">The admin center is changing.</span></span> <span data-ttu-id="bd216-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="bd216-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="bd216-106">В этой статье приведены ответы на часто задаваемые вопросы о доменах в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bd216-106">This article contains answers to frequently asked questions about domains in Microsoft 365.</span></span>

<span data-ttu-id="bd216-107">Если вы не нашли ответ на свой вопрос, оставьте комментарий и мы добавим его в список.</span><span class="sxs-lookup"><span data-stu-id="bd216-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>

<span data-ttu-id="bd216-108">В этой статье</span><span class="sxs-lookup"><span data-stu-id="bd216-108">In this article</span></span>

- [<span data-ttu-id="bd216-109">Что такое приоритет записей MX?</span><span class="sxs-lookup"><span data-stu-id="bd216-109">What is MX priority?</span></span>](#what-is-mx-priority)
- [<span data-ttu-id="bd216-110">Как проверить записи SPF для домена?</span><span class="sxs-lookup"><span data-stu-id="bd216-110">How can I validate SPF records for my domain?</span></span>](#how-can-i-validate-spf-records-for-my-domain)
- [<span data-ttu-id="bd216-111">Что такое доменное имя?</span><span class="sxs-lookup"><span data-stu-id="bd216-111">What is a domain name?</span></span>](#what-is-a-domain-name)
- [<span data-ttu-id="bd216-112">Что произойдет, если поставщик DNS не поддерживает некоторые типы записей?</span><span class="sxs-lookup"><span data-stu-id="bd216-112">What happens if my DNS provider doesn't support certain record types?</span></span>](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
- [<span data-ttu-id="bd216-113">Как задать или изменить домен по умолчанию в Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="bd216-113">How do I set or change the default domain in Microsoft 365?</span></span>](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [<span data-ttu-id="bd216-114">Можно ли добавить настраиваемые поддомены или несколько доменов в Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="bd216-114">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- <span data-ttu-id="bd216-115">[Как перенести домен из Microsoft 365 на другой узел?]</span><span class="sxs-lookup"><span data-stu-id="bd216-115">[How do I transfer a domain from Microsoft 365 to another host?]</span></span>
- [<span data-ttu-id="bd216-116">Почему у меня есть домен onmicrosoft.com?</span><span class="sxs-lookup"><span data-stu-id="bd216-116">Why do I have an "onmicrosoft.com" domain?</span></span>](#why-do-i-have-an-onmicrosoftcom-domain)
- [<span data-ttu-id="bd216-117">Почему у меня есть домен "onmicrosoft.de"?</span><span class="sxs-lookup"><span data-stu-id="bd216-117">Why do I have an "onmicrosoft.de" domain?</span></span>](#why-do-i-have-an-onmicrosoftde-domain)
- [<span data-ttu-id="bd216-118">Как проверить статус некоммерческой или образования?</span><span class="sxs-lookup"><span data-stu-id="bd216-118">How do I verify my nonprofit or education status?</span></span>](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="bd216-119">Что такое приоритет записей MX?</span><span class="sxs-lookup"><span data-stu-id="bd216-119">What is MX priority?</span></span>

<span data-ttu-id="bd216-120">Почта доставляется на сервер почтового обменника, который имеет наименьший номер предпочтения (наивысший приоритет), поэтому у записи MX, которая используется для маршрутизации, должен быть наименьший номер предпочтения (обычно 0) или  *высокий*  приоритет.</span><span class="sxs-lookup"><span data-stu-id="bd216-120">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="bd216-121">При создании записи MX большинство поставщиков услуг размещения DNS требуют указать номер предпочтения.</span><span class="sxs-lookup"><span data-stu-id="bd216-121">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="bd216-122">В некоторых службах соответствующий параметр называется  *предпочтением*  , а в некоторых   *приоритетом*  .</span><span class="sxs-lookup"><span data-stu-id="bd216-122">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="bd216-123">В некоторых требуется указать число, а в некоторых  выбрать значение  *Низкий*  ,  *Средний*  или  *Высокий*  .</span><span class="sxs-lookup"><span data-stu-id="bd216-123">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="bd216-124">Если у вас только одна запись MX, подойдет любое значение.</span><span class="sxs-lookup"><span data-stu-id="bd216-124">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="bd216-125">Если у вас есть несколько таких записей, убедитесь, что запись MX, используемая для маршрутизации почты, имеет более высокий приоритет, чем та, которая применяется для подтверждения владения доменом.</span><span class="sxs-lookup"><span data-stu-id="bd216-125">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="bd216-126">Как проверить записи SPF для домена?</span><span class="sxs-lookup"><span data-stu-id="bd216-126">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="bd216-127">Важно иметь или создать  **только одну запись TXT для SPF**.</span><span class="sxs-lookup"><span data-stu-id="bd216-127">It's important that you have or create  **only one TXT record for SPF**.</span></span> <span data-ttu-id="bd216-128">Если у вас уже есть запись SPF, добавьте к ней новые значения Microsoft 365, а не создайте новую.</span><span class="sxs-lookup"><span data-stu-id="bd216-128">If you already have an SPF record, you should append the new Microsoft 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="bd216-129">После добавления или обновления записи SPF для электронной почты Майкрософт необходимо убедиться в правильности синтаксиса с помощью одного из следующих средств:</span><span class="sxs-lookup"><span data-stu-id="bd216-129">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="bd216-130">Инструменты для тестирования записей SPF</span><span class="sxs-lookup"><span data-stu-id="bd216-130">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="bd216-131">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="bd216-131">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="bd216-132">Веб-интерфейс Dig</span><span class="sxs-lookup"><span data-stu-id="bd216-132">Dig web interface</span></span>](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a><span data-ttu-id="bd216-133">Что такое доменное имя?</span><span class="sxs-lookup"><span data-stu-id="bd216-133">What is a domain name?</span></span>

<span data-ttu-id="bd216-p103">Домен  это уникальное имя, которое указано после символа **@** в адресах электронной почты и после **www.** в веб-адресах. Как правило, за основу берется название вашей организации, к которому добавляется стандартный суффикс, например  *vasha_kompaniya.com*  или  *universitet.edu*  .</span><span class="sxs-lookup"><span data-stu-id="bd216-p103">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.** in web addresses. It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="bd216-137">Использование собственного домена, например "**роб \@ contoso.com**" с Microsoft 365, поможет вам создавать сведения о доходе и распознавание для вашей фирменной символики.</span><span class="sxs-lookup"><span data-stu-id="bd216-137">Using a custom domain like "**rob\@contoso.com**" with Microsoft 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="bd216-138">Вы можете [приобрести домен в Microsoft 365, а также настроить его автоматически](../get-help-with-domains/buy-a-domain-name.md)или приобрести у регистратора доменных имен, которым вы уже владеете.</span><span class="sxs-lookup"><span data-stu-id="bd216-138">You can [buy a domain in Microsoft 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="bd216-139">Что произойдет, если поставщик DNS не поддерживает некоторые типы записей?</span><span class="sxs-lookup"><span data-stu-id="bd216-139">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="bd216-140">Если вы управляете собственными DNS-записями, а узел DNS не поддерживает все записи DNS, необходимые для Microsoft 365, некоторые функции Microsoft 365 не будут работать.</span><span class="sxs-lookup"><span data-stu-id="bd216-140">If you manage your own DNS records and your DNS host does not support all the DNS records that Microsoft 365 needs, some Microsoft 365 features won't work.</span></span> <span data-ttu-id="bd216-141">Мы рекомендуем передать домен регистратору, который поддерживает все необходимые записи DNS.</span><span class="sxs-lookup"><span data-stu-id="bd216-141">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="bd216-142">Поставщики, поддерживающие все необходимые записи DNS:</span><span class="sxs-lookup"><span data-stu-id="bd216-142">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="bd216-143">Dynadot</span><span class="sxs-lookup"><span data-stu-id="bd216-143">Dynadot</span></span>
    
- <span data-ttu-id="bd216-144">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="bd216-144">eNomCentral</span></span>
    
- <span data-ttu-id="bd216-145">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="bd216-145">Europe Registry</span></span>
    
- <span data-ttu-id="bd216-146">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="bd216-146">GoDaddy</span></span>
    
- <span data-ttu-id="bd216-147">Hover</span><span class="sxs-lookup"><span data-stu-id="bd216-147">Hover</span></span>
    
- <span data-ttu-id="bd216-148">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="bd216-148">MyHosting.com</span></span>
    
- <span data-ttu-id="bd216-149">Name.com</span><span class="sxs-lookup"><span data-stu-id="bd216-149">Name.com</span></span>
    
- <span data-ttu-id="bd216-150">Nearly Free Speech</span><span class="sxs-lookup"><span data-stu-id="bd216-150">Nearly Free Speech</span></span>
    
- <span data-ttu-id="bd216-151">Nettica</span><span class="sxs-lookup"><span data-stu-id="bd216-151">Nettica</span></span>
    
- <span data-ttu-id="bd216-152">Network Information Center (NIC)</span><span class="sxs-lookup"><span data-stu-id="bd216-152">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="bd216-153">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="bd216-153">Network Solutions</span></span>
    
- <span data-ttu-id="bd216-154">Register.com</span><span class="sxs-lookup"><span data-stu-id="bd216-154">Register.com</span></span>
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a><span data-ttu-id="bd216-155">Как задать или изменить домен по умолчанию в Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="bd216-155">How do I set or change the default domain in Microsoft 365?</span></span>

<span data-ttu-id="bd216-156">Вы должны иметь по крайней мере один личный домен, добавленный в Microsoft 365, прежде чем вы сможете выбрать домен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bd216-156">You must have at least one custom domain that you've added to Microsoft 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="bd216-157">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="bd216-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="bd216-158">В Центре администрирования перейдите на страницу **Settings** (Параметры) > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="bd216-158">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="bd216-159">В Центре администрирования перейдите на страницу **Settings** (Параметры) > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="bd216-159">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="bd216-160">На странице **Domains (домены** ) выберите домен, который требуется установить в качестве значения по умолчанию для новых адресов электронной почты.</span><span class="sxs-lookup"><span data-stu-id="bd216-160">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="bd216-161">Нажмите кнопку **По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="bd216-161">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="bd216-162">Изменить имя первоначального домена  *.onmicrosoft.com*  невозможно.</span><span class="sxs-lookup"><span data-stu-id="bd216-162">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="bd216-163">Имя начального домена  *onmicrosoft.de*  нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="bd216-163">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="bd216-164">Имя начального домена  *Partner.onmschina.CN*  нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="bd216-164">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a><span data-ttu-id="bd216-165">Можно ли добавить настраиваемые поддомены или несколько доменов в Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="bd216-165">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="bd216-166">Да.</span><span class="sxs-lookup"><span data-stu-id="bd216-166">Yes.</span></span> <span data-ttu-id="bd216-167">Чтобы добавить поддомены, необходимо управлять собственными параметрами DNS на веб-сайте регистратора.</span><span class="sxs-lookup"><span data-stu-id="bd216-167">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="bd216-168">Если вы разработаны Майкрософт для управления параметрами DNS с записями NS или если вы приобрели домен от корпорации Майкрософт, вы не сможете добавить поддомены.</span><span class="sxs-lookup"><span data-stu-id="bd216-168">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="bd216-169">Нет!</span><span class="sxs-lookup"><span data-stu-id="bd216-169">Yes!</span></span> <span data-ttu-id="bd216-170">Чтобы добавить поддомены, необходимо управлять собственными параметрами DNS на веб-сайте регистратора.</span><span class="sxs-lookup"><span data-stu-id="bd216-170">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="bd216-171">Если вы разработаны Майкрософт для управления параметрами DNS с записями NS или если вы приобрели домен от корпорации Майкрософт, вы не сможете добавить поддомены.</span><span class="sxs-lookup"><span data-stu-id="bd216-171">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="bd216-172">Нет!</span><span class="sxs-lookup"><span data-stu-id="bd216-172">Yes!</span></span> <span data-ttu-id="bd216-173">Чтобы добавить поддомены, необходимо управлять собственными параметрами DNS на веб-сайте регистратора.</span><span class="sxs-lookup"><span data-stu-id="bd216-173">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="bd216-174">Если вы разпозволяете 21Vianet управлять параметрами DNS с записями NS, вы не можете добавлять поддомены.</span><span class="sxs-lookup"><span data-stu-id="bd216-174">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="bd216-175">Как правило, в подписку Microsoft 365 можно добавить до 900 доменов.</span><span class="sxs-lookup"><span data-stu-id="bd216-175">Typically, you can add up to 900 domains to your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="bd216-176">Например, вы можете добавить домены contoso.com и contosomarketing.com, а затем  поддомены www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com и т. д.</span><span class="sxs-lookup"><span data-stu-id="bd216-176">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="bd216-177">При добавлении дочернего домена он автоматически проверяется в соответствии с проверяемым родительским доменом.</span><span class="sxs-lookup"><span data-stu-id="bd216-177">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="bd216-178">При добавлении нескольких доменов в Microsoft 365 можно разместить любую службу (например, электронную почту) для всех добавленных доменов.</span><span class="sxs-lookup"><span data-stu-id="bd216-178">When you add multiple domains to Microsoft 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="bd216-179">*Когда вы изменяете электронную почту на Microsoft 365, обновляя запись MX в домене, все сообщения, отправленные на этот домен, начнут приходить в Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="bd216-179">*When you change your email to Microsoft 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Microsoft 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="bd216-180">Если вы добавили домен contoso.com в подписку на Microsoft 365, вы также можете добавить xyz.contoso.com дочернего домена в другую организацию Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bd216-180">If you added a contoso.com domain to a Microsoft 365 subscription, you can also add the subdomain xyz.contoso.com to another Microsoft 365 organization.</span></span> <span data-ttu-id="bd216-181">При добавлении поддомена вам будет предложено добавить запись TXT в поставщик услуг хостинга DNS.</span><span class="sxs-lookup"><span data-stu-id="bd216-181">When adding the subdomain, you are prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="how-do-i-transfer-a-domain-from-microsoft-365-to-another-host"></a><span data-ttu-id="bd216-182">Как перенести домен из Microsoft 365 на другой узел?</span><span class="sxs-lookup"><span data-stu-id="bd216-182">How do I transfer a domain from Microsoft 365 to another host?</span></span>

<span data-ttu-id="bd216-183">Процедура переноса домена приведена в [статье передача домена из Майкрософт на другой узел](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host).</span><span class="sxs-lookup"><span data-stu-id="bd216-183">For the procedure to transfer a domain, see [Transfer a domain from Microsoft to another host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host).</span></span>

## <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="bd216-184">Тестирование Microsoft 365 с личного домена</span><span class="sxs-lookup"><span data-stu-id="bd216-184">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="bd216-185">Для процедуры пилотного развертывания Microsoft 365 электронной почты из пользовательского домена в почтовый ящик Microsoft 365, ознакомьтесь со статьей [Пилотная версия microsoft 365 из личного домена](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain).</span><span class="sxs-lookup"><span data-stu-id="bd216-185">For the procedure to pilot Microsoft 365 email functionality from a custom domain to a Microsoft 365 mailbox, see [Pilot Microsoft 365 from my custom domain](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain).</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="bd216-186">Почему у меня есть домен onmicrosoft.com?</span><span class="sxs-lookup"><span data-stu-id="bd216-186">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="bd216-187">Microsoft 365 создает домен, например *contoso.onmicrosoft.com*, при регистрации в службе.</span><span class="sxs-lookup"><span data-stu-id="bd216-187">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="bd216-188">Идентификатор пользователя, который вы создаете при регистрации, включает домен, например *Alan@contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="bd216-188">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="bd216-189">**Если вы хотите, чтобы ваша электронная почта выглядела как *Сергей \@ contoso.com*:** [купите домен](../get-help-with-domains/buy-a-domain-name.md) или просто выполните действия, описанные в статье [Добавление пользователей и доменов в Microsoft 365](add-domain.md) , если у вас уже есть.</span><span class="sxs-lookup"><span data-stu-id="bd216-189">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="bd216-190">**Домен onmicrosoft невозможно переименовать после регистрации.**</span><span class="sxs-lookup"><span data-stu-id="bd216-190">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="bd216-191">Например, если первоначально вы выбрали домен fourthcoffee.onmicrosoft.com, его не удастся переименовать в fabrikam.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="bd216-191">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="bd216-192">Чтобы использовать другой домен onmicrosoft.com, вам потребуется начать новую подписку с помощью Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bd216-192">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="bd216-193">**Вы не можете переименовать URL-адрес сайта группы.**</span><span class="sxs-lookup"><span data-stu-id="bd216-193">**You can't rename your team site URL.**</span></span> <span data-ttu-id="bd216-194">URL-адрес сайта группы основан на вашем доменном имени onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="bd216-194">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="bd216-195">К сожалению, из-за способа работы архитектуры SharePoint Online нельзя переименовать сайт группы.</span><span class="sxs-lookup"><span data-stu-id="bd216-195">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="bd216-196">**Домен onmicrosoft невозможно удалить.**</span><span class="sxs-lookup"><span data-stu-id="bd216-196">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="bd216-197">Microsoft 365 необходимо обойти, так как она используется в фоновом режиме для вашей подписки.</span><span class="sxs-lookup"><span data-stu-id="bd216-197">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="bd216-198">Несмотря на это, вы можете им не пользоваться, если добавите личный домен.</span><span class="sxs-lookup"><span data-stu-id="bd216-198">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="bd216-p114">При желании можно продолжить использование исходного домена onmicrosoft.com даже после добавления личного домена. Он будет поддерживаться в электронной почте и других службах.</span><span class="sxs-lookup"><span data-stu-id="bd216-p114">You can keep using the initial onmicrosoft.com domain even after you add your domain. It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="bd216-201">Почему у меня есть домен "onmicrosoft.de"?</span><span class="sxs-lookup"><span data-stu-id="bd216-201">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="bd216-202">Microsoft 365 создает домен, например *contoso.onmicrosoft.de*, при регистрации в службе.</span><span class="sxs-lookup"><span data-stu-id="bd216-202">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="bd216-203">Идентификатор пользователя, который вы создаете при регистрации, включает домен, например *Alan@contoso.onmicrosoft.de*.</span><span class="sxs-lookup"><span data-stu-id="bd216-203">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="bd216-204">**Если вы хотите, чтобы ваша электронная почта выглядела как *Alan@contoso.de*:** [купите домен](../get-help-with-domains/buy-a-domain-name.md) или просто выполните действия, описанные в [статье Добавление пользователей и доменов в Microsoft 365](add-domain.md) , если вы уже являетесь ее владельцем.</span><span class="sxs-lookup"><span data-stu-id="bd216-204">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="bd216-205">**Домен onmicrosoft невозможно переименовать после регистрации.**</span><span class="sxs-lookup"><span data-stu-id="bd216-205">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="bd216-206">Например, если исходный домен, который вы выбрали, был fourthcoffee.onmicrosoft.de, его нельзя изменить на fabrikam.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="bd216-206">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="bd216-207">Чтобы использовать другой домен onmicrosoft.de, вам потребуется начать новую подписку с помощью Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bd216-207">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="bd216-208">**Вы не можете переименовать URL-адрес сайта группы.**</span><span class="sxs-lookup"><span data-stu-id="bd216-208">**You can't rename your team site URL.**</span></span> <span data-ttu-id="bd216-209">URL-адрес сайта группы основан на вашем доменном имени onmicrosoft.de. К сожалению, из-за способа работы архитектуры SharePoint Online нельзя переименовать сайт группы.</span><span class="sxs-lookup"><span data-stu-id="bd216-209">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="bd216-210">**Домен onmicrosoft невозможно удалить.**</span><span class="sxs-lookup"><span data-stu-id="bd216-210">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="bd216-211">Microsoft 365 необходимо обойти, так как она используется в фоновом режиме для вашей подписки.</span><span class="sxs-lookup"><span data-stu-id="bd216-211">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="bd216-212">Несмотря на это, вы можете им не пользоваться, если добавите личный домен.</span><span class="sxs-lookup"><span data-stu-id="bd216-212">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="bd216-213">Вы можете продолжить работу с исходным доменом onmicrosoft.de, даже после добавления домена.</span><span class="sxs-lookup"><span data-stu-id="bd216-213">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="bd216-214">Он будет поддерживаться в электронной почте и других службах.</span><span class="sxs-lookup"><span data-stu-id="bd216-214">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="bd216-215">Как проверить статус некоммерческой или образования?</span><span class="sxs-lookup"><span data-stu-id="bd216-215">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="bd216-216">В [центре администрирования](https://docs.microsoft.com/microsoft-365/admin/admin-home) выберите пункт **Настройка** , чтобы запустить мастер.</span><span class="sxs-lookup"><span data-stu-id="bd216-216">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="bd216-217">(Сначала войдите в Microsoft 365.)</span><span class="sxs-lookup"><span data-stu-id="bd216-217">(Be sure to sign in to Microsoft 365 first.)</span></span> 
    
2. <span data-ttu-id="bd216-218">Чтобы стать администратором учебного заведения, выберите параметр  **становится** администратором в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bd216-218">To become the admin for your school, select the  **Become an admin** option in Microsoft 365.</span></span> 
    
3. <span data-ttu-id="bd216-219">Вам будет предложено добавить запись DNS в формате TXT на веб-сайт узла DNS для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="bd216-219">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="bd216-220">Почему?</span><span class="sxs-lookup"><span data-stu-id="bd216-220">Why?</span></span> <span data-ttu-id="bd216-221">Так как при входе на узел DNS и добавлении записи в домен вы подтверждаете в Microsoft 365, что вы владеете доменным именем.</span><span class="sxs-lookup"><span data-stu-id="bd216-221">Because by signing in at the DNS host and adding a record for your domain, you prove to Microsoft 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="bd216-222">После добавления записи вы вернетесь на портал Microsoft 365 и подтвердите, что она добавлена, поэтому Microsoft 365 может проверить.</span><span class="sxs-lookup"><span data-stu-id="bd216-222">After you add the record, you'll go back to the Microsoft 365 portal and confirm that you've added it, so Microsoft 365 can check.</span></span>
    
<span data-ttu-id="bd216-223">У вас есть некоммерческие и хотите получить Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="bd216-223">Have a nonprofit and want to get Microsoft 365?</span></span> <span data-ttu-id="bd216-224">[Убедитесь, что ваша организация](https://www.microsoft.com/en-us/nonprofits/eligibility) поддается уточнению и зарегистрируйте ее.</span><span class="sxs-lookup"><span data-stu-id="bd216-224">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="bd216-225">Хотите узнать больше о том, как стать администратором учебного заведения?</span><span class="sxs-lookup"><span data-stu-id="bd216-225">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="bd216-226">[Узнайте больше об этом](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span><span class="sxs-lookup"><span data-stu-id="bd216-226">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>