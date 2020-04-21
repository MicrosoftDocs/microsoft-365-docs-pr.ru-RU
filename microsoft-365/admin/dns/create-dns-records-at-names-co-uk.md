---
title: Создание записей DNS на сайте Names.co.uk для Майкрософт
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
ms.assetid: b6c15128-b456-49b4-8b5e-5b823c700f26
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу Names.co.uk для Майкрософт.
ms.openlocfilehash: 2552017e06001c0b28605558b823fdb4c670ef8c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629327"
---
# <a name="create-dns-records-at-namescouk-for-microsoft"></a><span data-ttu-id="059a3-103">Создание записей DNS на сайте Names.co.uk для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="059a3-103">Create DNS records at Names.co.uk for Microsoft</span></span>

 <span data-ttu-id="059a3-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="059a3-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="059a3-105">Если ваш поставщик услуг размещения DNS  Names.co.uk, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="059a3-105">If Names.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="059a3-106">Когда вы добавите эти записи на сайте Names.co.uk, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="059a3-106">After you add these records at Names.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="059a3-107">Чтобы узнать о размещении и DNS для веб-сайтов с помощью Microsoft, ознакомьтесь со статьей [использование общедоступного веб-сайта с корпорацией Майкрософт](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="059a3-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="059a3-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="059a3-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="059a3-111">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="059a3-111">Add a TXT record for verification</span></span>
<span data-ttu-id="059a3-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="059a3-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="059a3-113">Перед использованием домена с корпорацией Майкрософт необходимо убедиться, что вы являетесь его владельцем.</span><span class="sxs-lookup"><span data-stu-id="059a3-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="059a3-114">Вы можете войти в свою учетную запись у вас в вашем регистраторе доменных имен и создать запись DNS в Майкрософт, если вы владеете этим доменом.</span><span class="sxs-lookup"><span data-stu-id="059a3-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="059a3-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="059a3-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="059a3-p104">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Names.co.uk по [этой ссылке](https://account.names.co.uk/dashboard#/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="059a3-p104">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![Намесук — BP — configure – 1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="059a3-120">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="059a3-120">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="059a3-121">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="059a3-121">(You may have to scroll down.)</span></span>
    
    ![Намесук — BP — configure – 1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="059a3-123">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="059a3-123">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="059a3-124">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="059a3-124">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="059a3-125">(Если необходимо добавить строку, выберите **добавить записи a/CNAME (+)**.)</span><span class="sxs-lookup"><span data-stu-id="059a3-125">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="059a3-126">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="059a3-126">(You may have to scroll down.)</span></span>
        
    |<span data-ttu-id="059a3-127">**Host Name (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="059a3-127">**Host name**</span></span>|<span data-ttu-id="059a3-128">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="059a3-128">**Type**</span></span>|<span data-ttu-id="059a3-129">**Результат**</span><span class="sxs-lookup"><span data-stu-id="059a3-129">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="059a3-130">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="059a3-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="059a3-131">TXT</span><span class="sxs-lookup"><span data-stu-id="059a3-131">TXT</span></span>  <br/> |<span data-ttu-id="059a3-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="059a3-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="059a3-133">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="059a3-133">**Note:** This is an example.</span></span> <span data-ttu-id="059a3-134">Используйте указанную здесь **конечную точку или значение адреса** из таблицы.</span><span class="sxs-lookup"><span data-stu-id="059a3-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="059a3-135">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="059a3-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
       
    ![Намесук — BP — Verify – 1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. <span data-ttu-id="059a3-137">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="059a3-137">Select **Save**.</span></span>
    
    <span data-ttu-id="059a3-138">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="059a3-138">(You may have to scroll down.)</span></span>
    
    ![Намесук — BP — Verify – 1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. <span data-ttu-id="059a3-140">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="059a3-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="059a3-141">Теперь, когда вы добавили запись на сайте регистратора доменных имен, вернитесь в корпорацию Майкрософт и запросите запись.</span><span class="sxs-lookup"><span data-stu-id="059a3-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="059a3-142">После того как корпорация Майкрософт обнаружит правильную запись TXT, ваш домен будет проверен.</span><span class="sxs-lookup"><span data-stu-id="059a3-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="059a3-143">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="059a3-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="059a3-144">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="059a3-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="059a3-145">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="059a3-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="059a3-146">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="059a3-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="059a3-p106">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="059a3-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="059a3-150">Добавление записи MX для отправки электронной почты для вашего домена в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="059a3-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="059a3-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="059a3-151"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="059a3-p107">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Names.co.uk по [этой ссылке](https://account.names.co.uk/dashboard#/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="059a3-p107">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![Намесук — BP — configure – 1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="059a3-155">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="059a3-155">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="059a3-156">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="059a3-156">(You may have to scroll down.)</span></span>
    
    ![Намесук — BP — configure – 1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="059a3-158">На странице **Add/Modify DNS Zone** (Добавить/изменить зону DNS) в разделе **Mail exchange records** (Записи обмена электронной почтой) в поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="059a3-158">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="059a3-159">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="059a3-159">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="059a3-160">**Host Name (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="059a3-160">**Host name**</span></span>|<span data-ttu-id="059a3-161">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="059a3-161">**Priority**</span></span>|<span data-ttu-id="059a3-162">**Результат**</span><span class="sxs-lookup"><span data-stu-id="059a3-162">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="059a3-163">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="059a3-163">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="059a3-164">1,1</span><span class="sxs-lookup"><span data-stu-id="059a3-164">1</span></span>  <br/> <span data-ttu-id="059a3-165">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="059a3-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="059a3-166">*\<ключ_домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="059a3-166">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="059a3-167">> [!NOTE]> получить \* \<ключ\> домена\* из учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="059a3-167">> [!NOTE]> Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="059a3-168">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="059a3-168">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![Намесук — BP — configure – 2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. <span data-ttu-id="059a3-170">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="059a3-170">Select **Save**.</span></span>
    
    <span data-ttu-id="059a3-171">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="059a3-171">(You may have to scroll down.)</span></span>
    
    ![Намесук — BP — configure – 2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. <span data-ttu-id="059a3-173">Если в разделе **Mail exchange records** (Записи обмена электронной почтой) есть какие-либо другие записи MX, удалите каждую из них, выделив ее и нажав на клавиатуре клавишу **DELETE**.</span><span class="sxs-lookup"><span data-stu-id="059a3-173">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Намесук — BP — configure – 2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. <span data-ttu-id="059a3-175">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="059a3-175">Select **Save**.</span></span>
    
    <span data-ttu-id="059a3-176">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="059a3-176">(You may have to scroll down.)</span></span>
    
    ![Намесук — BP — configure – 2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="059a3-178">Добавление шести записей CNAME, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="059a3-178">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="059a3-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="059a3-179"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="059a3-p109">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Names.co.uk по [этой ссылке](https://account.names.co.uk/dashboard#/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="059a3-p109">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![Намесук — BP — configure – 1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="059a3-183">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="059a3-183">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="059a3-184">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="059a3-184">(You may have to scroll down.)</span></span>
    
    ![Намесук — BP — configure – 1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="059a3-186">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="059a3-186">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="059a3-187">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="059a3-187">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="059a3-188">(Если необходимо добавить строку, выберите **добавить записи a/CNAME (+)**.)</span><span class="sxs-lookup"><span data-stu-id="059a3-188">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="059a3-189">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="059a3-189">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="059a3-190">**Host Name (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="059a3-190">**Host Name**</span></span>|<span data-ttu-id="059a3-191">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="059a3-191">**Type**</span></span>|<span data-ttu-id="059a3-192">**Результат**</span><span class="sxs-lookup"><span data-stu-id="059a3-192">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="059a3-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="059a3-193">autodiscover</span></span>  <br/> |<span data-ttu-id="059a3-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="059a3-194">CNAME</span></span>  <br/> |<span data-ttu-id="059a3-195">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="059a3-195">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="059a3-196">sip</span><span class="sxs-lookup"><span data-stu-id="059a3-196">sip</span></span>  <br/> |<span data-ttu-id="059a3-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="059a3-197">CNAME</span></span>  <br/> |<span data-ttu-id="059a3-198">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="059a3-198">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="059a3-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="059a3-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="059a3-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="059a3-200">CNAME</span></span>  <br/> |<span data-ttu-id="059a3-201">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="059a3-201">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="059a3-202">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="059a3-202">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="059a3-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="059a3-203">CNAME</span></span>  <br/> |<span data-ttu-id="059a3-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="059a3-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="059a3-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="059a3-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="059a3-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="059a3-206">CNAME</span></span>  <br/> |<span data-ttu-id="059a3-207">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="059a3-207">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![Намесук — BP — configure – 3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. <span data-ttu-id="059a3-209">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="059a3-209">Select **Save**.</span></span>
    
    ![Намесук — BP — configure – 3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="059a3-211">Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама</span><span class="sxs-lookup"><span data-stu-id="059a3-211">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="059a3-212"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="059a3-212"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="059a3-213">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="059a3-213">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="059a3-214">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="059a3-214">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="059a3-215">Если у вас уже есть запись SPF для вашего домена, не создавайте ее для Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="059a3-215">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="059a3-216">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="059a3-216">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="059a3-p111">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Names.co.uk по [этой ссылке](https://account.names.co.uk/dashboard#/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="059a3-p111">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![Намесук — BP — configure – 1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="059a3-220">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="059a3-220">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="059a3-221">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="059a3-221">(You may have to scroll down.)</span></span>
    
    ![Намесук — BP — configure – 1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="059a3-223">На странице " **зоны DNS в учетной записи** " в столбце **доменное имя** выберите доменное имя, которое вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="059a3-223">On the **DNS Zones on Account** page, in the **Domain name** column, select the name of the domain that you are updating.</span></span> 
    
    ![Намесук — BP — configure – 1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. <span data-ttu-id="059a3-225">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="059a3-225">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="059a3-226">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="059a3-226">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="059a3-227">(Если необходимо добавить строку, выберите **добавить записи a/CNAME (+)**.)</span><span class="sxs-lookup"><span data-stu-id="059a3-227">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="059a3-228">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="059a3-228">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="059a3-229">**Host Name (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="059a3-229">**Host name**</span></span>|<span data-ttu-id="059a3-230">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="059a3-230">**Type**</span></span>|<span data-ttu-id="059a3-231">**Результат**</span><span class="sxs-lookup"><span data-stu-id="059a3-231">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="059a3-232">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="059a3-232">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="059a3-233">TXT</span><span class="sxs-lookup"><span data-stu-id="059a3-233">TXT</span></span>  <br/> |<span data-ttu-id="059a3-234">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="059a3-234">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="059a3-235">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="059a3-235">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
       
    ![Намесук — BP — configure – 4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. <span data-ttu-id="059a3-237">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="059a3-237">Select **Save**.</span></span>
    
    <span data-ttu-id="059a3-238">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="059a3-238">(You may have to scroll down.)</span></span>
    
    ![Намесук — BP — configure – 4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="059a3-240">Добавление двух записей SRV, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="059a3-240">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="059a3-241"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="059a3-241"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="059a3-p112">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Names.co.uk по [этой ссылке](https://account.names.co.uk/dashboard#/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="059a3-p112">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![Намесук — BP — configure – 1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="059a3-245">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="059a3-245">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="059a3-246">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="059a3-246">(You may have to scroll down.)</span></span>
    
    ![Намесук — BP — configure – 1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="059a3-248">На странице **Add/Modify DNS Zone** (Добавить/изменить зону DNS) в разделе **Service records** (Записи службы) в поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="059a3-248">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="059a3-249">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="059a3-249">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="059a3-250">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="059a3-250">**Name**</span></span>|<span data-ttu-id="059a3-251">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="059a3-251">**Priority**</span></span>|<span data-ttu-id="059a3-252">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="059a3-252">**Weight**</span></span>|<span data-ttu-id="059a3-253">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="059a3-253">**Port**</span></span>|<span data-ttu-id="059a3-254">**Result (Результат)**</span><span class="sxs-lookup"><span data-stu-id="059a3-254">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="059a3-255">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="059a3-255">_sip._tls</span></span>  <br/> |<span data-ttu-id="059a3-256">100</span><span class="sxs-lookup"><span data-stu-id="059a3-256">100</span></span>  <br/> |<span data-ttu-id="059a3-257">1,1</span><span class="sxs-lookup"><span data-stu-id="059a3-257">1</span></span>  <br/> |<span data-ttu-id="059a3-258">443</span><span class="sxs-lookup"><span data-stu-id="059a3-258">443</span></span>  <br/> |<span data-ttu-id="059a3-259">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="059a3-259">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="059a3-260">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="059a3-260">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="059a3-261">100</span><span class="sxs-lookup"><span data-stu-id="059a3-261">100</span></span>  <br/> |<span data-ttu-id="059a3-262">1,1</span><span class="sxs-lookup"><span data-stu-id="059a3-262">1</span></span>  <br/> |<span data-ttu-id="059a3-263">5061</span><span class="sxs-lookup"><span data-stu-id="059a3-263">5061</span></span>  <br/> |<span data-ttu-id="059a3-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="059a3-264">sipfed.online.lync.com</span></span>  <br/> |
       
    ![Намесук — BP — configure – 5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. <span data-ttu-id="059a3-266">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="059a3-266">Select **Save**.</span></span>
    
    <span data-ttu-id="059a3-267">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="059a3-267">(You may have to scroll down.)</span></span>
    
    ![Намесук — BP — configure – 5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  <span data-ttu-id="059a3-p113">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="059a3-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
