---
title: Создание записей DNS на сайте name.com для Майкрософт
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
ms.assetid: 9ddcc2fc-9433-4335-8192-6ffb1f541087
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу name.com для Майкрософт.
ms.openlocfilehash: 8518ca2570b3be1cb3abcd5c57b8309e989481cb
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938664"
---
# <a name="create-dns-records-at-namecom-for-microsoft"></a><span data-ttu-id="0898f-103">Создание записей DNS на сайте name.com для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="0898f-103">Create DNS records at name.com for Microsoft</span></span>

 <span data-ttu-id="0898f-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="0898f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="0898f-105">Если ваш поставщик услуг размещения DNS  name.com, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="0898f-105">If name.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="0898f-106">Когда вы добавите эти записи на сайте name.com, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0898f-106">After you add these records at name.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
> <span data-ttu-id="0898f-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0898f-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="0898f-110">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="0898f-110">Add a TXT record for verification</span></span>
<span data-ttu-id="0898f-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="0898f-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="0898f-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="0898f-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0898f-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="0898f-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="0898f-p104">Чтобы приступить к работе, откройте страницу со своими доменами на сайте name.com по [этой ссылке](https://www.name.com/account/domain). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="0898f-p104">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="0898f-119">В разделе **My Domains (мои домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="0898f-119">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="0898f-121">В столбце **сведения** выберите **записи DNS**.</span><span class="sxs-lookup"><span data-stu-id="0898f-121">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="0898f-123">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="0898f-123">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="0898f-124">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="0898f-124">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0898f-125">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="0898f-125">**Type**</span></span> <br/> |<span data-ttu-id="0898f-126">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="0898f-126">**Host**</span></span> <br/> |<span data-ttu-id="0898f-127">**Answer** (Ответ)</span><span class="sxs-lookup"><span data-stu-id="0898f-127">**Answer**</span></span> <br/> |<span data-ttu-id="0898f-128">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="0898f-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="0898f-129">TXT</span><span class="sxs-lookup"><span data-stu-id="0898f-129">TXT</span></span>  <br/> |<span data-ttu-id="0898f-130">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="0898f-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="0898f-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="0898f-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="0898f-132">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="0898f-132">**Note:** This is an example.</span></span> <span data-ttu-id="0898f-133">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="0898f-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="0898f-134">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="0898f-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="0898f-135">Используйте значение по умолчанию (300).</span><span class="sxs-lookup"><span data-stu-id="0898f-135">Use the default value (300).</span></span>  <br/> |
   
    ![Name — BP — Verify – 1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. <span data-ttu-id="0898f-137">Выберите команду **Add Record** (Добавить запись).</span><span class="sxs-lookup"><span data-stu-id="0898f-137">Select **Add Record**.</span></span>
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. <span data-ttu-id="0898f-139">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="0898f-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="0898f-140">Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.</span><span class="sxs-lookup"><span data-stu-id="0898f-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="0898f-141">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="0898f-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="0898f-142">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="0898f-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="0898f-143">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="0898f-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="0898f-144">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="0898f-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="0898f-145">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="0898f-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="0898f-p106">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0898f-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="0898f-149">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0898f-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="0898f-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="0898f-150"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="0898f-p107">Чтобы приступить к работе, откройте страницу со своими доменами на сайте name.com по [этой ссылке](https://www.name.com/account/domain). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="0898f-p107">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="0898f-154">В разделе **My Domains (мои домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="0898f-154">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="0898f-156">В столбце **сведения** выберите **записи DNS**.</span><span class="sxs-lookup"><span data-stu-id="0898f-156">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="0898f-158">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="0898f-158">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="0898f-159">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="0898f-159">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="0898f-160">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="0898f-160">**Type**</span></span>|<span data-ttu-id="0898f-161">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="0898f-161">**Host**</span></span>|<span data-ttu-id="0898f-162">**Answer** (Ответ)</span><span class="sxs-lookup"><span data-stu-id="0898f-162">**Answer**</span></span>|<span data-ttu-id="0898f-163">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="0898f-163">**TTL**</span></span>|<span data-ttu-id="0898f-164">**Prio (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="0898f-164">**Prio**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0898f-165">MX</span><span class="sxs-lookup"><span data-stu-id="0898f-165">MX</span></span>  <br/> |<span data-ttu-id="0898f-166">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="0898f-166">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="0898f-167">*\<ключ_домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="0898f-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="0898f-168">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0898f-168">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="0898f-169">Как найти это значение?</span><span class="sxs-lookup"><span data-stu-id="0898f-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="0898f-170">Используйте значение по умолчанию (300).</span><span class="sxs-lookup"><span data-stu-id="0898f-170">Use the default value (300).</span></span>  <br/> |<span data-ttu-id="0898f-171">нуль</span><span class="sxs-lookup"><span data-stu-id="0898f-171">0</span></span>  <br/> <span data-ttu-id="0898f-172">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="0898f-172">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Name — BP — configure – 2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. <span data-ttu-id="0898f-174">Выберите команду **Add Record** (Добавить запись).</span><span class="sxs-lookup"><span data-stu-id="0898f-174">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. <span data-ttu-id="0898f-176">Если в списке указаны другие записи MX, удалите их. Для этого выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="0898f-176">If there are any other MX records, delete each of them by using the following two-step procedure:</span></span>
    
    <span data-ttu-id="0898f-177">Для каждой другой записи MX выберите команду **Удалить** в столбце **действия** .</span><span class="sxs-lookup"><span data-stu-id="0898f-177">For each other MX record, select **Delete** in the **Actions** column.</span></span> 
    
    ![Name-BP-Configure-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    <span data-ttu-id="0898f-179">Чтобы подтвердить каждое удаление, нажмите кнопку **Удалить** в столбце **действия** еще раз.</span><span class="sxs-lookup"><span data-stu-id="0898f-179">To confirm each deletion, select **Delete** in the **Actions** column again.</span></span> 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    <span data-ttu-id="0898f-181">Повторяйте эти действия, пока не удалите все остальные записи MX.</span><span class="sxs-lookup"><span data-stu-id="0898f-181">Repeat this two-step procedure until you have deleted each of the other MX records.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="0898f-182">Добавление записей CNAME, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="0898f-182">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="0898f-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="0898f-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="0898f-p109">Чтобы приступить к работе, откройте страницу со своими доменами на сайте name.com по [этой ссылке](https://www.name.com/account/domain). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="0898f-p109">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="0898f-187">В разделе **My Domains (мои домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="0898f-187">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="0898f-189">В столбце **сведения** выберите **записи DNS**.</span><span class="sxs-lookup"><span data-stu-id="0898f-189">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="0898f-191">Добавьте первую запись CNAME.</span><span class="sxs-lookup"><span data-stu-id="0898f-191">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="0898f-192">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="0898f-192">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="0898f-193">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="0898f-193">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="0898f-194">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="0898f-194">**Type**</span></span>|<span data-ttu-id="0898f-195">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="0898f-195">**Host**</span></span>|<span data-ttu-id="0898f-196">**Answer** (Ответ)</span><span class="sxs-lookup"><span data-stu-id="0898f-196">**Answer**</span></span>|<span data-ttu-id="0898f-197">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="0898f-197">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0898f-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="0898f-198">CNAME</span></span>  <br/> |<span data-ttu-id="0898f-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="0898f-199">autodiscover</span></span>  <br/> |<span data-ttu-id="0898f-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="0898f-200">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="0898f-201">Используйте значение по умолчанию (300).</span><span class="sxs-lookup"><span data-stu-id="0898f-201">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="0898f-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="0898f-202">CNAME</span></span>  <br/> |<span data-ttu-id="0898f-203">sip</span><span class="sxs-lookup"><span data-stu-id="0898f-203">sip</span></span>  <br/> |<span data-ttu-id="0898f-204">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0898f-204">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="0898f-205">Используйте значение по умолчанию (300).</span><span class="sxs-lookup"><span data-stu-id="0898f-205">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="0898f-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="0898f-206">CNAME</span></span>  <br/> |<span data-ttu-id="0898f-207">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="0898f-207">lyncdiscover</span></span>  <br/> |<span data-ttu-id="0898f-208">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0898f-208">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="0898f-209">Используйте значение по умолчанию (300).</span><span class="sxs-lookup"><span data-stu-id="0898f-209">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="0898f-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="0898f-210">CNAME</span></span>  <br/> |<span data-ttu-id="0898f-211">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="0898f-211">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="0898f-212">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="0898f-212">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="0898f-213">Используйте значение по умолчанию (300).</span><span class="sxs-lookup"><span data-stu-id="0898f-213">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="0898f-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="0898f-214">CNAME</span></span>  <br/> |<span data-ttu-id="0898f-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="0898f-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="0898f-216">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="0898f-216">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="0898f-217">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="0898f-217">Use the default value (300).</span></span>  <br/> |
   
   ![Name — BP — configure – 3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. <span data-ttu-id="0898f-219">Нажмите кнопку **Добавить запись** , чтобы добавить первую запись.</span><span class="sxs-lookup"><span data-stu-id="0898f-219">Select **Add Record** to add the first record.</span></span> 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. <span data-ttu-id="0898f-221">Добавьте вторую запись CNAME.</span><span class="sxs-lookup"><span data-stu-id="0898f-221">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="0898f-222">Используйте значения из второй строки приведенной выше таблицы, а затем выберите **Добавить запись** , чтобы добавить вторую запись.</span><span class="sxs-lookup"><span data-stu-id="0898f-222">Use the values from the second row of the table above, and then select **Add Record** to add the second record.</span></span> 
    
    <span data-ttu-id="0898f-223">Точно так же добавьте остальные записи, используя значения из третьей, четвертой, пятой и шестой строк таблицы.</span><span class="sxs-lookup"><span data-stu-id="0898f-223">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="0898f-224">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="0898f-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="0898f-225"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="0898f-225"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="0898f-226">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="0898f-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="0898f-227">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="0898f-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="0898f-228">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0898f-228">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="0898f-229">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="0898f-229">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="0898f-p111">Чтобы приступить к работе, откройте страницу со своими доменами на сайте name.com по [этой ссылке](https://www.name.com/account/domain). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="0898f-p111">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="0898f-233">В разделе **My Domains (мои домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="0898f-233">Under **My Domains**, select the name of the domain that you want to modify.</span></span>

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="0898f-235">В столбце **сведения** выберите **записи DNS**.</span><span class="sxs-lookup"><span data-stu-id="0898f-235">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="0898f-237">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="0898f-237">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="0898f-238">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="0898f-238">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="0898f-239">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="0898f-239">**Type**</span></span>|<span data-ttu-id="0898f-240">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="0898f-240">**Host**</span></span>|<span data-ttu-id="0898f-241">**Answer** (Ответ)</span><span class="sxs-lookup"><span data-stu-id="0898f-241">**Answer**</span></span>|<span data-ttu-id="0898f-242">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="0898f-242">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0898f-243">TXT</span><span class="sxs-lookup"><span data-stu-id="0898f-243">TXT</span></span>  <br/> |<span data-ttu-id="0898f-244">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="0898f-244">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="0898f-245">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="0898f-245">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="0898f-246">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="0898f-246">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="0898f-247">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="0898f-247">Use the default value (300).</span></span>  <br/> |
   
   ![Name — BP — configure – 4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. <span data-ttu-id="0898f-249">Выберите команду **Add Record** (Добавить запись).</span><span class="sxs-lookup"><span data-stu-id="0898f-249">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="0898f-251">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="0898f-251">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="0898f-252"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="0898f-252"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="0898f-p112">Чтобы приступить к работе, откройте страницу со своими доменами на сайте name.com по [этой ссылке](https://www.name.com/account/domain). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="0898f-p112">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="0898f-256">В разделе **My Domains (мои домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="0898f-256">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="0898f-258">В столбце **сведения** выберите **DNS-записи и**.</span><span class="sxs-lookup"><span data-stu-id="0898f-258">In the **Details** column, select **DNS Records+**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="0898f-260">Добавьте первую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="0898f-260">Add the first SRV record:</span></span>
    
    <span data-ttu-id="0898f-261">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="0898f-261">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="0898f-262">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="0898f-262">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="0898f-263">**Тип**</span><span class="sxs-lookup"><span data-stu-id="0898f-263">**Type**</span></span>|<span data-ttu-id="0898f-264">**Service (Служба)**</span><span class="sxs-lookup"><span data-stu-id="0898f-264">**Service**</span></span>|<span data-ttu-id="0898f-265">**Weight (Вес)**</span><span class="sxs-lookup"><span data-stu-id="0898f-265">**Weight**</span></span>|<span data-ttu-id="0898f-266">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="0898f-266">**TTL**</span></span>|<span data-ttu-id="0898f-267">**Prio (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="0898f-267">**Prio**</span></span>|<span data-ttu-id="0898f-268">**Protocol (Протокол)**</span><span class="sxs-lookup"><span data-stu-id="0898f-268">**Protocol**</span></span>|<span data-ttu-id="0898f-269">**Port (Порт)**</span><span class="sxs-lookup"><span data-stu-id="0898f-269">**Port**</span></span>|<span data-ttu-id="0898f-270">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="0898f-270">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0898f-271">SRV</span><span class="sxs-lookup"><span data-stu-id="0898f-271">SRV</span></span>|<span data-ttu-id="0898f-272">sip</span><span class="sxs-lookup"><span data-stu-id="0898f-272">sip</span></span>|<span data-ttu-id="0898f-273">1,1</span><span class="sxs-lookup"><span data-stu-id="0898f-273">1</span></span>|<span data-ttu-id="0898f-274">Используйте значение по умолчанию (300).</span><span class="sxs-lookup"><span data-stu-id="0898f-274">Use the default value (300).</span></span>|<span data-ttu-id="0898f-275">100</span><span class="sxs-lookup"><span data-stu-id="0898f-275">100</span></span>|<span data-ttu-id="0898f-276">tls</span><span class="sxs-lookup"><span data-stu-id="0898f-276">tls</span></span>|<span data-ttu-id="0898f-277">443</span><span class="sxs-lookup"><span data-stu-id="0898f-277">443</span></span>|<span data-ttu-id="0898f-278">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0898f-278">sipdir.online.lync.com</span></span> <br> <span data-ttu-id="0898f-279">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="0898f-279">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="0898f-280">SRV</span><span class="sxs-lookup"><span data-stu-id="0898f-280">SRV</span></span>|<span data-ttu-id="0898f-281">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="0898f-281">sipfederationtls</span></span>|<span data-ttu-id="0898f-282">1,1</span><span class="sxs-lookup"><span data-stu-id="0898f-282">1</span></span>|<span data-ttu-id="0898f-283">Используйте значение по умолчанию (300).</span><span class="sxs-lookup"><span data-stu-id="0898f-283">Use the default value (300).</span></span>|<span data-ttu-id="0898f-284">100</span><span class="sxs-lookup"><span data-stu-id="0898f-284">100</span></span>|<span data-ttu-id="0898f-285">tcp</span><span class="sxs-lookup"><span data-stu-id="0898f-285">tcp</span></span>|<span data-ttu-id="0898f-286">5061</span><span class="sxs-lookup"><span data-stu-id="0898f-286">5061</span></span>|<span data-ttu-id="0898f-287">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0898f-287">sipfed.online.lync.com</span></span> <br><span data-ttu-id="0898f-288">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="0898f-288">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Name — BP — configure – 5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. <span data-ttu-id="0898f-290">Выберите команду **Add Record** (Добавить запись).</span><span class="sxs-lookup"><span data-stu-id="0898f-290">Select **Add Record**.</span></span>

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. <span data-ttu-id="0898f-292">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="0898f-292">Add the second SRV record:</span></span>

<span data-ttu-id="0898f-293">Используйте значения из следующей строки приведенной выше таблицы, а затем выберите **Добавить запись** , чтобы добавить вторую запись.</span><span class="sxs-lookup"><span data-stu-id="0898f-293">Use the values from the next row of the table above, and then select **Add Record** to add the second record.</span></span>

>[!NOTE]
><span data-ttu-id="0898f-p113">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0898f-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
