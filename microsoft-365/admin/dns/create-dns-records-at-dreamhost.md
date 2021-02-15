---
title: Создание записей DNS для Майкрософт на сайте Dreamhost
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
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Dreamhost for Microsoft.
ms.openlocfilehash: 2faf7cae1fd9a0f9308e303c0588958e56b223e1
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658127"
---
# <a name="create-dns-records-at-dreamhost-for-microsoft"></a><span data-ttu-id="e9621-103">Создание записей DNS для Майкрософт на сайте Dreamhost</span><span class="sxs-lookup"><span data-stu-id="e9621-103">Create DNS records at Dreamhost for Microsoft</span></span>

 <span data-ttu-id="e9621-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="e9621-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e9621-105">Если ваш поставщик услуг размещения DNS  DreamHost, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Lync и других служб.</span><span class="sxs-lookup"><span data-stu-id="e9621-105">If DreamHost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
 
<span data-ttu-id="e9621-106">После добавления этих записей на сайте DreamHost ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e9621-106">After you add these records at DreamHost, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="e9621-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e9621-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e9621-110">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="e9621-110">Add a TXT record for verification</span></span>
<span data-ttu-id="e9621-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="e9621-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="e9621-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="e9621-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e9621-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="e9621-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="e9621-p104">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте DreamHost по [этой ссылке](https://panel.dreamhost.com/). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="e9621-p104">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="e9621-119">На странице **"Информационная** панель" выберите **"Домены"** и **"Управление доменами".**</span><span class="sxs-lookup"><span data-stu-id="e9621-119">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="e9621-121">На странице **"Управление доменами"** в **разделе** "Домен" выберите **DNS** для домена, который нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="e9621-121">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="e9621-123">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="e9621-123">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e9621-124">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="e9621-124">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="e9621-125">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="e9621-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e9621-126">**Имя**</span><span class="sxs-lookup"><span data-stu-id="e9621-126">**Name**</span></span>|<span data-ttu-id="e9621-127">**Тип**</span><span class="sxs-lookup"><span data-stu-id="e9621-127">**Type**</span></span>|<span data-ttu-id="e9621-128">**Значение**</span><span class="sxs-lookup"><span data-stu-id="e9621-128">**Value**</span></span>|<span data-ttu-id="e9621-129">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="e9621-129">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e9621-130">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="e9621-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="e9621-131">TXT</span><span class="sxs-lookup"><span data-stu-id="e9621-131">TXT</span></span>  <br/> |<span data-ttu-id="e9621-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e9621-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="e9621-133">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="e9621-133">**Note:** This is an example.</span></span> <span data-ttu-id="e9621-134">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="e9621-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="e9621-135">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="e9621-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="e9621-136">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="e9621-136">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost-BP-Verify-1-1](../../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. <span data-ttu-id="e9621-138">Выберите **"Добавить запись" сейчас!**</span><span class="sxs-lookup"><span data-stu-id="e9621-138">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Verify-1-2](../../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. <span data-ttu-id="e9621-140">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="e9621-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e9621-141">Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.</span><span class="sxs-lookup"><span data-stu-id="e9621-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="e9621-142">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="e9621-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e9621-143">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="e9621-143">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="e9621-144">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="e9621-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="e9621-145">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="e9621-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="e9621-146">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="e9621-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="e9621-p106">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e9621-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="e9621-150">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e9621-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="e9621-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="e9621-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="e9621-152">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e9621-152">Follow the steps below.</span></span>
  
