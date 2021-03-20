---
title: Создание записей DNS в Names.co.uk microsoft
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
ms.assetid: b6c15128-b456-49b4-8b5e-5b823c700f26
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб в Names.co.uk Microsoft.
ms.openlocfilehash: ddd7286d983a0f180c9aefdbf5218eb9765c8669
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910046"
---
# <a name="create-dns-records-at-namescouk-for-microsoft"></a><span data-ttu-id="04d36-103">Создание записей DNS в Names.co.uk microsoft</span><span class="sxs-lookup"><span data-stu-id="04d36-103">Create DNS records at Names.co.uk for Microsoft</span></span>

 <span data-ttu-id="04d36-104">**[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="04d36-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="04d36-105">Если ваш поставщик услуг размещения DNS  Names.co.uk, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="04d36-105">If Names.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="04d36-106">После добавления этих записей в Names.co.uk домен будет настроен для работы с службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="04d36-106">After you add these records at Names.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="04d36-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="04d36-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="04d36-110">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="04d36-110">Add a TXT record for verification</span></span>
<span data-ttu-id="04d36-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="04d36-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="04d36-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="04d36-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="04d36-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="04d36-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="04d36-p104">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Names.co.uk по [этой ссылке](https://account.names.co.uk/dashboard#/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="04d36-p104">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="04d36-119">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="04d36-119">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="04d36-120">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="04d36-120">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="04d36-122">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="04d36-122">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="04d36-123">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="04d36-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="04d36-124">(Если необходимо добавить строку, выберите **ADD A/CNAME RECORDS (+)**.)</span><span class="sxs-lookup"><span data-stu-id="04d36-124">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="04d36-125">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="04d36-125">(You may have to scroll down.)</span></span>
        
    |<span data-ttu-id="04d36-126">**Host Name (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="04d36-126">**Host name**</span></span>|<span data-ttu-id="04d36-127">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="04d36-127">**Type**</span></span>|<span data-ttu-id="04d36-128">**Result (Результат)**</span><span class="sxs-lookup"><span data-stu-id="04d36-128">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="04d36-129">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="04d36-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="04d36-130">TXT</span><span class="sxs-lookup"><span data-stu-id="04d36-130">TXT</span></span>  <br/> |<span data-ttu-id="04d36-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="04d36-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="04d36-132">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="04d36-132">**Note:** This is an example.</span></span> <span data-ttu-id="04d36-133">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="04d36-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="04d36-134">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="04d36-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
       
    ![NamesUK-BP-Verify-1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. <span data-ttu-id="04d36-136">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="04d36-136">Select **Save**.</span></span>
    
    <span data-ttu-id="04d36-137">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="04d36-137">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Verify-1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. <span data-ttu-id="04d36-139">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="04d36-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="04d36-140">Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.</span><span class="sxs-lookup"><span data-stu-id="04d36-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="04d36-141">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="04d36-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="04d36-142">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="04d36-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="04d36-143">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="04d36-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="04d36-144">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="04d36-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="04d36-145">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="04d36-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="04d36-p106">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="04d36-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="04d36-149">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="04d36-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="04d36-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="04d36-150"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="04d36-p107">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Names.co.uk по [этой ссылке](https://account.names.co.uk/dashboard#/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="04d36-p107">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="04d36-154">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="04d36-154">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="04d36-155">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="04d36-155">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="04d36-157">На странице **Add/Modify DNS Zone** (Добавить/изменить зону DNS) в разделе **Mail exchange records** (Записи обмена электронной почтой) в поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="04d36-157">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="04d36-158">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="04d36-158">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="04d36-159">**Host Name (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="04d36-159">**Host name**</span></span>|<span data-ttu-id="04d36-160">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="04d36-160">**Priority**</span></span>|<span data-ttu-id="04d36-161">**Result (Результат)**</span><span class="sxs-lookup"><span data-stu-id="04d36-161">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="04d36-162">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="04d36-162">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="04d36-163">1</span><span class="sxs-lookup"><span data-stu-id="04d36-163">1</span></span>  <br/> <span data-ttu-id="04d36-164">Дополнительные сведения о приоритете см. в статье [Что такое приоритет записей MX?](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="04d36-164">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> | <span data-ttu-id="04d36-165">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="04d36-165">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="04d36-166">> [!NOTE]> получите из  *\<domain-key\>*  учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="04d36-166">> [!NOTE]> Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="04d36-167">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="04d36-167">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![NamesUK-BP-Configure-2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. <span data-ttu-id="04d36-169">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="04d36-169">Select **Save**.</span></span>
    
    <span data-ttu-id="04d36-170">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="04d36-170">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. <span data-ttu-id="04d36-172">Если в разделе **Mail exchange records** (Записи обмена электронной почтой) есть какие-либо другие записи MX, удалите каждую из них, выделив ее и нажав на клавиатуре клавишу **DELETE**.</span><span class="sxs-lookup"><span data-stu-id="04d36-172">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![NamesUK-BP-Configure-2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. <span data-ttu-id="04d36-174">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="04d36-174">Select **Save**.</span></span>
    
    <span data-ttu-id="04d36-175">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="04d36-175">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="04d36-177">Добавление шести записей CNAME, необходимых для Корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="04d36-177">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="04d36-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="04d36-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="04d36-p109">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Names.co.uk по [этой ссылке](https://account.names.co.uk/dashboard#/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="04d36-p109">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="04d36-182">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="04d36-182">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="04d36-183">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="04d36-183">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="04d36-185">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="04d36-185">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="04d36-186">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="04d36-186">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="04d36-187">(Если необходимо добавить строку, выберите **ADD A/CNAME RECORDS (+)**.)</span><span class="sxs-lookup"><span data-stu-id="04d36-187">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="04d36-188">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="04d36-188">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="04d36-189">**Host Name (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="04d36-189">**Host Name**</span></span>|<span data-ttu-id="04d36-190">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="04d36-190">**Type**</span></span>|<span data-ttu-id="04d36-191">**Result (Результат)**</span><span class="sxs-lookup"><span data-stu-id="04d36-191">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="04d36-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="04d36-192">autodiscover</span></span>  <br/> |<span data-ttu-id="04d36-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="04d36-193">CNAME</span></span>  <br/> |<span data-ttu-id="04d36-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="04d36-194">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="04d36-195">sip</span><span class="sxs-lookup"><span data-stu-id="04d36-195">sip</span></span>  <br/> |<span data-ttu-id="04d36-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="04d36-196">CNAME</span></span>  <br/> |<span data-ttu-id="04d36-197">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="04d36-197">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="04d36-198">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="04d36-198">lyncdiscover</span></span>  <br/> |<span data-ttu-id="04d36-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="04d36-199">CNAME</span></span>  <br/> |<span data-ttu-id="04d36-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="04d36-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="04d36-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="04d36-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="04d36-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="04d36-202">CNAME</span></span>  <br/> |<span data-ttu-id="04d36-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="04d36-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="04d36-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="04d36-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="04d36-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="04d36-205">CNAME</span></span>  <br/> |<span data-ttu-id="04d36-206">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="04d36-206">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![NamesUK-BP-Configure-3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. <span data-ttu-id="04d36-208">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="04d36-208">Select **Save**.</span></span>
    
    ![NamesUK-BP-Configure-3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="04d36-210">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="04d36-210">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="04d36-211"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="04d36-211"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="04d36-212">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="04d36-212">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="04d36-213">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="04d36-213">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="04d36-214">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="04d36-214">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="04d36-215">Вместо этого добавьте необходимые значения Microsoft в текущую  запись, чтобы у вас была одна запись SPF, которая включает оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="04d36-215">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="04d36-p111">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Names.co.uk по [этой ссылке](https://account.names.co.uk/dashboard#/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="04d36-p111">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="04d36-219">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="04d36-219">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="04d36-220">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="04d36-220">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="04d36-222">На странице **DNS Zones on Account** в столбце **Доменное** имя выберите имя обновляемого домена.</span><span class="sxs-lookup"><span data-stu-id="04d36-222">On the **DNS Zones on Account** page, in the **Domain name** column, select the name of the domain that you are updating.</span></span> 
    
    ![NamesUK-BP-Configure-1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. <span data-ttu-id="04d36-224">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="04d36-224">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="04d36-225">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="04d36-225">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="04d36-226">(Если необходимо добавить строку, выберите **ADD A/CNAME RECORDS (+)**.)</span><span class="sxs-lookup"><span data-stu-id="04d36-226">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="04d36-227">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="04d36-227">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="04d36-228">**Host Name (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="04d36-228">**Host name**</span></span>|<span data-ttu-id="04d36-229">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="04d36-229">**Type**</span></span>|<span data-ttu-id="04d36-230">**Result (Результат)**</span><span class="sxs-lookup"><span data-stu-id="04d36-230">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="04d36-231">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="04d36-231">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="04d36-232">TXT</span><span class="sxs-lookup"><span data-stu-id="04d36-232">TXT</span></span>  <br/> |<span data-ttu-id="04d36-233">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="04d36-233">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="04d36-234">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="04d36-234">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
       
    ![NamesUK-BP-Configure-4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. <span data-ttu-id="04d36-236">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="04d36-236">Select **Save**.</span></span>
    
    <span data-ttu-id="04d36-237">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="04d36-237">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="04d36-239">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="04d36-239">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="04d36-240"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="04d36-240"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="04d36-p112">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Names.co.uk по [этой ссылке](https://account.names.co.uk/dashboard#/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="04d36-p112">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="04d36-244">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="04d36-244">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="04d36-245">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="04d36-245">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="04d36-247">На странице **Add/Modify DNS Zone** (Добавить/изменить зону DNS) в разделе **Service records** (Записи службы) в поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="04d36-247">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="04d36-248">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="04d36-248">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="04d36-249">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="04d36-249">**Name**</span></span>|<span data-ttu-id="04d36-250">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="04d36-250">**Priority**</span></span>|<span data-ttu-id="04d36-251">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="04d36-251">**Weight**</span></span>|<span data-ttu-id="04d36-252">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="04d36-252">**Port**</span></span>|<span data-ttu-id="04d36-253">**Result (Результат)**</span><span class="sxs-lookup"><span data-stu-id="04d36-253">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="04d36-254">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="04d36-254">_sip._tls</span></span>  <br/> |<span data-ttu-id="04d36-255">100</span><span class="sxs-lookup"><span data-stu-id="04d36-255">100</span></span>  <br/> |<span data-ttu-id="04d36-256">1</span><span class="sxs-lookup"><span data-stu-id="04d36-256">1</span></span>  <br/> |<span data-ttu-id="04d36-257">443</span><span class="sxs-lookup"><span data-stu-id="04d36-257">443</span></span>  <br/> |<span data-ttu-id="04d36-258">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="04d36-258">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="04d36-259">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="04d36-259">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="04d36-260">100</span><span class="sxs-lookup"><span data-stu-id="04d36-260">100</span></span>  <br/> |<span data-ttu-id="04d36-261">1</span><span class="sxs-lookup"><span data-stu-id="04d36-261">1</span></span>  <br/> |<span data-ttu-id="04d36-262">5061</span><span class="sxs-lookup"><span data-stu-id="04d36-262">5061</span></span>  <br/> |<span data-ttu-id="04d36-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="04d36-263">sipfed.online.lync.com</span></span>  <br/> |
       
    ![NamesUK-BP-Configure-5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. <span data-ttu-id="04d36-265">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="04d36-265">Select **Save**.</span></span>
    
    <span data-ttu-id="04d36-266">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="04d36-266">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  <span data-ttu-id="04d36-p113">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="04d36-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
