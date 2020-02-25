---
title: Создание записей DNS на веб-сайте GoDaddy для Office 365
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
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу GoDaddy для Office 365.
ms.custom: okr_smb
ms.openlocfilehash: 4a67ef090c2b91c4cf1fdde376ab35e3a4ed4e20
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42245372"
---
# <a name="create-dns-records-at-godaddy-for-office-365"></a><span data-ttu-id="985eb-103">Создание записей DNS на веб-сайте GoDaddy для Office 365</span><span class="sxs-lookup"><span data-stu-id="985eb-103">Create DNS records at GoDaddy for Office 365</span></span>

 <span data-ttu-id="985eb-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="985eb-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="985eb-105">Если ваш поставщик услуг размещения DNS  GoDaddy, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="985eb-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="985eb-106">Когда вы добавите эти записи на сайте GoDaddy, ваш домен будет настроен для работы со службами Office 365.</span><span class="sxs-lookup"><span data-stu-id="985eb-106">After you add these records at GoDaddy, your domain will be set up to work with Office 365 services.</span></span>

<span data-ttu-id="985eb-107">Дополнительные сведения о веб-хостинге и DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="985eb-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>

> [!NOTE]
> <span data-ttu-id="985eb-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="985eb-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="985eb-111">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="985eb-111">Add a TXT record for verification</span></span>
<span data-ttu-id="985eb-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="985eb-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="985eb-p102">Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете данным доменом.</span><span class="sxs-lookup"><span data-stu-id="985eb-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="985eb-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="985eb-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="985eb-117">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="985eb-117">Follow the steps below.</span></span>

