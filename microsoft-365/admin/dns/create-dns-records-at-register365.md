---
title: Создание записей DNS в Register365 для Microsoft
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб в Register365 для Microsoft.
ms.openlocfilehash: a0bf077a6e034add48e9745711fb37d59e2c8203
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910010"
---
# <a name="create-dns-records-at-register365-for-microsoft"></a><span data-ttu-id="09571-103">Создание записей DNS в Register365 для Microsoft</span><span class="sxs-lookup"><span data-stu-id="09571-103">Create DNS records at Register365 for Microsoft</span></span>

 <span data-ttu-id="09571-104">**[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="09571-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="09571-105">Если ваш поставщик услуг размещения DNS  Register365, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="09571-105">If Register365 is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="09571-106">Ниже перечислены основные записи, которые нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="09571-106">These are the main records to add.</span></span>  
  
- [<span data-ttu-id="09571-107">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="09571-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="09571-108">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="09571-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="09571-109">Добавление шести записей CNAME, необходимых для Корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="09571-109">Add the six CNAME records that are required for Microsoft</span></span>](#add-the-six-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="09571-110">Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="09571-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="09571-111">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="09571-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="09571-112">После добавления этих записей в Microsoft домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="09571-112">After you add these records at Microsoft, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="09571-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="09571-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="09571-116">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="09571-116">Add a TXT record for verification</span></span>
<span data-ttu-id="09571-117"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="09571-117"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="09571-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="09571-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="09571-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="09571-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="09571-p104">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register365 по [этой ссылке](https://admin.register365.com/dns/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="09571-p104">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Страница входа на панель управления](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="09571-125">На странице **Dashboard** (Панель мониторинга) найдите доменное имя, которое хотите обновить, и выберите в раскрывающемся списке пункт **DNS Settings** (Параметры DNS).</span><span class="sxs-lookup"><span data-stu-id="09571-125">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="09571-126">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="09571-126">(You may have to scroll down.)</span></span>
    
    ![Выбор параметров DNS в списке](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="09571-128">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="09571-128">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="09571-129">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="09571-129">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="09571-130">(Если необходимо добавить строку, выберите **ADD A/CNAME RECORDS (+)**.)</span><span class="sxs-lookup"><span data-stu-id="09571-130">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="09571-131">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="09571-131">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="09571-132">**Host Name (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="09571-132">**Host name**</span></span>|<span data-ttu-id="09571-133">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="09571-133">**Type**</span></span>|<span data-ttu-id="09571-134">**Result (Результат)**</span><span class="sxs-lookup"><span data-stu-id="09571-134">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="09571-135">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="09571-135">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="09571-136">TXT</span><span class="sxs-lookup"><span data-stu-id="09571-136">TXT</span></span>  <br/> |<span data-ttu-id="09571-137">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="09571-137">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="09571-138">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="09571-138">**Note:** This is an example.</span></span> <span data-ttu-id="09571-139">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="09571-139">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="09571-140">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="09571-140">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Ввод значений на странице Add/Modify DNS Zone](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. <span data-ttu-id="09571-142">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="09571-142">Select **Save**.</span></span>
    
    <span data-ttu-id="09571-143">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="09571-143">(You may have to scroll down.)</span></span>
    
    ![Нажмите Save (Сохранить)](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. <span data-ttu-id="09571-145">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="09571-145">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="09571-146">Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.</span><span class="sxs-lookup"><span data-stu-id="09571-146">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="09571-147">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="09571-147">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="09571-148">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="09571-148">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="09571-149">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="09571-149">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="09571-150">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="09571-150">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="09571-151">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="09571-151">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="09571-p106">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="09571-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="09571-155">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="09571-155">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="09571-156"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="09571-156"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="09571-p107">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register365 по [этой ссылке](https://admin.register365.com/dns/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="09571-p107">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Страница входа на панель управления](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="09571-160">На странице **Dashboard** (Панель мониторинга) найдите доменное имя, которое хотите обновить, и выберите в раскрывающемся списке пункт **DNS Settings** (Параметры DNS).</span><span class="sxs-lookup"><span data-stu-id="09571-160">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="09571-161">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="09571-161">(You may have to scroll down.)</span></span>
    
    ![Выбор параметров DNS в списке](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="09571-163">На странице **Add/Modify DNS Zone** (Добавить/изменить зону DNS) в разделе **Mail exchange records** (Записи обмена электронной почтой) в поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="09571-163">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="09571-164">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="09571-164">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="09571-165">**Host Name (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="09571-165">**Host name**</span></span>|<span data-ttu-id="09571-166">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="09571-166">**Priority**</span></span>|<span data-ttu-id="09571-167">**Result (Результат)**</span><span class="sxs-lookup"><span data-stu-id="09571-167">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="09571-168">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="09571-168">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="09571-169">1</span><span class="sxs-lookup"><span data-stu-id="09571-169">1</span></span>  <br/> <span data-ttu-id="09571-170">Дополнительные сведения о приоритете см. в статье [Что такое приоритет записей MX?](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="09571-170">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> | <span data-ttu-id="09571-171">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="09571-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="09571-172">**Примечание:** Получите вашу  *\<domain-key\>*  учетную запись Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="09571-172">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="09571-173">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="09571-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![Ввод значений на странице Add/Modify DNS Zone](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. <span data-ttu-id="09571-175">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="09571-175">Select **Save**.</span></span>
    
    <span data-ttu-id="09571-176">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="09571-176">(You may have to scroll down.)</span></span>
    
    ![Нажмите Save (Сохранить)](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. <span data-ttu-id="09571-178">Если в разделе **Mail exchange records** (Записи обмена электронной почтой) указаны какие-либо другие записи MX, удалите каждую из них, выделив ее и нажав на клавиатуре клавишу **DELETE**.</span><span class="sxs-lookup"><span data-stu-id="09571-178">If there are any other MX records in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. <span data-ttu-id="09571-180">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="09571-180">Select **Save**.</span></span>
    
    <span data-ttu-id="09571-181">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="09571-181">(You may have to scroll down.)</span></span>
    
    ![Нажмите Save (Сохранить)](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="09571-183">Добавление шести записей CNAME, необходимых для Корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="09571-183">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="09571-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="09571-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="09571-p109">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register365 по [этой ссылке](https://admin.register365.com/dns/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="09571-p109">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Страница входа на панель управления](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="09571-188">На странице **Dashboard** (Панель мониторинга) найдите доменное имя, которое хотите обновить, и выберите в раскрывающемся списке пункт **DNS Settings** (Параметры DNS).</span><span class="sxs-lookup"><span data-stu-id="09571-188">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="09571-189">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="09571-189">(You may have to scroll down.)</span></span>
    
    ![Выбор параметров DNS в списке](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="09571-191">На странице **Add/Modify DNS Zone** (Добавить/изменить зону DNS) в разделе **A, CNAME, AAAA, TXT and NS records** (Записи A, CNAME, AAAA, TXT и NS) в поля для новых записей введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="09571-191">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="09571-192">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="09571-192">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="09571-193">(Если необходимо добавить строку, выберите **ADD A/CNAME RECORDS (+)**.)</span><span class="sxs-lookup"><span data-stu-id="09571-193">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="09571-194">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="09571-194">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="09571-195">\*\*\*\*Host Name\*\* (Имя узла)\*\*</span><span class="sxs-lookup"><span data-stu-id="09571-195">\*\*\*\*Host name\*\*\*\*</span></span>|<span data-ttu-id="09571-196">\*\*\*\*Type\*\* (Тип)\*\*</span><span class="sxs-lookup"><span data-stu-id="09571-196">\*\*\*\*Type\*\*\*\*</span></span>|<span data-ttu-id="09571-197">\*\*\*\*Result\*\* (Результат)\*\*</span><span class="sxs-lookup"><span data-stu-id="09571-197">\*\*\*\*Result\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="09571-198">autodiscover</span><span class="sxs-lookup"><span data-stu-id="09571-198">autodiscover</span></span>  <br/> |<span data-ttu-id="09571-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="09571-199">CNAME</span></span>  <br/> |<span data-ttu-id="09571-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="09571-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="09571-201">sip</span><span class="sxs-lookup"><span data-stu-id="09571-201">sip</span></span>  <br/> |<span data-ttu-id="09571-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="09571-202">CNAME</span></span>  <br/> |<span data-ttu-id="09571-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="09571-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="09571-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="09571-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="09571-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="09571-205">CNAME</span></span>  <br/> |<span data-ttu-id="09571-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="09571-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="09571-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="09571-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="09571-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="09571-208">CNAME</span></span>  <br/> |<span data-ttu-id="09571-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="09571-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="09571-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="09571-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="09571-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="09571-211">CNAME</span></span>  <br/> |<span data-ttu-id="09571-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="09571-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Ввод значений на странице Add/Modify DNS Zone](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. <span data-ttu-id="09571-214">Нажмите **Save** (Сохранить).</span><span class="sxs-lookup"><span data-stu-id="09571-214">Select **Save**.</span></span>
    
    ![Нажмите Save (Сохранить)](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="09571-216">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="09571-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="09571-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="09571-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="09571-218">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="09571-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="09571-219">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="09571-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="09571-220">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="09571-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="09571-221">Вместо этого добавьте необходимые значения Microsoft в текущую  запись, чтобы у вас была одна запись SPF, которая включает оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="09571-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="09571-p111">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register365 по [этой ссылке](https://admin.register365.com/dns/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="09571-p111">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Страница входа на панель управления](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="09571-225">На странице **Dashboard** (Панель мониторинга) найдите доменное имя, которое хотите обновить, и выберите в раскрывающемся списке пункт **DNS Settings** (Параметры DNS).</span><span class="sxs-lookup"><span data-stu-id="09571-225">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="09571-226">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="09571-226">(You may have to scroll down.)</span></span>
    
    ![Выбор параметров DNS в списке](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="09571-228">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="09571-228">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="09571-229">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="09571-229">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="09571-230">(Если необходимо добавить строку, выберите **ADD A/CNAME RECORDS (+)**.)</span><span class="sxs-lookup"><span data-stu-id="09571-230">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="09571-231">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="09571-231">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="09571-232">**Host Name (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="09571-232">**Host name**</span></span>|<span data-ttu-id="09571-233">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="09571-233">**Type**</span></span>|<span data-ttu-id="09571-234">**Result (Результат)**</span><span class="sxs-lookup"><span data-stu-id="09571-234">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="09571-235">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="09571-235">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="09571-236">TXT</span><span class="sxs-lookup"><span data-stu-id="09571-236">TXT</span></span>  <br/> |<span data-ttu-id="09571-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="09571-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="09571-238">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="09571-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Ввод значений на странице Add/Modify DNS Zone](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. <span data-ttu-id="09571-240">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="09571-240">Select **Save**.</span></span>
    
    <span data-ttu-id="09571-241">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="09571-241">(You may have to scroll down.)</span></span>
    
    ![Нажмите Save (Сохранить)](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="09571-243">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="09571-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="09571-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="09571-244"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="09571-p112">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register365 по [этой ссылке](https://admin.register365.com/dns/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="09571-p112">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Страница входа на панель управления](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="09571-248">На странице **Dashboard** (Панель мониторинга) найдите доменное имя, которое хотите обновить, и выберите в раскрывающемся списке пункт **DNS Settings** (Параметры DNS).</span><span class="sxs-lookup"><span data-stu-id="09571-248">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="09571-249">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="09571-249">(You may have to scroll down.)</span></span>
    
    ![Выбор параметров DNS в списке](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="09571-251">На странице **Add/Modify DNS Zone** (Добавить/изменить зону DNS) в разделе **Service records** (Записи службы) в поля для новых записей введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="09571-251">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="09571-252">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="09571-252">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="09571-253">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="09571-253">**Name**</span></span>|<span data-ttu-id="09571-254">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="09571-254">**Priority**</span></span>|<span data-ttu-id="09571-255">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="09571-255">**Weight**</span></span>|<span data-ttu-id="09571-256">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="09571-256">**Port**</span></span>|<span data-ttu-id="09571-257">**Result (Результат)**</span><span class="sxs-lookup"><span data-stu-id="09571-257">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="09571-258">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="09571-258">_sip._tls</span></span>  <br/> |<span data-ttu-id="09571-259">100</span><span class="sxs-lookup"><span data-stu-id="09571-259">100</span></span>  <br/> |<span data-ttu-id="09571-260">1</span><span class="sxs-lookup"><span data-stu-id="09571-260">1</span></span>  <br/> |<span data-ttu-id="09571-261">443</span><span class="sxs-lookup"><span data-stu-id="09571-261">443</span></span>  <br/> |<span data-ttu-id="09571-262">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="09571-262">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="09571-263">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="09571-263">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="09571-264">100</span><span class="sxs-lookup"><span data-stu-id="09571-264">100</span></span>  <br/> |<span data-ttu-id="09571-265">1</span><span class="sxs-lookup"><span data-stu-id="09571-265">1</span></span>  <br/> |<span data-ttu-id="09571-266">5061</span><span class="sxs-lookup"><span data-stu-id="09571-266">5061</span></span>  <br/> |<span data-ttu-id="09571-267">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="09571-267">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Ввод значений в разделе Записи службы](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. <span data-ttu-id="09571-269">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="09571-269">Select **Save**.</span></span>
    
    <span data-ttu-id="09571-270">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="09571-270">(You may have to scroll down.)</span></span>
    
    ![Нажмите Save (Сохранить)](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  <span data-ttu-id="09571-p113">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="09571-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
