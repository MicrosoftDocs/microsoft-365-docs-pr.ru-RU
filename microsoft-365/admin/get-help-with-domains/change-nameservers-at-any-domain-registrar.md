---
title: Изменение именных имен, чтобы настроить Microsoft 365 с любым регистратором домена
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: Узнайте, как добавить и настроить домен в Microsoft 365, чтобы ваши службы, такие как электронная почта и Skype для бизнеса Online, использовали собственное доменное имя.
ms.openlocfilehash: 1348beb09fcbc5c12d01dbf197b1cb1240decded
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332646"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a><span data-ttu-id="27bb7-103">Изменение именных имен, чтобы настроить Microsoft 365 с любым регистратором домена</span><span class="sxs-lookup"><span data-stu-id="27bb7-103">Change nameservers to set up Microsoft 365 with any domain registrar</span></span>

 <span data-ttu-id="27bb7-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="27bb7-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="27bb7-105">Следуйте этим инструкциям, чтобы добавить и настроить домен в Microsoft 365, чтобы ваши службы, такие как электронная почта и Teams, использовали собственное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="27bb7-105">Follow these instructions to add and set up your domain in Microsoft 365 so your services like email and Teams will use your own domain name.</span></span> <span data-ttu-id="27bb7-106">Для этого необходимо проверить домен, а затем изменить тезки домена на Microsoft 365, чтобы можно было настроить правильные записи DNS.</span><span class="sxs-lookup"><span data-stu-id="27bb7-106">To do this, you'll verify your domain, and then change your domain's nameservers to Microsoft 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="27bb7-107">Выполните следующие действия, если в следующих утверждениях описана ваша ситуация:</span><span class="sxs-lookup"><span data-stu-id="27bb7-107">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="27bb7-108">У вас есть собственный домен и вы хотите настроить его для работы с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27bb7-108">You have your own domain and want to set it up to work with Microsoft 365.</span></span>
    
