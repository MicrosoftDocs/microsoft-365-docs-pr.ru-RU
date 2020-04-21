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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу DNSMadeEasy для Майкрософт.
ms.openlocfilehash: dde060b6e03eebb89029b742402558e95031b1d3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629687"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a><span data-ttu-id="3618e-103">Создание записей DNS на сайте DNSMadeEasy для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3618e-103">Create DNS records at DNSMadeEasy for Microsoft</span></span>

 <span data-ttu-id="3618e-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="3618e-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="3618e-105">Если ваш поставщик услуг размещения DNS  DNSMadeEasy, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="3618e-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="3618e-106">Когда вы добавите эти записи на сайте DNSMadeEasy, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3618e-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="3618e-107">Чтобы узнать о размещении и DNS для веб-сайтов с помощью Microsoft, ознакомьтесь со статьей [использование общедоступного веб-сайта с корпорацией Майкрософт](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="3618e-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3618e-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="3618e-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="3618e-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="3618e-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="3618e-110">Если у вас возникли проблемы с процессом обработки почты или другими проблемами после добавления записей DNS, ознакомьтесь с разрешениями [и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3618e-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="3618e-111">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="3618e-111">Add a TXT record for verification</span></span>
<span data-ttu-id="3618e-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="3618e-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="3618e-113">Перед использованием домена с корпорацией Майкрософт необходимо убедиться, что вы являетесь его владельцем.</span><span class="sxs-lookup"><span data-stu-id="3618e-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="3618e-114">Вы можете войти в свою учетную запись у вас в вашем регистраторе доменных имен и создать запись DNS в Майкрософт, если вы владеете этим доменом.</span><span class="sxs-lookup"><span data-stu-id="3618e-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3618e-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="3618e-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="3618e-117">Если вы используете учетную запись DNSMadeEasy, это означает, что добавленный вами домен приобретен у другой компании  регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="3618e-117">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="3618e-118">DNSMadeEasy не предоставляет услуг по регистрации доменных имен.</span><span class="sxs-lookup"><span data-stu-id="3618e-118">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="3618e-119">Если вы можете выполнить вход на сайте DNSMadeEasy и создать запись DNS, это подтверждает ваше владение доменом.</span><span class="sxs-lookup"><span data-stu-id="3618e-119">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="3618e-120">Чтобы приступить к работе, откройте страницу со своими доменами на сайте DNSMadeEasy по [этой ссылке](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="3618e-120">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="3618e-121">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="3618e-121">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="3618e-122">На странице **консоли управления** в области **Недавно обновленные домены** выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="3618e-122">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="3618e-123">На странице **Managed DNS** в области **записи TXT** выберите элемент ( **+** **Добавить новый**).</span><span class="sxs-lookup"><span data-stu-id="3618e-123">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="3618e-124">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="3618e-124">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="3618e-125">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3618e-125">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="3618e-126">**Имя**</span><span class="sxs-lookup"><span data-stu-id="3618e-126">**Name**</span></span> <br/> |<span data-ttu-id="3618e-127">**Value** (Значение)</span><span class="sxs-lookup"><span data-stu-id="3618e-127">**Value**</span></span> <br/> |<span data-ttu-id="3618e-128">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="3618e-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="3618e-129">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="3618e-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="3618e-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="3618e-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="3618e-131">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="3618e-131">**Note:** This is an example.</span></span> <span data-ttu-id="3618e-132">Используйте указанную здесь **конечную точку или значение адреса** из таблицы.</span><span class="sxs-lookup"><span data-stu-id="3618e-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="3618e-133">Как найти это значение?</span><span class="sxs-lookup"><span data-stu-id="3618e-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="3618e-134">1800</span><span class="sxs-lookup"><span data-stu-id="3618e-134">1800</span></span>  <br/> |
   
5. <span data-ttu-id="3618e-135">Нажмите кнопку **послать**.</span><span class="sxs-lookup"><span data-stu-id="3618e-135">Select **Submit**.</span></span>
    
