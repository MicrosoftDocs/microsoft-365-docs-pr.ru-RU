---
title: Создание записей DNS для Майкрософт на сайте Wix
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
description: Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Wix for Microsoft.
ms.openlocfilehash: 01317f7e2da87b532c93f12269fd65b7d4fe2dd6
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656883"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a><span data-ttu-id="3c1d6-103">Создание записей DNS для Майкрософт на сайте Wix</span><span class="sxs-lookup"><span data-stu-id="3c1d6-103">Create DNS records at Wix for Microsoft</span></span>

<span data-ttu-id="3c1d6-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="3c1d6-105">Если ваш поставщик услуг размещения DNS  Wix, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="3c1d6-106">Ниже перечислены основные записи, которые нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="3c1d6-107">[Добавление записи TXT для проверки](#add-a-txt-record-for-verification)</span><span class="sxs-lookup"><span data-stu-id="3c1d6-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="3c1d6-108">[Добавьте запись MX, чтобы электронная почта для вашего домена была отправлена в корпорацию Майкрософт.](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="3c1d6-108">[Add an MX record so email for your domain will come to Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span></span>
    
- <span data-ttu-id="3c1d6-109">[Добавьте пять записей CNAME, необходимых для Майкрософт.](#add-the-five-cname-records-that-are-required-for-microsoft)</span><span class="sxs-lookup"><span data-stu-id="3c1d6-109">[Add the five CNAME records that are required for Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span></span>
    
- <span data-ttu-id="3c1d6-110">[Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты](#add-a-txt-record-for-spf-to-help-prevent-email-spam)</span><span class="sxs-lookup"><span data-stu-id="3c1d6-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="3c1d6-111">[Добавьте две записи SRV, необходимые для Майкрософт.](#add-the-two-srv-records-that-are-required-for-microsoft)</span><span class="sxs-lookup"><span data-stu-id="3c1d6-111">[Add the two SRV records that are required for Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span></span>
    
<span data-ttu-id="3c1d6-112">После добавления этих записей на сайте Wix ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-112">After you add these records at Wix, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="3c1d6-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3c1d6-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="3c1d6-116">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="3c1d6-116">Add a TXT record for verification</span></span>
<span data-ttu-id="3c1d6-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="3c1d6-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="3c1d6-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3c1d6-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 

> [!NOTE]
> <span data-ttu-id="3c1d6-122">WIX не поддерживает записи DNS для поддоменов.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-122">WIX does not support DNS entries for subdomains.</span></span>
  
1. <span data-ttu-id="3c1d6-123">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Wix по [этой ссылке](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="3c1d6-123">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="3c1d6-124">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-124">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="3c1d6-125">На странице **"Мои домены"** в **области** "Дополнительные" выберите кнопку **"Изменить DNS".**</span><span class="sxs-lookup"><span data-stu-id="3c1d6-125">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="3c1d6-126">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-126">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="3c1d6-127">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-127">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
   ||||
   |:-----|:-----|:-----|
   | <span data-ttu-id="3c1d6-128">Имя узла</span><span class="sxs-lookup"><span data-stu-id="3c1d6-128">Host Name</span></span> <br/> | <span data-ttu-id="3c1d6-129">TXT Value</span><span class="sxs-lookup"><span data-stu-id="3c1d6-129">TXT Value</span></span> <br/> | <span data-ttu-id="3c1d6-130">TTL (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="3c1d6-130">TTL</span></span> <br/> |
   |<span data-ttu-id="3c1d6-131">Автоматическое заполнение</span><span class="sxs-lookup"><span data-stu-id="3c1d6-131">Automatically populated</span></span>  <br/> |<span data-ttu-id="3c1d6-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="3c1d6-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="3c1d6-133">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-133">**Note:** This is an example.</span></span> <span data-ttu-id="3c1d6-134">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="3c1d6-135">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="3c1d6-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="3c1d6-136">1 час</span><span class="sxs-lookup"><span data-stu-id="3c1d6-136">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="3c1d6-137">В **верхней части редактора DNS** выберите кнопку "Сохранить DNS".</span><span class="sxs-lookup"><span data-stu-id="3c1d6-137">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="3c1d6-138">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="3c1d6-139">Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="3c1d6-140">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="3c1d6-141">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="3c1d6-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="3c1d6-142">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
3. <span data-ttu-id="3c1d6-143">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="3c1d6-143">On the **Setup** page, select **Start setup**.</span></span>
   
4. <span data-ttu-id="3c1d6-144">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3c1d6-p106">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3c1d6-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="3c1d6-148">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="3c1d6-149"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="3c1d6-149"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="3c1d6-150">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Wix по [этой ссылке](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="3c1d6-150">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="3c1d6-151">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-151">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="3c1d6-152">На странице **"Мои домены"** в области "Почтовые ящики" выберите ссылку "Настройка **записей MX".** </span><span class="sxs-lookup"><span data-stu-id="3c1d6-152">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="3c1d6-153">Choose **Other** from the **Your Email Provider** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-153">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="3c1d6-154">Select **+ Add another**.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-154">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="3c1d6-155">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-155">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="3c1d6-156">Имя узла</span><span class="sxs-lookup"><span data-stu-id="3c1d6-156">Host Name</span></span> | <span data-ttu-id="3c1d6-157">Points to </span><span class="sxs-lookup"><span data-stu-id="3c1d6-157">Points to</span></span> | <span data-ttu-id="3c1d6-158">Priority (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="3c1d6-158">Priority</span></span> | <span data-ttu-id="3c1d6-159">TTL (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="3c1d6-159">TTL</span></span> |
   |:-----|:-----|:-----|:-----|
   |<span data-ttu-id="3c1d6-160">Автоматическое заполнение</span><span class="sxs-lookup"><span data-stu-id="3c1d6-160">Automatically populated</span></span> <br/> | <span data-ttu-id="3c1d6-161">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="3c1d6-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="3c1d6-162">**Примечание.** Получите свою  *\<domain-key\>*  учетную запись Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-162">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="3c1d6-163">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="3c1d6-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="3c1d6-164">0</span><span class="sxs-lookup"><span data-stu-id="3c1d6-164">0</span></span>  <br/> <span data-ttu-id="3c1d6-165">Дополнительные сведения о приоритете см. в статье [Что такое приоритет записей MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="3c1d6-165">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> | <span data-ttu-id="3c1d6-166">1 час</span><span class="sxs-lookup"><span data-stu-id="3c1d6-166">1 Hour</span></span>|
   
6. <span data-ttu-id="3c1d6-167">Если в списке есть какие-либо другие записи MX, удалите каждую из них.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-167">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="3c1d6-168">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-168">Select **OK**.</span></span>
    
8. <span data-ttu-id="3c1d6-169">В диалоговом окне подтверждения выберите **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="3c1d6-169">In the confirmation dialog box, select **OK**.</span></span>
    
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="3c1d6-170">Добавление пяти записей CNAME, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3c1d6-170">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="3c1d6-171"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="3c1d6-171"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="3c1d6-p109">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Wix по [этой ссылке](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-p109">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="3c1d6-174">На странице **"Мои домены"** в **области** "Дополнительные" выберите кнопку **"Изменить DNS".**</span><span class="sxs-lookup"><span data-stu-id="3c1d6-174">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="3c1d6-175">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-175">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="3c1d6-176">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-176">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="3c1d6-177">Имя узла</span><span class="sxs-lookup"><span data-stu-id="3c1d6-177">Host Name</span></span> | <span data-ttu-id="3c1d6-178">Points to </span><span class="sxs-lookup"><span data-stu-id="3c1d6-178">Points to</span></span> | <span data-ttu-id="3c1d6-179">TTL</span><span class="sxs-lookup"><span data-stu-id="3c1d6-179">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="3c1d6-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="3c1d6-180">autodiscover</span></span>  <br/> |<span data-ttu-id="3c1d6-181">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="3c1d6-181">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="3c1d6-182">1 час</span><span class="sxs-lookup"><span data-stu-id="3c1d6-182">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="3c1d6-183">sip</span><span class="sxs-lookup"><span data-stu-id="3c1d6-183">sip</span></span>  <br/> |<span data-ttu-id="3c1d6-184">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3c1d6-184">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="3c1d6-185">1 час</span><span class="sxs-lookup"><span data-stu-id="3c1d6-185">1 Hour</span></span> <br/> |
   |<span data-ttu-id="3c1d6-186">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3c1d6-186">lyncdiscover</span></span>  <br/> |<span data-ttu-id="3c1d6-187">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3c1d6-187">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="3c1d6-188">1 час</span><span class="sxs-lookup"><span data-stu-id="3c1d6-188">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="3c1d6-189">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="3c1d6-189">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="3c1d6-190">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="3c1d6-190">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="3c1d6-191">1 час</span><span class="sxs-lookup"><span data-stu-id="3c1d6-191">1 Hour</span></span> <br/> |
   |<span data-ttu-id="3c1d6-192">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="3c1d6-192">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="3c1d6-193">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3c1d6-193">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="3c1d6-194">1 Hour</span><span class="sxs-lookup"><span data-stu-id="3c1d6-194">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="3c1d6-195">В **верхней части редактора DNS** выберите кнопку "Сохранить DNS".</span><span class="sxs-lookup"><span data-stu-id="3c1d6-195">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="3c1d6-196">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-196">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="3c1d6-197">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="3c1d6-197">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="3c1d6-198"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="3c1d6-198"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="3c1d6-199">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-199">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="3c1d6-200">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-200">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="3c1d6-201">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-201">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="3c1d6-202">Вместо этого добавьте необходимые значения Майкрософт в текущую  запись, чтобы иметь одну запись SPF, которая включает оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-202">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="3c1d6-203">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Wix по [этой ссылке](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="3c1d6-203">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="3c1d6-204">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-204">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="3c1d6-205">На странице **"Мои домены"** в **области** "Дополнительные" выберите кнопку **"Изменить DNS".**</span><span class="sxs-lookup"><span data-stu-id="3c1d6-205">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="3c1d6-206">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-206">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="3c1d6-207">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-207">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="3c1d6-208">Имя узла</span><span class="sxs-lookup"><span data-stu-id="3c1d6-208">Host Name</span></span> | <span data-ttu-id="3c1d6-209">TXT Value</span><span class="sxs-lookup"><span data-stu-id="3c1d6-209">TXT Value</span></span> | <span data-ttu-id="3c1d6-210">TTL (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="3c1d6-210">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="3c1d6-211">[оставьте это пустым]</span><span class="sxs-lookup"><span data-stu-id="3c1d6-211">[leave this blank]</span></span>  <br/> |<span data-ttu-id="3c1d6-212">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="3c1d6-212">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="3c1d6-213">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="3c1d6-213">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="3c1d6-214">TXT</span><span class="sxs-lookup"><span data-stu-id="3c1d6-214">TXT</span></span>  <br/> | <span data-ttu-id="3c1d6-215">1 Hour</span><span class="sxs-lookup"><span data-stu-id="3c1d6-215">1 Hour</span></span> |
   
5. <span data-ttu-id="3c1d6-216">В **верхней части редактора DNS** выберите кнопку "Сохранить DNS".</span><span class="sxs-lookup"><span data-stu-id="3c1d6-216">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="3c1d6-217">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-217">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="3c1d6-218">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3c1d6-218">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="3c1d6-219"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="3c1d6-219"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="3c1d6-220">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Wix по [этой ссылке](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="3c1d6-220">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="3c1d6-221">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-221">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="3c1d6-222">На странице **"Мои домены"** в **области** "Дополнительные" выберите кнопку **"Изменить DNS".**</span><span class="sxs-lookup"><span data-stu-id="3c1d6-222">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="3c1d6-223">Select **+ Add another** in the **SRV** row of the DNS editor.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-223">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="3c1d6-224">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-224">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="3c1d6-225">Служба</span><span class="sxs-lookup"><span data-stu-id="3c1d6-225">Service</span></span> | <span data-ttu-id="3c1d6-226">Протокол</span><span class="sxs-lookup"><span data-stu-id="3c1d6-226">Protocol</span></span> | <span data-ttu-id="3c1d6-227">Имя</span><span class="sxs-lookup"><span data-stu-id="3c1d6-227">Name</span></span> | <span data-ttu-id="3c1d6-228">Насыщенность</span><span class="sxs-lookup"><span data-stu-id="3c1d6-228">Weight</span></span> | <span data-ttu-id="3c1d6-229">Порт</span><span class="sxs-lookup"><span data-stu-id="3c1d6-229">Port</span></span> | <span data-ttu-id="3c1d6-230">Target</span><span class="sxs-lookup"><span data-stu-id="3c1d6-230">Target</span></span> | <span data-ttu-id="3c1d6-231">Priority (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="3c1d6-231">Priority</span></span> | <span data-ttu-id="3c1d6-232">TTL (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="3c1d6-232">TTL</span></span> |
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |<span data-ttu-id="3c1d6-233">sip</span><span class="sxs-lookup"><span data-stu-id="3c1d6-233">sip</span></span>  |<span data-ttu-id="3c1d6-234">tls</span><span class="sxs-lookup"><span data-stu-id="3c1d6-234">tls</span></span>  |<span data-ttu-id="3c1d6-235">Автоматическое заполнение</span><span class="sxs-lookup"><span data-stu-id="3c1d6-235">Automatically populated</span></span> |<span data-ttu-id="3c1d6-236">1 </span><span class="sxs-lookup"><span data-stu-id="3c1d6-236">1</span></span>  |<span data-ttu-id="3c1d6-237">443</span><span class="sxs-lookup"><span data-stu-id="3c1d6-237">443</span></span>   |<span data-ttu-id="3c1d6-238">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3c1d6-238">sipdir.online.lync.com</span></span> |<span data-ttu-id="3c1d6-239">100</span><span class="sxs-lookup"><span data-stu-id="3c1d6-239">100</span></span> |<span data-ttu-id="3c1d6-240">1 Hour</span><span class="sxs-lookup"><span data-stu-id="3c1d6-240">1 Hour</span></span> |
   |<span data-ttu-id="3c1d6-241">sipfed</span><span class="sxs-lookup"><span data-stu-id="3c1d6-241">sipfed</span></span>|<span data-ttu-id="3c1d6-242">tcp</span><span class="sxs-lookup"><span data-stu-id="3c1d6-242">tcp</span></span> |<span data-ttu-id="3c1d6-243">Автоматическое заполнение</span><span class="sxs-lookup"><span data-stu-id="3c1d6-243">Automatically populated</span></span>|<span data-ttu-id="3c1d6-244">1 </span><span class="sxs-lookup"><span data-stu-id="3c1d6-244">1</span></span> |<span data-ttu-id="3c1d6-245">5061</span><span class="sxs-lookup"><span data-stu-id="3c1d6-245">5061</span></span> |<span data-ttu-id="3c1d6-246">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3c1d6-246">sipfed.online.lync.com</span></span>|<span data-ttu-id="3c1d6-247">100</span><span class="sxs-lookup"><span data-stu-id="3c1d6-247">100</span></span> | <span data-ttu-id="3c1d6-248">1 Hour</span><span class="sxs-lookup"><span data-stu-id="3c1d6-248">1 Hour</span></span> |
   
5. <span data-ttu-id="3c1d6-249">В **верхней части редактора DNS** выберите кнопку "Сохранить DNS".</span><span class="sxs-lookup"><span data-stu-id="3c1d6-249">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="3c1d6-250">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="3c1d6-250">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3c1d6-p113">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3c1d6-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
