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
description: Дополнительные сведения о доменах можно найти в статье ответы на свои вопросы в разделе "вопросы и ответы".
ms.openlocfilehash: a52513130f9bbbf7c4cd25d4c4827e833700d992
ms.sourcegitcommit: 9ea67fd2e02af760d4fb62e3d09c93b446173f9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/15/2020
ms.locfileid: "44739158"
---
# <a name="domains-faq"></a><span data-ttu-id="595f4-103">Вопросы и ответы о доменах</span><span class="sxs-lookup"><span data-stu-id="595f4-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="595f4-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="595f4-104">The admin center is changing.</span></span> <span data-ttu-id="595f4-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="595f4-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="595f4-106">В этой статье приводятся ответы на часто задаваемые вопросы о доменах в Office 365.</span><span class="sxs-lookup"><span data-stu-id="595f4-106">This article contains answers to Frequently Asked Questions about domains in Office 365.</span></span>

<span data-ttu-id="595f4-107">Если вы не нашли ответ на свой вопрос, оставьте комментарий, и мы добавим его.</span><span class="sxs-lookup"><span data-stu-id="595f4-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="595f4-108">Что такое приоритет записей MX?</span><span class="sxs-lookup"><span data-stu-id="595f4-108">What is MX priority?</span></span>

<span data-ttu-id="595f4-109">Почта доставляется на сервер почтового обменника, который имеет наименьший номер предпочтения (наивысший приоритет), поэтому у записи MX, которая используется для маршрутизации, должен быть наименьший номер предпочтения (обычно 0) или  *высокий*  приоритет.</span><span class="sxs-lookup"><span data-stu-id="595f4-109">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="595f4-110">При создании записи MX большинство поставщиков услуг размещения DNS требуют указать номер предпочтения.</span><span class="sxs-lookup"><span data-stu-id="595f4-110">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="595f4-111">В некоторых службах соответствующий параметр называется  *предпочтением*  , а в некоторых   *приоритетом*  .</span><span class="sxs-lookup"><span data-stu-id="595f4-111">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="595f4-112">В некоторых требуется указать число, а в некоторых  выбрать значение  *Низкий*  ,  *Средний*  или  *Высокий*  .</span><span class="sxs-lookup"><span data-stu-id="595f4-112">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="595f4-113">Если у вас только одна запись MX, подойдет любое значение.</span><span class="sxs-lookup"><span data-stu-id="595f4-113">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="595f4-114">Если у вас есть несколько таких записей, убедитесь, что запись MX, используемая для маршрутизации почты, имеет более высокий приоритет, чем та, которая применяется для подтверждения владения доменом.</span><span class="sxs-lookup"><span data-stu-id="595f4-114">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="595f4-115">Как проверить записи SPF для домена?</span><span class="sxs-lookup"><span data-stu-id="595f4-115">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="595f4-116">Важно использовать **только одну запись TXT для SPF**.</span><span class="sxs-lookup"><span data-stu-id="595f4-116">It's important that you have or create **only one TXT record for SPF**.</span></span> <span data-ttu-id="595f4-117">Если у вас уже есть запись SPF, нужно добавить в нее новые значения для Office 365, а не создавать новую.</span><span class="sxs-lookup"><span data-stu-id="595f4-117">If you already have an SPF record, you should append the new Office 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="595f4-118">После добавления или обновления записи SPF для электронной почты Майкрософт необходимо убедиться в правильности синтаксиса с помощью одного из следующих средств:</span><span class="sxs-lookup"><span data-stu-id="595f4-118">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="595f4-119">Инструменты для тестирования записей SPF</span><span class="sxs-lookup"><span data-stu-id="595f4-119">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="595f4-120">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="595f4-120">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="595f4-121">Веб-интерфейс Dig</span><span class="sxs-lookup"><span data-stu-id="595f4-121">Dig web interface</span></span>](http://digwebinterface.com/)
    
## <a name="how-does-office-365-manage-my-dns-records"></a><span data-ttu-id="595f4-122">Как Office 365 управляет записями DNS?</span><span class="sxs-lookup"><span data-stu-id="595f4-122">How does Office 365 manage my DNS records?</span></span>

<span data-ttu-id="595f4-123">Существует два способа управления DNS в Office 365:</span><span class="sxs-lookup"><span data-stu-id="595f4-123">There are two options for DNS management with Office 365:</span></span>
  
1. <span data-ttu-id="595f4-124">Вы изменяете записи сервера доменных имен (NS), а затем Майкрософт предпринимает все специфические записи, например настройку записи MX для электронной почты.</span><span class="sxs-lookup"><span data-stu-id="595f4-124">You change your nameserver (NS) records, and then Microsoft takes care of all the service-specific records, like setting up your MX record for email.</span></span> <span data-ttu-id="595f4-125">**Предложен**</span><span class="sxs-lookup"><span data-stu-id="595f4-125">**(Recommended)**</span></span>
    
2. <span data-ttu-id="595f4-126">Вы самостоятельно добавляете записи DNS для электронной почты и других служб Office 365 на своем узле DNS.</span><span class="sxs-lookup"><span data-stu-id="595f4-126">You add DNS records for email and other Office 365 services at your DNS host yourself.</span></span> <span data-ttu-id="595f4-127">**(Только для экспертов)**</span><span class="sxs-lookup"><span data-stu-id="595f4-127">**(Experts only)**</span></span>
    
### <a name="office-365-creates-and-hosts-the-dns-records"></a><span data-ttu-id="595f4-128">В Office 365 создаются и размещаются записи DNS.</span><span class="sxs-lookup"><span data-stu-id="595f4-128">Office 365 creates and hosts the DNS records</span></span> 
<span data-ttu-id="595f4-129">**Преимущества**</span><span class="sxs-lookup"><span data-stu-id="595f4-129">**Advantages**</span></span> 
- <span data-ttu-id="595f4-130">Вам не придется беспокоиться по поводу ошибок в значениях, указанных в записях DNS для служб Office 365.</span><span class="sxs-lookup"><span data-stu-id="595f4-130">You don't have to worry about making mistakes in the values you enter for the DNS records for Office 365 services.</span></span>  
- <span data-ttu-id="595f4-131">У вас есть более широкий выбор регистраторов доменных имен и узлов DNS.</span><span class="sxs-lookup"><span data-stu-id="595f4-131">You have more flexibility in your choice of domain registrar and DNS host.</span></span> 
- <span data-ttu-id="595f4-132">Вам подходит любой поставщик, который позволяет изменять записи сервера доменных имен, даже если он поддерживает не все необходимые типы записей.</span><span class="sxs-lookup"><span data-stu-id="595f4-132">Any provider that lets you change your nameserver records will work, even if the provider doesn't support all the required record types.</span></span>   
- <span data-ttu-id="595f4-133">Когда Office 365 добавляет новые записи DNS, вам не нужно выполнять обновление.</span><span class="sxs-lookup"><span data-stu-id="595f4-133">When Office 365 adds new DNS records, you don't have to make updates.</span></span>  

