---
title: Создание DNS-записей для Office 365 на сайте name.com
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
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу name.com для Office 365.
ms.openlocfilehash: f39cf9f241851e555ea23ca7b63453796a5f471b
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211659"
---
# <a name="create-dns-records-at-namecom-for-office-365"></a><span data-ttu-id="4eabc-103">Создание DNS-записей для Office 365 на сайте name.com</span><span class="sxs-lookup"><span data-stu-id="4eabc-103">Create DNS records at name.com for Office 365</span></span>

 <span data-ttu-id="4eabc-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="4eabc-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="4eabc-105">Если ваш поставщик услуг размещения DNS  name.com, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="4eabc-105">If name.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="4eabc-106">Когда вы добавите эти записи на сайте name.com, ваш домен будет настроен для работы со службами Office 365.</span><span class="sxs-lookup"><span data-stu-id="4eabc-106">After you add these records at name.com, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="4eabc-107">Дополнительные сведения о веб-хостинге и DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="4eabc-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4eabc-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4eabc-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="4eabc-111">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="4eabc-111">Add a TXT record for verification</span></span>
<span data-ttu-id="4eabc-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="4eabc-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="4eabc-p102">Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="4eabc-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4eabc-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="4eabc-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="4eabc-p104">Чтобы приступить к работе, откройте страницу со своими доменами на сайте name.com по [этой ссылке](https://www.name.com/account/domain). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="4eabc-p104">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="4eabc-120">В разделе **My Domains (мои домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="4eabc-120">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="4eabc-122">В столбце **сведения** выберите \* \* записи DNS \* \*.</span><span class="sxs-lookup"><span data-stu-id="4eabc-122">In the **Details** column, select \*\* DNS Records \*\*.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="4eabc-124">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="4eabc-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="4eabc-125">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="4eabc-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4eabc-126">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="4eabc-126">**Type**</span></span> <br/> |<span data-ttu-id="4eabc-127">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="4eabc-127">**Host**</span></span> <br/> |<span data-ttu-id="4eabc-128">**Answer** (Ответ)</span><span class="sxs-lookup"><span data-stu-id="4eabc-128">**Answer**</span></span> <br/> |<span data-ttu-id="4eabc-129">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="4eabc-129">**TTL**</span></span> <br/> |
    |<span data-ttu-id="4eabc-130">TXT</span><span class="sxs-lookup"><span data-stu-id="4eabc-130">TXT</span></span>  <br/> |<span data-ttu-id="4eabc-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="4eabc-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="4eabc-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="4eabc-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="4eabc-p105">**Примечание.** Это пример. Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.           [Где это находится?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="4eabc-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="4eabc-136">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="4eabc-136">Use the default value (300).</span></span>  <br/> |
   
    ![Name — BP — Verify – 1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. <span data-ttu-id="4eabc-138">Выберите команду **Add Record** (Добавить запись).</span><span class="sxs-lookup"><span data-stu-id="4eabc-138">Select **Add Record**.</span></span>
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. <span data-ttu-id="4eabc-140">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="4eabc-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="4eabc-141">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Office 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="4eabc-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="4eabc-142">Если Office 365 обнаружит правильную запись TXT, это значит, что домен проверен.</span><span class="sxs-lookup"><span data-stu-id="4eabc-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="4eabc-143">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="4eabc-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="4eabc-144">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="4eabc-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="4eabc-145">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="4eabc-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="4eabc-146">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="4eabc-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="4eabc-p106">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4eabc-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="4eabc-150">Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="4eabc-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="4eabc-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="4eabc-151"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="4eabc-p107">Чтобы приступить к работе, откройте страницу со своими доменами на сайте name.com по [этой ссылке](https://www.name.com/account/domain). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="4eabc-p107">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="4eabc-155">В разделе **My Domains (мои домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="4eabc-155">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="4eabc-157">В столбце **сведения** выберите **записи DNS**.</span><span class="sxs-lookup"><span data-stu-id="4eabc-157">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="4eabc-159">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="4eabc-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="4eabc-160">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="4eabc-160">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="4eabc-161">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="4eabc-161">**Type**</span></span>|<span data-ttu-id="4eabc-162">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="4eabc-162">**Host**</span></span>|<span data-ttu-id="4eabc-163">**Answer** (Ответ)</span><span class="sxs-lookup"><span data-stu-id="4eabc-163">**Answer**</span></span>|<span data-ttu-id="4eabc-164">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="4eabc-164">**TTL**</span></span>|<span data-ttu-id="4eabc-165">**Prio (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="4eabc-165">**Prio**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4eabc-166">MX</span><span class="sxs-lookup"><span data-stu-id="4eabc-166">MX</span></span>  <br/> |<span data-ttu-id="4eabc-167">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="4eabc-167">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="4eabc-168">*\<ключ_домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="4eabc-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="4eabc-169">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Office 365.</span><span class="sxs-lookup"><span data-stu-id="4eabc-169">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="4eabc-170">Как найти это значение?</span><span class="sxs-lookup"><span data-stu-id="4eabc-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="4eabc-171">Используйте значение по умолчанию (300).</span><span class="sxs-lookup"><span data-stu-id="4eabc-171">Use the default value (300).</span></span>  <br/> |<span data-ttu-id="4eabc-172">нуль</span><span class="sxs-lookup"><span data-stu-id="4eabc-172">0</span></span>  <br/> <span data-ttu-id="4eabc-173">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="4eabc-173">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Name — BP — configure – 2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. <span data-ttu-id="4eabc-175">Выберите команду **Add Record** (Добавить запись).</span><span class="sxs-lookup"><span data-stu-id="4eabc-175">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. <span data-ttu-id="4eabc-177">Если в списке указаны другие записи MX, удалите их. Для этого выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="4eabc-177">If there are any other MX records, delete each of them by using the following two-step procedure:</span></span>
    
    <span data-ttu-id="4eabc-178">Для каждой другой записи MX выберите команду **Удалить** в столбце **действия** .</span><span class="sxs-lookup"><span data-stu-id="4eabc-178">For each other MX record, select **Delete** in the **Actions** column.</span></span> 
    
    ![Name-BP-Configure-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    <span data-ttu-id="4eabc-180">Чтобы подтвердить каждое удаление, нажмите кнопку **Удалить** в столбце **действия** еще раз.</span><span class="sxs-lookup"><span data-stu-id="4eabc-180">To confirm each deletion, select **Delete** in the **Actions** column again.</span></span> 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    <span data-ttu-id="4eabc-182">Повторяйте эти действия, пока не удалите все остальные записи MX.</span><span class="sxs-lookup"><span data-stu-id="4eabc-182">Repeat this two-step procedure until you have deleted each of the other MX records.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="4eabc-183">Добавление записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="4eabc-183">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="4eabc-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="4eabc-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="4eabc-p109">Чтобы приступить к работе, откройте страницу со своими доменами на сайте name.com по [этой ссылке](https://www.name.com/account/domain). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="4eabc-p109">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="4eabc-188">В разделе **My Domains (мои домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="4eabc-188">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="4eabc-190">В столбце **сведения** выберите **записи DNS**.</span><span class="sxs-lookup"><span data-stu-id="4eabc-190">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="4eabc-192">Добавьте первую запись CNAME.</span><span class="sxs-lookup"><span data-stu-id="4eabc-192">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="4eabc-193">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="4eabc-193">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="4eabc-194">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="4eabc-194">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="4eabc-195">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="4eabc-195">**Type**</span></span>|<span data-ttu-id="4eabc-196">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="4eabc-196">**Host**</span></span>|<span data-ttu-id="4eabc-197">**Answer** (Ответ)</span><span class="sxs-lookup"><span data-stu-id="4eabc-197">**Answer**</span></span>|<span data-ttu-id="4eabc-198">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="4eabc-198">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4eabc-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="4eabc-199">CNAME</span></span>  <br/> |<span data-ttu-id="4eabc-200">autodiscover</span><span class="sxs-lookup"><span data-stu-id="4eabc-200">autodiscover</span></span>  <br/> |<span data-ttu-id="4eabc-201">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="4eabc-201">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="4eabc-202">Используйте значение по умолчанию (300).</span><span class="sxs-lookup"><span data-stu-id="4eabc-202">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="4eabc-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="4eabc-203">CNAME</span></span>  <br/> |<span data-ttu-id="4eabc-204">sip</span><span class="sxs-lookup"><span data-stu-id="4eabc-204">sip</span></span>  <br/> |<span data-ttu-id="4eabc-205">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4eabc-205">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="4eabc-206">Используйте значение по умолчанию (300).</span><span class="sxs-lookup"><span data-stu-id="4eabc-206">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="4eabc-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="4eabc-207">CNAME</span></span>  <br/> |<span data-ttu-id="4eabc-208">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="4eabc-208">lyncdiscover</span></span>  <br/> |<span data-ttu-id="4eabc-209">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4eabc-209">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="4eabc-210">Используйте значение по умолчанию (300).</span><span class="sxs-lookup"><span data-stu-id="4eabc-210">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="4eabc-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="4eabc-211">CNAME</span></span>  <br/> |<span data-ttu-id="4eabc-212">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="4eabc-212">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="4eabc-213">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="4eabc-213">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="4eabc-214">Используйте значение по умолчанию (300).</span><span class="sxs-lookup"><span data-stu-id="4eabc-214">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="4eabc-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="4eabc-215">CNAME</span></span>  <br/> |<span data-ttu-id="4eabc-216">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="4eabc-216">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="4eabc-217">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4eabc-217">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="4eabc-218">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="4eabc-218">Use the default value (300).</span></span>  <br/> |
   
   ![Name — BP — configure – 3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. <span data-ttu-id="4eabc-220">Нажмите кнопку **Добавить запись** , чтобы добавить первую запись.</span><span class="sxs-lookup"><span data-stu-id="4eabc-220">Select **Add Record** to add the first record.</span></span> 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. <span data-ttu-id="4eabc-222">Добавьте вторую запись CNAME.</span><span class="sxs-lookup"><span data-stu-id="4eabc-222">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="4eabc-223">Используйте значения из второй строки приведенной выше таблицы, а затем выберите **Добавить запись** , чтобы добавить вторую запись.</span><span class="sxs-lookup"><span data-stu-id="4eabc-223">Use the values from the second row of the table above, and then select **Add Record** to add the second record.</span></span> 
    
    <span data-ttu-id="4eabc-224">Точно так же добавьте остальные записи, используя значения из третьей, четвертой, пятой и шестой строк таблицы.</span><span class="sxs-lookup"><span data-stu-id="4eabc-224">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="4eabc-225">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="4eabc-225">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="4eabc-226"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="4eabc-226"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="4eabc-227">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="4eabc-227">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="4eabc-228">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="4eabc-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="4eabc-229">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="4eabc-229">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="4eabc-230">Вместо этого добавьте необходимые значения Office 365 в текущую запись. Таким образом, в *одной* записи SPF будут указаны оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="4eabc-230">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="4eabc-p111">Чтобы приступить к работе, откройте страницу со своими доменами на сайте name.com по [этой ссылке](https://www.name.com/account/domain). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="4eabc-p111">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="4eabc-234">В разделе **My Domains (мои домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="4eabc-234">Under **My Domains**, select the name of the domain that you want to modify.</span></span>

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="4eabc-236">В столбце **сведения** выберите **записи DNS**.</span><span class="sxs-lookup"><span data-stu-id="4eabc-236">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="4eabc-238">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="4eabc-238">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="4eabc-239">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="4eabc-239">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="4eabc-240">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="4eabc-240">**Type**</span></span>|<span data-ttu-id="4eabc-241">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="4eabc-241">**Host**</span></span>|<span data-ttu-id="4eabc-242">**Answer** (Ответ)</span><span class="sxs-lookup"><span data-stu-id="4eabc-242">**Answer**</span></span>|<span data-ttu-id="4eabc-243">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="4eabc-243">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4eabc-244">TXT</span><span class="sxs-lookup"><span data-stu-id="4eabc-244">TXT</span></span>  <br/> |<span data-ttu-id="4eabc-245">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="4eabc-245">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="4eabc-246">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="4eabc-246">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="4eabc-247">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="4eabc-247">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="4eabc-248">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="4eabc-248">Use the default value (300).</span></span>  <br/> |
   
   ![Name — BP — configure – 4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. <span data-ttu-id="4eabc-250">Выберите команду **Add Record** (Добавить запись).</span><span class="sxs-lookup"><span data-stu-id="4eabc-250">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="4eabc-252">Добавление двух записей SRV, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="4eabc-252">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="4eabc-253"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="4eabc-253"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="4eabc-p112">Чтобы приступить к работе, откройте страницу со своими доменами на сайте name.com по [этой ссылке](https://www.name.com/account/domain). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="4eabc-p112">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="4eabc-257">В разделе **My Domains (мои домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="4eabc-257">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="4eabc-259">В столбце **сведения** выберите **DNS-записи и**.</span><span class="sxs-lookup"><span data-stu-id="4eabc-259">In the **Details** column, select **DNS Records+**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="4eabc-261">Добавьте первую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="4eabc-261">Add the first SRV record:</span></span>
    
    <span data-ttu-id="4eabc-262">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="4eabc-262">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="4eabc-263">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="4eabc-263">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="4eabc-264">**Тип**</span><span class="sxs-lookup"><span data-stu-id="4eabc-264">**Type**</span></span>|<span data-ttu-id="4eabc-265">**Service (Служба)**</span><span class="sxs-lookup"><span data-stu-id="4eabc-265">**Service**</span></span>|<span data-ttu-id="4eabc-266">**Weight (Вес)**</span><span class="sxs-lookup"><span data-stu-id="4eabc-266">**Weight**</span></span>|<span data-ttu-id="4eabc-267">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="4eabc-267">**TTL**</span></span>|<span data-ttu-id="4eabc-268">**Prio (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="4eabc-268">**Prio**</span></span>|<span data-ttu-id="4eabc-269">**Protocol (Протокол)**</span><span class="sxs-lookup"><span data-stu-id="4eabc-269">**Protocol**</span></span>|<span data-ttu-id="4eabc-270">**Port (Порт)**</span><span class="sxs-lookup"><span data-stu-id="4eabc-270">**Port**</span></span>|<span data-ttu-id="4eabc-271">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="4eabc-271">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4eabc-272">SRV</span><span class="sxs-lookup"><span data-stu-id="4eabc-272">SRV</span></span>|<span data-ttu-id="4eabc-273">sip</span><span class="sxs-lookup"><span data-stu-id="4eabc-273">sip</span></span>|<span data-ttu-id="4eabc-274">1,1</span><span class="sxs-lookup"><span data-stu-id="4eabc-274">1</span></span>|<span data-ttu-id="4eabc-275">Используйте значение по умолчанию (300).</span><span class="sxs-lookup"><span data-stu-id="4eabc-275">Use the default value (300).</span></span>|<span data-ttu-id="4eabc-276">100</span><span class="sxs-lookup"><span data-stu-id="4eabc-276">100</span></span>|<span data-ttu-id="4eabc-277">tls</span><span class="sxs-lookup"><span data-stu-id="4eabc-277">tls</span></span>|<span data-ttu-id="4eabc-278">443</span><span class="sxs-lookup"><span data-stu-id="4eabc-278">443</span></span>|<span data-ttu-id="4eabc-279">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4eabc-279">sipdir.online.lync.com</span></span> <br> <span data-ttu-id="4eabc-280">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="4eabc-280">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="4eabc-281">SRV</span><span class="sxs-lookup"><span data-stu-id="4eabc-281">SRV</span></span>|<span data-ttu-id="4eabc-282">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="4eabc-282">sipfederationtls</span></span>|<span data-ttu-id="4eabc-283">1,1</span><span class="sxs-lookup"><span data-stu-id="4eabc-283">1</span></span>|<span data-ttu-id="4eabc-284">Используйте значение по умолчанию (300).</span><span class="sxs-lookup"><span data-stu-id="4eabc-284">Use the default value (300).</span></span>|<span data-ttu-id="4eabc-285">100</span><span class="sxs-lookup"><span data-stu-id="4eabc-285">100</span></span>|<span data-ttu-id="4eabc-286">tcp</span><span class="sxs-lookup"><span data-stu-id="4eabc-286">tcp</span></span>|<span data-ttu-id="4eabc-287">5061</span><span class="sxs-lookup"><span data-stu-id="4eabc-287">5061</span></span>|<span data-ttu-id="4eabc-288">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4eabc-288">sipfed.online.lync.com</span></span> <br><span data-ttu-id="4eabc-289">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="4eabc-289">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Name — BP — configure – 5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. <span data-ttu-id="4eabc-291">Выберите команду **Add Record** (Добавить запись).</span><span class="sxs-lookup"><span data-stu-id="4eabc-291">Select **Add Record**.</span></span>

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. <span data-ttu-id="4eabc-293">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="4eabc-293">Add the second SRV record:</span></span>

<span data-ttu-id="4eabc-294">Используйте значения из следующей строки приведенной выше таблицы, а затем выберите **Добавить запись** , чтобы добавить вторую запись.</span><span class="sxs-lookup"><span data-stu-id="4eabc-294">Use the values from the next row of the table above, and then select **Add Record** to add the second record.</span></span>

>[!NOTE]
><span data-ttu-id="4eabc-p113">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4eabc-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
