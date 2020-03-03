---
title: Создание записей DNS для Office 365 на сайте DNSMadeEasy
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу DNSMadeEasy для Office 365.
ms.openlocfilehash: 82244d216652b1957aefc3b81acd881ea4b32393
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2020
ms.locfileid: "42350320"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-office-365"></a><span data-ttu-id="1ac7a-103">Создание записей DNS для Office 365 на сайте DNSMadeEasy</span><span class="sxs-lookup"><span data-stu-id="1ac7a-103">Create DNS records at DNSMadeEasy for Office 365</span></span>

 <span data-ttu-id="1ac7a-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="1ac7a-105">Если ваш поставщик услуг размещения DNS  DNSMadeEasy, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="1ac7a-106">Когда вы добавите эти записи на сайте DNSMadeEasy, ваш домен будет настроен для работы со службами Office 365.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="1ac7a-107">Дополнительные сведения о веб-хостинге и DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="1ac7a-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1ac7a-p101">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1ac7a-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="1ac7a-111">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="1ac7a-111">Add a TXT record for verification</span></span>
<span data-ttu-id="1ac7a-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="1ac7a-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="1ac7a-p102">Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1ac7a-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="1ac7a-117">Если вы используете учетную запись DNSMadeEasy, это означает, что добавленный вами домен приобретен у другой компании  регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-117">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="1ac7a-118">DNSMadeEasy не предоставляет услуг по регистрации доменных имен.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-118">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="1ac7a-119">Если вы можете выполнить вход на сайте DNSMadeEasy и создать запись DNS, это подтверждает ваше владение доменом.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-119">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="1ac7a-120">Чтобы приступить к работе, откройте страницу со своими доменами на сайте DNSMadeEasy по [этой ссылке](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="1ac7a-120">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="1ac7a-121">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-121">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="1ac7a-122">На странице **консоли управления** в области **Недавно обновленные домены** выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-122">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="1ac7a-123">На странице **Managed DNS** в области **записи TXT** выберите элемент ( **+** **Добавить новый**).</span><span class="sxs-lookup"><span data-stu-id="1ac7a-123">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="1ac7a-124">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="1ac7a-124">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="1ac7a-125">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-125">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="1ac7a-126">**Имя**</span><span class="sxs-lookup"><span data-stu-id="1ac7a-126">**Name**</span></span> <br/> |<span data-ttu-id="1ac7a-127">**Value** (Значение)</span><span class="sxs-lookup"><span data-stu-id="1ac7a-127">**Value**</span></span> <br/> |<span data-ttu-id="1ac7a-128">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="1ac7a-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="1ac7a-129">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="1ac7a-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1ac7a-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="1ac7a-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="1ac7a-131">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-131">**Note:** This is an example.</span></span> <span data-ttu-id="1ac7a-132">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-132">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="1ac7a-133">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="1ac7a-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="1ac7a-134">1800</span><span class="sxs-lookup"><span data-stu-id="1ac7a-134">1800</span></span>  <br/> |
   
5. <span data-ttu-id="1ac7a-135">Нажмите кнопку **послать**.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-135">Select **Submit**.</span></span>
    