#### <a name="disadvantages"></a><span data-ttu-id="595f4-134">Недостатки</span><span class="sxs-lookup"><span data-stu-id="595f4-134">Disadvantages</span></span> 
- <span data-ttu-id="595f4-135">Вы не можете изменять записи DNS для размещения электронной почты за пределами Office 365.</span><span class="sxs-lookup"><span data-stu-id="595f4-135">You can't change your DNS records to host email outside of Office 365.</span></span> 
- <span data-ttu-id="595f4-136">Если у вас уже есть общедоступный веб-сайт с адресом в вашем домене, например www.fourthcoffee.com, вам понадобится перенаправить на него пользователей с Office 365.</span><span class="sxs-lookup"><span data-stu-id="595f4-136">If you already use a public website with your domain for its address, like www.fourthcoffee.com, you must redirect people to that address from Office 365.</span></span> 
- <span data-ttu-id="595f4-137">Для настройки перенаправления требуется статический IP-адрес, который не всегда легко получить для общедоступных веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="595f4-137">Setting up redirection requires a static IP address, which is not always easily available for public websites.</span></span> <span data-ttu-id="595f4-138">— Если текущий регистратор доменных имен не позволяет изменить записи серверов доменных имен, необходимо переключиться на другой регистратор, чтобы использовать эту функцию управления DNS.</span><span class="sxs-lookup"><span data-stu-id="595f4-138">- If your current domain registrar doesn't allow you to change your domain's nameserver records, you have to switch to a different registrar to use this DNS management option.</span></span>  

 ### <a name="you-manage-the-dns-records-yourself"></a><span data-ttu-id="595f4-139">Самостоятельное управление записями DNS</span><span class="sxs-lookup"><span data-stu-id="595f4-139">You manage the DNS records yourself</span></span> 
 #### <a name="advantages"></a><span data-ttu-id="595f4-140">Преимущества</span><span class="sxs-lookup"><span data-stu-id="595f4-140">Advantages</span></span>
- <span data-ttu-id="595f4-141">Вы управляете записями DNS для служб Office 365.</span><span class="sxs-lookup"><span data-stu-id="595f4-141">You control the DNS records for Office 365 services.</span></span>   
- <span data-ttu-id="595f4-142">Если у вас есть общедоступный веб-сайт с адресом в вашем домене, например www.fourthcoffee.com, вам не нужно беспокоиться о перенаправлении, чтобы обеспечить пользователям доступ на сайт после настройки домена в Office 365.</span><span class="sxs-lookup"><span data-stu-id="595f4-142">If you have a public website with your domain for its address, like www.fourthcoffee.com, you don't have to worry about using redirection to make sure people can still get to your website after you set up your domain in Office 365.</span></span>    
- <span data-ttu-id="595f4-143">Вы можете разместить электронную почту в любом другом месте, например на локальном сервере Exchange.</span><span class="sxs-lookup"><span data-stu-id="595f4-143">You have the flexibility to host email somewhere else, such as with an on-premises Exchange server.</span></span>  
 
#### <a name="disadvantages"></a><span data-ttu-id="595f4-144">Недостатки</span><span class="sxs-lookup"><span data-stu-id="595f4-144">Disadvantages</span></span>
<span data-ttu-id="595f4-145">Вам нужно самостоятельно настроить записи DNS для служб Office 365 (если у вас нет домена GoDaddy).</span><span class="sxs-lookup"><span data-stu-id="595f4-145">You have to set up the DNS records for Office 365 services yourself (unless you have a GoDaddy domain).</span></span> 
-  <span data-ttu-id="595f4-146">Если текущий узел DNS не поддерживает все необходимые типы записей для Microsoft 365, некоторые функции не будут доступны и может потребоваться переключиться на другой узел DNS.</span><span class="sxs-lookup"><span data-stu-id="595f4-146">If your current DNS host doesn't support all of the required record types for Microsoft 365, some features won't be available and you might need to switch to a different DNS host.</span></span> 
- <span data-ttu-id="595f4-147">При изменении требований к записям DNS или добавлении новых служб в Office 365 необходимо самостоятельно выполнять обновление в узле DNS.</span><span class="sxs-lookup"><span data-stu-id="595f4-147">When Office 365 changes requirements for DNS records, or adds new services, you have to make updates yourself at your DNS host.</span></span> 
   
## <a name="what-is-a-domain-name"></a><span data-ttu-id="595f4-148">Что такое доменное имя?</span><span class="sxs-lookup"><span data-stu-id="595f4-148">What is a domain name?</span></span>


