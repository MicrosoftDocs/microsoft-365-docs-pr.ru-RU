---
title: Создание записей DNS для Office 365 в Dyn.com
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу Dyn.com для Office 365.
ms.openlocfilehash: a09ba409b1788432c5cd5c060252bb76b6903342
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2020
ms.locfileid: "42349350"
---
# <a name="create-dns-records-at-dyncom-for-office-365"></a><span data-ttu-id="7a1df-103">Создание записей DNS для Office 365 в Dyn.com</span><span class="sxs-lookup"><span data-stu-id="7a1df-103">Create DNS records at Dyn.com for Office 365</span></span>

 <span data-ttu-id="7a1df-104">Если вы не нашли то, что вы ищете, обратитесь к разделу **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="7a1df-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="7a1df-105">Если Dyn.com является поставщиком услуг хостинга DNS, выполните действия, описанные в этой статье, чтобы проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и т. д.</span><span class="sxs-lookup"><span data-stu-id="7a1df-105">If Dyn.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
 
<span data-ttu-id="7a1df-106">Дополнительные сведения о веб-хостинге и DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="7a1df-106">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="7a1df-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7a1df-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="7a1df-110">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="7a1df-110">Add a TXT record for verification</span></span>
<span data-ttu-id="7a1df-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="7a1df-111"><a name="BKMK_verify"> </a></span></span>

