---
title: Изменение серверов доменных имен для настройки Office 365 у любого регистратора доменных имен
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: Узнайте, как добавить и настроить свой домен в Office 365, чтобы ваши службы, такие как электронная почта и Skype для бизнеса Online, использовали собственное доменное имя.
ms.custom: okr_smb
ms.openlocfilehash: 838025002443ec35787ea91775c60d3829545af4
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210496"
---
# <a name="change-nameservers-to-set-up-office-365-with-any-domain-registrar"></a><span data-ttu-id="63387-103">Изменение серверов доменных имен для настройки Office 365 у любого регистратора доменных имен</span><span class="sxs-lookup"><span data-stu-id="63387-103">Change nameservers to set up Office 365 with any domain registrar</span></span>

 <span data-ttu-id="63387-104">Если вы не нашли то, что вы ищете, обратитесь к разделу **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="63387-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="63387-105">Сначала проверьте [настройку домена (инструкции для конкретных узлов)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) , чтобы узнать, есть ли у вас инструкции для регистратора.</span><span class="sxs-lookup"><span data-stu-id="63387-105">Check [Set up your domain (host-specific instructions)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) first to see if we have instructions for your registrar.</span></span> 
  
<span data-ttu-id="63387-106">Вы можете добавить и настроить собственный домен в Office 365, чтобы такие службы, как электронная почта и Skype для бизнеса online, могли использовать ваше доменное имя.</span><span class="sxs-lookup"><span data-stu-id="63387-106">Follow these instructions to add and set up your domain in Office 365 so your services like email and Skype for Business Online will use your own domain name.</span></span> <span data-ttu-id="63387-107">Для этого подтвердите свой домен, а затем измените серверы доменных имен на Office 365, чтобы настроить правильные записи DNS.</span><span class="sxs-lookup"><span data-stu-id="63387-107">To do this, you'll verify your domain, and then change your domain's nameservers to Office 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="63387-108">Выполните следующие действия, если следующие инструкции описывают ситуацию:</span><span class="sxs-lookup"><span data-stu-id="63387-108">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="63387-109">У вас есть свой домен, который вы хотите настроить для работы с Office 365.</span><span class="sxs-lookup"><span data-stu-id="63387-109">You have your own domain and want to set it up to work with Office 365.</span></span>
    