<span data-ttu-id="595f4-149">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span><span class="sxs-lookup"><span data-stu-id="595f4-149">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span></span> <span data-ttu-id="595f4-150">in web addresses.</span><span class="sxs-lookup"><span data-stu-id="595f4-150">in web addresses.</span></span> <span data-ttu-id="595f4-151">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span><span class="sxs-lookup"><span data-stu-id="595f4-151">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="595f4-152">Использование пользовательского домена, например "**роб \@ contoso.com**", с помощью Office 365 поможет вам создавать сведения о доходе и распознавание для вашей торговой марки.</span><span class="sxs-lookup"><span data-stu-id="595f4-152">Using a custom domain like "**rob\@contoso.com**" with Office 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="595f4-153">Вы можете [купить домен в Office 365](../get-help-with-domains/buy-a-domain-name.md), и мы настроим его автоматически. Вы также можете приобрести домен у регистратора доменных имен или использовать уже имеющийся у вас домен.</span><span class="sxs-lookup"><span data-stu-id="595f4-153">You can [buy a domain in Office 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
  
## <a name="can-i-transfer-a-domain-i-purchased-from-microsoft-to-another-provider"></a><span data-ttu-id="595f4-154">Можно ли перенести домен, приобретенный у корпорации Майкрософт, другому поставщику?</span><span class="sxs-lookup"><span data-stu-id="595f4-154">Can I transfer a domain I purchased from Microsoft to another provider?</span></span>

<span data-ttu-id="595f4-155">Да, но вы не можете перенести домен Office 365 в другой регистратор до 60 дней после приобретения этого пакета Office 365.</span><span class="sxs-lookup"><span data-stu-id="595f4-155">Yes, but you can't transfer an Office 365 domain to another registrar until 60 days after you purchased it with Office 365.</span></span>

<span data-ttu-id="595f4-156">Обратите внимание, что запрос *Whois* будет показывать приобретенный регистратор домена Office 365 в качестве подстановочных доменов LLC.</span><span class="sxs-lookup"><span data-stu-id="595f4-156">Please note that a *Whois* query will show an Office 365 purchased domain registrar as Wild West Domains LLC.</span></span> <span data-ttu-id="595f4-157">Тем не менее, связаться с Office 365 можно только с помощью приобретенного домена Office 365.</span><span class="sxs-lookup"><span data-stu-id="595f4-157">However, only Office 365 should be contacted regarding your Office 365 purchased domain.</span></span>
  
<span data-ttu-id="595f4-158">С помощью приведенных ниже инструкций получите код в Office 365, а затем перейдите на веб-сайт другого регистратора доменных имен, чтобы выполнить перенос.</span><span class="sxs-lookup"><span data-stu-id="595f4-158">Follow the steps below to get the code at Office 365, and then go to the other domain registrar's website to set up transferring your domain name to that registrar.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="595f4-159">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="595f4-159">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="595f4-160">В Центре администрирования перейдите на страницу **Settings** (Параметры) > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="595f4-160">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="595f4-161">В центре администрирования откройте страницу "лицензии на **Параметры** " > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> .</span><span class="sxs-lookup"><span data-stu-id="595f4-161">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="595f4-162">На странице **Domains (домены** ) выберите домен Office 365, который вы хотите передать другому регистратору доменных имен, а затем выберите пункт **Передача домена**  >  **Разрешить передачу домена**.</span><span class="sxs-lookup"><span data-stu-id="595f4-162">On the **Domains** page, select the Office 365 domain that you want to transfer to another domain registrar, and then select **Domain Transfer** > **Enable domain transfer**.</span></span>
       
4. <span data-ttu-id="595f4-163">Выполните дальнейшие действия для подготовки домена к переносу.</span><span class="sxs-lookup"><span data-stu-id="595f4-163">Follow the steps to prepare for transferring your domain.</span></span>
    
5. <span data-ttu-id="595f4-164">После получения кода перейдите на веб-сайт регистратора, на котором в дальнейшем планируете управлять доменным именем, и следуйте приведенным там инструкциям по переносу домена (ознакомьтесь со справкой на этом сайте).</span><span class="sxs-lookup"><span data-stu-id="595f4-164">After you get the code, go to the website of the domain registrar where you want to manage your domain name going forward and follow their directions for transferring a domain (search for help on their website).</span></span>
    
6. <span data-ttu-id="595f4-165">Если вам нужно снова просмотреть код, на странице **Параметры домена** в Office 365 выберите **Просмотр кода авторизации для передачи в домене**.</span><span class="sxs-lookup"><span data-stu-id="595f4-165">If you need to see the code again, on the **Domain settings** page in Office 365, select **View authorization code for domain transfer**.</span></span>
    
7. <span data-ttu-id="595f4-166">После завершения переноса вы обновите свой домен в новом регистраторе доменных имен.</span><span class="sxs-lookup"><span data-stu-id="595f4-166">After the transfer is complete, you'll renew your domain at the new domain registrar.</span></span>
    
8. <span data-ttu-id="595f4-167">Чтобы завершить процесс, вернитесь на страницу " **домены** центра администрирования" и выберите пункт **полная передача домена**.</span><span class="sxs-lookup"><span data-stu-id="595f4-167">To finish the process, go back to the admin center **Domains** page and select **Complete Domain Transfer**.</span></span> 

<span data-ttu-id="595f4-168">*Примечание: Обратите внимание, что приобретенные домены Office 365 не подходят для изменения серверов имен или перемещения домена между клиентами Office 365.  Если это необходимо, необходимо перенести регистрацию домена в другой регистратор.*</span><span class="sxs-lookup"><span data-stu-id="595f4-168">*Note: Please note that Office 365 purchased domains are not eligible for Name Server changes or transferring the domain between Office 365 Tenants.  If either of these are required, the domain registration will need to be transferred to another registrar.*</span></span>
    
## <a name="how-do-i-change-how-my-dns-records-are-managed-in-office-365"></a><span data-ttu-id="595f4-169">Как настроить управление записями DNS в Office 365?</span><span class="sxs-lookup"><span data-stu-id="595f4-169">How do I change how my DNS records are managed in Office 365?</span></span>

### <a name="change-dns-management-to-a-dns-host-outside-office-365"></a><span data-ttu-id="595f4-170">Переключение управления DNS на узел DNS, не относящийся к Office 365</span><span class="sxs-lookup"><span data-stu-id="595f4-170">Change DNS management to a DNS host outside Office 365</span></span>
   
1. <span data-ttu-id="595f4-171">Войдите на сайт регистратора доменных имен для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="595f4-171">Sign in to the domain registrar for your domain.</span></span>
    
2. <span data-ttu-id="595f4-172">Find the area on the registrar's website where you update nameserver records, and update the nameservers to point to your domain's DNS host.</span><span class="sxs-lookup"><span data-stu-id="595f4-172">Find the area on the registrar's website where you update nameserver records, and update the nameservers to point to your domain's DNS host.</span></span> <span data-ttu-id="595f4-173">(The DNS host is often the domain registrar.)</span><span class="sxs-lookup"><span data-stu-id="595f4-173">(The DNS host is often the domain registrar.)</span></span>
    
3. <span data-ttu-id="595f4-174">Щелкните ссылку, чтобы перейти к мастеру настройки доменов:</span><span class="sxs-lookup"><span data-stu-id="595f4-174">Follow a link to go to the domains setup wizard:</span></span>

::: moniker range="o365-worldwide"

4. <span data-ttu-id="595f4-175">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="595f4-175">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

4. <span data-ttu-id="595f4-176">В Центре администрирования перейдите на страницу **Settings** (Параметры) > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="595f4-176">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

4. <span data-ttu-id="595f4-177">В Центре администрирования перейдите на страницу **Settings** (Параметры) > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="595f4-177">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
5. <span data-ttu-id="595f4-178">На странице **домены** выберите домен, который вы переключаете, и выберите **Управление DNS**.</span><span class="sxs-lookup"><span data-stu-id="595f4-178">On the **Domains** page, select the domain you're switching, and select **DNS management**.</span></span>
    
6. <span data-ttu-id="595f4-179">В мастере установки доменов на странице **Настройка веб-служб** установите флажок **я буду управлять собственными записями DNS**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="595f4-179">In the domains setup wizard, on the **Set up your online services** page, select **I'll manage my own DNS records**, and then select **Next**.</span></span>
    
7. <span data-ttu-id="595f4-180">Добавьте записи DNS, предложенные мастером, на странице " **Обновление параметров DNS** " на веб-сайт регистратора.</span><span class="sxs-lookup"><span data-stu-id="595f4-180">Add the DNS records suggested by the wizard on the **Update DNS settings** page to your registrar's website.</span></span> 
    
8. <span data-ttu-id="595f4-181">После добавления записей вернитесь в Office 365 и нажмите кнопку **проверить**.</span><span class="sxs-lookup"><span data-stu-id="595f4-181">After you've added the records, come back to Office 365 and select **Verify**.</span></span>
    

### <a name="change-dns-management-to-office-365"></a><span data-ttu-id="595f4-182">Переключение управления DNS на Office 365</span><span class="sxs-lookup"><span data-stu-id="595f4-182">Change DNS management to Office 365</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="595f4-183">В центре администрирования перейдите на страницу " **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> параметров"..</span><span class="sxs-lookup"><span data-stu-id="595f4-183">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page..</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="595f4-184">В Центре администрирования перейдите на страницу **Settings** (Параметры) > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="595f4-184">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="595f4-185">В Центре администрирования перейдите на страницу **Settings** (Параметры) > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="595f4-185">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="595f4-186">На странице **домены** выберите домен, который вы переключаете, и выберите **Управление DNS**.</span><span class="sxs-lookup"><span data-stu-id="595f4-186">On the **Domains** page, select the domain you're switching, and select **DNS Management**.</span></span>
    
3. <span data-ttu-id="595f4-187">В мастере установки доменов на странице **Настройка веб-служб** выберите **настроить мои Интернет-службы. (Рекомендуется)**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="595f4-187">In the domains setup wizard, on the **Set up your online services** page, select **Set up my online services for me. (Recommended)**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="595f4-188">Если вы еще не проверили домен, выполните сначала проверку.</span><span class="sxs-lookup"><span data-stu-id="595f4-188">If you haven't verified the domain yet, follow the steps to do that first.</span></span>
    
5. <span data-ttu-id="595f4-189">On the **Update DNS settings** page, we list the nameservers for Office 365.</span><span class="sxs-lookup"><span data-stu-id="595f4-189">On the **Update DNS settings** page, we list the nameservers for Office 365.</span></span> <span data-ttu-id="595f4-190">Go to the domain registrar for your domain, and update the nameservers to the Office 365 nameservers.</span><span class="sxs-lookup"><span data-stu-id="595f4-190">Go to the domain registrar for your domain, and update the nameservers to the Office 365 nameservers.</span></span> 
    
4. <span data-ttu-id="595f4-191">После изменения серверов доменных имен **подождите как минимум час**.</span><span class="sxs-lookup"><span data-stu-id="595f4-191">After you've updated the nameservers, **wait at least an hour**.</span></span> <span data-ttu-id="595f4-192">Затем вернитесь к мастеру в Office 365 и нажмите кнопку **проверить**.</span><span class="sxs-lookup"><span data-stu-id="595f4-192">Then, back in the wizard in Office 365, select **Verify**.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="595f4-193">Что произойдет, если поставщик DNS не поддерживает некоторые типы записей?</span><span class="sxs-lookup"><span data-stu-id="595f4-193">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="595f4-194">If you manage your own DNS records and your DNS host does not support all the DNS records that Office 365 needs, some Office 365 features won't work.</span><span class="sxs-lookup"><span data-stu-id="595f4-194">If you manage your own DNS records and your DNS host does not support all the DNS records that Office 365 needs, some Office 365 features won't work.</span></span> <span data-ttu-id="595f4-195">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span><span class="sxs-lookup"><span data-stu-id="595f4-195">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="595f4-196">Поставщики, поддерживающие все необходимые записи DNS:</span><span class="sxs-lookup"><span data-stu-id="595f4-196">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="595f4-197">Dynadot</span><span class="sxs-lookup"><span data-stu-id="595f4-197">Dynadot</span></span>
    
- <span data-ttu-id="595f4-198">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="595f4-198">eNomCentral</span></span>
    
- <span data-ttu-id="595f4-199">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="595f4-199">Europe Registry</span></span>
    
- <span data-ttu-id="595f4-200">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="595f4-200">GoDaddy</span></span>
    
- <span data-ttu-id="595f4-201">Hover</span><span class="sxs-lookup"><span data-stu-id="595f4-201">Hover</span></span>
    
- <span data-ttu-id="595f4-202">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="595f4-202">MyHosting.com</span></span>
    
- <span data-ttu-id="595f4-203">Name.com</span><span class="sxs-lookup"><span data-stu-id="595f4-203">Name.com</span></span>
    
- <span data-ttu-id="595f4-204">Nearly Free Speech</span><span class="sxs-lookup"><span data-stu-id="595f4-204">Nearly Free Speech</span></span>
    
- <span data-ttu-id="595f4-205">Nettica</span><span class="sxs-lookup"><span data-stu-id="595f4-205">Nettica</span></span>
    
- <span data-ttu-id="595f4-206">Network Information Center (NIC)</span><span class="sxs-lookup"><span data-stu-id="595f4-206">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="595f4-207">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="595f4-207">Network Solutions</span></span>
    
- <span data-ttu-id="595f4-208">Register.com</span><span class="sxs-lookup"><span data-stu-id="595f4-208">Register.com</span></span>
    
 <span data-ttu-id="595f4-209">**Если не поддерживаются записи SRV**, недоступны следующие функции Office 365:</span><span class="sxs-lookup"><span data-stu-id="595f4-209">**If SRV records are not supported**, the following Office 365 features are not available:</span></span> 
  
- <span data-ttu-id="595f4-210">Skype для бизнеса Online: обмен мгновенными сообщениями и сведениями о присутствии с пользователями Outlook Web App;</span><span class="sxs-lookup"><span data-stu-id="595f4-210">Skype for Business Online IM and presence integration with Outlook Web App</span></span>
    
- <span data-ttu-id="595f4-211">внешняя связь (федерация) с пользователями Skype для бизнеса Online в других организациях;</span><span class="sxs-lookup"><span data-stu-id="595f4-211">External communication (federation) with Skype for Business Online users in other organizations.</span></span>
    
- <span data-ttu-id="595f4-212">подключение к общедоступному Интернету для пользователей Skype для бизнеса Online, которые вошли в систему с помощью учетной записи Майкрософт (Windows Live ID).</span><span class="sxs-lookup"><span data-stu-id="595f4-212">Public Internet Connectivity (PIC) with Skype for Business Online users signed in with a Microsoft account (formerly known as a Windows Live ID).</span></span>
    
 <span data-ttu-id="595f4-213">**Если несколько записей CNAME не поддерживаются,** для Skype для бизнеса Online необходимо выбрать одну из следующих возможностей:</span><span class="sxs-lookup"><span data-stu-id="595f4-213">**If multiple CNAME records are not supported,** you have to choose between the following features for Skype for Business Online:</span></span> 
  
- <span data-ttu-id="595f4-214">классические и мобильные почтовые клиенты могут использовать функцию автообнаружения для автоматического поиска службы Exchange Online, чтобы пользователи могли входить в нее без ввода имени сервера;</span><span class="sxs-lookup"><span data-stu-id="595f4-214">Email desktop clients and mobile clients can use Autodiscover to automatically find the Exchange Online service so that users can sign in without having to enter a server name.</span></span>
    
- <span data-ttu-id="595f4-215">классические почтовые клиенты Skype для бизнеса Online могут использовать функцию автообнаружения для автоматического поиска службы Skype для бизнеса Online, чтобы пользователи могли входить в нее без ввода имени сервера;</span><span class="sxs-lookup"><span data-stu-id="595f4-215">Skype for Business Online desktop clients can use Autodiscover to automatically find the Skype for Business Online service so that users can sign in without having to enter a server name.</span></span>
    
- <span data-ttu-id="595f4-216">мобильные почтовые клиенты Skype для бизнеса Online могут использовать функцию автообнаружения для автоматического поиска службы Skype для бизнеса Online, чтобы пользователи могли входить в нее без ввода имени сервера.</span><span class="sxs-lookup"><span data-stu-id="595f4-216">Skype for Business Online mobile clients can use Autodiscover to automatically find the Skype for Business Online service so that users can sign in without having to enter a server name.</span></span>

- <span data-ttu-id="595f4-217">Федерация Microsoft Teams со Skype для бизнеса в локальной среде или в сети.</span><span class="sxs-lookup"><span data-stu-id="595f4-217">Microsoft Teams federation with Skype for Business, either on-premises or online.</span></span> <span data-ttu-id="595f4-218">Для получения дополнительных сведений ознакомьтесь [с разделом Подготовка сети Организации к работе с Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network).</span><span class="sxs-lookup"><span data-stu-id="595f4-218">For more information, see [Prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network).</span></span>
    
 <span data-ttu-id="595f4-219">**If SPF/TXT records are not supported**, other people may be able to use your domain to send spam or other malicious email.</span><span class="sxs-lookup"><span data-stu-id="595f4-219">**If SPF/TXT records are not supported**, other people may be able to use your domain to send spam or other malicious email.</span></span> <span data-ttu-id="595f4-220">SPF records work by identifying the servers that are authorized to send email from your domain.</span><span class="sxs-lookup"><span data-stu-id="595f4-220">SPF records work by identifying the servers that are authorized to send email from your domain.</span></span> 
  
## <a name="how-do-i-set-or-change-the-default-domain-in-office-365"></a><span data-ttu-id="595f4-221">Как задать или изменить домен по умолчанию в Office 365?</span><span class="sxs-lookup"><span data-stu-id="595f4-221">How do I set or change the default domain in Office 365?</span></span>

<span data-ttu-id="595f4-222">Чтобы можно было выбрать домен, используемый по умолчанию, необходимо добавить в Office 365 хотя бы один личный домен.</span><span class="sxs-lookup"><span data-stu-id="595f4-222">You must have at least one custom domain that you've added to Office 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="595f4-223">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="595f4-223">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="595f4-224">В Центре администрирования перейдите на страницу **Settings** (Параметры) > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="595f4-224">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="595f4-225">В Центре администрирования перейдите на страницу **Settings** (Параметры) > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="595f4-225">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="595f4-226">На странице **Domains (домены** ) выберите домен, который требуется установить в качестве значения по умолчанию для новых адресов электронной почты.</span><span class="sxs-lookup"><span data-stu-id="595f4-226">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="595f4-227">Нажмите кнопку **По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="595f4-227">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="595f4-228">Изменить имя первоначального домена  *.onmicrosoft.com*  невозможно.</span><span class="sxs-lookup"><span data-stu-id="595f4-228">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="595f4-229">Имя начального домена *onmicrosoft.de* нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="595f4-229">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="595f4-230">Имя начального домена *Partner.onmschina.CN* нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="595f4-230">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-office-365"></a><span data-ttu-id="595f4-231">Могу ли я добавлять пользовательские поддомены или несколько доменов к Office 365?</span><span class="sxs-lookup"><span data-stu-id="595f4-231">Can I add custom subdomains or multiple domains to Office 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="595f4-232">Нет!</span><span class="sxs-lookup"><span data-stu-id="595f4-232">Yes!</span></span> <span data-ttu-id="595f4-233">Чтобы добавить поддомены, необходимо управлять собственными параметрами DNS на веб-сайте регистратора.</span><span class="sxs-lookup"><span data-stu-id="595f4-233">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="595f4-234">Если вы разработаны Майкрософт для управления параметрами DNS с записями NS или если вы приобрели домен от корпорации Майкрософт, вы не сможете добавить поддомены.</span><span class="sxs-lookup"><span data-stu-id="595f4-234">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="595f4-235">Нет!</span><span class="sxs-lookup"><span data-stu-id="595f4-235">Yes!</span></span> <span data-ttu-id="595f4-236">Чтобы добавить поддомены, необходимо управлять собственными параметрами DNS на веб-сайте регистратора.</span><span class="sxs-lookup"><span data-stu-id="595f4-236">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="595f4-237">Если вы разработаны Майкрософт для управления параметрами DNS с записями NS или если вы приобрели домен от корпорации Майкрософт, вы не сможете добавить поддомены.</span><span class="sxs-lookup"><span data-stu-id="595f4-237">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="595f4-238">Нет!</span><span class="sxs-lookup"><span data-stu-id="595f4-238">Yes!</span></span> <span data-ttu-id="595f4-239">Чтобы добавить поддомены, необходимо управлять собственными параметрами DNS на веб-сайте регистратора.</span><span class="sxs-lookup"><span data-stu-id="595f4-239">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="595f4-240">Если вы разпозволяете 21Vianet управлять параметрами DNS с записями NS, вы не можете добавлять поддомены.</span><span class="sxs-lookup"><span data-stu-id="595f4-240">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="595f4-241">Обычно можно добавить до 900 доменов в подписку на Office 365.</span><span class="sxs-lookup"><span data-stu-id="595f4-241">Typically, you can add up to 900 domains to your Office 365 subscription.</span></span>
  
<span data-ttu-id="595f4-242">Например, вы можете добавить домены contoso.com и contosomarketing.com, а затем  поддомены www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com и т. д.</span><span class="sxs-lookup"><span data-stu-id="595f4-242">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="595f4-243">При добавлении дочернего домена он автоматически проверяется в соответствии с проверяемым родительским доменом.</span><span class="sxs-lookup"><span data-stu-id="595f4-243">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="595f4-244">When you add multiple domains to Office 365, you can host any of the services (like email) on any of the domains you've added.</span><span class="sxs-lookup"><span data-stu-id="595f4-244">When you add multiple domains to Office 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="595f4-245">*When you change your email to Office 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Office 365.*</span><span class="sxs-lookup"><span data-stu-id="595f4-245">*When you change your email to Office 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Office 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="595f4-246">Если вы уже добавили домен contoso.com в клиент Office 365, вы также можете добавить xyz.contoso.com дочернего домена в другой клиент Office 365.</span><span class="sxs-lookup"><span data-stu-id="595f4-246">If you have already added a contoso.com domain to an Office 365 tenant, you can also add the subdomain xyz.contoso.com to another Office 365 tenant.</span></span> <span data-ttu-id="595f4-247">При добавлении поддомена вам будет предложено добавить запись TXT в поставщик услуг хостинга DNS.</span><span class="sxs-lookup"><span data-stu-id="595f4-247">When adding the subdomain, you will be prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="595f4-248">Почему у меня есть домен onmicrosoft.com?</span><span class="sxs-lookup"><span data-stu-id="595f4-248">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="595f4-249">Office 365 создает домен для вас, например *contoso.onmicrosoft.com*, при регистрации в службе.</span><span class="sxs-lookup"><span data-stu-id="595f4-249">Office 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="595f4-250">Идентификатор пользователя, который вы создаете при регистрации, включает домен, например *Alan@contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="595f4-250">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="595f4-251">**Если вы хотите, чтобы ваша электронная почта выглядела как *Сергей \@ contoso.com*:** [купите домен](../get-help-with-domains/buy-a-domain-name.md) или просто выполните действия, описанные в статье [Добавление пользователей и доменов в Office 365](add-domain.md) , если у вас уже есть.</span><span class="sxs-lookup"><span data-stu-id="595f4-251">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Office 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="595f4-252">**You can't rename the onmicrosoft domain after sign-up.**</span><span class="sxs-lookup"><span data-stu-id="595f4-252">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="595f4-253">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="595f4-253">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="595f4-254">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Office 365.</span><span class="sxs-lookup"><span data-stu-id="595f4-254">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Office 365.</span></span> 
    
- <span data-ttu-id="595f4-255">**Вы не можете переименовать URL-адрес сайта группы.**</span><span class="sxs-lookup"><span data-stu-id="595f4-255">**You can't rename your team site URL.**</span></span> <span data-ttu-id="595f4-256">URL-адрес сайта группы основан на вашем доменном имени onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="595f4-256">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="595f4-257">К сожалению, из-за способа работы архитектуры SharePoint Online нельзя переименовать сайт группы.</span><span class="sxs-lookup"><span data-stu-id="595f4-257">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="595f4-258">**You can't remove your onmicrosoft domain.**</span><span class="sxs-lookup"><span data-stu-id="595f4-258">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="595f4-259">Office 365 needs to keep it around because it's used behind the scenes for your subscription.</span><span class="sxs-lookup"><span data-stu-id="595f4-259">Office 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="595f4-260">But you don't have to use the domain yourself after you've added a custom domain.</span><span class="sxs-lookup"><span data-stu-id="595f4-260">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="595f4-261">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span><span class="sxs-lookup"><span data-stu-id="595f4-261">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span></span> <span data-ttu-id="595f4-262">It still works for email and other services, so it's your choice.</span><span class="sxs-lookup"><span data-stu-id="595f4-262">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="595f4-263">Почему у меня есть домен "onmicrosoft.de"?</span><span class="sxs-lookup"><span data-stu-id="595f4-263">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="595f4-264">Office 365 создает домен для вас, например *contoso.onmicrosoft.de*, при регистрации в службе.</span><span class="sxs-lookup"><span data-stu-id="595f4-264">Office 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="595f4-265">Идентификатор пользователя, который вы создаете при регистрации, включает домен, например *Alan@contoso.onmicrosoft.de*.</span><span class="sxs-lookup"><span data-stu-id="595f4-265">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="595f4-266">**Если вы хотите, чтобы ваша электронная почта выглядела как *Alan@contoso.de*:** [купите домен](../get-help-with-domains/buy-a-domain-name.md) или просто выполните действия, описанные в статье [Добавление пользователей и доменов в Office 365](add-domain.md) , если у вас уже есть.</span><span class="sxs-lookup"><span data-stu-id="595f4-266">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Office 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="595f4-267">**Домен onmicrosoft невозможно переименовать после регистрации.**</span><span class="sxs-lookup"><span data-stu-id="595f4-267">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="595f4-268">Например, если исходный домен, который вы выбрали, был fourthcoffee.onmicrosoft.de, его нельзя изменить на fabrikam.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="595f4-268">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="595f4-269">Чтобы использовать другой домен onmicrosoft.de, вам потребуется начать новую подписку с помощью Office 365.</span><span class="sxs-lookup"><span data-stu-id="595f4-269">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Office 365.</span></span> 
    
- <span data-ttu-id="595f4-270">**Вы не можете переименовать URL-адрес сайта группы.**</span><span class="sxs-lookup"><span data-stu-id="595f4-270">**You can't rename your team site URL.**</span></span> <span data-ttu-id="595f4-271">URL-адрес сайта группы основан на вашем доменном имени onmicrosoft.de. К сожалению, из-за способа работы архитектуры SharePoint Online нельзя переименовать сайт группы.</span><span class="sxs-lookup"><span data-stu-id="595f4-271">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="595f4-272">**You can't remove your onmicrosoft domain.**</span><span class="sxs-lookup"><span data-stu-id="595f4-272">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="595f4-273">Office 365 needs to keep it around because it's used behind the scenes for your subscription.</span><span class="sxs-lookup"><span data-stu-id="595f4-273">Office 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="595f4-274">But you don't have to use the domain yourself after you've added a custom domain.</span><span class="sxs-lookup"><span data-stu-id="595f4-274">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="595f4-275">Вы можете продолжить работу с исходным доменом onmicrosoft.de, даже после добавления домена.</span><span class="sxs-lookup"><span data-stu-id="595f4-275">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="595f4-276">Он будет поддерживаться в электронной почте и других службах.</span><span class="sxs-lookup"><span data-stu-id="595f4-276">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="595f4-277">Как проверить статус некоммерческой или образования?</span><span class="sxs-lookup"><span data-stu-id="595f4-277">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="595f4-278">В [центре администрирования](https://docs.microsoft.com/microsoft-365/admin/admin-home) выберите пункт **Настройка** , чтобы запустить мастер.</span><span class="sxs-lookup"><span data-stu-id="595f4-278">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="595f4-279">(Сначала обязательно войдите в Office 365.)</span><span class="sxs-lookup"><span data-stu-id="595f4-279">(Be sure to sign in to Office 365 first.)</span></span> 
    
2. <span data-ttu-id="595f4-280">Чтобы стать администратором учебного заведения, выберите параметр **становится** администратором в Office 365.</span><span class="sxs-lookup"><span data-stu-id="595f4-280">To become the admin for your school, select the **Become an admin** option in Office 365.</span></span> 
    
3. <span data-ttu-id="595f4-281">Вам будет предложено добавить запись DNS в формате TXT на веб-сайт узла DNS для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="595f4-281">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="595f4-282">Почему?</span><span class="sxs-lookup"><span data-stu-id="595f4-282">Why?</span></span> <span data-ttu-id="595f4-283">Так как при входе на узел DNS и добавлении записи в домен вы подтверждаете Office 365, что вы владеете доменным именем.</span><span class="sxs-lookup"><span data-stu-id="595f4-283">Because by signing in at the DNS host and adding a record for your domain, you prove to Office 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="595f4-284">После добавления записи вернитесь к порталу Office 365 и подтвердите, что вы добавили его, поэтому Office 365 может проверить.</span><span class="sxs-lookup"><span data-stu-id="595f4-284">After you add the record, you'll go back to the Office 365 portal and confirm that you've added it, so Office 365 can check.</span></span>
    
<span data-ttu-id="595f4-285">У вас есть некоммерческие и хотите получить Office 365?</span><span class="sxs-lookup"><span data-stu-id="595f4-285">Have a nonprofit and want to get Office 365?</span></span> <span data-ttu-id="595f4-286">[Убедитесь, что ваша организация](https://www.microsoft.com/en-us/nonprofits/eligibility) поддается уточнению и зарегистрируйте ее.</span><span class="sxs-lookup"><span data-stu-id="595f4-286">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="595f4-287">Хотите узнать больше о том, как стать администратором учебного заведения?</span><span class="sxs-lookup"><span data-stu-id="595f4-287">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="595f4-288">[Узнайте больше об этом](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span><span class="sxs-lookup"><span data-stu-id="595f4-288">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>
  
## <a name="can-i-pilot-office-365-with-just-a-few-email-addresses-from-my-custom-domain"></a><span data-ttu-id="595f4-289">Можно ли настроить Office 365 с использованием всего нескольких адресов электронной почты из личного домена?</span><span class="sxs-lookup"><span data-stu-id="595f4-289">Can I pilot Office 365 with just a few email addresses from my custom domain?</span></span>

<span data-ttu-id="595f4-290">Вы можете, но есть ограничения:</span><span class="sxs-lookup"><span data-stu-id="595f4-290">You can, but there are limitations:</span></span>
  
- <span data-ttu-id="595f4-291">Ваш текущий поставщик электронной почты должен обеспечивать переадресацию электронной почты.</span><span class="sxs-lookup"><span data-stu-id="595f4-291">Your current email provider must provide email forwarding.</span></span>
    
- <span data-ttu-id="595f4-292">Необходимо управлять записями DNS, связанными с Office 365, в поставщике услуг размещения DNS, а не в Office 365 управлять этими записями.</span><span class="sxs-lookup"><span data-stu-id="595f4-292">You need to manage your Office 365-related DNS records at your DNS hosting provider, rather than having Office 365 manage these records for you.</span></span> <span data-ttu-id="595f4-293">Чтобы узнать, что это такое, ознакомьтесь со статьей Добавление домена в Office 365, когда вы хотите управлять собственными записями DNS.</span><span class="sxs-lookup"><span data-stu-id="595f4-293">To learn what this entails, see Add your domain to Office 365 when you want to manage your own DNS records.</span></span>
    
- <span data-ttu-id="595f4-294">Некоторые функции Office 365 не будут доступны:</span><span class="sxs-lookup"><span data-stu-id="595f4-294">Some Office 365 features won't be available:</span></span>
- <span data-ttu-id="595f4-295">Пользователи не смогут видеть сведения о доступности для пользователей, находящихся на другом поставщике электронной почты.</span><span class="sxs-lookup"><span data-stu-id="595f4-295">Users won't be able to see free/busy information for the users who are on the other email provider.</span></span>
- <span data-ttu-id="595f4-296">Администраторы не смогут администрировать учетные записи всех пользователей из одного места.</span><span class="sxs-lookup"><span data-stu-id="595f4-296">Admins won't be able to administer everyone's accounts from one place.</span></span>
- <span data-ttu-id="595f4-297">Пользователи могут не иметь возможность использовать фильтрацию нежелательной почты Office 365</span><span class="sxs-lookup"><span data-stu-id="595f4-297">Users may not be able to use Office 365 spam filtering</span></span>

### <a name="how-to-set-up-an-office-365-pilot"></a><span data-ttu-id="595f4-298">Настройка пилотного проекта Office 365</span><span class="sxs-lookup"><span data-stu-id="595f4-298">How to set up an Office 365 pilot</span></span>
    
1. <span data-ttu-id="595f4-299">Вход в центр администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="595f4-299">Sign in to the Microsoft 365 admin center</span></span>
    
    1. <span data-ttu-id="595f4-300">Войдите в Office 365 с рабочей или учебной учетной записью.</span><span class="sxs-lookup"><span data-stu-id="595f4-300">Sign in to Office 365 with your work or school account.</span></span>
        
    2. <span data-ttu-id="595f4-301">Перейдите в **Settings** раздел \> **домены**параметров.</span><span class="sxs-lookup"><span data-stu-id="595f4-301">Go to **Settings** \> **Domains**.</span></span> 
    
2. <span data-ttu-id="595f4-302">Убедитесь, что вы владеете доменом, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="595f4-302">Verify that you own the domain you want to use</span></span>
    
    1. <span data-ttu-id="595f4-303">На странице **домены** выберите **Добавить домен**.</span><span class="sxs-lookup"><span data-stu-id="595f4-303">On the **Domains** page, select **Add domain**.</span></span> 
        
    2. <span data-ttu-id="595f4-304">В этой панели введите домен, в данном примере cohowinery.com, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="595f4-304">In the panel, type the domain, in this example cohowinery.com, and then select **Next**.</span></span> 
        
    3. <span data-ttu-id="595f4-305">На странице **Проверка** домена выполните пошаговые инструкции.</span><span class="sxs-lookup"><span data-stu-id="595f4-305">On the **Verify** domain page, follow the step-by-step instructions.</span></span> 
        
    4. <span data-ttu-id="595f4-306">В раскрывающемся списке выберите поставщика услуг размещения DNS и следуйте инструкциям, чтобы показать, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="595f4-306">In the drop-down list, select your DNS hosting provider, and follow the instructions to show that you own the domain.</span></span>
        
    5. <span data-ttu-id="595f4-307">Нажмите кнопку **проверить**.</span><span class="sxs-lookup"><span data-stu-id="595f4-307">Select **Verify**.</span></span> <span data-ttu-id="595f4-308">Для вступления изменений в силу DNS потребуется от нескольких минут до 72 часов.</span><span class="sxs-lookup"><span data-stu-id="595f4-308">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span> 
        
    6. <span data-ttu-id="595f4-309">После успешной проверки вам будет предложено изменить записи DNS.</span><span class="sxs-lookup"><span data-stu-id="595f4-309">When verification is successful, you'll be asked to modify your DNS records.</span></span>
    
3. <span data-ttu-id="595f4-310">Пометка домена как общего в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="595f4-310">Mark the domain as shared in Exchange Online</span></span>
    
    1. <span data-ttu-id="595f4-311">Перейдите в **центр администрирования Exchange** .</span><span class="sxs-lookup"><span data-stu-id="595f4-311">Go to the **Exchange admin center** (EAC).</span></span> 
        
    2. <span data-ttu-id="595f4-312">В разделе **процесс обработки почты** выберите **обслуживаемые домены**.</span><span class="sxs-lookup"><span data-stu-id="595f4-312">In the **Mail flow** section, select **Accepted domains**.</span></span> 
        
    3. <span data-ttu-id="595f4-313">Дважды щелкните домен, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="595f4-313">Double-click the domain you want to modify.</span></span>
        
    4. <span data-ttu-id="595f4-314">В открывшемся окне выберите **Внутренняя ретрансляция**.</span><span class="sxs-lookup"><span data-stu-id="595f4-314">In the window that opens, select **Internal Relay**.</span></span> 
        
    5. <span data-ttu-id="595f4-315">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="595f4-315">Select **Save**.</span></span> <span data-ttu-id="595f4-316">Для вступления в силу этого параметра может потребоваться несколько минут.</span><span class="sxs-lookup"><span data-stu-id="595f4-316">This setting may require a few minutes to take effect.</span></span> 
    
4. <span data-ttu-id="595f4-317">При необходимости можно разблокировать существующий сервер электронной почты</span><span class="sxs-lookup"><span data-stu-id="595f4-317">Optionally, unblock the existing email server</span></span>
    
    1. <span data-ttu-id="595f4-318">В Office 365 для защиты от нежелательной почты используется Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="595f4-318">Office 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="595f4-319">Если EOP обнаруживает большой объем нежелательных сообщений, перенаправляемых текущим почтовым сервером, он может заблокировать его, что помешает пересылке.</span><span class="sxs-lookup"><span data-stu-id="595f4-319">If EOP detects a high volume of spam being forwarded by your current mail server, it may block it, which would prevent forwarding from working.</span></span> <span data-ttu-id="595f4-320">Если вы уверены в защите от нежелательной почты, используемой другим поставщиком электронной почты, вы можете добавить свой сервер в белый список в Office 365.</span><span class="sxs-lookup"><span data-stu-id="595f4-320">If you are confident with the spam protection your other email provider uses, you can add their server to an allow list in Office 365.</span></span> <span data-ttu-id="595f4-321">Тем не менее, это также позволит всем нежелательным сообщениям, поступающим через исходный сервер, поступать в почтовые ящики Office 365, и вы не сможете оценить, насколько хорошо Office 365 предотвращает нежелательную почту.</span><span class="sxs-lookup"><span data-stu-id="595f4-321">However, this will also allow any spam that arrives through your original server to come through to the Office 365 mailboxes, and you won't be able to evaluate how well Office 365 prevents spam.</span></span>
    
    2. <span data-ttu-id="595f4-322">Перейдите в центр администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="595f4-322">Go to Exchange admin center (EAC).</span></span>
        
    3. <span data-ttu-id="595f4-323">В центре администрирования Exchange выберите элемент **Защита**, а затем выберите элемент **Фильтр подключения**.</span><span class="sxs-lookup"><span data-stu-id="595f4-323">In EAC, select **Protection**, and then select **Connection filter**.</span></span> 
        
    4. <span data-ttu-id="595f4-324">В **списке разрешенных IP-адресов**выберите **+** и добавьте IP-адрес почтового сервера, который можно получить от текущего поставщика услуг электронной почты.</span><span class="sxs-lookup"><span data-stu-id="595f4-324">In the **IP Allow list**, select **+**, and add the mail server IP address that you can get from your current email provider.</span></span> 
    
5. <span data-ttu-id="595f4-325">Создание учетных записей пользователей и Настройка основного (ответного) адреса</span><span class="sxs-lookup"><span data-stu-id="595f4-325">Create user accounts and set the primary (reply-to) address</span></span>
    
    1. <span data-ttu-id="595f4-326">Перейдите в Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="595f4-326">Go to the Microsoft 365 admin center.</span></span>
        
    2. <span data-ttu-id="595f4-327">На левой панели навигации выберите пункт **Пользователи** \> **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="595f4-327">On the left navigation bar, select **Users** \> **Active Users**.</span></span> 
        
    3. <span data-ttu-id="595f4-328">Создайте учетные записи пользователей.</span><span class="sxs-lookup"><span data-stu-id="595f4-328">Create the user accounts.</span></span>
        
    4. <span data-ttu-id="595f4-329">Для каждой учетной записи выберите **+ (создать)** и введите необходимые сведения.</span><span class="sxs-lookup"><span data-stu-id="595f4-329">For each account select **+ (New)**, and fill out the required information.</span></span> 
        
    5. <span data-ttu-id="595f4-330">Чтобы сохранить адрес электронной почты пользователя так же, как в настоящее время, поле **имени пользователя** должно совпадать с существующим адресом электронной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="595f4-330">To keep user's email the same as it is currently, the **User name** field should be exactly the same as the user's existing email address.</span></span> 
        
    6. <span data-ttu-id="595f4-331">Рядом с полем Имя пользователя выберите имя личного домена из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="595f4-331">Next to User name, select your custom domain name from the drop-down list.</span></span>
        
    7. <span data-ttu-id="595f4-332">Нажмите кнопку " **создать** \> **Закрыть**".</span><span class="sxs-lookup"><span data-stu-id="595f4-332">Select **Create** \> **Close**.</span></span> 
        
6. <span data-ttu-id="595f4-333">Обновление записей DNS в поставщике услуг хранения DNS</span><span class="sxs-lookup"><span data-stu-id="595f4-333">Update DNS records at your DNS hosting provider</span></span>
    
    1. <span data-ttu-id="595f4-334">Войдите на веб-сайт поставщика услуг хостинга DNS и следуйте инструкциям по [созданию DNS-записей на любом поставщике услуг хостинга DNS для Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="595f4-334">Sign in to your DNS hosting provider's website, and follow the [Create DNS records at any DNS hosting provider for Office 365 steps](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> <span data-ttu-id="595f4-335">**Сделайте следующие исключения:**</span><span class="sxs-lookup"><span data-stu-id="595f4-335">**Make the following exceptions:**</span></span>
    
        1. <span data-ttu-id="595f4-336">Не создавайте новую запись MX или не меняйте существующую запись MX.</span><span class="sxs-lookup"><span data-stu-id="595f4-336">Do not create a new MX record or change your existing MX record.</span></span>
            
        2. <span data-ttu-id="595f4-337">Если у вас уже есть запись инфраструктуры политики отправителей (SPF) для прежнего поставщика услуг электронной почты, вместо создания новой записи SPF (TXT) для Exchange Online просто добавьте к текущей записи TXT "include:SPF. Protection. Outlook. com".</span><span class="sxs-lookup"><span data-stu-id="595f4-337">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, just add "include:spf.protection.outlook.com" to the current TXT record.</span></span> <span data-ttu-id="595f4-338">Например, "v = spf1 MX включает:адатум. com include:SPF. Protection. Outlook. com ~ ALL".</span><span class="sxs-lookup"><span data-stu-id="595f4-338">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>
            
        3. <span data-ttu-id="595f4-339">Если у вас еще нет записи SPF, измените ее в Office 365, чтобы она включала домен для текущего поставщика услуг электронной почты, а также spf.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="595f4-339">If you don't have an SPF record yet, modify the one recommended by Office 365 to include the domain for your current email provider, plus spf.protection.outlook.com.</span></span> <span data-ttu-id="595f4-340">Это разрешает исходящие сообщения из обеих систем электронной почты.</span><span class="sxs-lookup"><span data-stu-id="595f4-340">This authorizes outgoing messages from both email systems.</span></span>
            
7. <span data-ttu-id="595f4-341">Настройка переадресации электронной почты у текущего поставщика</span><span class="sxs-lookup"><span data-stu-id="595f4-341">Set up email forwarding at your current provider</span></span>
    
    1. <span data-ttu-id="595f4-342">В текущем поставщике электронной почты Настройте переадресацию для учетных записей электронной почты пользователей в домен onmicrosoft.com:</span><span class="sxs-lookup"><span data-stu-id="595f4-342">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>
        
    2. <span data-ttu-id="595f4-343">Почтовый ящик пользователя а должен пересылаться по адресу usera@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="595f4-343">User A's mailbox should forward to usera@yourcompany.onmicrosoft.com</span></span>
        
    3. <span data-ttu-id="595f4-344">Почтовый ящик пользователя б должен пересылаться в userb@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="595f4-344">User B's mailbox should forward to userb@yourcompany.onmicrosoft.com</span></span>
        
    4. <span data-ttu-id="595f4-345">По завершении этого действия выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="595f4-345">When you complete this step:</span></span>
        
    5. <span data-ttu-id="595f4-346">Все сообщения, отправленные в usera@yourcompany.com и userb@yourcompany.com, будут доступны в Office 365.</span><span class="sxs-lookup"><span data-stu-id="595f4-346">All mail sent to usera@yourcompany.com and userb@yourcompany.com will be available in Office 365.</span></span>
    
    6. <span data-ttu-id="595f4-347">Примечания.</span><span class="sxs-lookup"><span data-stu-id="595f4-347">Notes:</span></span>
        
        - <span data-ttu-id="595f4-348">Для получения точных инструкций по настройке переадресации обратитесь к поставщику услуг электронной почты.</span><span class="sxs-lookup"><span data-stu-id="595f4-348">Contact your current email provider for the exact steps for setting up forwarding.</span></span>
            
        - <span data-ttu-id="595f4-349">Нет необходимости хранить копии сообщений у текущего поставщика услуг электронной почты.</span><span class="sxs-lookup"><span data-stu-id="595f4-349">You don't need to keep a copy of messages at the current email provider.</span></span>
            
        - <span data-ttu-id="595f4-350">Большинство поставщиков пересылают сообщения электронной почты, оставляя обратный адрес отправителя, чтобы ответы отправляются исходному отправителю.</span><span class="sxs-lookup"><span data-stu-id="595f4-350">Most providers forward email leaving the Reply-to address of the sender intact, so that replies go to the original sender.</span></span>
    
8. <span data-ttu-id="595f4-351">Проверка потока обработки почты</span><span class="sxs-lookup"><span data-stu-id="595f4-351">Test mail flow</span></span>
    
    1. <span data-ttu-id="595f4-352">Войдите в Outlook Web App, используя учетные данные пользователя а.</span><span class="sxs-lookup"><span data-stu-id="595f4-352">Sign in to Outlook Web App using User A's credentials.</span></span>
        
    2. <span data-ttu-id="595f4-353">Выполните следующие тесты:</span><span class="sxs-lookup"><span data-stu-id="595f4-353">Perform the following tests:</span></span>
        
    3. <span data-ttu-id="595f4-354">Протестируйте локальную электронную почту Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="595f4-354">Test local Microsoft email.</span></span> <span data-ttu-id="595f4-355">Например, отправьте сообщение электронной почты пользователю б. Это сообщение должно доставляться немедленно.</span><span class="sxs-lookup"><span data-stu-id="595f4-355">For example, send an email to User B. This email should be delivered immediately.</span></span> <span data-ttu-id="595f4-356">В этом сценарии сообщение не будет маршрутизироваться к почтовому ящику пользователя б на исходном сервере, так как Office 365 видит почтовый ящик как локальный.</span><span class="sxs-lookup"><span data-stu-id="595f4-356">In this scenario, the message will not be routed to User B's mailbox on your original server because Office 365 sees the mailbox as being local.</span></span>
        
    4. <span data-ttu-id="595f4-357">Протестируйте электронную почту кому-то, кто находится в другой почтовой системе.</span><span class="sxs-lookup"><span data-stu-id="595f4-357">Test email to someone who's on the other email system.</span></span> <span data-ttu-id="595f4-358">Например, отправьте сообщение электронной почты пользователю C. Это сообщение должно быть доставлено в почтовый ящик пользователя на исходном почтовом сервере.</span><span class="sxs-lookup"><span data-stu-id="595f4-358">For example, send an email to User C. This email should be delivered to User C's mailbox on your original mail server.</span></span>
        
    5. <span data-ttu-id="595f4-359">С внешней учетной записи или из учетной записи сотрудника в другой почтовой системе убедитесь, что пересылка правильно настроена в другой почтовой системе.</span><span class="sxs-lookup"><span data-stu-id="595f4-359">From an outside account, or from an employee's email account on the other email system, verify that forwarding is set up properly on the other email system.</span></span> <span data-ttu-id="595f4-360">Например, с исходной учетной записи сервера пользователя или учетной записи Hotmail Отправьте пользователю сообщение электронной почты и убедитесь, что оно поступает в почтовый ящик пользователя Office 365.</span><span class="sxs-lookup"><span data-stu-id="595f4-360">For example, from User C's original server account or a Hotmail account, send User A an email and verify that it arrives in User A's Office 365 mailbox.</span></span>
        
9. <span data-ttu-id="595f4-361">Перемещение содержимого почтового ящика</span><span class="sxs-lookup"><span data-stu-id="595f4-361">Move mailbox contents</span></span>
    
    1. <span data-ttu-id="595f4-362">Так как существует только два пользователя для перемещения, а пользователь а и пользователь б одновременно используют Outlook, электронную почту можно переместить, открыв старую. PST-файл в новом профиле Outlook и скопировать сообщения, элементы календаря, контакты и т. д., как показано в разделе Импорт элементов Outlook из файла данных Outlook (PST).</span><span class="sxs-lookup"><span data-stu-id="595f4-362">Since there are only two users to move, and since User A and User B are both using Outlook already, the email can be moved by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, etc. as shown in Import Outlook items from an Outlook Data File (.pst).</span></span> <span data-ttu-id="595f4-363">Будучи организованными в нужные расположения в почтовом ящике Office 365, все элементы доступны с любого устройства в любом месте.</span><span class="sxs-lookup"><span data-stu-id="595f4-363">Once organized in the proper locations in the Office 365 mailbox, the items can all be accessed from any device, anywhere.</span></span>
        
    2. <span data-ttu-id="595f4-364">Если включены дополнительные почтовые ящики или если сотрудники еще не используют Outlook, вы можете использовать средства миграции, доступные в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="595f4-364">When more mailboxes are involved, or if the employees are not already using Outlook, you can use the migration tools available in the Exchange admin center.</span></span> <span data-ttu-id="595f4-365">Чтобы приступить к работе, перейдите в центр администрирования Exchange и следуйте указаниям в разделе Миграция электронной почты с сервера IMAP в почтовые ящики Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="595f4-365">To get started, go to Exchange admin center and follow the directions in Migrate Email from an IMAP Server to Exchange Online Mailboxes.</span></span>
    