1. <span data-ttu-id="e9621-p107">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте DreamHost по [этой ссылке](https://panel.dreamhost.com/). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="e9621-p107">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="e9621-156">На странице **"Информационная** панель" выберите **"Почта",** а затем **"Настраиваемая MX".**</span><span class="sxs-lookup"><span data-stu-id="e9621-156">On the **Dashboard** page, select **Mail**, and then **Custom MX**.</span></span>
    
    ![Dreamhost-BP-Configure-2-1](../../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. <span data-ttu-id="e9621-158">В разделе **"Управление доставкой** почты"  в **столбце** "Действия" выберите "Изменить" для домена, который нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="e9621-158">In the **Manage Mail Delivery** section, in the **Actions** column, select **Edit** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-2-2](../../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. <span data-ttu-id="e9621-160">В поля для новой записи в области **Custom MX Record** (Настраиваемая запись MX) введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="e9621-160">In the **Custom MX Record** section, in the boxes for the new record, type or copy and paste the following values from the following table.</span></span> 
    
    <span data-ttu-id="e9621-161">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="e9621-161">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="e9621-162">(Если существуют другие записи MX, пометьте их для удаления.)</span><span class="sxs-lookup"><span data-stu-id="e9621-162">(If there are any other existing MX records, mark those records to be deleted.)</span></span>
    
    |<span data-ttu-id="e9621-163">**Запись MX (обязательно)**</span><span class="sxs-lookup"><span data-stu-id="e9621-163">**MX Record (required)**</span></span>|
    |:-----|
    |<span data-ttu-id="e9621-164">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="e9621-164">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="e9621-165">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="e9621-165">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="e9621-p108">0  значение приоритета MX. Добавьте его в начало значения MX, отделив от остальной части пробелом.  </span><span class="sxs-lookup"><span data-stu-id="e9621-p108">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="e9621-168">**Примечание.** Получите свою  *\<domain-key\>*  учетную запись Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e9621-168">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="e9621-169">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="e9621-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Dreamhost-BP-Configure-2-3](../../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. <span data-ttu-id="e9621-171">Выберите **"Изменить этот домен для использования пользовательских записей MX"!**</span><span class="sxs-lookup"><span data-stu-id="e9621-171">Select **Change this domain to use custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-4](../../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. <span data-ttu-id="e9621-173">Если есть какие-либо другие записи MX, удалите каждую из них, выделив ее и нажав на клавиатуре клавишу **DELETE**.</span><span class="sxs-lookup"><span data-stu-id="e9621-173">If there are any other existing MX records, delete each record by selecting the entry and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Dreamhost-BP-Configure-2-5](../../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. <span data-ttu-id="e9621-175">Если вы удалили какие-либо записи, выберите "Обновить пользовательские **записи MX"!**</span><span class="sxs-lookup"><span data-stu-id="e9621-175">If you have deleted any records, select **Update your custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-6](../../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="e9621-177">Добавьте шесть записей CNAME, необходимых для Корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e9621-177">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="e9621-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="e9621-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="e9621-179">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e9621-179">Follow the steps below.</span></span>
  
1. <span data-ttu-id="e9621-p110">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте DreamHost по [этой ссылке](https://panel.dreamhost.com/). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="e9621-p110">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="e9621-183">На странице **"Информационная** панель" выберите **"Домены"** и **"Управление доменами".**</span><span class="sxs-lookup"><span data-stu-id="e9621-183">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="e9621-185">На странице **"Управление доменами"** в разделе **"Домен"** выберите **DNS** для домена, который нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="e9621-185">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="e9621-187">В поля для новой записи в области **Add a custom DNS record** (Добавление настраиваемой записи DNS) введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="e9621-187">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="e9621-188">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="e9621-188">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="e9621-189">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="e9621-189">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e9621-190">**Имя**</span><span class="sxs-lookup"><span data-stu-id="e9621-190">**Name**</span></span>|<span data-ttu-id="e9621-191">**Тип**</span><span class="sxs-lookup"><span data-stu-id="e9621-191">**Type**</span></span>|<span data-ttu-id="e9621-192">**Значение**</span><span class="sxs-lookup"><span data-stu-id="e9621-192">**Value**</span></span>|<span data-ttu-id="e9621-193">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="e9621-193">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e9621-194">autodiscover</span><span class="sxs-lookup"><span data-stu-id="e9621-194">autodiscover</span></span>  <br/> |<span data-ttu-id="e9621-195">CNAME</span><span class="sxs-lookup"><span data-stu-id="e9621-195">CNAME</span></span>  <br/> |<span data-ttu-id="e9621-196">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="e9621-196">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="e9621-197">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="e9621-197">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e9621-198">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="e9621-198">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="e9621-199">sip</span><span class="sxs-lookup"><span data-stu-id="e9621-199">sip</span></span>  <br/> |<span data-ttu-id="e9621-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="e9621-200">CNAME</span></span>  <br/> |<span data-ttu-id="e9621-201">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e9621-201">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="e9621-202">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="e9621-202">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e9621-203">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="e9621-203">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="e9621-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e9621-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e9621-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="e9621-205">CNAME</span></span>  <br/> |<span data-ttu-id="e9621-206">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e9621-206">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="e9621-207">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="e9621-207">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e9621-208">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="e9621-208">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="e9621-209">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e9621-209">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e9621-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="e9621-210">CNAME</span></span>  <br/> |<span data-ttu-id="e9621-211">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="e9621-211">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="e9621-212">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="e9621-212">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e9621-213">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="e9621-213">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="e9621-214">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e9621-214">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e9621-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="e9621-215">CNAME</span></span>  <br/> |<span data-ttu-id="e9621-216">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e9621-216">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="e9621-217">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="e9621-217">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e9621-218">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="e9621-218">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost-BP-Configure-3-1](../../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. <span data-ttu-id="e9621-220">Выберите **"Добавить запись" сейчас!**</span><span class="sxs-lookup"><span data-stu-id="e9621-220">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-3-2](../../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. <span data-ttu-id="e9621-222">Используя два предыдущих шага и значения из остальных пяти строк таблицы, добавьте каждую из остальных пяти записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="e9621-222">Using the preceding two steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e9621-223">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="e9621-223">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="e9621-224"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="e9621-224"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9621-225">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="e9621-225">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e9621-226">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="e9621-226">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e9621-227">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e9621-227">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="e9621-228">Вместо этого добавьте необходимые значения Майкрософт в текущую  запись, чтобы иметь одну запись SPF, которая включает оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="e9621-228">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="e9621-229">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e9621-229">Follow the steps below.</span></span>
  
1. <span data-ttu-id="e9621-p112">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте DreamHost по [этой ссылке](https://panel.dreamhost.com/). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="e9621-p112">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="e9621-233">На странице **"Информационная** панель" выберите **"Домены"** и **"Управление доменами".**</span><span class="sxs-lookup"><span data-stu-id="e9621-233">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="e9621-235">На странице **"Управление доменами"** в **разделе** "Домен" выберите **DNS** для домена, который нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="e9621-235">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="e9621-237">В поля для новой записи в области **Add a custom DNS record** (Добавление настраиваемой записи DNS) введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="e9621-237">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="e9621-238">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="e9621-238">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="e9621-239">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="e9621-239">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e9621-240">**Имя**</span><span class="sxs-lookup"><span data-stu-id="e9621-240">**Name**</span></span>|<span data-ttu-id="e9621-241">**Тип**</span><span class="sxs-lookup"><span data-stu-id="e9621-241">**Type**</span></span>|<span data-ttu-id="e9621-242">**Значение**</span><span class="sxs-lookup"><span data-stu-id="e9621-242">**Value**</span></span>|<span data-ttu-id="e9621-243">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="e9621-243">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e9621-244">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="e9621-244">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="e9621-245">TXT</span><span class="sxs-lookup"><span data-stu-id="e9621-245">TXT</span></span>  <br/> |<span data-ttu-id="e9621-246">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e9621-246">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="e9621-247">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="e9621-247">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="e9621-248">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="e9621-248">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost-BP-Configure-4-1](../../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. <span data-ttu-id="e9621-250">Выберите **"Добавить запись" сейчас!**</span><span class="sxs-lookup"><span data-stu-id="e9621-250">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-4-2](../../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. <span data-ttu-id="e9621-252">Повторите два описанных выше шага, используя значения из второй строки таблицы, чтобы добавить еще одну запись SRV.</span><span class="sxs-lookup"><span data-stu-id="e9621-252">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="e9621-253">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e9621-253">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="e9621-254"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="e9621-254"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="e9621-255">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e9621-255">Follow the steps below.</span></span>
  
1. <span data-ttu-id="e9621-p113">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте DreamHost по [этой ссылке](https://panel.dreamhost.com/). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="e9621-p113">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="e9621-259">На странице **"Информационная** панель" выберите **"Домены"** и **"Управление доменами".**</span><span class="sxs-lookup"><span data-stu-id="e9621-259">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="e9621-261">На странице **"Управление доменами"** в **разделе** "Домен" выберите **DNS** для домена, который нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="e9621-261">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="e9621-263">В поля для новой записи в области **Add a custom DNS record** (Добавление настраиваемой записи DNS) введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="e9621-263">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="e9621-264">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="e9621-264">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="e9621-265">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="e9621-265">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e9621-266">**Имя**</span><span class="sxs-lookup"><span data-stu-id="e9621-266">**Name**</span></span>|<span data-ttu-id="e9621-267">**Тип**</span><span class="sxs-lookup"><span data-stu-id="e9621-267">**Type**</span></span>|<span data-ttu-id="e9621-268">**Значение**</span><span class="sxs-lookup"><span data-stu-id="e9621-268">**Value**</span></span>|<span data-ttu-id="e9621-269">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="e9621-269">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e9621-270">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="e9621-270">_sip._tls</span></span>  <br/> |<span data-ttu-id="e9621-271">SRV</span><span class="sxs-lookup"><span data-stu-id="e9621-271">SRV</span></span>  <br/> |<span data-ttu-id="e9621-272">100 1 443</span><span class="sxs-lookup"><span data-stu-id="e9621-272">100 1 443</span></span>  <br/> <span data-ttu-id="e9621-273">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e9621-273">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="e9621-274">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="e9621-274">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e9621-275">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="e9621-275">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="e9621-276">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="e9621-276">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="e9621-277">SRV</span><span class="sxs-lookup"><span data-stu-id="e9621-277">SRV</span></span>  <br/> |<span data-ttu-id="e9621-278">100 1 5061</span><span class="sxs-lookup"><span data-stu-id="e9621-278">100 1 5061</span></span>  <br/> <span data-ttu-id="e9621-279">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e9621-279">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="e9621-280">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="e9621-280">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e9621-281">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="e9621-281">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost-BP-Configure-5-1](../../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. <span data-ttu-id="e9621-283">Выберите **"Добавить запись"!**.</span><span class="sxs-lookup"><span data-stu-id="e9621-283">Select **Add Record Now!**.</span></span>
    
    ![Dreamhost-BP-Configure-5-2](../../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. <span data-ttu-id="e9621-285">Повторите два описанных выше шага, используя значения из второй строки таблицы, чтобы добавить еще одну запись SRV.</span><span class="sxs-lookup"><span data-stu-id="e9621-285">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="e9621-p114">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e9621-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
