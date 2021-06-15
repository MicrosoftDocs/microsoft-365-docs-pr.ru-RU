---
title: Изменение именных имен для Microsoft 365 с любым регистратором домена
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
ms.openlocfilehash: 9c26f9afcf17857c4b3b8f05b89253272cf20e56
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924507"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a><span data-ttu-id="42c67-103">Изменение именных имен для Microsoft 365 с любым регистратором домена</span><span class="sxs-lookup"><span data-stu-id="42c67-103">Change nameservers to set up Microsoft 365 with any domain registrar</span></span>

 <span data-ttu-id="42c67-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="42c67-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="42c67-105">Следуйте этим инструкциям, чтобы добавить и настроить домен в Microsoft 365, чтобы ваши службы, такие как электронная почта и Teams, использовали собственное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="42c67-105">Follow these instructions to add and set up your domain in Microsoft 365 so your services like email and Teams will use your own domain name.</span></span> <span data-ttu-id="42c67-106">Для этого необходимо проверить домен, а затем изменить имена домена на Microsoft 365, чтобы можно было настроить правильные записи DNS.</span><span class="sxs-lookup"><span data-stu-id="42c67-106">To do this, you'll verify your domain, and then change your domain's nameservers to Microsoft 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="42c67-107">Выполните следующие действия, если в следующих утверждениях описана ваша ситуация:</span><span class="sxs-lookup"><span data-stu-id="42c67-107">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="42c67-108">У вас есть собственный домен и вы хотите настроить его для работы с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="42c67-108">You have your own domain and want to set it up to work with Microsoft 365.</span></span>
    
