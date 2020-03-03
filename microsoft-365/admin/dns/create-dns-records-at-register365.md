---
title: Создание записей DNS для Office 365 на сайте Register365
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу Register365 для Office 365.
ms.openlocfilehash: 7f9398e14ea5280948829b263d4cd66d61fab682
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362854"
---
# <a name="create-dns-records-at-register365-for-office-365"></a><span data-ttu-id="30bc9-103">Создание записей DNS для Office 365 на сайте Register365</span><span class="sxs-lookup"><span data-stu-id="30bc9-103">Create DNS records at Register365 for Office 365</span></span>

 <span data-ttu-id="30bc9-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="30bc9-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="30bc9-105">Если ваш поставщик услуг размещения DNS  Register365, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="30bc9-105">If Register365 is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="30bc9-106">Ниже перечислены основные записи, которые нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="30bc9-106">These are the main records to add.</span></span>  
  
- [<span data-ttu-id="30bc9-107">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="30bc9-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="30bc9-108">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в Office 365.</span><span class="sxs-lookup"><span data-stu-id="30bc9-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="30bc9-109">Добавление шести записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="30bc9-109">Add the six CNAME records that are required for Office 365</span></span>](#add-the-six-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="30bc9-110">Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="30bc9-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="30bc9-111">Добавление двух записей SRV, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="30bc9-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="30bc9-112">Когда вы добавите эти записи на сайте Office 365, ваш домен будет настроен для работы со службами Office 365.</span><span class="sxs-lookup"><span data-stu-id="30bc9-112">After you add these records at Office 365, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="30bc9-113">Дополнительные сведения о веб-хостинге и DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="30bc9-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="30bc9-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="30bc9-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="30bc9-117">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="30bc9-117">Add a TXT record for verification</span></span>
<span data-ttu-id="30bc9-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="30bc9-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="30bc9-p102">Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="30bc9-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="30bc9-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="30bc9-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="30bc9-p104">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register365 по [этой ссылке](https://admin.register365.com/dns/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="30bc9-p104">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Страница входа на панель управления](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="30bc9-126">На странице **Dashboard** (Панель мониторинга) найдите доменное имя, которое хотите обновить, и выберите в раскрывающемся списке пункт **DNS Settings** (Параметры DNS).</span><span class="sxs-lookup"><span data-stu-id="30bc9-126">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="30bc9-127">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="30bc9-127">(You may have to scroll down.)</span></span>
    
    ![Выбор параметров DNS в списке](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="30bc9-129">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="30bc9-129">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="30bc9-130">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="30bc9-130">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="30bc9-131">(Если необходимо добавить строку, выберите **добавить записи a/CNAME (+)**.)</span><span class="sxs-lookup"><span data-stu-id="30bc9-131">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="30bc9-132">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="30bc9-132">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="30bc9-133">**Host Name (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="30bc9-133">**Host name**</span></span>|<span data-ttu-id="30bc9-134">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="30bc9-134">**Type**</span></span>|<span data-ttu-id="30bc9-135">**Результат**</span><span class="sxs-lookup"><span data-stu-id="30bc9-135">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="30bc9-136">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="30bc9-136">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="30bc9-137">TXT</span><span class="sxs-lookup"><span data-stu-id="30bc9-137">TXT</span></span>  <br/> |<span data-ttu-id="30bc9-138">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="30bc9-138">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="30bc9-p105">**Примечание.** Это пример. Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.           [Где это находится?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="30bc9-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![Ввод значений на странице "Добавление и изменение зоны DNS"](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. <span data-ttu-id="30bc9-143">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="30bc9-143">Select **Save**.</span></span>
    
    <span data-ttu-id="30bc9-144">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="30bc9-144">(You may have to scroll down.)</span></span>
    
    ![Нажмите кнопку Сохранить](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. <span data-ttu-id="30bc9-146">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="30bc9-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="30bc9-147">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Office 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="30bc9-147">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="30bc9-148">Если Office 365 обнаружит правильную запись TXT, это значит, что домен проверен.</span><span class="sxs-lookup"><span data-stu-id="30bc9-148">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="30bc9-149">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="30bc9-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="30bc9-150">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="30bc9-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="30bc9-151">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="30bc9-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="30bc9-152">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="30bc9-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="30bc9-p106">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="30bc9-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="30bc9-156">Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="30bc9-156">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="30bc9-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="30bc9-157"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="30bc9-p107">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register365 по [этой ссылке](https://admin.register365.com/dns/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="30bc9-p107">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Страница входа на панель управления](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="30bc9-161">На странице **Dashboard** (Панель мониторинга) найдите доменное имя, которое хотите обновить, и выберите в раскрывающемся списке пункт **DNS Settings** (Параметры DNS).</span><span class="sxs-lookup"><span data-stu-id="30bc9-161">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="30bc9-162">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="30bc9-162">(You may have to scroll down.)</span></span>
    
    ![Выбор параметров DNS в списке](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="30bc9-164">На странице **Add/Modify DNS Zone** (Добавить/изменить зону DNS) в разделе **Mail exchange records** (Записи обмена электронной почтой) в поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="30bc9-164">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="30bc9-165">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="30bc9-165">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="30bc9-166">**Host Name (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="30bc9-166">**Host name**</span></span>|<span data-ttu-id="30bc9-167">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="30bc9-167">**Priority**</span></span>|<span data-ttu-id="30bc9-168">**Результат**</span><span class="sxs-lookup"><span data-stu-id="30bc9-168">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="30bc9-169">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="30bc9-169">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="30bc9-170">1,1</span><span class="sxs-lookup"><span data-stu-id="30bc9-170">1</span></span>  <br/> <span data-ttu-id="30bc9-171">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="30bc9-171">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="30bc9-172">*\<ключ_домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="30bc9-172">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="30bc9-173">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Office 365.</span><span class="sxs-lookup"><span data-stu-id="30bc9-173">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="30bc9-174">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="30bc9-174">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![Ввод значений на странице "Добавление и изменение зоны DNS"](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. <span data-ttu-id="30bc9-176">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="30bc9-176">Select **Save**.</span></span>
    
    <span data-ttu-id="30bc9-177">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="30bc9-177">(You may have to scroll down.)</span></span>
    
    ![Нажмите кнопку Сохранить](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. <span data-ttu-id="30bc9-179">Если в разделе **Mail exchange records** (Записи обмена электронной почтой) указаны какие-либо другие записи MX, удалите каждую из них, выделив ее и нажав на клавиатуре клавишу **DELETE**.</span><span class="sxs-lookup"><span data-stu-id="30bc9-179">If there are any other MX records in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. <span data-ttu-id="30bc9-181">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="30bc9-181">Select **Save**.</span></span>
    
    <span data-ttu-id="30bc9-182">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="30bc9-182">(You may have to scroll down.)</span></span>
    
    ![Нажмите кнопку Сохранить](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="30bc9-184">Добавление шести записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="30bc9-184">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="30bc9-185"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="30bc9-185"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="30bc9-p109">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register365 по [этой ссылке](https://admin.register365.com/dns/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="30bc9-p109">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Страница входа на панель управления](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="30bc9-189">На странице **Dashboard** (Панель мониторинга) найдите доменное имя, которое хотите обновить, и выберите в раскрывающемся списке пункт **DNS Settings** (Параметры DNS).</span><span class="sxs-lookup"><span data-stu-id="30bc9-189">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="30bc9-190">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="30bc9-190">(You may have to scroll down.)</span></span>
    
    ![Выбор параметров DNS в списке](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="30bc9-192">На странице **Add/Modify DNS Zone** (Добавить/изменить зону DNS) в разделе **A, CNAME, AAAA, TXT and NS records** (Записи A, CNAME, AAAA, TXT и NS) в поля для новых записей введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="30bc9-192">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="30bc9-193">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="30bc9-193">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="30bc9-194">(Если необходимо добавить строку, выберите **добавить записи a/CNAME (+)**.)</span><span class="sxs-lookup"><span data-stu-id="30bc9-194">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="30bc9-195">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="30bc9-195">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="30bc9-196">\*\*\*\*Host Name\*\* (Имя узла)\*\*</span><span class="sxs-lookup"><span data-stu-id="30bc9-196">\*\*\*\*Host name\*\*\*\*</span></span>|<span data-ttu-id="30bc9-197">\*\*\*\*Type\*\* (Тип)\*\*</span><span class="sxs-lookup"><span data-stu-id="30bc9-197">\*\*\*\*Type\*\*\*\*</span></span>|<span data-ttu-id="30bc9-198">\*\*\*\*Result\*\* (Результат)\*\*</span><span class="sxs-lookup"><span data-stu-id="30bc9-198">\*\*\*\*Result\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="30bc9-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="30bc9-199">autodiscover</span></span>  <br/> |<span data-ttu-id="30bc9-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="30bc9-200">CNAME</span></span>  <br/> |<span data-ttu-id="30bc9-201">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="30bc9-201">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="30bc9-202">sip</span><span class="sxs-lookup"><span data-stu-id="30bc9-202">sip</span></span>  <br/> |<span data-ttu-id="30bc9-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="30bc9-203">CNAME</span></span>  <br/> |<span data-ttu-id="30bc9-204">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="30bc9-204">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="30bc9-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="30bc9-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="30bc9-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="30bc9-206">CNAME</span></span>  <br/> |<span data-ttu-id="30bc9-207">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="30bc9-207">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="30bc9-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="30bc9-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="30bc9-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="30bc9-209">CNAME</span></span>  <br/> |<span data-ttu-id="30bc9-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="30bc9-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="30bc9-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="30bc9-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="30bc9-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="30bc9-212">CNAME</span></span>  <br/> |<span data-ttu-id="30bc9-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="30bc9-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Ввод значений на странице "Добавление и изменение зоны DNS"](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. <span data-ttu-id="30bc9-215">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="30bc9-215">Select **Save**.</span></span>
    
    ![Нажмите кнопку Сохранить](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="30bc9-217">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="30bc9-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="30bc9-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="30bc9-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="30bc9-219">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="30bc9-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="30bc9-220">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="30bc9-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="30bc9-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="30bc9-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="30bc9-222">Вместо этого добавьте необходимые значения Office 365 в текущую запись. Таким образом, в *одной* записи SPF будут указаны оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="30bc9-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="30bc9-p111">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register365 по [этой ссылке](https://admin.register365.com/dns/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="30bc9-p111">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Страница входа на панель управления](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="30bc9-226">На странице **Dashboard** (Панель мониторинга) найдите доменное имя, которое хотите обновить, и выберите в раскрывающемся списке пункт **DNS Settings** (Параметры DNS).</span><span class="sxs-lookup"><span data-stu-id="30bc9-226">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="30bc9-227">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="30bc9-227">(You may have to scroll down.)</span></span>
    
    ![Выбор параметров DNS в списке](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="30bc9-229">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="30bc9-229">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="30bc9-230">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="30bc9-230">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="30bc9-231">(Если необходимо добавить строку, выберите **добавить записи a/CNAME (+)**.)</span><span class="sxs-lookup"><span data-stu-id="30bc9-231">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="30bc9-232">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="30bc9-232">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="30bc9-233">**Host Name (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="30bc9-233">**Host name**</span></span>|<span data-ttu-id="30bc9-234">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="30bc9-234">**Type**</span></span>|<span data-ttu-id="30bc9-235">**Результат**</span><span class="sxs-lookup"><span data-stu-id="30bc9-235">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="30bc9-236">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="30bc9-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="30bc9-237">TXT</span><span class="sxs-lookup"><span data-stu-id="30bc9-237">TXT</span></span>  <br/> |<span data-ttu-id="30bc9-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="30bc9-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="30bc9-239">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="30bc9-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Ввод значений на странице "Добавление и изменение зоны DNS"](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. <span data-ttu-id="30bc9-241">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="30bc9-241">Select **Save**.</span></span>
    
    <span data-ttu-id="30bc9-242">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="30bc9-242">(You may have to scroll down.)</span></span>
    
    ![Нажмите кнопку Сохранить](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="30bc9-244">Добавление двух записей SRV, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="30bc9-244">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="30bc9-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="30bc9-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="30bc9-p112">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register365 по [этой ссылке](https://admin.register365.com/dns/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="30bc9-p112">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Страница входа на панель управления](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="30bc9-249">На странице **Dashboard** (Панель мониторинга) найдите доменное имя, которое хотите обновить, и выберите в раскрывающемся списке пункт **DNS Settings** (Параметры DNS).</span><span class="sxs-lookup"><span data-stu-id="30bc9-249">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="30bc9-250">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="30bc9-250">(You may have to scroll down.)</span></span>
    
    ![Выбор параметров DNS в списке](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="30bc9-252">На странице **Add/Modify DNS Zone** (Добавить/изменить зону DNS) в разделе **Service records** (Записи службы) в поля для новых записей введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="30bc9-252">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="30bc9-253">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="30bc9-253">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="30bc9-254">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="30bc9-254">**Name**</span></span>|<span data-ttu-id="30bc9-255">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="30bc9-255">**Priority**</span></span>|<span data-ttu-id="30bc9-256">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="30bc9-256">**Weight**</span></span>|<span data-ttu-id="30bc9-257">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="30bc9-257">**Port**</span></span>|<span data-ttu-id="30bc9-258">**Result (Результат)**</span><span class="sxs-lookup"><span data-stu-id="30bc9-258">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="30bc9-259">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="30bc9-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="30bc9-260">100</span><span class="sxs-lookup"><span data-stu-id="30bc9-260">100</span></span>  <br/> |<span data-ttu-id="30bc9-261">1,1</span><span class="sxs-lookup"><span data-stu-id="30bc9-261">1</span></span>  <br/> |<span data-ttu-id="30bc9-262">443</span><span class="sxs-lookup"><span data-stu-id="30bc9-262">443</span></span>  <br/> |<span data-ttu-id="30bc9-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="30bc9-263">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="30bc9-264">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="30bc9-264">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="30bc9-265">100</span><span class="sxs-lookup"><span data-stu-id="30bc9-265">100</span></span>  <br/> |<span data-ttu-id="30bc9-266">1,1</span><span class="sxs-lookup"><span data-stu-id="30bc9-266">1</span></span>  <br/> |<span data-ttu-id="30bc9-267">5061</span><span class="sxs-lookup"><span data-stu-id="30bc9-267">5061</span></span>  <br/> |<span data-ttu-id="30bc9-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="30bc9-268">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Ввод значений в раздел "записи службы"](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. <span data-ttu-id="30bc9-270">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="30bc9-270">Select **Save**.</span></span>
    
    <span data-ttu-id="30bc9-271">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="30bc9-271">(You may have to scroll down.)</span></span>
    
    ![Нажмите кнопку Сохранить](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  <span data-ttu-id="30bc9-p113">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="30bc9-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
