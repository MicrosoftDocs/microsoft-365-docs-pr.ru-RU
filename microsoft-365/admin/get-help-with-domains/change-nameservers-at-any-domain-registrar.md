---
title: Изменение доменных имен для настроить Microsoft 365 у любого регистратора доменных имен
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
description: Узнайте, как добавить и настроить домен в Microsoft 365, чтобы такие службы, как электронная почта и Skype для бизнеса Online, использовали собственное доменное имя.
ms.openlocfilehash: 492bc5d2a5f3fd9810f045e7effda1ea20fa15ed
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688253"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a><span data-ttu-id="0045b-103">Изменение доменных имен для настроить Microsoft 365 у любого регистратора доменных имен</span><span class="sxs-lookup"><span data-stu-id="0045b-103">Change nameservers to set up Microsoft 365 with any domain registrar</span></span>

 <span data-ttu-id="0045b-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="0045b-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="0045b-105">Сначала [проверьте, есть](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) ли у нас инструкции для вашего регистратора.</span><span class="sxs-lookup"><span data-stu-id="0045b-105">Check [Set up your domain (host-specific instructions)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) first to see if we have instructions for your registrar.</span></span> 
  
<span data-ttu-id="0045b-106">Следуйте этим инструкциям, чтобы добавить и настроить домен в Microsoft 365, чтобы ваши службы, такие как электронная почта и Teams, использовали собственное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="0045b-106">Follow these instructions to add and set up your domain in Microsoft 365 so your services like email and Teams will use your own domain name.</span></span> <span data-ttu-id="0045b-107">Для этого проверьте свой домен, а затем измените доменные имена на Microsoft 365, чтобы можно было настроить правильные записи DNS.</span><span class="sxs-lookup"><span data-stu-id="0045b-107">To do this, you'll verify your domain, and then change your domain's nameservers to Microsoft 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="0045b-108">Выполните следующие действия, если ваша ситуация описана в следующих заявлениях:</span><span class="sxs-lookup"><span data-stu-id="0045b-108">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="0045b-109">У вас есть собственный домен, и вы хотите настроить его для работы с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0045b-109">You have your own domain and want to set it up to work with Microsoft 365.</span></span>
    
