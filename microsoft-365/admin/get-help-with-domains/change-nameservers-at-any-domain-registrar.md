---
title: Изменение серверов доменных имен для настройки Microsoft 365 с помощью любого регистратора доменных имен
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
description: Узнайте, как добавить и настроить свой домен в Microsoft 365, чтобы ваши службы, такие как электронная почта и Skype для бизнеса Online, использовали собственное доменное имя.
ms.openlocfilehash: 8f98e054b4fa9fc9c8746f2b3bec8b59eb04e767
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560345"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a><span data-ttu-id="78c4f-103">Изменение серверов доменных имен для настройки Microsoft 365 с помощью любого регистратора доменных имен</span><span class="sxs-lookup"><span data-stu-id="78c4f-103">Change nameservers to set up Microsoft 365 with any domain registrar</span></span>

 <span data-ttu-id="78c4f-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="78c4f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="78c4f-105">Сначала проверьте [настройку домена (инструкции для конкретных узлов)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) , чтобы узнать, есть ли у вас инструкции для регистратора.</span><span class="sxs-lookup"><span data-stu-id="78c4f-105">Check [Set up your domain (host-specific instructions)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) first to see if we have instructions for your registrar.</span></span> 
  
<span data-ttu-id="78c4f-106">Следуйте этим инструкциям, чтобы добавить и настроить свой домен в Microsoft 365, чтобы ваши службы, такие как электронная почта и Skype для бизнеса Online, использовали собственное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="78c4f-106">Follow these instructions to add and set up your domain in Microsoft 365 so your services like email and Skype for Business Online will use your own domain name.</span></span> <span data-ttu-id="78c4f-107">Для этого необходимо проверить домен, а затем изменить серверов доменных имен домена на Microsoft 365, чтобы можно было настроить соответствующие записи DNS.</span><span class="sxs-lookup"><span data-stu-id="78c4f-107">To do this, you'll verify your domain, and then change your domain's nameservers to Microsoft 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="78c4f-108">Выполните следующие действия, если следующие инструкции описывают ситуацию:</span><span class="sxs-lookup"><span data-stu-id="78c4f-108">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="78c4f-109">У вас есть свой домен, и вы хотите настроить его для работы с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="78c4f-109">You have your own domain and want to set it up to work with Microsoft 365.</span></span>
    
