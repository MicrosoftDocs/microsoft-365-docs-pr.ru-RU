---
title: Создание записей DNS на сайте Register365 для Майкрософт
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу Register365 для Майкрософт.
ms.openlocfilehash: e580779ce674375564c1b3ab6123ef1b19f50be0
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400320"
---
# <a name="create-dns-records-at-register365-for-microsoft"></a><span data-ttu-id="4b31b-103">Создание записей DNS на сайте Register365 для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="4b31b-103">Create DNS records at Register365 for Microsoft</span></span>

 <span data-ttu-id="4b31b-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="4b31b-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="4b31b-105">Если ваш поставщик услуг размещения DNS  Register365, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="4b31b-105">If Register365 is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="4b31b-106">Ниже перечислены основные записи, которые нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="4b31b-106">These are the main records to add.</span></span>  
  
- [<span data-ttu-id="4b31b-107">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="4b31b-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="4b31b-108">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4b31b-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="4b31b-109">Добавление шести записей CNAME, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="4b31b-109">Add the six CNAME records that are required for Microsoft</span></span>](#add-the-six-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="4b31b-110">Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="4b31b-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="4b31b-111">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="4b31b-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="4b31b-112">Когда вы добавите эти записи в корпорацию Майкрософт, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4b31b-112">After you add these records at Microsoft, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="4b31b-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4b31b-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="4b31b-116">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="4b31b-116">Add a TXT record for verification</span></span>
<span data-ttu-id="4b31b-117"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="4b31b-117"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="4b31b-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="4b31b-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4b31b-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="4b31b-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="4b31b-p104">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register365 по [этой ссылке](https://admin.register365.com/dns/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="4b31b-p104">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Страница входа на панель управления](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="4b31b-125">На странице **Dashboard** (Панель мониторинга) найдите доменное имя, которое хотите обновить, и выберите в раскрывающемся списке пункт **DNS Settings** (Параметры DNS).</span><span class="sxs-lookup"><span data-stu-id="4b31b-125">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="4b31b-126">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="4b31b-126">(You may have to scroll down.)</span></span>
    
    ![Выбор параметров DNS в списке](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="4b31b-128">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="4b31b-128">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="4b31b-129">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="4b31b-129">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="4b31b-130">(Если необходимо добавить строку, выберите **добавить записи a/CNAME (+)**.)</span><span class="sxs-lookup"><span data-stu-id="4b31b-130">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="4b31b-131">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="4b31b-131">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="4b31b-132">**Host Name (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="4b31b-132">**Host name**</span></span>|<span data-ttu-id="4b31b-133">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="4b31b-133">**Type**</span></span>|<span data-ttu-id="4b31b-134">**Результат**</span><span class="sxs-lookup"><span data-stu-id="4b31b-134">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="4b31b-135">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="4b31b-135">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="4b31b-136">TXT</span><span class="sxs-lookup"><span data-stu-id="4b31b-136">TXT</span></span>  <br/> |<span data-ttu-id="4b31b-137">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="4b31b-137">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="4b31b-138">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="4b31b-138">**Note:** This is an example.</span></span> <span data-ttu-id="4b31b-139">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="4b31b-139">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="4b31b-140">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="4b31b-140">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Ввод значений на странице "Добавление и изменение зоны DNS"](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. <span data-ttu-id="4b31b-142">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4b31b-142">Select **Save**.</span></span>
    
    <span data-ttu-id="4b31b-143">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="4b31b-143">(You may have to scroll down.)</span></span>
    
    ![Нажмите кнопку Сохранить](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. <span data-ttu-id="4b31b-145">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="4b31b-145">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="4b31b-146">Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.</span><span class="sxs-lookup"><span data-stu-id="4b31b-146">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="4b31b-147">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="4b31b-147">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="4b31b-148">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="4b31b-148">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="4b31b-149">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="4b31b-149">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="4b31b-150">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="4b31b-150">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="4b31b-151">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="4b31b-151">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="4b31b-p106">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4b31b-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="4b31b-155">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4b31b-155">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="4b31b-156"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="4b31b-156"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="4b31b-p107">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register365 по [этой ссылке](https://admin.register365.com/dns/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="4b31b-p107">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Страница входа на панель управления](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="4b31b-160">На странице **Dashboard** (Панель мониторинга) найдите доменное имя, которое хотите обновить, и выберите в раскрывающемся списке пункт **DNS Settings** (Параметры DNS).</span><span class="sxs-lookup"><span data-stu-id="4b31b-160">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="4b31b-161">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="4b31b-161">(You may have to scroll down.)</span></span>
    
    ![Выбор параметров DNS в списке](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="4b31b-163">На странице **Add/Modify DNS Zone** (Добавить/изменить зону DNS) в разделе **Mail exchange records** (Записи обмена электронной почтой) в поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="4b31b-163">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="4b31b-164">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="4b31b-164">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="4b31b-165">**Host Name (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="4b31b-165">**Host name**</span></span>|<span data-ttu-id="4b31b-166">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="4b31b-166">**Priority**</span></span>|<span data-ttu-id="4b31b-167">**Результат**</span><span class="sxs-lookup"><span data-stu-id="4b31b-167">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="4b31b-168">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="4b31b-168">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="4b31b-169">1 </span><span class="sxs-lookup"><span data-stu-id="4b31b-169">1</span></span>  <br/> <span data-ttu-id="4b31b-170">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).   </span><span class="sxs-lookup"><span data-stu-id="4b31b-170">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="4b31b-171">*\<domain-key\>*. mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="4b31b-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="4b31b-172">**Примечание:** Получение *\<domain-key\>* учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4b31b-172">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="4b31b-173">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="4b31b-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![Ввод значений на странице "Добавление и изменение зоны DNS"](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. <span data-ttu-id="4b31b-175">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4b31b-175">Select **Save**.</span></span>
    
    <span data-ttu-id="4b31b-176">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="4b31b-176">(You may have to scroll down.)</span></span>
    
    ![Нажмите кнопку Сохранить](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. <span data-ttu-id="4b31b-178">Если в разделе **Mail exchange records** (Записи обмена электронной почтой) указаны какие-либо другие записи MX, удалите каждую из них, выделив ее и нажав на клавиатуре клавишу **DELETE**.</span><span class="sxs-lookup"><span data-stu-id="4b31b-178">If there are any other MX records in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. <span data-ttu-id="4b31b-180">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4b31b-180">Select **Save**.</span></span>
    
    <span data-ttu-id="4b31b-181">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="4b31b-181">(You may have to scroll down.)</span></span>
    
    ![Нажмите кнопку Сохранить](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="4b31b-183">Добавление шести записей CNAME, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="4b31b-183">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="4b31b-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="4b31b-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="4b31b-p109">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register365 по [этой ссылке](https://admin.register365.com/dns/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="4b31b-p109">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Страница входа на панель управления](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="4b31b-188">На странице **Dashboard** (Панель мониторинга) найдите доменное имя, которое хотите обновить, и выберите в раскрывающемся списке пункт **DNS Settings** (Параметры DNS).</span><span class="sxs-lookup"><span data-stu-id="4b31b-188">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="4b31b-189">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="4b31b-189">(You may have to scroll down.)</span></span>
    
    ![Выбор параметров DNS в списке](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="4b31b-191">На странице **Add/Modify DNS Zone** (Добавить/изменить зону DNS) в разделе **A, CNAME, AAAA, TXT and NS records** (Записи A, CNAME, AAAA, TXT и NS) в поля для новых записей введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="4b31b-191">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="4b31b-192">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="4b31b-192">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="4b31b-193">(Если необходимо добавить строку, выберите **добавить записи a/CNAME (+)**.)</span><span class="sxs-lookup"><span data-stu-id="4b31b-193">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="4b31b-194">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="4b31b-194">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="4b31b-195">\*\*\*\*Host Name\*\* (Имя узла)\*\*</span><span class="sxs-lookup"><span data-stu-id="4b31b-195">\*\*\*\*Host name\*\*\*\*</span></span>|<span data-ttu-id="4b31b-196">\*\*\*\*Type\*\* (Тип)\*\*</span><span class="sxs-lookup"><span data-stu-id="4b31b-196">\*\*\*\*Type\*\*\*\*</span></span>|<span data-ttu-id="4b31b-197">\*\*\*\*Result\*\* (Результат)\*\*</span><span class="sxs-lookup"><span data-stu-id="4b31b-197">\*\*\*\*Result\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="4b31b-198">autodiscover</span><span class="sxs-lookup"><span data-stu-id="4b31b-198">autodiscover</span></span>  <br/> |<span data-ttu-id="4b31b-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="4b31b-199">CNAME</span></span>  <br/> |<span data-ttu-id="4b31b-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="4b31b-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="4b31b-201">sip</span><span class="sxs-lookup"><span data-stu-id="4b31b-201">sip</span></span>  <br/> |<span data-ttu-id="4b31b-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="4b31b-202">CNAME</span></span>  <br/> |<span data-ttu-id="4b31b-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4b31b-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="4b31b-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="4b31b-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="4b31b-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="4b31b-205">CNAME</span></span>  <br/> |<span data-ttu-id="4b31b-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4b31b-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="4b31b-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="4b31b-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="4b31b-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="4b31b-208">CNAME</span></span>  <br/> |<span data-ttu-id="4b31b-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="4b31b-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="4b31b-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="4b31b-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="4b31b-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="4b31b-211">CNAME</span></span>  <br/> |<span data-ttu-id="4b31b-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4b31b-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Ввод значений на странице "Добавление и изменение зоны DNS"](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. <span data-ttu-id="4b31b-214">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4b31b-214">Select **Save**.</span></span>
    
    ![Нажмите кнопку Сохранить](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="4b31b-216">Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама</span><span class="sxs-lookup"><span data-stu-id="4b31b-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="4b31b-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="4b31b-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="4b31b-218">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="4b31b-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="4b31b-219">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="4b31b-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="4b31b-220">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4b31b-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="4b31b-221">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="4b31b-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="4b31b-p111">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register365 по [этой ссылке](https://admin.register365.com/dns/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="4b31b-p111">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Страница входа на панель управления](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="4b31b-225">На странице **Dashboard** (Панель мониторинга) найдите доменное имя, которое хотите обновить, и выберите в раскрывающемся списке пункт **DNS Settings** (Параметры DNS).</span><span class="sxs-lookup"><span data-stu-id="4b31b-225">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="4b31b-226">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="4b31b-226">(You may have to scroll down.)</span></span>
    
    ![Выбор параметров DNS в списке](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="4b31b-228">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="4b31b-228">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="4b31b-229">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="4b31b-229">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="4b31b-230">(Если необходимо добавить строку, выберите **добавить записи a/CNAME (+)**.)</span><span class="sxs-lookup"><span data-stu-id="4b31b-230">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="4b31b-231">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="4b31b-231">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="4b31b-232">**Host Name (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="4b31b-232">**Host name**</span></span>|<span data-ttu-id="4b31b-233">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="4b31b-233">**Type**</span></span>|<span data-ttu-id="4b31b-234">**Результат**</span><span class="sxs-lookup"><span data-stu-id="4b31b-234">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="4b31b-235">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="4b31b-235">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="4b31b-236">TXT</span><span class="sxs-lookup"><span data-stu-id="4b31b-236">TXT</span></span>  <br/> |<span data-ttu-id="4b31b-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="4b31b-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="4b31b-238">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="4b31b-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Ввод значений на странице "Добавление и изменение зоны DNS"](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. <span data-ttu-id="4b31b-240">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4b31b-240">Select **Save**.</span></span>
    
    <span data-ttu-id="4b31b-241">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="4b31b-241">(You may have to scroll down.)</span></span>
    
    ![Нажмите кнопку Сохранить](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="4b31b-243">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="4b31b-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="4b31b-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="4b31b-244"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="4b31b-p112">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register365 по [этой ссылке](https://admin.register365.com/dns/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="4b31b-p112">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Страница входа на панель управления](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="4b31b-248">На странице **Dashboard** (Панель мониторинга) найдите доменное имя, которое хотите обновить, и выберите в раскрывающемся списке пункт **DNS Settings** (Параметры DNS).</span><span class="sxs-lookup"><span data-stu-id="4b31b-248">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="4b31b-249">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="4b31b-249">(You may have to scroll down.)</span></span>
    
    ![Выбор параметров DNS в списке](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="4b31b-251">На странице **Add/Modify DNS Zone** (Добавить/изменить зону DNS) в разделе **Service records** (Записи службы) в поля для новых записей введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="4b31b-251">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="4b31b-252">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="4b31b-252">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="4b31b-253">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="4b31b-253">**Name**</span></span>|<span data-ttu-id="4b31b-254">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="4b31b-254">**Priority**</span></span>|<span data-ttu-id="4b31b-255">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="4b31b-255">**Weight**</span></span>|<span data-ttu-id="4b31b-256">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="4b31b-256">**Port**</span></span>|<span data-ttu-id="4b31b-257">**Result (Результат)**</span><span class="sxs-lookup"><span data-stu-id="4b31b-257">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4b31b-258">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="4b31b-258">_sip._tls</span></span>  <br/> |<span data-ttu-id="4b31b-259">100</span><span class="sxs-lookup"><span data-stu-id="4b31b-259">100</span></span>  <br/> |<span data-ttu-id="4b31b-260">1 </span><span class="sxs-lookup"><span data-stu-id="4b31b-260">1</span></span>  <br/> |<span data-ttu-id="4b31b-261">443</span><span class="sxs-lookup"><span data-stu-id="4b31b-261">443</span></span>  <br/> |<span data-ttu-id="4b31b-262">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4b31b-262">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="4b31b-263">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="4b31b-263">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="4b31b-264">100</span><span class="sxs-lookup"><span data-stu-id="4b31b-264">100</span></span>  <br/> |<span data-ttu-id="4b31b-265">1 </span><span class="sxs-lookup"><span data-stu-id="4b31b-265">1</span></span>  <br/> |<span data-ttu-id="4b31b-266">5061</span><span class="sxs-lookup"><span data-stu-id="4b31b-266">5061</span></span>  <br/> |<span data-ttu-id="4b31b-267">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4b31b-267">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Ввод значений в раздел "записи службы"](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. <span data-ttu-id="4b31b-269">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4b31b-269">Select **Save**.</span></span>
    
    <span data-ttu-id="4b31b-270">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="4b31b-270">(You may have to scroll down.)</span></span>
    
    ![Нажмите кнопку Сохранить](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  <span data-ttu-id="4b31b-p113">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4b31b-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
