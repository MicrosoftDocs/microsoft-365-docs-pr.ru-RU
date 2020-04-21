---
title: Создание записей DNS на сайте GoDaddy для Майкрософт
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
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу GoDaddy для Майкрософт.
ms.custom: okr_smb
ms.openlocfilehash: 0e9b75bcd4aa93270efd9b2d94fa2ceeb6e55f75
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629555"
---
# <a name="create-dns-records-at-godaddy-for-microsoft"></a><span data-ttu-id="a3355-103">Создание записей DNS на сайте GoDaddy для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a3355-103">Create DNS records at GoDaddy for Microsoft</span></span>

 <span data-ttu-id="a3355-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="a3355-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="a3355-105">Если ваш поставщик услуг размещения DNS  GoDaddy, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="a3355-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="a3355-106">Когда вы добавите эти записи на сайте GoDaddy, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a3355-106">After you add these records at GoDaddy, your domain will be set up to work with Microsoft services.</span></span>

<span data-ttu-id="a3355-107">Чтобы узнать о размещении и DNS для веб-сайтов с помощью Microsoft, ознакомьтесь со статьей [использование общедоступного веб-сайта с корпорацией Майкрософт](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="a3355-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>

> [!NOTE]
> <span data-ttu-id="a3355-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a3355-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a3355-111">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="a3355-111">Add a TXT record for verification</span></span>
<span data-ttu-id="a3355-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a3355-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a3355-113">Перед использованием домена с корпорацией Майкрософт необходимо убедиться, что вы являетесь его владельцем.</span><span class="sxs-lookup"><span data-stu-id="a3355-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="a3355-114">Вы можете войти в свою учетную запись у вас в вашем регистраторе доменных имен и создать запись DNS в Майкрософт, если вы владеете этим доменом.</span><span class="sxs-lookup"><span data-stu-id="a3355-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="a3355-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="a3355-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="a3355-117">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a3355-117">Follow the steps below.</span></span>

1. <span data-ttu-id="a3355-p104">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте GoDaddy по [этой ссылке](https://account.godaddy.com/products/?go_redirect=disabled). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="a3355-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy — BP — configure – 1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="a3355-121">В разделе **домены**выберите DNS в домене, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="a3355-121">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy — BP — configure – 1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="a3355-123">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="a3355-123">Select **Add**.</span></span>

    ![GoDaddy — BP — configure – 1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="a3355-125">В раскрывающемся списке выберите значение **TXT (Text)** (Текст).</span><span class="sxs-lookup"><span data-stu-id="a3355-125">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="a3355-126">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="a3355-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="a3355-127">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="a3355-127">**Record type**</span></span> |<span data-ttu-id="a3355-128">**Host** (Узел)</span><span class="sxs-lookup"><span data-stu-id="a3355-128">**Host**</span></span>|<span data-ttu-id="a3355-129">**TXT Value** (Значение TXT)</span><span class="sxs-lookup"><span data-stu-id="a3355-129">**TXT Value**</span></span>|<span data-ttu-id="a3355-130">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="a3355-130">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a3355-131">TXT (текст)</span><span class="sxs-lookup"><span data-stu-id="a3355-131">TXT (Text)</span></span>|@|<span data-ttu-id="a3355-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a3355-132">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="a3355-133">**Примечание**: это пример.</span><span class="sxs-lookup"><span data-stu-id="a3355-133">**Note**: This is an example.</span></span> <span data-ttu-id="a3355-134">Используйте указанную здесь **конечную точку или значение адреса** из таблицы.</span><span class="sxs-lookup"><span data-stu-id="a3355-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="a3355-135">Как найти это значение?</span><span class="sxs-lookup"><span data-stu-id="a3355-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="a3355-136">1 час</span><span class="sxs-lookup"><span data-stu-id="a3355-136">1 hour</span></span>  <br><span data-ttu-id="a3355-137">(Выберите значение из раскрывающегося списка.)</span><span class="sxs-lookup"><span data-stu-id="a3355-137">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy — BP — Verify – 1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="a3355-139">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a3355-139">Select **Save**.</span></span>

6. <span data-ttu-id="a3355-140">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="a3355-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="a3355-141">Теперь, когда вы добавили запись на сайте регистратора доменных имен, вернитесь в корпорацию Майкрософт и запросите запись.</span><span class="sxs-lookup"><span data-stu-id="a3355-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>

<span data-ttu-id="a3355-142">После того как корпорация Майкрософт обнаружит правильную запись TXT, ваш домен будет проверен.</span><span class="sxs-lookup"><span data-stu-id="a3355-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a3355-143">В центре администрирования Майкрософт перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> **параметров** \> ".</span><span class="sxs-lookup"><span data-stu-id="a3355-143">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="a3355-144">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="a3355-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="a3355-145">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="a3355-145">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="a3355-146">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="a3355-146">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="a3355-p107">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a3355-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="a3355-150">Добавление записи MX для отправки электронной почты для вашего домена в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a3355-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="a3355-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a3355-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="a3355-152">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a3355-152">Follow the steps below.</span></span>

1. <span data-ttu-id="a3355-p108">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте GoDaddy по [этой ссылке](https://account.godaddy.com/products/?go_redirect=disabled). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="a3355-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy — BP — configure – 1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="a3355-156">В разделе **домены**выберите DNS в домене, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="a3355-156">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy — BP — configure – 1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="a3355-158">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="a3355-158">Select **Add**.</span></span>

    ![GoDaddy — BP — configure – 1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="a3355-160">В раскрывающемся списке выберите значение **MX (Mail Exchanger)** (почтовый обменник).</span><span class="sxs-lookup"><span data-stu-id="a3355-160">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy — BP — configure – 2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="a3355-162">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="a3355-162">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="a3355-163">В раскрывающемся списке выберите значение **TTL (срок жизни** ).</span><span class="sxs-lookup"><span data-stu-id="a3355-163">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="a3355-164">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="a3355-164">**Record type**</span></span>|<span data-ttu-id="a3355-165">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="a3355-165">**Host**</span></span>|<span data-ttu-id="a3355-166">**Points to** (Указывает на)</span><span class="sxs-lookup"><span data-stu-id="a3355-166">**Points to**</span></span>|<span data-ttu-id="a3355-167">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="a3355-167">**Priority**</span></span>|<span data-ttu-id="a3355-168">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="a3355-168">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a3355-169">MX (Mail Exchanger) (Почтовый обменник)</span><span class="sxs-lookup"><span data-stu-id="a3355-169">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="a3355-170">*\<ключ_домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a3355-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="a3355-171">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a3355-171">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="a3355-172">Где это находится?</span><span class="sxs-lookup"><span data-stu-id="a3355-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="a3355-173">10 </span><span class="sxs-lookup"><span data-stu-id="a3355-173">10</span></span>  <br/> <span data-ttu-id="a3355-174">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).   </span><span class="sxs-lookup"><span data-stu-id="a3355-174">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="a3355-175">1 час</span><span class="sxs-lookup"><span data-stu-id="a3355-175">1 hour</span></span>  <br/> |

6. <span data-ttu-id="a3355-176">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a3355-176">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="a3355-177">Добавление записей CNAME, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a3355-177">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="a3355-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a3355-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="a3355-179">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a3355-179">Follow the steps below.</span></span>

1. <span data-ttu-id="a3355-p110">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте GoDaddy по [этой ссылке](https://account.godaddy.com/products/?go_redirect=disabled). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="a3355-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy — BP — configure – 1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="a3355-183">В разделе **домены**выберите DNS в домене, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="a3355-183">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy — BP — configure – 1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="a3355-185">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="a3355-185">Select **Add**.</span></span>

    ![GoDaddy — BP — configure – 1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="a3355-187">В раскрывающемся списке выберите значение **CNAME (Alias)** (Псевдоним CNAME).</span><span class="sxs-lookup"><span data-stu-id="a3355-187">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy — BP — configure – 3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="a3355-189">Создайте первую запись CNAME.</span><span class="sxs-lookup"><span data-stu-id="a3355-189">Create the first CNAME record.</span></span>

    <span data-ttu-id="a3355-190">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="a3355-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="a3355-191">В раскрывающемся списке выберите значение **TTL (срок жизни** ).</span><span class="sxs-lookup"><span data-stu-id="a3355-191">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="a3355-192">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="a3355-192">**Record type**</span></span>|<span data-ttu-id="a3355-193">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="a3355-193">**Host**</span></span>|<span data-ttu-id="a3355-194">**Points to** (Указывает на)</span><span class="sxs-lookup"><span data-stu-id="a3355-194">**Points to**</span></span>|<span data-ttu-id="a3355-195">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="a3355-195">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a3355-196">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="a3355-196">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="a3355-197">autodiscover</span><span class="sxs-lookup"><span data-stu-id="a3355-197">autodiscover</span></span>  <br/> |<span data-ttu-id="a3355-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a3355-198">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="a3355-199">1 час</span><span class="sxs-lookup"><span data-stu-id="a3355-199">1 hour</span></span>  <br/> |
    |<span data-ttu-id="a3355-200">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="a3355-200">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="a3355-201">sip</span><span class="sxs-lookup"><span data-stu-id="a3355-201">sip</span></span>  <br/> |<span data-ttu-id="a3355-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a3355-202">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="a3355-203">1 час</span><span class="sxs-lookup"><span data-stu-id="a3355-203">1 hour</span></span>  <br/> |
    |<span data-ttu-id="a3355-204">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="a3355-204">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="a3355-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a3355-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a3355-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a3355-206">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="a3355-207">1 час</span><span class="sxs-lookup"><span data-stu-id="a3355-207">1 hour</span></span>  <br/> |
    |<span data-ttu-id="a3355-208">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="a3355-208">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="a3355-209">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a3355-209">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a3355-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="a3355-210">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="a3355-211">1 час</span><span class="sxs-lookup"><span data-stu-id="a3355-211">1 hour</span></span>  <br/> |
    |<span data-ttu-id="a3355-212">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="a3355-212">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="a3355-213">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a3355-213">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a3355-214">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a3355-214">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="a3355-215">1 час</span><span class="sxs-lookup"><span data-stu-id="a3355-215">1 hour</span></span>  <br/> |



6. <span data-ttu-id="a3355-216">Повторите эти действия, чтобы добавить следующую запись CNAME, пока не будут созданы все шесть записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="a3355-216">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a3355-217">Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама</span><span class="sxs-lookup"><span data-stu-id="a3355-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a3355-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a3355-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3355-219">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="a3355-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a3355-220">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="a3355-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a3355-221">Если у вас уже есть запись SPF для вашего домена, не создавайте ее для Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a3355-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="a3355-222">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="a3355-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="a3355-223">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a3355-223">Follow the steps below.</span></span>

1. <span data-ttu-id="a3355-p112">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте GoDaddy по [этой ссылке](https://account.godaddy.com/products/?go_redirect=disabled). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="a3355-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy — BP — configure – 1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="a3355-227">В разделе **домены**выберите DNS в домене, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="a3355-227">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy — BP — configure – 1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="a3355-229">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="a3355-229">Select **Add**.</span></span>

    ![GoDaddy — BP — configure – 1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="a3355-231">В раскрывающемся списке выберите значение **TXT (Text)** (Текст).</span><span class="sxs-lookup"><span data-stu-id="a3355-231">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy — BP — configure – 4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="a3355-233">В поля для новой записи введите (или скопируйте и вставьте) указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="a3355-233">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="a3355-234">(Выберите значение **TTL** в раскрывающихся списках.)</span><span class="sxs-lookup"><span data-stu-id="a3355-234">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="a3355-235">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="a3355-235">**Record type**</span></span>|<span data-ttu-id="a3355-236">**Host** (Узел)</span><span class="sxs-lookup"><span data-stu-id="a3355-236">**Host**</span></span>|<span data-ttu-id="a3355-237">**TXT Value** (Значение TXT)</span><span class="sxs-lookup"><span data-stu-id="a3355-237">**TXT Value**</span></span>|<span data-ttu-id="a3355-238">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="a3355-238">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a3355-239">TXT (текст)</span><span class="sxs-lookup"><span data-stu-id="a3355-239">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="a3355-240">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a3355-240">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="a3355-241">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="a3355-241">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="a3355-242">1 час</span><span class="sxs-lookup"><span data-stu-id="a3355-242">1 hour</span></span>  <br/> |

    ![GoDaddy — BP — configure – 4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="a3355-244">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a3355-244">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="a3355-245">Добавление двух записей SRV, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a3355-245">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="a3355-246"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a3355-246"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="a3355-247">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a3355-247">Follow the steps below.</span></span>

1. <span data-ttu-id="a3355-p113">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте GoDaddy по [этой ссылке](https://account.godaddy.com/products/?go_redirect=disabled). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="a3355-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy — BP — configure – 1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="a3355-251">В разделе **домены**выберите DNS в домене, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="a3355-251">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy — BP — configure – 1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="a3355-253">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="a3355-253">Select **Add**.</span></span>

    ![GoDaddy — BP — configure – 1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="a3355-255">В раскрывающемся списке выберите значение **SRV (Service)** (Служба).</span><span class="sxs-lookup"><span data-stu-id="a3355-255">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy — BP — configure – 5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="a3355-257">Создайте первую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="a3355-257">Create the first SRV record.</span></span>

    <span data-ttu-id="a3355-258">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="a3355-258">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="a3355-259">В раскрывающихся списках выберите **тип записи** и значения **срока жизни (TTL** ).</span><span class="sxs-lookup"><span data-stu-id="a3355-259">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="a3355-260">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="a3355-260">**Record type**</span></span>|<span data-ttu-id="a3355-261">**Name** (Имя)</span><span class="sxs-lookup"><span data-stu-id="a3355-261">**Name**</span></span>|<span data-ttu-id="a3355-262">**Target** (Целевое значение)</span><span class="sxs-lookup"><span data-stu-id="a3355-262">**Target**</span></span>|<span data-ttu-id="a3355-263">**Protocol** (Протокол)</span><span class="sxs-lookup"><span data-stu-id="a3355-263">**Protocol**</span></span>|<span data-ttu-id="a3355-264">**Service** (Служба)</span><span class="sxs-lookup"><span data-stu-id="a3355-264">**Service**</span></span>|<span data-ttu-id="a3355-265">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="a3355-265">**Priority**</span></span>|<span data-ttu-id="a3355-266">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="a3355-266">**Weight**</span></span>|<span data-ttu-id="a3355-267">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="a3355-267">**Port**</span></span>|<span data-ttu-id="a3355-268">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="a3355-268">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a3355-269">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="a3355-269">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="a3355-270">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a3355-270">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="a3355-271">_tls</span><span class="sxs-lookup"><span data-stu-id="a3355-271">_tls</span></span>  <br/> |<span data-ttu-id="a3355-272">_sip</span><span class="sxs-lookup"><span data-stu-id="a3355-272">_sip</span></span>  <br/> |<span data-ttu-id="a3355-273">100</span><span class="sxs-lookup"><span data-stu-id="a3355-273">100</span></span>  <br/> |<span data-ttu-id="a3355-274">1,1</span><span class="sxs-lookup"><span data-stu-id="a3355-274">1</span></span>  <br/> |<span data-ttu-id="a3355-275">443</span><span class="sxs-lookup"><span data-stu-id="a3355-275">443</span></span>  <br/> |<span data-ttu-id="a3355-276">1 час</span><span class="sxs-lookup"><span data-stu-id="a3355-276">1 hour</span></span>  <br/> |
    |<span data-ttu-id="a3355-277">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="a3355-277">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="a3355-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a3355-278">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="a3355-279">_tcp</span><span class="sxs-lookup"><span data-stu-id="a3355-279">_tcp</span></span>  <br/> |<span data-ttu-id="a3355-280">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="a3355-280">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="a3355-281">100</span><span class="sxs-lookup"><span data-stu-id="a3355-281">100</span></span>  <br/> |<span data-ttu-id="a3355-282">1,1</span><span class="sxs-lookup"><span data-stu-id="a3355-282">1</span></span>  <br/> |<span data-ttu-id="a3355-283">5061</span><span class="sxs-lookup"><span data-stu-id="a3355-283">5061</span></span>  <br/> |<span data-ttu-id="a3355-284">1 час</span><span class="sxs-lookup"><span data-stu-id="a3355-284">1 hour</span></span>  <br/> |

    ![GoDaddy — BP — configure – 5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="a3355-286">Повторите **Шаг 5** , чтобы создать другую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="a3355-286">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="a3355-287">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a3355-287">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="a3355-p114">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a3355-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
