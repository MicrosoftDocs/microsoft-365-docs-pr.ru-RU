---
title: Создание записей DNS для Office 365 на сайте Bluehost
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу Bluehost для Office 365.
ms.openlocfilehash: 0e64ed8787dca9822e71a63c57de7a7a3e2b3fe4
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2020
ms.locfileid: "42350960"
---
# <a name="create-dns-records-at-bluehost-for-office-365"></a><span data-ttu-id="579d3-103">Создание записей DNS для Office 365 на сайте Bluehost</span><span class="sxs-lookup"><span data-stu-id="579d3-103">Create DNS records at Bluehost for Office 365</span></span>

 <span data-ttu-id="579d3-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="579d3-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="579d3-105">Если ваш поставщик услуг размещения DNS  Bluehost, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="579d3-105">If Bluehost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="579d3-106">Когда вы добавите эти записи на сайте Bluehost, ваш домен будет настроен для работы со службами Office 365.</span><span class="sxs-lookup"><span data-stu-id="579d3-106">After you add these records at Bluehost, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="579d3-107">Дополнительные сведения о веб-хостинге и DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="579d3-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="579d3-p101">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="579d3-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="579d3-111">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="579d3-111">Add a TXT record for verification</span></span>
<span data-ttu-id="579d3-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="579d3-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="579d3-p102">Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="579d3-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="579d3-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="579d3-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="579d3-117">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Bluehost по [этой ссылке](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="579d3-117">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="579d3-118">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="579d3-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="579d3-119">На странице **доменов** в области **домена** установите флажок домена, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="579d3-119">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="579d3-120">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="579d3-120">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="579d3-121">В области ***domain_name*** в строке **Редактор зоны DNS** выберите **Управление записями DNS**.</span><span class="sxs-lookup"><span data-stu-id="579d3-121">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="579d3-122">На странице \* \* редактор \*\*зоны DNS \*\*\* \* в поля для новой записи введите (или скопируйте и вставьте) значения из приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="579d3-122">On the \*\* DNS Zone Editor \*\* page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="579d3-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="579d3-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="579d3-124">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="579d3-124">**Host Record**</span></span> <br/> |<span data-ttu-id="579d3-125">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="579d3-125">**TTL**</span></span> <br/> |<span data-ttu-id="579d3-126">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="579d3-126">**Type**</span></span> <br/> |<span data-ttu-id="579d3-127">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="579d3-127">**TXT Value**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="579d3-128">14400</span><span class="sxs-lookup"><span data-stu-id="579d3-128">14400</span></span>  <br/> |<span data-ttu-id="579d3-129">TXT</span><span class="sxs-lookup"><span data-stu-id="579d3-129">TXT</span></span>  <br/> |<span data-ttu-id="579d3-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="579d3-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="579d3-131">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="579d3-131">**Note:** This is an example.</span></span> <span data-ttu-id="579d3-132">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="579d3-132">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="579d3-133">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="579d3-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
5. <span data-ttu-id="579d3-134">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="579d3-134">Select **add record**.</span></span>
    
