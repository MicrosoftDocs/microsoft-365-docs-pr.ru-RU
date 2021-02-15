---
title: Создание записей DNS для Майкрософт на сайте Bluehost
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Bluehost for Microsoft.
ms.openlocfilehash: a9de709b0981c3e74eec1a3ea0e0452d068c5ad4
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658151"
---
# <a name="create-dns-records-at-bluehost-for-microsoft"></a><span data-ttu-id="7f109-103">Создание записей DNS для Майкрософт на сайте Bluehost</span><span class="sxs-lookup"><span data-stu-id="7f109-103">Create DNS records at Bluehost for Microsoft</span></span>

 <span data-ttu-id="7f109-104">**[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="7f109-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="7f109-105">Если ваш поставщик услуг размещения DNS  Bluehost, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="7f109-105">If Bluehost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="7f109-106">После добавления этих записей на сайте Bluehost ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7f109-106">After you add these records at Bluehost, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="7f109-p101">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7f109-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="7f109-110">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="7f109-110">Add a TXT record for verification</span></span>
<span data-ttu-id="7f109-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="7f109-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="7f109-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="7f109-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7f109-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="7f109-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="7f109-116">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Bluehost по [этой ссылке](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="7f109-116">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="7f109-117">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="7f109-117">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="7f109-118">На странице **доменов** в области **домена** установите флажок домена, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="7f109-118">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="7f109-119">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="7f109-119">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="7f109-120">В области **_domain_name_\*_ в строке редактора зоны _DNS**\* выберите **"Управление записями DNS".**</span><span class="sxs-lookup"><span data-stu-id="7f109-120">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="7f109-121">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="7f109-121">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="7f109-122">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="7f109-122">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7f109-123">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="7f109-123">**Host Record**</span></span> <br/> |<span data-ttu-id="7f109-124">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="7f109-124">**TTL**</span></span> <br/> |<span data-ttu-id="7f109-125">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="7f109-125">**Type**</span></span> <br/> |<span data-ttu-id="7f109-126">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="7f109-126">**TXT Value**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="7f109-127">14400</span><span class="sxs-lookup"><span data-stu-id="7f109-127">14400</span></span>  <br/> |<span data-ttu-id="7f109-128">TXT</span><span class="sxs-lookup"><span data-stu-id="7f109-128">TXT</span></span>  <br/> |<span data-ttu-id="7f109-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="7f109-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="7f109-130">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="7f109-130">**Note:** This is an example.</span></span> <span data-ttu-id="7f109-131">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="7f109-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="7f109-132">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="7f109-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
5. <span data-ttu-id="7f109-133">Выберите **"Добавить запись".**</span><span class="sxs-lookup"><span data-stu-id="7f109-133">Select **add record**.</span></span>
    
6. <span data-ttu-id="7f109-134">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="7f109-134">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="7f109-135">Теперь, когда вы добавили запись на сайте регистратора доменных имен, вы вернемся в корпорацию Майкрософт и запросите поиск записи.</span><span class="sxs-lookup"><span data-stu-id="7f109-135">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="7f109-136">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="7f109-136">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="7f109-137">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="7f109-137">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="7f109-138">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="7f109-138">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="7f109-139">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="7f109-139">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="7f109-140">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="7f109-140">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7f109-p106">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7f109-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="7f109-144">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7f109-144">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="7f109-145"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="7f109-145"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="7f109-146">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Bluehost по [этой ссылке](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="7f109-146">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="7f109-147">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="7f109-147">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="7f109-148">На странице **доменов** в области **домена** установите флажок домена, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="7f109-148">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="7f109-149">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="7f109-149">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="7f109-150">В области **_domain_name_\*_ в строке редактора зоны _DNS**\* выберите **"Управление записями DNS".**</span><span class="sxs-lookup"><span data-stu-id="7f109-150">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="7f109-151">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="7f109-151">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="7f109-152">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="7f109-152">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7f109-153">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="7f109-153">**Host Record**</span></span>|<span data-ttu-id="7f109-154">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="7f109-154">**TTL**</span></span>|<span data-ttu-id="7f109-155">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="7f109-155">**Type**</span></span>|<span data-ttu-id="7f109-156">**Points To (Указывает на)**</span><span class="sxs-lookup"><span data-stu-id="7f109-156">**Points To**</span></span>|<span data-ttu-id="7f109-157">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="7f109-157">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="7f109-158">14400</span><span class="sxs-lookup"><span data-stu-id="7f109-158">14400</span></span>  <br/> |<span data-ttu-id="7f109-159">MX</span><span class="sxs-lookup"><span data-stu-id="7f109-159">MX</span></span>  <br/> | <span data-ttu-id="7f109-160">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="7f109-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/><span data-ttu-id="7f109-161">**Примечание.**  Получите свой \<*domain-key*\> из учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7f109-161">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="7f109-162">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="7f109-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="7f109-163">0</span><span class="sxs-lookup"><span data-stu-id="7f109-163">0</span></span>  <br/> <span data-ttu-id="7f109-164">Дополнительные сведения о приоритете см. в статье [Что такое приоритет записей MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="7f109-164">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
   ![Choose Type from the drop-down list](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. <span data-ttu-id="7f109-166">Выберите **"Добавить запись".**</span><span class="sxs-lookup"><span data-stu-id="7f109-166">Select **add record**.</span></span>
    
    ![Select Add Record](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. <span data-ttu-id="7f109-168">Если в разделе **MX (Mail Exchanger)** (Почтовый обменник) есть другие записи MX, удалите их.</span><span class="sxs-lookup"><span data-stu-id="7f109-168">If there are any other MX records in the **MX (Mail Exchanger)** section, delete each of them.</span></span> 
    
    <span data-ttu-id="7f109-169">Для одной из других записей MX выберите **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="7f109-169">For one of the other MX records, select **Delete.**</span></span>
    
    ![Выберите "Удалить" для каждой дополнительной записи MX](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. <span data-ttu-id="7f109-171">В диалоговом окне подтверждения выберите **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="7f109-171">In the confirmation dialog box, select **OK**.</span></span>
    
    ![Выберите "ОК"](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. <span data-ttu-id="7f109-173">Повторите эти действия для всех ненужных записей MX.</span><span class="sxs-lookup"><span data-stu-id="7f109-173">Use the same process to delete any other MX records that were already listed.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="7f109-174">Добавление шести записей CNAME, необходимых для Корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="7f109-174">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="7f109-175"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="7f109-175"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="7f109-176">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Bluehost по [этой ссылке](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="7f109-176">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="7f109-177">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="7f109-177">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="7f109-178">На странице **доменов** в области **домена** установите флажок домена, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="7f109-178">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="7f109-179">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="7f109-179">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="7f109-180">В области **_domain_name_\*_ в строке редактора зоны _DNS**\* выберите **"Управление записями DNS".**</span><span class="sxs-lookup"><span data-stu-id="7f109-180">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="7f109-181">В разделе **записей A (Host)** найдите  строку для записи автоопоисков, а затем выберите "Удалить" **для** этой строки.</span><span class="sxs-lookup"><span data-stu-id="7f109-181">In the **A (Host)** records section, find the row for the **autodiscover** record, and then select **delete** for that row.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="7f109-182">Перед добавлением  записи автооружия, необходимой корпорации Майкрософт, удалить существующую запись автооружия.  </span><span class="sxs-lookup"><span data-stu-id="7f109-182">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Microsoft.</span></span> <span data-ttu-id="7f109-183">Bluehost не обеспечивает одновременную поддержку двух записей **autodiscover**.</span><span class="sxs-lookup"><span data-stu-id="7f109-183">Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span></span> 
  
    ![Выберите Delete (Удалить)](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. <span data-ttu-id="7f109-185">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7f109-185">Select **OK**.</span></span>
    
    ![Выберите "ОК"](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. <span data-ttu-id="7f109-187">Создайте первую из шести записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="7f109-187">Create the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="7f109-188">На странице **DNS Zone Editor** (Редактор зон DNS) в поля для новой записи в области **Add DNS Record** (Добавление записи DNS) введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="7f109-188">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="7f109-189">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="7f109-189">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7f109-190">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="7f109-190">**Host Record**</span></span>|<span data-ttu-id="7f109-191">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="7f109-191">**TTL**</span></span>|<span data-ttu-id="7f109-192">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="7f109-192">**Type**</span></span>|<span data-ttu-id="7f109-193">**Points To (Указывает на)**</span><span class="sxs-lookup"><span data-stu-id="7f109-193">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7f109-194">autodiscover</span><span class="sxs-lookup"><span data-stu-id="7f109-194">autodiscover</span></span>  <br/> |<span data-ttu-id="7f109-195">14400</span><span class="sxs-lookup"><span data-stu-id="7f109-195">14400</span></span>  <br/> |<span data-ttu-id="7f109-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="7f109-196">CNAME</span></span>  <br/> |<span data-ttu-id="7f109-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="7f109-197">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="7f109-198">sip</span><span class="sxs-lookup"><span data-stu-id="7f109-198">sip</span></span>  <br/> |<span data-ttu-id="7f109-199">14400</span><span class="sxs-lookup"><span data-stu-id="7f109-199">14400</span></span>  <br/> |<span data-ttu-id="7f109-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="7f109-200">CNAME</span></span>  <br/> |<span data-ttu-id="7f109-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7f109-201">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="7f109-202">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7f109-202">lyncdiscover</span></span>  <br/> |<span data-ttu-id="7f109-203">14400</span><span class="sxs-lookup"><span data-stu-id="7f109-203">14400</span></span>  <br/> |<span data-ttu-id="7f109-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="7f109-204">CNAME</span></span>  <br/> |<span data-ttu-id="7f109-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7f109-205">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="7f109-206">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="7f109-206">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="7f109-207">14400</span><span class="sxs-lookup"><span data-stu-id="7f109-207">14400</span></span>  <br/> |<span data-ttu-id="7f109-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="7f109-208">CNAME</span></span>  <br/> |<span data-ttu-id="7f109-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="7f109-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="7f109-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="7f109-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="7f109-211">14400</span><span class="sxs-lookup"><span data-stu-id="7f109-211">14400</span></span>  <br/> |<span data-ttu-id="7f109-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="7f109-212">CNAME</span></span>  <br/> |<span data-ttu-id="7f109-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7f109-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Создание первой записи CNAME](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. <span data-ttu-id="7f109-215">Выберите **"Добавить запись".**</span><span class="sxs-lookup"><span data-stu-id="7f109-215">Select **add record**.</span></span>
    
    ![Select Add Record](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. <span data-ttu-id="7f109-217">Добавьте остальные пять записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="7f109-217">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="7f109-218">В разделе **"Добавление записи DNS"** создайте запись, используя значения из следующей  строки таблицы, а затем снова выберите "Добавить запись", чтобы завершить запись.</span><span class="sxs-lookup"><span data-stu-id="7f109-218">Still in the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **add record** to complete that record.</span></span> 
    
    <span data-ttu-id="7f109-219">Повторяйте эти действия, пока не будут созданы все шесть записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="7f109-219">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="7f109-220">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="7f109-220">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="7f109-221"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="7f109-221"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="7f109-222">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="7f109-222">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="7f109-223">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="7f109-223">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="7f109-224">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7f109-224">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="7f109-225">Вместо этого добавьте необходимые значения Майкрософт в текущую  запись, чтобы иметь одну запись SPF, которая включает оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="7f109-225">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="7f109-226">Нужны примеры?</span><span class="sxs-lookup"><span data-stu-id="7f109-226">Need examples?</span></span> <span data-ttu-id="7f109-227">Ознакомьтесь с этими [записями системы внешних доменных имен для продуктов корпорации Майкрософт](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span><span class="sxs-lookup"><span data-stu-id="7f109-227">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="7f109-228">Для проверки записи SPF можно использовать одно из этих средств[проверки SPF.](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="7f109-228">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="7f109-229">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Bluehost по [этой ссылке](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="7f109-229">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="7f109-230">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="7f109-230">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="7f109-231">На странице **доменов** в области **домена** установите флажок домена, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="7f109-231">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="7f109-232">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="7f109-232">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="7f109-233">В области **_domain_name_\*_ в строке редактора зоны _DNS**\* выберите **"Управление записями DNS".**</span><span class="sxs-lookup"><span data-stu-id="7f109-233">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="7f109-234">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="7f109-234">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="7f109-235">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="7f109-235">(Choose the **Type** value from the drop-down list.)</span></span> 
        
    |<span data-ttu-id="7f109-236">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="7f109-236">**Host Record**</span></span>|<span data-ttu-id="7f109-237">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="7f109-237">**TTL**</span></span>|<span data-ttu-id="7f109-238">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="7f109-238">**Type**</span></span>|<span data-ttu-id="7f109-239">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="7f109-239">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="7f109-240">14400</span><span class="sxs-lookup"><span data-stu-id="7f109-240">14400</span></span>  <br/> |<span data-ttu-id="7f109-241">TXT</span><span class="sxs-lookup"><span data-stu-id="7f109-241">TXT</span></span>  <br/> |<span data-ttu-id="7f109-242">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="7f109-242">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="7f109-243">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="7f109-243">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Копирование значения TXT](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. <span data-ttu-id="7f109-245">Выберите **"Добавить запись".**</span><span class="sxs-lookup"><span data-stu-id="7f109-245">Select **add record**.</span></span>
    
    ![Select Add Record](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="7f109-247">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="7f109-247">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="7f109-248"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="7f109-248"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="7f109-249">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Bluehost по [этой ссылке](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="7f109-249">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="7f109-250">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="7f109-250">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="7f109-251">На странице **доменов** в области **домена** установите флажок домена, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="7f109-251">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="7f109-252">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="7f109-252">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="7f109-253">В области **_domain_name_\*_ в строке редактора зоны _DNS**\* выберите **"Управление записями DNS".**</span><span class="sxs-lookup"><span data-stu-id="7f109-253">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="7f109-254">Создайте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="7f109-254">Create the first of the two SRV records.</span></span>
    
    <span data-ttu-id="7f109-255">На странице **DNS Zone Editor** (Редактор зон DNS) в поля для новой записи в области **Add DNS Record** (Добавление записи DNS) введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="7f109-255">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="7f109-256">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="7f109-256">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7f109-257">**Служба**</span><span class="sxs-lookup"><span data-stu-id="7f109-257">**Service**</span></span>|<span data-ttu-id="7f109-258">**Protocol (Протокол)**</span><span class="sxs-lookup"><span data-stu-id="7f109-258">**Protocol**</span></span>|<span data-ttu-id="7f109-259">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="7f109-259">**Host**</span></span>|<span data-ttu-id="7f109-260">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="7f109-260">**TTL**</span></span>|<span data-ttu-id="7f109-261">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="7f109-261">**Type**</span></span>|<span data-ttu-id="7f109-262">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="7f109-262">**Priority**</span></span>|<span data-ttu-id="7f109-263">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="7f109-263">**Weight**</span></span>|<span data-ttu-id="7f109-264">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="7f109-264">**Port**</span></span>|<span data-ttu-id="7f109-265">**Points To (Указывает на)**</span><span class="sxs-lookup"><span data-stu-id="7f109-265">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7f109-266">_sip</span><span class="sxs-lookup"><span data-stu-id="7f109-266">_sip</span></span>  <br/> |<span data-ttu-id="7f109-267">_tls</span><span class="sxs-lookup"><span data-stu-id="7f109-267">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="7f109-268">14400</span><span class="sxs-lookup"><span data-stu-id="7f109-268">14400</span></span>  <br/> |<span data-ttu-id="7f109-269">SRV</span><span class="sxs-lookup"><span data-stu-id="7f109-269">SRV</span></span>  <br/> |<span data-ttu-id="7f109-270">100</span><span class="sxs-lookup"><span data-stu-id="7f109-270">100</span></span>  <br/> |<span data-ttu-id="7f109-271">1 </span><span class="sxs-lookup"><span data-stu-id="7f109-271">1</span></span>  <br/> |<span data-ttu-id="7f109-272">443</span><span class="sxs-lookup"><span data-stu-id="7f109-272">443</span></span>  <br/> |<span data-ttu-id="7f109-273">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7f109-273">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="7f109-274">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="7f109-274">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="7f109-275">_tcp</span><span class="sxs-lookup"><span data-stu-id="7f109-275">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="7f109-276">14400</span><span class="sxs-lookup"><span data-stu-id="7f109-276">14400</span></span>  <br/> |<span data-ttu-id="7f109-277">SRV</span><span class="sxs-lookup"><span data-stu-id="7f109-277">SRV</span></span>  <br/> |<span data-ttu-id="7f109-278">100</span><span class="sxs-lookup"><span data-stu-id="7f109-278">100</span></span>  <br/> |<span data-ttu-id="7f109-279">1 </span><span class="sxs-lookup"><span data-stu-id="7f109-279">1</span></span>  <br/> |<span data-ttu-id="7f109-280">5061</span><span class="sxs-lookup"><span data-stu-id="7f109-280">5061</span></span>  <br/> |<span data-ttu-id="7f109-281">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7f109-281">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Копирование значения для новой записи](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. <span data-ttu-id="7f109-283">Выберите **"Добавить запись".**</span><span class="sxs-lookup"><span data-stu-id="7f109-283">Select **add record**.</span></span>
    
    ![Select Add Record](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. <span data-ttu-id="7f109-285">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="7f109-285">Add the other SRV record.</span></span>
    
    <span data-ttu-id="7f109-286">В разделе  **"Добавление записи DNS"** создайте запись, используя значения из другой строки таблицы, а затем снова выберите "Добавить запись", чтобы завершить запись.</span><span class="sxs-lookup"><span data-stu-id="7f109-286">Still in the **Add DNS Record** section, create a record by using the values from the other row in the table, and then again select **add record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="7f109-p114">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7f109-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