- <span data-ttu-id="42c67-109">Вы хотите Microsoft 365 управлять записями DNS для вас.</span><span class="sxs-lookup"><span data-stu-id="42c67-109">You want Microsoft 365 to manage your DNS records for you.</span></span> <span data-ttu-id="42c67-110">При желании вы можете [управлять своими записями DNS самостоятельно](../setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="42c67-110">(If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="42c67-111">Добавьте запись TXT или MX для проверки</span><span class="sxs-lookup"><span data-stu-id="42c67-111">Add a TXT or MX record for verification</span></span>

> [!NOTE]
> <span data-ttu-id="42c67-p103">Нужно создать только одну из этих записей. TXT является предпочтительным типом, но некоторые поставщики услуг размещения DNS не поддерживают его. В таком случае можно создать MX-запись.</span><span class="sxs-lookup"><span data-stu-id="42c67-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="42c67-p104">Прежде чем вы сможете использовать свой домен в Microsoft 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Microsoft 365 подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="42c67-p104">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="42c67-p105">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="42c67-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="42c67-118">Найдите область на веб-сайте поставщика хостинга DNS, в которой можно создать новую запись</span><span class="sxs-lookup"><span data-stu-id="42c67-118">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="42c67-119">Войдите на сайт поставщика услуг размещения DNS.</span><span class="sxs-lookup"><span data-stu-id="42c67-119">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="42c67-120"> Выберите свой домен.</span><span class="sxs-lookup"><span data-stu-id="42c67-120">Choose your domain.</span></span>
    
3. <span data-ttu-id="42c67-121">Найдите страницу, на которой можно редактировать DNS-записи для домена.</span><span class="sxs-lookup"><span data-stu-id="42c67-121">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="42c67-122">Создание записи</span><span class="sxs-lookup"><span data-stu-id="42c67-122">Create the record</span></span>

<span data-ttu-id="42c67-123">При создании записи TXT или MX следуйте соответствующим инструкциям.</span><span class="sxs-lookup"><span data-stu-id="42c67-123">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="42c67-124">**Для создания TXT-записи используйте следующие значения:**</span><span class="sxs-lookup"><span data-stu-id="42c67-124">**If you create a TXT record, use these values:**</span></span>
    

|<span data-ttu-id="42c67-125">Тип записи</span><span class="sxs-lookup"><span data-stu-id="42c67-125">Record type</span></span><br/> |<span data-ttu-id="42c67-126">Псевдоним или имя хозяина</span><span class="sxs-lookup"><span data-stu-id="42c67-126">Alias or host name</span></span> <br/> |<span data-ttu-id="42c67-127">Значение</span><span class="sxs-lookup"><span data-stu-id="42c67-127">Value</span></span> <br/> |<span data-ttu-id="42c67-128">TTL</span><span class="sxs-lookup"><span data-stu-id="42c67-128">TTL</span></span><br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="42c67-129">TXT</span><span class="sxs-lookup"><span data-stu-id="42c67-129">TXT</span></span>  <br/> |<span data-ttu-id="42c67-130">Выполните одно из следующих действий: Введите **@**, оставьте поле пустым или укажите имя своего домена.</span><span class="sxs-lookup"><span data-stu-id="42c67-130">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="42c67-131">> [!NOTE]> У различных узлов DNS могут быть разные требования к этому полю.</span><span class="sxs-lookup"><span data-stu-id="42c67-131">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="42c67-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="42c67-132">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="42c67-133">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="42c67-133">**Note:** This is an example.</span></span> <span data-ttu-id="42c67-134">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="42c67-134">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="42c67-135">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="42c67-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="42c67-136">Задайте для этого значения **1 hour** (1 час) или эквивалент в минутах ( **60** ), секундах ( **3600** ) и т. д.</span><span class="sxs-lookup"><span data-stu-id="42c67-136">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="42c67-137">**Для создания MX-записи используйте следующие значения:**</span><span class="sxs-lookup"><span data-stu-id="42c67-137">**If you create an MX record, use these values:**</span></span>
    
|<span data-ttu-id="42c67-138">Тип записи</span><span class="sxs-lookup"><span data-stu-id="42c67-138">Record type</span></span>|<span data-ttu-id="42c67-139">Псевдоним или имя хозяина</span><span class="sxs-lookup"><span data-stu-id="42c67-139">Alias or host name</span></span>|<span data-ttu-id="42c67-140">Значение</span><span class="sxs-lookup"><span data-stu-id="42c67-140">Value</span></span>|<span data-ttu-id="42c67-141">Priority (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="42c67-141">Priority</span></span>|<span data-ttu-id="42c67-142">TTL (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="42c67-142">TTL</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="42c67-143">MX</span><span class="sxs-lookup"><span data-stu-id="42c67-143">MX</span></span>|<span data-ttu-id="42c67-144">Введите знак **@** или имя своего домена.</span><span class="sxs-lookup"><span data-stu-id="42c67-144">Type either **@** or your domain name.</span></span> |<span data-ttu-id="42c67-145">ПРИМЕЧАНИЕ MS=ms *XXXXXXXXXX:*  Вот пример.</span><span class="sxs-lookup"><span data-stu-id="42c67-145">MS=ms *XXXXXXXX* **Note:** This is an example.</span></span> <span data-ttu-id="42c67-146">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="42c67-146">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="42c67-147">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="42c67-147">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="42c67-148">В поле **Priority** (Приоритет) используйте более низкое значение приоритета, чем указанное для других записей MX, во избежание конфликтов с записью MX, используемой для потока обработки почты.</span><span class="sxs-lookup"><span data-stu-id="42c67-148">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="42c67-149">Дополнительные сведения о приоритете см. в статье [Что такое приоритет записей MX?](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="42c67-149">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> |<span data-ttu-id="42c67-150">Задайте для этого значения **1 hour** (1 час) или эквивалент в минутах ( **60** ), секундах ( **3600** ) и т. д.</span><span class="sxs-lookup"><span data-stu-id="42c67-150">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="42c67-151">Сохранение записи</span><span class="sxs-lookup"><span data-stu-id="42c67-151">Save the record</span></span>

<span data-ttu-id="42c67-152">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Microsoft 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="42c67-152">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="42c67-153">Если Microsoft 365 обнаружит правильную запись TXT, это значит, что домен проверен.</span><span class="sxs-lookup"><span data-stu-id="42c67-153">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="42c67-154">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="42c67-154">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="42c67-155">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="42c67-155">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="42c67-156">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="42c67-156">On the **Setup** page, select **Start setup**.</span></span>
 
  
4. <span data-ttu-id="42c67-157">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="42c67-157">On the **Verify domain** page, select **Verify**.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="42c67-p109">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="42c67-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="42c67-161">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="42c67-161">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="42c67-162">Когда вы доберется до последнего шага мастера настройки доменов в Microsoft 365, у вас остается одна задача.</span><span class="sxs-lookup"><span data-stu-id="42c67-162">When you get to the last step of the domains setup wizard in Microsoft 365, you have one task remaining.</span></span> <span data-ttu-id="42c67-163">Чтобы настроить домен с Microsoft 365 службами, например электронной почтой, вы измените записи имен домена (или NS) в регистраторе домена, чтобы указать на Microsoft 365 и вторичные имена.</span><span class="sxs-lookup"><span data-stu-id="42c67-163">To set up your domain with Microsoft 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Microsoft 365 primary and secondary nameservers.</span></span> <span data-ttu-id="42c67-164">Затем, Microsoft 365 в котором размещена DNS, для вас автоматически устанавливаются необходимые записи DNS для ваших служб.</span><span class="sxs-lookup"><span data-stu-id="42c67-164">Then, because Microsoft 365 hosts your DNS, the required DNS records for your services are set up automatically for you.</span></span> <span data-ttu-id="42c67-165">Вы можете самостоятельно обновлять записи сервера доменных имен, следуя инструкциям в разделе справки на веб-сайте регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="42c67-165">You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website.</span></span> <span data-ttu-id="42c67-166">Если вы еще не знакомы с DNS, обратитесь в службу поддержки регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="42c67-166">If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="42c67-167">Чтобы самостоятельно изменить серверы доменных имен на веб-сайте регистратора доменных имен, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="42c67-167">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="42c67-168">Найдите область на веб-сайте регистратора домена, в которой можно изменить тезки для домена или области, в которой можно использовать настраиваемые именные имена.</span><span class="sxs-lookup"><span data-stu-id="42c67-168">Find the area on the domain registrar's website where you can change the nameservers for your domain or an area where you can use custom nameservers.</span></span>
    
2. <span data-ttu-id="42c67-169">Создайте записи nameserver или отредактировать существующие записи nameserver, чтобы соответствовать следующим значениям:</span><span class="sxs-lookup"><span data-stu-id="42c67-169">Create nameserver records, or edit the existing nameserver records to match the following values:</span></span>

    - <span data-ttu-id="42c67-170">Первый именник: ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="42c67-170">First nameserver: ns1.bdm.microsoftonline.com</span></span>
    - <span data-ttu-id="42c67-171">Второй именник: ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="42c67-171">Second nameserver: ns2.bdm.microsoftonline.com</span></span>
    - <span data-ttu-id="42c67-172">Третий nameserver: ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="42c67-172">Third nameserver: ns3.bdm.microsoftonline.com</span></span>
    - <span data-ttu-id="42c67-173">Четвертый именник: ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="42c67-173">Fourth nameserver: ns4.bdm.microsoftonline.com</span></span>
      
   
   > [!TIP]
   > <span data-ttu-id="42c67-174">Лучше всего добавить все четыре записи, но если регистратор поддерживает только **две,** добавьте ns1.bdm.microsoftonline.com **и ns2.bdm.microsoftonline.com.**</span><span class="sxs-lookup"><span data-stu-id="42c67-174">It's best to add all four records, but if your registrar only supports two, add **ns1.bdm.microsoftonline.com** and **ns2.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="42c67-175">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="42c67-175">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="42c67-176">При изменении записей NS домена, указываю на Microsoft 365 имен, все службы, которые в настоящее время связаны с доменом, затронуты.</span><span class="sxs-lookup"><span data-stu-id="42c67-176">When you change your domain's NS records to point to the Microsoft 365 nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="42c67-177">Если вы пропустили какие-либо этапы работы мастера, например добавление адресов электронной почты, или используете свой домен для размещения блогов, корзин для покупок или других служб, необходимо выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="42c67-177">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="42c67-178">В противном случае это изменение может привести к простою служб, например к отсутствию доступа к электронной почте или веб-сайту.</span><span class="sxs-lookup"><span data-stu-id="42c67-178">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="42c67-179">Найдите на веб-сайте регистратора домена область, в которой можно изменить серверы доменных имен для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="42c67-179">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="42c67-180">Создайте две записи сервера доменных имен или измените существующие так, чтобы они соответствовали указанным ниже значениям.</span><span class="sxs-lookup"><span data-stu-id="42c67-180">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>

   - <span data-ttu-id="42c67-181">Первый nameserver: ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="42c67-181">First nameserver: ns1.dns.partner.microsoftonline.cn</span></span>
   - <span data-ttu-id="42c67-182">Второй именник: ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="42c67-182">Second nameserver: ns2.dns.partner.microsoftonline.cn</span></span>
    
   > [!TIP]
   > <span data-ttu-id="42c67-183">Необходимо использовать по крайней мере две записи nameserver.</span><span class="sxs-lookup"><span data-stu-id="42c67-183">You should use at least two nameserver records.</span></span> <span data-ttu-id="42c67-184">Если в списке указаны другие имена, их можно либо  удалить, либо изменить на ns3.dns.partner.microsoftonline.cn **и ns4.dns.partner.microsoftonline.cn.**</span><span class="sxs-lookup"><span data-stu-id="42c67-184">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="42c67-185">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="42c67-185">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="42c67-186">При изменении записей NS вашего домена, чтобы указать на Office 365, выполняемые 21 nameserversVianet, все службы, которые в настоящее время связаны с вашим доменом, затронуты.</span><span class="sxs-lookup"><span data-stu-id="42c67-186">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="42c67-187">Если вы пропустили какие-либо этапы работы мастера, например добавление адресов электронной почты, или используете свой домен для размещения блогов, корзин для покупок или других служб, необходимо выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="42c67-187">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="42c67-188">В противном случае это изменение может привести к простою служб, например к отсутствию доступа к электронной почте или веб-сайту.</span><span class="sxs-lookup"><span data-stu-id="42c67-188">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="42c67-189">Например, для размещения электронной почты и веб-сайта может понадобиться выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="42c67-189">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="42c67-190">Перед изменением записей NS переместите все адреса электронной почты, Microsoft 365 домена.</span><span class="sxs-lookup"><span data-stu-id="42c67-190">Move all email addresses that use your domain to Microsoft 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="42c67-191">Хотите добавить домен, который в настоящее время используется с веб-адресом, например www.fourthcoffee.com?</span><span class="sxs-lookup"><span data-stu-id="42c67-191">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="42c67-192">При добавлении домена можно сделать следующие действия, чтобы сохранить веб-сайт, на котором сейчас находится сайт, чтобы люди могли по-прежнему получать доступ к веб-сайту после изменения записей NS домена, чтобы указать на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="42c67-192">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Microsoft 365.</span></span>

1. <span data-ttu-id="42c67-193">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="42c67-193">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="42c67-194">На странице **Домены** выберите домен.</span><span class="sxs-lookup"><span data-stu-id="42c67-194">On the **Domains** page, select a domain.</span></span>

3. <span data-ttu-id="42c67-195">На странице сведения о домене выберите вкладку **записей DNS.**</span><span class="sxs-lookup"><span data-stu-id="42c67-195">On the domain details page, select the **DNS records** tab.</span></span>
 
4. <span data-ttu-id="42c67-196">Выберите **запись Добавить**.</span><span class="sxs-lookup"><span data-stu-id="42c67-196">Select **Add record**.</span></span>

5. <span data-ttu-id="42c67-197">В **пользовательской области записи DNS**  из списка выпаданий типа выберите **A (Address).**</span><span class="sxs-lookup"><span data-stu-id="42c67-197">In the **Add a custom DNS record** pane, from the **Type** dropdown list, select **A (Address)**.</span></span>

6. <span data-ttu-id="42c67-198">В поле **Имя хозяина или псевдоним введите** **@** .</span><span class="sxs-lookup"><span data-stu-id="42c67-198">In the **Host name or Alias** box, type **@**.</span></span>

7. <span data-ttu-id="42c67-199">В поле **IP-адрес** введите статичный IP-адрес веб-сайта, на котором он в настоящее время находится.</span><span class="sxs-lookup"><span data-stu-id="42c67-199">In the **IP Address** box, type the static IP address for the website where it's currently hosted.</span></span> <span data-ttu-id="42c67-200">Например, 172.16.140.1.</span><span class="sxs-lookup"><span data-stu-id="42c67-200">For example, 172.16.140.1.</span></span>
    
> [!IMPORTANT]
>  <span data-ttu-id="42c67-201">Это должен быть _статичный_ IP-адрес для веб-сайта, а не _динамический_ IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="42c67-201">This must be a _static_ IP address for the website, not a _dynamic_ IP address.</span></span> <span data-ttu-id="42c67-202">Чтобы убедиться, что вы можете получить статичный IP-адрес для общедоступных веб-сайтов, ознакомьтесь с сайтом, на котором размещен ваш веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="42c67-202">To make sure you can get a static IP address for your public website, check with the site that hosts your website.</span></span>
   
8. <span data-ttu-id="42c67-203">Если вы хотите изменить параметр TTL для записи, выберите новое время из списка **отсевов TTL.**</span><span class="sxs-lookup"><span data-stu-id="42c67-203">If you want to change the TTL setting for the record, select a new length of time from the **TTL** dropdown list.</span></span> <span data-ttu-id="42c67-204">В противном случае продолжайте шаг 9.</span><span class="sxs-lookup"><span data-stu-id="42c67-204">Otherwise, continue to step 9.</span></span>
    
9. <span data-ttu-id="42c67-205">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="42c67-205">Select **Save**.</span></span> 
    
<span data-ttu-id="42c67-206">Кроме того, можно создать запись CNAME, чтобы упростить поиск веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="42c67-206">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1.  <span data-ttu-id="42c67-207">Выберите **запись Добавить**.</span><span class="sxs-lookup"><span data-stu-id="42c67-207">Select **Add record**.</span></span>

3.  <span data-ttu-id="42c67-208">В **пользовательской области записи DNS**  из списка выпаданий типа выберите **CNAME (Alias).**</span><span class="sxs-lookup"><span data-stu-id="42c67-208">In the **Add a custom DNS record** pane, from the **Type** dropdown list, select **CNAME (Alias)**.</span></span>
4.  <span data-ttu-id="42c67-209">В поле **Имя хозяина или псевдоним** введите **www**.</span><span class="sxs-lookup"><span data-stu-id="42c67-209">In the **Host name or Alias** box, type **www**.</span></span>
5.  <span data-ttu-id="42c67-210">В поле **Пункты для адреса** введите полное доменное имя (FQDN) для вашего веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="42c67-210">In the **Points to address** box, type the fully qualified domain name (FQDN) for your website.</span></span> <span data-ttu-id="42c67-211">Например, **contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="42c67-211">For example, **contoso.com**.</span></span>
6.  <span data-ttu-id="42c67-212">Если вы хотите изменить параметр TTL для записи, выберите новое время из списка **отсевов TTL.**</span><span class="sxs-lookup"><span data-stu-id="42c67-212">If you want to change the TTL setting for the record, select a new length of time from the **TTL** dropdown list.</span></span> <span data-ttu-id="42c67-213">В противном случае продолжайте шаг 6.</span><span class="sxs-lookup"><span data-stu-id="42c67-213">Otherwise, continue to step 6.</span></span>
7.  <span data-ttu-id="42c67-214">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="42c67-214">Select **Save**.</span></span>

<span data-ttu-id="42c67-215">После обновления записей имен, чтобы указать на Microsoft, настройка домена завершена.</span><span class="sxs-lookup"><span data-stu-id="42c67-215">After the nameserver records are updated to point to Microsoft, your domain setup is complete.</span></span> <span data-ttu-id="42c67-216">Электронная почта отправлена в Корпорацию Майкрософт, и трафик на ваш веб-сайт продолжает переходить на текущий веб-сайт."</span><span class="sxs-lookup"><span data-stu-id="42c67-216">Email is routed to Microsoft, and traffic to your website address continues to go to your current website host.\`</span></span>
    
> [!NOTE]
> <span data-ttu-id="42c67-217">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="42c67-217">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="42c67-218">Затем ваша электронная почта Майкрософт и другие службы будут настроены на работу с доменом.</span><span class="sxs-lookup"><span data-stu-id="42c67-218">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="related-content"></a><span data-ttu-id="42c67-219">См. также:</span><span class="sxs-lookup"><span data-stu-id="42c67-219">Related content</span></span>

<span data-ttu-id="42c67-220">[Добавление записей DNS для подключения домена](create-dns-records-at-any-dns-hosting-provider.md) (статьи)</span><span class="sxs-lookup"><span data-stu-id="42c67-220">[Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md) (article)</span></span>\
<span data-ttu-id="42c67-221">[Поиск и устранение неполадок после добавления домена и записей DNS](find-and-fix-issues.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="42c67-221">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>\
<span data-ttu-id="42c67-222">[Управление доменами](index.yml) (страница ссылки)</span><span class="sxs-lookup"><span data-stu-id="42c67-222">[Manage domains](index.yml) (link page)</span></span>
