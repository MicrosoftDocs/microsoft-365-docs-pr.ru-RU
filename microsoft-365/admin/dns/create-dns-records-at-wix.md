---
title: Создание записей DNS в WiX для Майкрософт
f1.keywords:
- NOCSH
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
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб в WiX для Майкрософт.
ms.openlocfilehash: ee236a9178092bb8fd14a9615c2ac5911b1ecc87
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645663"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a><span data-ttu-id="cbb68-103">Создание записей DNS в WiX для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="cbb68-103">Create DNS records at Wix for Microsoft</span></span>

<span data-ttu-id="cbb68-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="cbb68-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="cbb68-105">Если ваш поставщик услуг размещения DNS  Wix, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб.</span><span class="sxs-lookup"><span data-stu-id="cbb68-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="cbb68-106">Ниже перечислены основные записи, которые нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="cbb68-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="cbb68-107">[Добавление записи TXT для проверки](#add-a-txt-record-for-verification)</span><span class="sxs-lookup"><span data-stu-id="cbb68-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="cbb68-108">[Добавьте запись MX, чтобы электронная почта для вашего домена поступила в корпорацию Майкрософт](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="cbb68-108">[Add an MX record so email for your domain will come to Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span></span>
    
- <span data-ttu-id="cbb68-109">[Добавьте пять записей CNAME, необходимых для Майкрософт](#add-the-five-cname-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="cbb68-109">[Add the five CNAME records that are required for Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span></span>
    
- <span data-ttu-id="cbb68-110">[Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты](#add-a-txt-record-for-spf-to-help-prevent-email-spam)</span><span class="sxs-lookup"><span data-stu-id="cbb68-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="cbb68-111">[Добавьте две записи SRV, необходимые для Майкрософт](#add-the-two-srv-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="cbb68-111">[Add the two SRV records that are required for Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span></span>
    
<span data-ttu-id="cbb68-112">Когда вы добавите эти записи на сайте WiX, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cbb68-112">After you add these records at Wix, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="cbb68-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cbb68-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="cbb68-116">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="cbb68-116">Add a TXT record for verification</span></span>
<span data-ttu-id="cbb68-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="cbb68-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="cbb68-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="cbb68-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cbb68-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="cbb68-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 

> [!NOTE]
> <span data-ttu-id="cbb68-122">WIX не поддерживает записи DNS для поддоменов.</span><span class="sxs-lookup"><span data-stu-id="cbb68-122">WIX does not support DNS entries for subdomains.</span></span>
  
1. <span data-ttu-id="cbb68-123">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Wix по [этой ссылке](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="cbb68-123">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="cbb68-124">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="cbb68-124">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="cbb68-125">На странице **My Domains (мои домены** ) в области **Дополнительно** нажмите кнопку **изменить DNS** .</span><span class="sxs-lookup"><span data-stu-id="cbb68-125">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="cbb68-126">Нажмите кнопку **+ Добавить еще одну** строку в строке **txt (текст)** редактора DNS.</span><span class="sxs-lookup"><span data-stu-id="cbb68-126">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="cbb68-127">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="cbb68-127">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
   ||||
   |:-----|:-----|:-----|
   | <span data-ttu-id="cbb68-128">Имя узла</span><span class="sxs-lookup"><span data-stu-id="cbb68-128">Host Name</span></span> <br/> | <span data-ttu-id="cbb68-129">TXT Value</span><span class="sxs-lookup"><span data-stu-id="cbb68-129">TXT Value</span></span> <br/> | <span data-ttu-id="cbb68-130">TTL (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="cbb68-130">TTL</span></span> <br/> |
   |<span data-ttu-id="cbb68-131">Заполняется автоматически</span><span class="sxs-lookup"><span data-stu-id="cbb68-131">Automatically populated</span></span>  <br/> |<span data-ttu-id="cbb68-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="cbb68-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="cbb68-133">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="cbb68-133">**Note:** This is an example.</span></span> <span data-ttu-id="cbb68-134">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="cbb68-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="cbb68-135">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="cbb68-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="cbb68-136">1 час</span><span class="sxs-lookup"><span data-stu-id="cbb68-136">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="cbb68-137">Нажмите кнопку **Save DNS (сохранить DNS** ) в верхней части редактора DNS.</span><span class="sxs-lookup"><span data-stu-id="cbb68-137">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="cbb68-138">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="cbb68-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="cbb68-139">Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.</span><span class="sxs-lookup"><span data-stu-id="cbb68-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="cbb68-140">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="cbb68-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="cbb68-141">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="cbb68-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="cbb68-142">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="cbb68-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
3. <span data-ttu-id="cbb68-143">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="cbb68-143">On the **Setup** page, select **Start setup**.</span></span>
   
4. <span data-ttu-id="cbb68-144">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="cbb68-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cbb68-p106">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cbb68-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="cbb68-148">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cbb68-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="cbb68-149"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="cbb68-149"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="cbb68-150">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Wix по [этой ссылке](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="cbb68-150">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="cbb68-151">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="cbb68-151">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="cbb68-152">На странице **My Domains (мои домены** ) в области **почтовые ящики** выберите ссылку **Настройка записей MX** .</span><span class="sxs-lookup"><span data-stu-id="cbb68-152">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="cbb68-153">Выберите пункт **другое** из раскрывающегося списка **поставщика электронной почты** .</span><span class="sxs-lookup"><span data-stu-id="cbb68-153">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="cbb68-154">Нажмите кнопку **+ Добавить еще одну**.</span><span class="sxs-lookup"><span data-stu-id="cbb68-154">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="cbb68-155">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="cbb68-155">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="cbb68-156">Имя узла</span><span class="sxs-lookup"><span data-stu-id="cbb68-156">Host Name</span></span> | <span data-ttu-id="cbb68-157">Points to </span><span class="sxs-lookup"><span data-stu-id="cbb68-157">Points to</span></span> | <span data-ttu-id="cbb68-158">Priority (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="cbb68-158">Priority</span></span> | <span data-ttu-id="cbb68-159">TTL (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="cbb68-159">TTL</span></span> |
   |:-----|:-----|:-----|:-----|
   |<span data-ttu-id="cbb68-160">Заполняется автоматически</span><span class="sxs-lookup"><span data-stu-id="cbb68-160">Automatically populated</span></span> <br/> | <span data-ttu-id="cbb68-161">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="cbb68-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="cbb68-162">**Примечание:** Получение  *\<domain-key\>*  учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cbb68-162">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="cbb68-163">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="cbb68-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="cbb68-164">нуль</span><span class="sxs-lookup"><span data-stu-id="cbb68-164">0</span></span>  <br/> <span data-ttu-id="cbb68-165">Дополнительные сведения о приоритете см. в статье [Что такое приоритет записей MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="cbb68-165">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> | <span data-ttu-id="cbb68-166">1 час</span><span class="sxs-lookup"><span data-stu-id="cbb68-166">1 Hour</span></span>|
   
6. <span data-ttu-id="cbb68-167">Если в списке есть другие записи MX, удалите их.</span><span class="sxs-lookup"><span data-stu-id="cbb68-167">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="cbb68-168">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cbb68-168">Select **OK**.</span></span>
    
8. <span data-ttu-id="cbb68-169">В диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cbb68-169">In the confirmation dialog box, select **OK**.</span></span>
    
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="cbb68-170">Добавление пяти записей CNAME, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="cbb68-170">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="cbb68-171"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="cbb68-171"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="cbb68-p109">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Wix по [этой ссылке](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="cbb68-p109">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="cbb68-174">На странице **My Domains (мои домены** ) в области **Дополнительно** нажмите кнопку **изменить DNS** .</span><span class="sxs-lookup"><span data-stu-id="cbb68-174">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="cbb68-175">Нажмите кнопку **+ Добавить еще одну** строку **CNAME (псевдонимы)** в редакторе DNS для каждой записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="cbb68-175">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="cbb68-176">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="cbb68-176">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="cbb68-177">Имя узла</span><span class="sxs-lookup"><span data-stu-id="cbb68-177">Host Name</span></span> | <span data-ttu-id="cbb68-178">Points to </span><span class="sxs-lookup"><span data-stu-id="cbb68-178">Points to</span></span> | <span data-ttu-id="cbb68-179">TTL</span><span class="sxs-lookup"><span data-stu-id="cbb68-179">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="cbb68-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="cbb68-180">autodiscover</span></span>  <br/> |<span data-ttu-id="cbb68-181">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="cbb68-181">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="cbb68-182">1 час</span><span class="sxs-lookup"><span data-stu-id="cbb68-182">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="cbb68-183">sip</span><span class="sxs-lookup"><span data-stu-id="cbb68-183">sip</span></span>  <br/> |<span data-ttu-id="cbb68-184">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cbb68-184">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="cbb68-185">1 час</span><span class="sxs-lookup"><span data-stu-id="cbb68-185">1 Hour</span></span> <br/> |
   |<span data-ttu-id="cbb68-186">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="cbb68-186">lyncdiscover</span></span>  <br/> |<span data-ttu-id="cbb68-187">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cbb68-187">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="cbb68-188">1 час</span><span class="sxs-lookup"><span data-stu-id="cbb68-188">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="cbb68-189">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="cbb68-189">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="cbb68-190">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="cbb68-190">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="cbb68-191">1 час</span><span class="sxs-lookup"><span data-stu-id="cbb68-191">1 Hour</span></span> <br/> |
   |<span data-ttu-id="cbb68-192">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="cbb68-192">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="cbb68-193">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cbb68-193">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="cbb68-194">1 Hour</span><span class="sxs-lookup"><span data-stu-id="cbb68-194">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="cbb68-195">Нажмите кнопку **Save DNS (сохранить DNS** ) в верхней части редактора DNS.</span><span class="sxs-lookup"><span data-stu-id="cbb68-195">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="cbb68-196">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="cbb68-196">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="cbb68-197">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="cbb68-197">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="cbb68-198"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="cbb68-198"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="cbb68-199">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="cbb68-199">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="cbb68-200">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="cbb68-200">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="cbb68-201">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cbb68-201">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="cbb68-202">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь  *одну*  запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="cbb68-202">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="cbb68-203">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Wix по [этой ссылке](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="cbb68-203">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="cbb68-204">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="cbb68-204">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="cbb68-205">На странице **My Domains (мои домены** ) в области **Дополнительно** нажмите кнопку **изменить DNS** .</span><span class="sxs-lookup"><span data-stu-id="cbb68-205">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="cbb68-206">Нажмите кнопку **+ Добавить еще одну** строку в строке **txt (текст)** редактора DNS.</span><span class="sxs-lookup"><span data-stu-id="cbb68-206">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="cbb68-207">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="cbb68-207">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="cbb68-208">Имя узла</span><span class="sxs-lookup"><span data-stu-id="cbb68-208">Host Name</span></span> | <span data-ttu-id="cbb68-209">TXT Value</span><span class="sxs-lookup"><span data-stu-id="cbb68-209">TXT Value</span></span> | <span data-ttu-id="cbb68-210">TTL (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="cbb68-210">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="cbb68-211">[оставьте это поле пустым]</span><span class="sxs-lookup"><span data-stu-id="cbb68-211">[leave this blank]</span></span>  <br/> |<span data-ttu-id="cbb68-212">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="cbb68-212">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="cbb68-213">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="cbb68-213">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="cbb68-214">TXT</span><span class="sxs-lookup"><span data-stu-id="cbb68-214">TXT</span></span>  <br/> | <span data-ttu-id="cbb68-215">1 Hour</span><span class="sxs-lookup"><span data-stu-id="cbb68-215">1 Hour</span></span> |
   
5. <span data-ttu-id="cbb68-216">Нажмите кнопку **Save DNS (сохранить DNS** ) в верхней части редактора DNS.</span><span class="sxs-lookup"><span data-stu-id="cbb68-216">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="cbb68-217">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="cbb68-217">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="cbb68-218">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="cbb68-218">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="cbb68-219"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="cbb68-219"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="cbb68-220">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Wix по [этой ссылке](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="cbb68-220">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="cbb68-221">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="cbb68-221">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="cbb68-222">На странице **My Domains (мои домены** ) в области **Дополнительно** нажмите кнопку **изменить DNS** .</span><span class="sxs-lookup"><span data-stu-id="cbb68-222">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="cbb68-223">Нажмите кнопку **+ Добавить еще один** в строке **SRV** редактора DNS.</span><span class="sxs-lookup"><span data-stu-id="cbb68-223">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="cbb68-224">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="cbb68-224">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="cbb68-225">Служба</span><span class="sxs-lookup"><span data-stu-id="cbb68-225">Service</span></span> | <span data-ttu-id="cbb68-226">Протокол</span><span class="sxs-lookup"><span data-stu-id="cbb68-226">Protocol</span></span> | <span data-ttu-id="cbb68-227">Имя</span><span class="sxs-lookup"><span data-stu-id="cbb68-227">Name</span></span> | <span data-ttu-id="cbb68-228">Насыщенность</span><span class="sxs-lookup"><span data-stu-id="cbb68-228">Weight</span></span> | <span data-ttu-id="cbb68-229">Порт</span><span class="sxs-lookup"><span data-stu-id="cbb68-229">Port</span></span> | <span data-ttu-id="cbb68-230">Target</span><span class="sxs-lookup"><span data-stu-id="cbb68-230">Target</span></span> | <span data-ttu-id="cbb68-231">Priority (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="cbb68-231">Priority</span></span> | <span data-ttu-id="cbb68-232">TTL (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="cbb68-232">TTL</span></span> |
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |<span data-ttu-id="cbb68-233">sip</span><span class="sxs-lookup"><span data-stu-id="cbb68-233">sip</span></span>  |<span data-ttu-id="cbb68-234">tls</span><span class="sxs-lookup"><span data-stu-id="cbb68-234">tls</span></span>  |<span data-ttu-id="cbb68-235">Заполняется автоматически</span><span class="sxs-lookup"><span data-stu-id="cbb68-235">Automatically populated</span></span> |<span data-ttu-id="cbb68-236">1,1</span><span class="sxs-lookup"><span data-stu-id="cbb68-236">1</span></span>  |<span data-ttu-id="cbb68-237">443</span><span class="sxs-lookup"><span data-stu-id="cbb68-237">443</span></span>   |<span data-ttu-id="cbb68-238">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cbb68-238">sipdir.online.lync.com</span></span> |<span data-ttu-id="cbb68-239">100</span><span class="sxs-lookup"><span data-stu-id="cbb68-239">100</span></span> |<span data-ttu-id="cbb68-240">1 Hour</span><span class="sxs-lookup"><span data-stu-id="cbb68-240">1 Hour</span></span> |
   |<span data-ttu-id="cbb68-241">sipfed</span><span class="sxs-lookup"><span data-stu-id="cbb68-241">sipfed</span></span>|<span data-ttu-id="cbb68-242">tcp</span><span class="sxs-lookup"><span data-stu-id="cbb68-242">tcp</span></span> |<span data-ttu-id="cbb68-243">Заполняется автоматически</span><span class="sxs-lookup"><span data-stu-id="cbb68-243">Automatically populated</span></span>|<span data-ttu-id="cbb68-244">1,1</span><span class="sxs-lookup"><span data-stu-id="cbb68-244">1</span></span> |<span data-ttu-id="cbb68-245">5061</span><span class="sxs-lookup"><span data-stu-id="cbb68-245">5061</span></span> |<span data-ttu-id="cbb68-246">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cbb68-246">sipfed.online.lync.com</span></span>|<span data-ttu-id="cbb68-247">100</span><span class="sxs-lookup"><span data-stu-id="cbb68-247">100</span></span> | <span data-ttu-id="cbb68-248">1 Hour</span><span class="sxs-lookup"><span data-stu-id="cbb68-248">1 Hour</span></span> |
   
5. <span data-ttu-id="cbb68-249">Нажмите кнопку **Save DNS (сохранить DNS** ) в верхней части редактора DNS.</span><span class="sxs-lookup"><span data-stu-id="cbb68-249">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="cbb68-250">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="cbb68-250">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cbb68-p113">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cbb68-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