1. <span data-ttu-id="985eb-p104">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте GoDaddy по [этой ссылке](https://account.godaddy.com/products/?go_redirect=disabled). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="985eb-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy — BP — configure – 1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="985eb-121">В разделе **домены**выберите DNS в домене, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="985eb-121">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy — BP — configure – 1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="985eb-123">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="985eb-123">Select **Add**.</span></span>

    ![GoDaddy — BP — configure – 1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="985eb-125">В раскрывающемся списке выберите значение **TXT (Text)** (Текст).</span><span class="sxs-lookup"><span data-stu-id="985eb-125">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="985eb-126">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="985eb-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="985eb-127">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="985eb-127">**Record type**</span></span> |<span data-ttu-id="985eb-128">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="985eb-128">**Host**</span></span>|<span data-ttu-id="985eb-129">**TXT Value (Значение TXT)**</span><span class="sxs-lookup"><span data-stu-id="985eb-129">**TXT Value**</span></span>|<span data-ttu-id="985eb-130">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="985eb-130">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="985eb-131">TXT (Text) (TXT (Текст))</span><span class="sxs-lookup"><span data-stu-id="985eb-131">TXT (Text)</span></span>|@|<span data-ttu-id="985eb-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="985eb-132">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="985eb-133">**Примечание**: это пример.</span><span class="sxs-lookup"><span data-stu-id="985eb-133">**Note**: This is an example.</span></span> <span data-ttu-id="985eb-134">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="985eb-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="985eb-135">Как найти это значение?</span><span class="sxs-lookup"><span data-stu-id="985eb-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="985eb-136">1 час</span><span class="sxs-lookup"><span data-stu-id="985eb-136">1 hour</span></span>  <br><span data-ttu-id="985eb-137">(Выберите значение из раскрывающегося списка.)</span><span class="sxs-lookup"><span data-stu-id="985eb-137">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy — BP — Verify – 1-0](../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="985eb-139">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="985eb-139">Select **Save**.</span></span>

6. <span data-ttu-id="985eb-140">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="985eb-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="985eb-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="985eb-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>

<span data-ttu-id="985eb-142">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="985eb-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="985eb-143">В центре администрирования перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> **параметров** \> ".</span><span class="sxs-lookup"><span data-stu-id="985eb-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="985eb-144">На странице **Domains (домены** ) выберите домен, который вы хотите проверить.</span><span class="sxs-lookup"><span data-stu-id="985eb-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="985eb-145">На странице **Настройка** выберите пункт **Запуск программы установки**.</span><span class="sxs-lookup"><span data-stu-id="985eb-145">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="985eb-146">На странице **Проверка домена** нажмите кнопку **проверить**.</span><span class="sxs-lookup"><span data-stu-id="985eb-146">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="985eb-p107">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="985eb-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="985eb-150">Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="985eb-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="985eb-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="985eb-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="985eb-152">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="985eb-152">Follow the steps below.</span></span>

1. <span data-ttu-id="985eb-p108">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте GoDaddy по [этой ссылке](https://account.godaddy.com/products/?go_redirect=disabled). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="985eb-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy — BP — configure – 1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="985eb-156">В разделе **домены**выберите DNS в домене, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="985eb-156">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy — BP — configure – 1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="985eb-158">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="985eb-158">Select **Add**.</span></span>

    ![GoDaddy — BP — configure – 1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="985eb-160">В раскрывающемся списке выберите значение **MX (Mail Exchanger)** (почтовый обменник).</span><span class="sxs-lookup"><span data-stu-id="985eb-160">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy — BP — configure – 2-0](../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="985eb-162">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="985eb-162">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="985eb-163">В раскрывающемся списке выберите значение **TTL (срок жизни** ).</span><span class="sxs-lookup"><span data-stu-id="985eb-163">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="985eb-164">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="985eb-164">**Record type**</span></span>|<span data-ttu-id="985eb-165">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="985eb-165">**Host**</span></span>|<span data-ttu-id="985eb-166">**Points to (Указывает на)**</span><span class="sxs-lookup"><span data-stu-id="985eb-166">**Points to**</span></span>|<span data-ttu-id="985eb-167">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="985eb-167">**Priority**</span></span>|<span data-ttu-id="985eb-168">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="985eb-168">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="985eb-169">MX (Mail Exchanger) (Почтовый обменник)</span><span class="sxs-lookup"><span data-stu-id="985eb-169">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="985eb-170">*\<ключ_домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="985eb-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="985eb-171">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Office 365.</span><span class="sxs-lookup"><span data-stu-id="985eb-171">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="985eb-172">Где это находится?</span><span class="sxs-lookup"><span data-stu-id="985eb-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="985eb-173">10 </span><span class="sxs-lookup"><span data-stu-id="985eb-173">10</span></span>  <br/> <span data-ttu-id="985eb-174">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).   </span><span class="sxs-lookup"><span data-stu-id="985eb-174">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="985eb-175">1 hour</span><span class="sxs-lookup"><span data-stu-id="985eb-175">1 hour</span></span>  <br/> |

6. <span data-ttu-id="985eb-176">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="985eb-176">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="985eb-177">Добавление записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="985eb-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="985eb-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="985eb-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="985eb-179">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="985eb-179">Follow the steps below.</span></span>

1. <span data-ttu-id="985eb-p110">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте GoDaddy по [этой ссылке](https://account.godaddy.com/products/?go_redirect=disabled). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="985eb-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy — BP — configure – 1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="985eb-183">В разделе **домены**выберите DNS в домене, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="985eb-183">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy — BP — configure – 1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="985eb-185">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="985eb-185">Select **Add**.</span></span>

    ![GoDaddy — BP — configure – 1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="985eb-187">В раскрывающемся списке выберите значение **CNAME (Alias)** (Псевдоним CNAME).</span><span class="sxs-lookup"><span data-stu-id="985eb-187">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy — BP — configure – 3-0](../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="985eb-189">Создайте первую запись CNAME.</span><span class="sxs-lookup"><span data-stu-id="985eb-189">Create the first CNAME record.</span></span>

    <span data-ttu-id="985eb-190">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="985eb-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="985eb-191">В раскрывающемся списке выберите значение **TTL (срок жизни** ).</span><span class="sxs-lookup"><span data-stu-id="985eb-191">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="985eb-192">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="985eb-192">**Record type**</span></span>|<span data-ttu-id="985eb-193">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="985eb-193">**Host**</span></span>|<span data-ttu-id="985eb-194">**Points to (Указывает на)**</span><span class="sxs-lookup"><span data-stu-id="985eb-194">**Points to**</span></span>|<span data-ttu-id="985eb-195">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="985eb-195">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="985eb-196">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="985eb-196">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="985eb-197">autodiscover</span><span class="sxs-lookup"><span data-stu-id="985eb-197">autodiscover</span></span>  <br/> |<span data-ttu-id="985eb-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="985eb-198">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="985eb-199">1 hour</span><span class="sxs-lookup"><span data-stu-id="985eb-199">1 hour</span></span>  <br/> |
    |<span data-ttu-id="985eb-200">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="985eb-200">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="985eb-201">sip</span><span class="sxs-lookup"><span data-stu-id="985eb-201">sip</span></span>  <br/> |<span data-ttu-id="985eb-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="985eb-202">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="985eb-203">1 час</span><span class="sxs-lookup"><span data-stu-id="985eb-203">1 hour</span></span>  <br/> |
    |<span data-ttu-id="985eb-204">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="985eb-204">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="985eb-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="985eb-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="985eb-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="985eb-206">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="985eb-207">1 час</span><span class="sxs-lookup"><span data-stu-id="985eb-207">1 hour</span></span>  <br/> |
    |<span data-ttu-id="985eb-208">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="985eb-208">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="985eb-209">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="985eb-209">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="985eb-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="985eb-210">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="985eb-211">1 час</span><span class="sxs-lookup"><span data-stu-id="985eb-211">1 hour</span></span>  <br/> |
    |<span data-ttu-id="985eb-212">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="985eb-212">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="985eb-213">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="985eb-213">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="985eb-214">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="985eb-214">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="985eb-215">1 hour</span><span class="sxs-lookup"><span data-stu-id="985eb-215">1 hour</span></span>  <br/> |



6. <span data-ttu-id="985eb-216">Повторите эти действия, чтобы добавить следующую запись CNAME, пока не будут созданы все шесть записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="985eb-216">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="985eb-217">Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="985eb-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="985eb-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="985eb-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="985eb-219">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="985eb-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="985eb-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="985eb-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="985eb-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="985eb-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="985eb-222">Вместо этого добавьте необходимые значения Office 365 к текущей записи, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="985eb-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="985eb-223">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="985eb-223">Follow the steps below.</span></span>

1. <span data-ttu-id="985eb-p112">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте GoDaddy по [этой ссылке](https://account.godaddy.com/products/?go_redirect=disabled). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="985eb-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy — BP — configure – 1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="985eb-227">В разделе **домены**выберите DNS в домене, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="985eb-227">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy — BP — configure – 1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="985eb-229">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="985eb-229">Select **Add**.</span></span>

    ![GoDaddy — BP — configure – 1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="985eb-231">В раскрывающемся списке выберите значение **TXT (Text)** (Текст).</span><span class="sxs-lookup"><span data-stu-id="985eb-231">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy — BP — configure – 4-0](../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="985eb-233">В поля для новой записи введите (или скопируйте и вставьте) указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="985eb-233">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="985eb-234">(Выберите значение **TTL** в раскрывающихся списках.)</span><span class="sxs-lookup"><span data-stu-id="985eb-234">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="985eb-235">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="985eb-235">**Record type**</span></span>|<span data-ttu-id="985eb-236">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="985eb-236">**Host**</span></span>|<span data-ttu-id="985eb-237">**TXT Value (Значение TXT)**</span><span class="sxs-lookup"><span data-stu-id="985eb-237">**TXT Value**</span></span>|<span data-ttu-id="985eb-238">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="985eb-238">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="985eb-239">TXT (Text) (TXT (Текст))</span><span class="sxs-lookup"><span data-stu-id="985eb-239">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="985eb-240">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="985eb-240">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="985eb-241">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="985eb-241">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="985eb-242">1 hour</span><span class="sxs-lookup"><span data-stu-id="985eb-242">1 hour</span></span>  <br/> |

    ![GoDaddy — BP — configure – 4-1](../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="985eb-244">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="985eb-244">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="985eb-245">Добавление двух записей SRV, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="985eb-245">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="985eb-246"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="985eb-246"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="985eb-247">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="985eb-247">Follow the steps below.</span></span>

1. <span data-ttu-id="985eb-p113">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте GoDaddy по [этой ссылке](https://account.godaddy.com/products/?go_redirect=disabled). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="985eb-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy — BP — configure – 1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="985eb-251">В разделе **домены**выберите DNS в домене, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="985eb-251">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy — BP — configure – 1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="985eb-253">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="985eb-253">Select **Add**.</span></span>

    ![GoDaddy — BP — configure – 1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="985eb-255">В раскрывающемся списке выберите значение **SRV (Service)** (Служба).</span><span class="sxs-lookup"><span data-stu-id="985eb-255">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy — BP — configure – 5-0](../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="985eb-257">Создайте первую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="985eb-257">Create the first SRV record.</span></span>

    <span data-ttu-id="985eb-258">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="985eb-258">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="985eb-259">В раскрывающихся списках выберите **тип записи** и значения **срока жизни (TTL** ).</span><span class="sxs-lookup"><span data-stu-id="985eb-259">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="985eb-260">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="985eb-260">**Record type**</span></span>|<span data-ttu-id="985eb-261">**Имя**</span><span class="sxs-lookup"><span data-stu-id="985eb-261">**Name**</span></span>|<span data-ttu-id="985eb-262">**Target**</span><span class="sxs-lookup"><span data-stu-id="985eb-262">**Target**</span></span>|<span data-ttu-id="985eb-263">**Протокол**</span><span class="sxs-lookup"><span data-stu-id="985eb-263">**Protocol**</span></span>|<span data-ttu-id="985eb-264">**Служба**</span><span class="sxs-lookup"><span data-stu-id="985eb-264">**Service**</span></span>|<span data-ttu-id="985eb-265">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="985eb-265">**Priority**</span></span>|<span data-ttu-id="985eb-266">**Weight (Вес)**</span><span class="sxs-lookup"><span data-stu-id="985eb-266">**Weight**</span></span>|<span data-ttu-id="985eb-267">**Port (Порт)**</span><span class="sxs-lookup"><span data-stu-id="985eb-267">**Port**</span></span>|<span data-ttu-id="985eb-268">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="985eb-268">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="985eb-269">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="985eb-269">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="985eb-270">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="985eb-270">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="985eb-271">_tls</span><span class="sxs-lookup"><span data-stu-id="985eb-271">_tls</span></span>  <br/> |<span data-ttu-id="985eb-272">_sip</span><span class="sxs-lookup"><span data-stu-id="985eb-272">_sip</span></span>  <br/> |<span data-ttu-id="985eb-273">100</span><span class="sxs-lookup"><span data-stu-id="985eb-273">100</span></span>  <br/> |<span data-ttu-id="985eb-274">1,1</span><span class="sxs-lookup"><span data-stu-id="985eb-274">1</span></span>  <br/> |<span data-ttu-id="985eb-275">443</span><span class="sxs-lookup"><span data-stu-id="985eb-275">443</span></span>  <br/> |<span data-ttu-id="985eb-276">1 час</span><span class="sxs-lookup"><span data-stu-id="985eb-276">1 hour</span></span>  <br/> |
    |<span data-ttu-id="985eb-277">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="985eb-277">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="985eb-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="985eb-278">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="985eb-279">_tcp</span><span class="sxs-lookup"><span data-stu-id="985eb-279">_tcp</span></span>  <br/> |<span data-ttu-id="985eb-280">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="985eb-280">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="985eb-281">100</span><span class="sxs-lookup"><span data-stu-id="985eb-281">100</span></span>  <br/> |<span data-ttu-id="985eb-282">1,1</span><span class="sxs-lookup"><span data-stu-id="985eb-282">1</span></span>  <br/> |<span data-ttu-id="985eb-283">5061</span><span class="sxs-lookup"><span data-stu-id="985eb-283">5061</span></span>  <br/> |<span data-ttu-id="985eb-284">1 час</span><span class="sxs-lookup"><span data-stu-id="985eb-284">1 hour</span></span>  <br/> |

    ![GoDaddy — BP — configure – 5-1](../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="985eb-286">Повторите **Шаг 5** , чтобы создать другую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="985eb-286">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="985eb-287">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="985eb-287">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="985eb-p114">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="985eb-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