6. <span data-ttu-id="3618e-136">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="3618e-136">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="3618e-137">Теперь, когда вы добавили запись на сайте регистратора доменных имен, вернитесь в корпорацию Майкрософт и запросите запись.</span><span class="sxs-lookup"><span data-stu-id="3618e-137">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="3618e-138">После того как корпорация Майкрософт обнаружит правильную запись TXT, ваш домен будет проверен.</span><span class="sxs-lookup"><span data-stu-id="3618e-138">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="3618e-139">В центре администрирования Майкрософт перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> **параметров** \> ".</span><span class="sxs-lookup"><span data-stu-id="3618e-139">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="3618e-140">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="3618e-140">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="3618e-141">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="3618e-141">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="3618e-142">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="3618e-142">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3618e-143">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="3618e-143">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="3618e-144">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="3618e-144">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="3618e-145">Если у вас возникли проблемы с процессом обработки почты или другими проблемами после добавления записей DNS, ознакомьтесь с разрешениями [и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3618e-145">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="3618e-146">Добавление записи MX для отправки электронной почты для вашего домена в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3618e-146">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="3618e-147"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="3618e-147"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="3618e-p108">Чтобы приступить к работе, откройте страницу со своими доменами на сайте DNSMadeEasy по [этой ссылке](https://cp.dnsmadeeasy.com/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="3618e-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="3618e-150">На странице **консоли управления** в области **Недавно обновленные домены** выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="3618e-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="3618e-151">На странице **консоли управления** в области **Недавно обновленные домены** выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="3618e-151">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![DNSMadeEasy — BP — configure – 1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="3618e-153">На странице **управляемых DNS** в области MX- **записи** выберите элемент управления **(+)** ( **Добавить новый**).</span><span class="sxs-lookup"><span data-stu-id="3618e-153">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="3618e-154">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="3618e-154">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy — BP — configure – 2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="3618e-156">В поля для новой записи в области **Add MX Records** (Добавление записей MX) введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="3618e-156">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3618e-157">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="3618e-157">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="3618e-158">**Name**</span><span class="sxs-lookup"><span data-stu-id="3618e-158">**Name**</span></span>|<span data-ttu-id="3618e-159">**Server**</span><span class="sxs-lookup"><span data-stu-id="3618e-159">**Server**</span></span>|<span data-ttu-id="3618e-160">**MX Level (Уровень MX)**</span><span class="sxs-lookup"><span data-stu-id="3618e-160">**MX Level**</span></span>|<span data-ttu-id="3618e-161">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="3618e-161">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3618e-162">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="3618e-162">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="3618e-163">*\<ключ_домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="3618e-163">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="3618e-164">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="3618e-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="3618e-165">**Примечание:** \<Получите *ключ* \> домена из учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3618e-165">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="3618e-166">Где это находится?</span><span class="sxs-lookup"><span data-stu-id="3618e-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="3618e-167">10 </span><span class="sxs-lookup"><span data-stu-id="3618e-167">10</span></span>  <br/> <span data-ttu-id="3618e-168">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).   </span><span class="sxs-lookup"><span data-stu-id="3618e-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="3618e-169">1800</span><span class="sxs-lookup"><span data-stu-id="3618e-169">1800</span></span>  <br/> |
   
    ![DNSMadeEasy — BP — configure – 2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="3618e-171">Нажмите кнопку **послать**.</span><span class="sxs-lookup"><span data-stu-id="3618e-171">Select **Submit**.</span></span>
    
    ![DNSMadeEasy — BP — configure – 2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="3618e-173">Если в разделе **MX Records** (Записи MX) есть другие записи MX, выберите их.</span><span class="sxs-lookup"><span data-stu-id="3618e-173">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![DNSMadeEasy — BP — configure – 2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="3618e-175">После выбора всех записей выберите пункт **Удалить выбранные**.</span><span class="sxs-lookup"><span data-stu-id="3618e-175">When all records are selected, select **Delete selected**.</span></span>
    
    ![DNSMadeEasy — BP — configure – 2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="3618e-177">В диалоговом окне **Удаление записей MX** нажмите кнопку **Удалить** , чтобы подтвердить изменения.</span><span class="sxs-lookup"><span data-stu-id="3618e-177">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![DNSMadeEasy — BP — configure – 2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="3618e-179">Добавление пяти записей CNAME, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3618e-179">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="3618e-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="3618e-180"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="3618e-p110">Чтобы приступить к работе, откройте страницу со своими доменами на сайте DNSMadeEasy по [этой ссылке](https://cp.dnsmadeeasy.com/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="3618e-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="3618e-183">На странице **консоли управления** в области **Недавно обновленные домены** выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="3618e-183">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="3618e-184">На странице **УПРАВЛЯЕМЫХ DNS** в области **записи CNAME** выберите элемент управления **("+"** ) ( **Добавить новый**).</span><span class="sxs-lookup"><span data-stu-id="3618e-184">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="3618e-185">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="3618e-185">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy — BP — configure – 3-1](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="3618e-187">Добавьте первую из пяти записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="3618e-187">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="3618e-188">В поля для новой записи в области **Add CNAME Records** (Добавление записей CNAME) введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="3618e-188">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="3618e-189">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="3618e-189">**Name**</span></span>|<span data-ttu-id="3618e-190">**Alias to (Псевдоним для)**</span><span class="sxs-lookup"><span data-stu-id="3618e-190">**Alias to**</span></span>|<span data-ttu-id="3618e-191">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="3618e-191">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="3618e-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="3618e-192">autodiscover</span></span>  <br/> |<span data-ttu-id="3618e-193">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="3618e-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="3618e-194">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="3618e-194">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="3618e-195">1800</span><span class="sxs-lookup"><span data-stu-id="3618e-195">1800</span></span>  <br/> |
    |<span data-ttu-id="3618e-196">sip</span><span class="sxs-lookup"><span data-stu-id="3618e-196">sip</span></span>  <br/> |<span data-ttu-id="3618e-197">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3618e-197">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="3618e-198">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="3618e-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="3618e-199">1800</span><span class="sxs-lookup"><span data-stu-id="3618e-199">1800</span></span>  <br/> |
    |<span data-ttu-id="3618e-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3618e-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="3618e-201">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3618e-201">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="3618e-202">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="3618e-202">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="3618e-203">1800</span><span class="sxs-lookup"><span data-stu-id="3618e-203">1800</span></span>  <br/> |
    |<span data-ttu-id="3618e-204">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="3618e-204">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="3618e-205">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="3618e-205">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="3618e-206">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="3618e-206">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="3618e-207">1800</span><span class="sxs-lookup"><span data-stu-id="3618e-207">1800</span></span>  <br/> |
    |<span data-ttu-id="3618e-208">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="3618e-208">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="3618e-209">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="3618e-209">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="3618e-210">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="3618e-210">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="3618e-211">1800</span><span class="sxs-lookup"><span data-stu-id="3618e-211">1800</span></span>  <br/> |
   
    ![DNSMadeEasy — BP — configure – 3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="3618e-213">Нажмите кнопку **послать**.</span><span class="sxs-lookup"><span data-stu-id="3618e-213">Select **Submit**.</span></span>
    
    ![DNSMadeEasy — BP — configure – 3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="3618e-215">Добавьте все остальные четыре записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="3618e-215">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="3618e-216">В разделе **CNAME Records (записи CNAME** **) выберите элемент управления** ( **Добавить новый**), создайте запись, используя значения из следующей строки таблицы, а затем еще раз нажмите кнопку **послать** , чтобы завершить эту запись.</span><span class="sxs-lookup"><span data-stu-id="3618e-216">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="3618e-217">Повторяйте эту процедуру, пока не будут созданы все пять записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="3618e-217">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="3618e-218">Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама</span><span class="sxs-lookup"><span data-stu-id="3618e-218">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="3618e-219"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="3618e-219"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="3618e-220">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="3618e-220">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="3618e-221">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="3618e-221">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="3618e-222">Если у вас уже есть запись SPF для вашего домена, не создавайте ее для Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3618e-222">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="3618e-223">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="3618e-223">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="3618e-224">Нужны примеры?</span><span class="sxs-lookup"><span data-stu-id="3618e-224">Need examples?</span></span> <span data-ttu-id="3618e-225">Ознакомьтесь с этими [записями о внешних доменных именах для Майкрософт](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="3618e-225">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="3618e-226">Чтобы проверить запись SPF, можно использовать один из этих[средств проверки SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="3618e-226">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="3618e-227">Чтобы приступить к работе, откройте страницу со своими доменами на сайте DNSMadeEasy по [этой ссылке](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="3618e-227">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="3618e-228">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="3618e-228">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="3618e-229">На странице **консоли управления** в области **Недавно обновленные домены** выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="3618e-229">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="3618e-230">На странице **УПРАВЛЯЕМЫХ DNS** в области **записи TXT** выберите элемент управления **("+"** ) ( **Добавить новый**).</span><span class="sxs-lookup"><span data-stu-id="3618e-230">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="3618e-231">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="3618e-231">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy — BP — configure – 4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="3618e-233">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3618e-233">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="3618e-234">**Name**</span><span class="sxs-lookup"><span data-stu-id="3618e-234">**Name**</span></span>|<span data-ttu-id="3618e-235">**Value** (Значение)</span><span class="sxs-lookup"><span data-stu-id="3618e-235">**Value**</span></span>|<span data-ttu-id="3618e-236">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="3618e-236">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="3618e-237">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="3618e-237">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="3618e-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="3618e-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="3618e-239">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="3618e-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="3618e-240">1800</span><span class="sxs-lookup"><span data-stu-id="3618e-240">1800</span></span>  <br/> |
   
    ![DNSMadeEasy — BP — configure – 4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="3618e-242">Нажмите кнопку **послать**.</span><span class="sxs-lookup"><span data-stu-id="3618e-242">Select **Submit**.</span></span>
    
    ![DNSMadeEasy — BP — configure – 4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="3618e-244">Добавление двух записей SRV, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3618e-244">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="3618e-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="3618e-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="3618e-p113">Чтобы приступить к работе, откройте страницу со своими доменами на сайте DNSMadeEasy по [этой ссылке](https://cp.dnsmadeeasy.com/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="3618e-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="3618e-248">На странице **консоли управления** в области **Недавно обновленные домены** выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="3618e-248">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="3618e-249">На странице **Managed DNS** ( **записи SRV** ) выберите элемент управления **(+)** ( **Добавить новый**).</span><span class="sxs-lookup"><span data-stu-id="3618e-249">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="3618e-250">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="3618e-250">(You may have to scroll down)</span></span>
    
    ![DNSMadeEasy — BP — configure – 5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="3618e-252">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="3618e-252">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="3618e-253">В поля для новой записи в области **Add SRV Records** (Добавление записей SRV) введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="3618e-253">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="3618e-254">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="3618e-254">**Name**</span></span>|<span data-ttu-id="3618e-255">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="3618e-255">**Priority**</span></span>|<span data-ttu-id="3618e-256">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="3618e-256">**Weight**</span></span>|<span data-ttu-id="3618e-257">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="3618e-257">**Port**</span></span>|<span data-ttu-id="3618e-258">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="3618e-258">**Host**</span></span>|<span data-ttu-id="3618e-259">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="3618e-259">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3618e-260">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="3618e-260">_sip._tls</span></span>  <br/> |<span data-ttu-id="3618e-261">100</span><span class="sxs-lookup"><span data-stu-id="3618e-261">100</span></span>  <br/> |<span data-ttu-id="3618e-262">1,1</span><span class="sxs-lookup"><span data-stu-id="3618e-262">1</span></span>  <br/> |<span data-ttu-id="3618e-263">443</span><span class="sxs-lookup"><span data-stu-id="3618e-263">443</span></span>  <br/> |<span data-ttu-id="3618e-264">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3618e-264">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="3618e-265">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="3618e-265">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="3618e-266">1800</span><span class="sxs-lookup"><span data-stu-id="3618e-266">1800</span></span>  <br/> |
    |<span data-ttu-id="3618e-267">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="3618e-267">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="3618e-268">100</span><span class="sxs-lookup"><span data-stu-id="3618e-268">100</span></span>  <br/> |<span data-ttu-id="3618e-269">1,1</span><span class="sxs-lookup"><span data-stu-id="3618e-269">1</span></span>  <br/> |<span data-ttu-id="3618e-270">5061</span><span class="sxs-lookup"><span data-stu-id="3618e-270">5061</span></span>  <br/> |<span data-ttu-id="3618e-271">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3618e-271">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="3618e-272">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="3618e-272">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="3618e-273">1800</span><span class="sxs-lookup"><span data-stu-id="3618e-273">1800</span></span>  <br/> |
   
    ![DNSMadeEasy — BP — configure – 5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="3618e-275">Нажмите кнопку **послать**.</span><span class="sxs-lookup"><span data-stu-id="3618e-275">Select **Submit**.</span></span>
    
    ![DNSMadeEasy — BP — configure – 5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="3618e-277">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="3618e-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="3618e-278">В разделе **SRV Records (записи SRV** ) выберите элемент управления **(** **Добавить новый**), создайте запись, используя значения из следующей строки таблицы, а затем еще раз нажмите кнопку **послать** , чтобы завершить эту запись.</span><span class="sxs-lookup"><span data-stu-id="3618e-278">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="3618e-279">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="3618e-279">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="3618e-280">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="3618e-280">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="3618e-281">Если у вас возникли проблемы с процессом обработки почты или другими проблемами после добавления записей DNS, ознакомьтесь с разрешениями [и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3618e-281">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

