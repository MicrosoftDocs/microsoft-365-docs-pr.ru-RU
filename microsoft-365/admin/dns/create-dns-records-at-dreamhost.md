---
title: Создание записей DNS для Office 365 на сайте Dreamhost
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
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу Dreamhost для Office 365.
ms.openlocfilehash: 201452bc68f82138c08e2054452747a900ed0e6b
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2020
ms.locfileid: "42349490"
---
# <a name="create-dns-records-at-dreamhost-for-office-365"></a><span data-ttu-id="62ba2-103">Создание записей DNS для Office 365 на сайте Dreamhost</span><span class="sxs-lookup"><span data-stu-id="62ba2-103">Create DNS records at Dreamhost for Office 365</span></span>

 <span data-ttu-id="62ba2-104">Если вы не нашли то, что вы ищете, обратитесь к разделу **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="62ba2-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="62ba2-105">Если ваш поставщик услуг размещения DNS  DreamHost, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Lync и других служб.</span><span class="sxs-lookup"><span data-stu-id="62ba2-105">If DreamHost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
 
<span data-ttu-id="62ba2-106">Когда вы добавите эти записи на сайте DreamHost, ваш домен будет настроен для работы со службами Office 365.</span><span class="sxs-lookup"><span data-stu-id="62ba2-106">After you add these records at DreamHost, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="62ba2-107">Дополнительные сведения о веб-хостинге и DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="62ba2-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="62ba2-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="62ba2-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="62ba2-111">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="62ba2-111">Add a TXT record for verification</span></span>
<span data-ttu-id="62ba2-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="62ba2-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="62ba2-p102">Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="62ba2-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="62ba2-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="62ba2-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="62ba2-p104">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте DreamHost по [этой ссылке](https://panel.dreamhost.com/). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="62ba2-p104">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="62ba2-120">На странице **панели мониторинга** выберите **домены**, а затем **Управление доменами**.</span><span class="sxs-lookup"><span data-stu-id="62ba2-120">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="62ba2-122">На странице " **Управление доменами** " в разделе **домен** выберите **DNS** для домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="62ba2-122">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="62ba2-124">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="62ba2-124">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="62ba2-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="62ba2-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="62ba2-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="62ba2-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="62ba2-127">**Имя**</span><span class="sxs-lookup"><span data-stu-id="62ba2-127">**Name**</span></span>|<span data-ttu-id="62ba2-128">**Тип**</span><span class="sxs-lookup"><span data-stu-id="62ba2-128">**Type**</span></span>|<span data-ttu-id="62ba2-129">**Значение**</span><span class="sxs-lookup"><span data-stu-id="62ba2-129">**Value**</span></span>|<span data-ttu-id="62ba2-130">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="62ba2-130">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="62ba2-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="62ba2-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="62ba2-132">TXT</span><span class="sxs-lookup"><span data-stu-id="62ba2-132">TXT</span></span>  <br/> |<span data-ttu-id="62ba2-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="62ba2-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="62ba2-p105">**Примечание.** Это пример. Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.           [Где это находится?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="62ba2-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="62ba2-137">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="62ba2-137">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost — BP — Verify – 1-1](../../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. <span data-ttu-id="62ba2-139">Нажмите кнопку **Добавить запись.**</span><span class="sxs-lookup"><span data-stu-id="62ba2-139">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Verify-1-2](../../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. <span data-ttu-id="62ba2-141">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="62ba2-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="62ba2-142">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Office 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="62ba2-142">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="62ba2-143">Если Office 365 обнаружит правильную запись TXT, это значит, что домен проверен.</span><span class="sxs-lookup"><span data-stu-id="62ba2-143">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="62ba2-144">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="62ba2-144">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="62ba2-145">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="62ba2-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="62ba2-146">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="62ba2-146">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="62ba2-147">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="62ba2-147">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="62ba2-p106">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="62ba2-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="62ba2-151">Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="62ba2-151">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="62ba2-152"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="62ba2-152"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="62ba2-153">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="62ba2-153">Follow the steps below.</span></span>
  
1. <span data-ttu-id="62ba2-p107">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте DreamHost по [этой ссылке](https://panel.dreamhost.com/). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="62ba2-p107">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="62ba2-157">На странице **панель мониторинга** выберите пункт **почта**, а затем — **Пользовательская MX**.</span><span class="sxs-lookup"><span data-stu-id="62ba2-157">On the **Dashboard** page, select **Mail**, and then **Custom MX**.</span></span>
    
    ![Dreamhost-BP-Configure-2-1](../../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. <span data-ttu-id="62ba2-159">В разделе **Управление доставкой почты** в столбце **действия** выберите команду **изменить** для домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="62ba2-159">In the **Manage Mail Delivery** section, in the **Actions** column, select **Edit** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-2-2](../../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. <span data-ttu-id="62ba2-161">В поля для новой записи в области **Custom MX Record** (Настраиваемая запись MX) введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="62ba2-161">In the **Custom MX Record** section, in the boxes for the new record, type or copy and paste the following values from the following table.</span></span> 
    
    <span data-ttu-id="62ba2-162">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="62ba2-162">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="62ba2-163">(Если существуют другие записи MX, пометьте их для удаления.)</span><span class="sxs-lookup"><span data-stu-id="62ba2-163">(If there are any other existing MX records, mark those records to be deleted.)</span></span>
    
    |<span data-ttu-id="62ba2-164">**Запись MX (обязательно)**</span><span class="sxs-lookup"><span data-stu-id="62ba2-164">**MX Record (required)**</span></span>|
    |:-----|
    |<span data-ttu-id="62ba2-165">0  *\<ключ_домена\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="62ba2-165">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="62ba2-166">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="62ba2-166">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="62ba2-p108">0  значение приоритета MX. Добавьте его в начало значения MX, отделив от остальной части пробелом.  </span><span class="sxs-lookup"><span data-stu-id="62ba2-p108">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="62ba2-169">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Office 365.</span><span class="sxs-lookup"><span data-stu-id="62ba2-169">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="62ba2-170">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="62ba2-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Dreamhost — BP — configure – 2-3](../../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. <span data-ttu-id="62ba2-172">Выберите **изменить этот домен для использования настраиваемых записей MX сейчас!**</span><span class="sxs-lookup"><span data-stu-id="62ba2-172">Select **Change this domain to use custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-4](../../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. <span data-ttu-id="62ba2-174">Если есть какие-либо другие записи MX, удалите каждую из них, выделив ее и нажав на клавиатуре клавишу **DELETE**.</span><span class="sxs-lookup"><span data-stu-id="62ba2-174">If there are any other existing MX records, delete each record by selecting the entry and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Dreamhost-BP-Configure-2-5](../../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. <span data-ttu-id="62ba2-176">Если вы удалили какие-либо записи, установите флажок **обновить пользовательские записи MX теперь.**</span><span class="sxs-lookup"><span data-stu-id="62ba2-176">If you have deleted any records, select **Update your custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-6](../../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="62ba2-178">Добавление шести записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="62ba2-178">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="62ba2-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="62ba2-179"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="62ba2-180">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="62ba2-180">Follow the steps below.</span></span>
  
1. <span data-ttu-id="62ba2-p110">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте DreamHost по [этой ссылке](https://panel.dreamhost.com/). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="62ba2-p110">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="62ba2-184">На странице **панели мониторинга** выберите **домены**, а затем **Управление доменами**.</span><span class="sxs-lookup"><span data-stu-id="62ba2-184">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="62ba2-186">На странице " **Управление доменами** " в разделе **домен** выберите **DNS** для домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="62ba2-186">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="62ba2-188">В поля для новой записи в области **Add a custom DNS record** (Добавление настраиваемой записи DNS) введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="62ba2-188">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="62ba2-189">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="62ba2-189">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="62ba2-190">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="62ba2-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="62ba2-191">**Имя**</span><span class="sxs-lookup"><span data-stu-id="62ba2-191">**Name**</span></span>|<span data-ttu-id="62ba2-192">**Тип**</span><span class="sxs-lookup"><span data-stu-id="62ba2-192">**Type**</span></span>|<span data-ttu-id="62ba2-193">**Значение**</span><span class="sxs-lookup"><span data-stu-id="62ba2-193">**Value**</span></span>|<span data-ttu-id="62ba2-194">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="62ba2-194">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="62ba2-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="62ba2-195">autodiscover</span></span>  <br/> |<span data-ttu-id="62ba2-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="62ba2-196">CNAME</span></span>  <br/> |<span data-ttu-id="62ba2-197">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="62ba2-197">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="62ba2-198">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="62ba2-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="62ba2-199">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="62ba2-199">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="62ba2-200">sip</span><span class="sxs-lookup"><span data-stu-id="62ba2-200">sip</span></span>  <br/> |<span data-ttu-id="62ba2-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="62ba2-201">CNAME</span></span>  <br/> |<span data-ttu-id="62ba2-202">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="62ba2-202">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="62ba2-203">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="62ba2-203">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="62ba2-204">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="62ba2-204">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="62ba2-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="62ba2-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="62ba2-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="62ba2-206">CNAME</span></span>  <br/> |<span data-ttu-id="62ba2-207">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="62ba2-207">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="62ba2-208">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="62ba2-208">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="62ba2-209">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="62ba2-209">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="62ba2-210">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="62ba2-210">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="62ba2-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="62ba2-211">CNAME</span></span>  <br/> |<span data-ttu-id="62ba2-212">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="62ba2-212">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="62ba2-213">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="62ba2-213">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="62ba2-214">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="62ba2-214">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="62ba2-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="62ba2-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="62ba2-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="62ba2-216">CNAME</span></span>  <br/> |<span data-ttu-id="62ba2-217">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="62ba2-217">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="62ba2-218">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="62ba2-218">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="62ba2-219">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="62ba2-219">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost — BP — configure – 3-1](../../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. <span data-ttu-id="62ba2-221">Нажмите кнопку **Добавить запись.**</span><span class="sxs-lookup"><span data-stu-id="62ba2-221">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-3-2](../../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. <span data-ttu-id="62ba2-223">Используя предыдущие два действия и значения из других пяти строк в таблице, добавьте все остальные пять записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="62ba2-223">Using the preceding two steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="62ba2-224">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="62ba2-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="62ba2-225"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="62ba2-225"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="62ba2-226">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="62ba2-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="62ba2-227">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="62ba2-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="62ba2-228">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="62ba2-228">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="62ba2-229">Вместо этого добавьте необходимые значения Office 365 в текущую запись. Таким образом, в *одной* записи SPF будут указаны оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="62ba2-229">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="62ba2-230">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="62ba2-230">Follow the steps below.</span></span>
  
1. <span data-ttu-id="62ba2-p112">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте DreamHost по [этой ссылке](https://panel.dreamhost.com/). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="62ba2-p112">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="62ba2-234">На странице **панели мониторинга** выберите **домены**, а затем **Управление доменами**.</span><span class="sxs-lookup"><span data-stu-id="62ba2-234">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="62ba2-236">На странице " **Управление доменами** " в разделе **домен** выберите **DNS** для домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="62ba2-236">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="62ba2-238">В поля для новой записи в области **Add a custom DNS record** (Добавление настраиваемой записи DNS) введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="62ba2-238">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="62ba2-239">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="62ba2-239">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="62ba2-240">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="62ba2-240">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="62ba2-241">**Имя**</span><span class="sxs-lookup"><span data-stu-id="62ba2-241">**Name**</span></span>|<span data-ttu-id="62ba2-242">**Тип**</span><span class="sxs-lookup"><span data-stu-id="62ba2-242">**Type**</span></span>|<span data-ttu-id="62ba2-243">**Значение**</span><span class="sxs-lookup"><span data-stu-id="62ba2-243">**Value**</span></span>|<span data-ttu-id="62ba2-244">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="62ba2-244">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="62ba2-245">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="62ba2-245">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="62ba2-246">TXT</span><span class="sxs-lookup"><span data-stu-id="62ba2-246">TXT</span></span>  <br/> |<span data-ttu-id="62ba2-247">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="62ba2-247">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="62ba2-248">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="62ba2-248">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="62ba2-249">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="62ba2-249">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost — BP — configure – 4-1](../../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. <span data-ttu-id="62ba2-251">Нажмите кнопку **Добавить запись.**</span><span class="sxs-lookup"><span data-stu-id="62ba2-251">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-4-2](../../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. <span data-ttu-id="62ba2-253">Повторите два описанных выше шага, используя значения из второй строки таблицы, чтобы добавить еще одну запись SRV.</span><span class="sxs-lookup"><span data-stu-id="62ba2-253">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="62ba2-254">Добавление двух записей SRV, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="62ba2-254">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="62ba2-255"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="62ba2-255"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="62ba2-256">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="62ba2-256">Follow the steps below.</span></span>
  
1. <span data-ttu-id="62ba2-p113">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте DreamHost по [этой ссылке](https://panel.dreamhost.com/). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="62ba2-p113">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="62ba2-260">На странице **панели мониторинга** выберите **домены**, а затем **Управление доменами**.</span><span class="sxs-lookup"><span data-stu-id="62ba2-260">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="62ba2-262">На странице " **Управление доменами** " в разделе **домен** выберите **DNS** для домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="62ba2-262">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="62ba2-264">В поля для новой записи в области **Add a custom DNS record** (Добавление настраиваемой записи DNS) введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="62ba2-264">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="62ba2-265">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="62ba2-265">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="62ba2-266">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="62ba2-266">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="62ba2-267">**Имя**</span><span class="sxs-lookup"><span data-stu-id="62ba2-267">**Name**</span></span>|<span data-ttu-id="62ba2-268">**Тип**</span><span class="sxs-lookup"><span data-stu-id="62ba2-268">**Type**</span></span>|<span data-ttu-id="62ba2-269">**Значение**</span><span class="sxs-lookup"><span data-stu-id="62ba2-269">**Value**</span></span>|<span data-ttu-id="62ba2-270">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="62ba2-270">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="62ba2-271">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="62ba2-271">_sip._tls</span></span>  <br/> |<span data-ttu-id="62ba2-272">SRV</span><span class="sxs-lookup"><span data-stu-id="62ba2-272">SRV</span></span>  <br/> |<span data-ttu-id="62ba2-273">100 1 443</span><span class="sxs-lookup"><span data-stu-id="62ba2-273">100 1 443</span></span>  <br/> <span data-ttu-id="62ba2-274">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="62ba2-274">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="62ba2-275">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="62ba2-275">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="62ba2-276">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="62ba2-276">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="62ba2-277">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="62ba2-277">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="62ba2-278">SRV</span><span class="sxs-lookup"><span data-stu-id="62ba2-278">SRV</span></span>  <br/> |<span data-ttu-id="62ba2-279">100 1 5061</span><span class="sxs-lookup"><span data-stu-id="62ba2-279">100 1 5061</span></span>  <br/> <span data-ttu-id="62ba2-280">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="62ba2-280">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="62ba2-281">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="62ba2-281">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="62ba2-282">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="62ba2-282">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost — BP — configure – 5-1](../../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. <span data-ttu-id="62ba2-284">Нажмите **Добавить запись сейчас!**.</span><span class="sxs-lookup"><span data-stu-id="62ba2-284">Select **Add Record Now!**.</span></span>
    
    ![Dreamhost-BP-Configure-5-2](../../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. <span data-ttu-id="62ba2-286">Повторите два описанных выше шага, используя значения из второй строки таблицы, чтобы добавить еще одну запись SRV.</span><span class="sxs-lookup"><span data-stu-id="62ba2-286">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="62ba2-p114">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="62ba2-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