- <span data-ttu-id="0045b-110">Вы хотите, чтобы Microsoft 365 управляет своими записями DNS за вас.</span><span class="sxs-lookup"><span data-stu-id="0045b-110">You want Microsoft 365 to manage your DNS records for you.</span></span> <span data-ttu-id="0045b-111">При желании вы можете [управлять своими записями DNS самостоятельно](../setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="0045b-111">(If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="0045b-112">Добавьте запись TXT или MX для проверки</span><span class="sxs-lookup"><span data-stu-id="0045b-112">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="0045b-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="0045b-113"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="0045b-p103">Нужно создать только одну из этих записей. TXT является предпочтительным типом, но некоторые поставщики услуг размещения DNS не поддерживают его. В таком случае можно создать MX-запись.</span><span class="sxs-lookup"><span data-stu-id="0045b-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="0045b-p104">Прежде чем вы сможете использовать свой домен в Microsoft 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Microsoft 365 подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="0045b-p104">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0045b-p105">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="0045b-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="0045b-120">Найдите область на веб-сайте поставщика услуг размещения DNS, где можно создать новую запись</span><span class="sxs-lookup"><span data-stu-id="0045b-120">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="0045b-121">Войдите на сайт поставщика услуг размещения DNS.</span><span class="sxs-lookup"><span data-stu-id="0045b-121">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="0045b-122"> Выберите свой домен.</span><span class="sxs-lookup"><span data-stu-id="0045b-122">Choose your domain.</span></span>
    
3. <span data-ttu-id="0045b-123">Найдите страницу, на которой можно редактировать DNS-записи для домена.</span><span class="sxs-lookup"><span data-stu-id="0045b-123">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="0045b-124">Создание записи</span><span class="sxs-lookup"><span data-stu-id="0045b-124">Create the record</span></span>

<span data-ttu-id="0045b-125">При создании записи TXT или MX следуйте соответствующим инструкциям.</span><span class="sxs-lookup"><span data-stu-id="0045b-125">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="0045b-126">**Для создания TXT-записи используйте следующие значения:**</span><span class="sxs-lookup"><span data-stu-id="0045b-126">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0045b-127">**Record Type** (Тип записи)</span><span class="sxs-lookup"><span data-stu-id="0045b-127">**Record Type**</span></span> <br/> |<span data-ttu-id="0045b-128">**Alias** (Псевдоним) или **Host Name** (Имя узла)</span><span class="sxs-lookup"><span data-stu-id="0045b-128">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="0045b-129">**Value** (Значение)</span><span class="sxs-lookup"><span data-stu-id="0045b-129">**Value**</span></span> <br/> |<span data-ttu-id="0045b-130">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="0045b-130">**TTL**</span></span> <br/> |
|<span data-ttu-id="0045b-131">TXT</span><span class="sxs-lookup"><span data-stu-id="0045b-131">TXT</span></span>  <br/> |<span data-ttu-id="0045b-132">Выполните одно из следующих действий: Введите **@**, оставьте поле пустым или укажите имя своего домена.</span><span class="sxs-lookup"><span data-stu-id="0045b-132">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="0045b-133">> [!NOTE]> У различных узлов DNS могут быть разные требования к этому полю.</span><span class="sxs-lookup"><span data-stu-id="0045b-133">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="0045b-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="0045b-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="0045b-135">> [!NOTE]> Это пример.</span><span class="sxs-lookup"><span data-stu-id="0045b-135">> [!NOTE]> This is an example.</span></span> <span data-ttu-id="0045b-136">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0045b-136">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="0045b-137">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="0045b-137">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="0045b-138">Задайте для этого значения **1 hour** (1 час) или эквивалент в минутах ( **60** ), секундах ( **3600** ) и т. д.</span><span class="sxs-lookup"><span data-stu-id="0045b-138">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="0045b-139">**Для создания MX-записи используйте следующие значения:**</span><span class="sxs-lookup"><span data-stu-id="0045b-139">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0045b-140">**Record Type** (Тип записи)</span><span class="sxs-lookup"><span data-stu-id="0045b-140">**Record Type**</span></span>|<span data-ttu-id="0045b-141">**Alias** (Псевдоним) или **Host Name** (Имя узла)</span><span class="sxs-lookup"><span data-stu-id="0045b-141">**Alias** or **Host Name**</span></span>|<span data-ttu-id="0045b-142">**Value** (Значение)</span><span class="sxs-lookup"><span data-stu-id="0045b-142">**Value**</span></span>|<span data-ttu-id="0045b-143">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="0045b-143">**Priority**</span></span>|<span data-ttu-id="0045b-144">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="0045b-144">**TTL**</span></span>|
|<span data-ttu-id="0045b-145">MX</span><span class="sxs-lookup"><span data-stu-id="0045b-145">MX</span></span>|<span data-ttu-id="0045b-146">Введите знак **@** или имя своего домена.</span><span class="sxs-lookup"><span data-stu-id="0045b-146">Type either **@** or your domain name.</span></span> |<span data-ttu-id="0045b-147">MS=ms *XXXXXXXX* > [!NOTE]> Это пример.</span><span class="sxs-lookup"><span data-stu-id="0045b-147">MS=ms *XXXXXXXX* > [!NOTE]> This is an example.</span></span> <span data-ttu-id="0045b-148">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0045b-148">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="0045b-149">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="0045b-149">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="0045b-150">В поле **Priority** (Приоритет) используйте более низкое значение приоритета, чем указанное для других записей MX, во избежание конфликтов с записью MX, используемой для потока обработки почты.</span><span class="sxs-lookup"><span data-stu-id="0045b-150">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="0045b-151">Дополнительные сведения о приоритете см. в статье [Что такое приоритет записей MX?](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="0045b-151">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> |<span data-ttu-id="0045b-152">Задайте для этого значения **1 hour** (1 час) или эквивалент в минутах ( **60** ), секундах ( **3600** ) и т. д.</span><span class="sxs-lookup"><span data-stu-id="0045b-152">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="0045b-153">Сохранение записи</span><span class="sxs-lookup"><span data-stu-id="0045b-153">Save the record</span></span>

<span data-ttu-id="0045b-154">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Microsoft 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="0045b-154">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="0045b-155">Если Microsoft 365 обнаружит правильную запись TXT, это значит, что домен проверен.</span><span class="sxs-lookup"><span data-stu-id="0045b-155">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="0045b-156">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="0045b-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="0045b-157">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="0045b-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="0045b-158">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="0045b-158">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="0045b-159">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="0045b-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="0045b-p109">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0045b-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="0045b-163">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="0045b-163">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="0045b-164"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="0045b-164"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="0045b-165">Когда вы дойдете до последнего шага мастера настройки доменов в Microsoft 365, остается одна задача.</span><span class="sxs-lookup"><span data-stu-id="0045b-165">When you get to the last step of the domains setup wizard in Microsoft 365, you have one task remaining.</span></span> <span data-ttu-id="0045b-166">Чтобы настроить домен со службами Microsoft 365, например электронной почтой, измените записи доменных имен (или NS) у регистратора доменных имен так, чтобы они указывают на основной и дополнительный доменные имена Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0045b-166">To set up your domain with Microsoft 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Microsoft 365 primary and secondary nameservers.</span></span> <span data-ttu-id="0045b-167">После этого, так как в Microsoft 365 размещена служба DNS, необходимые записи DNS для ваших служб устанавливаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="0045b-167">Then, because Microsoft 365 hosts your DNS, the required DNS records for your services are set up automatically for you.</span></span> <span data-ttu-id="0045b-168">Вы можете самостоятельно обновлять записи сервера доменных имен, следуя инструкциям в разделе справки на веб-сайте регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="0045b-168">You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website.</span></span> <span data-ttu-id="0045b-169">Если вы еще не знакомы с DNS, обратитесь в службу поддержки регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="0045b-169">If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="0045b-170">Чтобы самостоятельно изменить серверы доменных имен на веб-сайте регистратора доменных имен, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="0045b-170">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="0045b-171">Найдите область на веб-сайте регистратора доменных имен, где можно изменить доменные имена или область, в которой можно использовать настраиваемые доменные имена.</span><span class="sxs-lookup"><span data-stu-id="0045b-171">Find the area on the domain registrar's website where you can change the nameservers for your domain or an area where you can use custom nameservers.</span></span>
    
2. <span data-ttu-id="0045b-172">Создайте записи для доменных имен или отредактируете существующие записи в соответствии со следующими значениями:</span><span class="sxs-lookup"><span data-stu-id="0045b-172">Create nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="0045b-173">Основной сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="0045b-173">First nameserver</span></span>  <br/> |<span data-ttu-id="0045b-174">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="0045b-174">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="0045b-175">Второстепенный сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="0045b-175">Second nameserver</span></span>  <br/> |<span data-ttu-id="0045b-176">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="0045b-176">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="0045b-177">Третий сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="0045b-177">Third nameserver</span></span>  <br/> |<span data-ttu-id="0045b-178">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="0045b-178">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="0045b-179">Четвертый сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="0045b-179">Fourth nameserver</span></span>  <br/> |<span data-ttu-id="0045b-180">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="0045b-180">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="0045b-181">Лучше всего добавить все четыре записи, но если ваш регистратор  поддерживает только две записи, добавьте ns1.bdm.microsoftonline.com и **ns2.bdm.microsoftonline.com.**</span><span class="sxs-lookup"><span data-stu-id="0045b-181">It's best to add all four records, but if your registrar only supports two, add **ns1.bdm.microsoftonline.com** and **ns2.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="0045b-182">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="0045b-182">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="0045b-183">Когда вы меняете записи доменных имен таким образом, чтобы они указывают на доменные службы Microsoft 365, это влияет на все службы, связанные с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="0045b-183">When you change your domain's NS records to point to the Microsoft 365 nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="0045b-184">Если вы пропустили какие-либо этапы работы мастера, например добавление адресов электронной почты, или используете свой домен для размещения блогов, корзин для покупок или других служб, необходимо выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="0045b-184">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="0045b-185">В противном случае это изменение может привести к простою служб, например к отсутствию доступа к электронной почте или веб-сайту.</span><span class="sxs-lookup"><span data-stu-id="0045b-185">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="0045b-186">Найдите на веб-сайте регистратора домена область, в которой можно изменить серверы доменных имен для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="0045b-186">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="0045b-187">Создайте две записи сервера доменных имен или измените существующие так, чтобы они соответствовали указанным ниже значениям.</span><span class="sxs-lookup"><span data-stu-id="0045b-187">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="0045b-188">Основной сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="0045b-188">First nameserver</span></span>  <br/> |<span data-ttu-id="0045b-189">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="0045b-189">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="0045b-190">Второстепенный сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="0045b-190">Second nameserver</span></span>  <br/> |<span data-ttu-id="0045b-191">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="0045b-191">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="0045b-192">Следует использовать по крайней мере две записи для доменных имен.</span><span class="sxs-lookup"><span data-stu-id="0045b-192">You should use at least two nameserver records.</span></span> <span data-ttu-id="0045b-193">Если в списке есть другие доменные имена, их можно  удалить или изменить на ns3.dns.partner.microsoftonline.cn и **ns4.dns.partner.microsoftonline.cn.**</span><span class="sxs-lookup"><span data-stu-id="0045b-193">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="0045b-194">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="0045b-194">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="0045b-195">Когда вы меняете записи доменных имен так, чтобы они указывают на службы Office 365, управляемые 21Vianet, это влияет на все службы, которые в настоящее время связаны с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="0045b-195">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="0045b-196">Если вы пропустили какие-либо этапы работы мастера, например добавление адресов электронной почты, или используете свой домен для размещения блогов, корзин для покупок или других служб, необходимо выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="0045b-196">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="0045b-197">В противном случае это изменение может привести к простою служб, например к отсутствию доступа к электронной почте или веб-сайту.</span><span class="sxs-lookup"><span data-stu-id="0045b-197">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="0045b-198">Например, для размещения электронной почты и веб-сайта может понадобиться выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="0045b-198">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="0045b-199">Перед изменением записей NS переместите все адреса электронной почты, которые используют ваш домен, в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0045b-199">Move all email addresses that use your domain to Microsoft 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="0045b-200">Хотите добавить домен, который в настоящее время используется с адресом веб-сайта, например www.fourthcoffee.com?</span><span class="sxs-lookup"><span data-stu-id="0045b-200">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="0045b-201">Вы можете предпринять следующие действия при добавлении домена, чтобы оставить его веб-сайт, на котором сейчас находится сайт, чтобы после изменения записей NS домена на Microsoft 365 все еще можно было доступ к веб-сайту.</span><span class="sxs-lookup"><span data-stu-id="0045b-201">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Microsoft 365.</span></span>

1. <span data-ttu-id="0045b-202">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="0045b-202">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="0045b-203">На странице **"Домены"** выберите домен и затем выберите **"Записи DNS".**</span><span class="sxs-lookup"><span data-stu-id="0045b-203">On the **Domains** page, select the domain and then choose **DNS Records**.</span></span>

3. <span data-ttu-id="0045b-204">В **области "Управление DNS"** выберите **"Пользовательские** записи" и выберите **"Новая настраиваемая запись".**</span><span class="sxs-lookup"><span data-stu-id="0045b-204">Under **Manage DNS**, select **Custom Records**, and then choose **New custom record**.</span></span>

4. <span data-ttu-id="0045b-205">Выберите тип записи DNS, которую необходимо добавить, и введите сведения о новой записи.</span><span class="sxs-lookup"><span data-stu-id="0045b-205">Select the type of DNS record you want to add, and type the information for the new record.</span></span>

5. <span data-ttu-id="0045b-206">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0045b-206">Select **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0045b-207">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="0045b-207">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="0045b-208">Затем ваша почта Майкрософт и другие службы будут настроены для работы с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="0045b-208">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