6. <span data-ttu-id="579d3-135">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="579d3-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="579d3-136">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Office 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="579d3-136">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="579d3-137">Если Office 365 обнаружит правильную запись TXT, это значит, что домен проверен.</span><span class="sxs-lookup"><span data-stu-id="579d3-137">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="579d3-138">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="579d3-138">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="579d3-139">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="579d3-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="579d3-140">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="579d3-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="579d3-141">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="579d3-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="579d3-p106">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="579d3-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="579d3-145">Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="579d3-145">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="579d3-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="579d3-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="579d3-147">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Bluehost по [этой ссылке](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="579d3-147">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="579d3-148">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="579d3-148">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="579d3-149">На странице **доменов** в области **домена** установите флажок домена, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="579d3-149">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="579d3-150">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="579d3-150">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="579d3-151">В области ***domain_name*** в строке **Редактор зоны DNS** выберите **Управление записями DNS**.</span><span class="sxs-lookup"><span data-stu-id="579d3-151">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="579d3-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="579d3-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="579d3-153">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="579d3-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="579d3-154">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="579d3-154">**Host Record**</span></span>|<span data-ttu-id="579d3-155">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="579d3-155">**TTL**</span></span>|<span data-ttu-id="579d3-156">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="579d3-156">**Type**</span></span>|<span data-ttu-id="579d3-157">**Points To (Указывает на)**</span><span class="sxs-lookup"><span data-stu-id="579d3-157">**Points To**</span></span>|<span data-ttu-id="579d3-158">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="579d3-158">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="579d3-159">14400</span><span class="sxs-lookup"><span data-stu-id="579d3-159">14400</span></span>  <br/> |<span data-ttu-id="579d3-160">MX</span><span class="sxs-lookup"><span data-stu-id="579d3-160">MX</span></span>  <br/> | <span data-ttu-id="579d3-161">*\<ключ_домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="579d3-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/><span data-ttu-id="579d3-162">**Примечание.**  Получите свой \<*ключ-домена*\> из учетной записи портала Office 365.</span><span class="sxs-lookup"><span data-stu-id="579d3-162">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> [<span data-ttu-id="579d3-163">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="579d3-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="579d3-164">нуль</span><span class="sxs-lookup"><span data-stu-id="579d3-164">0</span></span>  <br/> <span data-ttu-id="579d3-165">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="579d3-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Выберите тип из раскрывающегося списка.](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. <span data-ttu-id="579d3-167">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="579d3-167">Select **add record**.</span></span>
    
    ![Нажмите кнопку Добавить запись](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. <span data-ttu-id="579d3-169">Если в разделе **MX (Mail Exchanger)** (Почтовый обменник) есть другие записи MX, удалите их.</span><span class="sxs-lookup"><span data-stu-id="579d3-169">If there are any other MX records in the **MX (Mail Exchanger)** section, delete each of them.</span></span> 
    
    <span data-ttu-id="579d3-170">Для одной из других записей MX нажмите кнопку **Удалить.**</span><span class="sxs-lookup"><span data-stu-id="579d3-170">For one of the other MX records, select **Delete.**</span></span>
    
    ![Выберите Delete (удалить) для каждой дополнительной записи MX](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. <span data-ttu-id="579d3-172">В диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="579d3-172">In the confirmation dialog box, select **OK**.</span></span>
    
    ![Нажмите кнопку ОК.](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. <span data-ttu-id="579d3-174">Повторите эти действия для всех ненужных записей MX.</span><span class="sxs-lookup"><span data-stu-id="579d3-174">Use the same process to delete any other MX records that were already listed.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="579d3-175">Добавление шести записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="579d3-175">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="579d3-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="579d3-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="579d3-177">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Bluehost по [этой ссылке](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="579d3-177">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="579d3-178">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="579d3-178">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="579d3-179">На странице **доменов** в области **домена** установите флажок домена, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="579d3-179">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="579d3-180">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="579d3-180">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="579d3-181">В области ***domain_name*** в строке **Редактор зоны DNS** выберите **Управление записями DNS**.</span><span class="sxs-lookup"><span data-stu-id="579d3-181">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="579d3-182">В разделе **A (Host) (записи узла)** найдите строку для записи **автообнаружения** , а затем выберите команду **Удалить** для этой строки.</span><span class="sxs-lookup"><span data-stu-id="579d3-182">In the **A (Host)** records section, find the row for the **autodiscover** record, and then select **delete** for that row.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="579d3-p110">Существующую запись **autodiscover** необходимо удалить  *перед*  добавлением записи **autodiscover**, которая нужна для Office 365. Bluehost не обеспечивает одновременную поддержку двух записей **autodiscover**.</span><span class="sxs-lookup"><span data-stu-id="579d3-p110">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Office 365. Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span></span> 
  
    ![Нажмите кнопку Удалить](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. <span data-ttu-id="579d3-186">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="579d3-186">Select **OK**.</span></span>
    
    ![Нажмите кнопку ОК.](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. <span data-ttu-id="579d3-188">Создайте первую из шести записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="579d3-188">Create the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="579d3-189">На странице **DNS Zone Editor** (Редактор зон DNS) в поля для новой записи в области **Add DNS Record** (Добавление записи DNS) введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="579d3-189">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="579d3-190">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="579d3-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="579d3-191">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="579d3-191">**Host Record**</span></span>|<span data-ttu-id="579d3-192">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="579d3-192">**TTL**</span></span>|<span data-ttu-id="579d3-193">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="579d3-193">**Type**</span></span>|<span data-ttu-id="579d3-194">**Points To (Указывает на)**</span><span class="sxs-lookup"><span data-stu-id="579d3-194">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="579d3-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="579d3-195">autodiscover</span></span>  <br/> |<span data-ttu-id="579d3-196">14400</span><span class="sxs-lookup"><span data-stu-id="579d3-196">14400</span></span>  <br/> |<span data-ttu-id="579d3-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="579d3-197">CNAME</span></span>  <br/> |<span data-ttu-id="579d3-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="579d3-198">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="579d3-199">sip</span><span class="sxs-lookup"><span data-stu-id="579d3-199">sip</span></span>  <br/> |<span data-ttu-id="579d3-200">14400</span><span class="sxs-lookup"><span data-stu-id="579d3-200">14400</span></span>  <br/> |<span data-ttu-id="579d3-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="579d3-201">CNAME</span></span>  <br/> |<span data-ttu-id="579d3-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="579d3-202">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="579d3-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="579d3-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="579d3-204">14400</span><span class="sxs-lookup"><span data-stu-id="579d3-204">14400</span></span>  <br/> |<span data-ttu-id="579d3-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="579d3-205">CNAME</span></span>  <br/> |<span data-ttu-id="579d3-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="579d3-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="579d3-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="579d3-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="579d3-208">14400</span><span class="sxs-lookup"><span data-stu-id="579d3-208">14400</span></span>  <br/> |<span data-ttu-id="579d3-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="579d3-209">CNAME</span></span>  <br/> |<span data-ttu-id="579d3-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="579d3-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="579d3-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="579d3-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="579d3-212">14400</span><span class="sxs-lookup"><span data-stu-id="579d3-212">14400</span></span>  <br/> |<span data-ttu-id="579d3-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="579d3-213">CNAME</span></span>  <br/> |<span data-ttu-id="579d3-214">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="579d3-214">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Создание первой записи CNAME](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. <span data-ttu-id="579d3-216">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="579d3-216">Select **add record**.</span></span>
    
    ![Нажмите кнопку Добавить запись](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. <span data-ttu-id="579d3-218">Добавьте остальные пять записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="579d3-218">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="579d3-219">По-прежнему в разделе **Добавление записи DNS** создайте запись, используя значения из следующей строки таблицы, а затем снова выберите **Добавить запись** , чтобы завершить эту запись.</span><span class="sxs-lookup"><span data-stu-id="579d3-219">Still in the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **add record** to complete that record.</span></span> 
    
    <span data-ttu-id="579d3-220">Повторяйте эти действия, пока не будут созданы все шесть записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="579d3-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="579d3-221">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="579d3-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="579d3-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="579d3-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="579d3-223">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="579d3-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="579d3-224">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="579d3-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="579d3-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="579d3-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="579d3-226">Вместо этого добавьте необходимые значения Office 365 в текущую запись. Таким образом, в *одной* записи SPF будут указаны оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="579d3-226">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="579d3-227">Нужны примеры?</span><span class="sxs-lookup"><span data-stu-id="579d3-227">Need examples?</span></span> <span data-ttu-id="579d3-228">Ознакомьтесь с этими [сведениями и образцами записей SPF](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="579d3-228">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="579d3-229">Чтобы проверить запись SPF, можно использовать один из этих[средств проверки SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="579d3-229">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="579d3-230">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Bluehost по [этой ссылке](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="579d3-230">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="579d3-231">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="579d3-231">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="579d3-232">На странице **доменов** в области **домена** установите флажок домена, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="579d3-232">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="579d3-233">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="579d3-233">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="579d3-234">В области ***domain_name*** в строке **Редактор зоны DNS** выберите **Управление записями DNS**.</span><span class="sxs-lookup"><span data-stu-id="579d3-234">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="579d3-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="579d3-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="579d3-236">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="579d3-236">(Choose the **Type** value from the drop-down list.)</span></span> 
        
    |<span data-ttu-id="579d3-237">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="579d3-237">**Host Record**</span></span>|<span data-ttu-id="579d3-238">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="579d3-238">**TTL**</span></span>|<span data-ttu-id="579d3-239">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="579d3-239">**Type**</span></span>|<span data-ttu-id="579d3-240">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="579d3-240">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="579d3-241">14400</span><span class="sxs-lookup"><span data-stu-id="579d3-241">14400</span></span>  <br/> |<span data-ttu-id="579d3-242">TXT</span><span class="sxs-lookup"><span data-stu-id="579d3-242">TXT</span></span>  <br/> |<span data-ttu-id="579d3-243">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="579d3-243">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="579d3-244">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="579d3-244">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Копирование значения TXT](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. <span data-ttu-id="579d3-246">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="579d3-246">Select **add record**.</span></span>
    
    ![Нажмите кнопку Добавить запись](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="579d3-248">Добавление двух записей SRV, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="579d3-248">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="579d3-249"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="579d3-249"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="579d3-250">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Bluehost по [этой ссылке](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="579d3-250">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="579d3-251">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="579d3-251">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="579d3-252">На странице **доменов** в области **домена** установите флажок домена, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="579d3-252">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="579d3-253">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="579d3-253">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="579d3-254">В области ***domain_name*** в строке **Редактор зоны DNS** выберите **Управление записями DNS**.</span><span class="sxs-lookup"><span data-stu-id="579d3-254">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="579d3-255">Создайте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="579d3-255">Create the first of the two SRV records.</span></span>
    
    <span data-ttu-id="579d3-256">На странице **DNS Zone Editor** (Редактор зон DNS) в поля для новой записи в области **Add DNS Record** (Добавление записи DNS) введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="579d3-256">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="579d3-257">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="579d3-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="579d3-258">**Служба**</span><span class="sxs-lookup"><span data-stu-id="579d3-258">**Service**</span></span>|<span data-ttu-id="579d3-259">**Protocol (Протокол)**</span><span class="sxs-lookup"><span data-stu-id="579d3-259">**Protocol**</span></span>|<span data-ttu-id="579d3-260">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="579d3-260">**Host**</span></span>|<span data-ttu-id="579d3-261">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="579d3-261">**TTL**</span></span>|<span data-ttu-id="579d3-262">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="579d3-262">**Type**</span></span>|<span data-ttu-id="579d3-263">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="579d3-263">**Priority**</span></span>|<span data-ttu-id="579d3-264">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="579d3-264">**Weight**</span></span>|<span data-ttu-id="579d3-265">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="579d3-265">**Port**</span></span>|<span data-ttu-id="579d3-266">**Points To (Указывает на)**</span><span class="sxs-lookup"><span data-stu-id="579d3-266">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="579d3-267">_sip</span><span class="sxs-lookup"><span data-stu-id="579d3-267">_sip</span></span>  <br/> |<span data-ttu-id="579d3-268">_tls</span><span class="sxs-lookup"><span data-stu-id="579d3-268">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="579d3-269">14400</span><span class="sxs-lookup"><span data-stu-id="579d3-269">14400</span></span>  <br/> |<span data-ttu-id="579d3-270">SRV</span><span class="sxs-lookup"><span data-stu-id="579d3-270">SRV</span></span>  <br/> |<span data-ttu-id="579d3-271">100</span><span class="sxs-lookup"><span data-stu-id="579d3-271">100</span></span>  <br/> |<span data-ttu-id="579d3-272">1,1</span><span class="sxs-lookup"><span data-stu-id="579d3-272">1</span></span>  <br/> |<span data-ttu-id="579d3-273">443</span><span class="sxs-lookup"><span data-stu-id="579d3-273">443</span></span>  <br/> |<span data-ttu-id="579d3-274">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="579d3-274">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="579d3-275">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="579d3-275">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="579d3-276">_tcp</span><span class="sxs-lookup"><span data-stu-id="579d3-276">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="579d3-277">14400</span><span class="sxs-lookup"><span data-stu-id="579d3-277">14400</span></span>  <br/> |<span data-ttu-id="579d3-278">SRV</span><span class="sxs-lookup"><span data-stu-id="579d3-278">SRV</span></span>  <br/> |<span data-ttu-id="579d3-279">100</span><span class="sxs-lookup"><span data-stu-id="579d3-279">100</span></span>  <br/> |<span data-ttu-id="579d3-280">1,1</span><span class="sxs-lookup"><span data-stu-id="579d3-280">1</span></span>  <br/> |<span data-ttu-id="579d3-281">5061</span><span class="sxs-lookup"><span data-stu-id="579d3-281">5061</span></span>  <br/> |<span data-ttu-id="579d3-282">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="579d3-282">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Копирование значения для новой записи](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. <span data-ttu-id="579d3-284">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="579d3-284">Select **add record**.</span></span>
    
    ![Нажмите кнопку Добавить запись](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. <span data-ttu-id="579d3-286">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="579d3-286">Add the other SRV record.</span></span>
    
    <span data-ttu-id="579d3-287">По-прежнему в разделе **Добавление записи DNS** создайте запись, используя значения из другой строки таблицы, а затем снова выберите **Добавить запись** , чтобы завершить эту запись.</span><span class="sxs-lookup"><span data-stu-id="579d3-287">Still in the **Add DNS Record** section, create a record by using the values from the other row in the table, and then again select **add record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="579d3-p114">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="579d3-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

