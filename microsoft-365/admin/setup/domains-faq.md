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
description: Узнайте больше о доменах, накоторых наследовать ответы на часто задаваемые вопросы.
ms.openlocfilehash: fe602c45059be1b273b7ebe3a11cd91adf89a479
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845848"
---
# <a name="domains-faq"></a><span data-ttu-id="3fc0c-103">Вопросы и ответы о доменах</span><span class="sxs-lookup"><span data-stu-id="3fc0c-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="3fc0c-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-104">The admin center is changing.</span></span> <span data-ttu-id="3fc0c-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="3fc0c-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="3fc0c-106">В этой статье содержатся ответы на часто задаваемые вопросы о доменах в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-106">This article contains answers to frequently asked questions about domains in Microsoft 365.</span></span>

<span data-ttu-id="3fc0c-107">Если вы не нашли ответ на свой вопрос, оставьте комментарий и мы добавим его в список.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>

<span data-ttu-id="3fc0c-108">В этой статье</span><span class="sxs-lookup"><span data-stu-id="3fc0c-108">In this article</span></span>

- [<span data-ttu-id="3fc0c-109">Что такое приоритет записей MX?</span><span class="sxs-lookup"><span data-stu-id="3fc0c-109">What is MX priority?</span></span>](#what-is-mx-priority)
- [<span data-ttu-id="3fc0c-110">Как проверить записи SPF для домена?</span><span class="sxs-lookup"><span data-stu-id="3fc0c-110">How can I validate SPF records for my domain?</span></span>](#how-can-i-validate-spf-records-for-my-domain)
- [<span data-ttu-id="3fc0c-111">Что такое доменное имя?</span><span class="sxs-lookup"><span data-stu-id="3fc0c-111">What is a domain name?</span></span>](#what-is-a-domain-name)
- [<span data-ttu-id="3fc0c-112">Что произойдет, если поставщик DNS не поддерживает некоторые типы записей?</span><span class="sxs-lookup"><span data-stu-id="3fc0c-112">What happens if my DNS provider doesn't support certain record types?</span></span>](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
- [<span data-ttu-id="3fc0c-113">Как установить или изменить домен по умолчанию в Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="3fc0c-113">How do I set or change the default domain in Microsoft 365?</span></span>](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [<span data-ttu-id="3fc0c-114">Могу ли я добавлять пользовательские поддомены или несколько доменов в Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="3fc0c-114">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- [<span data-ttu-id="3fc0c-115">Как перенести домен из Microsoft 365 в другой узел?</span><span class="sxs-lookup"><span data-stu-id="3fc0c-115">How do I transfer a domain from Microsoft 365 to another host?</span></span>](#how-do-i-transfer-a-domain-from-microsoft-365-to-another-host)
- [<span data-ttu-id="3fc0c-116">Почему у меня есть домен onmicrosoft.com?</span><span class="sxs-lookup"><span data-stu-id="3fc0c-116">Why do I have an "onmicrosoft.com" domain?</span></span>](#why-do-i-have-an-onmicrosoftcom-domain)
- [<span data-ttu-id="3fc0c-117">Почему у меня есть onmicrosoft.de?</span><span class="sxs-lookup"><span data-stu-id="3fc0c-117">Why do I have an "onmicrosoft.de" domain?</span></span>](#why-do-i-have-an-onmicrosoftde-domain)
- [<span data-ttu-id="3fc0c-118">Как проверить состояние некоммерческого использования или образования?</span><span class="sxs-lookup"><span data-stu-id="3fc0c-118">How do I verify my nonprofit or education status?</span></span>](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="3fc0c-119">Что такое приоритет записей MX?</span><span class="sxs-lookup"><span data-stu-id="3fc0c-119">What is MX priority?</span></span>

<span data-ttu-id="3fc0c-120">Почта доставляется на сервер почтового обменника, который имеет наименьший номер предпочтения (наивысший приоритет), поэтому у записи MX, которая используется для маршрутизации, должен быть наименьший номер предпочтения (обычно 0) или  *высокий*  приоритет.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-120">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="3fc0c-121">При создании записи MX большинство поставщиков услуг размещения DNS требуют указать номер предпочтения.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-121">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="3fc0c-122">В некоторых службах соответствующий параметр называется  *предпочтением*  , а в некоторых   *приоритетом*  .</span><span class="sxs-lookup"><span data-stu-id="3fc0c-122">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="3fc0c-123">В некоторых требуется указать число, а в некоторых  выбрать значение  *Низкий*  ,  *Средний*  или  *Высокий*  .</span><span class="sxs-lookup"><span data-stu-id="3fc0c-123">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="3fc0c-124">Если у вас только одна запись MX, подойдет любое значение.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-124">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="3fc0c-125">Если у вас есть несколько таких записей, убедитесь, что запись MX, используемая для маршрутизации почты, имеет более высокий приоритет, чем та, которая применяется для подтверждения владения доменом.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-125">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="3fc0c-126">Как проверить записи SPF для домена?</span><span class="sxs-lookup"><span data-stu-id="3fc0c-126">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="3fc0c-127">Важно использовать только одну запись **TXT для spF.**</span><span class="sxs-lookup"><span data-stu-id="3fc0c-127">It's important that you have or create  **only one TXT record for SPF**.</span></span> <span data-ttu-id="3fc0c-128">Если у вас уже есть запись SPF, нужно добавить в нее новые значения Microsoft 365, а не создавать новую.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-128">If you already have an SPF record, you should append the new Microsoft 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="3fc0c-129">После добавления или обновления записи SPF для электронной почты Майкрософт проверьте правильности синтаксиса с помощью одного из следующих средств:</span><span class="sxs-lookup"><span data-stu-id="3fc0c-129">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="3fc0c-130">Инструменты для тестирования записей SPF</span><span class="sxs-lookup"><span data-stu-id="3fc0c-130">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="3fc0c-131">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="3fc0c-131">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="3fc0c-132">Веб-интерфейс Dig</span><span class="sxs-lookup"><span data-stu-id="3fc0c-132">Dig web interface</span></span>](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a><span data-ttu-id="3fc0c-133">Что такое доменное имя?</span><span class="sxs-lookup"><span data-stu-id="3fc0c-133">What is a domain name?</span></span>

<span data-ttu-id="3fc0c-p103">Домен  это уникальное имя, которое указано после символа **@** в адресах электронной почты и после **www.** в веб-адресах. Как правило, за основу берется название вашей организации, к которому добавляется стандартный суффикс, например  *vasha_kompaniya.com*  или  *universitet.edu*  .</span><span class="sxs-lookup"><span data-stu-id="3fc0c-p103">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.** in web addresses. It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="3fc0c-137">Использование личного домена, например\*\* \@ "надежного contoso.com" с\*\*Microsoft 365, помогает сформировать доверие и повысить свою торговую марку.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-137">Using a custom domain like "**rob\@contoso.com**" with Microsoft 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="3fc0c-138">В [Microsoft 365 можно купить](../get-help-with-domains/buy-a-domain-name.md)домен в Microsoft 365 и настроить его автоматически, или вы можете купить или воспользоваться им ее у регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-138">You can [buy a domain in Microsoft 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="3fc0c-139">Что произойдет, если поставщик DNS не поддерживает некоторые типы записей?</span><span class="sxs-lookup"><span data-stu-id="3fc0c-139">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="3fc0c-140">Если вы управляете своими записями DNS сами, но ваш узел DNS поддерживает не все записи, необходимые для Microsoft 365, некоторые функции Microsoft 365 не будут работать.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-140">If you manage your own DNS records and your DNS host does not support all the DNS records that Microsoft 365 needs, some Microsoft 365 features won't work.</span></span> <span data-ttu-id="3fc0c-141">Мы рекомендуем передать домен регистратору, который поддерживает все необходимые записи DNS.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-141">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="3fc0c-142">Поставщики, поддерживающие все необходимые записи DNS:</span><span class="sxs-lookup"><span data-stu-id="3fc0c-142">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="3fc0c-143">Dynadot</span><span class="sxs-lookup"><span data-stu-id="3fc0c-143">Dynadot</span></span>
    
- <span data-ttu-id="3fc0c-144">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="3fc0c-144">eNomCentral</span></span>
    
- <span data-ttu-id="3fc0c-145">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="3fc0c-145">Europe Registry</span></span>
    
- <span data-ttu-id="3fc0c-146">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="3fc0c-146">GoDaddy</span></span>
    
- <span data-ttu-id="3fc0c-147">Hover</span><span class="sxs-lookup"><span data-stu-id="3fc0c-147">Hover</span></span>
    
- <span data-ttu-id="3fc0c-148">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="3fc0c-148">MyHosting.com</span></span>
    
- <span data-ttu-id="3fc0c-149">Name.com</span><span class="sxs-lookup"><span data-stu-id="3fc0c-149">Name.com</span></span>
    
- <span data-ttu-id="3fc0c-150">Nearly Free Speech</span><span class="sxs-lookup"><span data-stu-id="3fc0c-150">Nearly Free Speech</span></span>
    
- <span data-ttu-id="3fc0c-151">Nettica</span><span class="sxs-lookup"><span data-stu-id="3fc0c-151">Nettica</span></span>
    
- <span data-ttu-id="3fc0c-152">Network Information Center (NIC)</span><span class="sxs-lookup"><span data-stu-id="3fc0c-152">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="3fc0c-153">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="3fc0c-153">Network Solutions</span></span>
    
- <span data-ttu-id="3fc0c-154">Register.com</span><span class="sxs-lookup"><span data-stu-id="3fc0c-154">Register.com</span></span>
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a><span data-ttu-id="3fc0c-155">Как установить или изменить домен по умолчанию в Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="3fc0c-155">How do I set or change the default domain in Microsoft 365?</span></span>

<span data-ttu-id="3fc0c-156">Чтобы можно было выбрать домен по умолчанию, необходимо добавить хотя бы один настроенный домен, добавленный в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-156">You must have at least one custom domain that you've added to Microsoft 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3fc0c-157">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="3fc0c-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3fc0c-158">В Центре администрирования перейдите на страницу **Settings** (Параметры) > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="3fc0c-158">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3fc0c-159">В Центре администрирования перейдите на страницу **Settings** (Параметры) > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="3fc0c-159">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="3fc0c-160">На странице **"Домены"** выберите домен, который необходимо использовать по умолчанию для новых адресов электронной почты.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-160">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="3fc0c-161">Нажмите кнопку **По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-161">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="3fc0c-162">Изменить имя первоначального домена  *.onmicrosoft.com*  невозможно.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-162">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="3fc0c-163">Невозможно изменить имя исходного *домена .onmicrosoft.de.*</span><span class="sxs-lookup"><span data-stu-id="3fc0c-163">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="3fc0c-164">Невозможно изменить имя исходного *домена partner.onmschina.cn нельзя.*</span><span class="sxs-lookup"><span data-stu-id="3fc0c-164">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a><span data-ttu-id="3fc0c-165">Могу ли я добавлять пользовательские поддомены или несколько доменов в Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="3fc0c-165">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="3fc0c-166">Да.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-166">Yes.</span></span> <span data-ttu-id="3fc0c-167">Чтобы добавить поддомены, необходимо управлять собственными настройками DNS на веб-сайте регистратора.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-167">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="3fc0c-168">Если вы позволяете Майкрософт управлять параметрами DNS с записями nS или если вы его купили на сайте Майкрософт, вы не сможете добавить поддомены.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-168">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="3fc0c-169">Да!</span><span class="sxs-lookup"><span data-stu-id="3fc0c-169">Yes!</span></span> <span data-ttu-id="3fc0c-170">Чтобы добавить поддомены, необходимо управлять собственными настройками DNS на веб-сайте регистратора.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-170">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="3fc0c-171">Если вы позволяете Майкрософт управлять параметрами DNS с записями nS или если вы его купили на сайте Майкрософт, вы не сможете добавить поддомены.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-171">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="3fc0c-172">Да!</span><span class="sxs-lookup"><span data-stu-id="3fc0c-172">Yes!</span></span> <span data-ttu-id="3fc0c-173">Чтобы добавить поддомены, необходимо управлять собственными настройками DNS на веб-сайте регистратора.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-173">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="3fc0c-174">Если вы дали возможности управлять параметрами DNS с записями NS в 21Vianet, вы не сможете добавить поддомены.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-174">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="3fc0c-175">Обычно в подписку Microsoft 365 можно добавить до 900 доменов.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-175">Typically, you can add up to 900 domains to your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="3fc0c-176">Например, вы можете добавить домены contoso.com и contosomarketing.com, а затем  поддомены www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com и т. д.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-176">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="3fc0c-177">При добавлении поддомена он автоматически проверяется на основе проверяемого родительского домена.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-177">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="3fc0c-178">При добавлении в Microsoft 365 нескольких доменов в любом из добавленных вами доменов можно разместить любую службу (например, почтовую).</span><span class="sxs-lookup"><span data-stu-id="3fc0c-178">When you add multiple domains to Microsoft 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="3fc0c-179">*Когда вы меняете электронную почту в Microsoft 365, обновывая запись MX домена, все сообщения, отправляемые в этот домен, будут поступать в Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="3fc0c-179">*When you change your email to Microsoft 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Microsoft 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="3fc0c-180">Если вы добавили contoso.com в подписку на Microsoft 365, вы также можете добавить дочернего домена xyz.contoso.com к другой организации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-180">If you added a contoso.com domain to a Microsoft 365 subscription, you can also add the subdomain xyz.contoso.com to another Microsoft 365 organization.</span></span> <span data-ttu-id="3fc0c-181">При добавлении поддомена вам будет предложено добавить запись TXT в поставщик услуг размещения DNS.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-181">When adding the subdomain, you are prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="how-do-i-transfer-a-domain-from-microsoft-365-to-another-host"></a><span data-ttu-id="3fc0c-182">Как перенести домен из Microsoft 365 в другой узел?</span><span class="sxs-lookup"><span data-stu-id="3fc0c-182">How do I transfer a domain from Microsoft 365 to another host?</span></span>

<span data-ttu-id="3fc0c-183">Процедура передачи домена см. в разделе ["Передача домена из Майкрософт на другой узел".](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host)</span><span class="sxs-lookup"><span data-stu-id="3fc0c-183">For the procedure to transfer a domain, see [Transfer a domain from Microsoft to another host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host).</span></span>

## <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="3fc0c-184">Тестирование Microsoft 365 с личного домена</span><span class="sxs-lookup"><span data-stu-id="3fc0c-184">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="3fc0c-185">Процедуру пилотной работы с электронной почтой Microsoft 365 с личного домена в почтовый ящик Microsoft 365 см. в [пилотном проекте Microsoft 365 из своего личного домена.](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain)</span><span class="sxs-lookup"><span data-stu-id="3fc0c-185">For the procedure to pilot Microsoft 365 email functionality from a custom domain to a Microsoft 365 mailbox, see [Pilot Microsoft 365 from my custom domain](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain).</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="3fc0c-186">Почему у меня есть домен onmicrosoft.com?</span><span class="sxs-lookup"><span data-stu-id="3fc0c-186">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="3fc0c-187">После регистрации в службе Microsoft 365 *создает contoso.onmicrosoft.com.*</span><span class="sxs-lookup"><span data-stu-id="3fc0c-187">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="3fc0c-188">Он будет исползован при регистрации *(например, alan@contoso.onmicrosoft.com).*</span><span class="sxs-lookup"><span data-stu-id="3fc0c-188">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="3fc0c-189">**Если вы хотите, чтобы ваша электронная почта \* \@ выглядела как contoso.com-адрес, или**\* выполните действия, описанные в разделе Добавление пользователей и домена в Microsoft [365,](add-domain.md) если вы уже принадлежите ему. [buy the domain](../get-help-with-domains/buy-a-domain-name.md)</span><span class="sxs-lookup"><span data-stu-id="3fc0c-189">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="3fc0c-190">**Домен onmicrosoft невозможно переименовать после регистрации.**</span><span class="sxs-lookup"><span data-stu-id="3fc0c-190">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="3fc0c-191">Например, если первоначально вы выбрали домен fourthcoffee.onmicrosoft.com, его не удастся переименовать в fabrikam.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-191">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="3fc0c-192">Чтобы использовать другой onmicrosoft.com, необходимо создать новую подписку в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-192">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="3fc0c-193">**URL-адрес сайта группы переименовать нельзя.**</span><span class="sxs-lookup"><span data-stu-id="3fc0c-193">**You can't rename your team site URL.**</span></span> <span data-ttu-id="3fc0c-194">URL-адрес сайта группы основан на onmicrosoft.com вашего имени.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-194">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="3fc0c-195">К сожалению, из-за такого способа архитектуры SharePoint Online невозможно переименовать сайт группы.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-195">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="3fc0c-196">**Домен onmicrosoft невозможно удалить.**</span><span class="sxs-lookup"><span data-stu-id="3fc0c-196">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="3fc0c-197">Microsoft 365 необходимо держать это решение, так как она используется в нем в своей подписке в работе.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-197">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="3fc0c-198">Несмотря на это, вы можете им не пользоваться, если добавите личный домен.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-198">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="3fc0c-p114">При желании можно продолжить использование исходного домена onmicrosoft.com даже после добавления личного домена. Он будет поддерживаться в электронной почте и других службах.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-p114">You can keep using the initial onmicrosoft.com domain even after you add your domain. It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="3fc0c-201">Почему у меня есть onmicrosoft.de?</span><span class="sxs-lookup"><span data-stu-id="3fc0c-201">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="3fc0c-202">При регистрации в службе Microsoft 365 создает *для вас домен, например contoso.onmicrosoft.de.*</span><span class="sxs-lookup"><span data-stu-id="3fc0c-202">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="3fc0c-203">Он будет исползован при регистрации *(например, alan@contoso.onmicrosoft.de.*</span><span class="sxs-lookup"><span data-stu-id="3fc0c-203">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="3fc0c-204">**Если вы хотите, чтобы *ваше сообщение электронной почты выглядело как alan@contoso.de:* купите** [домен или](../get-help-with-domains/buy-a-domain-name.md) просто выполните действия, описанные в разделе Добавление пользователей и домена в [Microsoft 365,](add-domain.md) если вы уже владеете им.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-204">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="3fc0c-205">**Домен onmicrosoft невозможно переименовать после регистрации.**</span><span class="sxs-lookup"><span data-stu-id="3fc0c-205">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="3fc0c-206">Например, если первоначально вы выбрали fourthcoffee.onmicrosoft.de, не можете использовать fabrikam.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-206">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="3fc0c-207">Чтобы использовать другой onmicrosoft.de, необходимо создать новую подписку в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-207">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="3fc0c-208">**URL-адрес сайта группы переименовать нельзя.**</span><span class="sxs-lookup"><span data-stu-id="3fc0c-208">**You can't rename your team site URL.**</span></span> <span data-ttu-id="3fc0c-209">URL-адрес сайта группы основан на onmicrosoft.de имя вашего домена. К сожалению, из-за такого способа архитектуры SharePoint Online невозможно переименовать сайт группы.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-209">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="3fc0c-210">**Домен onmicrosoft невозможно удалить.**</span><span class="sxs-lookup"><span data-stu-id="3fc0c-210">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="3fc0c-211">Microsoft 365 необходимо держать это решение, так как она используется в нем в своей подписке в работе.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-211">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="3fc0c-212">Несмотря на это, вы можете им не пользоваться, если добавите личный домен.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-212">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="3fc0c-213">Можно продолжить использование исходного домена onmicrosoft.de даже после добавления домена.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-213">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="3fc0c-214">Он будет поддерживаться в электронной почте и других службах.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-214">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="3fc0c-215">Как проверить состояние некоммерческого использования или образования?</span><span class="sxs-lookup"><span data-stu-id="3fc0c-215">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="3fc0c-216">Выберите **"Настройка"** в [Центре администрирования,](https://docs.microsoft.com/microsoft-365/admin/admin-home) чтобы запустить мастер.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-216">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="3fc0c-217">(Сначала войдите в Microsoft 365.)</span><span class="sxs-lookup"><span data-stu-id="3fc0c-217">(Be sure to sign in to Microsoft 365 first.)</span></span> 
    
2. <span data-ttu-id="3fc0c-218">Чтобы стать администратором в учебном заведении, выберите  **параметр "Стать администратором"** в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-218">To become the admin for your school, select the  **Become an admin** option in Microsoft 365.</span></span> 
    
3. <span data-ttu-id="3fc0c-219">Вам будет предложено добавить запись DNS TXT на сайте узла DNS для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-219">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="3fc0c-220">Почему?</span><span class="sxs-lookup"><span data-stu-id="3fc0c-220">Why?</span></span> <span data-ttu-id="3fc0c-221">Поскольку при входе на узел DNS добавлена запись для вашего домена, вы послушаете Microsoft 365 подтвердить, что вы владеете доменным именем.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-221">Because by signing in at the DNS host and adding a record for your domain, you prove to Microsoft 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="3fc0c-222">После добавления записи вернитесь на портал Microsoft 365 и подтвердите, что вы добавили запись, чтобы Microsoft 365 мог проверить.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-222">After you add the record, you'll go back to the Microsoft 365 portal and confirm that you've added it, so Microsoft 365 can check.</span></span>
    
<span data-ttu-id="3fc0c-223">У вас есть некоммерческая организация и вам требуется получить Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="3fc0c-223">Have a nonprofit and want to get Microsoft 365?</span></span> <span data-ttu-id="3fc0c-224">[Убедитесь, что ваша организация квалифицицируется,](https://www.microsoft.com/en-us/nonprofits/eligibility) и затем зарегистрируйтесь для получения этой услуги.</span><span class="sxs-lookup"><span data-stu-id="3fc0c-224">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="3fc0c-225">Хотите узнать больше о получении прав администратора в учебном заведении?</span><span class="sxs-lookup"><span data-stu-id="3fc0c-225">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="3fc0c-226">[Узнайте о нем целиком.](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)</span><span class="sxs-lookup"><span data-stu-id="3fc0c-226">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>