- <span data-ttu-id="78c4f-110">Вы хотите, чтобы Microsoft 365 управляла своими записями DNS.</span><span class="sxs-lookup"><span data-stu-id="78c4f-110">You want Microsoft 365 to manage your DNS records for you.</span></span> <span data-ttu-id="78c4f-111">При желании вы можете [управлять своими записями DNS самостоятельно](../setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="78c4f-111">(If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="78c4f-112">Добавьте запись TXT или MX для проверки</span><span class="sxs-lookup"><span data-stu-id="78c4f-112">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="78c4f-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="78c4f-113"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="78c4f-p103">Нужно создать только одну из этих записей. TXT является предпочтительным типом, но некоторые поставщики услуг размещения DNS не поддерживают его. В таком случае можно создать MX-запись.</span><span class="sxs-lookup"><span data-stu-id="78c4f-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="78c4f-p104">Прежде чем вы сможете использовать свой домен в Microsoft 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Microsoft 365 подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="78c4f-p104">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="78c4f-p105">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="78c4f-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="78c4f-120">Найдите область на веб-сайте поставщика услуг размещения DNS, на которой можно создать новую запись.</span><span class="sxs-lookup"><span data-stu-id="78c4f-120">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="78c4f-121">Войдите на сайт поставщика услуг размещения DNS.</span><span class="sxs-lookup"><span data-stu-id="78c4f-121">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="78c4f-122"> Выберите свой домен.</span><span class="sxs-lookup"><span data-stu-id="78c4f-122">Choose your domain.</span></span>
    
3. <span data-ttu-id="78c4f-123">Найдите страницу, на которой можно редактировать DNS-записи для домена.</span><span class="sxs-lookup"><span data-stu-id="78c4f-123">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="78c4f-124">Создание записи</span><span class="sxs-lookup"><span data-stu-id="78c4f-124">Create the record</span></span>

<span data-ttu-id="78c4f-125">При создании записи TXT или MX следуйте соответствующим инструкциям.</span><span class="sxs-lookup"><span data-stu-id="78c4f-125">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="78c4f-126">**Для создания TXT-записи используйте следующие значения:**</span><span class="sxs-lookup"><span data-stu-id="78c4f-126">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="78c4f-127">**Record Type** (Тип записи)</span><span class="sxs-lookup"><span data-stu-id="78c4f-127">**Record Type**</span></span> <br/> |<span data-ttu-id="78c4f-128">**Alias** (Псевдоним) или **Host Name** (Имя узла)</span><span class="sxs-lookup"><span data-stu-id="78c4f-128">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="78c4f-129">**Value** (Значение)</span><span class="sxs-lookup"><span data-stu-id="78c4f-129">**Value**</span></span> <br/> |<span data-ttu-id="78c4f-130">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="78c4f-130">**TTL**</span></span> <br/> |
|<span data-ttu-id="78c4f-131">TXT</span><span class="sxs-lookup"><span data-stu-id="78c4f-131">TXT</span></span>  <br/> |<span data-ttu-id="78c4f-132">Выполните одно из следующих действий: Введите **@**, оставьте поле пустым или укажите имя своего домена.</span><span class="sxs-lookup"><span data-stu-id="78c4f-132">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="78c4f-133">> [!NOTE]> У различных узлов DNS могут быть разные требования к этому полю.</span><span class="sxs-lookup"><span data-stu-id="78c4f-133">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="78c4f-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="78c4f-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="78c4f-135">> [!NOTE]> Это пример.</span><span class="sxs-lookup"><span data-stu-id="78c4f-135">> [!NOTE]> This is an example.</span></span> <span data-ttu-id="78c4f-136">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="78c4f-136">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="78c4f-137">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="78c4f-137">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="78c4f-138">Задайте для этого значения **1 hour** (1 час) или эквивалент в минутах ( **60** ), секундах ( **3600** ) и т. д.</span><span class="sxs-lookup"><span data-stu-id="78c4f-138">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="78c4f-139">**Для создания MX-записи используйте следующие значения:**</span><span class="sxs-lookup"><span data-stu-id="78c4f-139">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="78c4f-140">**Record Type** (Тип записи)</span><span class="sxs-lookup"><span data-stu-id="78c4f-140">**Record Type**</span></span>|<span data-ttu-id="78c4f-141">**Alias** (Псевдоним) или **Host Name** (Имя узла)</span><span class="sxs-lookup"><span data-stu-id="78c4f-141">**Alias** or **Host Name**</span></span>|<span data-ttu-id="78c4f-142">**Value** (Значение)</span><span class="sxs-lookup"><span data-stu-id="78c4f-142">**Value**</span></span>|<span data-ttu-id="78c4f-143">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="78c4f-143">**Priority**</span></span>|<span data-ttu-id="78c4f-144">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="78c4f-144">**TTL**</span></span>|
|<span data-ttu-id="78c4f-145">MX</span><span class="sxs-lookup"><span data-stu-id="78c4f-145">MX</span></span>|<span data-ttu-id="78c4f-146">Введите знак **@** или имя своего домена.</span><span class="sxs-lookup"><span data-stu-id="78c4f-146">Type either **@** or your domain name.</span></span> |<span data-ttu-id="78c4f-147">MS=ms *XXXXXXXX* > [!NOTE]> Это пример.</span><span class="sxs-lookup"><span data-stu-id="78c4f-147">MS=ms *XXXXXXXX* > [!NOTE]> This is an example.</span></span> <span data-ttu-id="78c4f-148">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="78c4f-148">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="78c4f-149">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="78c4f-149">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="78c4f-150">В поле **Priority** (Приоритет) используйте более низкое значение приоритета, чем указанное для других записей MX, во избежание конфликтов с записью MX, используемой для потока обработки почты.</span><span class="sxs-lookup"><span data-stu-id="78c4f-150">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="78c4f-151">Дополнительные сведения о приоритете см. в статье [Что такое приоритет записей MX?](../setup/domains-faq.md#what-is-mx-priority).</span><span class="sxs-lookup"><span data-stu-id="78c4f-151">For more information about priority, see [What is MX priority?](../setup/domains-faq.md#what-is-mx-priority)</span></span> |<span data-ttu-id="78c4f-152">Задайте для этого значения **1 hour** (1 час) или эквивалент в минутах ( **60** ), секундах ( **3600** ) и т. д.</span><span class="sxs-lookup"><span data-stu-id="78c4f-152">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="78c4f-153">Сохранение записи</span><span class="sxs-lookup"><span data-stu-id="78c4f-153">Save the record</span></span>

<span data-ttu-id="78c4f-154">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Microsoft 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="78c4f-154">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="78c4f-155">Если Microsoft 365 обнаружит правильную запись TXT, это значит, что домен проверен.</span><span class="sxs-lookup"><span data-stu-id="78c4f-155">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="78c4f-156">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="78c4f-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="78c4f-157">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="78c4f-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="78c4f-158">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="78c4f-158">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="78c4f-159">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="78c4f-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="78c4f-p109">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="78c4f-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="78c4f-163">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="78c4f-163">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="78c4f-164"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="78c4f-164"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="78c4f-165">При переходе к последнему этапу работы мастера установки доменов в Microsoft 365 остается одна из задач.</span><span class="sxs-lookup"><span data-stu-id="78c4f-165">When you get to the last step of the domains setup wizard in Microsoft 365, you have one task remaining.</span></span> <span data-ttu-id="78c4f-166">Чтобы настроить свой домен с помощью служб Microsoft 365, например электронной почты, измените записи сервера доменных имен (или записи NS) в вашем регистраторе доменных имен, чтобы они ссылались на основной и дополнительный серверов доменных имен Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="78c4f-166">To set up your domain with Microsoft 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Microsoft 365 primary and secondary nameservers.</span></span> <span data-ttu-id="78c4f-167">После этого, так как в Microsoft 365 размещается DNS, необходимые записи DNS для служб автоматически настраиваются.</span><span class="sxs-lookup"><span data-stu-id="78c4f-167">Then, because Microsoft 365 hosts your DNS, the required DNS records for your services are set up automatically for you.</span></span> <span data-ttu-id="78c4f-168">Вы можете самостоятельно обновлять записи сервера доменных имен, следуя инструкциям в разделе справки на веб-сайте регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="78c4f-168">You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website.</span></span> <span data-ttu-id="78c4f-169">Если вы еще не знакомы с DNS, обратитесь в службу поддержки регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="78c4f-169">If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="78c4f-170">Чтобы самостоятельно изменить серверы доменных имен на веб-сайте регистратора доменных имен, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="78c4f-170">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="78c4f-171">Найдите на веб-сайте регистратора домена область, в которой можно изменить серверы доменных имен для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="78c4f-171">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="78c4f-172">Создайте две записи сервера доменных имен или измените существующие так, чтобы они соответствовали указанным ниже значениям.</span><span class="sxs-lookup"><span data-stu-id="78c4f-172">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="78c4f-173">Основной сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="78c4f-173">First nameserver</span></span>  <br/> |<span data-ttu-id="78c4f-174">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="78c4f-174">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="78c4f-175">Второстепенный сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="78c4f-175">Second nameserver</span></span>  <br/> |<span data-ttu-id="78c4f-176">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="78c4f-176">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="78c4f-177">Следует использовать по крайней мере две записи серверов доменных имен.</span><span class="sxs-lookup"><span data-stu-id="78c4f-177">You should use at least two nameserver records.</span></span> <span data-ttu-id="78c4f-178">Если в списке есть другие серверов доменных имен, их можно удалить или изменить на **NS3.BDM.microsoftonline.com** и **NS4.BDM.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="78c4f-178">If there are any other nameservers listed, you can either delete them, or change them to **ns3.bdm.microsoftonline.com** and **ns4.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="78c4f-179">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="78c4f-179">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="78c4f-180">Когда вы изменяете записи NS домена так, чтобы они ссылались на Microsoft 365 серверов доменных имен, затрагиваются все службы, которые в настоящее время связаны с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="78c4f-180">When you change your domain's NS records to point to the Microsoft 365 nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="78c4f-181">Если вы пропустили какие-либо этапы работы мастера, например добавление адресов электронной почты, или используете свой домен для размещения блогов, корзин для покупок или других служб, необходимо выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="78c4f-181">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="78c4f-182">В противном случае это изменение может привести к простою служб, например к отсутствию доступа к электронной почте или веб-сайту.</span><span class="sxs-lookup"><span data-stu-id="78c4f-182">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="78c4f-183">Найдите на веб-сайте регистратора домена область, в которой можно изменить серверы доменных имен для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="78c4f-183">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="78c4f-184">Создайте две записи сервера доменных имен или измените существующие так, чтобы они соответствовали указанным ниже значениям.</span><span class="sxs-lookup"><span data-stu-id="78c4f-184">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="78c4f-185">Основной сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="78c4f-185">First nameserver</span></span>  <br/> |<span data-ttu-id="78c4f-186">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="78c4f-186">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="78c4f-187">Второстепенный сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="78c4f-187">Second nameserver</span></span>  <br/> |<span data-ttu-id="78c4f-188">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="78c4f-188">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="78c4f-189">Следует использовать по крайней мере две записи серверов доменных имен.</span><span class="sxs-lookup"><span data-stu-id="78c4f-189">You should use at least two nameserver records.</span></span> <span data-ttu-id="78c4f-190">Если в списке есть другие серверов доменных имен, их можно удалить или изменить на **NS3.DNS.Partner.microsoftonline.CN** и **NS4.DNS.Partner.microsoftonline.CN**.</span><span class="sxs-lookup"><span data-stu-id="78c4f-190">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="78c4f-191">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="78c4f-191">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="78c4f-192">Когда вы изменяете записи NS домена так, чтобы они ссылались на Office 365 под управлением 21Vianet серверов доменных имен, затрагиваются все службы, которые в настоящее время связаны с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="78c4f-192">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="78c4f-193">Если вы пропустили какие-либо этапы работы мастера, например добавление адресов электронной почты, или используете свой домен для размещения блогов, корзин для покупок или других служб, необходимо выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="78c4f-193">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="78c4f-194">В противном случае это изменение может привести к простою служб, например к отсутствию доступа к электронной почте или веб-сайту.</span><span class="sxs-lookup"><span data-stu-id="78c4f-194">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="78c4f-195">Например, для размещения электронной почты и веб-сайта может понадобиться выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="78c4f-195">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="78c4f-196">Перед изменением записей NS переместите все адреса электронной почты, которые используют ваш домен, в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="78c4f-196">Move all email addresses that use your domain to Microsoft 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="78c4f-197">Хотите добавить домен, который в настоящее время используется с адресом веб-сайта, например www.fourthcoffee.com?</span><span class="sxs-lookup"><span data-stu-id="78c4f-197">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="78c4f-198">Вы можете выполнить следующие действия, а затем добавить домен для размещения веб-сайта, на котором размещен сайт, чтобы пользователи по-прежнему могли перейти на веб-сайт после того, как вы измените записи NS домена так, чтобы они ссылались на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="78c4f-198">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Microsoft 365.</span></span>

1. <span data-ttu-id="78c4f-199">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="78c4f-199">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="78c4f-200">На странице **домены** выберите домен, а затем — **записи DNS**.</span><span class="sxs-lookup"><span data-stu-id="78c4f-200">On the **Domains** page, select the domain and then choose **DNS Records**.</span></span>

3. <span data-ttu-id="78c4f-201">В разделе **параметры DNS**выберите **Настраиваемые записи**, а затем нажмите **создать настраиваемую запись**.</span><span class="sxs-lookup"><span data-stu-id="78c4f-201">Under **DNS settings**, select **Custom Records**, and then choose **New custom record**.</span></span>

4. <span data-ttu-id="78c4f-202">Выберите тип записи DNS, которую вы хотите добавить, и введите сведения для новой записи.</span><span class="sxs-lookup"><span data-stu-id="78c4f-202">Select the type of DNS record you want to add, and type the information for the new record.</span></span>

5. <span data-ttu-id="78c4f-203">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="78c4f-203">Select **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="78c4f-204">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="78c4f-204">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="78c4f-205">После этого ваша электронная почта Майкрософт и другие службы будут настроены для работы с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="78c4f-205">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
