---
title: Создание записей DNS в WiX для Майкрософт
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб в WiX для Майкрософт.
ms.openlocfilehash: b5fe216e65954bbcbdd9a1da223258a8362743ca
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400296"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a><span data-ttu-id="d03e4-103">Создание записей DNS в WiX для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d03e4-103">Create DNS records at Wix for Microsoft</span></span>

 <span data-ttu-id="d03e4-104">Если вы не нашли то, что вы ищете, обратитесь к разделу **[вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="d03e4-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d03e4-105">Если ваш поставщик услуг размещения DNS  Wix, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб.</span><span class="sxs-lookup"><span data-stu-id="d03e4-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="d03e4-106">Ниже перечислены основные записи, которые нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="d03e4-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="d03e4-107">[Добавление записи TXT для проверки](#add-a-txt-record-for-verification)</span><span class="sxs-lookup"><span data-stu-id="d03e4-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="d03e4-108">[Добавьте запись MX, чтобы электронная почта для вашего домена поступила в корпорацию Майкрософт](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="d03e4-108">[Add an MX record so email for your domain will come to Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span></span>
    
- <span data-ttu-id="d03e4-109">[Добавьте пять записей CNAME, необходимых для Майкрософт](#add-the-five-cname-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="d03e4-109">[Add the five CNAME records that are required for Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span></span>
    
- <span data-ttu-id="d03e4-110">[Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты](#add-a-txt-record-for-spf-to-help-prevent-email-spam)</span><span class="sxs-lookup"><span data-stu-id="d03e4-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="d03e4-111">[Добавьте две записи SRV, необходимые для Майкрософт](#add-the-two-srv-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="d03e4-111">[Add the two SRV records that are required for Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span></span>
    
<span data-ttu-id="d03e4-112">Когда вы добавите эти записи на сайте WiX, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d03e4-112">After you add these records at Wix, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="d03e4-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d03e4-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d03e4-116">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="d03e4-116">Add a TXT record for verification</span></span>
<span data-ttu-id="d03e4-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="d03e4-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="d03e4-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="d03e4-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d03e4-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="d03e4-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="d03e4-122">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Wix по [этой ссылке](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="d03e4-122">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="d03e4-123">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="d03e4-123">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d03e4-124">На странице **My Domains (мои домены** ) в области **Дополнительно** нажмите кнопку **изменить DNS** .</span><span class="sxs-lookup"><span data-stu-id="d03e4-124">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="d03e4-125">Нажмите кнопку **+ Добавить еще одну** строку в строке **txt (текст)** редактора DNS.</span><span class="sxs-lookup"><span data-stu-id="d03e4-125">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="d03e4-126">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d03e4-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="d03e4-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="d03e4-127">**Host Name**</span></span> <br/> |<span data-ttu-id="d03e4-128">**TXT Value** (Значение TXT)</span><span class="sxs-lookup"><span data-stu-id="d03e4-128">**TXT Value**</span></span> <br/> |<span data-ttu-id="d03e4-129">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="d03e4-129">**TTL**</span></span> <br/> |
|<span data-ttu-id="d03e4-130">Заполняется автоматически</span><span class="sxs-lookup"><span data-stu-id="d03e4-130">Automatically populated</span></span>  <br/> |<span data-ttu-id="d03e4-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d03e4-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="d03e4-132">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="d03e4-132">**Note:** This is an example.</span></span> <span data-ttu-id="d03e4-133">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="d03e4-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="d03e4-134">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="d03e4-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="d03e4-135">1 час</span><span class="sxs-lookup"><span data-stu-id="d03e4-135">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="d03e4-136">Нажмите кнопку **Save DNS (сохранить DNS** ) в верхней части редактора DNS.</span><span class="sxs-lookup"><span data-stu-id="d03e4-136">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="d03e4-137">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="d03e4-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d03e4-138">Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.</span><span class="sxs-lookup"><span data-stu-id="d03e4-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="d03e4-139">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="d03e4-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d03e4-140">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="d03e4-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="d03e4-141">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="d03e4-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
  
3. <span data-ttu-id="d03e4-142">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="d03e4-142">On the **Setup** page, select **Start setup**.</span></span>
   
  
4. <span data-ttu-id="d03e4-143">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="d03e4-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="d03e4-p106">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d03e4-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="d03e4-147">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d03e4-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="d03e4-148"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="d03e4-148"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="d03e4-149">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Wix по [этой ссылке](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="d03e4-149">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="d03e4-150">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="d03e4-150">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d03e4-151">На странице **My Domains (мои домены** ) в области **почтовые ящики** выберите ссылку **Настройка записей MX** .</span><span class="sxs-lookup"><span data-stu-id="d03e4-151">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="d03e4-152">Выберите пункт **другое** из раскрывающегося списка **поставщика электронной почты** .</span><span class="sxs-lookup"><span data-stu-id="d03e4-152">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="d03e4-153">Нажмите кнопку **+ Добавить еще одну**.</span><span class="sxs-lookup"><span data-stu-id="d03e4-153">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="d03e4-154">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="d03e4-154">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="d03e4-155">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="d03e4-155">**Host Name**</span></span>|<span data-ttu-id="d03e4-156">**Points to (Указывает на)**</span><span class="sxs-lookup"><span data-stu-id="d03e4-156">**Points to**</span></span>|<span data-ttu-id="d03e4-157">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="d03e4-157">**Priority**</span></span>|<span data-ttu-id="d03e4-158">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="d03e4-158">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d03e4-159">Заполняется автоматически</span><span class="sxs-lookup"><span data-stu-id="d03e4-159">Automatically populated</span></span> <br/> | <span data-ttu-id="d03e4-160">*\<domain-key\>*. mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d03e4-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="d03e4-161">**Примечание:** Получение *\<domain-key\>* учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d03e4-161">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="d03e4-162">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="d03e4-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="d03e4-163">нуль</span><span class="sxs-lookup"><span data-stu-id="d03e4-163">0</span></span>  <br/> <span data-ttu-id="d03e4-164">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="d03e4-164">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> | <span data-ttu-id="d03e4-165">1 Hour</span><span class="sxs-lookup"><span data-stu-id="d03e4-165">1 Hour</span></span>|
   
6. <span data-ttu-id="d03e4-166">Если в списке есть другие записи MX, удалите их.</span><span class="sxs-lookup"><span data-stu-id="d03e4-166">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="d03e4-167">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d03e4-167">Select **OK**.</span></span>
    
8. <span data-ttu-id="d03e4-168">В диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d03e4-168">In the confirmation dialog box, select **OK**.</span></span>
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="d03e4-169">Добавление пяти записей CNAME, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d03e4-169">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="d03e4-170"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="d03e4-170"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="d03e4-p109">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Wix по [этой ссылке](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="d03e4-p109">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="d03e4-173">На странице **My Domains (мои домены** ) в области **Дополнительно** нажмите кнопку **изменить DNS** .</span><span class="sxs-lookup"><span data-stu-id="d03e4-173">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="d03e4-174">Нажмите кнопку **+ Добавить еще одну** строку **CNAME (псевдонимы)** в редакторе DNS для каждой записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="d03e4-174">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="d03e4-175">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="d03e4-175">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="d03e4-176">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="d03e4-176">**Host Name**</span></span>|<span data-ttu-id="d03e4-177">**Points to** (Указывает на)</span><span class="sxs-lookup"><span data-stu-id="d03e4-177">**Points to**</span></span>|<span data-ttu-id="d03e4-178">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="d03e4-178">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d03e4-179">autodiscover</span><span class="sxs-lookup"><span data-stu-id="d03e4-179">autodiscover</span></span>  <br/> |<span data-ttu-id="d03e4-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d03e4-180">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="d03e4-181">1 Hour</span><span class="sxs-lookup"><span data-stu-id="d03e4-181">1 Hour</span></span>  <br/> |
|<span data-ttu-id="d03e4-182">sip</span><span class="sxs-lookup"><span data-stu-id="d03e4-182">sip</span></span>  <br/> |<span data-ttu-id="d03e4-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d03e4-183">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="d03e4-184">1 Hour</span><span class="sxs-lookup"><span data-stu-id="d03e4-184">1 Hour</span></span> <br/> |
|<span data-ttu-id="d03e4-185">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d03e4-185">lyncdiscover</span></span>  <br/> |<span data-ttu-id="d03e4-186">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d03e4-186">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="d03e4-187">1 Hour</span><span class="sxs-lookup"><span data-stu-id="d03e4-187">1 Hour</span></span>  <br/> |
|<span data-ttu-id="d03e4-188">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="d03e4-188">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="d03e4-189">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="d03e4-189">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="d03e4-190">1 Hour</span><span class="sxs-lookup"><span data-stu-id="d03e4-190">1 Hour</span></span> <br/> |
|<span data-ttu-id="d03e4-191">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="d03e4-191">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="d03e4-192">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d03e4-192">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="d03e4-193">1 Hour</span><span class="sxs-lookup"><span data-stu-id="d03e4-193">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="d03e4-194">Нажмите кнопку **Save DNS (сохранить DNS** ) в верхней части редактора DNS.</span><span class="sxs-lookup"><span data-stu-id="d03e4-194">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="d03e4-195">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="d03e4-195">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d03e4-196">Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама</span><span class="sxs-lookup"><span data-stu-id="d03e4-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="d03e4-197"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="d03e4-197"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d03e4-198">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="d03e4-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="d03e4-199">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="d03e4-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="d03e4-200">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d03e4-200">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="d03e4-201">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="d03e4-201">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="d03e4-202">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Wix по [этой ссылке](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="d03e4-202">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="d03e4-203">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="d03e4-203">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d03e4-204">На странице **My Domains (мои домены** ) в области **Дополнительно** нажмите кнопку **изменить DNS** .</span><span class="sxs-lookup"><span data-stu-id="d03e4-204">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="d03e4-205">Нажмите кнопку **+ Добавить еще одну** строку в строке **txt (текст)** редактора DNS.</span><span class="sxs-lookup"><span data-stu-id="d03e4-205">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="d03e4-206">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="d03e4-206">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="d03e4-207">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="d03e4-207">**Host Name**</span></span>|<span data-ttu-id="d03e4-208">**TXT Value** (Значение TXT)</span><span class="sxs-lookup"><span data-stu-id="d03e4-208">**TXT Value**</span></span>|<span data-ttu-id="d03e4-209">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="d03e4-209">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d03e4-210">[оставьте это поле пустым]</span><span class="sxs-lookup"><span data-stu-id="d03e4-210">[leave this blank]</span></span>  <br/> |<span data-ttu-id="d03e4-211">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="d03e4-211">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="d03e4-212">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="d03e4-212">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="d03e4-213">TXT</span><span class="sxs-lookup"><span data-stu-id="d03e4-213">TXT</span></span>  <br/> | <span data-ttu-id="d03e4-214">1 Hour</span><span class="sxs-lookup"><span data-stu-id="d03e4-214">1 Hour</span></span> |
   
5. <span data-ttu-id="d03e4-215">Нажмите кнопку **Save DNS (сохранить DNS** ) в верхней части редактора DNS.</span><span class="sxs-lookup"><span data-stu-id="d03e4-215">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="d03e4-216">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="d03e4-216">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="d03e4-217">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d03e4-217">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="d03e4-218"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="d03e4-218"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="d03e4-219">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Wix по [этой ссылке](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="d03e4-219">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="d03e4-220">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="d03e4-220">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d03e4-221">На странице **My Domains (мои домены** ) в области **Дополнительно** нажмите кнопку **изменить DNS** .</span><span class="sxs-lookup"><span data-stu-id="d03e4-221">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="d03e4-222">Нажмите кнопку **+ Добавить еще один** в строке **SRV** редактора DNS.</span><span class="sxs-lookup"><span data-stu-id="d03e4-222">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="d03e4-223">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="d03e4-223">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="d03e4-224">**Служба**</span><span class="sxs-lookup"><span data-stu-id="d03e4-224">**Service**</span></span>|<span data-ttu-id="d03e4-225">**Protocol (Протокол)**</span><span class="sxs-lookup"><span data-stu-id="d03e4-225">**Protocol**</span></span>|<span data-ttu-id="d03e4-226">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="d03e4-226">**Name**</span></span>|<span data-ttu-id="d03e4-227">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="d03e4-227">**Weight**</span></span>|<span data-ttu-id="d03e4-228">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="d03e4-228">**Port**</span></span>|<span data-ttu-id="d03e4-229">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="d03e4-229">**Target**</span></span>|<span data-ttu-id="d03e4-230">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="d03e4-230">**Priority**</span></span>|<span data-ttu-id="d03e4-231">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="d03e4-231">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d03e4-232">sip</span><span class="sxs-lookup"><span data-stu-id="d03e4-232">sip</span></span>  |<span data-ttu-id="d03e4-233">tls</span><span class="sxs-lookup"><span data-stu-id="d03e4-233">tls</span></span>  |<span data-ttu-id="d03e4-234">Заполняется автоматически</span><span class="sxs-lookup"><span data-stu-id="d03e4-234">Automatically populated</span></span> |<span data-ttu-id="d03e4-235">1 </span><span class="sxs-lookup"><span data-stu-id="d03e4-235">1</span></span>  |<span data-ttu-id="d03e4-236">443</span><span class="sxs-lookup"><span data-stu-id="d03e4-236">443</span></span>   |<span data-ttu-id="d03e4-237">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d03e4-237">sipdir.online.lync.com</span></span> |<span data-ttu-id="d03e4-238">100</span><span class="sxs-lookup"><span data-stu-id="d03e4-238">100</span></span> |<span data-ttu-id="d03e4-239">1 Hour</span><span class="sxs-lookup"><span data-stu-id="d03e4-239">1 Hour</span></span> |
|<span data-ttu-id="d03e4-240">sipfed</span><span class="sxs-lookup"><span data-stu-id="d03e4-240">sipfed</span></span>|<span data-ttu-id="d03e4-241">tcp</span><span class="sxs-lookup"><span data-stu-id="d03e4-241">tcp</span></span> |<span data-ttu-id="d03e4-242">Заполняется автоматически</span><span class="sxs-lookup"><span data-stu-id="d03e4-242">Automatically populated</span></span>|<span data-ttu-id="d03e4-243">1 </span><span class="sxs-lookup"><span data-stu-id="d03e4-243">1</span></span> |<span data-ttu-id="d03e4-244">5061</span><span class="sxs-lookup"><span data-stu-id="d03e4-244">5061</span></span> |<span data-ttu-id="d03e4-245">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d03e4-245">sipfed.online.lync.com</span></span>|<span data-ttu-id="d03e4-246">100</span><span class="sxs-lookup"><span data-stu-id="d03e4-246">100</span></span> | <span data-ttu-id="d03e4-247">1 Hour</span><span class="sxs-lookup"><span data-stu-id="d03e4-247">1 Hour</span></span> |
   
5. <span data-ttu-id="d03e4-248">Нажмите кнопку **Save DNS (сохранить DNS** ) в верхней части редактора DNS.</span><span class="sxs-lookup"><span data-stu-id="d03e4-248">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="d03e4-249">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="d03e4-249">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="d03e4-p113">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d03e4-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

