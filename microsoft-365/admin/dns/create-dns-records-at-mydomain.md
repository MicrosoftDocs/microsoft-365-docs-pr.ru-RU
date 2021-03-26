---
title: Создать записи DNS на сайте MyDomain для работы с продуктами корпорации Майкрософт
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
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
ms.assetid: 9982191d-ed79-46a9-b2e7-317d1a3a9867
description: Узнайте, как проверить свой домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб корпорации Майкрософт на сайте My Domain.
ms.openlocfilehash: f306e84509ddbea9f2e7bba598f0f490080e9f2a
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2021
ms.locfileid: "51221971"
---
# <a name="create-dns-records-at-mydomain-for-microsoft"></a><span data-ttu-id="04620-103">Создать записи DNS на сайте MyDomain для работы с продуктами корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="04620-103">Create DNS records at MyDomain for Microsoft</span></span>


  
 <span data-ttu-id="04620-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="04620-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="04620-p101">На веб-сайте MyDomain не поддерживаются записи SRV, поэтому некоторые функции Skype для бизнеса Online и Outlook Web App работать не будут. Если вы управляете своими записями DNS на сайте MyDomain, то независимо от того, на какой план корпорации Майкрософт вы подписаны, существуют [существенные ограничения в работе служб](../setup/domains-faq.yml). Поэтому, возможно, стоит задуматься о переходе к другому поставщику услуг размещения DNS.</span><span class="sxs-lookup"><span data-stu-id="04620-p101">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](../setup/domains-faq.yml), and you might want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="04620-107">Если вы хотите управлять своими записями DNS при работе с продуктами корпорации Майкрософт на сайте MyDomain несмотря на ограничения в работе служб, выполните действия, описанные в этой статье, чтобы настроить записи DNS для электронной почты, Skype для бизнеса Online и т. д.</span><span class="sxs-lookup"><span data-stu-id="04620-107">If you choose to manage your own Microsoft DNS records at MyDomain despite the service limitations, follow the steps in this article to set up your DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="04620-108">Когда вы добавите эти записи на сайте MyDomain, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="04620-108">After you add these records at MyDomain, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="04620-p102">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="04620-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="04620-112">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="04620-112">Add a TXT record for verification</span></span>
<span data-ttu-id="04620-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="04620-113"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="04620-p103">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="04620-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="04620-p104">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="04620-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="04620-p105">Чтобы приступить к работе, откройте страницу со своими доменами на сайте MyDomain по предоставленной ссылке. Сначала вам потребуется [выполнить вход](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="04620-p105">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="04620-120">В разделе **My Favorites** (Избранное) выберите **Domain Central** (Центральный домен).</span><span class="sxs-lookup"><span data-stu-id="04620-120">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="04620-121">В поле **Domain** (Домен) выберите доменное имя, которое хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="04620-121">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="04620-122">В строке **Overview** (Обзор) выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="04620-122">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="04620-123">В раскрывающемся списке **Modify** (Изменить) выберите **TXT/SPF Record** (Запись TXT/SPF).</span><span class="sxs-lookup"><span data-stu-id="04620-123">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="04620-124">В разделе **Content** (Контент) в поле для новой записи введите (или скопируйте и вставьте) значение из приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="04620-124">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    ||
    |:-----|
    |<span data-ttu-id="04620-125">**Контент**</span><span class="sxs-lookup"><span data-stu-id="04620-125">**Content**</span></span> <br/> |
    |<span data-ttu-id="04620-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="04620-126">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="04620-127">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="04620-127">**Note:** This is an example.</span></span> <span data-ttu-id="04620-128">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="04620-128">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="04620-129">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="04620-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="04620-130">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="04620-130">Select **Add**.</span></span>
    
