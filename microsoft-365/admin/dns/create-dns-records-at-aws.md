---
title: Создание записей DNS на веб-службах Amazon (AWS) для Майкрософт
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб в веб-службах Amazon (AWS) для Майкрософт.
ms.openlocfilehash: 1ce4d47dce2fce177efafade49b78ea706cf14e2
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919543"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-microsoft"></a><span data-ttu-id="36333-103">Создание записей DNS на веб-службах Amazon (AWS) для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="36333-103">Create DNS records at Amazon Web Services (AWS) for Microsoft</span></span>

 <span data-ttu-id="36333-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="36333-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="36333-105">Если AWS является поставщиком услуг хостинга DNS, выполните действия, описанные в этой статье, чтобы проверить домен и настроить записи DNS для электронной почты, Skype Online для бизнеса и т. д.</span><span class="sxs-lookup"><span data-stu-id="36333-105">If AWS is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype Online for Business, and so on.</span></span>
  
<span data-ttu-id="36333-106">Когда вы добавите эти записи на сайте AWS, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="36333-106">After you add these records at AWS, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="36333-107">Чтобы узнать о размещении и DNS для веб-сайтов с Микросфот, ознакомьтесь со статьей [использование общедоступного веб-сайта с корпорацией Майкрософт](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="36333-107">To learn about webhosting and DNS for websites with Microsfot, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="36333-p101">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="36333-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="36333-111">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="36333-111">Add a TXT record for verification</span></span>
<span data-ttu-id="36333-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="36333-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="36333-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="36333-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="36333-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="36333-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="36333-117">Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="36333-117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="36333-118">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="36333-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="36333-119">На странице **ресурсы** выберите пункт **размещенные зоны**.</span><span class="sxs-lookup"><span data-stu-id="36333-119">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="36333-120">На странице " **размещенные зоны** " в столбце **доменное имя** выберите доменное имя, которое требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="36333-120">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="36333-121">Выберите **создать набор записей**.</span><span class="sxs-lookup"><span data-stu-id="36333-121">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="36333-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="36333-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="36333-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="36333-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="36333-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="36333-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="36333-126">**Имя**</span><span class="sxs-lookup"><span data-stu-id="36333-126">**Name**</span></span> <br/> |<span data-ttu-id="36333-127">**Тип**</span><span class="sxs-lookup"><span data-stu-id="36333-127">**Type**</span></span> <br/> |<span data-ttu-id="36333-128">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="36333-128">**Alias**</span></span> <br/> |<span data-ttu-id="36333-129">**TTL (Seconds) (Срок жизни, в секундах)**</span><span class="sxs-lookup"><span data-stu-id="36333-129">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="36333-130">**Value (Значение)**</span><span class="sxs-lookup"><span data-stu-id="36333-130">**Value**</span></span> <br/> |<span data-ttu-id="36333-131">**Routing Policy (Политика маршрутизации)**</span><span class="sxs-lookup"><span data-stu-id="36333-131">**Routing Policy**</span></span> <br/> |
    |<span data-ttu-id="36333-132">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="36333-132">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="36333-133">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="36333-133">TXT - Text</span></span>  <br/> |<span data-ttu-id="36333-134">Нет</span><span class="sxs-lookup"><span data-stu-id="36333-134">No</span></span>  <br/> |<span data-ttu-id="36333-135">300</span><span class="sxs-lookup"><span data-stu-id="36333-135">300</span></span>  <br/> |<span data-ttu-id="36333-136">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="36333-136">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="36333-137">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="36333-137">**Note:** This is an example.</span></span> <span data-ttu-id="36333-138">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="36333-138">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="36333-139">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="36333-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="36333-140">Simple (Простая)</span><span class="sxs-lookup"><span data-stu-id="36333-140">Simple</span></span>  <br/> |
   
6. <span data-ttu-id="36333-141">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="36333-141">Select **Create**.</span></span>
    
7. <span data-ttu-id="36333-142">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="36333-142">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="36333-143">Теперь, когда вы добавили запись на сайт регистратора доменных имен, вернитесь в корпорацию Майкрософт и запросите Поиск записи.</span><span class="sxs-lookup"><span data-stu-id="36333-143">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="36333-144">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="36333-144">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="36333-145">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="36333-145">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="36333-146">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="36333-146">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="36333-147">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="36333-147">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="36333-148">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="36333-148">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="36333-p107">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="36333-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a><span data-ttu-id="36333-152">Добавьте запись MX, чтобы электронная почта для вашего домена поступила в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="36333-152">Add an MX record so email for your domain will come to Microsoft 365</span></span>
<span data-ttu-id="36333-153"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="36333-153"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="36333-p108">Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="36333-p108">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="36333-156">На странице **ресурсы** выберите пункт **размещенные зоны**.</span><span class="sxs-lookup"><span data-stu-id="36333-156">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="36333-157">На странице " **размещенные зоны** " в столбце **доменное имя** выберите доменное имя, которое требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="36333-157">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="36333-158">Выберите **создать набор записей**.</span><span class="sxs-lookup"><span data-stu-id="36333-158">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="36333-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="36333-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="36333-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="36333-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="36333-161">**Имя**</span><span class="sxs-lookup"><span data-stu-id="36333-161">**Name**</span></span>|<span data-ttu-id="36333-162">**Тип**</span><span class="sxs-lookup"><span data-stu-id="36333-162">**Type**</span></span>|<span data-ttu-id="36333-163">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="36333-163">**Alias**</span></span>|<span data-ttu-id="36333-164">**TTL (Seconds) (Срок жизни, в секундах)**</span><span class="sxs-lookup"><span data-stu-id="36333-164">**TTL (Seconds)**</span></span>|<span data-ttu-id="36333-165">**Value (Значение)**</span><span class="sxs-lookup"><span data-stu-id="36333-165">**Value**</span></span>|<span data-ttu-id="36333-166">**Routing Policy (Политика маршрутизации)**</span><span class="sxs-lookup"><span data-stu-id="36333-166">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="36333-167">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="36333-167">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="36333-168">MX  почтовый обменник</span><span class="sxs-lookup"><span data-stu-id="36333-168">MX - Mail exchange</span></span>  <br/> |<span data-ttu-id="36333-169">Нет</span><span class="sxs-lookup"><span data-stu-id="36333-169">No</span></span>  <br/> |<span data-ttu-id="36333-170">300</span><span class="sxs-lookup"><span data-stu-id="36333-170">300</span></span>  <br/> |<span data-ttu-id="36333-171">0  *\<ключ_домена\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="36333-171">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="36333-p109">0  значение приоритета MX. Добавьте его в начало значения MX, отделив от остальной части пробелом.  </span><span class="sxs-lookup"><span data-stu-id="36333-p109">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="36333-174">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="36333-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="36333-175">**Примечание:** \<Получите *ключ* \> домена из учетной записи Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="36333-175">**Note:** Get your \<*domain-key*\> from your Microsoft 365 account.</span></span> [<span data-ttu-id="36333-176">Как найти это значение?</span><span class="sxs-lookup"><span data-stu-id="36333-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="36333-177">Simple (Простая)</span><span class="sxs-lookup"><span data-stu-id="36333-177">Simple</span></span>  <br/> |
       
    ![AWS — BP — configure – 2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. <span data-ttu-id="36333-179">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="36333-179">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. <span data-ttu-id="36333-181">Если есть другие записи MX, удалите их.</span><span class="sxs-lookup"><span data-stu-id="36333-181">If there are any other MX records, remove them.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="36333-182">AWS хранит записи MX в виде наборов, которые могут содержать сразу несколько записей.</span><span class="sxs-lookup"><span data-stu-id="36333-182">AWS stores MX records as a set that may contain multiple records.</span></span> <span data-ttu-id="36333-183">**Не** выбирайте параметр **Удалить набор записей**, так как это приведет к удалению всех записей MX, включая только что добавленный.</span><span class="sxs-lookup"><span data-stu-id="36333-183">**DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added.</span></span> <span data-ttu-id="36333-184">Вместо этого сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="36333-184">Use the following instructions instead.</span></span> 
  
    <span data-ttu-id="36333-185">Сначала выберите набор записей MX.</span><span class="sxs-lookup"><span data-stu-id="36333-185">First, select the MX record set.</span></span>
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    <span data-ttu-id="36333-187">Затем в области **Edit Record Set** (Изменить набор записей) удалите каждую из устаревших записей MX, выбрав ее в поле **Value** (Значение) и нажав клавишу **DELETE**.</span><span class="sxs-lookup"><span data-stu-id="36333-187">Next, in the **Edit Record Set** area, delete each obsolete MX record by selecting the entry in the **Value** box and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. <span data-ttu-id="36333-189">Выберите **сохранить набор записей**.</span><span class="sxs-lookup"><span data-stu-id="36333-189">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="36333-191">Добавьте пять записей CNAME, необходимых для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="36333-191">Add the five CNAME records that are required for Microsoft 365</span></span>
<span data-ttu-id="36333-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="36333-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="36333-p112">Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="36333-p112">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="36333-195">На странице **ресурсы** выберите пункт **размещенные зоны**.</span><span class="sxs-lookup"><span data-stu-id="36333-195">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="36333-196">На странице " **размещенные зоны** " в столбце **доменное имя** выберите доменное имя, которое требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="36333-196">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="36333-197">Выберите **создать набор записей**.</span><span class="sxs-lookup"><span data-stu-id="36333-197">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="36333-198">Добавьте первую запись CNAME.</span><span class="sxs-lookup"><span data-stu-id="36333-198">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="36333-199">В поля для новой записи в области **Create Record Set** (Создание набора записей) введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="36333-199">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="36333-200">Выберите в раскрывающихся списках значения параметров **Type** (Тип) и **Routing Policy** (Политика маршрутизации).</span><span class="sxs-lookup"><span data-stu-id="36333-200">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="36333-201">**Имя**</span><span class="sxs-lookup"><span data-stu-id="36333-201">**Name**</span></span>|<span data-ttu-id="36333-202">**Тип**</span><span class="sxs-lookup"><span data-stu-id="36333-202">**Type**</span></span>|<span data-ttu-id="36333-203">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="36333-203">**Alias**</span></span>|<span data-ttu-id="36333-204">**TTL (Seconds) (Срок жизни, в секундах)**</span><span class="sxs-lookup"><span data-stu-id="36333-204">**TTL (Seconds)**</span></span>|<span data-ttu-id="36333-205">**Value (Значение)**</span><span class="sxs-lookup"><span data-stu-id="36333-205">**Value**</span></span>|<span data-ttu-id="36333-206">**Routing Policy (Политика маршрутизации)**</span><span class="sxs-lookup"><span data-stu-id="36333-206">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="36333-207">autodiscover</span><span class="sxs-lookup"><span data-stu-id="36333-207">autodiscover</span></span>  <br/> |<span data-ttu-id="36333-208">CNAME  каноническое имя</span><span class="sxs-lookup"><span data-stu-id="36333-208">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="36333-209">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="36333-209">No</span></span>  <br/> |<span data-ttu-id="36333-210">300</span><span class="sxs-lookup"><span data-stu-id="36333-210">300</span></span>  <br/> |<span data-ttu-id="36333-211">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="36333-211">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="36333-212">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="36333-212">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="36333-213">Это совсем не сложно.</span><span class="sxs-lookup"><span data-stu-id="36333-213">Simple</span></span>  <br/> |
    |<span data-ttu-id="36333-214">sip</span><span class="sxs-lookup"><span data-stu-id="36333-214">sip</span></span>  <br/> |<span data-ttu-id="36333-215">CNAME  каноническое имя</span><span class="sxs-lookup"><span data-stu-id="36333-215">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="36333-216">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="36333-216">No</span></span>  <br/> |<span data-ttu-id="36333-217">300</span><span class="sxs-lookup"><span data-stu-id="36333-217">300</span></span>  <br/> |<span data-ttu-id="36333-218">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="36333-218">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="36333-219">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="36333-219">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="36333-220">Это совсем не сложно.</span><span class="sxs-lookup"><span data-stu-id="36333-220">Simple</span></span>  <br/> |
    |<span data-ttu-id="36333-221">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="36333-221">lyncdiscover</span></span>  <br/> |<span data-ttu-id="36333-222">CNAME  каноническое имя</span><span class="sxs-lookup"><span data-stu-id="36333-222">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="36333-223">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="36333-223">No</span></span>  <br/> |<span data-ttu-id="36333-224">300</span><span class="sxs-lookup"><span data-stu-id="36333-224">300</span></span>  <br/> |<span data-ttu-id="36333-225">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="36333-225">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="36333-226">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="36333-226">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="36333-227">Это совсем не сложно.</span><span class="sxs-lookup"><span data-stu-id="36333-227">Simple</span></span>  <br/> |
    |<span data-ttu-id="36333-228">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="36333-228">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="36333-229">CNAME  каноническое имя</span><span class="sxs-lookup"><span data-stu-id="36333-229">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="36333-230">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="36333-230">No</span></span>  <br/> |<span data-ttu-id="36333-231">300</span><span class="sxs-lookup"><span data-stu-id="36333-231">300</span></span>  <br/> |<span data-ttu-id="36333-232">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="36333-232">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="36333-233">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="36333-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="36333-234">Simple (Простая)</span><span class="sxs-lookup"><span data-stu-id="36333-234">Simple</span></span>  <br/> |
    |<span data-ttu-id="36333-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="36333-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="36333-236">CNAME  каноническое имя</span><span class="sxs-lookup"><span data-stu-id="36333-236">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="36333-237">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="36333-237">No</span></span>  <br/> |<span data-ttu-id="36333-238">300</span><span class="sxs-lookup"><span data-stu-id="36333-238">300</span></span>  <br/> |<span data-ttu-id="36333-239">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="36333-239">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="36333-240">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="36333-240">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="36333-241">Это совсем не сложно.</span><span class="sxs-lookup"><span data-stu-id="36333-241">Simple</span></span>  <br/> |
   
    ![AWS — BP — configure – 3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. <span data-ttu-id="36333-243">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="36333-243">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. <span data-ttu-id="36333-245">Добавьте остальные четыре записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="36333-245">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="36333-246">На странице " **размещенные зоны** " выберите **создать набор записей**, создайте запись, используя значения из следующей строки таблицы, а затем еще раз нажмите кнопку **создать** , чтобы завершить эту запись.</span><span class="sxs-lookup"><span data-stu-id="36333-246">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
    <span data-ttu-id="36333-247">Повторяйте эту процедуру, пока не будут созданы все пять записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="36333-247">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="36333-248">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="36333-248">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="36333-249"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="36333-249"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="36333-250">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="36333-250">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="36333-251">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="36333-251">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="36333-252">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="36333-252">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="36333-253">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="36333-253">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="36333-254">Нужны примеры?</span><span class="sxs-lookup"><span data-stu-id="36333-254">Need examples?</span></span> <span data-ttu-id="36333-255">Ознакомьтесь с этими [записями системы внешних доменных имен для продуктов корпорации Майкрософт](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="36333-255">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="36333-256">Чтобы проверить запись SPF, можно использовать один из этих[средств проверки SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="36333-256">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="36333-257">Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="36333-257">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="36333-258">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="36333-258">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="36333-259">На странице **ресурсы** выберите пункт **размещенные зоны**.</span><span class="sxs-lookup"><span data-stu-id="36333-259">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="36333-260">На странице " **размещенные зоны** " в столбце **доменное имя** выберите доменное имя, которое требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="36333-260">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="36333-261">Выберите набор записей **txt** .</span><span class="sxs-lookup"><span data-stu-id="36333-261">Select the **TXT** record set.</span></span> 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. <span data-ttu-id="36333-p115">В области **Edit Record Set** (Изменение набора записей) в конце текущего элемента в поле **Value:** (Значение) существующей записи нажмите клавишу ВВОД, чтобы перейти на новую строку, а затем в этой новой строке (под существующим значением) введите или вставьте значение из таблицы ниже. (Пример приведен на рисунке под таблицей.)</span><span class="sxs-lookup"><span data-stu-id="36333-p115">In the **Edit Record Set** area, at the end of the current entry in the **Value:** box for the existing record, press Enter on your keyboard to create a new line; and then, on that new line (under the existing value), type or copy and paste the value from the following table. (You can see an example in the illustration below the table.)</span></span> 
    
    |<span data-ttu-id="36333-265">**Значение:**</span><span class="sxs-lookup"><span data-stu-id="36333-265">**Value:**</span></span>|
    |:-----|
    |<span data-ttu-id="36333-266">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="36333-266">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="36333-p116">(Кавычки, которые требуются в инструкциях на экране, добавляются автоматически. Вводить их вручную не нужно.)  </span><span class="sxs-lookup"><span data-stu-id="36333-p116">(The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.)  </span></span><br/> <span data-ttu-id="36333-269">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="36333-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![AWS — BP — configure – 4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. <span data-ttu-id="36333-271">Выберите **сохранить набор записей**.</span><span class="sxs-lookup"><span data-stu-id="36333-271">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="36333-273">Добавьте две записи SRV, необходимые для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="36333-273">Add the two SRV records that are required for Microsoft 365</span></span>
<span data-ttu-id="36333-274"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="36333-274"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="36333-p117">Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="36333-p117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="36333-277">На странице **ресурсы** выберите пункт **размещенные зоны**.</span><span class="sxs-lookup"><span data-stu-id="36333-277">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="36333-278">На странице " **размещенные зоны** " в столбце **доменное имя** выберите доменное имя, которое требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="36333-278">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="36333-279">Выберите **создать набор записей**.</span><span class="sxs-lookup"><span data-stu-id="36333-279">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="36333-280">Добавьте первую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="36333-280">Add the first SRV record:</span></span>
    
    <span data-ttu-id="36333-281">В поля для новой записи в области **Create Record Set** (Создание набора записей) введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="36333-281">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="36333-282">Выберите в раскрывающихся списках значения параметров **Type** (Тип) и **Routing Policy** (Политика маршрутизации).</span><span class="sxs-lookup"><span data-stu-id="36333-282">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="36333-283">**Имя**</span><span class="sxs-lookup"><span data-stu-id="36333-283">**Name**</span></span>|<span data-ttu-id="36333-284">**Тип**</span><span class="sxs-lookup"><span data-stu-id="36333-284">**Type**</span></span>|<span data-ttu-id="36333-285">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="36333-285">**Alias**</span></span>|<span data-ttu-id="36333-286">**TTL (Seconds) (Срок жизни, в секундах)**</span><span class="sxs-lookup"><span data-stu-id="36333-286">**TTL (Seconds)**</span></span>|<span data-ttu-id="36333-287">**Value (Значение)**</span><span class="sxs-lookup"><span data-stu-id="36333-287">**Value**</span></span>|<span data-ttu-id="36333-288">**Routing Policy (Политика маршрутизации)**</span><span class="sxs-lookup"><span data-stu-id="36333-288">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="36333-289">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="36333-289">_sip._tls</span></span>|<span data-ttu-id="36333-290">SRV  указатель служб</span><span class="sxs-lookup"><span data-stu-id="36333-290">SRV - Service locator</span></span>|<span data-ttu-id="36333-291">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="36333-291">No</span></span>|<span data-ttu-id="36333-292">300</span><span class="sxs-lookup"><span data-stu-id="36333-292">300</span></span>|<span data-ttu-id="36333-293">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="36333-293">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="36333-294">**Это значение должно заканчиваться точкой (.).**></span><span class="sxs-lookup"><span data-stu-id="36333-294">**This value MUST end with a period (.)**></span></span><br> <span data-ttu-id="36333-295">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="36333-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="36333-296">Simple (Простая)</span><span class="sxs-lookup"><span data-stu-id="36333-296">Simple</span></span>|
    |<span data-ttu-id="36333-297">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="36333-297">_sipfederationtls._tcp</span></span>|<span data-ttu-id="36333-298">SRV  указатель служб</span><span class="sxs-lookup"><span data-stu-id="36333-298">SRV - Service locator</span></span>|<span data-ttu-id="36333-299">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="36333-299">No</span></span>|<span data-ttu-id="36333-300">300</span><span class="sxs-lookup"><span data-stu-id="36333-300">300</span></span>|<span data-ttu-id="36333-301">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="36333-301">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="36333-302">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="36333-302">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="36333-303">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="36333-303">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="36333-304">Простое</span><span class="sxs-lookup"><span data-stu-id="36333-304">Simple</span></span>|
   
    ![AWS — BP — configure – 5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. <span data-ttu-id="36333-306">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="36333-306">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. <span data-ttu-id="36333-308">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="36333-308">To add the other SRV record:</span></span>
    
    <span data-ttu-id="36333-309">На странице " **размещенные зоны** " выберите **создать набор записей**, создайте запись, используя значения из следующей строки таблицы, а затем еще раз нажмите кнопку **создать** , чтобы завершить эту запись.</span><span class="sxs-lookup"><span data-stu-id="36333-309">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="36333-p120">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="36333-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
