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
ms.openlocfilehash: f3f52e97fefece72dd96d9370e75e24fc4cebedf
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42248885"
---
# <a name="create-dns-records-at-dreamhost-for-office-365"></a><span data-ttu-id="aca42-103">Создание записей DNS для Office 365 на сайте Dreamhost</span><span class="sxs-lookup"><span data-stu-id="aca42-103">Create DNS records at Dreamhost for Office 365</span></span>

 <span data-ttu-id="aca42-104">Если вы не нашли то, что вы ищете, обратитесь к разделу **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="aca42-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="aca42-105">Если ваш поставщик услуг размещения DNS  DreamHost, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Lync и других служб.</span><span class="sxs-lookup"><span data-stu-id="aca42-105">If DreamHost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
 
<span data-ttu-id="aca42-106">Когда вы добавите эти записи на сайте DreamHost, ваш домен будет настроен для работы со службами Office 365.</span><span class="sxs-lookup"><span data-stu-id="aca42-106">After you add these records at DreamHost, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="aca42-107">Дополнительные сведения о веб-хостинге и DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="aca42-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="aca42-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="aca42-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="aca42-111">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="aca42-111">Add a TXT record for verification</span></span>
<span data-ttu-id="aca42-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="aca42-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="aca42-p102">Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете данным доменом.</span><span class="sxs-lookup"><span data-stu-id="aca42-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aca42-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="aca42-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="aca42-p104">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте DreamHost по [этой ссылке](https://panel.dreamhost.com/). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="aca42-p104">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="aca42-120">На странице **панели мониторинга** выберите **домены**, а затем **Управление доменами**.</span><span class="sxs-lookup"><span data-stu-id="aca42-120">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="aca42-122">На странице " **Управление доменами** " в разделе **домен** выберите **DNS** для домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="aca42-122">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="aca42-124">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="aca42-124">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="aca42-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="aca42-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="aca42-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="aca42-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="aca42-127">**Имя**</span><span class="sxs-lookup"><span data-stu-id="aca42-127">**Name**</span></span>|<span data-ttu-id="aca42-128">**Тип**</span><span class="sxs-lookup"><span data-stu-id="aca42-128">**Type**</span></span>|<span data-ttu-id="aca42-129">**Значение**</span><span class="sxs-lookup"><span data-stu-id="aca42-129">**Value**</span></span>|<span data-ttu-id="aca42-130">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="aca42-130">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="aca42-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="aca42-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="aca42-132">TXT</span><span class="sxs-lookup"><span data-stu-id="aca42-132">TXT</span></span>  <br/> |<span data-ttu-id="aca42-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="aca42-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="aca42-p105">**Примечание.** Это пример. Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.           [Где это находится?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="aca42-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="aca42-137">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="aca42-137">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost — BP — Verify – 1-1](../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. <span data-ttu-id="aca42-139">Нажмите кнопку **Добавить запись.**</span><span class="sxs-lookup"><span data-stu-id="aca42-139">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Verify-1-2](../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. <span data-ttu-id="aca42-141">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="aca42-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="aca42-142">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="aca42-142">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="aca42-143">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="aca42-143">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="aca42-144">В центре администрирования перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> **параметров** \> ".</span><span class="sxs-lookup"><span data-stu-id="aca42-144">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="aca42-145">На странице **Domains (домены** ) выберите домен, который вы хотите проверить.</span><span class="sxs-lookup"><span data-stu-id="aca42-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="aca42-146">На странице **Настройка** выберите пункт **Запуск программы установки**.</span><span class="sxs-lookup"><span data-stu-id="aca42-146">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="aca42-147">На странице **Проверка домена** нажмите кнопку **проверить**.</span><span class="sxs-lookup"><span data-stu-id="aca42-147">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="aca42-p106">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="aca42-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="aca42-151">Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="aca42-151">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="aca42-152"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="aca42-152"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="aca42-153">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="aca42-153">Follow the steps below.</span></span>
  
1. <span data-ttu-id="aca42-p107">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте DreamHost по [этой ссылке](https://panel.dreamhost.com/). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="aca42-p107">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="aca42-157">На странице **панель мониторинга** выберите пункт **почта**, а затем — **Пользовательская MX**.</span><span class="sxs-lookup"><span data-stu-id="aca42-157">On the **Dashboard** page, select **Mail**, and then **Custom MX**.</span></span>
    
    ![Dreamhost-BP-Configure-2-1](../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. <span data-ttu-id="aca42-159">В разделе **Управление доставкой почты** в столбце **действия** выберите команду **изменить** для домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="aca42-159">In the **Manage Mail Delivery** section, in the **Actions** column, select **Edit** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-2-2](../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. <span data-ttu-id="aca42-161">В поля для новой записи в области **Custom MX Record** (Настраиваемая запись MX) введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="aca42-161">In the **Custom MX Record** section, in the boxes for the new record, type or copy and paste the following values from the following table.</span></span> 
    
    <span data-ttu-id="aca42-162">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="aca42-162">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="aca42-163">(Если существуют другие записи MX, пометьте их для удаления.)</span><span class="sxs-lookup"><span data-stu-id="aca42-163">(If there are any other existing MX records, mark those records to be deleted.)</span></span>
    
    |<span data-ttu-id="aca42-164">**Запись MX (обязательно)**</span><span class="sxs-lookup"><span data-stu-id="aca42-164">**MX Record (required)**</span></span>|
    |:-----|
    |<span data-ttu-id="aca42-165">0  *\<ключ_домена\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="aca42-165">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="aca42-166">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="aca42-166">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="aca42-p108">0  значение приоритета MX. Добавьте его в начало значения MX, отделив от остальной части пробелом.  </span><span class="sxs-lookup"><span data-stu-id="aca42-p108">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="aca42-169">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Office 365.</span><span class="sxs-lookup"><span data-stu-id="aca42-169">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="aca42-170">Как найти это значение?</span><span class="sxs-lookup"><span data-stu-id="aca42-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Dreamhost — BP — configure – 2-3](../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. <span data-ttu-id="aca42-172">Выберите **изменить этот домен для использования настраиваемых записей MX сейчас!**</span><span class="sxs-lookup"><span data-stu-id="aca42-172">Select **Change this domain to use custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-4](../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. <span data-ttu-id="aca42-174">Если есть какие-либо другие записи MX, удалите каждую из них, выделив ее и нажав на клавиатуре клавишу **DELETE**.</span><span class="sxs-lookup"><span data-stu-id="aca42-174">If there are any other existing MX records, delete each record by selecting the entry and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Dreamhost-BP-Configure-2-5](../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. <span data-ttu-id="aca42-176">Если вы удалили какие-либо записи, установите флажок **обновить пользовательские записи MX теперь.**</span><span class="sxs-lookup"><span data-stu-id="aca42-176">If you have deleted any records, select **Update your custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-6](../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="aca42-178">Добавление шести записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="aca42-178">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="aca42-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="aca42-179"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="aca42-180">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="aca42-180">Follow the steps below.</span></span>
  
1. <span data-ttu-id="aca42-p110">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте DreamHost по [этой ссылке](https://panel.dreamhost.com/). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="aca42-p110">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="aca42-184">На странице **панели мониторинга** выберите **домены**, а затем **Управление доменами**.</span><span class="sxs-lookup"><span data-stu-id="aca42-184">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="aca42-186">На странице " **Управление доменами** " в разделе **домен** выберите **DNS** для домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="aca42-186">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="aca42-188">В поля для новой записи в области **Add a custom DNS record** (Добавление настраиваемой записи DNS) введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="aca42-188">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="aca42-189">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="aca42-189">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="aca42-190">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="aca42-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="aca42-191">**Имя**</span><span class="sxs-lookup"><span data-stu-id="aca42-191">**Name**</span></span>|<span data-ttu-id="aca42-192">**Тип**</span><span class="sxs-lookup"><span data-stu-id="aca42-192">**Type**</span></span>|<span data-ttu-id="aca42-193">**Значение**</span><span class="sxs-lookup"><span data-stu-id="aca42-193">**Value**</span></span>|<span data-ttu-id="aca42-194">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="aca42-194">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="aca42-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="aca42-195">autodiscover</span></span>  <br/> |<span data-ttu-id="aca42-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="aca42-196">CNAME</span></span>  <br/> |<span data-ttu-id="aca42-197">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="aca42-197">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="aca42-198">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="aca42-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="aca42-199">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="aca42-199">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="aca42-200">sip</span><span class="sxs-lookup"><span data-stu-id="aca42-200">sip</span></span>  <br/> |<span data-ttu-id="aca42-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="aca42-201">CNAME</span></span>  <br/> |<span data-ttu-id="aca42-202">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="aca42-202">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="aca42-203">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="aca42-203">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="aca42-204">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="aca42-204">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="aca42-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="aca42-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="aca42-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="aca42-206">CNAME</span></span>  <br/> |<span data-ttu-id="aca42-207">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="aca42-207">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="aca42-208">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="aca42-208">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="aca42-209">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="aca42-209">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="aca42-210">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="aca42-210">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="aca42-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="aca42-211">CNAME</span></span>  <br/> |<span data-ttu-id="aca42-212">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="aca42-212">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="aca42-213">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="aca42-213">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="aca42-214">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="aca42-214">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="aca42-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="aca42-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="aca42-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="aca42-216">CNAME</span></span>  <br/> |<span data-ttu-id="aca42-217">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="aca42-217">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="aca42-218">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="aca42-218">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="aca42-219">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="aca42-219">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost — BP — configure – 3-1](../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. <span data-ttu-id="aca42-221">Нажмите кнопку **Добавить запись.**</span><span class="sxs-lookup"><span data-stu-id="aca42-221">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-3-2](../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. <span data-ttu-id="aca42-223">Используя предыдущие два действия и значения из других пяти строк в таблице, добавьте все остальные пять записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="aca42-223">Using the preceding two steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="aca42-224">Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="aca42-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="aca42-225"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="aca42-225"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="aca42-226">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="aca42-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="aca42-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="aca42-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="aca42-228">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="aca42-228">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="aca42-229">Вместо этого добавьте необходимые значения Office 365 к текущей записи, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="aca42-229">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="aca42-230">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="aca42-230">Follow the steps below.</span></span>
  
1. <span data-ttu-id="aca42-p112">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте DreamHost по [этой ссылке](https://panel.dreamhost.com/). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="aca42-p112">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="aca42-234">На странице **панели мониторинга** выберите **домены**, а затем **Управление доменами**.</span><span class="sxs-lookup"><span data-stu-id="aca42-234">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="aca42-236">На странице " **Управление доменами** " в разделе **домен** выберите **DNS** для домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="aca42-236">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="aca42-238">В поля для новой записи в области **Add a custom DNS record** (Добавление настраиваемой записи DNS) введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="aca42-238">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="aca42-239">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="aca42-239">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="aca42-240">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="aca42-240">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="aca42-241">**Имя**</span><span class="sxs-lookup"><span data-stu-id="aca42-241">**Name**</span></span>|<span data-ttu-id="aca42-242">**Тип**</span><span class="sxs-lookup"><span data-stu-id="aca42-242">**Type**</span></span>|<span data-ttu-id="aca42-243">**Значение**</span><span class="sxs-lookup"><span data-stu-id="aca42-243">**Value**</span></span>|<span data-ttu-id="aca42-244">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="aca42-244">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="aca42-245">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="aca42-245">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="aca42-246">TXT</span><span class="sxs-lookup"><span data-stu-id="aca42-246">TXT</span></span>  <br/> |<span data-ttu-id="aca42-247">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="aca42-247">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="aca42-248">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="aca42-248">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="aca42-249">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="aca42-249">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost — BP — configure – 4-1](../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. <span data-ttu-id="aca42-251">Нажмите кнопку **Добавить запись.**</span><span class="sxs-lookup"><span data-stu-id="aca42-251">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-4-2](../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. <span data-ttu-id="aca42-253">Повторите два описанных выше шага, используя значения из второй строки таблицы, чтобы добавить еще одну запись SRV.</span><span class="sxs-lookup"><span data-stu-id="aca42-253">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="aca42-254">Добавление двух записей SRV, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="aca42-254">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="aca42-255"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="aca42-255"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="aca42-256">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="aca42-256">Follow the steps below.</span></span>
  
1. <span data-ttu-id="aca42-p113">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте DreamHost по [этой ссылке](https://panel.dreamhost.com/). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="aca42-p113">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="aca42-260">На странице **панели мониторинга** выберите **домены**, а затем **Управление доменами**.</span><span class="sxs-lookup"><span data-stu-id="aca42-260">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="aca42-262">На странице " **Управление доменами** " в разделе **домен** выберите **DNS** для домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="aca42-262">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="aca42-264">В поля для новой записи в области **Add a custom DNS record** (Добавление настраиваемой записи DNS) введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="aca42-264">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="aca42-265">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="aca42-265">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="aca42-266">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="aca42-266">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="aca42-267">**Имя**</span><span class="sxs-lookup"><span data-stu-id="aca42-267">**Name**</span></span>|<span data-ttu-id="aca42-268">**Тип**</span><span class="sxs-lookup"><span data-stu-id="aca42-268">**Type**</span></span>|<span data-ttu-id="aca42-269">**Значение**</span><span class="sxs-lookup"><span data-stu-id="aca42-269">**Value**</span></span>|<span data-ttu-id="aca42-270">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="aca42-270">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="aca42-271">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="aca42-271">_sip._tls</span></span>  <br/> |<span data-ttu-id="aca42-272">SRV</span><span class="sxs-lookup"><span data-stu-id="aca42-272">SRV</span></span>  <br/> |<span data-ttu-id="aca42-273">100 1 443</span><span class="sxs-lookup"><span data-stu-id="aca42-273">100 1 443</span></span>  <br/> <span data-ttu-id="aca42-274">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="aca42-274">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="aca42-275">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="aca42-275">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="aca42-276">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="aca42-276">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="aca42-277">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="aca42-277">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="aca42-278">SRV</span><span class="sxs-lookup"><span data-stu-id="aca42-278">SRV</span></span>  <br/> |<span data-ttu-id="aca42-279">100 1 5061</span><span class="sxs-lookup"><span data-stu-id="aca42-279">100 1 5061</span></span>  <br/> <span data-ttu-id="aca42-280">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="aca42-280">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="aca42-281">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="aca42-281">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="aca42-282">(Это поле является обязательным.)</span><span class="sxs-lookup"><span data-stu-id="aca42-282">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost — BP — configure – 5-1](../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. <span data-ttu-id="aca42-284">Нажмите **Добавить запись сейчас!**.</span><span class="sxs-lookup"><span data-stu-id="aca42-284">Select **Add Record Now!**.</span></span>
    
    ![Dreamhost-BP-Configure-5-2](../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. <span data-ttu-id="aca42-286">Повторите два описанных выше шага, используя значения из второй строки таблицы, чтобы добавить еще одну запись SRV.</span><span class="sxs-lookup"><span data-stu-id="aca42-286">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="aca42-p114">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="aca42-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