8. <span data-ttu-id="04620-131">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="04620-131">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="04620-132">Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.</span><span class="sxs-lookup"><span data-stu-id="04620-132">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="04620-133">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="04620-133">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="04620-134">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="04620-134">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="04620-135">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="04620-135">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="04620-136">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="04620-136">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="04620-137">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="04620-137">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="04620-p107">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="04620-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="04620-141">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="04620-141">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="04620-142"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="04620-142"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="04620-p108">Чтобы приступить к работе, откройте страницу со своими доменами на сайте MyDomain по предоставленной ссылке. Сначала вам потребуется [выполнить вход](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="04620-p108">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="04620-145">В разделе **My Favorites** (Избранное) выберите **Domain Central** (Центральный домен).</span><span class="sxs-lookup"><span data-stu-id="04620-145">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="04620-146">В поле **Domain** (Домен) выберите доменное имя, которое хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="04620-146">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="04620-147">В строке **Overview** (Обзор) выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="04620-147">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="04620-148">В раскрывающемся списке **Modify** (Изменить) выберите **MX Record** (Запись MX).</span><span class="sxs-lookup"><span data-stu-id="04620-148">From the **Modify** drop-down list, choose **MX Record**.</span></span>
    
    ![MyDomain-BP-Configure-2-1](../../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. <span data-ttu-id="04620-150">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="04620-150">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="04620-151">**Priority**</span><span class="sxs-lookup"><span data-stu-id="04620-151">**Priority**</span></span>|<span data-ttu-id="04620-152">**Host**</span><span class="sxs-lookup"><span data-stu-id="04620-152">**Host**</span></span>|<span data-ttu-id="04620-153">**Points To** (Указывает на)</span><span class="sxs-lookup"><span data-stu-id="04620-153">**Points To:**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="04620-154">0</span><span class="sxs-lookup"><span data-stu-id="04620-154">0</span></span>  <br/> <span data-ttu-id="04620-155">Дополнительные сведения о приоритете см. в статье [Что такое приоритет записей MX?](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="04620-155">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |@  <br/> | <span data-ttu-id="04620-156">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="04620-156">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="04620-157">**Примечание.**  Получите свой \<*domain-key*\> из учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="04620-157">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span><span data-ttu-id="04620-158"> > [Как его найти?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="04620-158"> > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![MyDomain-BP-Configure-2-2](../../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. <span data-ttu-id="04620-160">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="04620-160">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-2-3](../../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. <span data-ttu-id="04620-162">Если в списке указаны другие существующие записи MX, для каждой из них выберите команду **Remove** (Удалить) в столбце **Action** (Действие).</span><span class="sxs-lookup"><span data-stu-id="04620-162">If there are any other existing MX records, select **Remove** in the **Action** column for each one to delete it.</span></span> 
    
    ![MyDomain-BP-Configure-2-4](../../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. <span data-ttu-id="04620-164">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="04620-164">Select **OK**.</span></span>
    
    ![MyDomain-BP-Configure-2-5](../../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="04620-166">Добавление записей CNAME, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="04620-166">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="04620-167"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="04620-167"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="04620-p110">Чтобы приступить к работе, откройте страницу со своими доменами на сайте MyDomain по предоставленной ссылке. Сначала вам потребуется [выполнить вход](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="04620-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="04620-170">В разделе **My Favorites** (Избранное) выберите **Domain Central** (Центральный домен).</span><span class="sxs-lookup"><span data-stu-id="04620-170">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="04620-171">В поле **Domain** (Домен) выберите доменное имя, которое хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="04620-171">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="04620-172">В строке **Overview** (Обзор) выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="04620-172">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="04620-173">В раскрывающемся списке **Modify** (Изменить) выберите **CNAME Alias** (Псевдоним CNAME).</span><span class="sxs-lookup"><span data-stu-id="04620-173">From the **Modify** drop-down list, choose **CNAME Alias**.</span></span>
    
    ![MyDomain-BP-Configure-3-1](../../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. <span data-ttu-id="04620-175">Добавьте первую запись CNAME.</span><span class="sxs-lookup"><span data-stu-id="04620-175">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="04620-176">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="04620-176">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="04620-177">**Host**</span><span class="sxs-lookup"><span data-stu-id="04620-177">**Host**</span></span>|<span data-ttu-id="04620-178">**Points To** (Указывает на)</span><span class="sxs-lookup"><span data-stu-id="04620-178">**Points To:**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="04620-179">autodiscover</span><span class="sxs-lookup"><span data-stu-id="04620-179">autodiscover</span></span>  <br/> |<span data-ttu-id="04620-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="04620-180">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="04620-181">sip</span><span class="sxs-lookup"><span data-stu-id="04620-181">sip</span></span>  <br/> |<span data-ttu-id="04620-182">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="04620-182">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="04620-183">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="04620-183">lyncdiscover</span></span>  <br/> |<span data-ttu-id="04620-184">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="04620-184">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="04620-185">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="04620-185">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="04620-186">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="04620-186">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="04620-187">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="04620-187">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="04620-188">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="04620-188">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. <span data-ttu-id="04620-190">Нажмите **Add** (Добавить), чтобы добавить первую запись.</span><span class="sxs-lookup"><span data-stu-id="04620-190">Select **Add** to add the first record.</span></span> 
    
    ![MyDomain-BP-Configure-3-3](../../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. <span data-ttu-id="04620-192">Добавьте вторую запись CNAME.</span><span class="sxs-lookup"><span data-stu-id="04620-192">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="04620-193">Введите значения из второй строки приведенной выше таблицы, а затем нажмите кнопку **Add** (Добавить), чтобы создать вторую запись.</span><span class="sxs-lookup"><span data-stu-id="04620-193">Use the values from the second row of the table above, and then select **Add** to add the second record.</span></span> 
    
    <span data-ttu-id="04620-194">Точно так же добавьте остальные записи, используя значения из третьей, четвертой, пятой и шестой строк таблицы.</span><span class="sxs-lookup"><span data-stu-id="04620-194">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="04620-195">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="04620-195">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="04620-196"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="04620-196"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="04620-197">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="04620-197">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="04620-198">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="04620-198">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="04620-199">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="04620-199">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="04620-200">Вместо этого добавьте необходимые значения для продуктов корпорации Майкрософт в текущую запись. Таким образом, в одной записи SPF будут указаны оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="04620-200">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="04620-201">Нужны примеры?</span><span class="sxs-lookup"><span data-stu-id="04620-201">Need examples?</span></span> <span data-ttu-id="04620-202">Ознакомьтесь с этими [записями системы внешних доменных имен для продуктов корпорации Майкрософт](../../enterprise/external-domain-name-system-records.md).</span><span class="sxs-lookup"><span data-stu-id="04620-202">Check out these [External Domain Name System records for Microsoft](../../enterprise/external-domain-name-system-records.md).</span></span> <span data-ttu-id="04620-203">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="04620-203">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="04620-p112">Чтобы приступить к работе, откройте страницу со своими доменами на сайте MyDomain по предоставленной ссылке. Сначала вам потребуется [выполнить вход](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="04620-p112">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="04620-206">В разделе **My Favorites** (Избранное) выберите **Domain Central** (Центральный домен).</span><span class="sxs-lookup"><span data-stu-id="04620-206">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="04620-207">В поле **Domain** (Домен) выберите доменное имя, которое хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="04620-207">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="04620-208">В строке **Overview** (Обзор) выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="04620-208">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="04620-209">В раскрывающемся списке **Modify** (Изменить) выберите **TXT/SPF Record** (Запись TXT/SPF).</span><span class="sxs-lookup"><span data-stu-id="04620-209">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
    ![MyDomain-BP-Configure-4-1](../../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. <span data-ttu-id="04620-211">В разделе **Content** (Контент) в поле для новой записи введите (или скопируйте и вставьте) значение из приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="04620-211">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    |<span data-ttu-id="04620-212">**Контент**</span><span class="sxs-lookup"><span data-stu-id="04620-212">**Content**</span></span>|
    |:-----|
    |<span data-ttu-id="04620-213">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="04620-213">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="04620-214">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="04620-214">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![MyDomain-BP-Configure-4-2](../../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. <span data-ttu-id="04620-216">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="04620-216">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-4-3](../../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="04620-218">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="04620-218">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="04620-219"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="04620-219"><a name="BKMK_add_SRV"> </a></span></span>

> [!CAUTION]
> <span data-ttu-id="04620-p113">На веб-сайте MyDomain не поддерживаются записи SRV, поэтому некоторые функции Skype для бизнеса Online и Outlook Web App работать не будут. Если вы управляете своими записями DNS на сайте MyDomain, то независимо от того, на какой план корпорации Майкрософт вы подписаны, существуют [существенные ограничения в работе служб](../setup/domains-faq.yml). Поэтому, возможно, стоит задуматься о переходе к другому поставщику услуг размещения DNS.</span><span class="sxs-lookup"><span data-stu-id="04620-p113">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](../setup/domains-faq.yml), and you might want to switch to a different DNS hosting provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="04620-p114">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="04620-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
