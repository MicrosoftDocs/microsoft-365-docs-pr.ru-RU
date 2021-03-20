---
title: Создание записей DNS в DNSMadeEasy для Microsoft
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб в DNSMadeEasy для Microsoft.
ms.openlocfilehash: 11e8072ab3c798ed550043370d0e6e79c7370b4d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910394"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a><span data-ttu-id="5021a-103">Создание записей DNS в DNSMadeEasy для Microsoft</span><span class="sxs-lookup"><span data-stu-id="5021a-103">Create DNS records at DNSMadeEasy for Microsoft</span></span>

 <span data-ttu-id="5021a-104">**[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="5021a-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="5021a-105">Если ваш поставщик услуг размещения DNS  DNSMadeEasy, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="5021a-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="5021a-106">После добавления этих записей в DNSMadeEasy домен будет настроен для работы с службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5021a-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="5021a-p101">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5021a-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5021a-110">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="5021a-110">Add a TXT record for verification</span></span>
<span data-ttu-id="5021a-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="5021a-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="5021a-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="5021a-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5021a-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="5021a-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="5021a-116">Если вы используете учетную запись DNSMadeEasy, это означает, что добавленный вами домен приобретен у другой компании  регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="5021a-116">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="5021a-117">DNSMadeEasy не предоставляет услуг по регистрации доменных имен.</span><span class="sxs-lookup"><span data-stu-id="5021a-117">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="5021a-118">Если вы можете выполнить вход на сайте DNSMadeEasy и создать запись DNS, это подтверждает ваше владение доменом.</span><span class="sxs-lookup"><span data-stu-id="5021a-118">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="5021a-119">Чтобы приступить к работе, откройте страницу со своими доменами на сайте DNSMadeEasy по [этой ссылке](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="5021a-119">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="5021a-120">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="5021a-120">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="5021a-121">На странице **Консоль управления**  в области недавно обновленных доменов выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="5021a-121">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="5021a-122">На странице **Управляемый DNS** в области **TXT Records** выберите **+** () управление **(Добавить новое).**</span><span class="sxs-lookup"><span data-stu-id="5021a-122">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="5021a-123">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="5021a-123">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="5021a-124">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="5021a-124">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="5021a-125">**Name**</span><span class="sxs-lookup"><span data-stu-id="5021a-125">**Name**</span></span> <br/> |<span data-ttu-id="5021a-126">**Value** (Значение)</span><span class="sxs-lookup"><span data-stu-id="5021a-126">**Value**</span></span> <br/> |<span data-ttu-id="5021a-127">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="5021a-127">**TTL**</span></span> <br/> |
    |<span data-ttu-id="5021a-128">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="5021a-128">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="5021a-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5021a-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="5021a-130">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="5021a-130">**Note:** This is an example.</span></span> <span data-ttu-id="5021a-131">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="5021a-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="5021a-132">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="5021a-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="5021a-133">1800</span><span class="sxs-lookup"><span data-stu-id="5021a-133">1800</span></span>  <br/> |
   
5. <span data-ttu-id="5021a-134">Выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="5021a-134">Select **Submit**.</span></span>
    
6. <span data-ttu-id="5021a-135">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="5021a-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="5021a-136">Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.</span><span class="sxs-lookup"><span data-stu-id="5021a-136">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="5021a-137">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="5021a-137">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5021a-138">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="5021a-138">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="5021a-139">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="5021a-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="5021a-140">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="5021a-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="5021a-141">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="5021a-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5021a-p107">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5021a-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="5021a-145">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5021a-145">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="5021a-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="5021a-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="5021a-p108">Чтобы приступить к работе, откройте страницу со своими доменами на сайте DNSMadeEasy по [этой ссылке](https://cp.dnsmadeeasy.com/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="5021a-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="5021a-149">На странице **Консоль управления**  в области недавно обновленных доменов выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="5021a-149">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="5021a-150">На странице **Консоль управления**  в области недавно обновленных доменов выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="5021a-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="5021a-152">На странице **Управляемый DNS** в области **MX Records** выберите **(+) управление (+)** **(Добавить новое).**</span><span class="sxs-lookup"><span data-stu-id="5021a-152">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="5021a-153">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="5021a-153">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="5021a-155">В поля для новой записи в области **Add MX Records** (Добавление записей MX) введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="5021a-155">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5021a-156">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="5021a-156">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="5021a-157">**Name**</span><span class="sxs-lookup"><span data-stu-id="5021a-157">**Name**</span></span>|<span data-ttu-id="5021a-158">**Server**</span><span class="sxs-lookup"><span data-stu-id="5021a-158">**Server**</span></span>|<span data-ttu-id="5021a-159">**MX Level (Уровень MX)**</span><span class="sxs-lookup"><span data-stu-id="5021a-159">**MX Level**</span></span>|<span data-ttu-id="5021a-160">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="5021a-160">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5021a-161">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="5021a-161">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="5021a-162">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5021a-162">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="5021a-163">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="5021a-163">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="5021a-164">**Примечание.**  Получите свой \<*domain-key*\> из учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5021a-164">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="5021a-165">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="5021a-165">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="5021a-166">10 </span><span class="sxs-lookup"><span data-stu-id="5021a-166">10</span></span>  <br/> <span data-ttu-id="5021a-167">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](../setup/domains-faq.yml).   </span><span class="sxs-lookup"><span data-stu-id="5021a-167">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |<span data-ttu-id="5021a-168">1800</span><span class="sxs-lookup"><span data-stu-id="5021a-168">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="5021a-170">Выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="5021a-170">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="5021a-172">Если в разделе **MX Records** (Записи MX) есть другие записи MX, выберите их.</span><span class="sxs-lookup"><span data-stu-id="5021a-172">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="5021a-174">Когда все записи выбраны, выберите **Удалить выбранный**.</span><span class="sxs-lookup"><span data-stu-id="5021a-174">When all records are selected, select **Delete selected**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="5021a-176">В **диалоговом окне Delete MX Records** выберите **Удаление,** чтобы подтвердить изменения.</span><span class="sxs-lookup"><span data-stu-id="5021a-176">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="5021a-178">Добавление пяти записей CNAME, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5021a-178">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="5021a-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="5021a-179"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="5021a-p110">Чтобы приступить к работе, откройте страницу со своими доменами на сайте DNSMadeEasy по [этой ссылке](https://cp.dnsmadeeasy.com/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="5021a-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="5021a-182">На странице **Консоль управления**  в области недавно обновленных доменов выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="5021a-182">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="5021a-183">На странице **Управляемый DNS** в области **записей CNAME** выберите **(+) управление (+)** **(Добавить новое).**</span><span class="sxs-lookup"><span data-stu-id="5021a-183">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="5021a-184">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="5021a-184">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-3-1](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="5021a-186">Добавьте первую из пяти записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="5021a-186">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="5021a-187">В поля для новой записи в области **Add CNAME Records** (Добавление записей CNAME) введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="5021a-187">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="5021a-188">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="5021a-188">**Name**</span></span>|<span data-ttu-id="5021a-189">**Alias to (Псевдоним для)**</span><span class="sxs-lookup"><span data-stu-id="5021a-189">**Alias to**</span></span>|<span data-ttu-id="5021a-190">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="5021a-190">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5021a-191">autodiscover</span><span class="sxs-lookup"><span data-stu-id="5021a-191">autodiscover</span></span>  <br/> |<span data-ttu-id="5021a-192">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="5021a-192">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="5021a-193">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="5021a-193">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5021a-194">1800</span><span class="sxs-lookup"><span data-stu-id="5021a-194">1800</span></span>  <br/> |
    |<span data-ttu-id="5021a-195">sip</span><span class="sxs-lookup"><span data-stu-id="5021a-195">sip</span></span>  <br/> |<span data-ttu-id="5021a-196">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="5021a-196">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="5021a-197">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="5021a-197">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5021a-198">1800</span><span class="sxs-lookup"><span data-stu-id="5021a-198">1800</span></span>  <br/> |
    |<span data-ttu-id="5021a-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5021a-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="5021a-200">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="5021a-200">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="5021a-201">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="5021a-201">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5021a-202">1800</span><span class="sxs-lookup"><span data-stu-id="5021a-202">1800</span></span>  <br/> |
    |<span data-ttu-id="5021a-203">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="5021a-203">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="5021a-204">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="5021a-204">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="5021a-205">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="5021a-205">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5021a-206">1800</span><span class="sxs-lookup"><span data-stu-id="5021a-206">1800</span></span>  <br/> |
    |<span data-ttu-id="5021a-207">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="5021a-207">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="5021a-208">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="5021a-208">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="5021a-209">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="5021a-209">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5021a-210">1800</span><span class="sxs-lookup"><span data-stu-id="5021a-210">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="5021a-212">Выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="5021a-212">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="5021a-214">Добавьте все остальные четыре записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="5021a-214">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="5021a-215">В разделе **CNAME Records** выберите **(+) управление (+)** **(Добавить** новое), создайте запись с помощью значений из следующей строки в таблице, а затем снова выберите **Отправить** для завершения этой записи.</span><span class="sxs-lookup"><span data-stu-id="5021a-215">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="5021a-216">Повторите этот процесс, пока не создайте все пять записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="5021a-216">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="5021a-217">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="5021a-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="5021a-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="5021a-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5021a-219">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="5021a-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="5021a-220">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="5021a-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="5021a-221">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5021a-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="5021a-222">Вместо этого добавьте необходимые значения Microsoft в текущую  запись, чтобы у вас была одна запись SPF, которая включает оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="5021a-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="5021a-223">Нужны примеры?</span><span class="sxs-lookup"><span data-stu-id="5021a-223">Need examples?</span></span> <span data-ttu-id="5021a-224">Ознакомьтесь с этими [записями системы внешних доменных имен для продуктов корпорации Майкрософт](../../enterprise/external-domain-name-system-records.md).</span><span class="sxs-lookup"><span data-stu-id="5021a-224">Check out these [External Domain Name System records for Microsoft](../../enterprise/external-domain-name-system-records.md).</span></span> <span data-ttu-id="5021a-225">Для проверки записи SPF можно использовать один из этих средств проверки[SPF.](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="5021a-225">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="5021a-226">Чтобы приступить к работе, откройте страницу со своими доменами на сайте DNSMadeEasy по [этой ссылке](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="5021a-226">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="5021a-227">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="5021a-227">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="5021a-228">На странице **Консоль управления**  в области недавно обновленных доменов выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="5021a-228">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="5021a-229">На странице **Управляемый DNS** в области **TXT Records** выберите **(+) управление (+)** **(Добавление новых).**</span><span class="sxs-lookup"><span data-stu-id="5021a-229">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="5021a-230">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="5021a-230">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="5021a-232">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="5021a-232">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="5021a-233">**Name**</span><span class="sxs-lookup"><span data-stu-id="5021a-233">**Name**</span></span>|<span data-ttu-id="5021a-234">**Value** (Значение)</span><span class="sxs-lookup"><span data-stu-id="5021a-234">**Value**</span></span>|<span data-ttu-id="5021a-235">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="5021a-235">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5021a-236">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="5021a-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="5021a-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="5021a-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="5021a-238">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="5021a-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="5021a-239">1800</span><span class="sxs-lookup"><span data-stu-id="5021a-239">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="5021a-241">Выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="5021a-241">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="5021a-243">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5021a-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="5021a-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="5021a-244"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="5021a-p113">Чтобы приступить к работе, откройте страницу со своими доменами на сайте DNSMadeEasy по [этой ссылке](https://cp.dnsmadeeasy.com/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="5021a-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="5021a-247">На странице **Консоль управления**  в области недавно обновленных доменов выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="5021a-247">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="5021a-248">На странице **Управляемый DNS** в области **SRV Records** выберите **(+) управление (+)** **(Добавить новое).**</span><span class="sxs-lookup"><span data-stu-id="5021a-248">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="5021a-249">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="5021a-249">(You may have to scroll down)</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="5021a-251">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="5021a-251">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="5021a-252">В поля для новой записи в области **Add SRV Records** (Добавление записей SRV) введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="5021a-252">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="5021a-253">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="5021a-253">**Name**</span></span>|<span data-ttu-id="5021a-254">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="5021a-254">**Priority**</span></span>|<span data-ttu-id="5021a-255">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="5021a-255">**Weight**</span></span>|<span data-ttu-id="5021a-256">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="5021a-256">**Port**</span></span>|<span data-ttu-id="5021a-257">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="5021a-257">**Host**</span></span>|<span data-ttu-id="5021a-258">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="5021a-258">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5021a-259">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="5021a-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="5021a-260">100</span><span class="sxs-lookup"><span data-stu-id="5021a-260">100</span></span>  <br/> |<span data-ttu-id="5021a-261">1</span><span class="sxs-lookup"><span data-stu-id="5021a-261">1</span></span>  <br/> |<span data-ttu-id="5021a-262">443</span><span class="sxs-lookup"><span data-stu-id="5021a-262">443</span></span>  <br/> |<span data-ttu-id="5021a-263">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="5021a-263">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="5021a-264">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="5021a-264">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5021a-265">1800</span><span class="sxs-lookup"><span data-stu-id="5021a-265">1800</span></span>  <br/> |
    |<span data-ttu-id="5021a-266">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="5021a-266">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="5021a-267">100</span><span class="sxs-lookup"><span data-stu-id="5021a-267">100</span></span>  <br/> |<span data-ttu-id="5021a-268">1</span><span class="sxs-lookup"><span data-stu-id="5021a-268">1</span></span>  <br/> |<span data-ttu-id="5021a-269">5061</span><span class="sxs-lookup"><span data-stu-id="5021a-269">5061</span></span>  <br/> |<span data-ttu-id="5021a-270">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="5021a-270">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="5021a-271">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="5021a-271">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5021a-272">1800</span><span class="sxs-lookup"><span data-stu-id="5021a-272">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="5021a-274">Выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="5021a-274">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="5021a-276">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="5021a-276">Add the other SRV record.</span></span>
    
    <span data-ttu-id="5021a-277">В разделе **SRV Records** выберите управление **(+) (Добавить** **новое),** создайте запись с помощью значений из следующей строки в таблице, а затем снова выберите **Отправить** для завершения этой записи.</span><span class="sxs-lookup"><span data-stu-id="5021a-277">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="5021a-p114">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5021a-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