- <span data-ttu-id="63387-p102">Вы хотите, чтобы служба Office 365 управляла записями DNS. При желании вы можете [управлять своими записями DNS самостоятельно](../setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="63387-p102">You want Office 365 to manage your DNS records for you. (If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="63387-112">Добавьте запись TXT или MX для проверки</span><span class="sxs-lookup"><span data-stu-id="63387-112">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="63387-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="63387-113"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="63387-p103">Нужно создать только одну из этих записей. TXT является предпочтительным типом, но некоторые поставщики услуг размещения DNS не поддерживают его. В таком случае можно создать MX-запись.</span><span class="sxs-lookup"><span data-stu-id="63387-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="63387-p104">Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="63387-p104">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="63387-p105">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="63387-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="63387-120">Найдите область на веб-сайте поставщика услуг размещения DNS, на которой можно создать новую запись.</span><span class="sxs-lookup"><span data-stu-id="63387-120">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="63387-121">Войдите на сайт поставщика услуг размещения DNS.</span><span class="sxs-lookup"><span data-stu-id="63387-121">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="63387-122"> Выберите свой домен.</span><span class="sxs-lookup"><span data-stu-id="63387-122">Choose your domain.</span></span>
    
3. <span data-ttu-id="63387-123">Найдите страницу, на которой можно редактировать DNS-записи для домена.</span><span class="sxs-lookup"><span data-stu-id="63387-123">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="63387-124">Создание записи</span><span class="sxs-lookup"><span data-stu-id="63387-124">Create the record</span></span>

<span data-ttu-id="63387-125">При создании записи TXT или MX следуйте соответствующим инструкциям.</span><span class="sxs-lookup"><span data-stu-id="63387-125">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="63387-126">**Для создания TXT-записи используйте следующие значения:**</span><span class="sxs-lookup"><span data-stu-id="63387-126">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="63387-127">**Record Type** (Тип записи)</span><span class="sxs-lookup"><span data-stu-id="63387-127">**Record Type**</span></span> <br/> |<span data-ttu-id="63387-128">**Alias** (Псевдоним) или **Host Name** (Имя узла)</span><span class="sxs-lookup"><span data-stu-id="63387-128">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="63387-129">**Value** (Значение)</span><span class="sxs-lookup"><span data-stu-id="63387-129">**Value**</span></span> <br/> |<span data-ttu-id="63387-130">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="63387-130">**TTL**</span></span> <br/> |
|<span data-ttu-id="63387-131">TXT</span><span class="sxs-lookup"><span data-stu-id="63387-131">TXT</span></span>  <br/> |<span data-ttu-id="63387-132">Выполните одно из следующих действий: Введите **@**, оставьте поле пустым или укажите имя своего домена.</span><span class="sxs-lookup"><span data-stu-id="63387-132">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="63387-133">> [!NOTE]> У различных узлов DNS могут быть разные требования к этому полю.</span><span class="sxs-lookup"><span data-stu-id="63387-133">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="63387-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="63387-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="63387-p106">> [!NOTE]> Это пример. Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.           [Как найти это значение?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="63387-p106">> [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="63387-138">Задайте для этого значения **1 hour** (1 час) или эквивалент в минутах ( **60** ), секундах ( **3600** ) и т. д.</span><span class="sxs-lookup"><span data-stu-id="63387-138">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="63387-139">**Для создания MX-записи используйте следующие значения:**</span><span class="sxs-lookup"><span data-stu-id="63387-139">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="63387-140">**Record Type** (Тип записи)</span><span class="sxs-lookup"><span data-stu-id="63387-140">**Record Type**</span></span>|<span data-ttu-id="63387-141">**Alias** (Псевдоним) или **Host Name** (Имя узла)</span><span class="sxs-lookup"><span data-stu-id="63387-141">**Alias** or **Host Name**</span></span>|<span data-ttu-id="63387-142">**Value** (Значение)</span><span class="sxs-lookup"><span data-stu-id="63387-142">**Value**</span></span>|<span data-ttu-id="63387-143">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="63387-143">**Priority**</span></span>|<span data-ttu-id="63387-144">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="63387-144">**TTL**</span></span>|
|<span data-ttu-id="63387-145">MX</span><span class="sxs-lookup"><span data-stu-id="63387-145">MX</span></span>|<span data-ttu-id="63387-146">Введите знак **@** или имя своего домена.</span><span class="sxs-lookup"><span data-stu-id="63387-146">Type either **@** or your domain name.</span></span> |<span data-ttu-id="63387-p107">MS=ms *XXXXXXXX* > [!NOTE]> Это пример. Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.           [Как найти это значение?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="63387-p107">MS=ms *XXXXXXXX* > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="63387-150">В поле **Priority** (Приоритет) используйте более низкое значение приоритета, чем указанное для других записей MX, во избежание конфликтов с записью MX, используемой для потока обработки почты.</span><span class="sxs-lookup"><span data-stu-id="63387-150">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="63387-151">Дополнительные сведения о приоритете см. в статье [Что такое приоритет записей MX?](../setup/domains-faq.md#what-is-mx-priority).</span><span class="sxs-lookup"><span data-stu-id="63387-151">For more information about priority, see [What is MX priority?](../setup/domains-faq.md#what-is-mx-priority)</span></span> |<span data-ttu-id="63387-152">Задайте для этого значения **1 hour** (1 час) или эквивалент в минутах ( **60** ), секундах ( **3600** ) и т. д.</span><span class="sxs-lookup"><span data-stu-id="63387-152">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="63387-153">Сохранение записи</span><span class="sxs-lookup"><span data-stu-id="63387-153">Save the record</span></span>

<span data-ttu-id="63387-154">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Office 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="63387-154">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="63387-155">Если Office 365 обнаружит правильную запись TXT, это значит, что домен проверен.</span><span class="sxs-lookup"><span data-stu-id="63387-155">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="63387-156">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="63387-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="63387-157">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="63387-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="63387-158">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="63387-158">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="63387-159">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="63387-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="63387-p109">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="63387-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="63387-163">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="63387-163">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="63387-164"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="63387-164"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="63387-p110">На последнем этапе работы мастера настройки домена в Office 365 остается выполнить лишь одну задачу. Чтобы настроить на своем домене службы Office 365, например почту, измените записи своего сервера доменных имен у регистратора доменных имен, чтобы они указывали на основной и второстепенный серверы имен Office 365. После этого необходимые DNS-записи ваших служб настраиваются автоматически, так как система DNS размещается в Office 365. Вы можете самостоятельно обновлять записи сервера доменных имен, следуя инструкциям в разделе справки на веб-сайте регистратора доменных имен. Если вы еще не знакомы с DNS, обратитесь в службу поддержки регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="63387-p110">When you get to the last step of the domains setup wizard in Office 365, you have one task remaining. To set up your domain with Office 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Office 365 primary and secondary nameservers. Then, because Office 365 hosts your DNS, the required DNS records for your services are set up automatically for you. You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website. If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="63387-170">Чтобы самостоятельно изменить серверы доменных имен на веб-сайте регистратора доменных имен, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="63387-170">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="63387-171">Найдите на веб-сайте регистратора домена область, в которой можно изменить серверы доменных имен для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="63387-171">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="63387-172">Создайте две записи сервера доменных имен или измените существующие так, чтобы они соответствовали указанным ниже значениям.</span><span class="sxs-lookup"><span data-stu-id="63387-172">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="63387-173">Основной сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="63387-173">First nameserver</span></span>  <br/> |<span data-ttu-id="63387-174">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="63387-174">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="63387-175">Второстепенный сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="63387-175">Second nameserver</span></span>  <br/> |<span data-ttu-id="63387-176">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="63387-176">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="63387-177">Следует использовать по крайней мере две записи серверов доменных имен.</span><span class="sxs-lookup"><span data-stu-id="63387-177">You should use at least two nameserver records.</span></span> <span data-ttu-id="63387-178">Если в списке есть другие серверов доменных имен, их можно удалить или изменить на **NS3.BDM.microsoftonline.com** и **NS4.BDM.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="63387-178">If there are any other nameservers listed, you can either delete them, or change them to **ns3.bdm.microsoftonline.com** and **ns4.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="63387-179">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="63387-179">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="63387-p112">Когда вы изменяете записи сервера доменных имен для своего домена таким образом, чтобы они указывали на серверы имен Office 365, это влияет на все службы, связанные с вашим доменом. Если вы пропустили какие-либо этапы работы мастера, например добавление адресов электронной почты, или используете свой домен для размещения блогов, корзин для покупок или других служб, необходимо выполнить дополнительные действия. В противном случае это изменение может привести к простою служб, например к отсутствию доступа к электронной почте или веб-сайту.</span><span class="sxs-lookup"><span data-stu-id="63387-p112">When you change your domain's NS records to point to the Office 365 nameservers, all the services that are currently associated with your domain are affected. If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required. Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="63387-183">Найдите на веб-сайте регистратора домена область, в которой можно изменить серверы доменных имен для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="63387-183">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="63387-184">Создайте две записи сервера доменных имен или измените существующие так, чтобы они соответствовали указанным ниже значениям.</span><span class="sxs-lookup"><span data-stu-id="63387-184">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="63387-185">Основной сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="63387-185">First nameserver</span></span>  <br/> |<span data-ttu-id="63387-186">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="63387-186">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="63387-187">Второстепенный сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="63387-187">Second nameserver</span></span>  <br/> |<span data-ttu-id="63387-188">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="63387-188">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="63387-189">Следует использовать по крайней мере две записи серверов доменных имен.</span><span class="sxs-lookup"><span data-stu-id="63387-189">You should use at least two nameserver records.</span></span> <span data-ttu-id="63387-190">Если в списке есть другие серверов доменных имен, их можно удалить или изменить на **NS3.DNS.Partner.microsoftonline.CN** и **NS4.DNS.Partner.microsoftonline.CN**.</span><span class="sxs-lookup"><span data-stu-id="63387-190">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="63387-191">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="63387-191">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="63387-192">Когда вы изменяете записи NS домена так, чтобы они ссылались на Office 365 под управлением 21Vianet серверов доменных имен, затрагиваются все службы, которые в настоящее время связаны с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="63387-192">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="63387-193">Если вы пропустили какие-либо этапы работы мастера, например добавление адресов электронной почты, или используете свой домен для размещения блогов, корзин для покупок или других служб, необходимо выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="63387-193">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="63387-194">В противном случае это изменение может привести к простою служб, например к отсутствию доступа к электронной почте или веб-сайту.</span><span class="sxs-lookup"><span data-stu-id="63387-194">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="63387-195">Например, для размещения электронной почты и веб-сайта может понадобиться выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="63387-195">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="63387-196">Перед изменением записей NS переместите все адреса электронной почты, которые используют ваш домен, в Office 365.</span><span class="sxs-lookup"><span data-stu-id="63387-196">Move all email addresses that use your domain to Office 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="63387-197">Хотите добавить домен, который в настоящее время используется с адресом веб-сайта, например www.fourthcoffee.com?</span><span class="sxs-lookup"><span data-stu-id="63387-197">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="63387-198">Вы можете выполнить следующие действия, а затем добавить домен, чтобы сохранить его веб-сайт, на котором размещен сайт, чтобы пользователи по-прежнему могли получить доступ к веб-сайту после того, как вы измените записи NS домена так, чтобы они ссылались на Office 365.</span><span class="sxs-lookup"><span data-stu-id="63387-198">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Office 365.</span></span>

1. <span data-ttu-id="63387-199">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="63387-199">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

3. <span data-ttu-id="63387-200">На странице Домены выберите домен.</span><span class="sxs-lookup"><span data-stu-id="63387-200">On the Domains page, select a domain.</span></span>

4. <span data-ttu-id="63387-201">В разделе **параметры DNS**выберите **Настраиваемые записи**, а затем нажмите **создать настраиваемую запись**.</span><span class="sxs-lookup"><span data-stu-id="63387-201">Under **DNS settings**, select **Custom Records**, and then choose **New custom record**.</span></span>

5. <span data-ttu-id="63387-202">Выберите тип записи DNS, которую вы хотите добавить, и введите сведения для новой записи.</span><span class="sxs-lookup"><span data-stu-id="63387-202">Select the type of DNS record you want to add, and type the information for the new record.</span></span>

6. <span data-ttu-id="63387-203">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="63387-203">Select **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="63387-p116">На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов. После этого ваша электронная почта и все остальные службы Office 365 будут настроены на работу с новым доменом.</span><span class="sxs-lookup"><span data-stu-id="63387-p116">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  

