---
title: Создание записей DNS на сайте Namecheap для Майкрософт
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
ms.assetid: 54ae2002-b38e-43a1-82fa-3e49d78fda56
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу Namecheap для Майкрософт.
ms.openlocfilehash: 25b40dad0eb47c190df9496d5df4f061d8fdba6d
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645927"
---
# <a name="create-dns-records-at-namecheap-for-microsoft"></a><span data-ttu-id="fa114-103">Создание записей DNS на сайте Namecheap для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="fa114-103">Create DNS records at Namecheap for Microsoft</span></span>

 <span data-ttu-id="fa114-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="fa114-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="fa114-105">Если ваш поставщик услуг размещения DNS  Namecheap, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб.</span><span class="sxs-lookup"><span data-stu-id="fa114-105">If Namecheap is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="fa114-106">Когда вы добавите эти записи на сайте Namecheap, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fa114-106">After you add these records at Namecheap, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fa114-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fa114-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="fa114-110">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="fa114-110">Add a TXT record for verification</span></span>
<span data-ttu-id="fa114-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="fa114-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="fa114-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="fa114-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fa114-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="fa114-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="fa114-116">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="fa114-116">Follow the steps below.</span></span>
  
1. <span data-ttu-id="fa114-p104">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Namecheap по [этой ссылке](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Вам потребуется войти в службу.</span><span class="sxs-lookup"><span data-stu-id="fa114-p104">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="fa114-120">На **начальной** странице в разделе **учетная запись**выберите **список доменов** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="fa114-120">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="fa114-122">На странице **список доменов** найдите имя домена, который требуется изменить, и выберите пункт **Управление**.</span><span class="sxs-lookup"><span data-stu-id="fa114-122">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="fa114-124">Выберите **Advanced DNS**.</span><span class="sxs-lookup"><span data-stu-id="fa114-124">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="fa114-126">В разделе **записи узла** выберите **Добавить новую запись**.</span><span class="sxs-lookup"><span data-stu-id="fa114-126">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="fa114-128">В раскрывающемся списке **Type** (Тип) выберите **TXT Record** (Запись TXT).</span><span class="sxs-lookup"><span data-stu-id="fa114-128">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fa114-129">Раскрывающийся список **типов** автоматически отображается при выборе параметра **Добавить новую запись**.</span><span class="sxs-lookup"><span data-stu-id="fa114-129">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="fa114-131">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="fa114-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="fa114-132">В раскрывающемся списке выберите значение **TTL (срок жизни** ).</span><span class="sxs-lookup"><span data-stu-id="fa114-132">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="fa114-133">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="fa114-133">**Type**</span></span>|<span data-ttu-id="fa114-134">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="fa114-134">**Host**</span></span>|<span data-ttu-id="fa114-135">**Value** (Значение)</span><span class="sxs-lookup"><span data-stu-id="fa114-135">**Value**</span></span>|<span data-ttu-id="fa114-136">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="fa114-136">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="fa114-137">TXT</span><span class="sxs-lookup"><span data-stu-id="fa114-137">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="fa114-138">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="fa114-138">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="fa114-139">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="fa114-139">**Note:** This is an example.</span></span> <span data-ttu-id="fa114-140">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="fa114-140">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="fa114-141">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="fa114-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="fa114-142">30 мин</span><span class="sxs-lookup"><span data-stu-id="fa114-142">30 min</span></span>  <br/> |
       
    ![Namecheap — BP — Verify – 1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="fa114-144">Выберите элемент управления **Сохранение изменений** (галочка).</span><span class="sxs-lookup"><span data-stu-id="fa114-144">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="fa114-146">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="fa114-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="fa114-147">Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.</span><span class="sxs-lookup"><span data-stu-id="fa114-147">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="fa114-148">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="fa114-148">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="fa114-149">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="fa114-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="fa114-150">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="fa114-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="fa114-151">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="fa114-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="fa114-152">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="fa114-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="fa114-p106">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fa114-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="fa114-156">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fa114-156">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="fa114-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="fa114-157"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="fa114-158">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="fa114-158">Follow the steps below.</span></span>
  
1. <span data-ttu-id="fa114-p107">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Namecheap по [этой ссылке](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Вам потребуется войти в службу.</span><span class="sxs-lookup"><span data-stu-id="fa114-p107">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="fa114-162">На **начальной** странице в разделе **учетная запись**выберите **список доменов** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="fa114-162">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="fa114-164">На странице **список доменов** найдите имя домена, который требуется изменить, и выберите пункт **Управление**.</span><span class="sxs-lookup"><span data-stu-id="fa114-164">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="fa114-166">Выберите **Advanced DNS**.</span><span class="sxs-lookup"><span data-stu-id="fa114-166">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="fa114-168">В разделе **MAIL SETTINGS** (Параметры почты) выберите **Custom MX** (Настраиваемая запись MX) в раскрывающемся списке **Email Forwarding** (Переадресация электронной почты).</span><span class="sxs-lookup"><span data-stu-id="fa114-168">In the **MAIL SETTINGS** section, select **Custom MX** from the **Email Forwarding** drop-down list.</span></span> 
    
    <span data-ttu-id="fa114-169">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="fa114-169">(You may have to scroll down.)</span></span>
    
    ![Namecheap-BP-Configure-2-1](../../media/40199e2c-42cf-4c3f-9936-3cbe5d4e81a4.png)
  
6. <span data-ttu-id="fa114-171">Нажмите кнопку **Добавить новую запись**.</span><span class="sxs-lookup"><span data-stu-id="fa114-171">Select **Add New Record**.</span></span>
    
    ![Namecheap — BP — configure – 2-2-1](../../media/8d169b81-ba48-4d51-84ea-a08fa1616457.png)
  
7. <span data-ttu-id="fa114-173">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="fa114-173">In the boxes for the new record, type or copy and paste the values, from the following table.</span></span>
    
    <span data-ttu-id="fa114-174">(Поле **Priority** (Приоритет)  это поле без названия справа от поля **Value** (Значение).</span><span class="sxs-lookup"><span data-stu-id="fa114-174">(The **Priority** box is the unnamed box to the right of the **Value** box.</span></span> <span data-ttu-id="fa114-175">Выберите значение **TTL** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="fa114-175">Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="fa114-176">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="fa114-176">**Type**</span></span>|<span data-ttu-id="fa114-177">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="fa114-177">**Host**</span></span>|<span data-ttu-id="fa114-178">**Value** (Значение)</span><span class="sxs-lookup"><span data-stu-id="fa114-178">**Value**</span></span>|<span data-ttu-id="fa114-179">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="fa114-179">**Priority**</span></span>|<span data-ttu-id="fa114-180">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="fa114-180">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="fa114-181">MX Record (Запись MX)</span><span class="sxs-lookup"><span data-stu-id="fa114-181">MX Record</span></span>  <br/> |@  <br/> |<span data-ttu-id="fa114-182">\<*domain-key*\>. mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="fa114-182">\<*domain-key*\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="fa114-183">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="fa114-183">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="fa114-184">**Примечание:** Получение  *\<domain-key\>*  учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fa114-184">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="fa114-185">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="fa114-185">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="fa114-186">нуль</span><span class="sxs-lookup"><span data-stu-id="fa114-186">0</span></span>  <br/> <span data-ttu-id="fa114-187">Дополнительные сведения о приоритете см. в статье [Что такое приоритет записей MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="fa114-187">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="fa114-188">30 мин</span><span class="sxs-lookup"><span data-stu-id="fa114-188">30 min</span></span>  <br/> |
       
    ![Namecheap — BP — configure – 2-2-2](../../media/f3b76d62-5022-48c1-901b-8615a8571309.png)
  
8. <span data-ttu-id="fa114-190">Выберите элемент управления **Сохранение изменений** (галочка).</span><span class="sxs-lookup"><span data-stu-id="fa114-190">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-2-3](../../media/ef4e3112-36d2-47c8-a478-136a565dd71d.png)
  
9. <span data-ttu-id="fa114-192">Если есть какие-либо другие записи MX, удалите каждую из них, выполнив двухшаговую процедуру.</span><span class="sxs-lookup"><span data-stu-id="fa114-192">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="fa114-193">Сначала выберите значок " **Удалить** " (корзина может) для записи, которую необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="fa114-193">First, select the **Delete icon** (trash can) for the record that you want to remove.</span></span> 
    
    ![Namecheap-BP-Configure-2-4](../../media/7a7a751f-29c2-495f-8f55-98ca37ce555a.png)
  
    <span data-ttu-id="fa114-195">Во вторых, нажмите кнопку **Да** , чтобы подтвердить удаление.</span><span class="sxs-lookup"><span data-stu-id="fa114-195">Second, select **Yes** to confirm the deletion.</span></span> 
    
    ![Namecheap-BP-Configure-2-5](../../media/85ebc0c7-8787-43ee-9e7b-647375b3345c.png)
  
    <span data-ttu-id="fa114-197">Удалите все записи MX, кроме той, которую вы добавили ранее в этой процедуре.</span><span class="sxs-lookup"><span data-stu-id="fa114-197">Remove all MX records except for the one that you added earlier in this procedure.</span></span>

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="fa114-198">Добавление шести записей CNAME, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="fa114-198">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="fa114-199"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="fa114-199"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="fa114-200">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="fa114-200">Follow the steps below.</span></span>
  
1. <span data-ttu-id="fa114-p110">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Namecheap по [этой ссылке](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Вам потребуется войти в службу.</span><span class="sxs-lookup"><span data-stu-id="fa114-p110">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="fa114-204">На **начальной** странице в разделе **учетная запись**выберите **список доменов** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="fa114-204">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="fa114-206">На странице **список доменов** найдите имя домена, который требуется изменить, и выберите пункт **Управление**.</span><span class="sxs-lookup"><span data-stu-id="fa114-206">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="fa114-208">Выберите **Advanced DNS**.</span><span class="sxs-lookup"><span data-stu-id="fa114-208">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="fa114-210">В разделе **записи узла** выберите **Добавить новую запись**.</span><span class="sxs-lookup"><span data-stu-id="fa114-210">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="fa114-212">В раскрывающемся списке **Type** (Тип) выберите **CNAME Record** (Запись CNAME).</span><span class="sxs-lookup"><span data-stu-id="fa114-212">In the **Type** drop-down, select **CNAME Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fa114-213">Раскрывающийся список **типов** автоматически отображается при выборе параметра **Добавить новую запись**.</span><span class="sxs-lookup"><span data-stu-id="fa114-213">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-3-1](../../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png)
  
7. <span data-ttu-id="fa114-215">В пустых полях для новой записи выберите значение **CNAME** для параметра **Record Type** (Тип записи) и введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="fa114-215">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="fa114-216">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="fa114-216">**Type**</span></span>|<span data-ttu-id="fa114-217">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="fa114-217">**Host**</span></span>|<span data-ttu-id="fa114-218">**Value** (Значение)</span><span class="sxs-lookup"><span data-stu-id="fa114-218">**Value**</span></span>|<span data-ttu-id="fa114-219">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="fa114-219">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="fa114-220">CNAME</span><span class="sxs-lookup"><span data-stu-id="fa114-220">CNAME</span></span>  <br/> |<span data-ttu-id="fa114-221">autodiscover</span><span class="sxs-lookup"><span data-stu-id="fa114-221">autodiscover</span></span>  <br/> |<span data-ttu-id="fa114-222">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="fa114-222">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="fa114-223">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="fa114-223">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="fa114-224">3600</span><span class="sxs-lookup"><span data-stu-id="fa114-224">3600</span></span>  <br/> |
    |<span data-ttu-id="fa114-225">CNAME</span><span class="sxs-lookup"><span data-stu-id="fa114-225">CNAME</span></span>  <br/> |<span data-ttu-id="fa114-226">sip</span><span class="sxs-lookup"><span data-stu-id="fa114-226">sip</span></span>  <br/> |<span data-ttu-id="fa114-227">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="fa114-227">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="fa114-228">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="fa114-228">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="fa114-229">3600</span><span class="sxs-lookup"><span data-stu-id="fa114-229">3600</span></span>  <br/> |
    |<span data-ttu-id="fa114-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="fa114-230">CNAME</span></span>  <br/> |<span data-ttu-id="fa114-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="fa114-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="fa114-232">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="fa114-232">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="fa114-233">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="fa114-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="fa114-234">3600</span><span class="sxs-lookup"><span data-stu-id="fa114-234">3600</span></span>  <br/> |
    |<span data-ttu-id="fa114-235">CNAME</span><span class="sxs-lookup"><span data-stu-id="fa114-235">CNAME</span></span>  <br/> |<span data-ttu-id="fa114-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="fa114-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="fa114-237">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="fa114-237">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="fa114-238">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="fa114-238">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="fa114-239">3600</span><span class="sxs-lookup"><span data-stu-id="fa114-239">3600</span></span>  <br/> |
    |<span data-ttu-id="fa114-240">CNAME</span><span class="sxs-lookup"><span data-stu-id="fa114-240">CNAME</span></span>  <br/> |<span data-ttu-id="fa114-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="fa114-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="fa114-242">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="fa114-242">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="fa114-243">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="fa114-243">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="fa114-244">3600</span><span class="sxs-lookup"><span data-stu-id="fa114-244">3600</span></span>  <br/> |
       
    ![Namecheap — BP — configure – 3-2](../../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png)
  
8. <span data-ttu-id="fa114-246">Выберите элемент управления **Сохранение изменений** (галочка).</span><span class="sxs-lookup"><span data-stu-id="fa114-246">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-3-3](../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png)
  
9. <span data-ttu-id="fa114-248">С помощью приведенных выше четырех шагов и значений из других пяти строк в таблице добавьте все остальные пять записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="fa114-248">Using the preceding four steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="fa114-249">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="fa114-249">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="fa114-250"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="fa114-250"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa114-251">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="fa114-251">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="fa114-252">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="fa114-252">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="fa114-253">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fa114-253">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="fa114-254">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь  *одну*  запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="fa114-254">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

<span data-ttu-id="fa114-255">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="fa114-255">Follow the steps below.</span></span>
  
1. <span data-ttu-id="fa114-p112">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Namecheap по [этой ссылке](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Вам потребуется войти в службу.</span><span class="sxs-lookup"><span data-stu-id="fa114-p112">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
2. <span data-ttu-id="fa114-258">На **начальной** странице в разделе **учетная запись**выберите **список доменов** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="fa114-258">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="fa114-260">На странице **список доменов** найдите имя домена, который требуется изменить, и выберите пункт **Управление**.</span><span class="sxs-lookup"><span data-stu-id="fa114-260">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="fa114-262">Выберите **Advanced DNS**.</span><span class="sxs-lookup"><span data-stu-id="fa114-262">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="fa114-264">В разделе **записи узла** выберите **Добавить новую запись**.</span><span class="sxs-lookup"><span data-stu-id="fa114-264">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="fa114-266">В раскрывающемся списке **Type** (Тип) выберите **TXT Record** (Запись TXT).</span><span class="sxs-lookup"><span data-stu-id="fa114-266">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fa114-267">Раскрывающийся список **типов** автоматически отображается при выборе параметра **Добавить новую запись**.</span><span class="sxs-lookup"><span data-stu-id="fa114-267">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-4-1](../../media/c5d1fddb-28b5-48ec-91c9-3e5d3955ac80.png)
  
7. <span data-ttu-id="fa114-269">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="fa114-269">In the boxes for the new record, type or copy and paste the following values from the following table.</span></span>
    
    <span data-ttu-id="fa114-270">В раскрывающемся списке выберите значение **TTL (срок жизни** ).</span><span class="sxs-lookup"><span data-stu-id="fa114-270">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="fa114-271">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="fa114-271">**Type**</span></span>|<span data-ttu-id="fa114-272">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="fa114-272">**Host**</span></span>|<span data-ttu-id="fa114-273">**Value** (Значение)</span><span class="sxs-lookup"><span data-stu-id="fa114-273">**Value**</span></span>|<span data-ttu-id="fa114-274">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="fa114-274">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="fa114-275">TXT</span><span class="sxs-lookup"><span data-stu-id="fa114-275">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="fa114-276">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="fa114-276">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="fa114-277">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="fa114-277">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="fa114-278">30 мин</span><span class="sxs-lookup"><span data-stu-id="fa114-278">30 min</span></span>  <br/> |
       
    ![Namecheap — BP — configure – 4-2](../../media/ea0829f1-990b-424b-b26e-9859468318dd.png)
  
8. <span data-ttu-id="fa114-280">Выберите элемент управления **Сохранение изменений** (галочка).</span><span class="sxs-lookup"><span data-stu-id="fa114-280">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-4-3](../../media/f2846c36-ace3-43d8-be5d-a65e2c267619.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="fa114-282">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="fa114-282">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="fa114-283"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="fa114-283"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="fa114-p113">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Namecheap по [этой ссылке](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Вам потребуется войти в службу.</span><span class="sxs-lookup"><span data-stu-id="fa114-p113">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to sign in.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="fa114-287">На **начальной** странице в разделе **учетная запись**выберите **список доменов** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="fa114-287">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="fa114-289">На странице **список доменов** найдите имя домена, который требуется изменить, и выберите пункт **Управление**.</span><span class="sxs-lookup"><span data-stu-id="fa114-289">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="fa114-291">Выберите **Advanced DNS**.</span><span class="sxs-lookup"><span data-stu-id="fa114-291">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="fa114-293">В разделе **записи узла** выберите **Добавить новую запись**.</span><span class="sxs-lookup"><span data-stu-id="fa114-293">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="fa114-295">В раскрывающемся списке **Type** (Тип) выберите **SRV Record** (Запись SRV).</span><span class="sxs-lookup"><span data-stu-id="fa114-295">In the **Type** drop-down, select **SRV Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fa114-296">Раскрывающийся список **типов** автоматически отображается при выборе параметра **Добавить новую запись**.</span><span class="sxs-lookup"><span data-stu-id="fa114-296">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-5-1](../../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png)
  
7. <span data-ttu-id="fa114-298">В пустые поля для новых записей введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="fa114-298">In the empty boxes for the new records, type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="fa114-299">**Служба**</span><span class="sxs-lookup"><span data-stu-id="fa114-299">**Service**</span></span>|<span data-ttu-id="fa114-300">**Protocol (Протокол)**</span><span class="sxs-lookup"><span data-stu-id="fa114-300">**Protocol**</span></span>|<span data-ttu-id="fa114-301">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="fa114-301">**Priority**</span></span>|<span data-ttu-id="fa114-302">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="fa114-302">**Weight**</span></span>|<span data-ttu-id="fa114-303">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="fa114-303">**Port**</span></span>|<span data-ttu-id="fa114-304">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="fa114-304">**Target**</span></span>|<span data-ttu-id="fa114-305">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="fa114-305">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="fa114-306">_sip</span><span class="sxs-lookup"><span data-stu-id="fa114-306">_sip</span></span>  <br/> |<span data-ttu-id="fa114-307">_tls</span><span class="sxs-lookup"><span data-stu-id="fa114-307">_tls</span></span>  <br/> |<span data-ttu-id="fa114-308">100</span><span class="sxs-lookup"><span data-stu-id="fa114-308">100</span></span>  <br/> |<span data-ttu-id="fa114-309">1,1</span><span class="sxs-lookup"><span data-stu-id="fa114-309">1</span></span>  <br/> |<span data-ttu-id="fa114-310">443</span><span class="sxs-lookup"><span data-stu-id="fa114-310">443</span></span>  <br/> |<span data-ttu-id="fa114-311">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="fa114-311">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="fa114-312">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="fa114-312">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="fa114-313">30 мин</span><span class="sxs-lookup"><span data-stu-id="fa114-313">30 min</span></span>  <br/> |
    |<span data-ttu-id="fa114-314">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="fa114-314">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="fa114-315">_tcp</span><span class="sxs-lookup"><span data-stu-id="fa114-315">_tcp</span></span>  <br/> |<span data-ttu-id="fa114-316">100</span><span class="sxs-lookup"><span data-stu-id="fa114-316">100</span></span>  <br/> |<span data-ttu-id="fa114-317">1,1</span><span class="sxs-lookup"><span data-stu-id="fa114-317">1</span></span>  <br/> |<span data-ttu-id="fa114-318">5061</span><span class="sxs-lookup"><span data-stu-id="fa114-318">5061</span></span>  <br/> |<span data-ttu-id="fa114-319">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="fa114-319">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="fa114-320">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="fa114-320">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="fa114-321">30 мин</span><span class="sxs-lookup"><span data-stu-id="fa114-321">30 min</span></span>  <br/> |
       
    ![Namecheap — BP — configure – 5-2](../../media/ff9566ea-0096-4b7f-873c-027080a23b56.png)
  
8. <span data-ttu-id="fa114-323">Выберите элемент управления **Сохранение изменений** (галочка).</span><span class="sxs-lookup"><span data-stu-id="fa114-323">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-5-3](../../media/48a8dee4-c66d-449d-8759-9e9784c82b13.png)
  
9. <span data-ttu-id="fa114-325">Повторите четыре описанных выше шага, используя значения из второй строки таблицы, чтобы добавить еще одну запись SRV.</span><span class="sxs-lookup"><span data-stu-id="fa114-325">Using the preceding four steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="fa114-p114">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fa114-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
