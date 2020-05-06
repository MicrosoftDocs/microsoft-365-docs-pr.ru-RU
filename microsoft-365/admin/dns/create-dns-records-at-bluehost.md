---
title: Создание записей DNS на сайте BlueHost для Майкрософт
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу Bluehost для Майкрософт.
ms.openlocfilehash: c2aabd7a578ab792cfb341f67765fc3021038e44
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049099"
---
# <a name="create-dns-records-at-bluehost-for-microsoft"></a><span data-ttu-id="c9064-103">Создание записей DNS на сайте BlueHost для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c9064-103">Create DNS records at Bluehost for Microsoft</span></span>

 <span data-ttu-id="c9064-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="c9064-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="c9064-105">Если ваш поставщик услуг размещения DNS  Bluehost, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="c9064-105">If Bluehost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="c9064-106">Когда вы добавите эти записи на сайте BlueHost, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c9064-106">After you add these records at Bluehost, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="c9064-p101">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c9064-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="c9064-110">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="c9064-110">Add a TXT record for verification</span></span>
<span data-ttu-id="c9064-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="c9064-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="c9064-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="c9064-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c9064-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="c9064-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="c9064-116">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Bluehost по [этой ссылке](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="c9064-116">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="c9064-117">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="c9064-117">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c9064-118">На странице **доменов** в области **домена** установите флажок домена, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="c9064-118">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="c9064-119">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="c9064-119">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="c9064-120">В области ***domain_name*** в строке **Редактор зоны DNS** выберите **Управление записями DNS**.</span><span class="sxs-lookup"><span data-stu-id="c9064-120">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="c9064-121">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="c9064-121">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="c9064-122">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="c9064-122">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c9064-123">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="c9064-123">**Host Record**</span></span> <br/> |<span data-ttu-id="c9064-124">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="c9064-124">**TTL**</span></span> <br/> |<span data-ttu-id="c9064-125">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="c9064-125">**Type**</span></span> <br/> |<span data-ttu-id="c9064-126">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="c9064-126">**TXT Value**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="c9064-127">14400</span><span class="sxs-lookup"><span data-stu-id="c9064-127">14400</span></span>  <br/> |<span data-ttu-id="c9064-128">TXT</span><span class="sxs-lookup"><span data-stu-id="c9064-128">TXT</span></span>  <br/> |<span data-ttu-id="c9064-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="c9064-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="c9064-130">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="c9064-130">**Note:** This is an example.</span></span> <span data-ttu-id="c9064-131">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="c9064-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="c9064-132">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="c9064-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
5. <span data-ttu-id="c9064-133">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="c9064-133">Select **add record**.</span></span>
    
