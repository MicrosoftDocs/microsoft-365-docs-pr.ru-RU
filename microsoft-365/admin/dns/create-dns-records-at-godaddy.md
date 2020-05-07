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
ms.openlocfilehash: b1c5539af6683bbf8f94fd15880fb870caf31342
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049027"
---
# <a name="create-dns-records-at-godaddy-for-microsoft"></a><span data-ttu-id="88b72-103">Создание записей DNS на сайте GoDaddy для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="88b72-103">Create DNS records at GoDaddy for Microsoft</span></span>

 <span data-ttu-id="88b72-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="88b72-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="88b72-105">Если ваш поставщик услуг размещения DNS  GoDaddy, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="88b72-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="88b72-106">Когда вы добавите эти записи на сайте GoDaddy, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="88b72-106">After you add these records at GoDaddy, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="88b72-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="88b72-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="88b72-110">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="88b72-110">Add a TXT record for verification</span></span>
<span data-ttu-id="88b72-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="88b72-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="88b72-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="88b72-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="88b72-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="88b72-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="88b72-116">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="88b72-116">Follow the steps below.</span></span>

1. <span data-ttu-id="88b72-p104">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте GoDaddy по [этой ссылке](https://account.godaddy.com/products/?go_redirect=disabled). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="88b72-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy — BP — configure – 1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="88b72-120">В разделе **домены**выберите DNS в домене, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="88b72-120">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy — BP — configure – 1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="88b72-122">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="88b72-122">Select **Add**.</span></span>

    ![GoDaddy — BP — configure – 1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="88b72-124">В раскрывающемся списке выберите значение **TXT (Text)** (Текст).</span><span class="sxs-lookup"><span data-stu-id="88b72-124">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="88b72-125">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="88b72-125">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="88b72-126">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="88b72-126">**Record type**</span></span> |<span data-ttu-id="88b72-127">**Host** (Узел)</span><span class="sxs-lookup"><span data-stu-id="88b72-127">**Host**</span></span>|<span data-ttu-id="88b72-128">**TXT Value** (Значение TXT)</span><span class="sxs-lookup"><span data-stu-id="88b72-128">**TXT Value**</span></span>|<span data-ttu-id="88b72-129">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="88b72-129">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="88b72-130">TXT (текст)</span><span class="sxs-lookup"><span data-stu-id="88b72-130">TXT (Text)</span></span>|@|<span data-ttu-id="88b72-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="88b72-131">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="88b72-132">**Примечание**: это пример.</span><span class="sxs-lookup"><span data-stu-id="88b72-132">**Note**: This is an example.</span></span> <span data-ttu-id="88b72-133">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="88b72-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="88b72-134">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="88b72-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="88b72-135">1 час</span><span class="sxs-lookup"><span data-stu-id="88b72-135">1 hour</span></span>  <br><span data-ttu-id="88b72-136">(Выберите значение из раскрывающегося списка.)</span><span class="sxs-lookup"><span data-stu-id="88b72-136">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy — BP — Verify – 1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="88b72-138">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="88b72-138">Select **Save**.</span></span>

6. <span data-ttu-id="88b72-139">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="88b72-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="88b72-140">Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.</span><span class="sxs-lookup"><span data-stu-id="88b72-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>

<span data-ttu-id="88b72-141">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="88b72-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="88b72-142">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="88b72-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="88b72-143">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="88b72-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="88b72-144">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="88b72-144">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="88b72-145">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="88b72-145">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="88b72-p107">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="88b72-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="88b72-149">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="88b72-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="88b72-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="88b72-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="88b72-151">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="88b72-151">Follow the steps below.</span></span>

1. <span data-ttu-id="88b72-p108">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте GoDaddy по [этой ссылке](https://account.godaddy.com/products/?go_redirect=disabled). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="88b72-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy — BP — configure – 1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="88b72-155">В разделе **домены**выберите DNS в домене, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="88b72-155">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy — BP — configure – 1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="88b72-157">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="88b72-157">Select **Add**.</span></span>

    ![GoDaddy — BP — configure – 1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="88b72-159">В раскрывающемся списке выберите значение **MX (Mail Exchanger)** (почтовый обменник).</span><span class="sxs-lookup"><span data-stu-id="88b72-159">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy — BP — configure – 2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="88b72-161">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="88b72-161">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="88b72-162">В раскрывающемся списке выберите значение **TTL (срок жизни** ).</span><span class="sxs-lookup"><span data-stu-id="88b72-162">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="88b72-163">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="88b72-163">**Record type**</span></span>|<span data-ttu-id="88b72-164">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="88b72-164">**Host**</span></span>|<span data-ttu-id="88b72-165">**Points to** (Указывает на)</span><span class="sxs-lookup"><span data-stu-id="88b72-165">**Points to**</span></span>|<span data-ttu-id="88b72-166">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="88b72-166">**Priority**</span></span>|<span data-ttu-id="88b72-167">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="88b72-167">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="88b72-168">MX (Mail Exchanger) (Почтовый обменник)</span><span class="sxs-lookup"><span data-stu-id="88b72-168">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="88b72-169">*\<ключ_домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="88b72-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="88b72-170">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="88b72-170">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="88b72-171">Где это находится?</span><span class="sxs-lookup"><span data-stu-id="88b72-171">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="88b72-172">10 </span><span class="sxs-lookup"><span data-stu-id="88b72-172">10</span></span>  <br/> <span data-ttu-id="88b72-173">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).   </span><span class="sxs-lookup"><span data-stu-id="88b72-173">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="88b72-174">1 час</span><span class="sxs-lookup"><span data-stu-id="88b72-174">1 hour</span></span>  <br/> |

6. <span data-ttu-id="88b72-175">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="88b72-175">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="88b72-176">Добавление записей CNAME, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="88b72-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="88b72-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="88b72-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="88b72-178">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="88b72-178">Follow the steps below.</span></span>

1. <span data-ttu-id="88b72-p110">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте GoDaddy по [этой ссылке](https://account.godaddy.com/products/?go_redirect=disabled). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="88b72-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy — BP — configure – 1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="88b72-182">В разделе **домены**выберите DNS в домене, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="88b72-182">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy — BP — configure – 1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="88b72-184">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="88b72-184">Select **Add**.</span></span>

    ![GoDaddy — BP — configure – 1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="88b72-186">В раскрывающемся списке выберите значение **CNAME (Alias)** (Псевдоним CNAME).</span><span class="sxs-lookup"><span data-stu-id="88b72-186">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy — BP — configure – 3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="88b72-188">Создайте первую запись CNAME.</span><span class="sxs-lookup"><span data-stu-id="88b72-188">Create the first CNAME record.</span></span>

    <span data-ttu-id="88b72-189">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="88b72-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="88b72-190">В раскрывающемся списке выберите значение **TTL (срок жизни** ).</span><span class="sxs-lookup"><span data-stu-id="88b72-190">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="88b72-191">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="88b72-191">**Record type**</span></span>|<span data-ttu-id="88b72-192">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="88b72-192">**Host**</span></span>|<span data-ttu-id="88b72-193">**Points to** (Указывает на)</span><span class="sxs-lookup"><span data-stu-id="88b72-193">**Points to**</span></span>|<span data-ttu-id="88b72-194">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="88b72-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="88b72-195">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="88b72-195">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="88b72-196">autodiscover</span><span class="sxs-lookup"><span data-stu-id="88b72-196">autodiscover</span></span>  <br/> |<span data-ttu-id="88b72-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="88b72-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="88b72-198">1 час</span><span class="sxs-lookup"><span data-stu-id="88b72-198">1 hour</span></span>  <br/> |
    |<span data-ttu-id="88b72-199">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="88b72-199">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="88b72-200">sip</span><span class="sxs-lookup"><span data-stu-id="88b72-200">sip</span></span>  <br/> |<span data-ttu-id="88b72-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="88b72-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="88b72-202">1 час</span><span class="sxs-lookup"><span data-stu-id="88b72-202">1 hour</span></span>  <br/> |
    |<span data-ttu-id="88b72-203">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="88b72-203">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="88b72-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="88b72-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="88b72-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="88b72-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="88b72-206">1 час</span><span class="sxs-lookup"><span data-stu-id="88b72-206">1 hour</span></span>  <br/> |
    |<span data-ttu-id="88b72-207">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="88b72-207">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="88b72-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="88b72-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="88b72-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="88b72-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="88b72-210">1 час</span><span class="sxs-lookup"><span data-stu-id="88b72-210">1 hour</span></span>  <br/> |
    |<span data-ttu-id="88b72-211">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="88b72-211">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="88b72-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="88b72-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="88b72-213">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="88b72-213">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="88b72-214">1 час</span><span class="sxs-lookup"><span data-stu-id="88b72-214">1 hour</span></span>  <br/> |



6. <span data-ttu-id="88b72-215">Повторите эти действия, чтобы добавить следующую запись CNAME, пока не будут созданы все шесть записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="88b72-215">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="88b72-216">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="88b72-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="88b72-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="88b72-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="88b72-218">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="88b72-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="88b72-219">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="88b72-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="88b72-220">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="88b72-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="88b72-221">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="88b72-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="88b72-222">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="88b72-222">Follow the steps below.</span></span>

1. <span data-ttu-id="88b72-p112">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте GoDaddy по [этой ссылке](https://account.godaddy.com/products/?go_redirect=disabled). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="88b72-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy — BP — configure – 1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="88b72-226">В разделе **домены**выберите DNS в домене, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="88b72-226">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy — BP — configure – 1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="88b72-228">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="88b72-228">Select **Add**.</span></span>

    ![GoDaddy — BP — configure – 1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="88b72-230">В раскрывающемся списке выберите значение **TXT (Text)** (Текст).</span><span class="sxs-lookup"><span data-stu-id="88b72-230">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy — BP — configure – 4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="88b72-232">В поля для новой записи введите (или скопируйте и вставьте) указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="88b72-232">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="88b72-233">(Выберите значение **TTL** в раскрывающихся списках.)</span><span class="sxs-lookup"><span data-stu-id="88b72-233">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="88b72-234">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="88b72-234">**Record type**</span></span>|<span data-ttu-id="88b72-235">**Host** (Узел)</span><span class="sxs-lookup"><span data-stu-id="88b72-235">**Host**</span></span>|<span data-ttu-id="88b72-236">**TXT Value** (Значение TXT)</span><span class="sxs-lookup"><span data-stu-id="88b72-236">**TXT Value**</span></span>|<span data-ttu-id="88b72-237">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="88b72-237">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="88b72-238">TXT (текст)</span><span class="sxs-lookup"><span data-stu-id="88b72-238">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="88b72-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="88b72-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="88b72-240">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="88b72-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="88b72-241">1 час</span><span class="sxs-lookup"><span data-stu-id="88b72-241">1 hour</span></span>  <br/> |

    ![GoDaddy — BP — configure – 4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="88b72-243">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="88b72-243">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="88b72-244">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="88b72-244">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="88b72-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="88b72-245"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="88b72-246">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="88b72-246">Follow the steps below.</span></span>

1. <span data-ttu-id="88b72-p113">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте GoDaddy по [этой ссылке](https://account.godaddy.com/products/?go_redirect=disabled). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="88b72-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy — BP — configure – 1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="88b72-250">В разделе **домены**выберите DNS в домене, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="88b72-250">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy — BP — configure – 1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="88b72-252">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="88b72-252">Select **Add**.</span></span>

    ![GoDaddy — BP — configure – 1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="88b72-254">В раскрывающемся списке выберите значение **SRV (Service)** (Служба).</span><span class="sxs-lookup"><span data-stu-id="88b72-254">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy — BP — configure – 5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="88b72-256">Создайте первую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="88b72-256">Create the first SRV record.</span></span>

    <span data-ttu-id="88b72-257">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="88b72-257">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="88b72-258">В раскрывающихся списках выберите **тип записи** и значения **срока жизни (TTL** ).</span><span class="sxs-lookup"><span data-stu-id="88b72-258">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="88b72-259">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="88b72-259">**Record type**</span></span>|<span data-ttu-id="88b72-260">**Name** (Имя)</span><span class="sxs-lookup"><span data-stu-id="88b72-260">**Name**</span></span>|<span data-ttu-id="88b72-261">**Target** (Целевое значение)</span><span class="sxs-lookup"><span data-stu-id="88b72-261">**Target**</span></span>|<span data-ttu-id="88b72-262">**Protocol** (Протокол)</span><span class="sxs-lookup"><span data-stu-id="88b72-262">**Protocol**</span></span>|<span data-ttu-id="88b72-263">**Service** (Служба)</span><span class="sxs-lookup"><span data-stu-id="88b72-263">**Service**</span></span>|<span data-ttu-id="88b72-264">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="88b72-264">**Priority**</span></span>|<span data-ttu-id="88b72-265">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="88b72-265">**Weight**</span></span>|<span data-ttu-id="88b72-266">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="88b72-266">**Port**</span></span>|<span data-ttu-id="88b72-267">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="88b72-267">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="88b72-268">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="88b72-268">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="88b72-269">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="88b72-269">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="88b72-270">_tls</span><span class="sxs-lookup"><span data-stu-id="88b72-270">_tls</span></span>  <br/> |<span data-ttu-id="88b72-271">_sip</span><span class="sxs-lookup"><span data-stu-id="88b72-271">_sip</span></span>  <br/> |<span data-ttu-id="88b72-272">100</span><span class="sxs-lookup"><span data-stu-id="88b72-272">100</span></span>  <br/> |<span data-ttu-id="88b72-273">1,1</span><span class="sxs-lookup"><span data-stu-id="88b72-273">1</span></span>  <br/> |<span data-ttu-id="88b72-274">443</span><span class="sxs-lookup"><span data-stu-id="88b72-274">443</span></span>  <br/> |<span data-ttu-id="88b72-275">1 час</span><span class="sxs-lookup"><span data-stu-id="88b72-275">1 hour</span></span>  <br/> |
    |<span data-ttu-id="88b72-276">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="88b72-276">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="88b72-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="88b72-277">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="88b72-278">_tcp</span><span class="sxs-lookup"><span data-stu-id="88b72-278">_tcp</span></span>  <br/> |<span data-ttu-id="88b72-279">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="88b72-279">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="88b72-280">100</span><span class="sxs-lookup"><span data-stu-id="88b72-280">100</span></span>  <br/> |<span data-ttu-id="88b72-281">1,1</span><span class="sxs-lookup"><span data-stu-id="88b72-281">1</span></span>  <br/> |<span data-ttu-id="88b72-282">5061</span><span class="sxs-lookup"><span data-stu-id="88b72-282">5061</span></span>  <br/> |<span data-ttu-id="88b72-283">1 час</span><span class="sxs-lookup"><span data-stu-id="88b72-283">1 hour</span></span>  <br/> |

    ![GoDaddy — BP — configure – 5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="88b72-285">Повторите **Шаг 5** , чтобы создать другую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="88b72-285">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="88b72-286">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="88b72-286">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="88b72-p114">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="88b72-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
