---
title: Создание записей DNS на сайте DNSMadeEasy для Майкрософт
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу DNSMadeEasy для Майкрософт.
ms.openlocfilehash: db28ac0cb95bd86bc13a1a1ce47f273989aa4436
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400525"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a><span data-ttu-id="31fe0-103">Создание записей DNS на сайте DNSMadeEasy для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="31fe0-103">Create DNS records at DNSMadeEasy for Microsoft</span></span>

 <span data-ttu-id="31fe0-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="31fe0-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="31fe0-105">Если ваш поставщик услуг размещения DNS  DNSMadeEasy, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="31fe0-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="31fe0-106">Когда вы добавите эти записи на сайте DNSMadeEasy, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="31fe0-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="31fe0-p101">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="31fe0-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="31fe0-110">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="31fe0-110">Add a TXT record for verification</span></span>
<span data-ttu-id="31fe0-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="31fe0-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="31fe0-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="31fe0-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="31fe0-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="31fe0-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="31fe0-116">Если вы используете учетную запись DNSMadeEasy, это означает, что добавленный вами домен приобретен у другой компании  регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="31fe0-116">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="31fe0-117">DNSMadeEasy не предоставляет услуг по регистрации доменных имен.</span><span class="sxs-lookup"><span data-stu-id="31fe0-117">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="31fe0-118">Если вы можете выполнить вход на сайте DNSMadeEasy и создать запись DNS, это подтверждает ваше владение доменом.</span><span class="sxs-lookup"><span data-stu-id="31fe0-118">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="31fe0-119">Чтобы приступить к работе, откройте страницу со своими доменами на сайте DNSMadeEasy по [этой ссылке](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="31fe0-119">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="31fe0-120">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="31fe0-120">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="31fe0-121">На странице **консоли управления** в области **Недавно обновленные домены** выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="31fe0-121">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="31fe0-122">На странице **Managed DNS** в области **записи TXT** выберите **+** элемент ( **Добавить новый**).</span><span class="sxs-lookup"><span data-stu-id="31fe0-122">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="31fe0-123">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="31fe0-123">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="31fe0-124">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="31fe0-124">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="31fe0-125">**Имя**</span><span class="sxs-lookup"><span data-stu-id="31fe0-125">**Name**</span></span> <br/> |<span data-ttu-id="31fe0-126">**Value**</span><span class="sxs-lookup"><span data-stu-id="31fe0-126">**Value**</span></span> <br/> |<span data-ttu-id="31fe0-127">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="31fe0-127">**TTL**</span></span> <br/> |
    |<span data-ttu-id="31fe0-128">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="31fe0-128">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="31fe0-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="31fe0-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="31fe0-130">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="31fe0-130">**Note:** This is an example.</span></span> <span data-ttu-id="31fe0-131">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="31fe0-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="31fe0-132">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="31fe0-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="31fe0-133">1800</span><span class="sxs-lookup"><span data-stu-id="31fe0-133">1800</span></span>  <br/> |
   
5. <span data-ttu-id="31fe0-134">Нажмите кнопку **послать**.</span><span class="sxs-lookup"><span data-stu-id="31fe0-134">Select **Submit**.</span></span>
    
6. <span data-ttu-id="31fe0-135">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="31fe0-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="31fe0-136">Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.</span><span class="sxs-lookup"><span data-stu-id="31fe0-136">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="31fe0-137">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="31fe0-137">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="31fe0-138">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="31fe0-138">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="31fe0-139">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="31fe0-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="31fe0-140">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="31fe0-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="31fe0-141">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="31fe0-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="31fe0-p107">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="31fe0-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="31fe0-145">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="31fe0-145">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="31fe0-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="31fe0-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="31fe0-p108">Чтобы приступить к работе, откройте страницу со своими доменами на сайте DNSMadeEasy по [этой ссылке](https://cp.dnsmadeeasy.com/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="31fe0-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="31fe0-149">На странице **консоли управления** в области **Недавно обновленные домены** выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="31fe0-149">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="31fe0-150">На странице **консоли управления** в области **Недавно обновленные домены** выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="31fe0-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![DNSMadeEasy — BP — configure – 1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="31fe0-152">На странице **управляемых DNS** в области MX- **записи** выберите элемент управления **(+)** ( **Добавить новый**).</span><span class="sxs-lookup"><span data-stu-id="31fe0-152">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="31fe0-153">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="31fe0-153">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy — BP — configure – 2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="31fe0-155">В поля для новой записи в области **Add MX Records** (Добавление записей MX) введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="31fe0-155">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="31fe0-156">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="31fe0-156">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="31fe0-157">**Name**</span><span class="sxs-lookup"><span data-stu-id="31fe0-157">**Name**</span></span>|<span data-ttu-id="31fe0-158">**Server**</span><span class="sxs-lookup"><span data-stu-id="31fe0-158">**Server**</span></span>|<span data-ttu-id="31fe0-159">**MX Level (Уровень MX)**</span><span class="sxs-lookup"><span data-stu-id="31fe0-159">**MX Level**</span></span>|<span data-ttu-id="31fe0-160">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="31fe0-160">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="31fe0-161">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="31fe0-161">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="31fe0-162">*\<domain-key\>*. mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="31fe0-162">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="31fe0-163">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="31fe0-163">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="31fe0-164">**Примечание:** Получение \<*domain-key*\> учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="31fe0-164">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="31fe0-165">Где это находится?</span><span class="sxs-lookup"><span data-stu-id="31fe0-165">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="31fe0-166">10 </span><span class="sxs-lookup"><span data-stu-id="31fe0-166">10</span></span>  <br/> <span data-ttu-id="31fe0-167">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).   </span><span class="sxs-lookup"><span data-stu-id="31fe0-167">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="31fe0-168">1800</span><span class="sxs-lookup"><span data-stu-id="31fe0-168">1800</span></span>  <br/> |
   
    ![DNSMadeEasy — BP — configure – 2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="31fe0-170">Нажмите кнопку **послать**.</span><span class="sxs-lookup"><span data-stu-id="31fe0-170">Select **Submit**.</span></span>
    
    ![DNSMadeEasy — BP — configure – 2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="31fe0-172">Если в разделе **MX Records** (Записи MX) есть другие записи MX, выберите их.</span><span class="sxs-lookup"><span data-stu-id="31fe0-172">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![DNSMadeEasy — BP — configure – 2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="31fe0-174">После выбора всех записей выберите пункт **Удалить выбранные**.</span><span class="sxs-lookup"><span data-stu-id="31fe0-174">When all records are selected, select **Delete selected**.</span></span>
    
    ![DNSMadeEasy — BP — configure – 2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="31fe0-176">В диалоговом окне **Удаление записей MX** нажмите кнопку **Удалить** , чтобы подтвердить изменения.</span><span class="sxs-lookup"><span data-stu-id="31fe0-176">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![DNSMadeEasy — BP — configure – 2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="31fe0-178">Добавление пяти записей CNAME, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="31fe0-178">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="31fe0-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="31fe0-179"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="31fe0-p110">Чтобы приступить к работе, откройте страницу со своими доменами на сайте DNSMadeEasy по [этой ссылке](https://cp.dnsmadeeasy.com/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="31fe0-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="31fe0-182">На странице **консоли управления** в области **Недавно обновленные домены** выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="31fe0-182">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="31fe0-183">На странице **УПРАВЛЯЕМЫХ DNS** в области **записи CNAME** выберите элемент управления **("+"** ) ( **Добавить новый**).</span><span class="sxs-lookup"><span data-stu-id="31fe0-183">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="31fe0-184">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="31fe0-184">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy — BP — configure – 3-1](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="31fe0-186">Добавьте первую из пяти записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="31fe0-186">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="31fe0-187">В поля для новой записи в области **Add CNAME Records** (Добавление записей CNAME) введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="31fe0-187">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="31fe0-188">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="31fe0-188">**Name**</span></span>|<span data-ttu-id="31fe0-189">**Alias to (Псевдоним для)**</span><span class="sxs-lookup"><span data-stu-id="31fe0-189">**Alias to**</span></span>|<span data-ttu-id="31fe0-190">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="31fe0-190">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="31fe0-191">autodiscover</span><span class="sxs-lookup"><span data-stu-id="31fe0-191">autodiscover</span></span>  <br/> |<span data-ttu-id="31fe0-192">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="31fe0-192">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="31fe0-193">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="31fe0-193">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="31fe0-194">1800</span><span class="sxs-lookup"><span data-stu-id="31fe0-194">1800</span></span>  <br/> |
    |<span data-ttu-id="31fe0-195">sip</span><span class="sxs-lookup"><span data-stu-id="31fe0-195">sip</span></span>  <br/> |<span data-ttu-id="31fe0-196">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="31fe0-196">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="31fe0-197">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="31fe0-197">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="31fe0-198">1800</span><span class="sxs-lookup"><span data-stu-id="31fe0-198">1800</span></span>  <br/> |
    |<span data-ttu-id="31fe0-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="31fe0-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="31fe0-200">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="31fe0-200">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="31fe0-201">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="31fe0-201">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="31fe0-202">1800</span><span class="sxs-lookup"><span data-stu-id="31fe0-202">1800</span></span>  <br/> |
    |<span data-ttu-id="31fe0-203">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="31fe0-203">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="31fe0-204">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="31fe0-204">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="31fe0-205">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="31fe0-205">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="31fe0-206">1800</span><span class="sxs-lookup"><span data-stu-id="31fe0-206">1800</span></span>  <br/> |
    |<span data-ttu-id="31fe0-207">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="31fe0-207">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="31fe0-208">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="31fe0-208">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="31fe0-209">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="31fe0-209">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="31fe0-210">1800</span><span class="sxs-lookup"><span data-stu-id="31fe0-210">1800</span></span>  <br/> |
   
    ![DNSMadeEasy — BP — configure – 3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="31fe0-212">Нажмите кнопку **послать**.</span><span class="sxs-lookup"><span data-stu-id="31fe0-212">Select **Submit**.</span></span>
    
    ![DNSMadeEasy — BP — configure – 3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="31fe0-214">Добавьте все остальные четыре записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="31fe0-214">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="31fe0-215">В разделе **CNAME Records (записи CNAME** **) выберите элемент управления** ( **Добавить новый**), создайте запись, используя значения из следующей строки таблицы, а затем еще раз нажмите кнопку **послать** , чтобы завершить эту запись.</span><span class="sxs-lookup"><span data-stu-id="31fe0-215">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="31fe0-216">Повторяйте эту процедуру, пока не будут созданы все пять записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="31fe0-216">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="31fe0-217">Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама</span><span class="sxs-lookup"><span data-stu-id="31fe0-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="31fe0-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="31fe0-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="31fe0-219">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="31fe0-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="31fe0-220">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="31fe0-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="31fe0-221">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="31fe0-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="31fe0-222">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="31fe0-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="31fe0-223">Нужны примеры?</span><span class="sxs-lookup"><span data-stu-id="31fe0-223">Need examples?</span></span> <span data-ttu-id="31fe0-224">Ознакомьтесь с этими [записями системы внешних доменных имен для продуктов корпорации Майкрософт](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span><span class="sxs-lookup"><span data-stu-id="31fe0-224">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="31fe0-225">Чтобы проверить запись SPF, можно использовать один из этих[средств проверки SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="31fe0-225">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="31fe0-226">Чтобы приступить к работе, откройте страницу со своими доменами на сайте DNSMadeEasy по [этой ссылке](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="31fe0-226">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="31fe0-227">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="31fe0-227">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="31fe0-228">На странице **консоли управления** в области **Недавно обновленные домены** выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="31fe0-228">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="31fe0-229">На странице **УПРАВЛЯЕМЫХ DNS** в области **записи TXT** выберите элемент управления **("+"** ) ( **Добавить новый**).</span><span class="sxs-lookup"><span data-stu-id="31fe0-229">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="31fe0-230">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="31fe0-230">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy — BP — configure – 4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="31fe0-232">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="31fe0-232">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="31fe0-233">**Name**</span><span class="sxs-lookup"><span data-stu-id="31fe0-233">**Name**</span></span>|<span data-ttu-id="31fe0-234">**Value**</span><span class="sxs-lookup"><span data-stu-id="31fe0-234">**Value**</span></span>|<span data-ttu-id="31fe0-235">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="31fe0-235">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="31fe0-236">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="31fe0-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="31fe0-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="31fe0-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="31fe0-238">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="31fe0-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="31fe0-239">1800</span><span class="sxs-lookup"><span data-stu-id="31fe0-239">1800</span></span>  <br/> |
   
    ![DNSMadeEasy — BP — configure – 4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="31fe0-241">Нажмите кнопку **послать**.</span><span class="sxs-lookup"><span data-stu-id="31fe0-241">Select **Submit**.</span></span>
    
    ![DNSMadeEasy — BP — configure – 4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="31fe0-243">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="31fe0-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="31fe0-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="31fe0-244"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="31fe0-p113">Чтобы приступить к работе, откройте страницу со своими доменами на сайте DNSMadeEasy по [этой ссылке](https://cp.dnsmadeeasy.com/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="31fe0-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="31fe0-247">На странице **консоли управления** в области **Недавно обновленные домены** выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="31fe0-247">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="31fe0-248">На странице **Managed DNS** ( **записи SRV** ) выберите элемент управления **(+)** ( **Добавить новый**).</span><span class="sxs-lookup"><span data-stu-id="31fe0-248">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="31fe0-249">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="31fe0-249">(You may have to scroll down)</span></span>
    
    ![DNSMadeEasy — BP — configure – 5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="31fe0-251">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="31fe0-251">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="31fe0-252">В поля для новой записи в области **Add SRV Records** (Добавление записей SRV) введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="31fe0-252">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="31fe0-253">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="31fe0-253">**Name**</span></span>|<span data-ttu-id="31fe0-254">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="31fe0-254">**Priority**</span></span>|<span data-ttu-id="31fe0-255">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="31fe0-255">**Weight**</span></span>|<span data-ttu-id="31fe0-256">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="31fe0-256">**Port**</span></span>|<span data-ttu-id="31fe0-257">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="31fe0-257">**Host**</span></span>|<span data-ttu-id="31fe0-258">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="31fe0-258">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="31fe0-259">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="31fe0-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="31fe0-260">100</span><span class="sxs-lookup"><span data-stu-id="31fe0-260">100</span></span>  <br/> |<span data-ttu-id="31fe0-261">1 </span><span class="sxs-lookup"><span data-stu-id="31fe0-261">1</span></span>  <br/> |<span data-ttu-id="31fe0-262">443</span><span class="sxs-lookup"><span data-stu-id="31fe0-262">443</span></span>  <br/> |<span data-ttu-id="31fe0-263">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="31fe0-263">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="31fe0-264">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="31fe0-264">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="31fe0-265">1800</span><span class="sxs-lookup"><span data-stu-id="31fe0-265">1800</span></span>  <br/> |
    |<span data-ttu-id="31fe0-266">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="31fe0-266">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="31fe0-267">100</span><span class="sxs-lookup"><span data-stu-id="31fe0-267">100</span></span>  <br/> |<span data-ttu-id="31fe0-268">1 </span><span class="sxs-lookup"><span data-stu-id="31fe0-268">1</span></span>  <br/> |<span data-ttu-id="31fe0-269">5061</span><span class="sxs-lookup"><span data-stu-id="31fe0-269">5061</span></span>  <br/> |<span data-ttu-id="31fe0-270">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="31fe0-270">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="31fe0-271">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="31fe0-271">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="31fe0-272">1800</span><span class="sxs-lookup"><span data-stu-id="31fe0-272">1800</span></span>  <br/> |
   
    ![DNSMadeEasy — BP — configure – 5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="31fe0-274">Нажмите кнопку **послать**.</span><span class="sxs-lookup"><span data-stu-id="31fe0-274">Select **Submit**.</span></span>
    
    ![DNSMadeEasy — BP — configure – 5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="31fe0-276">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="31fe0-276">Add the other SRV record.</span></span>
    
    <span data-ttu-id="31fe0-277">В разделе **SRV Records (записи SRV** ) выберите элемент управления **(** **Добавить новый**), создайте запись, используя значения из следующей строки таблицы, а затем еще раз нажмите кнопку **послать** , чтобы завершить эту запись.</span><span class="sxs-lookup"><span data-stu-id="31fe0-277">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="31fe0-p114">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="31fe0-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