6. <span data-ttu-id="c9064-134">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="c9064-134">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="c9064-135">Теперь, когда вы добавили запись на сайт регистратора доменных имен, вернитесь в корпорацию Майкрософт и запросите Поиск записи.</span><span class="sxs-lookup"><span data-stu-id="c9064-135">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="c9064-136">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="c9064-136">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="c9064-137">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="c9064-137">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="c9064-138">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="c9064-138">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="c9064-139">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="c9064-139">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="c9064-140">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="c9064-140">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c9064-p106">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c9064-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="c9064-144">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c9064-144">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="c9064-145"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="c9064-145"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="c9064-146">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Bluehost по [этой ссылке](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="c9064-146">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="c9064-147">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="c9064-147">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c9064-148">На странице **доменов** в области **домена** установите флажок домена, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="c9064-148">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="c9064-149">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="c9064-149">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="c9064-150">В области ***domain_name*** в строке **Редактор зоны DNS** выберите **Управление записями DNS**.</span><span class="sxs-lookup"><span data-stu-id="c9064-150">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="c9064-151">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="c9064-151">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="c9064-152">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="c9064-152">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="c9064-153">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="c9064-153">**Host Record**</span></span>|<span data-ttu-id="c9064-154">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="c9064-154">**TTL**</span></span>|<span data-ttu-id="c9064-155">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="c9064-155">**Type**</span></span>|<span data-ttu-id="c9064-156">**Points To (Указывает на)**</span><span class="sxs-lookup"><span data-stu-id="c9064-156">**Points To**</span></span>|<span data-ttu-id="c9064-157">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="c9064-157">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="c9064-158">14400</span><span class="sxs-lookup"><span data-stu-id="c9064-158">14400</span></span>  <br/> |<span data-ttu-id="c9064-159">MX</span><span class="sxs-lookup"><span data-stu-id="c9064-159">MX</span></span>  <br/> | <span data-ttu-id="c9064-160">*\<ключ_домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c9064-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/><span data-ttu-id="c9064-161">**Примечание.**  Получите свой \<*domain-key*\> (ключ домена) из учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c9064-161">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="c9064-162">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="c9064-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="c9064-163">нуль</span><span class="sxs-lookup"><span data-stu-id="c9064-163">0</span></span>  <br/> <span data-ttu-id="c9064-164">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="c9064-164">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
   ![Выберите тип из раскрывающегося списка.](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. <span data-ttu-id="c9064-166">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="c9064-166">Select **add record**.</span></span>
    
    ![Нажмите кнопку Добавить запись](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. <span data-ttu-id="c9064-168">Если в разделе **MX (Mail Exchanger)** (Почтовый обменник) есть другие записи MX, удалите их.</span><span class="sxs-lookup"><span data-stu-id="c9064-168">If there are any other MX records in the **MX (Mail Exchanger)** section, delete each of them.</span></span> 
    
    <span data-ttu-id="c9064-169">Для одной из других записей MX нажмите кнопку **Удалить.**</span><span class="sxs-lookup"><span data-stu-id="c9064-169">For one of the other MX records, select **Delete.**</span></span>
    
    ![Выберите Delete (удалить) для каждой дополнительной записи MX](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. <span data-ttu-id="c9064-171">В диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c9064-171">In the confirmation dialog box, select **OK**.</span></span>
    
    ![Нажмите кнопку ОК.](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. <span data-ttu-id="c9064-173">Повторите эти действия для всех ненужных записей MX.</span><span class="sxs-lookup"><span data-stu-id="c9064-173">Use the same process to delete any other MX records that were already listed.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="c9064-174">Добавление шести записей CNAME, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c9064-174">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="c9064-175"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="c9064-175"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="c9064-176">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Bluehost по [этой ссылке](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="c9064-176">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="c9064-177">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="c9064-177">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c9064-178">На странице **доменов** в области **домена** установите флажок домена, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="c9064-178">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="c9064-179">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="c9064-179">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="c9064-180">В области ***domain_name*** в строке **Редактор зоны DNS** выберите **Управление записями DNS**.</span><span class="sxs-lookup"><span data-stu-id="c9064-180">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="c9064-181">В разделе **A (Host) (записи узла)** найдите строку для записи **автообнаружения** , а затем выберите команду **Удалить** для этой строки.</span><span class="sxs-lookup"><span data-stu-id="c9064-181">In the **A (Host)** records section, find the row for the **autodiscover** record, and then select **delete** for that row.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="c9064-182">Необходимо удалить существующую запись **автообнаружения** *перед* добавлением записи **автообнаружения** , необходимой корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c9064-182">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Microsoft.</span></span> <span data-ttu-id="c9064-183">Bluehost не обеспечивает одновременную поддержку двух записей **autodiscover**.</span><span class="sxs-lookup"><span data-stu-id="c9064-183">Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span></span> 
  
    ![Нажмите кнопку Удалить](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. <span data-ttu-id="c9064-185">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c9064-185">Select **OK**.</span></span>
    
    ![Нажмите кнопку ОК.](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. <span data-ttu-id="c9064-187">Создайте первую из шести записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="c9064-187">Create the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="c9064-188">На странице **DNS Zone Editor** (Редактор зон DNS) в поля для новой записи в области **Add DNS Record** (Добавление записи DNS) введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="c9064-188">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="c9064-189">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="c9064-189">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="c9064-190">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="c9064-190">**Host Record**</span></span>|<span data-ttu-id="c9064-191">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="c9064-191">**TTL**</span></span>|<span data-ttu-id="c9064-192">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="c9064-192">**Type**</span></span>|<span data-ttu-id="c9064-193">**Points To (Указывает на)**</span><span class="sxs-lookup"><span data-stu-id="c9064-193">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c9064-194">autodiscover</span><span class="sxs-lookup"><span data-stu-id="c9064-194">autodiscover</span></span>  <br/> |<span data-ttu-id="c9064-195">14400</span><span class="sxs-lookup"><span data-stu-id="c9064-195">14400</span></span>  <br/> |<span data-ttu-id="c9064-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="c9064-196">CNAME</span></span>  <br/> |<span data-ttu-id="c9064-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c9064-197">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="c9064-198">sip</span><span class="sxs-lookup"><span data-stu-id="c9064-198">sip</span></span>  <br/> |<span data-ttu-id="c9064-199">14400</span><span class="sxs-lookup"><span data-stu-id="c9064-199">14400</span></span>  <br/> |<span data-ttu-id="c9064-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="c9064-200">CNAME</span></span>  <br/> |<span data-ttu-id="c9064-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c9064-201">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="c9064-202">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="c9064-202">lyncdiscover</span></span>  <br/> |<span data-ttu-id="c9064-203">14400</span><span class="sxs-lookup"><span data-stu-id="c9064-203">14400</span></span>  <br/> |<span data-ttu-id="c9064-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="c9064-204">CNAME</span></span>  <br/> |<span data-ttu-id="c9064-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c9064-205">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="c9064-206">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="c9064-206">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="c9064-207">14400</span><span class="sxs-lookup"><span data-stu-id="c9064-207">14400</span></span>  <br/> |<span data-ttu-id="c9064-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="c9064-208">CNAME</span></span>  <br/> |<span data-ttu-id="c9064-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="c9064-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="c9064-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="c9064-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="c9064-211">14400</span><span class="sxs-lookup"><span data-stu-id="c9064-211">14400</span></span>  <br/> |<span data-ttu-id="c9064-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="c9064-212">CNAME</span></span>  <br/> |<span data-ttu-id="c9064-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c9064-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Создание первой записи CNAME](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. <span data-ttu-id="c9064-215">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="c9064-215">Select **add record**.</span></span>
    
    ![Нажмите кнопку Добавить запись](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. <span data-ttu-id="c9064-217">Добавьте остальные пять записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="c9064-217">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="c9064-218">По-прежнему в разделе **Добавление записи DNS** создайте запись, используя значения из следующей строки таблицы, а затем снова выберите **Добавить запись** , чтобы завершить эту запись.</span><span class="sxs-lookup"><span data-stu-id="c9064-218">Still in the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **add record** to complete that record.</span></span> 
    
    <span data-ttu-id="c9064-219">Повторяйте эти действия, пока не будут созданы все шесть записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="c9064-219">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="c9064-220">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="c9064-220">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="c9064-221"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="c9064-221"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9064-222">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="c9064-222">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="c9064-223">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="c9064-223">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="c9064-224">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c9064-224">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="c9064-225">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="c9064-225">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="c9064-226">Нужны примеры?</span><span class="sxs-lookup"><span data-stu-id="c9064-226">Need examples?</span></span> <span data-ttu-id="c9064-227">Ознакомьтесь с этими [записями системы внешних доменных имен для продуктов корпорации Майкрософт](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span><span class="sxs-lookup"><span data-stu-id="c9064-227">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="c9064-228">Чтобы проверить запись SPF, можно использовать один из этих[средств проверки SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="c9064-228">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="c9064-229">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Bluehost по [этой ссылке](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="c9064-229">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="c9064-230">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="c9064-230">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c9064-231">На странице **доменов** в области **домена** установите флажок домена, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="c9064-231">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="c9064-232">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="c9064-232">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="c9064-233">В области ***domain_name*** в строке **Редактор зоны DNS** выберите **Управление записями DNS**.</span><span class="sxs-lookup"><span data-stu-id="c9064-233">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="c9064-234">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="c9064-234">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="c9064-235">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="c9064-235">(Choose the **Type** value from the drop-down list.)</span></span> 
        
    |<span data-ttu-id="c9064-236">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="c9064-236">**Host Record**</span></span>|<span data-ttu-id="c9064-237">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="c9064-237">**TTL**</span></span>|<span data-ttu-id="c9064-238">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="c9064-238">**Type**</span></span>|<span data-ttu-id="c9064-239">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="c9064-239">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="c9064-240">14400</span><span class="sxs-lookup"><span data-stu-id="c9064-240">14400</span></span>  <br/> |<span data-ttu-id="c9064-241">TXT</span><span class="sxs-lookup"><span data-stu-id="c9064-241">TXT</span></span>  <br/> |<span data-ttu-id="c9064-242">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="c9064-242">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="c9064-243">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="c9064-243">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Копирование значения TXT](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. <span data-ttu-id="c9064-245">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="c9064-245">Select **add record**.</span></span>
    
    ![Нажмите кнопку Добавить запись](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="c9064-247">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c9064-247">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="c9064-248"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="c9064-248"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="c9064-249">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Bluehost по [этой ссылке](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="c9064-249">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="c9064-250">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="c9064-250">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c9064-251">На странице **доменов** в области **домена** установите флажок домена, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="c9064-251">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="c9064-252">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="c9064-252">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="c9064-253">В области ***domain_name*** в строке **Редактор зоны DNS** выберите **Управление записями DNS**.</span><span class="sxs-lookup"><span data-stu-id="c9064-253">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="c9064-254">Создайте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="c9064-254">Create the first of the two SRV records.</span></span>
    
    <span data-ttu-id="c9064-255">На странице **DNS Zone Editor** (Редактор зон DNS) в поля для новой записи в области **Add DNS Record** (Добавление записи DNS) введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="c9064-255">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="c9064-256">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="c9064-256">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="c9064-257">**Служба**</span><span class="sxs-lookup"><span data-stu-id="c9064-257">**Service**</span></span>|<span data-ttu-id="c9064-258">**Protocol (Протокол)**</span><span class="sxs-lookup"><span data-stu-id="c9064-258">**Protocol**</span></span>|<span data-ttu-id="c9064-259">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="c9064-259">**Host**</span></span>|<span data-ttu-id="c9064-260">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="c9064-260">**TTL**</span></span>|<span data-ttu-id="c9064-261">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="c9064-261">**Type**</span></span>|<span data-ttu-id="c9064-262">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="c9064-262">**Priority**</span></span>|<span data-ttu-id="c9064-263">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="c9064-263">**Weight**</span></span>|<span data-ttu-id="c9064-264">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="c9064-264">**Port**</span></span>|<span data-ttu-id="c9064-265">**Points To (Указывает на)**</span><span class="sxs-lookup"><span data-stu-id="c9064-265">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c9064-266">_sip</span><span class="sxs-lookup"><span data-stu-id="c9064-266">_sip</span></span>  <br/> |<span data-ttu-id="c9064-267">_tls</span><span class="sxs-lookup"><span data-stu-id="c9064-267">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="c9064-268">14400</span><span class="sxs-lookup"><span data-stu-id="c9064-268">14400</span></span>  <br/> |<span data-ttu-id="c9064-269">SRV</span><span class="sxs-lookup"><span data-stu-id="c9064-269">SRV</span></span>  <br/> |<span data-ttu-id="c9064-270">100</span><span class="sxs-lookup"><span data-stu-id="c9064-270">100</span></span>  <br/> |<span data-ttu-id="c9064-271">1,1</span><span class="sxs-lookup"><span data-stu-id="c9064-271">1</span></span>  <br/> |<span data-ttu-id="c9064-272">443</span><span class="sxs-lookup"><span data-stu-id="c9064-272">443</span></span>  <br/> |<span data-ttu-id="c9064-273">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c9064-273">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="c9064-274">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="c9064-274">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="c9064-275">_tcp</span><span class="sxs-lookup"><span data-stu-id="c9064-275">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="c9064-276">14400</span><span class="sxs-lookup"><span data-stu-id="c9064-276">14400</span></span>  <br/> |<span data-ttu-id="c9064-277">SRV</span><span class="sxs-lookup"><span data-stu-id="c9064-277">SRV</span></span>  <br/> |<span data-ttu-id="c9064-278">100</span><span class="sxs-lookup"><span data-stu-id="c9064-278">100</span></span>  <br/> |<span data-ttu-id="c9064-279">1,1</span><span class="sxs-lookup"><span data-stu-id="c9064-279">1</span></span>  <br/> |<span data-ttu-id="c9064-280">5061</span><span class="sxs-lookup"><span data-stu-id="c9064-280">5061</span></span>  <br/> |<span data-ttu-id="c9064-281">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c9064-281">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Копирование значения для новой записи](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. <span data-ttu-id="c9064-283">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="c9064-283">Select **add record**.</span></span>
    
    ![Нажмите кнопку Добавить запись](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. <span data-ttu-id="c9064-285">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="c9064-285">Add the other SRV record.</span></span>
    
    <span data-ttu-id="c9064-286">По-прежнему в разделе **Добавление записи DNS** создайте запись, используя значения из другой строки таблицы, а затем снова выберите **Добавить запись** , чтобы завершить эту запись.</span><span class="sxs-lookup"><span data-stu-id="c9064-286">Still in the **Add DNS Record** section, create a record by using the values from the other row in the table, and then again select **add record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="c9064-p114">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c9064-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

