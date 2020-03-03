---
title: Создание записей DNS для Office 365 на сайте Crazy Domains
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб в доменах Crazy для Office 365.
ms.openlocfilehash: 157c33a52403efbefe673bf11465de525ffb4f33
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2020
ms.locfileid: "42351160"
---
# <a name="create-dns-records-at-crazy-domains-for-office-365"></a><span data-ttu-id="833c1-103">Создание записей DNS для Office 365 на сайте Crazy Domains</span><span class="sxs-lookup"><span data-stu-id="833c1-103">Create DNS records at Crazy Domains for Office 365</span></span>

 <span data-ttu-id="833c1-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="833c1-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="833c1-105">Если ваш поставщик услуг размещения DNS  Crazy Domains, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="833c1-105">If Crazy Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="833c1-106">Когда вы добавите эти записи на сайте Crazy Domains, ваш домен будет настроен для работы со службами Office 365.</span><span class="sxs-lookup"><span data-stu-id="833c1-106">After you add these records at Crazy Domains, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="833c1-107">Дополнительные сведения о веб-хостинге и DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="833c1-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="833c1-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="833c1-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="833c1-111">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="833c1-111">Add a TXT record for verification</span></span>
<span data-ttu-id="833c1-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="833c1-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="833c1-p102">Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="833c1-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="833c1-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="833c1-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="833c1-p104">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Crazy Domains по [этой ссылке](https://manage.crazydomains.com/members/domains/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="833c1-p104">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="833c1-120">В разделе " **Моя учетная запись** " выберите пункт **домены**.</span><span class="sxs-lookup"><span data-stu-id="833c1-120">In the **My Account** section, select **Domains**.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="833c1-122">На странице **Domain Names** (доменные имена) в разделе **Domain (домен** ) выберите имя обновляемого домена.</span><span class="sxs-lookup"><span data-stu-id="833c1-122">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![Кразидомаинс — BP — configure – 1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="833c1-124">В разделе **параметры DNS** выберите значок раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="833c1-124">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![Кразидомаинс — BP — configure – 1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="833c1-126">Выберите команду **Add Record** (Добавить запись).</span><span class="sxs-lookup"><span data-stu-id="833c1-126">Select **Add Record**.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="833c1-128">В раскрывающемся списке **Add Record** (Добавить запись) выберите пункт **TXT Record** (Запись TXT).</span><span class="sxs-lookup"><span data-stu-id="833c1-128">Choose **TXT Record** from the **Add Record** drop-down list.</span></span> 
    
    ![Кразидомаинс — BP — Verify – 1-1](../../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. <span data-ttu-id="833c1-130">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="833c1-130">Select **Add**.</span></span>
    
    ![Кразидомаинс — BP — Verify – 1-2](../../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. <span data-ttu-id="833c1-132">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="833c1-132">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="833c1-133">**Sub Domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="833c1-133">**Sub Domain**</span></span>|<span data-ttu-id="833c1-134">**Text Record (Текстовая запись)**</span><span class="sxs-lookup"><span data-stu-id="833c1-134">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="833c1-135">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="833c1-135">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="833c1-136">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="833c1-136">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="833c1-p105">**Примечание.** Это пример. Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.           [Где это находится?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="833c1-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![Кразидомаинс — BP — Verify – 1-3](../../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. <span data-ttu-id="833c1-141">Нажмите кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="833c1-141">Select **Update**.</span></span>
    
    ![Кразидомаинс — BP — Verify – 1-4](../../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. <span data-ttu-id="833c1-143">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="833c1-143">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="833c1-144">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Office 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="833c1-144">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="833c1-145">Если Office 365 обнаружит правильную запись TXT, это значит, что домен проверен.</span><span class="sxs-lookup"><span data-stu-id="833c1-145">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="833c1-146">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="833c1-146">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="833c1-147">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="833c1-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="833c1-148">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="833c1-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="833c1-149">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="833c1-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="833c1-p106">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="833c1-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="833c1-153">Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="833c1-153">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="833c1-154"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="833c1-154"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="833c1-p107">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Crazy Domains по [этой ссылке](https://manage.crazydomains.com/members/domains/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="833c1-p107">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="833c1-158">В разделе " **Моя учетная запись** " выберите пункт **домены**.</span><span class="sxs-lookup"><span data-stu-id="833c1-158">In the **My Account** section, select **Domains**.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="833c1-160">На странице **Domain Names** (доменные имена) в разделе **Domain (домен** ) выберите имя обновляемого домена.</span><span class="sxs-lookup"><span data-stu-id="833c1-160">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![Кразидомаинс — BP — configure – 1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="833c1-162">В разделе **параметры DNS** выберите значок раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="833c1-162">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![Кразидомаинс — BP — configure – 1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="833c1-164">Выберите команду **Add Record** (Добавить запись).</span><span class="sxs-lookup"><span data-stu-id="833c1-164">Select **Add Record**.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="833c1-166">В раскрывающемся списке **Add Record:** (Добавить запись) выберите пункт **MX Record** (Запись MX).</span><span class="sxs-lookup"><span data-stu-id="833c1-166">Choose **MX Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![Кразидомаинс — BP — configure – 2-1](../../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. <span data-ttu-id="833c1-168">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="833c1-168">Select **Add**.</span></span>
    
    ![Кразидомаинс — BP — configure – 2-2](../../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. <span data-ttu-id="833c1-170">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="833c1-170">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="833c1-171">В раскрывающемся списке выберите значение **Priority (приоритет** ).</span><span class="sxs-lookup"><span data-stu-id="833c1-171">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="833c1-172">**Mail For Zone (Почта для зоны)**</span><span class="sxs-lookup"><span data-stu-id="833c1-172">**Mail For Zone**</span></span>|<span data-ttu-id="833c1-173">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="833c1-173">**Priority**</span></span>|<span data-ttu-id="833c1-174">**Assigned To Server (Назначено серверу)**</span><span class="sxs-lookup"><span data-stu-id="833c1-174">**Assigned To Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="833c1-175">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="833c1-175">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="833c1-176">1,1</span><span class="sxs-lookup"><span data-stu-id="833c1-176">1</span></span>  <br/> <span data-ttu-id="833c1-177">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="833c1-177">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="833c1-178">*\<ключ_домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="833c1-178">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="833c1-179">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Office 365.</span><span class="sxs-lookup"><span data-stu-id="833c1-179">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="833c1-180">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="833c1-180">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Кразидомаинс — BP — configure – 2-3](../../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. <span data-ttu-id="833c1-182">Нажмите кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="833c1-182">Select **Update**.</span></span>
    
    ![Кразидомаинс — BP — configure – 2-4](../../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. <span data-ttu-id="833c1-184">Если в разделе **MX Record (запись MX** ) указаны другие записи MX, выберите **изменить** для одной из этих записей.</span><span class="sxs-lookup"><span data-stu-id="833c1-184">If there are any other MX records listed in the **MX Record** section, select **Modify** for one of those records.</span></span> 
    
    ![Кразидомаинс — BP — configure – 2-5](../../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. <span data-ttu-id="833c1-186">Нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="833c1-186">Select **Delete**.</span></span>
    
    ![Кразидомаинс — BP — configure – 2-6](../../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. <span data-ttu-id="833c1-188">Нажмите кнопку **Обновить** , чтобы подтвердить удаление.</span><span class="sxs-lookup"><span data-stu-id="833c1-188">Select **Update** to confirm the deletion.</span></span> 
    
    ![Кразидомаинс — BP — configure – 2-7](../../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. <span data-ttu-id="833c1-190">Повторите эти действия для удаления из списка всех остальных записей MX, кроме той, которую вы добавили на предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="833c1-190">Use the same process to remove any other MX records in the list, until only the one that you added earlier in this procedure remains.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="833c1-191">Добавление шести записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="833c1-191">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="833c1-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="833c1-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="833c1-p109">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Crazy Domains по [этой ссылке](https://manage.crazydomains.com/members/domains/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="833c1-p109">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="833c1-196">В разделе " **Моя учетная запись** " выберите пункт **домены**.</span><span class="sxs-lookup"><span data-stu-id="833c1-196">In the **My Account** section, select **Domains**.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="833c1-198">На странице **Domain Names** (доменные имена) в разделе **Domain (домен** ) выберите имя обновляемого домена.</span><span class="sxs-lookup"><span data-stu-id="833c1-198">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![Кразидомаинс — BP — configure – 1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="833c1-200">В разделе **параметры DNS** выберите значок раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="833c1-200">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![Кразидомаинс — BP — configure – 1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="833c1-202">Выберите команду **Add Record** (Добавить запись).</span><span class="sxs-lookup"><span data-stu-id="833c1-202">Select **Add Record**.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="833c1-204">В раскрывающемся списке **Add Record:** (Добавить запись) выберите пункт **CNAME Record** (Запись CNAME).</span><span class="sxs-lookup"><span data-stu-id="833c1-204">Choose **CNAME Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![Кразидомаинс — BP — configure – 3-1](../../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. <span data-ttu-id="833c1-206">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="833c1-206">Select **Add**.</span></span>
    
    ![Кразидомаинс — BP — configure – 3-2](../../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. <span data-ttu-id="833c1-208">Добавьте первую из шести записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="833c1-208">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="833c1-209">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="833c1-209">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="833c1-210">**Sub Domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="833c1-210">**Sub Domain**</span></span>|<span data-ttu-id="833c1-211">**Alias for (Псевдоним для)**</span><span class="sxs-lookup"><span data-stu-id="833c1-211">**Alias for**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="833c1-212">autodiscover</span><span class="sxs-lookup"><span data-stu-id="833c1-212">autodiscover</span></span>  <br/> |<span data-ttu-id="833c1-213">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="833c1-213">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="833c1-214">sip</span><span class="sxs-lookup"><span data-stu-id="833c1-214">sip</span></span>  <br/> |<span data-ttu-id="833c1-215">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="833c1-215">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="833c1-216">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="833c1-216">lyncdiscover</span></span>  <br/> |<span data-ttu-id="833c1-217">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="833c1-217">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="833c1-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="833c1-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="833c1-219">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="833c1-219">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="833c1-220">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="833c1-220">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="833c1-221">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="833c1-221">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Кразидомаинс — BP — configure – 3-3](../../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. <span data-ttu-id="833c1-223">Выберите **Добавить запись CNAME**.</span><span class="sxs-lookup"><span data-stu-id="833c1-223">Select **Add CNAME Record**.</span></span>
    
    ![Кразидомаинс — BP — configure – 3-4](../../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. <span data-ttu-id="833c1-225">Добавьте вторую запись CNAME.</span><span class="sxs-lookup"><span data-stu-id="833c1-225">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="833c1-226">В поля для новой записи используйте значения из следующей строки таблицы, а затем снова выберите **Добавить запись CNAME**.</span><span class="sxs-lookup"><span data-stu-id="833c1-226">In the boxes for the new record, use the values from the next row in the table, and then again select **Add CNAME Record**.</span></span>
    
    <span data-ttu-id="833c1-227">Повторяйте эти действия, пока не будут созданы все шесть записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="833c1-227">Repeat this process until you have created all six CNAME records.</span></span>
    
11. <span data-ttu-id="833c1-228">Нажмите кнопку **Обновить** , чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="833c1-228">Select **Update** to save your changes.</span></span> 
    
    ![Кразидомаинс — BP — configure – 3-5](../../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="833c1-230">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="833c1-230">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="833c1-231"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="833c1-231"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="833c1-232">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="833c1-232">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="833c1-233">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="833c1-233">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="833c1-234">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="833c1-234">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="833c1-235">Вместо этого добавьте необходимые значения Office 365 в текущую запись. Таким образом, в *одной* записи SPF будут указаны оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="833c1-235">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="833c1-p111">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Crazy Domains по [этой ссылке](https://manage.crazydomains.com/members/domains/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="833c1-p111">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="833c1-239">В разделе " **Моя учетная запись** " выберите пункт **домены**.</span><span class="sxs-lookup"><span data-stu-id="833c1-239">In the **My Account** section, select **Domains**.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="833c1-241">На странице **Domain Names** (доменные имена) в разделе **Domain (домен** ) выберите имя обновляемого домена.</span><span class="sxs-lookup"><span data-stu-id="833c1-241">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![Кразидомаинс — BP — configure – 1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="833c1-243">В разделе **параметры DNS** выберите значок раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="833c1-243">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![Кразидомаинс — BP — configure – 1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="833c1-245">Выберите команду **Add Record** (Добавить запись).</span><span class="sxs-lookup"><span data-stu-id="833c1-245">Select **Add Record**.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="833c1-247">В раскрывающемся списке **Add Record:** (Добавить запись) выберите пункт **TXT Record** (Запись TXT).</span><span class="sxs-lookup"><span data-stu-id="833c1-247">Choose **TXT Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![Кразидомаинс — BP — configure – 4-1](../../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. <span data-ttu-id="833c1-249">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="833c1-249">Select **Add**.</span></span>
    
    ![Кразидомаинс — BP — configure – 4-2](../../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. <span data-ttu-id="833c1-251">В поля для новой записи введите или вставьте значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="833c1-251">In the boxes for the new record, type or paste the values from the following table.</span></span>
    
    |<span data-ttu-id="833c1-252">**Sub Domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="833c1-252">**Sub Domain**</span></span>|<span data-ttu-id="833c1-253">**Text Record (Текстовая запись)**</span><span class="sxs-lookup"><span data-stu-id="833c1-253">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="833c1-254">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="833c1-254">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="833c1-255">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="833c1-255">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="833c1-256">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="833c1-256">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Кразидомаинс — BP — configure – 4-3](../../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. <span data-ttu-id="833c1-258">Нажмите кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="833c1-258">Select **Update**.</span></span>
    
    ![Кразидомаинс — BP — configure – 4-4](../../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="833c1-260">Добавление двух записей SRV, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="833c1-260">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="833c1-261"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="833c1-261"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="833c1-p112">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Crazy Domains по [этой ссылке](https://manage.crazydomains.com/members/domains/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="833c1-p112">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="833c1-265">В разделе " **Моя учетная запись** " выберите пункт **домены**.</span><span class="sxs-lookup"><span data-stu-id="833c1-265">In the **My Account** section, select **Domains**.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="833c1-267">На странице **Domain Names** (доменные имена) в разделе **Domain (домен** ) выберите имя обновляемого домена.</span><span class="sxs-lookup"><span data-stu-id="833c1-267">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![Кразидомаинс — BP — configure – 1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="833c1-269">В разделе **параметры DNS** выберите значок раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="833c1-269">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![Кразидомаинс — BP — configure – 1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="833c1-271">Выберите команду **Add Record** (Добавить запись).</span><span class="sxs-lookup"><span data-stu-id="833c1-271">Select **Add Record**.</span></span>
    
    ![Кразидомаинс — BP — configure – 1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="833c1-273">В раскрывающемся списке **Add Record:** (Добавить запись) выберите пункт **SRV Record** (Запись SRV).</span><span class="sxs-lookup"><span data-stu-id="833c1-273">Choose **SRV Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![Кразидомаинс — BP — configure – 5-1](../../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. <span data-ttu-id="833c1-275">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="833c1-275">Select **Add**.</span></span>
    
    ![Кразидомаинс — BP — configure – 5-2](../../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. <span data-ttu-id="833c1-277">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="833c1-277">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="833c1-278">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="833c1-278">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="833c1-279">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="833c1-279">**Record Type**</span></span>|<span data-ttu-id="833c1-280">**Sub Domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="833c1-280">**Sub Domain**</span></span>|<span data-ttu-id="833c1-281">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="833c1-281">**Priority**</span></span>|<span data-ttu-id="833c1-282">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="833c1-282">**Weight**</span></span>|<span data-ttu-id="833c1-283">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="833c1-283">**Port**</span></span>|<span data-ttu-id="833c1-284">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="833c1-284">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="833c1-285">SRV Record (Запись SRV)</span><span class="sxs-lookup"><span data-stu-id="833c1-285">SRV Record</span></span>  <br/> |<span data-ttu-id="833c1-286">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="833c1-286">_sip._tls</span></span>  <br/> |<span data-ttu-id="833c1-287">100</span><span class="sxs-lookup"><span data-stu-id="833c1-287">100</span></span>  <br/> |<span data-ttu-id="833c1-288">1,1</span><span class="sxs-lookup"><span data-stu-id="833c1-288">1</span></span>  <br/> |<span data-ttu-id="833c1-289">443</span><span class="sxs-lookup"><span data-stu-id="833c1-289">443</span></span>  <br/> |<span data-ttu-id="833c1-290">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="833c1-290">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="833c1-291">SRV Record (Запись SRV)</span><span class="sxs-lookup"><span data-stu-id="833c1-291">SRV Record</span></span>  <br/> |<span data-ttu-id="833c1-292">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="833c1-292">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="833c1-293">100</span><span class="sxs-lookup"><span data-stu-id="833c1-293">100</span></span>  <br/> |<span data-ttu-id="833c1-294">1,1</span><span class="sxs-lookup"><span data-stu-id="833c1-294">1</span></span>  <br/> |<span data-ttu-id="833c1-295">5061</span><span class="sxs-lookup"><span data-stu-id="833c1-295">5061</span></span>  <br/> |<span data-ttu-id="833c1-296">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="833c1-296">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Кразидомаинс — BP — configure – 5-3](../../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. <span data-ttu-id="833c1-298">Выберите **Добавить запись SRV**.</span><span class="sxs-lookup"><span data-stu-id="833c1-298">Select **Add SRV Record**.</span></span>
    
    ![Кразидомаинс — BP — configure – 5-4](../../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. <span data-ttu-id="833c1-300">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="833c1-300">Add the other SRV record.</span></span>
    
    <span data-ttu-id="833c1-301">В поля для новой записи введите значения из второй строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="833c1-301">In the boxes for the new record, use the values from the second row in the table.</span></span>
    
11. <span data-ttu-id="833c1-302">Нажмите кнопку **Обновить** , чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="833c1-302">Select **Update** to save your changes.</span></span> 
    
    ![Кразидомаинс — BP — configure – 5-5](../../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> <span data-ttu-id="833c1-p113">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="833c1-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
