---
title: Создание записей DNS на сайте 123-reg.co.uk для Майкрософт
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу 123-reg.co.uk для Майкрософт.
ms.openlocfilehash: 3c188c7e9f2f9390aa45196d798e04441d33bcb0
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400585"
---
# <a name="create-dns-records-at-123-regcouk-for-microsoft"></a><span data-ttu-id="e66d7-103">Создание записей DNS на сайте 123-reg.co.uk для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e66d7-103">Create DNS records at 123-reg.co.uk for Microsoft</span></span>

 <span data-ttu-id="e66d7-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="e66d7-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e66d7-105">Если ваш поставщик услуг размещения DNS  123-reg.co.uk, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="e66d7-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="e66d7-106">Когда вы добавите эти записи на сайте 123-reg.co.uk, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e66d7-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="e66d7-p101">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e66d7-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e66d7-110">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="e66d7-110">Add a TXT record for verification</span></span>
<span data-ttu-id="e66d7-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="e66d7-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="e66d7-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="e66d7-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e66d7-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="e66d7-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="e66d7-116">Чтобы приступить к работе, откройте страницу со своими доменами на сайте 123-reg.co.uk по [этой ссылке](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="e66d7-116">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="e66d7-117">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="e66d7-117">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e66d7-118">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="e66d7-118">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="e66d7-119">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="e66d7-119">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="e66d7-120">На странице " **Управление DNS** " перейдите на вкладку **Advanced DNS (дополнительно** ).</span><span class="sxs-lookup"><span data-stu-id="e66d7-120">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="e66d7-121">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="e66d7-121">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e66d7-122">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="e66d7-122">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="e66d7-123">**Hostname (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="e66d7-123">**Hostname**</span></span> <br/> |<span data-ttu-id="e66d7-124">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="e66d7-124">**Type**</span></span> <br/> |<span data-ttu-id="e66d7-125">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="e66d7-125">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="e66d7-126">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="e66d7-126">TXT/SPF</span></span>  <br/> |<span data-ttu-id="e66d7-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e66d7-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="e66d7-128">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="e66d7-128">**Note:** This is an example.</span></span> <span data-ttu-id="e66d7-129">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="e66d7-129">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="e66d7-130">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="e66d7-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
6. <span data-ttu-id="e66d7-131">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="e66d7-131">Select **Add**.</span></span>
    
