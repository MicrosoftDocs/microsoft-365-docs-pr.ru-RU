---
title: Создание DNS-записей для Office 365 на сайте MyDomain
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9982191d-ed79-46a9-b2e7-317d1a3a9867
description: Узнайте, как проверить свой домен и настроить DNS-записи для электронной почты, Skype для бизнеса Online и других служб в My Domain для Office 365.
ms.openlocfilehash: 5a935ea456175f6d63926c9aa33280c4ec113abd
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42249373"
---
# <a name="create-dns-records-at-mydomain-for-office-365"></a><span data-ttu-id="c7ad7-103">Создание DNS-записей для Office 365 на сайте MyDomain</span><span class="sxs-lookup"><span data-stu-id="c7ad7-103">Create DNS records at MyDomain for Office 365</span></span>


  
 <span data-ttu-id="c7ad7-104">Если вы не нашли то, что вы ищете, обратитесь к разделу **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="c7ad7-p101">На веб-сайте MyDomain не поддерживаются записи SRV, поэтому некоторые функции Skype для бизнеса online и Outlook Web App не будут работать. Если вы управляете своими записями DNS на сайте MyDomain, то независимо от вашего плана Office 365 на доступные службы накладываются [существенные ограничения](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx). В этом случае, возможно, стоит задуматься о переходе к другому поставщику услуг размещения DNS.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-p101">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), and you might want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="c7ad7-107">Если вы хотите управлять своими записями DNS для Office 365 на сайте MyDomain несмотря на ограничения служб, выполните действия, описанные в этой статье, чтобы настроить записи DNS для электронной почты, Skype для бизнеса online и т. д.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-107">If you choose to manage your own Office 365 DNS records at MyDomain despite the service limitations, follow the steps in this article to set up your DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="c7ad7-108">Когда вы добавите эти записи на сайте MyDomain, ваш домен будет настроен для работы со службами Office 365.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-108">After you add these records at MyDomain, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="c7ad7-109">Дополнительные сведения о веб-хостинге и DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="c7ad7-109">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c7ad7-p102">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c7ad7-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="c7ad7-113">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="c7ad7-113">Add a TXT record for verification</span></span>
<span data-ttu-id="c7ad7-114"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="c7ad7-114"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="c7ad7-p103">Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c7ad7-p104">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="c7ad7-119">Чтобы приступить к работе, откройте страницу со своими доменами на сайте MyDomain по предоставленной ссылке.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-119">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="c7ad7-120">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-120">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c7ad7-121">В разделе **My Favorites** (Избранное) выберите **Domain Central** (Центральный домен).</span><span class="sxs-lookup"><span data-stu-id="c7ad7-121">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="c7ad7-122">В поле **Domain** (Домен) выберите доменное имя, которое хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-122">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="c7ad7-123">В строке **Overview** (Обзор) выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-123">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="c7ad7-124">В раскрывающемся списке **Modify** (Изменить) выберите **TXT/SPF Record** (Запись TXT/SPF).</span><span class="sxs-lookup"><span data-stu-id="c7ad7-124">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="c7ad7-125">В разделе **Content** (Контент) в поле для новой записи введите (или скопируйте и вставьте) значение из приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-125">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    ||
    |:-----|
    |<span data-ttu-id="c7ad7-126">**Контент**</span><span class="sxs-lookup"><span data-stu-id="c7ad7-126">**Content**</span></span> <br/> |
    |<span data-ttu-id="c7ad7-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="c7ad7-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="c7ad7-128">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-128">**Note:** This is an example.</span></span> <span data-ttu-id="c7ad7-129">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-129">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="c7ad7-130">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="c7ad7-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="c7ad7-131">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="c7ad7-131">Select **Add**.</span></span>
    
