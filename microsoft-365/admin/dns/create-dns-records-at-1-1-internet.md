---
title: Создайте записи DNS на 1&1 ИОНОС для Office 365
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб на 1&1 ИОНОС для Office 365.
ms.openlocfilehash: 88a46fa51ac3e259d617d6d6e1a3dbb189c1ee6d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42246860"
---
# <a name="create-dns-records-at-11-ionos-for-office-365"></a><span data-ttu-id="ac4f4-103">Создайте записи DNS на 1&1 ИОНОС для Office 365</span><span class="sxs-lookup"><span data-stu-id="ac4f4-103">Create DNS records at 1&1 IONOS for Office 365</span></span>

 <span data-ttu-id="ac4f4-104">Если вы не нашли то, что вы ищете, обратитесь к разделу **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="ac4f4-105">Обратите внимание, что 1&1 ИОНОС не позволяет домену иметь запись MX и запись CNAME верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-105">Note that 1&1 IONOS doesn't allow a domain to have both an MX record and a top-level Autodiscover CNAME record.</span></span> <span data-ttu-id="ac4f4-106">Это позволяет ограничить способы настройки Exchange Online для Office 365.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-106">This limits the ways in which you can configure Exchange Online for Office 365.</span></span> <span data-ttu-id="ac4f4-107">Существует обходной путь, но мы рекомендуем использовать его, **только** если у вас уже есть опыт создания поддоменов на 1&1 ионос 1.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-107">There is a workaround, but we recommend employing it **only** if you already have experience with creating subdomains at 1&1 IONOS.</span></span> <span data-ttu-id="ac4f4-108">> если несмотря на это [ограничение службы](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) вы решили управлять собственными ЗАПИСЯМи DNS для Office 365 по адресу 1&1 ионос, выполните действия, описанные в этой статье, чтобы проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и т. д.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-108">> If despite this [service limitation](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) you choose to manage your own Office 365 DNS records at 1&1 IONOS, follow the steps in this article to verify your domain and to set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="ac4f4-109">Когда вы добавите эти записи на 1&1 ИОНОС, ваш домен будет настроен для работы со службами Office 365.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-109">After you add these records at 1&1 IONOS, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="ac4f4-110">Дополнительные сведения о веб-хостинге и размещении DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="ac4f4-110">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ac4f4-p102">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ac4f4-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="ac4f4-114">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="ac4f4-114">Add a TXT record for verification</span></span>

<span data-ttu-id="ac4f4-p103">Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете данным доменом.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ac4f4-p104">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="ac4f4-119">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="ac4f4-119">Follow the steps below or [watch the video (start at 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="ac4f4-120">Чтобы приступить к работе, перейдите на страницу своих доменов по адресу 1&1 ИОНОС, используя [эту ссылку](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="ac4f4-120">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="ac4f4-121">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-121">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="ac4f4-122">Выберите **Управление доменами**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-122">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="ac4f4-123">На странице " **центр домена** " найдите домен, который необходимо обновить, а затем выберите элемент управления **Panel** ( **v**) для этого домена.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-123">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="ac4f4-124">В области **Параметры домена** выберите **изменить параметры DNS**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-124">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="ac4f4-125">В разделе **txt and SRV Records (записи TXT и SRV** ) выберите **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-125">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="ac4f4-126">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-126">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ac4f4-127">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-127">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="ac4f4-128">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-128">**Type**</span></span> <br/> |<span data-ttu-id="ac4f4-129">**Prefix (Префикс)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-129">**Prefix**</span></span> <br/> |<span data-ttu-id="ac4f4-130">**Name Value (Значение имени)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-130">**Name Value**</span></span> <br/> |
    |<span data-ttu-id="ac4f4-131">TXT</span><span class="sxs-lookup"><span data-stu-id="ac4f4-131">TXT</span></span>  <br/> |<span data-ttu-id="ac4f4-132">(Оставьте это поле пустым)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-132">(Leave this field blank)</span></span>  <br/> |<span data-ttu-id="ac4f4-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="ac4f4-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="ac4f4-134">Примечание: это пример.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-134">NOTE: This is an example.</span></span> <span data-ttu-id="ac4f4-135">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-135">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="ac4f4-136">Как найти это значение?</span><span class="sxs-lookup"><span data-stu-id="ac4f4-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="ac4f4-137">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-137">Select **Save**.</span></span>
    
