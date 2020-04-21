---
title: Создание записей DNS на сайте Dreamhost для Майкрософт
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
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу Dreamhost для Майкрософт.
ms.openlocfilehash: 2187cc155bc15e8482960d933d9136401ea29beb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629807"
---
# <a name="create-dns-records-at-dreamhost-for-microsoft"></a><span data-ttu-id="184cd-103">Создание записей DNS на сайте Dreamhost для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="184cd-103">Create DNS records at Dreamhost for Microsoft</span></span>

 <span data-ttu-id="184cd-104">Если вы не нашли то, что вы ищете, обратитесь к разделу **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="184cd-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="184cd-105">Если ваш поставщик услуг размещения DNS  DreamHost, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Lync и других служб.</span><span class="sxs-lookup"><span data-stu-id="184cd-105">If DreamHost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
 
<span data-ttu-id="184cd-106">Когда вы добавите эти записи на сайте DreamHost, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="184cd-106">After you add these records at DreamHost, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="184cd-107">Чтобы узнать о размещении и DNS для веб-сайтов с помощью Microsoft, ознакомьтесь со статьей [использование общедоступного веб-сайта с корпорацией Майкрософт](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="184cd-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="184cd-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="184cd-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="184cd-111">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="184cd-111">Add a TXT record for verification</span></span>
<span data-ttu-id="184cd-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="184cd-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="184cd-113">Перед использованием домена с корпорацией Майкрософт необходимо убедиться, что вы являетесь его владельцем.</span><span class="sxs-lookup"><span data-stu-id="184cd-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="184cd-114">Вы можете войти в свою учетную запись у вас в вашем регистраторе доменных имен и создать запись DNS в Майкрософт, если вы владеете этим доменом.</span><span class="sxs-lookup"><span data-stu-id="184cd-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="184cd-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="184cd-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="184cd-p104">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте DreamHost по [этой ссылке](https://panel.dreamhost.com/). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="184cd-p104">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="184cd-120">На странице **панели мониторинга** выберите **домены**, а затем **Управление доменами**.</span><span class="sxs-lookup"><span data-stu-id="184cd-120">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="184cd-122">На странице " **Управление доменами** " в разделе **домен** выберите **DNS** для домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="184cd-122">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="184cd-124">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="184cd-124">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="184cd-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="184cd-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="184cd-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="184cd-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="184cd-127">**Имя**</span><span class="sxs-lookup"><span data-stu-id="184cd-127">**Name**</span></span>|<span data-ttu-id="184cd-128">**Тип**</span><span class="sxs-lookup"><span data-stu-id="184cd-128">**Type**</span></span>|<span data-ttu-id="184cd-129">**Значение**</span><span class="sxs-lookup"><span data-stu-id="184cd-129">**Value**</span></span>|<span data-ttu-id="184cd-130">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="184cd-130">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="184cd-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="184cd-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="184cd-132">TXT</span><span class="sxs-lookup"><span data-stu-id="184cd-132">TXT</span></span>  <br/> |<span data-ttu-id="184cd-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="184cd-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="184cd-134">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="184cd-134">**Note:** This is an example.</span></span> <span data-ttu-id="184cd-135">Используйте указанную здесь **конечную точку или значение адреса** из таблицы.</span><span class="sxs-lookup"><span data-stu-id="184cd-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="184cd-136">Как найти это значение?</span><span class="sxs-lookup"><span data-stu-id="184cd-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="184cd-137">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="184cd-137">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost — BP — Verify – 1-1](../../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. <span data-ttu-id="184cd-139">Нажмите кнопку **Добавить запись.**</span><span class="sxs-lookup"><span data-stu-id="184cd-139">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Verify-1-2](../../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. <span data-ttu-id="184cd-141">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="184cd-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="184cd-142">Теперь, когда вы добавили запись на сайте регистратора доменных имен, вернитесь в корпорацию Майкрософт и запросите запись.</span><span class="sxs-lookup"><span data-stu-id="184cd-142">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="184cd-143">После того как корпорация Майкрософт обнаружит правильную запись TXT, ваш домен будет проверен.</span><span class="sxs-lookup"><span data-stu-id="184cd-143">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="184cd-144">В центре администрирования Майкрософт перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> **параметров** \> ".</span><span class="sxs-lookup"><span data-stu-id="184cd-144">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="184cd-145">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="184cd-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="184cd-146">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="184cd-146">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="184cd-147">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="184cd-147">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="184cd-p106">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="184cd-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="184cd-151">Добавление записи MX для отправки электронной почты для вашего домена в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="184cd-151">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="184cd-152"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="184cd-152"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="184cd-153">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="184cd-153">Follow the steps below.</span></span>
  
1. <span data-ttu-id="184cd-p107">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте DreamHost по [этой ссылке](https://panel.dreamhost.com/). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="184cd-p107">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="184cd-157">На странице **панель мониторинга** выберите пункт **почта**, а затем — **Пользовательская MX**.</span><span class="sxs-lookup"><span data-stu-id="184cd-157">On the **Dashboard** page, select **Mail**, and then **Custom MX**.</span></span>
    
    ![Dreamhost-BP-Configure-2-1](../../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. <span data-ttu-id="184cd-159">В разделе **Управление доставкой почты** в столбце **действия** выберите команду **изменить** для домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="184cd-159">In the **Manage Mail Delivery** section, in the **Actions** column, select **Edit** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-2-2](../../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. <span data-ttu-id="184cd-161">В поля для новой записи в области **Custom MX Record** (Настраиваемая запись MX) введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="184cd-161">In the **Custom MX Record** section, in the boxes for the new record, type or copy and paste the following values from the following table.</span></span> 
    
    <span data-ttu-id="184cd-162">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="184cd-162">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="184cd-163">(Если существуют другие записи MX, пометьте их для удаления.)</span><span class="sxs-lookup"><span data-stu-id="184cd-163">(If there are any other existing MX records, mark those records to be deleted.)</span></span>
    
    |<span data-ttu-id="184cd-164">**Запись MX (обязательно)**</span><span class="sxs-lookup"><span data-stu-id="184cd-164">**MX Record (required)**</span></span>|
    |:-----|
    |<span data-ttu-id="184cd-165">0  *\<ключ_домена\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="184cd-165">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="184cd-166">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="184cd-166">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="184cd-p108">0  значение приоритета MX. Добавьте его в начало значения MX, отделив от остальной части пробелом.  </span><span class="sxs-lookup"><span data-stu-id="184cd-p108">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="184cd-169">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="184cd-169">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="184cd-170">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="184cd-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Dreamhost — BP — configure – 2-3](../../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. <span data-ttu-id="184cd-172">Выберите **изменить этот домен для использования настраиваемых записей MX сейчас!**</span><span class="sxs-lookup"><span data-stu-id="184cd-172">Select **Change this domain to use custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-4](../../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. <span data-ttu-id="184cd-174">Если есть какие-либо другие записи MX, удалите каждую из них, выделив ее и нажав на клавиатуре клавишу **DELETE**.</span><span class="sxs-lookup"><span data-stu-id="184cd-174">If there are any other existing MX records, delete each record by selecting the entry and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Dreamhost-BP-Configure-2-5](../../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. <span data-ttu-id="184cd-176">Если вы удалили какие-либо записи, установите флажок **обновить пользовательские записи MX теперь.**</span><span class="sxs-lookup"><span data-stu-id="184cd-176">If you have deleted any records, select **Update your custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-6](../../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="184cd-178">Добавление шести записей CNAME, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="184cd-178">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="184cd-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="184cd-179"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="184cd-180">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="184cd-180">Follow the steps below.</span></span>
  
1. <span data-ttu-id="184cd-p110">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте DreamHost по [этой ссылке](https://panel.dreamhost.com/). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="184cd-p110">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="184cd-184">На странице **панели мониторинга** выберите **домены**, а затем **Управление доменами**.</span><span class="sxs-lookup"><span data-stu-id="184cd-184">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="184cd-186">На странице " **Управление доменами** " в разделе **домен** выберите **DNS** для домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="184cd-186">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="184cd-188">В поля для новой записи в области **Add a custom DNS record** (Добавление настраиваемой записи DNS) введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="184cd-188">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="184cd-189">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="184cd-189">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="184cd-190">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="184cd-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="184cd-191">**Имя**</span><span class="sxs-lookup"><span data-stu-id="184cd-191">**Name**</span></span>|<span data-ttu-id="184cd-192">**Тип**</span><span class="sxs-lookup"><span data-stu-id="184cd-192">**Type**</span></span>|<span data-ttu-id="184cd-193">**Значение**</span><span class="sxs-lookup"><span data-stu-id="184cd-193">**Value**</span></span>|<span data-ttu-id="184cd-194">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="184cd-194">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="184cd-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="184cd-195">autodiscover</span></span>  <br/> |<span data-ttu-id="184cd-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="184cd-196">CNAME</span></span>  <br/> |<span data-ttu-id="184cd-197">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="184cd-197">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="184cd-198">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="184cd-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="184cd-199">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="184cd-199">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="184cd-200">sip</span><span class="sxs-lookup"><span data-stu-id="184cd-200">sip</span></span>  <br/> |<span data-ttu-id="184cd-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="184cd-201">CNAME</span></span>  <br/> |<span data-ttu-id="184cd-202">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="184cd-202">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="184cd-203">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="184cd-203">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="184cd-204">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="184cd-204">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="184cd-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="184cd-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="184cd-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="184cd-206">CNAME</span></span>  <br/> |<span data-ttu-id="184cd-207">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="184cd-207">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="184cd-208">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="184cd-208">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="184cd-209">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="184cd-209">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="184cd-210">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="184cd-210">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="184cd-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="184cd-211">CNAME</span></span>  <br/> |<span data-ttu-id="184cd-212">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="184cd-212">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="184cd-213">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="184cd-213">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="184cd-214">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="184cd-214">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="184cd-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="184cd-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="184cd-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="184cd-216">CNAME</span></span>  <br/> |<span data-ttu-id="184cd-217">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="184cd-217">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="184cd-218">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="184cd-218">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="184cd-219">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="184cd-219">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost — BP — configure – 3-1](../../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. <span data-ttu-id="184cd-221">Нажмите кнопку **Добавить запись.**</span><span class="sxs-lookup"><span data-stu-id="184cd-221">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-3-2](../../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. <span data-ttu-id="184cd-223">Используя предыдущие два действия и значения из других пяти строк в таблице, добавьте все остальные пять записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="184cd-223">Using the preceding two steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="184cd-224">Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама</span><span class="sxs-lookup"><span data-stu-id="184cd-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="184cd-225"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="184cd-225"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="184cd-226">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="184cd-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="184cd-227">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="184cd-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="184cd-228">Если у вас уже есть запись SPF для вашего домена, не создавайте ее для Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="184cd-228">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="184cd-229">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="184cd-229">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="184cd-230">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="184cd-230">Follow the steps below.</span></span>
  
1. <span data-ttu-id="184cd-p112">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте DreamHost по [этой ссылке](https://panel.dreamhost.com/). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="184cd-p112">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="184cd-234">На странице **панели мониторинга** выберите **домены**, а затем **Управление доменами**.</span><span class="sxs-lookup"><span data-stu-id="184cd-234">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="184cd-236">На странице " **Управление доменами** " в разделе **домен** выберите **DNS** для домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="184cd-236">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="184cd-238">В поля для новой записи в области **Add a custom DNS record** (Добавление настраиваемой записи DNS) введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="184cd-238">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="184cd-239">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="184cd-239">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="184cd-240">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="184cd-240">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="184cd-241">**Имя**</span><span class="sxs-lookup"><span data-stu-id="184cd-241">**Name**</span></span>|<span data-ttu-id="184cd-242">**Тип**</span><span class="sxs-lookup"><span data-stu-id="184cd-242">**Type**</span></span>|<span data-ttu-id="184cd-243">**Значение**</span><span class="sxs-lookup"><span data-stu-id="184cd-243">**Value**</span></span>|<span data-ttu-id="184cd-244">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="184cd-244">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="184cd-245">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="184cd-245">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="184cd-246">TXT</span><span class="sxs-lookup"><span data-stu-id="184cd-246">TXT</span></span>  <br/> |<span data-ttu-id="184cd-247">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="184cd-247">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="184cd-248">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="184cd-248">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="184cd-249">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="184cd-249">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost — BP — configure – 4-1](../../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. <span data-ttu-id="184cd-251">Нажмите кнопку **Добавить запись.**</span><span class="sxs-lookup"><span data-stu-id="184cd-251">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-4-2](../../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. <span data-ttu-id="184cd-253">Повторите два описанных выше шага, используя значения из второй строки таблицы, чтобы добавить еще одну запись SRV.</span><span class="sxs-lookup"><span data-stu-id="184cd-253">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="184cd-254">Добавление двух записей SRV, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="184cd-254">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="184cd-255"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="184cd-255"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="184cd-256">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="184cd-256">Follow the steps below.</span></span>
  
1. <span data-ttu-id="184cd-p113">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте DreamHost по [этой ссылке](https://panel.dreamhost.com/). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="184cd-p113">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="184cd-260">На странице **панели мониторинга** выберите **домены**, а затем **Управление доменами**.</span><span class="sxs-lookup"><span data-stu-id="184cd-260">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="184cd-262">На странице " **Управление доменами** " в разделе **домен** выберите **DNS** для домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="184cd-262">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="184cd-264">В поля для новой записи в области **Add a custom DNS record** (Добавление настраиваемой записи DNS) введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="184cd-264">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="184cd-265">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="184cd-265">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="184cd-266">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="184cd-266">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="184cd-267">**Имя**</span><span class="sxs-lookup"><span data-stu-id="184cd-267">**Name**</span></span>|<span data-ttu-id="184cd-268">**Тип**</span><span class="sxs-lookup"><span data-stu-id="184cd-268">**Type**</span></span>|<span data-ttu-id="184cd-269">**Значение**</span><span class="sxs-lookup"><span data-stu-id="184cd-269">**Value**</span></span>|<span data-ttu-id="184cd-270">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="184cd-270">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="184cd-271">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="184cd-271">_sip._tls</span></span>  <br/> |<span data-ttu-id="184cd-272">SRV</span><span class="sxs-lookup"><span data-stu-id="184cd-272">SRV</span></span>  <br/> |<span data-ttu-id="184cd-273">100 1 443</span><span class="sxs-lookup"><span data-stu-id="184cd-273">100 1 443</span></span>  <br/> <span data-ttu-id="184cd-274">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="184cd-274">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="184cd-275">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="184cd-275">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="184cd-276">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="184cd-276">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="184cd-277">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="184cd-277">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="184cd-278">SRV</span><span class="sxs-lookup"><span data-stu-id="184cd-278">SRV</span></span>  <br/> |<span data-ttu-id="184cd-279">100 1 5061</span><span class="sxs-lookup"><span data-stu-id="184cd-279">100 1 5061</span></span>  <br/> <span data-ttu-id="184cd-280">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="184cd-280">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="184cd-281">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="184cd-281">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="184cd-282">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="184cd-282">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost — BP — configure – 5-1](../../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. <span data-ttu-id="184cd-284">Нажмите **Добавить запись сейчас!**.</span><span class="sxs-lookup"><span data-stu-id="184cd-284">Select **Add Record Now!**.</span></span>
    
    ![Dreamhost-BP-Configure-5-2](../../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. <span data-ttu-id="184cd-286">Повторите два описанных выше шага, используя значения из второй строки таблицы, чтобы добавить еще одну запись SRV.</span><span class="sxs-lookup"><span data-stu-id="184cd-286">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="184cd-p114">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="184cd-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