- <span data-ttu-id="27bb7-109">Вы хотите, чтобы Microsoft 365 управляет записями DNS для вас.</span><span class="sxs-lookup"><span data-stu-id="27bb7-109">You want Microsoft 365 to manage your DNS records for you.</span></span> <span data-ttu-id="27bb7-110">При желании вы можете [управлять своими записями DNS самостоятельно](../setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="27bb7-110">(If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="27bb7-111">Добавьте запись TXT или MX для проверки</span><span class="sxs-lookup"><span data-stu-id="27bb7-111">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="27bb7-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="27bb7-112"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="27bb7-p103">Нужно создать только одну из этих записей. TXT является предпочтительным типом, но некоторые поставщики услуг размещения DNS не поддерживают его. В таком случае можно создать MX-запись.</span><span class="sxs-lookup"><span data-stu-id="27bb7-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="27bb7-p104">Прежде чем вы сможете использовать свой домен в Microsoft 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Microsoft 365 подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="27bb7-p104">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="27bb7-p105">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="27bb7-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="27bb7-119">Найдите область на веб-сайте поставщика хостинга DNS, в которой можно создать новую запись</span><span class="sxs-lookup"><span data-stu-id="27bb7-119">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="27bb7-120">Войдите на сайт поставщика услуг размещения DNS.</span><span class="sxs-lookup"><span data-stu-id="27bb7-120">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="27bb7-121"> Выберите свой домен.</span><span class="sxs-lookup"><span data-stu-id="27bb7-121">Choose your domain.</span></span>
    
3. <span data-ttu-id="27bb7-122">Найдите страницу, на которой можно редактировать DNS-записи для домена.</span><span class="sxs-lookup"><span data-stu-id="27bb7-122">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="27bb7-123">Создание записи</span><span class="sxs-lookup"><span data-stu-id="27bb7-123">Create the record</span></span>

<span data-ttu-id="27bb7-124">При создании записи TXT или MX следуйте соответствующим инструкциям.</span><span class="sxs-lookup"><span data-stu-id="27bb7-124">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="27bb7-125">**Для создания TXT-записи используйте следующие значения:**</span><span class="sxs-lookup"><span data-stu-id="27bb7-125">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="27bb7-126">**Record Type** (Тип записи)</span><span class="sxs-lookup"><span data-stu-id="27bb7-126">**Record Type**</span></span> <br/> |<span data-ttu-id="27bb7-127">**Alias** (Псевдоним) или **Host Name** (Имя узла)</span><span class="sxs-lookup"><span data-stu-id="27bb7-127">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="27bb7-128">**Value** (Значение)</span><span class="sxs-lookup"><span data-stu-id="27bb7-128">**Value**</span></span> <br/> |<span data-ttu-id="27bb7-129">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="27bb7-129">**TTL**</span></span> <br/> |
|<span data-ttu-id="27bb7-130">TXT</span><span class="sxs-lookup"><span data-stu-id="27bb7-130">TXT</span></span>  <br/> |<span data-ttu-id="27bb7-131">Выполните одно из следующих действий: Введите **@**, оставьте поле пустым или укажите имя своего домена.</span><span class="sxs-lookup"><span data-stu-id="27bb7-131">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="27bb7-132">> [!NOTE]> У различных узлов DNS могут быть разные требования к этому полю.</span><span class="sxs-lookup"><span data-stu-id="27bb7-132">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="27bb7-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="27bb7-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="27bb7-134">> [!NOTE]> Это пример.</span><span class="sxs-lookup"><span data-stu-id="27bb7-134">> [!NOTE]> This is an example.</span></span> <span data-ttu-id="27bb7-135">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27bb7-135">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="27bb7-136">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="27bb7-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="27bb7-137">Задайте для этого значения **1 hour** (1 час) или эквивалент в минутах ( **60** ), секундах ( **3600** ) и т. д.</span><span class="sxs-lookup"><span data-stu-id="27bb7-137">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="27bb7-138">**Для создания MX-записи используйте следующие значения:**</span><span class="sxs-lookup"><span data-stu-id="27bb7-138">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="27bb7-139">**Record Type** (Тип записи)</span><span class="sxs-lookup"><span data-stu-id="27bb7-139">**Record Type**</span></span>|<span data-ttu-id="27bb7-140">**Alias** (Псевдоним) или **Host Name** (Имя узла)</span><span class="sxs-lookup"><span data-stu-id="27bb7-140">**Alias** or **Host Name**</span></span>|<span data-ttu-id="27bb7-141">**Value** (Значение)</span><span class="sxs-lookup"><span data-stu-id="27bb7-141">**Value**</span></span>|<span data-ttu-id="27bb7-142">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="27bb7-142">**Priority**</span></span>|<span data-ttu-id="27bb7-143">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="27bb7-143">**TTL**</span></span>|
|<span data-ttu-id="27bb7-144">MX</span><span class="sxs-lookup"><span data-stu-id="27bb7-144">MX</span></span>|<span data-ttu-id="27bb7-145">Введите знак **@** или имя своего домена.</span><span class="sxs-lookup"><span data-stu-id="27bb7-145">Type either **@** or your domain name.</span></span> |<span data-ttu-id="27bb7-146">MS=ms *XXXXXXXX* > [!NOTE]> Это пример.</span><span class="sxs-lookup"><span data-stu-id="27bb7-146">MS=ms *XXXXXXXX* > [!NOTE]> This is an example.</span></span> <span data-ttu-id="27bb7-147">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27bb7-147">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="27bb7-148">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="27bb7-148">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="27bb7-149">В поле **Priority** (Приоритет) используйте более низкое значение приоритета, чем указанное для других записей MX, во избежание конфликтов с записью MX, используемой для потока обработки почты.</span><span class="sxs-lookup"><span data-stu-id="27bb7-149">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="27bb7-150">Дополнительные сведения о приоритете см. в статье [Что такое приоритет записей MX?](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="27bb7-150">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> |<span data-ttu-id="27bb7-151">Задайте для этого значения **1 hour** (1 час) или эквивалент в минутах ( **60** ), секундах ( **3600** ) и т. д.</span><span class="sxs-lookup"><span data-stu-id="27bb7-151">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="27bb7-152">Сохранение записи</span><span class="sxs-lookup"><span data-stu-id="27bb7-152">Save the record</span></span>

<span data-ttu-id="27bb7-153">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Microsoft 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="27bb7-153">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="27bb7-154">Если Microsoft 365 обнаружит правильную запись TXT, это значит, что домен проверен.</span><span class="sxs-lookup"><span data-stu-id="27bb7-154">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="27bb7-155">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="27bb7-155">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="27bb7-156">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="27bb7-156">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="27bb7-157">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="27bb7-157">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="27bb7-158">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="27bb7-158">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="27bb7-p109">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="27bb7-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="27bb7-162">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="27bb7-162">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="27bb7-163"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="27bb7-163"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="27bb7-164">Когда вы доберется до последнего шага мастера настройки доменов в Microsoft 365, у вас остается одна задача.</span><span class="sxs-lookup"><span data-stu-id="27bb7-164">When you get to the last step of the domains setup wizard in Microsoft 365, you have one task remaining.</span></span> <span data-ttu-id="27bb7-165">Чтобы настроить домен службами Microsoft 365, например электронной почтой, вы измените записи имен домена (или NS) в регистраторе домена, чтобы указать на первичные и вторичные именные имена Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27bb7-165">To set up your domain with Microsoft 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Microsoft 365 primary and secondary nameservers.</span></span> <span data-ttu-id="27bb7-166">Затем, так как в Microsoft 365 размещена DNS, необходимые DNS-записи для ваших служб настроены автоматически для вас.</span><span class="sxs-lookup"><span data-stu-id="27bb7-166">Then, because Microsoft 365 hosts your DNS, the required DNS records for your services are set up automatically for you.</span></span> <span data-ttu-id="27bb7-167">Вы можете самостоятельно обновлять записи сервера доменных имен, следуя инструкциям в разделе справки на веб-сайте регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="27bb7-167">You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website.</span></span> <span data-ttu-id="27bb7-168">Если вы еще не знакомы с DNS, обратитесь в службу поддержки регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="27bb7-168">If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="27bb7-169">Чтобы самостоятельно изменить серверы доменных имен на веб-сайте регистратора доменных имен, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="27bb7-169">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="27bb7-170">Найдите область на веб-сайте регистратора домена, в которой можно изменить тезки для домена или области, в которой можно использовать настраиваемые именные имена.</span><span class="sxs-lookup"><span data-stu-id="27bb7-170">Find the area on the domain registrar's website where you can change the nameservers for your domain or an area where you can use custom nameservers.</span></span>
    
2. <span data-ttu-id="27bb7-171">Создайте записи nameserver или отредактировать существующие записи nameserver, чтобы соответствовать следующим значениям:</span><span class="sxs-lookup"><span data-stu-id="27bb7-171">Create nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="27bb7-172">Основной сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="27bb7-172">First nameserver</span></span>  <br/> |<span data-ttu-id="27bb7-173">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="27bb7-173">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="27bb7-174">Второстепенный сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="27bb7-174">Second nameserver</span></span>  <br/> |<span data-ttu-id="27bb7-175">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="27bb7-175">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="27bb7-176">Третий сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="27bb7-176">Third nameserver</span></span>  <br/> |<span data-ttu-id="27bb7-177">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="27bb7-177">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="27bb7-178">Четвертый сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="27bb7-178">Fourth nameserver</span></span>  <br/> |<span data-ttu-id="27bb7-179">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="27bb7-179">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="27bb7-180">Лучше всего добавить все четыре записи, но если регистратор поддерживает только **две,** добавьте ns1.bdm.microsoftonline.com **и ns2.bdm.microsoftonline.com.**</span><span class="sxs-lookup"><span data-stu-id="27bb7-180">It's best to add all four records, but if your registrar only supports two, add **ns1.bdm.microsoftonline.com** and **ns2.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="27bb7-181">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="27bb7-181">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="27bb7-182">При изменении записей NS домена, указываю на тезки Microsoft 365, все службы, которые в настоящее время связаны с вашим доменом, будут затронуты.</span><span class="sxs-lookup"><span data-stu-id="27bb7-182">When you change your domain's NS records to point to the Microsoft 365 nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="27bb7-183">Если вы пропустили какие-либо этапы работы мастера, например добавление адресов электронной почты, или используете свой домен для размещения блогов, корзин для покупок или других служб, необходимо выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="27bb7-183">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="27bb7-184">В противном случае это изменение может привести к простою служб, например к отсутствию доступа к электронной почте или веб-сайту.</span><span class="sxs-lookup"><span data-stu-id="27bb7-184">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="27bb7-185">Найдите на веб-сайте регистратора домена область, в которой можно изменить серверы доменных имен для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="27bb7-185">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="27bb7-186">Создайте две записи сервера доменных имен или измените существующие так, чтобы они соответствовали указанным ниже значениям.</span><span class="sxs-lookup"><span data-stu-id="27bb7-186">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="27bb7-187">Основной сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="27bb7-187">First nameserver</span></span>  <br/> |<span data-ttu-id="27bb7-188">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="27bb7-188">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="27bb7-189">Второстепенный сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="27bb7-189">Second nameserver</span></span>  <br/> |<span data-ttu-id="27bb7-190">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="27bb7-190">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="27bb7-191">Необходимо использовать по крайней мере две записи nameserver.</span><span class="sxs-lookup"><span data-stu-id="27bb7-191">You should use at least two nameserver records.</span></span> <span data-ttu-id="27bb7-192">Если в списке указаны другие имена, их можно либо  удалить, либо изменить на ns3.dns.partner.microsoftonline.cn **и ns4.dns.partner.microsoftonline.cn.**</span><span class="sxs-lookup"><span data-stu-id="27bb7-192">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="27bb7-193">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="27bb7-193">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="27bb7-194">При изменении записей NS вашего домена, указываемых на Office 365, управляемых 21 nameserversVianet, все службы, которые в настоящее время связаны с вашим доменом, будут затронуты.</span><span class="sxs-lookup"><span data-stu-id="27bb7-194">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="27bb7-195">Если вы пропустили какие-либо этапы работы мастера, например добавление адресов электронной почты, или используете свой домен для размещения блогов, корзин для покупок или других служб, необходимо выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="27bb7-195">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="27bb7-196">В противном случае это изменение может привести к простою служб, например к отсутствию доступа к электронной почте или веб-сайту.</span><span class="sxs-lookup"><span data-stu-id="27bb7-196">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="27bb7-197">Например, для размещения электронной почты и веб-сайта может понадобиться выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="27bb7-197">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="27bb7-198">Перед изменением записей NS переместите все адреса электронной почты, которые используют ваш домен, в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27bb7-198">Move all email addresses that use your domain to Microsoft 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="27bb7-199">Хотите добавить домен, который в настоящее время используется с веб-адресом, например www.fourthcoffee.com?</span><span class="sxs-lookup"><span data-stu-id="27bb7-199">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="27bb7-200">При добавлении домена можно сделать следующие действия, чтобы сохранить веб-сайт, на котором сейчас находится сайт, чтобы люди могли по-прежнему получать доступ к веб-сайту после изменения записей NS домена, указав на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27bb7-200">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Microsoft 365.</span></span>

1. <span data-ttu-id="27bb7-201">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="27bb7-201">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="27bb7-202">На странице **Домены** выберите домен.</span><span class="sxs-lookup"><span data-stu-id="27bb7-202">On the **Domains** page, select a domain.</span></span>

3. <span data-ttu-id="27bb7-203">На странице сведения о домене выберите вкладку **записей DNS.**</span><span class="sxs-lookup"><span data-stu-id="27bb7-203">On the domain details page, select the **DNS records** tab.</span></span>
 
4. <span data-ttu-id="27bb7-204">Выберите **запись Добавить**.</span><span class="sxs-lookup"><span data-stu-id="27bb7-204">Select **Add record**.</span></span>

5. <span data-ttu-id="27bb7-205">В **пользовательской области записи DNS**  из списка выпаданий типа выберите **A (Address).**</span><span class="sxs-lookup"><span data-stu-id="27bb7-205">In the **Add a custom DNS record** pane, from the **Type** dropdown list, select **A (Address)**.</span></span>

6. <span data-ttu-id="27bb7-206">В поле **Имя хозяина или псевдоним введите** **@** .</span><span class="sxs-lookup"><span data-stu-id="27bb7-206">In the **Host name or Alias** box, type **@**.</span></span>

7. <span data-ttu-id="27bb7-207">В поле **IP-адрес** введите статичный IP-адрес веб-сайта, на котором он в настоящее время находится.</span><span class="sxs-lookup"><span data-stu-id="27bb7-207">In the **IP Address** box, type the static IP address for the website where it's currently hosted.</span></span> <span data-ttu-id="27bb7-208">Например, 172.16.140.1.</span><span class="sxs-lookup"><span data-stu-id="27bb7-208">For example, 172.16.140.1.</span></span>
    
> [!IMPORTANT]
>  <span data-ttu-id="27bb7-209">Это должен быть _статичный_ IP-адрес для веб-сайта, а не _динамический_ IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="27bb7-209">This must be a _static_ IP address for the website, not a _dynamic_ IP address.</span></span> <span data-ttu-id="27bb7-210">Чтобы убедиться, что вы можете получить статичный IP-адрес для общедоступных веб-сайтов, ознакомьтесь с сайтом, на котором размещен ваш веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="27bb7-210">To make sure you can get a static IP address for your public website, check with the site that hosts your website.</span></span>
   
8. <span data-ttu-id="27bb7-211">Если вы хотите изменить параметр TTL для записи, выберите новое время из списка **отсевов TTL.**</span><span class="sxs-lookup"><span data-stu-id="27bb7-211">If you want to change the TTL setting for the record, select a new length of time from the **TTL** dropdown list.</span></span> <span data-ttu-id="27bb7-212">В противном случае продолжайте шаг 9.</span><span class="sxs-lookup"><span data-stu-id="27bb7-212">Otherwise, continue to step 9.</span></span>
    
9. <span data-ttu-id="27bb7-213">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="27bb7-213">Select **Save**.</span></span> 
    
<span data-ttu-id="27bb7-214">Кроме того, можно создать запись CNAME, чтобы упростить поиск веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="27bb7-214">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1.  <span data-ttu-id="27bb7-215">Выберите **запись Добавить**.</span><span class="sxs-lookup"><span data-stu-id="27bb7-215">Select **Add record**.</span></span>

3.  <span data-ttu-id="27bb7-216">В **пользовательской области записи DNS**  из списка выпаданий типа выберите **CNAME (Alias).**</span><span class="sxs-lookup"><span data-stu-id="27bb7-216">In the **Add a custom DNS record** pane, from the **Type** dropdown list, select **CNAME (Alias)**.</span></span>
4.  <span data-ttu-id="27bb7-217">В поле **Имя хозяина или псевдоним** введите **www**.</span><span class="sxs-lookup"><span data-stu-id="27bb7-217">In the **Host name or Alias** box, type **www**.</span></span>
5.  <span data-ttu-id="27bb7-218">В поле **Пункты для адреса** введите полное доменное имя (FQDN) для вашего веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="27bb7-218">In the **Points to address** box, type the fully qualified domain name (FQDN) for your website.</span></span> <span data-ttu-id="27bb7-219">Например, **contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="27bb7-219">For example, **contoso.com**.</span></span>
6.  <span data-ttu-id="27bb7-220">Если вы хотите изменить параметр TTL для записи, выберите новое время из списка **отсевов TTL.**</span><span class="sxs-lookup"><span data-stu-id="27bb7-220">If you want to change the TTL setting for the record, select a new length of time from the **TTL** dropdown list.</span></span> <span data-ttu-id="27bb7-221">В противном случае продолжайте шаг 6.</span><span class="sxs-lookup"><span data-stu-id="27bb7-221">Otherwise, continue to step 6.</span></span>
7.  <span data-ttu-id="27bb7-222">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="27bb7-222">Select **Save**.</span></span>

<span data-ttu-id="27bb7-223">После обновления записей имен, чтобы указать на Microsoft, настройка домена завершена.</span><span class="sxs-lookup"><span data-stu-id="27bb7-223">After the nameserver records are updated to point to Microsoft, your domain setup is complete.</span></span> <span data-ttu-id="27bb7-224">Электронная почта отправлена в Корпорацию Майкрософт, и трафик на ваш веб-сайт продолжает переходить на текущий веб-сайт."</span><span class="sxs-lookup"><span data-stu-id="27bb7-224">Email is routed to Microsoft, and traffic to your website address continues to go to your current website host.\`</span></span>
    
> [!NOTE]
> <span data-ttu-id="27bb7-225">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="27bb7-225">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="27bb7-226">Затем ваша электронная почта Майкрософт и другие службы будут настроены на работу с доменом.</span><span class="sxs-lookup"><span data-stu-id="27bb7-226">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