8. <span data-ttu-id="ac4f4-138">Снова нажмите кнопку **сохранить** .</span><span class="sxs-lookup"><span data-stu-id="ac4f4-138">Select **Save** again.</span></span> 
    
9. <span data-ttu-id="ac4f4-139">В диалоговом окне **изменение параметров DNS** нажмите **кнопку Да**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-139">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="ac4f4-140">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="ac4f4-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="ac4f4-142">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="ac4f4-143">В центре администрирования перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> **параметров** \> ".</span><span class="sxs-lookup"><span data-stu-id="ac4f4-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="ac4f4-144">На странице **Domains (домены** ) выберите домен, который вы хотите проверить.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="ac4f4-145">На странице **Настройка** выберите пункт **Запуск программы установки**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="ac4f4-146">На странице **Проверка домена** нажмите кнопку **проверить**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ac4f4-p107">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ac4f4-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="ac4f4-150">Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="ac4f4-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="ac4f4-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="ac4f4-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="ac4f4-152">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="ac4f4-152">Follow the steps below or [watch the video (start at 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ac4f4-153">Если вы зарегистрировались с помощью 1und1.de, [выполните вход здесь](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="ac4f4-153">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="ac4f4-154">Чтобы приступить к работе, перейдите на страницу своих доменов по адресу 1&1 ИОНОС, используя [эту ссылку](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="ac4f4-154">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="ac4f4-155">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-155">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="ac4f4-156">Выберите **Управление доменами**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-156">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="ac4f4-157">На странице " **центр домена** " найдите домен, который необходимо обновить, а затем выберите элемент управления **Panel** ( **v**) для этого домена.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-157">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="ac4f4-158">В области **Параметры домена** выберите **изменить параметры DNS**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-158">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="ac4f4-159">In the **MX Records** section, in the \*\* Mail Exchanger (MX Record) \*\* area, select **Other mail server**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-159">In the **MX Records** section, in the \*\* Mail Exchanger (MX Record) \*\* area, select **Other mail server**.</span></span><br/><span data-ttu-id="ac4f4-160">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-160">(You may have to scroll down.)</span></span><br/><span data-ttu-id="ac4f4-161">![1&amp;1 — BP — Configure – 2-1](../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-161">![1&amp;1-BP-Configure-2-1](../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span></span> <br/>
  
6. <span data-ttu-id="ac4f4-162">Если уже указаны другие записи MX, удалите их, выбрав каждую из них и нажав клавишу **DELETE**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-162">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span></span><br/><span data-ttu-id="ac4f4-163">(Если записи MX не указаны, перейдите к следующему действию.)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-163">(If there are no MX records already listed, continue to the next step.)</span></span><br/><span data-ttu-id="ac4f4-164">![1&amp;1 — BP — Configure – 2-2](../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-164">![1&amp;1-BP-Configure-2-2](../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span></span><br/>
  
7. <span data-ttu-id="ac4f4-165">В поля для записи **MX 1** введите (или скопируйте и вставьте) значения из приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-165">In the boxes for the **MX 1** record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="ac4f4-166">**MX 1**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-166">**MX 1**</span></span>|<span data-ttu-id="ac4f4-167">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-167">**Priority**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="ac4f4-168">*\<ключ-домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ac4f4-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <span data-ttu-id="ac4f4-169">Примечание: получите ключ \<\> домена из учетной записи Office 365.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-169">NOTE: Get your \<domain-key\> from your Office 365 account.</span></span> [<span data-ttu-id="ac4f4-170">Где это находится?</span><span class="sxs-lookup"><span data-stu-id="ac4f4-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="ac4f4-171">10 </span><span class="sxs-lookup"><span data-stu-id="ac4f4-171">10</span></span>  <br/> <span data-ttu-id="ac4f4-172">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).   </span><span class="sxs-lookup"><span data-stu-id="ac4f4-172">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | 
    
    ![1 и 1 — Настройка 2 и 3](../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. <span data-ttu-id="ac4f4-174">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-174">Select **Save**.</span></span><br/><span data-ttu-id="ac4f4-175">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-175">(You may have to scroll down.)</span></span><br/><span data-ttu-id="ac4f4-176">![1&amp;1 — BP — Configure – 2-4](../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-176">![1&amp;1-BP-Configure-2-4](../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span></span>
  
9. <span data-ttu-id="ac4f4-177">В диалоговом окне **изменение параметров DNS** нажмите **кнопку Да**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-177">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="ac4f4-178">![Выбор параметра "Да" в диалоговом окне Изменение параметров DNS](../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-178">![Selecting Yes in the Edit DNS Settings dialog box](../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="ac4f4-179">Добавление шести записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="ac4f4-179">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="ac4f4-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="ac4f4-180"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="ac4f4-181">1&1 для ИОНОС требуется обходной путь, чтобы можно было использовать запись MX вместе с записями CNAME, необходимыми для служб электронной почты Office 365.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-181">1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records that are required for Office 365 email services.</span></span> <span data-ttu-id="ac4f4-182">Для этого обходного пути необходимо создать набор поддоменов на 1&1 ИОНОС и назначить им записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-182">This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ac4f4-183">Прежде чем начать эту процедуру, убедитесь в том, что доступно по крайней мере два поддомена.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-183">Make sure that you have at least two available subdomains before starting this procedure.</span></span> <span data-ttu-id="ac4f4-184">Это решение рекомендуется только в том случае, если у вас уже есть опыт создания поддоменов по адресу 1&1 ИОНОС.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-184">We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.</span></span> 
  
### <a name="basic-cname-records"></a><span data-ttu-id="ac4f4-185">Основные записи CNAME</span><span class="sxs-lookup"><span data-stu-id="ac4f4-185">Basic CNAME records</span></span>

<span data-ttu-id="ac4f4-186">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="ac4f4-186">Follow the steps below or [watch the video (start at 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ac4f4-187">Если вы зарегистрировались с помощью 1und1.de, [выполните вход здесь](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="ac4f4-187">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="ac4f4-188">Чтобы приступить к работе, перейдите на страницу своих доменов по адресу 1&1 ИОНОС, используя [эту ссылку](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="ac4f4-188">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="ac4f4-189">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-189">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="ac4f4-190">Выберите **Управление доменами**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-190">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="ac4f4-191">На странице " **центр домена** " найдите домен, который необходимо обновить, и выберите пункт **Управление поддоменами**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-191">On the **Domain Center** page, find the domain that you want to update, and then select **Manage Subdomains**.</span></span><br/><span data-ttu-id="ac4f4-192">![1&amp;1 — BP — Configure – 3-0](../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-192">![1&amp;1-BP-Configure-3-0](../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span></span> <br/><span data-ttu-id="ac4f4-193">Теперь нужно создать два поддомена и задать для каждого из них значение **Alias** (Псевдоним).</span><span class="sxs-lookup"><span data-stu-id="ac4f4-193">Now you'll create two subdomains and set an **Alias** value for each.</span></span><br/><span data-ttu-id="ac4f4-194">(Это необходимо, поскольку 1&1 ИОНОС поддерживает только одну запись CNAME верхнего уровня, но для Office 365 требуется несколько записей CNAME.)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-194">(This is required because 1&1 IONOS supports only one top-level CNAME record, but Office 365 requires several CNAME records.)</span></span><br/><span data-ttu-id="ac4f4-195">Сначала необходимо создать поддомен автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-195">First, you'll create the Autodiscover subdomain.</span></span>
    
4. <span data-ttu-id="ac4f4-196">В разделе **Обзор поддомена** выберите **создать поддомен**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-196">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
    ![1&amp;1-BP-Configure-3-1](../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. <span data-ttu-id="ac4f4-p113">В поле **Create Subdomain** (Создать поддомен) для нового поддомена введите или скопируйте и вставьте только значение **Create Subdomain** из приведенной ниже таблицы. (Вы добавите значение **Alias** (Псевдоним) на следующем шаге.)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-p113">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span>

    |<span data-ttu-id="ac4f4-200">**Create Subdomain (Создать поддомен)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-200">**Create Subdomain**</span></span>|<span data-ttu-id="ac4f4-201">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-201">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="ac4f4-202">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ac4f4-202">autodiscover</span></span>  <br/> |<span data-ttu-id="ac4f4-203">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ac4f4-203">autodiscover.outlook.com</span></span>   | 

    ![1&amp;1 — BP — Configure – 3-2](../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. <span data-ttu-id="ac4f4-205">Выберите **создать поддомен**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-205">Select **Create Subdomain**.</span></span><br/><span data-ttu-id="ac4f4-206">![1&amp;1 — BP — Configure – 3-3](../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-206">![1&amp;1-BP-Configure-3-3](../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span></span>
  
7. <span data-ttu-id="ac4f4-207">В разделе **Обзор поддомена** найдите только что созданный поддомен **автообнаружения** , а затем выберите элемент управления **Panel (v)** для этого поддомена.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-207">In the **Subdomain Overview** section, locate the **autodiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="ac4f4-208">![1&amp;1 — BP — Configure – 3-4](../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-208">![1&amp;1-BP-Configure-3-4](../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span></span>
  
8. <span data-ttu-id="ac4f4-209">В области **Параметры поддомена** выберите **изменить параметры DNS**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-209">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span> <br/><span data-ttu-id="ac4f4-210">![1&amp;1 — BP — Configure – 3-5](../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-210">![1&amp;1-BP-Configure-3-5](../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span></span>
  
9. <span data-ttu-id="ac4f4-211">В разделе **A/AAAA Records (IP-адреса)** в области **IP-адрес (запись a)** выберите **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-211">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span><br/><span data-ttu-id="ac4f4-212">![1&amp;1 — BP — Configure – 3-6](../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-212">![1&amp;1-BP-Configure-3-6](../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span></span>
  
10. <span data-ttu-id="ac4f4-213">В поле **Alias** (Псевдоним) введите (или скопируйте и вставьте) значение **Alias** из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-213">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span><br/> 
    
    |<span data-ttu-id="ac4f4-214">**Create Subdomain (Создать поддомен)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-214">**Create Subdomain**</span></span>|<span data-ttu-id="ac4f4-215">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-215">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="ac4f4-216">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ac4f4-216">autodiscover</span></span>  <br/> |<span data-ttu-id="ac4f4-217">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ac4f4-217">autodiscover.outlook.com</span></span>   |

    ![1&amp;1 — BP — Configure – 3-7](../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. <span data-ttu-id="ac4f4-219">Установите флажок в отказе от ответственности **I am aware** (Я понимаю).</span><span class="sxs-lookup"><span data-stu-id="ac4f4-219">Select the check box for the **I am aware** disclaimer.</span></span><br/><span data-ttu-id="ac4f4-220">![1&amp;1 — BP — Configure – 3-8-1](../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-220">![1&amp;1-BP-Configure-3-8-1](../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span></span>
  
12. <span data-ttu-id="ac4f4-221">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-221">Select **Save**.</span></span><br/><span data-ttu-id="ac4f4-222">![1&amp;1 — BP — Configure – 3-8-2](../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-222">![1&amp;1-BP-Configure-3-8-2](../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span></span>
  
  
### <a name="additional-cname-records"></a><span data-ttu-id="ac4f4-223">Дополнительные записи CNAME</span><span class="sxs-lookup"><span data-stu-id="ac4f4-223">Additional CNAME records</span></span>

<span data-ttu-id="ac4f4-p114">Дополнительные записи CNAME, которые создаются с помощью этой процедуры, обеспечивают работу служб Skype для бизнеса online. Вы выполните те же действия, которые использовались для создания двух записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-p114">The additional CNAME records created in the following procedure enable Skype for Business Online services. You will employ the same steps that you used to create the two CNAME records you have already created.</span></span>
  
1. <span data-ttu-id="ac4f4-226">Создайте третий поддомен (Lyncdiscover).</span><span class="sxs-lookup"><span data-stu-id="ac4f4-226">Create the third subdomain (Lyncdiscover).</span></span><br/><span data-ttu-id="ac4f4-227">В разделе **Обзор поддомена** выберите **создать поддомен**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-227">On the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
2. <span data-ttu-id="ac4f4-p115">В поле **Create Subdomain** (Создать поддомен) для нового поддомена введите или скопируйте и вставьте только значение **Create Subdomain** из приведенной ниже таблицы. (Вы добавите значение **Alias** (Псевдоним) на следующем шаге.)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-p115">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span><br/> 
    
    |<span data-ttu-id="ac4f4-230">**Create Subdomain (Создать поддомен)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-230">**Create Subdomain**</span></span>|<span data-ttu-id="ac4f4-231">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-231">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="ac4f4-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ac4f4-232">lyncdiscover</span></span>   |<span data-ttu-id="ac4f4-233">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ac4f4-233">webdir.online.lync.com</span></span>  |
   
3. <span data-ttu-id="ac4f4-234">Выберите **создать поддомен**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-234">Select **Create Subdomain**.</span></span>
    
4. <span data-ttu-id="ac4f4-235">На странице " **центр домена** " выберите пункт **Управление поддоменами**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-235">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
5. <span data-ttu-id="ac4f4-236">В разделе **Обзор поддомена** найдите только что созданный дочерний домен **lyncdiscover** , а затем выберите элемент управления **Panel (v)** для этого поддомена.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-236">In the **Subdomain Overview** section, find the **lyncdiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="ac4f4-237">В области **Параметры поддомена** выберите **изменить параметры DNS**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-237">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
6. <span data-ttu-id="ac4f4-238">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-238">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span></span>
    
7. <span data-ttu-id="ac4f4-239">В поле **Alias** (Псевдоним) введите (или скопируйте и вставьте) значение **Alias** из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-239">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> <br/>
    
    |<span data-ttu-id="ac4f4-240">**Create Subdomain (Создать поддомен)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-240">**Create Subdomain**</span></span>|<span data-ttu-id="ac4f4-241">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-241">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="ac4f4-242">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ac4f4-242">lyncdiscover</span></span>  <br/> |<span data-ttu-id="ac4f4-243">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ac4f4-243">webdir.online.lync.com</span></span>  <br/> |
   
8. <span data-ttu-id="ac4f4-244">Установите флажок для заявления **об** отказе от ответственности, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-244">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
9. <span data-ttu-id="ac4f4-245">В диалоговом окне **изменение параметров DNS** нажмите **кнопку Да**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-245">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="ac4f4-246">Создание четвертого поддомена (SIP)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-246">Create the fourth subdomain (SIP):</span></span> <br/><span data-ttu-id="ac4f4-247">В разделе **Обзор поддомена** выберите **создать поддомен**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-247">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
11. <span data-ttu-id="ac4f4-p116">В поле **Create Subdomain** (Создать поддомен) для нового поддомена введите или скопируйте и вставьте только значение **Create Subdomain** из приведенной ниже таблицы. (Вы добавите значение **Alias** (Псевдоним) на следующем шаге.)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-p116">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.) </span></span><br/>
    
    |<span data-ttu-id="ac4f4-250">**Create Subdomain (Создать поддомен)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-250">**Create Subdomain**</span></span>|<span data-ttu-id="ac4f4-251">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-251">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="ac4f4-252">sip</span><span class="sxs-lookup"><span data-stu-id="ac4f4-252">sip</span></span>  <br/> |<span data-ttu-id="ac4f4-253">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ac4f4-253">sipdir.online.lync.com</span></span>  <br/> |
   
12. <span data-ttu-id="ac4f4-254">Выберите **создать поддомен**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-254">Select **Create Subdomain**.</span></span>
    
13. <span data-ttu-id="ac4f4-255">На странице " **центр домена** " выберите пункт **Управление поддоменами**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-255">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
14. <span data-ttu-id="ac4f4-256">В разделе **Обзор поддомена** найдите только что созданный поддомен **SIP** , а затем выберите элемент управления **Panel (v)** для этого поддомена.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-256">In the **Subdomain Overview** section, find the **sip** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="ac4f4-257">В области **Параметры поддомена** выберите **изменить параметры DNS**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-257">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
15. <span data-ttu-id="ac4f4-258">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-258">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span></span>
    
16. <span data-ttu-id="ac4f4-259">В поле **Alias** (Псевдоним) введите (или скопируйте и вставьте) значение **Alias** из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-259">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> 
    
    |<span data-ttu-id="ac4f4-260">**Create Subdomain (Создать поддомен)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-260">**Create Subdomain**</span></span>|<span data-ttu-id="ac4f4-261">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-261">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="ac4f4-262">sip</span><span class="sxs-lookup"><span data-stu-id="ac4f4-262">sip</span></span>  <br/> |<span data-ttu-id="ac4f4-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ac4f4-263">sipdir.online.lync.com</span></span>  <br/> |
   
17. <span data-ttu-id="ac4f4-264">Установите флажок для заявления **об** отказе от ответственности, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-264">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
18. <span data-ttu-id="ac4f4-265">В диалоговом окне **изменение параметров DNS** нажмите **кнопку Да**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-265">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
### <a name="cname-records-needed-for-mdm"></a><span data-ttu-id="ac4f4-266">Записи CNAME, необходимые для MDM</span><span class="sxs-lookup"><span data-stu-id="ac4f4-266">CNAME records needed for MDM</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac4f4-267">Повторите действия, которые вы совершали при добавлении предыдущих четырех записей CNAME, подставив значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-267">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> 
  
|<span data-ttu-id="ac4f4-268">**Create Subdomain (Создать поддомен)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-268">**Create Subdomain**</span></span>|<span data-ttu-id="ac4f4-269">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-269">**Alias**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ac4f4-270">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="ac4f4-270">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="ac4f4-271">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="ac4f4-271">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="ac4f4-272">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="ac4f4-272">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="ac4f4-273">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ac4f4-273">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="ac4f4-274">Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="ac4f4-274">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac4f4-275">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-275">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="ac4f4-276">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-276">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="ac4f4-277">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-277">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="ac4f4-278">Вместо этого добавьте необходимые значения Office 365 к текущей записи, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-278">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="ac4f4-279">Нужны примеры?</span><span class="sxs-lookup"><span data-stu-id="ac4f4-279">Need examples?</span></span> <span data-ttu-id="ac4f4-280">Ознакомьтесь с этими [сведениями и образцами записей SPF](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="ac4f4-280">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="ac4f4-281">Чтобы проверить запись SPF, можно использовать один из этих[средств проверки SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="ac4f4-281">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
<span data-ttu-id="ac4f4-282">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="ac4f4-282">Follow the steps below or [watch the video (start at 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ac4f4-283">Если вы зарегистрировались с помощью 1und1.de, [выполните вход здесь](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="ac4f4-283">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="ac4f4-284">Чтобы приступить к работе, перейдите на страницу своих доменов по адресу 1&1 ИОНОС, используя [эту ссылку](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="ac4f4-284">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="ac4f4-285">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-285">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="ac4f4-286">Выберите **Управление доменами**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-286">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="ac4f4-287">На странице " **центр домена** " найдите домен, который необходимо обновить, а затем выберите элемент управления **Panel** (**v**) для этого домена.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-287">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** (**v**) control for that domain.</span></span>
    
4. <span data-ttu-id="ac4f4-288">В области **Параметры домена** выберите **изменить параметры DNS**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-288">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="ac4f4-289">В разделе **txt and SRV Records (записи TXT и SRV** ) выберите **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-289">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="ac4f4-290">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-290">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="ac4f4-291">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-291">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> <br/><span data-ttu-id="ac4f4-292">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-292">(Choose the **Type** value from the drop-down list.)</span></span> <br/>
    
    |<span data-ttu-id="ac4f4-293">**Тип**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-293">**Type**</span></span>|<span data-ttu-id="ac4f4-294">**Prefix (Префикс)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-294">**Prefix**</span></span>|<span data-ttu-id="ac4f4-295">**Name Value (Значение имени)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-295">**Name Value**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="ac4f4-296">TXT</span><span class="sxs-lookup"><span data-stu-id="ac4f4-296">TXT</span></span>  <br/> |<span data-ttu-id="ac4f4-297">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-297">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="ac4f4-298">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="ac4f4-298">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="ac4f4-299">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="ac4f4-299">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           | 
    
    ![Запись TXT](../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. <span data-ttu-id="ac4f4-301">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-301">Select **Save**.</span></span><br/><span data-ttu-id="ac4f4-302">![Add record](../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-302">![Add record](../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span></span>
  
8. <span data-ttu-id="ac4f4-303">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-303">Select **Save**.</span></span><br/><span data-ttu-id="ac4f4-304">![Save record](../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-304">![Save record](../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span></span>
  
9. <span data-ttu-id="ac4f4-305">В диалоговом окне **изменение параметров DNS** нажмите **кнопку Да**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-305">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="ac4f4-306">![Выбор параметра "Да" в диалоговом окне Изменение параметров DNS](../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-306">![Selecting Yes in the Edit DNS Settings dialog box](../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="ac4f4-307">Добавьте две записи SRV, необходимые для Office 365</span><span class="sxs-lookup"><span data-stu-id="ac4f4-307">Add the two SRV records that are required for Office 365</span></span>

<span data-ttu-id="ac4f4-308">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="ac4f4-308">Follow the steps below or [watch the video (start at 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ac4f4-309">Если вы зарегистрировались с помощью 1und1.de, [выполните вход здесь](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="ac4f4-309">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="ac4f4-310">Чтобы приступить к работе, перейдите на страницу своих доменов по адресу 1&1 ИОНОС, используя [эту ссылку](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="ac4f4-310">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="ac4f4-311">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-311">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="ac4f4-312">Выберите **Управление доменами**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-312">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="ac4f4-313">На странице " **центр домена** " найдите домен, который необходимо обновить, а затем выберите элемент управления **Panel** ( **v**) для этого домена.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-313">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="ac4f4-314">В области **Параметры домена** выберите **изменить параметры DNS**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-314">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="ac4f4-315">В разделе **txt and SRV Records (записи TXT и SRV** ) выберите **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-315">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="ac4f4-316">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-316">Add the first of the two SRV records.</span></span><br/><span data-ttu-id="ac4f4-317">В поля для новой записи в области **Add Record** (Добавление записи) введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-317">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> <br/><span data-ttu-id="ac4f4-318">В раскрывающемся списке выберите значения **Type (тип** ) и **TTL (срок жизни** ).</span><span class="sxs-lookup"><span data-stu-id="ac4f4-318">(Choose the **Type** and **TTL** values from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="ac4f4-319">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-319">**Type**</span></span>|<span data-ttu-id="ac4f4-320">**Service (Служба)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-320">**Service**</span></span>|<span data-ttu-id="ac4f4-321">**Protocol (Протокол)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-321">**Protocol**</span></span>|<span data-ttu-id="ac4f4-322">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-322">**Name**</span></span>|<span data-ttu-id="ac4f4-323">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-323">**Host**</span></span>|<span data-ttu-id="ac4f4-324">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-324">**Priority**</span></span>|<span data-ttu-id="ac4f4-325">**Weight (Вес)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-325">**Weight**</span></span>|<span data-ttu-id="ac4f4-326">**Port (Порт)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-326">**Port**</span></span>|<span data-ttu-id="ac4f4-327">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="ac4f4-327">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ac4f4-328">SRV</span><span class="sxs-lookup"><span data-stu-id="ac4f4-328">SRV</span></span>  <br/> |<span data-ttu-id="ac4f4-329">sip</span><span class="sxs-lookup"><span data-stu-id="ac4f4-329">sip</span></span>  <br/> |<span data-ttu-id="ac4f4-330">tls</span><span class="sxs-lookup"><span data-stu-id="ac4f4-330">tls</span></span>  <br/> |<span data-ttu-id="ac4f4-331">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-331">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="ac4f4-332">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ac4f4-332">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="ac4f4-333">100</span><span class="sxs-lookup"><span data-stu-id="ac4f4-333">100</span></span>  <br/> |<span data-ttu-id="ac4f4-334">1,1</span><span class="sxs-lookup"><span data-stu-id="ac4f4-334">1</span></span>  <br/> |<span data-ttu-id="ac4f4-335">443</span><span class="sxs-lookup"><span data-stu-id="ac4f4-335">443</span></span>  <br/> |<span data-ttu-id="ac4f4-336">3600 (1 ч)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-336">3600 (1 h)</span></span>  <br/> |
    |<span data-ttu-id="ac4f4-337">SRV</span><span class="sxs-lookup"><span data-stu-id="ac4f4-337">SRV</span></span>  <br/> |<span data-ttu-id="ac4f4-338">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="ac4f4-338">sipfederationtls</span></span>  <br/> |<span data-ttu-id="ac4f4-339">tcp</span><span class="sxs-lookup"><span data-stu-id="ac4f4-339">tcp</span></span>  <br/> |<span data-ttu-id="ac4f4-340">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-340">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="ac4f4-341">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ac4f4-341">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="ac4f4-342">100</span><span class="sxs-lookup"><span data-stu-id="ac4f4-342">100</span></span>  <br/> |<span data-ttu-id="ac4f4-343">1,1</span><span class="sxs-lookup"><span data-stu-id="ac4f4-343">1</span></span>  <br/> |<span data-ttu-id="ac4f4-344">5061</span><span class="sxs-lookup"><span data-stu-id="ac4f4-344">5061</span></span>  <br/> |<span data-ttu-id="ac4f4-345">3600 (1 ч)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-345">3600 (1 h)</span></span>  <br/> |  
    
    ![1&amp;1 — BP — Configure – 5-1](../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. <span data-ttu-id="ac4f4-347">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-347">Select **Save**.</span></span> <br/><span data-ttu-id="ac4f4-348">![1&amp;1 — BP — Configure – 5-2](../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-348">![1&amp;1-BP-Configure-5-2](../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span></span>
  
8. <span data-ttu-id="ac4f4-349">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-349">Select **Save**.</span></span> <br/><span data-ttu-id="ac4f4-350">![1&amp;1 — BP — Configure – 5-3](../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-350">![1&amp;1-BP-Configure-5-3](../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span></span>
  
9. <span data-ttu-id="ac4f4-351">В диалоговом окне **изменение параметров DNS** нажмите **кнопку Да**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-351">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span> <br/><span data-ttu-id="ac4f4-352">![Выбор параметра "Да" в диалоговом окне Изменение параметров DNS](../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="ac4f4-352">![Selecting Yes in the Edit DNS Settings dialog box](../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
10. <span data-ttu-id="ac4f4-353">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-353">Add the other SRV record.</span></span> <br/><span data-ttu-id="ac4f4-354">В разделе **txt and SRV Records (записи TXT и SRV** ) выберите **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-354">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="ac4f4-355">В области **Добавить запись** создайте запись, используя значения из другой строки таблицы, а затем снова выберите **Добавить**, **сохранить**и **Да** , чтобы завершить запись.</span><span class="sxs-lookup"><span data-stu-id="ac4f4-355">In the **Add Record** area, create a record using the values from the other row in the table, and then again select **Add**, **Save**, and **Yes** to complete the record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="ac4f4-p120">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ac4f4-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
