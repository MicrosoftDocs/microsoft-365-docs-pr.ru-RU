---
title: Создание записей DNS в доменах Crazy для Майкрософт
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
ms.assetid: 6386d63e-b78f-4736-90e7-b99a2c116a9f
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб в доменах Crazy для Майкрософт.
ms.openlocfilehash: 5a5a0f4c92e14bdfd6c54249cd66c9e88abee075
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939335"
---
# <a name="create-dns-records-at-crazy-domains-for-microsoft"></a><span data-ttu-id="88da0-103">Создание записей DNS в доменах Crazy для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="88da0-103">Create DNS records at Crazy Domains for Microsoft</span></span>

 <span data-ttu-id="88da0-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="88da0-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="88da0-105">Если ваш поставщик услуг размещения DNS  Crazy Domains, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="88da0-105">If Crazy Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="88da0-106">Когда вы добавите эти записи на сайте Crazy Domains, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="88da0-106">After you add these records at Crazy Domains, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="88da0-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="88da0-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="88da0-110">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="88da0-110">Add a TXT record for verification</span></span>
<span data-ttu-id="88da0-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="88da0-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="88da0-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="88da0-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="88da0-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="88da0-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="88da0-p104">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Crazy Domains по [этой ссылке](https://manage.crazydomains.com/members/domains/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="88da0-p104">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="88da0-119">В разделе " **Моя учетная запись** " выберите пункт **домены**.</span><span class="sxs-lookup"><span data-stu-id="88da0-119">In the **My Account** section, select **Domains**.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="88da0-121">На странице **Domain Names** (доменные имена) в разделе **Domain (домен** ) выберите имя обновляемого домена.</span><span class="sxs-lookup"><span data-stu-id="88da0-121">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![Кразидомаинс — BP — configure – 1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="88da0-123">В разделе **параметры DNS** выберите значок раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="88da0-123">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![Кразидомаинс — BP — configure – 1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="88da0-125">Выберите команду **Add Record** (Добавить запись).</span><span class="sxs-lookup"><span data-stu-id="88da0-125">Select **Add Record**.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="88da0-127">В раскрывающемся списке **Add Record** (Добавить запись) выберите пункт **TXT Record** (Запись TXT).</span><span class="sxs-lookup"><span data-stu-id="88da0-127">Choose **TXT Record** from the **Add Record** drop-down list.</span></span> 
    
    ![Кразидомаинс — BP — Verify – 1-1](../../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. <span data-ttu-id="88da0-129">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="88da0-129">Select **Add**.</span></span>
    
    ![Кразидомаинс — BP — Verify – 1-2](../../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. <span data-ttu-id="88da0-131">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="88da0-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="88da0-132">**Sub Domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="88da0-132">**Sub Domain**</span></span>|<span data-ttu-id="88da0-133">**Text Record (Текстовая запись)**</span><span class="sxs-lookup"><span data-stu-id="88da0-133">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="88da0-134">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="88da0-134">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="88da0-135">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="88da0-135">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="88da0-136">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="88da0-136">**Note:** This is an example.</span></span> <span data-ttu-id="88da0-137">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="88da0-137">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="88da0-138">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="88da0-138">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Кразидомаинс — BP — Verify – 1-3](../../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. <span data-ttu-id="88da0-140">Нажмите кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="88da0-140">Select **Update**.</span></span>
    
    ![Кразидомаинс — BP — Verify – 1-4](../../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. <span data-ttu-id="88da0-142">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="88da0-142">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="88da0-143">Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.</span><span class="sxs-lookup"><span data-stu-id="88da0-143">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="88da0-144">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="88da0-144">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="88da0-145">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="88da0-145">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="88da0-146">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="88da0-146">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="88da0-147">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="88da0-147">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="88da0-148">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="88da0-148">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="88da0-p106">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="88da0-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="88da0-152">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="88da0-152">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="88da0-153"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="88da0-153"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="88da0-p107">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Crazy Domains по [этой ссылке](https://manage.crazydomains.com/members/domains/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="88da0-p107">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="88da0-157">В разделе " **Моя учетная запись** " выберите пункт **домены**.</span><span class="sxs-lookup"><span data-stu-id="88da0-157">In the **My Account** section, select **Domains**.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="88da0-159">На странице **Domain Names** (доменные имена) в разделе **Domain (домен** ) выберите имя обновляемого домена.</span><span class="sxs-lookup"><span data-stu-id="88da0-159">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![Кразидомаинс — BP — configure – 1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="88da0-161">В разделе **параметры DNS** выберите значок раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="88da0-161">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![Кразидомаинс — BP — configure – 1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="88da0-163">Выберите команду **Add Record** (Добавить запись).</span><span class="sxs-lookup"><span data-stu-id="88da0-163">Select **Add Record**.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="88da0-165">В раскрывающемся списке **Add Record:** (Добавить запись) выберите пункт **MX Record** (Запись MX).</span><span class="sxs-lookup"><span data-stu-id="88da0-165">Choose **MX Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![Кразидомаинс — BP — configure – 2-1](../../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. <span data-ttu-id="88da0-167">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="88da0-167">Select **Add**.</span></span>
    
    ![Кразидомаинс — BP — configure – 2-2](../../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. <span data-ttu-id="88da0-169">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="88da0-169">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="88da0-170">В раскрывающемся списке выберите значение **Priority (приоритет** ).</span><span class="sxs-lookup"><span data-stu-id="88da0-170">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="88da0-171">**Mail For Zone (Почта для зоны)**</span><span class="sxs-lookup"><span data-stu-id="88da0-171">**Mail For Zone**</span></span>|<span data-ttu-id="88da0-172">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="88da0-172">**Priority**</span></span>|<span data-ttu-id="88da0-173">**Assigned To Server (Назначено серверу)**</span><span class="sxs-lookup"><span data-stu-id="88da0-173">**Assigned To Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="88da0-174">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="88da0-174">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="88da0-175">1,1</span><span class="sxs-lookup"><span data-stu-id="88da0-175">1</span></span>  <br/> <span data-ttu-id="88da0-176">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="88da0-176">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="88da0-177">*\<ключ_домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="88da0-177">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="88da0-178">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="88da0-178">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="88da0-179">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="88da0-179">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Кразидомаинс — BP — configure – 2-3](../../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. <span data-ttu-id="88da0-181">Нажмите кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="88da0-181">Select **Update**.</span></span>
    
    ![Кразидомаинс — BP — configure – 2-4](../../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. <span data-ttu-id="88da0-183">Если в разделе **MX Record (запись MX** ) указаны другие записи MX, выберите **изменить** для одной из этих записей.</span><span class="sxs-lookup"><span data-stu-id="88da0-183">If there are any other MX records listed in the **MX Record** section, select **Modify** for one of those records.</span></span> 
    
    ![Кразидомаинс — BP — configure – 2-5](../../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. <span data-ttu-id="88da0-185">Выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="88da0-185">Select **Delete**.</span></span>
    
    ![Кразидомаинс — BP — configure – 2-6](../../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. <span data-ttu-id="88da0-187">Нажмите кнопку **Обновить** , чтобы подтвердить удаление.</span><span class="sxs-lookup"><span data-stu-id="88da0-187">Select **Update** to confirm the deletion.</span></span> 
    
    ![Кразидомаинс — BP — configure – 2-7](../../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. <span data-ttu-id="88da0-189">Повторите эти действия для удаления из списка всех остальных записей MX, кроме той, которую вы добавили на предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="88da0-189">Use the same process to remove any other MX records in the list, until only the one that you added earlier in this procedure remains.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="88da0-190">Добавление шести записей CNAME, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="88da0-190">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="88da0-191"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="88da0-191"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="88da0-p109">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Crazy Domains по [этой ссылке](https://manage.crazydomains.com/members/domains/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="88da0-p109">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="88da0-195">В разделе " **Моя учетная запись** " выберите пункт **домены**.</span><span class="sxs-lookup"><span data-stu-id="88da0-195">In the **My Account** section, select **Domains**.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="88da0-197">На странице **Domain Names** (доменные имена) в разделе **Domain (домен** ) выберите имя обновляемого домена.</span><span class="sxs-lookup"><span data-stu-id="88da0-197">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![Кразидомаинс — BP — configure – 1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="88da0-199">В разделе **параметры DNS** выберите значок раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="88da0-199">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![Кразидомаинс — BP — configure – 1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="88da0-201">Выберите команду **Add Record** (Добавить запись).</span><span class="sxs-lookup"><span data-stu-id="88da0-201">Select **Add Record**.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="88da0-203">В раскрывающемся списке **Add Record:** (Добавить запись) выберите пункт **CNAME Record** (Запись CNAME).</span><span class="sxs-lookup"><span data-stu-id="88da0-203">Choose **CNAME Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![Кразидомаинс — BP — configure – 3-1](../../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. <span data-ttu-id="88da0-205">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="88da0-205">Select **Add**.</span></span>
    
    ![Кразидомаинс — BP — configure – 3-2](../../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. <span data-ttu-id="88da0-207">Добавьте первую из шести записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="88da0-207">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="88da0-208">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="88da0-208">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="88da0-209">**Sub Domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="88da0-209">**Sub Domain**</span></span>|<span data-ttu-id="88da0-210">**Alias for (Псевдоним для)**</span><span class="sxs-lookup"><span data-stu-id="88da0-210">**Alias for**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="88da0-211">autodiscover</span><span class="sxs-lookup"><span data-stu-id="88da0-211">autodiscover</span></span>  <br/> |<span data-ttu-id="88da0-212">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="88da0-212">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="88da0-213">sip</span><span class="sxs-lookup"><span data-stu-id="88da0-213">sip</span></span>  <br/> |<span data-ttu-id="88da0-214">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="88da0-214">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="88da0-215">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="88da0-215">lyncdiscover</span></span>  <br/> |<span data-ttu-id="88da0-216">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="88da0-216">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="88da0-217">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="88da0-217">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="88da0-218">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="88da0-218">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="88da0-219">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="88da0-219">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="88da0-220">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="88da0-220">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Кразидомаинс — BP — configure – 3-3](../../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. <span data-ttu-id="88da0-222">Выберите **Добавить запись CNAME**.</span><span class="sxs-lookup"><span data-stu-id="88da0-222">Select **Add CNAME Record**.</span></span>
    
    ![Кразидомаинс — BP — configure – 3-4](../../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. <span data-ttu-id="88da0-224">Добавьте вторую запись CNAME.</span><span class="sxs-lookup"><span data-stu-id="88da0-224">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="88da0-225">В поля для новой записи используйте значения из следующей строки таблицы, а затем снова выберите **Добавить запись CNAME**.</span><span class="sxs-lookup"><span data-stu-id="88da0-225">In the boxes for the new record, use the values from the next row in the table, and then again select **Add CNAME Record**.</span></span>
    
    <span data-ttu-id="88da0-226">Повторяйте эти действия, пока не будут созданы все шесть записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="88da0-226">Repeat this process until you have created all six CNAME records.</span></span>
    
11. <span data-ttu-id="88da0-227">Нажмите кнопку **Обновить** , чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="88da0-227">Select **Update** to save your changes.</span></span> 
    
    ![Кразидомаинс — BP — configure – 3-5](../../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="88da0-229">Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама</span><span class="sxs-lookup"><span data-stu-id="88da0-229">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="88da0-230"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="88da0-230"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="88da0-231">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="88da0-231">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="88da0-232">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="88da0-232">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="88da0-233">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="88da0-233">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="88da0-234">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="88da0-234">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="88da0-p111">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Crazy Domains по [этой ссылке](https://manage.crazydomains.com/members/domains/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="88da0-p111">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="88da0-238">В разделе " **Моя учетная запись** " выберите пункт **домены**.</span><span class="sxs-lookup"><span data-stu-id="88da0-238">In the **My Account** section, select **Domains**.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="88da0-240">На странице **Domain Names** (доменные имена) в разделе **Domain (домен** ) выберите имя обновляемого домена.</span><span class="sxs-lookup"><span data-stu-id="88da0-240">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![Кразидомаинс — BP — configure – 1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="88da0-242">В разделе **параметры DNS** выберите значок раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="88da0-242">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![Кразидомаинс — BP — configure – 1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="88da0-244">Выберите команду **Add Record** (Добавить запись).</span><span class="sxs-lookup"><span data-stu-id="88da0-244">Select **Add Record**.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="88da0-246">В раскрывающемся списке **Add Record:** (Добавить запись) выберите пункт **TXT Record** (Запись TXT).</span><span class="sxs-lookup"><span data-stu-id="88da0-246">Choose **TXT Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![Кразидомаинс — BP — configure – 4-1](../../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. <span data-ttu-id="88da0-248">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="88da0-248">Select **Add**.</span></span>
    
    ![Кразидомаинс — BP — configure – 4-2](../../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. <span data-ttu-id="88da0-250">В поля для новой записи введите или вставьте значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="88da0-250">In the boxes for the new record, type or paste the values from the following table.</span></span>
    
    |<span data-ttu-id="88da0-251">**Sub Domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="88da0-251">**Sub Domain**</span></span>|<span data-ttu-id="88da0-252">**Text Record (Текстовая запись)**</span><span class="sxs-lookup"><span data-stu-id="88da0-252">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="88da0-253">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="88da0-253">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="88da0-254">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="88da0-254">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="88da0-255">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="88da0-255">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Кразидомаинс — BP — configure – 4-3](../../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. <span data-ttu-id="88da0-257">Нажмите кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="88da0-257">Select **Update**.</span></span>
    
    ![Кразидомаинс — BP — configure – 4-4](../../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="88da0-259">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="88da0-259">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="88da0-260"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="88da0-260"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="88da0-p112">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Crazy Domains по [этой ссылке](https://manage.crazydomains.com/members/domains/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="88da0-p112">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="88da0-264">В разделе " **Моя учетная запись** " выберите пункт **домены**.</span><span class="sxs-lookup"><span data-stu-id="88da0-264">In the **My Account** section, select **Domains**.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="88da0-266">На странице **Domain Names** (доменные имена) в разделе **Domain (домен** ) выберите имя обновляемого домена.</span><span class="sxs-lookup"><span data-stu-id="88da0-266">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![Кразидомаинс — BP — configure – 1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="88da0-268">В разделе **параметры DNS** выберите значок раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="88da0-268">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![Кразидомаинс — BP — configure – 1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="88da0-270">Выберите команду **Add Record** (Добавить запись).</span><span class="sxs-lookup"><span data-stu-id="88da0-270">Select **Add Record**.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="88da0-272">В раскрывающемся списке **Add Record:** (Добавить запись) выберите пункт **SRV Record** (Запись SRV).</span><span class="sxs-lookup"><span data-stu-id="88da0-272">Choose **SRV Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![Кразидомаинс — BP — configure – 5-1](../../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. <span data-ttu-id="88da0-274">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="88da0-274">Select **Add**.</span></span>
    
    ![Кразидомаинс — BP — configure – 5-2](../../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. <span data-ttu-id="88da0-276">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="88da0-276">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="88da0-277">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="88da0-277">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="88da0-278">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="88da0-278">**Record Type**</span></span>|<span data-ttu-id="88da0-279">**Sub Domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="88da0-279">**Sub Domain**</span></span>|<span data-ttu-id="88da0-280">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="88da0-280">**Priority**</span></span>|<span data-ttu-id="88da0-281">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="88da0-281">**Weight**</span></span>|<span data-ttu-id="88da0-282">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="88da0-282">**Port**</span></span>|<span data-ttu-id="88da0-283">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="88da0-283">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="88da0-284">SRV Record (Запись SRV)</span><span class="sxs-lookup"><span data-stu-id="88da0-284">SRV Record</span></span>  <br/> |<span data-ttu-id="88da0-285">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="88da0-285">_sip._tls</span></span>  <br/> |<span data-ttu-id="88da0-286">100</span><span class="sxs-lookup"><span data-stu-id="88da0-286">100</span></span>  <br/> |<span data-ttu-id="88da0-287">1,1</span><span class="sxs-lookup"><span data-stu-id="88da0-287">1</span></span>  <br/> |<span data-ttu-id="88da0-288">443</span><span class="sxs-lookup"><span data-stu-id="88da0-288">443</span></span>  <br/> |<span data-ttu-id="88da0-289">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="88da0-289">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="88da0-290">SRV Record (Запись SRV)</span><span class="sxs-lookup"><span data-stu-id="88da0-290">SRV Record</span></span>  <br/> |<span data-ttu-id="88da0-291">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="88da0-291">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="88da0-292">100</span><span class="sxs-lookup"><span data-stu-id="88da0-292">100</span></span>  <br/> |<span data-ttu-id="88da0-293">1,1</span><span class="sxs-lookup"><span data-stu-id="88da0-293">1</span></span>  <br/> |<span data-ttu-id="88da0-294">5061</span><span class="sxs-lookup"><span data-stu-id="88da0-294">5061</span></span>  <br/> |<span data-ttu-id="88da0-295">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="88da0-295">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Кразидомаинс — BP — configure – 5-3](../../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. <span data-ttu-id="88da0-297">Выберите **Добавить запись SRV**.</span><span class="sxs-lookup"><span data-stu-id="88da0-297">Select **Add SRV Record**.</span></span>
    
    ![Кразидомаинс — BP — configure – 5-4](../../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. <span data-ttu-id="88da0-299">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="88da0-299">Add the other SRV record.</span></span>
    
    <span data-ttu-id="88da0-300">В поля для новой записи введите значения из второй строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="88da0-300">In the boxes for the new record, use the values from the second row in the table.</span></span>
    
11. <span data-ttu-id="88da0-301">Нажмите кнопку **Обновить** , чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="88da0-301">Select **Update** to save your changes.</span></span> 
    
    ![Кразидомаинс — BP — configure – 5-5](../../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> <span data-ttu-id="88da0-p113">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="88da0-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