1. <span data-ttu-id="7a1df-p102">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Dyn.com по [этой ссылке](https://account.dyn.com/dns/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="7a1df-p102">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="7a1df-115">На странице " **службы уровня зоны** " выберите **Дин стандартная служба DNS** для домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="7a1df-115">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="7a1df-116">На странице **DNS** для вашего домена выберите **предпочтения**.</span><span class="sxs-lookup"><span data-stu-id="7a1df-116">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="7a1df-117">Выберите **включить экспертный интерфейс**.</span><span class="sxs-lookup"><span data-stu-id="7a1df-117">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="7a1df-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="7a1df-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="7a1df-119">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="7a1df-119">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7a1df-120">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="7a1df-120">**Host**</span></span>|<span data-ttu-id="7a1df-121">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="7a1df-121">**TTL**</span></span>|<span data-ttu-id="7a1df-122">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="7a1df-122">**Type**</span></span>|<span data-ttu-id="7a1df-123">**Data (Данные)**</span><span class="sxs-lookup"><span data-stu-id="7a1df-123">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7a1df-124">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="7a1df-124">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="7a1df-125">600</span><span class="sxs-lookup"><span data-stu-id="7a1df-125">600</span></span>  <br/> |<span data-ttu-id="7a1df-126">TXT</span><span class="sxs-lookup"><span data-stu-id="7a1df-126">TXT</span></span>  <br/> |<span data-ttu-id="7a1df-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="7a1df-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="7a1df-p103">**Примечание.** Это пример. Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.           [Где это находится?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="7a1df-p103">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
       
   ![Дин — BP — Verify – 1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. <span data-ttu-id="7a1df-132">Выберите **создать запись**.</span><span class="sxs-lookup"><span data-stu-id="7a1df-132">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. <span data-ttu-id="7a1df-134">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="7a1df-134">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="7a1df-135">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Office 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="7a1df-135">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="7a1df-136">Если Office 365 обнаружит правильную запись TXT, это значит, что домен проверен.</span><span class="sxs-lookup"><span data-stu-id="7a1df-136">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="7a1df-137">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="7a1df-137">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="7a1df-138">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="7a1df-138">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="7a1df-139">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="7a1df-139">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="7a1df-140">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="7a1df-140">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="7a1df-p104">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7a1df-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="7a1df-144">Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="7a1df-144">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="7a1df-145"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="7a1df-145"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="7a1df-p105">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Dyn.com по [этой ссылке](https://account.dyn.com/dns/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="7a1df-p105">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="7a1df-149">На странице " **службы уровня зоны** " выберите **Дин стандартная служба DNS** для домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="7a1df-149">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="7a1df-150">На странице DNS для вашего домена выберите **предпочтения**.</span><span class="sxs-lookup"><span data-stu-id="7a1df-150">On the DNS page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="7a1df-151">Выберите **включить экспертный интерфейс**.</span><span class="sxs-lookup"><span data-stu-id="7a1df-151">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="7a1df-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="7a1df-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="7a1df-153">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="7a1df-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7a1df-154">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="7a1df-154">**Host**</span></span>|<span data-ttu-id="7a1df-155">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="7a1df-155">**TTL**</span></span>|<span data-ttu-id="7a1df-156">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="7a1df-156">**Type**</span></span>|<span data-ttu-id="7a1df-157">**Data (Данные)**</span><span class="sxs-lookup"><span data-stu-id="7a1df-157">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7a1df-158">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="7a1df-158">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="7a1df-159">600</span><span class="sxs-lookup"><span data-stu-id="7a1df-159">600</span></span>  <br/> |<span data-ttu-id="7a1df-160">MX</span><span class="sxs-lookup"><span data-stu-id="7a1df-160">MX</span></span>  <br/> |<span data-ttu-id="7a1df-161">10  *\<ключ_домена\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="7a1df-161">10  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="7a1df-162">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="7a1df-162">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="7a1df-p106">**10**  значение приоритета MX. Добавьте его в начало значения MX, отделив от остальной части пробелом.  </span><span class="sxs-lookup"><span data-stu-id="7a1df-p106">The **10** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="7a1df-165">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Office 365.</span><span class="sxs-lookup"><span data-stu-id="7a1df-165">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="7a1df-166">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="7a1df-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      <br>    <span data-ttu-id="7a1df-167">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="7a1df-167">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![Дин — BP — configure – 2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. <span data-ttu-id="7a1df-169">Выберите **создать запись**.</span><span class="sxs-lookup"><span data-stu-id="7a1df-169">Select **Create Record**.</span></span>
    
    ![Дин — BP — configure – 2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. <span data-ttu-id="7a1df-171">Если существуют какие-либо другие записи MX, удалите их, установив флажок для каждого из них в столбце **Delete (удалить** ).</span><span class="sxs-lookup"><span data-stu-id="7a1df-171">If there are any other MX records, remove them by selecting the check box for each one in the **Delete** column.</span></span> 
    
    ![Дин — BP — configure – 2-3](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. <span data-ttu-id="7a1df-173">Выберите **Apply Changes (применить изменения**).</span><span class="sxs-lookup"><span data-stu-id="7a1df-173">Select **Apply Changes**.</span></span>
    
    ![Дин — BP — configure – 2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="7a1df-175">Добавление шести записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="7a1df-175">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="7a1df-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="7a1df-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="7a1df-p108">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Dyn.com по [этой ссылке](https://account.dyn.com/dns/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="7a1df-p108">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="7a1df-180">На странице " **службы уровня зоны** " выберите **Дин стандартная служба DNS** для домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="7a1df-180">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="7a1df-181">На странице **DNS** для вашего домена выберите **предпочтения**.</span><span class="sxs-lookup"><span data-stu-id="7a1df-181">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="7a1df-182">Выберите **включить экспертный интерфейс**.</span><span class="sxs-lookup"><span data-stu-id="7a1df-182">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="7a1df-183">Добавьте первую из шести записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="7a1df-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="7a1df-184">В поля для новой записи в разделе **Добавление DNS-записи** введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="7a1df-184">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="7a1df-185">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="7a1df-185">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7a1df-186">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="7a1df-186">**Host**</span></span>|<span data-ttu-id="7a1df-187">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="7a1df-187">**TTL**</span></span>|<span data-ttu-id="7a1df-188">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="7a1df-188">**Type**</span></span>|<span data-ttu-id="7a1df-189">**Data (Данные)**</span><span class="sxs-lookup"><span data-stu-id="7a1df-189">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7a1df-190">autodiscover</span><span class="sxs-lookup"><span data-stu-id="7a1df-190">autodiscover</span></span>  <br/> |<span data-ttu-id="7a1df-191">600</span><span class="sxs-lookup"><span data-stu-id="7a1df-191">600</span></span>  <br/> |<span data-ttu-id="7a1df-192">CNAME</span><span class="sxs-lookup"><span data-stu-id="7a1df-192">CNAME</span></span>  <br/> |<span data-ttu-id="7a1df-193">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="7a1df-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="7a1df-194">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="7a1df-194">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="7a1df-195">sip</span><span class="sxs-lookup"><span data-stu-id="7a1df-195">sip</span></span>  <br/> |<span data-ttu-id="7a1df-196">600</span><span class="sxs-lookup"><span data-stu-id="7a1df-196">600</span></span>  <br/> |<span data-ttu-id="7a1df-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="7a1df-197">CNAME</span></span>  <br/> |<span data-ttu-id="7a1df-198">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7a1df-198">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="7a1df-199">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="7a1df-199">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="7a1df-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7a1df-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="7a1df-201">600</span><span class="sxs-lookup"><span data-stu-id="7a1df-201">600</span></span>  <br/> |<span data-ttu-id="7a1df-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="7a1df-202">CNAME</span></span>  <br/> |<span data-ttu-id="7a1df-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7a1df-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="7a1df-204">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="7a1df-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="7a1df-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="7a1df-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="7a1df-206">600</span><span class="sxs-lookup"><span data-stu-id="7a1df-206">600</span></span>  <br/> |<span data-ttu-id="7a1df-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="7a1df-207">CNAME</span></span>  <br/> |<span data-ttu-id="7a1df-208">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="7a1df-208">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="7a1df-209">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="7a1df-209">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="7a1df-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="7a1df-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="7a1df-211">600</span><span class="sxs-lookup"><span data-stu-id="7a1df-211">600</span></span>  <br/> |<span data-ttu-id="7a1df-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="7a1df-212">CNAME</span></span>  <br/> |<span data-ttu-id="7a1df-213">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="7a1df-213">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="7a1df-214">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="7a1df-214">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Дин — BP — configure – 3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. <span data-ttu-id="7a1df-216">Выберите **создать запись**.</span><span class="sxs-lookup"><span data-stu-id="7a1df-216">Select **Create Record**.</span></span>
    
    ![Дин — BP — configure – 3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. <span data-ttu-id="7a1df-218">Добавьте оставшиеся пять записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="7a1df-218">Add the remaining five CNAME records.</span></span>
    
    <span data-ttu-id="7a1df-219">В разделе **Добавление записи DNS** создайте запись, используя значения из следующей строки таблицы, а затем еще раз выберите **создать запись** , чтобы завершить эту запись.</span><span class="sxs-lookup"><span data-stu-id="7a1df-219">In the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
    <span data-ttu-id="7a1df-220">Повторяйте эти действия, пока не будут созданы все шесть записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="7a1df-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="7a1df-221">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="7a1df-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="7a1df-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="7a1df-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="7a1df-223">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="7a1df-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="7a1df-224">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="7a1df-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="7a1df-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="7a1df-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="7a1df-226">Вместо этого добавьте необходимые значения Office 365 в текущую запись. Таким образом, в *одной* записи SPF будут указаны оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="7a1df-226">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="7a1df-p110">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Dyn.com по [этой ссылке](https://account.dyn.com/dns/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="7a1df-p110">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="7a1df-230">На странице " **службы уровня зоны** " выберите **Дин стандартная служба DNS** для домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="7a1df-230">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="7a1df-231">На странице **DNS** для вашего домена выберите **предпочтения**.</span><span class="sxs-lookup"><span data-stu-id="7a1df-231">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="7a1df-232">Выберите **включить экспертный интерфейс**.</span><span class="sxs-lookup"><span data-stu-id="7a1df-232">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="7a1df-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="7a1df-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="7a1df-234">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="7a1df-234">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7a1df-235">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="7a1df-235">**Host**</span></span>|<span data-ttu-id="7a1df-236">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="7a1df-236">**TTL**</span></span>|<span data-ttu-id="7a1df-237">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="7a1df-237">**Type**</span></span>|<span data-ttu-id="7a1df-238">**Data (Данные)**</span><span class="sxs-lookup"><span data-stu-id="7a1df-238">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7a1df-239">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="7a1df-239">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="7a1df-240">600</span><span class="sxs-lookup"><span data-stu-id="7a1df-240">600</span></span>  <br/> |<span data-ttu-id="7a1df-241">TXT</span><span class="sxs-lookup"><span data-stu-id="7a1df-241">TXT</span></span>  <br/> |<span data-ttu-id="7a1df-242">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="7a1df-242">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="7a1df-243">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="7a1df-243">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Дин — BP — configure – 4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. <span data-ttu-id="7a1df-245">Выберите **создать запись**.</span><span class="sxs-lookup"><span data-stu-id="7a1df-245">Select **Create Record**.</span></span>
    
    ![Дин — BP — configure – 4-2](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="7a1df-247">Добавление двух записей SRV, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="7a1df-247">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="7a1df-248"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="7a1df-248"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="7a1df-249">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Dyn.com по [этой ссылке](https://account.dyn.com/dns/).</span><span class="sxs-lookup"><span data-stu-id="7a1df-249">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/).</span></span> <span data-ttu-id="7a1df-250">Сначала вам будет предложено выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="7a1df-250">You'll be prompted to login first</span></span> 
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="7a1df-252">На странице " **службы уровня зоны** " выберите **Дин стандартная служба DNS** для домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="7a1df-252">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="7a1df-253">На странице **DNS** для вашего домена выберите **предпочтения**.</span><span class="sxs-lookup"><span data-stu-id="7a1df-253">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="7a1df-254">Выберите **включить экспертный интерфейс**.</span><span class="sxs-lookup"><span data-stu-id="7a1df-254">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="7a1df-255">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="7a1df-255">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="7a1df-256">В поля для новой записи в разделе **Добавление DNS-записи** введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="7a1df-256">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="7a1df-257">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="7a1df-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7a1df-258">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="7a1df-258">**Host**</span></span>|<span data-ttu-id="7a1df-259">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="7a1df-259">**TTL**</span></span>|<span data-ttu-id="7a1df-260">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="7a1df-260">**Type**</span></span>|<span data-ttu-id="7a1df-261">**Data (Данные)**</span><span class="sxs-lookup"><span data-stu-id="7a1df-261">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7a1df-262">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="7a1df-262">_sip._tls</span></span>|<span data-ttu-id="7a1df-263">600</span><span class="sxs-lookup"><span data-stu-id="7a1df-263">600</span></span>|<span data-ttu-id="7a1df-264">SRV</span><span class="sxs-lookup"><span data-stu-id="7a1df-264">SRV</span></span>|<span data-ttu-id="7a1df-265">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7a1df-265">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="7a1df-266">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="7a1df-266">**This value MUST end with a period (.)**</span></span><br><span data-ttu-id="7a1df-267">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="7a1df-267">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="7a1df-268">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="7a1df-268">_sipfederationtls._tcp</span></span>|<span data-ttu-id="7a1df-269">600</span><span class="sxs-lookup"><span data-stu-id="7a1df-269">600</span></span>|<span data-ttu-id="7a1df-270">SRV</span><span class="sxs-lookup"><span data-stu-id="7a1df-270">SRV</span></span>|<span data-ttu-id="7a1df-271">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7a1df-271">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="7a1df-272">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="7a1df-272">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="7a1df-273">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="7a1df-273">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Дин — BP — configure – 5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. <span data-ttu-id="7a1df-275">Выберите **создать запись**.</span><span class="sxs-lookup"><span data-stu-id="7a1df-275">Select **Create Record**.</span></span>
    
    ![Дин — BP — configure – 5-2](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. <span data-ttu-id="7a1df-277">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="7a1df-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="7a1df-278">В разделе **Добавление записи DNS** создайте запись, используя значения из второй строки таблицы, а затем еще раз выберите **создать запись** , чтобы завершить эту запись.</span><span class="sxs-lookup"><span data-stu-id="7a1df-278">In the **Add DNS Record** section, create a record by using the values from the second row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
> [!NOTE]
>  <span data-ttu-id="7a1df-p114">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7a1df-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
