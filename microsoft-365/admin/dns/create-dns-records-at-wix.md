---
title: Создание записей DNS для Office 365 на сайте Wix
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
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб в WiX для Office 365.
ms.openlocfilehash: 8487c49e989bf2db345ae9e6d0e2970c5eb40cb6
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211066"
---
# <a name="create-dns-records-at-wix-for-office-365"></a><span data-ttu-id="2344c-103">Создание записей DNS для Office 365 на сайте Wix</span><span class="sxs-lookup"><span data-stu-id="2344c-103">Create DNS records at Wix for Office 365</span></span>

 <span data-ttu-id="2344c-104">Если вы не нашли то, что вы ищете, обратитесь к разделу **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="2344c-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="2344c-105">Если ваш поставщик услуг размещения DNS  Wix, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб.</span><span class="sxs-lookup"><span data-stu-id="2344c-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="2344c-106">Ниже перечислены основные записи, которые нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="2344c-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="2344c-107">[Добавление записи TXT для проверки](#add-a-txt-record-for-verification)</span><span class="sxs-lookup"><span data-stu-id="2344c-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="2344c-108">[Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)</span><span class="sxs-lookup"><span data-stu-id="2344c-108">[Add an MX record so email for your domain will come to Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365).</span></span>
    
- <span data-ttu-id="2344c-109">[Добавьте пять записей CNAME, необходимых для Office 365](#add-the-five-cname-records-that-are-required-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="2344c-109">[Add the five CNAME records that are required for Office 365](#add-the-five-cname-records-that-are-required-for-office-365).</span></span>
    
- <span data-ttu-id="2344c-110">[Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты](#add-a-txt-record-for-spf-to-help-prevent-email-spam)</span><span class="sxs-lookup"><span data-stu-id="2344c-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="2344c-111">[Добавление двух записей SRV, необходимых для Office 365](#add-the-two-srv-records-that-are-required-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="2344c-111">[Add the two SRV records that are required for Office 365](#add-the-two-srv-records-that-are-required-for-office-365).</span></span>
    
<span data-ttu-id="2344c-112">Когда вы добавите эти записи на сайте Wix, ваш домен будет настроен для работы со службами Office 365.</span><span class="sxs-lookup"><span data-stu-id="2344c-112">After you add these records at Wix, your domain will be set up to work with Office 365 services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="2344c-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2344c-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="2344c-116">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="2344c-116">Add a TXT record for verification</span></span>
<span data-ttu-id="2344c-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="2344c-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="2344c-p102">Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="2344c-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2344c-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="2344c-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="2344c-122">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Wix по [этой ссылке](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="2344c-122">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="2344c-123">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="2344c-123">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="2344c-124">На странице **My Domains (мои домены** ) в области **Дополнительно** нажмите кнопку **изменить DNS** .</span><span class="sxs-lookup"><span data-stu-id="2344c-124">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="2344c-125">Нажмите кнопку **+ Добавить еще одну** строку в строке **txt (текст)** редактора DNS.</span><span class="sxs-lookup"><span data-stu-id="2344c-125">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="2344c-126">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="2344c-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="2344c-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="2344c-127">**Host Name**</span></span> <br/> |<span data-ttu-id="2344c-128">**TXT Value** (Значение TXT)</span><span class="sxs-lookup"><span data-stu-id="2344c-128">**TXT Value**</span></span> <br/> |<span data-ttu-id="2344c-129">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="2344c-129">**TTL**</span></span> <br/> |
|<span data-ttu-id="2344c-130">Заполняется автоматически</span><span class="sxs-lookup"><span data-stu-id="2344c-130">Automatically populated</span></span>  <br/> |<span data-ttu-id="2344c-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="2344c-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="2344c-132">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="2344c-132">**Note:** This is an example.</span></span> <span data-ttu-id="2344c-133">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="2344c-133">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>  [<span data-ttu-id="2344c-134">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="2344c-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="2344c-135">1 час</span><span class="sxs-lookup"><span data-stu-id="2344c-135">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="2344c-136">Нажмите кнопку **Save DNS (сохранить DNS** ) в верхней части редактора DNS.</span><span class="sxs-lookup"><span data-stu-id="2344c-136">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="2344c-137">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="2344c-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="2344c-138">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Office 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="2344c-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="2344c-139">Если Office 365 обнаружит правильную запись TXT, это значит, что домен проверен.</span><span class="sxs-lookup"><span data-stu-id="2344c-139">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="2344c-140">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="2344c-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="2344c-141">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="2344c-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
  
3. <span data-ttu-id="2344c-142">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="2344c-142">On the **Setup** page, select **Start setup**.</span></span>
   
  
4. <span data-ttu-id="2344c-143">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="2344c-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="2344c-p106">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2344c-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="2344c-147">Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="2344c-147">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="2344c-148"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="2344c-148"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="2344c-149">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Wix по [этой ссылке](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="2344c-149">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="2344c-150">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="2344c-150">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="2344c-151">На странице **My Domains (мои домены** ) в области **почтовые ящики** выберите ссылку **Настройка записей MX** .</span><span class="sxs-lookup"><span data-stu-id="2344c-151">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="2344c-152">Выберите пункт **другое** из раскрывающегося списка **поставщика электронной почты** .</span><span class="sxs-lookup"><span data-stu-id="2344c-152">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="2344c-153">Нажмите кнопку **+ Добавить еще одну**.</span><span class="sxs-lookup"><span data-stu-id="2344c-153">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="2344c-154">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="2344c-154">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="2344c-155">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="2344c-155">**Host Name**</span></span>|<span data-ttu-id="2344c-156">**Points to (Указывает на)**</span><span class="sxs-lookup"><span data-stu-id="2344c-156">**Points to**</span></span>|<span data-ttu-id="2344c-157">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="2344c-157">**Priority**</span></span>|<span data-ttu-id="2344c-158">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="2344c-158">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2344c-159">Заполняется автоматически</span><span class="sxs-lookup"><span data-stu-id="2344c-159">Automatically populated</span></span> <br/> | <span data-ttu-id="2344c-160">*\<ключ_домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="2344c-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="2344c-161">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Office 365.</span><span class="sxs-lookup"><span data-stu-id="2344c-161">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="2344c-162">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="2344c-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="2344c-163">нуль</span><span class="sxs-lookup"><span data-stu-id="2344c-163">0</span></span>  <br/> <span data-ttu-id="2344c-164">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83).</span><span class="sxs-lookup"><span data-stu-id="2344c-164">For more information about priority, see [What is MX priority?](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83)</span></span> | <span data-ttu-id="2344c-165">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2344c-165">1 Hour</span></span>|
   
6. <span data-ttu-id="2344c-166">Если в списке есть другие записи MX, удалите их.</span><span class="sxs-lookup"><span data-stu-id="2344c-166">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="2344c-167">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2344c-167">Select **OK**.</span></span>
    
8. <span data-ttu-id="2344c-168">В диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2344c-168">In the confirmation dialog box, select **OK**.</span></span>
    
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="2344c-169">Добавление пяти записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="2344c-169">Add the five CNAME records that are required for Office 365</span></span>
<span data-ttu-id="2344c-170"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="2344c-170"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="2344c-p109">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Wix по [этой ссылке](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="2344c-p109">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="2344c-173">На странице **My Domains (мои домены** ) в области **Дополнительно** нажмите кнопку **изменить DNS** .</span><span class="sxs-lookup"><span data-stu-id="2344c-173">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="2344c-174">Нажмите кнопку **+ Добавить еще одну** строку **CNAME (псевдонимы)** в редакторе DNS для каждой записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="2344c-174">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="2344c-175">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="2344c-175">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="2344c-176">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="2344c-176">**Host Name**</span></span>|<span data-ttu-id="2344c-177">**Points to** (Указывает на)</span><span class="sxs-lookup"><span data-stu-id="2344c-177">**Points to**</span></span>|<span data-ttu-id="2344c-178">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="2344c-178">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2344c-179">autodiscover</span><span class="sxs-lookup"><span data-stu-id="2344c-179">autodiscover</span></span>  <br/> |<span data-ttu-id="2344c-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="2344c-180">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="2344c-181">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2344c-181">1 Hour</span></span>  <br/> |
|<span data-ttu-id="2344c-182">sip</span><span class="sxs-lookup"><span data-stu-id="2344c-182">sip</span></span>  <br/> |<span data-ttu-id="2344c-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2344c-183">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="2344c-184">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2344c-184">1 Hour</span></span> <br/> |
|<span data-ttu-id="2344c-185">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="2344c-185">lyncdiscover</span></span>  <br/> |<span data-ttu-id="2344c-186">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2344c-186">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="2344c-187">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2344c-187">1 Hour</span></span>  <br/> |
|<span data-ttu-id="2344c-188">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="2344c-188">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="2344c-189">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="2344c-189">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="2344c-190">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2344c-190">1 Hour</span></span> <br/> |
|<span data-ttu-id="2344c-191">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="2344c-191">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="2344c-192">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2344c-192">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="2344c-193">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2344c-193">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="2344c-194">Нажмите кнопку **Save DNS (сохранить DNS** ) в верхней части редактора DNS.</span><span class="sxs-lookup"><span data-stu-id="2344c-194">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="2344c-195">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="2344c-195">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="2344c-196">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="2344c-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="2344c-197"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="2344c-197"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="2344c-198">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="2344c-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="2344c-199">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="2344c-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="2344c-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="2344c-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="2344c-201">Вместо этого добавьте необходимые значения Office 365 в текущую запись. Таким образом, в *одной* записи SPF будут указаны оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="2344c-201">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="2344c-202">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Wix по [этой ссылке](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="2344c-202">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="2344c-203">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="2344c-203">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="2344c-204">На странице **My Domains (мои домены** ) в области **Дополнительно** нажмите кнопку **изменить DNS** .</span><span class="sxs-lookup"><span data-stu-id="2344c-204">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="2344c-205">Нажмите кнопку **+ Добавить еще одну** строку в строке **txt (текст)** редактора DNS.</span><span class="sxs-lookup"><span data-stu-id="2344c-205">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="2344c-206">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="2344c-206">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="2344c-207">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="2344c-207">**Host Name**</span></span>|<span data-ttu-id="2344c-208">**TXT Value** (Значение TXT)</span><span class="sxs-lookup"><span data-stu-id="2344c-208">**TXT Value**</span></span>|<span data-ttu-id="2344c-209">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="2344c-209">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2344c-210">[оставьте это поле пустым]</span><span class="sxs-lookup"><span data-stu-id="2344c-210">[leave this blank]</span></span>  <br/> |<span data-ttu-id="2344c-211">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="2344c-211">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="2344c-212">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="2344c-212">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="2344c-213">TXT</span><span class="sxs-lookup"><span data-stu-id="2344c-213">TXT</span></span>  <br/> | <span data-ttu-id="2344c-214">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2344c-214">1 Hour</span></span> |
   
5. <span data-ttu-id="2344c-215">Нажмите кнопку **Save DNS (сохранить DNS** ) в верхней части редактора DNS.</span><span class="sxs-lookup"><span data-stu-id="2344c-215">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="2344c-216">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="2344c-216">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="2344c-217">Добавление двух записей SRV, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="2344c-217">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="2344c-218"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="2344c-218"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="2344c-219">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Wix по [этой ссылке](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="2344c-219">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="2344c-220">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="2344c-220">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="2344c-221">На странице **My Domains (мои домены** ) в области **Дополнительно** нажмите кнопку **изменить DNS** .</span><span class="sxs-lookup"><span data-stu-id="2344c-221">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="2344c-222">Нажмите кнопку **+ Добавить еще один** в строке **SRV** редактора DNS.</span><span class="sxs-lookup"><span data-stu-id="2344c-222">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="2344c-223">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="2344c-223">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="2344c-224">**Служба**</span><span class="sxs-lookup"><span data-stu-id="2344c-224">**Service**</span></span>|<span data-ttu-id="2344c-225">**Protocol (Протокол)**</span><span class="sxs-lookup"><span data-stu-id="2344c-225">**Protocol**</span></span>|<span data-ttu-id="2344c-226">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="2344c-226">**Name**</span></span>|<span data-ttu-id="2344c-227">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="2344c-227">**Weight**</span></span>|<span data-ttu-id="2344c-228">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="2344c-228">**Port**</span></span>|<span data-ttu-id="2344c-229">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="2344c-229">**Target**</span></span>|<span data-ttu-id="2344c-230">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="2344c-230">**Priority**</span></span>|<span data-ttu-id="2344c-231">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="2344c-231">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2344c-232">sip</span><span class="sxs-lookup"><span data-stu-id="2344c-232">sip</span></span>  |<span data-ttu-id="2344c-233">tls</span><span class="sxs-lookup"><span data-stu-id="2344c-233">tls</span></span>  |<span data-ttu-id="2344c-234">Заполняется автоматически</span><span class="sxs-lookup"><span data-stu-id="2344c-234">Automatically populated</span></span> |<span data-ttu-id="2344c-235">1,1</span><span class="sxs-lookup"><span data-stu-id="2344c-235">1</span></span>  |<span data-ttu-id="2344c-236">443</span><span class="sxs-lookup"><span data-stu-id="2344c-236">443</span></span>   |<span data-ttu-id="2344c-237">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2344c-237">sipdir.online.lync.com</span></span> |<span data-ttu-id="2344c-238">100</span><span class="sxs-lookup"><span data-stu-id="2344c-238">100</span></span> |<span data-ttu-id="2344c-239">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2344c-239">1 Hour</span></span> |
|<span data-ttu-id="2344c-240">sipfed</span><span class="sxs-lookup"><span data-stu-id="2344c-240">sipfed</span></span>|<span data-ttu-id="2344c-241">tcp</span><span class="sxs-lookup"><span data-stu-id="2344c-241">tcp</span></span> |<span data-ttu-id="2344c-242">Заполняется автоматически</span><span class="sxs-lookup"><span data-stu-id="2344c-242">Automatically populated</span></span>|<span data-ttu-id="2344c-243">1,1</span><span class="sxs-lookup"><span data-stu-id="2344c-243">1</span></span> |<span data-ttu-id="2344c-244">5061</span><span class="sxs-lookup"><span data-stu-id="2344c-244">5061</span></span> |<span data-ttu-id="2344c-245">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2344c-245">sipfed.online.lync.com</span></span>|<span data-ttu-id="2344c-246">100</span><span class="sxs-lookup"><span data-stu-id="2344c-246">100</span></span> | <span data-ttu-id="2344c-247">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2344c-247">1 Hour</span></span> |
   
5. <span data-ttu-id="2344c-248">Нажмите кнопку **Save DNS (сохранить DNS** ) в верхней части редактора DNS.</span><span class="sxs-lookup"><span data-stu-id="2344c-248">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="2344c-249">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="2344c-249">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="2344c-p113">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2344c-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