6. <span data-ttu-id="1ac7a-136">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-136">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="1ac7a-137">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Office 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-137">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="1ac7a-138">Если Office 365 обнаружит правильную запись TXT, это значит, что домен проверен.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-138">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="1ac7a-139">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="1ac7a-139">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="1ac7a-140">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-140">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="1ac7a-141">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="1ac7a-141">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="1ac7a-142">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="1ac7a-142">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1ac7a-p107">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1ac7a-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="1ac7a-146">Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="1ac7a-146">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="1ac7a-147"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="1ac7a-147"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="1ac7a-p108">Чтобы приступить к работе, откройте страницу со своими доменами на сайте DNSMadeEasy по [этой ссылке](https://cp.dnsmadeeasy.com/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="1ac7a-150">На странице **консоли управления** в области **Недавно обновленные домены** выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="1ac7a-151">На странице **консоли управления** в области **Недавно обновленные домены** выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-151">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![DNSMadeEasy — BP — configure – 1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="1ac7a-153">На странице **управляемых DNS** в области MX- **записи** выберите элемент управления **(+)** ( **Добавить новый**).</span><span class="sxs-lookup"><span data-stu-id="1ac7a-153">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="1ac7a-154">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="1ac7a-154">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy — BP — configure – 2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="1ac7a-156">В поля для новой записи в области **Add MX Records** (Добавление записей MX) введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-156">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="1ac7a-157">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="1ac7a-157">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="1ac7a-158">**Name**</span><span class="sxs-lookup"><span data-stu-id="1ac7a-158">**Name**</span></span>|<span data-ttu-id="1ac7a-159">**Server**</span><span class="sxs-lookup"><span data-stu-id="1ac7a-159">**Server**</span></span>|<span data-ttu-id="1ac7a-160">**MX Level (Уровень MX)**</span><span class="sxs-lookup"><span data-stu-id="1ac7a-160">**MX Level**</span></span>|<span data-ttu-id="1ac7a-161">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="1ac7a-161">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1ac7a-162">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="1ac7a-162">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="1ac7a-163">*\<ключ_домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1ac7a-163">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="1ac7a-164">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="1ac7a-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="1ac7a-165">**Примечание.**  Получите свой \<*ключ-домена*\> из учетной записи портала Office 365.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-165">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> [<span data-ttu-id="1ac7a-166">Где это находится?</span><span class="sxs-lookup"><span data-stu-id="1ac7a-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="1ac7a-167">10 </span><span class="sxs-lookup"><span data-stu-id="1ac7a-167">10</span></span>  <br/> <span data-ttu-id="1ac7a-168">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).   </span><span class="sxs-lookup"><span data-stu-id="1ac7a-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="1ac7a-169">1800</span><span class="sxs-lookup"><span data-stu-id="1ac7a-169">1800</span></span>  <br/> |
   
    ![DNSMadeEasy — BP — configure – 2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="1ac7a-171">Нажмите кнопку **послать**.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-171">Select **Submit**.</span></span>
    
    ![DNSMadeEasy — BP — configure – 2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="1ac7a-173">Если в разделе **MX Records** (Записи MX) есть другие записи MX, выберите их.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-173">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![DNSMadeEasy — BP — configure – 2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="1ac7a-175">После выбора всех записей выберите пункт **Удалить выбранные**.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-175">When all records are selected, select **Delete selected**.</span></span>
    
    ![DNSMadeEasy — BP — configure – 2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="1ac7a-177">В диалоговом окне **Удаление записей MX** нажмите кнопку **Удалить** , чтобы подтвердить изменения.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-177">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![DNSMadeEasy — BP — configure – 2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="1ac7a-179">Добавление пяти записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="1ac7a-179">Add the five CNAME records that are required for Office 365</span></span>
<span data-ttu-id="1ac7a-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="1ac7a-180"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="1ac7a-p110">Чтобы приступить к работе, откройте страницу со своими доменами на сайте DNSMadeEasy по [этой ссылке](https://cp.dnsmadeeasy.com/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="1ac7a-183">На странице **консоли управления** в области **Недавно обновленные домены** выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-183">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="1ac7a-184">На странице **УПРАВЛЯЕМЫХ DNS** в области **записи CNAME** выберите элемент управления **("+"** ) ( **Добавить новый**).</span><span class="sxs-lookup"><span data-stu-id="1ac7a-184">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="1ac7a-185">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="1ac7a-185">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy — BP — configure – 3-1](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="1ac7a-187">Добавьте первую из пяти записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-187">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="1ac7a-188">В поля для новой записи в области **Add CNAME Records** (Добавление записей CNAME) введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-188">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="1ac7a-189">**Название**</span><span class="sxs-lookup"><span data-stu-id="1ac7a-189">**Name**</span></span>|<span data-ttu-id="1ac7a-190">**Alias to (Псевдоним для)**</span><span class="sxs-lookup"><span data-stu-id="1ac7a-190">**Alias to**</span></span>|<span data-ttu-id="1ac7a-191">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="1ac7a-191">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="1ac7a-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="1ac7a-192">autodiscover</span></span>  <br/> |<span data-ttu-id="1ac7a-193">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="1ac7a-194">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="1ac7a-194">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="1ac7a-195">1800</span><span class="sxs-lookup"><span data-stu-id="1ac7a-195">1800</span></span>  <br/> |
    |<span data-ttu-id="1ac7a-196">sip</span><span class="sxs-lookup"><span data-stu-id="1ac7a-196">sip</span></span>  <br/> |<span data-ttu-id="1ac7a-197">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-197">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1ac7a-198">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="1ac7a-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="1ac7a-199">1800</span><span class="sxs-lookup"><span data-stu-id="1ac7a-199">1800</span></span>  <br/> |
    |<span data-ttu-id="1ac7a-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1ac7a-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="1ac7a-201">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-201">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1ac7a-202">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="1ac7a-202">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="1ac7a-203">1800</span><span class="sxs-lookup"><span data-stu-id="1ac7a-203">1800</span></span>  <br/> |
    |<span data-ttu-id="1ac7a-204">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="1ac7a-204">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="1ac7a-205">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-205">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="1ac7a-206">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="1ac7a-206">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="1ac7a-207">1800</span><span class="sxs-lookup"><span data-stu-id="1ac7a-207">1800</span></span>  <br/> |
    |<span data-ttu-id="1ac7a-208">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="1ac7a-208">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="1ac7a-209">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-209">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="1ac7a-210">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="1ac7a-210">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="1ac7a-211">1800</span><span class="sxs-lookup"><span data-stu-id="1ac7a-211">1800</span></span>  <br/> |
   
    ![DNSMadeEasy — BP — configure – 3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="1ac7a-213">Нажмите кнопку **послать**.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-213">Select **Submit**.</span></span>
    
    ![DNSMadeEasy — BP — configure – 3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="1ac7a-215">Добавьте все остальные четыре записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-215">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="1ac7a-216">В разделе **CNAME Records (записи CNAME** **) выберите элемент управления** ( **Добавить новый**), создайте запись, используя значения из следующей строки таблицы, а затем еще раз нажмите кнопку **послать** , чтобы завершить эту запись.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-216">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="1ac7a-217">Повторяйте эту процедуру, пока не будут созданы все пять записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-217">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="1ac7a-218">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="1ac7a-218">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="1ac7a-219"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="1ac7a-219"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ac7a-220">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-220">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="1ac7a-221">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-221">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="1ac7a-222">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-222">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="1ac7a-223">Вместо этого добавьте необходимые значения Office 365 в текущую запись. Таким образом, в *одной* записи SPF будут указаны оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-223">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="1ac7a-224">Нужны примеры?</span><span class="sxs-lookup"><span data-stu-id="1ac7a-224">Need examples?</span></span> <span data-ttu-id="1ac7a-225">Ознакомьтесь с этими [сведениями и образцами записей SPF](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="1ac7a-225">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="1ac7a-226">Чтобы проверить запись SPF, можно использовать один из этих[средств проверки SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="1ac7a-226">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="1ac7a-227">Чтобы приступить к работе, откройте страницу со своими доменами на сайте DNSMadeEasy по [этой ссылке](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="1ac7a-227">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="1ac7a-228">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-228">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="1ac7a-229">На странице **консоли управления** в области **Недавно обновленные домены** выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-229">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="1ac7a-230">На странице **УПРАВЛЯЕМЫХ DNS** в области **записи TXT** выберите элемент управления **("+"** ) ( **Добавить новый**).</span><span class="sxs-lookup"><span data-stu-id="1ac7a-230">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="1ac7a-231">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="1ac7a-231">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy — BP — configure – 4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="1ac7a-233">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-233">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="1ac7a-234">**Name**</span><span class="sxs-lookup"><span data-stu-id="1ac7a-234">**Name**</span></span>|<span data-ttu-id="1ac7a-235">**Value** (Значение)</span><span class="sxs-lookup"><span data-stu-id="1ac7a-235">**Value**</span></span>|<span data-ttu-id="1ac7a-236">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="1ac7a-236">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="1ac7a-237">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="1ac7a-237">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1ac7a-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="1ac7a-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="1ac7a-239">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="1ac7a-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="1ac7a-240">1800</span><span class="sxs-lookup"><span data-stu-id="1ac7a-240">1800</span></span>  <br/> |
   
    ![DNSMadeEasy — BP — configure – 4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="1ac7a-242">Нажмите кнопку **послать**.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-242">Select **Submit**.</span></span>
    
    ![DNSMadeEasy — BP — configure – 4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="1ac7a-244">Добавление двух записей SRV, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="1ac7a-244">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="1ac7a-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="1ac7a-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="1ac7a-p113">Чтобы приступить к работе, откройте страницу со своими доменами на сайте DNSMadeEasy по [этой ссылке](https://cp.dnsmadeeasy.com/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="1ac7a-248">На странице **консоли управления** в области **Недавно обновленные домены** выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-248">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="1ac7a-249">На странице **Managed DNS** ( **записи SRV** ) выберите элемент управления **(+)** ( **Добавить новый**).</span><span class="sxs-lookup"><span data-stu-id="1ac7a-249">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="1ac7a-250">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="1ac7a-250">(You may have to scroll down)</span></span>
    
    ![DNSMadeEasy — BP — configure – 5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="1ac7a-252">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-252">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="1ac7a-253">В поля для новой записи в области **Add SRV Records** (Добавление записей SRV) введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-253">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="1ac7a-254">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="1ac7a-254">**Name**</span></span>|<span data-ttu-id="1ac7a-255">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="1ac7a-255">**Priority**</span></span>|<span data-ttu-id="1ac7a-256">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="1ac7a-256">**Weight**</span></span>|<span data-ttu-id="1ac7a-257">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="1ac7a-257">**Port**</span></span>|<span data-ttu-id="1ac7a-258">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="1ac7a-258">**Host**</span></span>|<span data-ttu-id="1ac7a-259">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="1ac7a-259">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1ac7a-260">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="1ac7a-260">_sip._tls</span></span>  <br/> |<span data-ttu-id="1ac7a-261">100</span><span class="sxs-lookup"><span data-stu-id="1ac7a-261">100</span></span>  <br/> |<span data-ttu-id="1ac7a-262">1,1</span><span class="sxs-lookup"><span data-stu-id="1ac7a-262">1</span></span>  <br/> |<span data-ttu-id="1ac7a-263">443</span><span class="sxs-lookup"><span data-stu-id="1ac7a-263">443</span></span>  <br/> |<span data-ttu-id="1ac7a-264">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-264">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1ac7a-265">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="1ac7a-265">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="1ac7a-266">1800</span><span class="sxs-lookup"><span data-stu-id="1ac7a-266">1800</span></span>  <br/> |
    |<span data-ttu-id="1ac7a-267">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="1ac7a-267">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="1ac7a-268">100</span><span class="sxs-lookup"><span data-stu-id="1ac7a-268">100</span></span>  <br/> |<span data-ttu-id="1ac7a-269">1,1</span><span class="sxs-lookup"><span data-stu-id="1ac7a-269">1</span></span>  <br/> |<span data-ttu-id="1ac7a-270">5061</span><span class="sxs-lookup"><span data-stu-id="1ac7a-270">5061</span></span>  <br/> |<span data-ttu-id="1ac7a-271">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-271">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="1ac7a-272">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="1ac7a-272">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="1ac7a-273">1800</span><span class="sxs-lookup"><span data-stu-id="1ac7a-273">1800</span></span>  <br/> |
   
    ![DNSMadeEasy — BP — configure – 5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="1ac7a-275">Нажмите кнопку **послать**.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-275">Select **Submit**.</span></span>
    
    ![DNSMadeEasy — BP — configure – 5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="1ac7a-277">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="1ac7a-278">В разделе **SRV Records (записи SRV** ) выберите элемент управления **(** **Добавить новый**), создайте запись, используя значения из следующей строки таблицы, а затем еще раз нажмите кнопку **послать** , чтобы завершить эту запись.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-278">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="1ac7a-p114">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1ac7a-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