8. <span data-ttu-id="c7ad7-132">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="c7ad7-133">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Office 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-133">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="c7ad7-134">Если Office 365 обнаружит правильную запись TXT, это значит, что домен проверен.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-134">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="c7ad7-135">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="c7ad7-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="c7ad7-136">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="c7ad7-137">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="c7ad7-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="c7ad7-138">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="c7ad7-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c7ad7-p107">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c7ad7-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="c7ad7-142">Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="c7ad7-142">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="c7ad7-143"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="c7ad7-143"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="c7ad7-p108">Чтобы приступить к работе, откройте страницу со своими доменами на сайте MyDomain по предоставленной ссылке. Сначала вам потребуется [выполнить вход](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="c7ad7-p108">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c7ad7-146">В разделе **My Favorites** (Избранное) выберите **Domain Central** (Центральный домен).</span><span class="sxs-lookup"><span data-stu-id="c7ad7-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="c7ad7-147">В поле **Domain** (Домен) выберите доменное имя, которое хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="c7ad7-148">В строке **Overview** (Обзор) выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-148">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="c7ad7-149">В раскрывающемся списке **Modify** (Изменить) выберите **MX Record** (Запись MX).</span><span class="sxs-lookup"><span data-stu-id="c7ad7-149">From the **Modify** drop-down list, choose **MX Record**.</span></span>
    
    ![MyDomain-BP-Configure-2-1](../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. <span data-ttu-id="c7ad7-151">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-151">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="c7ad7-152">**Priority**</span><span class="sxs-lookup"><span data-stu-id="c7ad7-152">**Priority**</span></span>|<span data-ttu-id="c7ad7-153">**Host**</span><span class="sxs-lookup"><span data-stu-id="c7ad7-153">**Host**</span></span>|<span data-ttu-id="c7ad7-154">**Points To** (Указывает на)</span><span class="sxs-lookup"><span data-stu-id="c7ad7-154">**Points To:**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="c7ad7-155">0</span><span class="sxs-lookup"><span data-stu-id="c7ad7-155">0</span></span>  <br/> <span data-ttu-id="c7ad7-156">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="c7ad7-156">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |@  <br/> | <span data-ttu-id="c7ad7-157">*\<ключ_домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c7ad7-157">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="c7ad7-158">**Примечание.**  Получите свой \<*ключ-домена*\> из учетной записи портала Office 365.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-158">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span><span data-ttu-id="c7ad7-159"> > [Как его найти?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="c7ad7-159"> > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![MyDomain-BP-Configure-2-2](../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. <span data-ttu-id="c7ad7-161">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="c7ad7-161">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-2-3](../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. <span data-ttu-id="c7ad7-163">Если в списке указаны другие существующие записи MX, для каждой из них выберите команду **Remove** (Удалить) в столбце **Action** (Действие).</span><span class="sxs-lookup"><span data-stu-id="c7ad7-163">If there are any other existing MX records, select **Remove** in the **Action** column for each one to delete it.</span></span> 
    
    ![MyDomain-BP-Configure-2-4](../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. <span data-ttu-id="c7ad7-165">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-165">Select **OK**.</span></span>
    
    ![MyDomain-BP-Configure-2-5](../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="c7ad7-167">Добавление записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="c7ad7-167">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="c7ad7-168"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="c7ad7-168"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="c7ad7-p110">Чтобы приступить к работе, откройте страницу со своими доменами на сайте MyDomain по предоставленной ссылке. Сначала вам потребуется [выполнить вход](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="c7ad7-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c7ad7-171">В разделе **My Favorites** (Избранное) выберите **Domain Central** (Центральный домен).</span><span class="sxs-lookup"><span data-stu-id="c7ad7-171">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="c7ad7-172">В поле **Domain** (Домен) выберите доменное имя, которое хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-172">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="c7ad7-173">В строке **Overview** (Обзор) выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-173">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="c7ad7-174">В раскрывающемся списке **Modify** (Изменить) выберите **CNAME Alias** (Псевдоним CNAME).</span><span class="sxs-lookup"><span data-stu-id="c7ad7-174">From the **Modify** drop-down list, choose **CNAME Alias**.</span></span>
    
    ![MyDomain-BP-Configure-3-1](../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. <span data-ttu-id="c7ad7-176">Добавьте первую запись CNAME.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-176">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="c7ad7-177">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-177">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="c7ad7-178">**Host**</span><span class="sxs-lookup"><span data-stu-id="c7ad7-178">**Host**</span></span>|<span data-ttu-id="c7ad7-179">**Points To** (Указывает на)</span><span class="sxs-lookup"><span data-stu-id="c7ad7-179">**Points To:**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="c7ad7-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="c7ad7-180">autodiscover</span></span>  <br/> |<span data-ttu-id="c7ad7-181">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c7ad7-181">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="c7ad7-182">sip</span><span class="sxs-lookup"><span data-stu-id="c7ad7-182">sip</span></span>  <br/> |<span data-ttu-id="c7ad7-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c7ad7-183">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="c7ad7-184">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="c7ad7-184">lyncdiscover</span></span>  <br/> |<span data-ttu-id="c7ad7-185">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c7ad7-185">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="c7ad7-186">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="c7ad7-186">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="c7ad7-187">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="c7ad7-187">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="c7ad7-188">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="c7ad7-188">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="c7ad7-189">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c7ad7-189">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. <span data-ttu-id="c7ad7-191">Нажмите **Add** (Добавить), чтобы добавить первую запись.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-191">Select **Add** to add the first record.</span></span> 
    
    ![MyDomain-BP-Configure-3-3](../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. <span data-ttu-id="c7ad7-193">Добавьте вторую запись CNAME.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-193">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="c7ad7-194">Введите значения из второй строки приведенной выше таблицы, а затем нажмите кнопку **Add** (Добавить), чтобы создать вторую запись.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-194">Use the values from the second row of the table above, and then select **Add** to add the second record.</span></span> 
    
    <span data-ttu-id="c7ad7-195">Точно так же добавьте остальные записи, используя значения из третьей, четвертой, пятой и шестой строк таблицы.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-195">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="c7ad7-196">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="c7ad7-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="c7ad7-197"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="c7ad7-197"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="c7ad7-198">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="c7ad7-199">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="c7ad7-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="c7ad7-201">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-201">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="c7ad7-202">Нужны примеры?</span><span class="sxs-lookup"><span data-stu-id="c7ad7-202">Need examples?</span></span> <span data-ttu-id="c7ad7-203">Ознакомьтесь с этими [сведениями и образцами записей SPF](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="c7ad7-203">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="c7ad7-204">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="c7ad7-204">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="c7ad7-205">Чтобы приступить к работе, откройте страницу со своими доменами на сайте MyDomain по предоставленной ссылке.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-205">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="c7ad7-206">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-206">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c7ad7-207">В разделе **My Favorites** (Избранное) выберите **Domain Central** (Центральный домен).</span><span class="sxs-lookup"><span data-stu-id="c7ad7-207">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="c7ad7-208">В поле **Domain** (Домен) выберите доменное имя, которое хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-208">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="c7ad7-209">В строке **Overview** (Обзор) выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-209">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="c7ad7-210">В раскрывающемся списке **Modify** (Изменить) выберите **TXT/SPF Record** (Запись TXT/SPF).</span><span class="sxs-lookup"><span data-stu-id="c7ad7-210">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
    ![MyDomain-BP-Configure-4-1](../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. <span data-ttu-id="c7ad7-212">В разделе **Content** (Контент) в поле для новой записи введите (или скопируйте и вставьте) значение из приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-212">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    |<span data-ttu-id="c7ad7-213">**Контент**</span><span class="sxs-lookup"><span data-stu-id="c7ad7-213">**Content**</span></span>|
    |:-----|
    |<span data-ttu-id="c7ad7-214">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="c7ad7-214">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="c7ad7-215">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="c7ad7-215">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![MyDomain-BP-Configure-4-2](../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. <span data-ttu-id="c7ad7-217">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="c7ad7-217">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-4-3](../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="c7ad7-219">Добавление двух записей SRV, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="c7ad7-219">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="c7ad7-220"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="c7ad7-220"><a name="BKMK_add_SRV"> </a></span></span>

> [!CAUTION]
> <span data-ttu-id="c7ad7-p113">На веб-сайте MyDomain не поддерживаются записи SRV, поэтому некоторые функции Skype для бизнеса online и Outlook Web App не будут работать. Если вы управляете своими записями DNS на сайте MyDomain, то независимо от вашего плана Office 365 на доступные службы накладываются [существенные ограничения](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx). В этом случае, возможно, стоит задуматься о переходе к другому поставщику услуг размещения DNS.</span><span class="sxs-lookup"><span data-stu-id="c7ad7-p113">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), and you might want to switch to a different DNS hosting provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c7ad7-p114">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c7ad7-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