7. <span data-ttu-id="e66d7-132">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="e66d7-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e66d7-133">Теперь, когда вы добавили запись на сайт регистратора доменных имен, вернитесь в корпорацию Майкрософт и запросите Поиск записи.</span><span class="sxs-lookup"><span data-stu-id="e66d7-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="e66d7-134">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="e66d7-134">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e66d7-135">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="e66d7-135">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="e66d7-136">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="e66d7-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="e66d7-137">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="e66d7-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="e66d7-138">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="e66d7-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e66d7-p106">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e66d7-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="e66d7-142">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e66d7-142">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="e66d7-143"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="e66d7-143"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="e66d7-p107">Чтобы приступить к работе, откройте страницу со своими доменами на сайте 123-reg.co.uk по [этой ссылке](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="e66d7-p107">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e66d7-146">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="e66d7-146">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="e66d7-147">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="e66d7-147">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="e66d7-148">На странице " **Управление DNS** " перейдите на вкладку **Advanced DNS (дополнительно** ).</span><span class="sxs-lookup"><span data-stu-id="e66d7-148">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="e66d7-149">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="e66d7-149">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e66d7-150">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="e66d7-150">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e66d7-151">**Hostname (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="e66d7-151">**Hostname**</span></span>|<span data-ttu-id="e66d7-152">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="e66d7-152">**Type**</span></span>|<span data-ttu-id="e66d7-153">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="e66d7-153">**Priority**</span></span>|<span data-ttu-id="e66d7-154">**Destination MX (Запись MX назначения)**</span><span class="sxs-lookup"><span data-stu-id="e66d7-154">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="e66d7-155">MX</span><span class="sxs-lookup"><span data-stu-id="e66d7-155">MX</span></span>  <br/> |<span data-ttu-id="e66d7-156">1 </span><span class="sxs-lookup"><span data-stu-id="e66d7-156">1</span></span>  <br/> <span data-ttu-id="e66d7-157">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).   </span><span class="sxs-lookup"><span data-stu-id="e66d7-157">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="e66d7-158">*\<domain-key\>*. mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="e66d7-158">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="e66d7-159">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="e66d7-159">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="e66d7-160">**Примечание:** Получение \<domain-key\> учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e66d7-160">**Note:** Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="e66d7-161">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="e66d7-161">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Копирование и вставка значений из таблицы](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="e66d7-163">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="e66d7-163">Select **Add**.</span></span>
    
    ![Нажмите кнопку Добавить](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="e66d7-165">Если есть какие-либо другие записи MX, удалите каждую из них, щелкнув соответствующий значок с изображением **корзины**.</span><span class="sxs-lookup"><span data-stu-id="e66d7-165">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![Нажмите кнопку Удалить (значок корзины).](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="e66d7-167">Добавление шести записей CNAME, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e66d7-167">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="e66d7-168"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="e66d7-168"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="e66d7-p109">Чтобы приступить к работе, откройте страницу со своими доменами на сайте 123-reg.co.uk по [этой ссылке](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="e66d7-p109">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e66d7-171">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="e66d7-171">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="e66d7-172">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="e66d7-172">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="e66d7-173">На странице " **Управление DNS** " перейдите на вкладку **Advanced DNS (дополнительно** ).</span><span class="sxs-lookup"><span data-stu-id="e66d7-173">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="e66d7-174">Добавьте первую из шести записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="e66d7-174">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="e66d7-175">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="e66d7-175">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e66d7-176">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="e66d7-176">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e66d7-177">**Hostname (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="e66d7-177">**Hostname**</span></span>|<span data-ttu-id="e66d7-178">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="e66d7-178">**Type**</span></span>|<span data-ttu-id="e66d7-179">**Destination CNAME (Запись CNAME назначения)**</span><span class="sxs-lookup"><span data-stu-id="e66d7-179">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="e66d7-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="e66d7-180">autodiscover</span></span>  <br/> |<span data-ttu-id="e66d7-181">CNAME</span><span class="sxs-lookup"><span data-stu-id="e66d7-181">CNAME</span></span>  <br/> |<span data-ttu-id="e66d7-182">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="e66d7-182">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="e66d7-183">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="e66d7-183">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="e66d7-184">sip</span><span class="sxs-lookup"><span data-stu-id="e66d7-184">sip</span></span>  <br/> |<span data-ttu-id="e66d7-185">CNAME</span><span class="sxs-lookup"><span data-stu-id="e66d7-185">CNAME</span></span>  <br/> |<span data-ttu-id="e66d7-186">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e66d7-186">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="e66d7-187">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="e66d7-187">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="e66d7-188">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e66d7-188">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e66d7-189">CNAME</span><span class="sxs-lookup"><span data-stu-id="e66d7-189">CNAME</span></span>  <br/> |<span data-ttu-id="e66d7-190">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e66d7-190">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="e66d7-191">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="e66d7-191">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="e66d7-192">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e66d7-192">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e66d7-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="e66d7-193">CNAME</span></span>  <br/> |<span data-ttu-id="e66d7-194">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="e66d7-194">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="e66d7-195">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="e66d7-195">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="e66d7-196">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e66d7-196">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e66d7-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="e66d7-197">CNAME</span></span>  <br/> |<span data-ttu-id="e66d7-198">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e66d7-198">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="e66d7-199">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="e66d7-199">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Скопируйте и вставьте значения из таблицы](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="e66d7-201">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="e66d7-201">Select **Add**.</span></span>
    
    ![Нажмите кнопку Добавить](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="e66d7-203">Добавьте пять других записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="e66d7-203">Add the other five CNAME records.</span></span>
    
    <span data-ttu-id="e66d7-204">В разделе **Advanced DNS (Расширенный DNS** ) создайте запись, используя значения из следующей строки таблицы, а затем еще раз нажмите кнопку **Добавить** , чтобы завершить эту запись.</span><span class="sxs-lookup"><span data-stu-id="e66d7-204">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="e66d7-205">Повторяйте эти действия, пока не будут созданы все шесть записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="e66d7-205">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e66d7-206">Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама</span><span class="sxs-lookup"><span data-stu-id="e66d7-206">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="e66d7-207"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="e66d7-207"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e66d7-208">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="e66d7-208">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e66d7-209">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="e66d7-209">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e66d7-210">Если у вас уже есть запись SPF для вашего домена, не создавайте ее для Микросфот.</span><span class="sxs-lookup"><span data-stu-id="e66d7-210">If you already have an SPF record for your domain, don't create a new one for Microsfot.</span></span> <span data-ttu-id="e66d7-211">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="e66d7-211">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="e66d7-212">Нужны примеры?</span><span class="sxs-lookup"><span data-stu-id="e66d7-212">Need examples?</span></span> <span data-ttu-id="e66d7-213">Ознакомьтесь с этими [записями системы внешних доменных имен для продуктов корпорации Майкрософт](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="e66d7-213">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span></span> <span data-ttu-id="e66d7-214">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="e66d7-214">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="e66d7-215">Чтобы приступить к работе, откройте страницу со своими доменами на сайте 123-reg.co.uk по [этой ссылке](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="e66d7-215">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="e66d7-216">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="e66d7-216">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e66d7-217">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="e66d7-217">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="e66d7-218">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="e66d7-218">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="e66d7-219">На странице " **Управление DNS** " перейдите на вкладку **Advanced DNS (дополнительно** ).</span><span class="sxs-lookup"><span data-stu-id="e66d7-219">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="e66d7-220">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="e66d7-220">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e66d7-221">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="e66d7-221">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e66d7-222">**Hostname (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="e66d7-222">**Hostname**</span></span>|<span data-ttu-id="e66d7-223">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="e66d7-223">**Type**</span></span>|<span data-ttu-id="e66d7-224">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="e66d7-224">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="e66d7-225">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="e66d7-225">TXT/SPF</span></span>  <br/> |<span data-ttu-id="e66d7-226">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e66d7-226">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="e66d7-227">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="e66d7-227">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![123Reg — BP — configure – 4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="e66d7-229">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="e66d7-229">Select **Add**.</span></span>
    
    ![Нажмите кнопку Добавить](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="e66d7-231">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e66d7-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="e66d7-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="e66d7-232"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="e66d7-p112">Чтобы приступить к работе, откройте страницу со своими доменами на сайте 123-reg.co.uk по [этой ссылке](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="e66d7-p112">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e66d7-235">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="e66d7-235">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="e66d7-236">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="e66d7-236">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="e66d7-237">На странице " **Управление DNS** " перейдите на вкладку **Advanced DNS (дополнительно** ).</span><span class="sxs-lookup"><span data-stu-id="e66d7-237">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="e66d7-238">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="e66d7-238">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="e66d7-239">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="e66d7-239">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e66d7-240">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="e66d7-240">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e66d7-241">Hostname (Имя узла)</span><span class="sxs-lookup"><span data-stu-id="e66d7-241">Hostname</span></span>|<span data-ttu-id="e66d7-242">Type (Тип)</span><span class="sxs-lookup"><span data-stu-id="e66d7-242">Type</span></span>|<span data-ttu-id="e66d7-243">Priority (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="e66d7-243">Priority</span></span>|<span data-ttu-id="e66d7-244">TTL (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="e66d7-244">TTL</span></span>|<span data-ttu-id="e66d7-245">Destination SRV (Запись SRV назначения)</span><span class="sxs-lookup"><span data-stu-id="e66d7-245">Destination SRV</span></span>|
    |<span data-ttu-id="e66d7-246">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="e66d7-246">_sip._tls</span></span>|<span data-ttu-id="e66d7-247">SRV</span><span class="sxs-lookup"><span data-stu-id="e66d7-247">SRV</span></span>|<span data-ttu-id="e66d7-248">100</span><span class="sxs-lookup"><span data-stu-id="e66d7-248">100</span></span>|<span data-ttu-id="e66d7-249">3600</span><span class="sxs-lookup"><span data-stu-id="e66d7-249">3600</span></span>|<span data-ttu-id="e66d7-250">1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e66d7-250">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="e66d7-251">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="e66d7-251">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="e66d7-252">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="e66d7-252">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="e66d7-253">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="e66d7-253">_sipfederationtls._tcp</span></span>|<span data-ttu-id="e66d7-254">SRV</span><span class="sxs-lookup"><span data-stu-id="e66d7-254">SRV</span></span>|<span data-ttu-id="e66d7-255">100</span><span class="sxs-lookup"><span data-stu-id="e66d7-255">100</span></span>|<span data-ttu-id="e66d7-256">3600</span><span class="sxs-lookup"><span data-stu-id="e66d7-256">3600</span></span>|<span data-ttu-id="e66d7-257">1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e66d7-257">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="e66d7-258">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="e66d7-258">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="e66d7-259">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="e66d7-259">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Скопируйте и вставьте значения из таблицы](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="e66d7-261">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="e66d7-261">Select **Add**.</span></span>
    
    ![Нажмите кнопку Добавить](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="e66d7-263">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="e66d7-263">To add the other SRV record:</span></span>
    
    <span data-ttu-id="e66d7-264">В разделе **Advanced DNS (Расширенный DNS** ) создайте запись, используя значения из второй строки таблицы, а затем еще раз нажмите кнопку **Добавить** , чтобы завершить эту запись.</span><span class="sxs-lookup"><span data-stu-id="e66d7-264">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="e66d7-p115">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e66d7-p115">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
