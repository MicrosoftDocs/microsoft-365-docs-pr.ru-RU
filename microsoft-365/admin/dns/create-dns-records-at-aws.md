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
ms.openlocfilehash: d75822feef5848575b8ec7fe09f834f67cdc6c55
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049111"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-microsoft"></a><span data-ttu-id="af698-103">Создание записей DNS на веб-службах Amazon (AWS) для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="af698-103">Create DNS records at Amazon Web Services (AWS) for Microsoft</span></span>

 <span data-ttu-id="af698-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="af698-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="af698-105">Если AWS является поставщиком услуг хостинга DNS, выполните действия, описанные в этой статье, чтобы проверить домен и настроить записи DNS для электронной почты, Skype Online для бизнеса и т. д.</span><span class="sxs-lookup"><span data-stu-id="af698-105">If AWS is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype Online for Business, and so on.</span></span>
  
<span data-ttu-id="af698-106">Когда вы добавите эти записи на сайте AWS, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="af698-106">After you add these records at AWS, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="af698-p101">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="af698-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="af698-110">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="af698-110">Add a TXT record for verification</span></span>
<span data-ttu-id="af698-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="af698-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="af698-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="af698-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="af698-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="af698-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="af698-116">Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="af698-116">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="af698-117">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="af698-117">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="af698-118">На странице **ресурсы** выберите пункт **размещенные зоны**.</span><span class="sxs-lookup"><span data-stu-id="af698-118">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="af698-119">На странице " **размещенные зоны** " в столбце **доменное имя** выберите доменное имя, которое требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="af698-119">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="af698-120">Выберите **создать набор записей**.</span><span class="sxs-lookup"><span data-stu-id="af698-120">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="af698-121">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="af698-121">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="af698-122">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="af698-122">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="af698-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="af698-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="af698-125">**Name**</span><span class="sxs-lookup"><span data-stu-id="af698-125">**Name**</span></span> <br/> |<span data-ttu-id="af698-126">**Тип**</span><span class="sxs-lookup"><span data-stu-id="af698-126">**Type**</span></span> <br/> |<span data-ttu-id="af698-127">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="af698-127">**Alias**</span></span> <br/> |<span data-ttu-id="af698-128">**TTL (Seconds) (Срок жизни, в секундах)**</span><span class="sxs-lookup"><span data-stu-id="af698-128">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="af698-129">**Value (Значение)**</span><span class="sxs-lookup"><span data-stu-id="af698-129">**Value**</span></span> <br/> |<span data-ttu-id="af698-130">**Routing Policy (Политика маршрутизации)**</span><span class="sxs-lookup"><span data-stu-id="af698-130">**Routing Policy**</span></span> <br/> |
    |<span data-ttu-id="af698-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="af698-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="af698-132">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="af698-132">TXT - Text</span></span>  <br/> |<span data-ttu-id="af698-133">Нет</span><span class="sxs-lookup"><span data-stu-id="af698-133">No</span></span>  <br/> |<span data-ttu-id="af698-134">300</span><span class="sxs-lookup"><span data-stu-id="af698-134">300</span></span>  <br/> |<span data-ttu-id="af698-135">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="af698-135">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="af698-136">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="af698-136">**Note:** This is an example.</span></span> <span data-ttu-id="af698-137">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="af698-137">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="af698-138">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="af698-138">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="af698-139">Simple (Простая)</span><span class="sxs-lookup"><span data-stu-id="af698-139">Simple</span></span>  <br/> |
   
6. <span data-ttu-id="af698-140">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="af698-140">Select **Create**.</span></span>
    
7. <span data-ttu-id="af698-141">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="af698-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="af698-142">Теперь, когда вы добавили запись на сайт регистратора доменных имен, вернитесь в корпорацию Майкрософт и запросите Поиск записи.</span><span class="sxs-lookup"><span data-stu-id="af698-142">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="af698-143">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="af698-143">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="af698-144">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="af698-144">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="af698-145">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="af698-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="af698-146">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="af698-146">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="af698-147">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="af698-147">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="af698-p107">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="af698-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a><span data-ttu-id="af698-151">Добавьте запись MX, чтобы электронная почта для вашего домена поступила в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="af698-151">Add an MX record so email for your domain will come to Microsoft 365</span></span>
<span data-ttu-id="af698-152"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="af698-152"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="af698-p108">Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="af698-p108">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="af698-155">На странице **ресурсы** выберите пункт **размещенные зоны**.</span><span class="sxs-lookup"><span data-stu-id="af698-155">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="af698-156">На странице " **размещенные зоны** " в столбце **доменное имя** выберите доменное имя, которое требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="af698-156">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="af698-157">Выберите **создать набор записей**.</span><span class="sxs-lookup"><span data-stu-id="af698-157">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="af698-158">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="af698-158">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="af698-159">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="af698-159">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="af698-160">**Name**</span><span class="sxs-lookup"><span data-stu-id="af698-160">**Name**</span></span>|<span data-ttu-id="af698-161">**Тип**</span><span class="sxs-lookup"><span data-stu-id="af698-161">**Type**</span></span>|<span data-ttu-id="af698-162">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="af698-162">**Alias**</span></span>|<span data-ttu-id="af698-163">**TTL (Seconds) (Срок жизни, в секундах)**</span><span class="sxs-lookup"><span data-stu-id="af698-163">**TTL (Seconds)**</span></span>|<span data-ttu-id="af698-164">**Value (Значение)**</span><span class="sxs-lookup"><span data-stu-id="af698-164">**Value**</span></span>|<span data-ttu-id="af698-165">**Routing Policy (Политика маршрутизации)**</span><span class="sxs-lookup"><span data-stu-id="af698-165">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="af698-166">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="af698-166">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="af698-167">MX  почтовый обменник</span><span class="sxs-lookup"><span data-stu-id="af698-167">MX - Mail exchange</span></span>  <br/> |<span data-ttu-id="af698-168">Нет</span><span class="sxs-lookup"><span data-stu-id="af698-168">No</span></span>  <br/> |<span data-ttu-id="af698-169">300</span><span class="sxs-lookup"><span data-stu-id="af698-169">300</span></span>  <br/> |<span data-ttu-id="af698-170">0  *\<ключ_домена\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="af698-170">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="af698-p109">0  значение приоритета MX. Добавьте его в начало значения MX, отделив от остальной части пробелом.  </span><span class="sxs-lookup"><span data-stu-id="af698-p109">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="af698-173">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="af698-173">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="af698-174">**Примечание:** \<Получите *ключ* \> домена из учетной записи Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="af698-174">**Note:** Get your \<*domain-key*\> from your Microsoft 365 account.</span></span> [<span data-ttu-id="af698-175">Как найти это значение?</span><span class="sxs-lookup"><span data-stu-id="af698-175">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="af698-176">Simple (Простая)</span><span class="sxs-lookup"><span data-stu-id="af698-176">Simple</span></span>  <br/> |
       
    ![AWS — BP — configure – 2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. <span data-ttu-id="af698-178">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="af698-178">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. <span data-ttu-id="af698-180">Если есть другие записи MX, удалите их.</span><span class="sxs-lookup"><span data-stu-id="af698-180">If there are any other MX records, remove them.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="af698-181">AWS хранит записи MX в виде наборов, которые могут содержать сразу несколько записей.</span><span class="sxs-lookup"><span data-stu-id="af698-181">AWS stores MX records as a set that may contain multiple records.</span></span> <span data-ttu-id="af698-182">**Не** выбирайте параметр **Удалить набор записей**, так как это приведет к удалению всех записей MX, включая только что добавленный.</span><span class="sxs-lookup"><span data-stu-id="af698-182">**DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added.</span></span> <span data-ttu-id="af698-183">Вместо этого сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="af698-183">Use the following instructions instead.</span></span> 
  
    <span data-ttu-id="af698-184">Сначала выберите набор записей MX.</span><span class="sxs-lookup"><span data-stu-id="af698-184">First, select the MX record set.</span></span>
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    <span data-ttu-id="af698-186">Затем в области **Edit Record Set** (Изменить набор записей) удалите каждую из устаревших записей MX, выбрав ее в поле **Value** (Значение) и нажав клавишу **DELETE**.</span><span class="sxs-lookup"><span data-stu-id="af698-186">Next, in the **Edit Record Set** area, delete each obsolete MX record by selecting the entry in the **Value** box and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. <span data-ttu-id="af698-188">Выберите **сохранить набор записей**.</span><span class="sxs-lookup"><span data-stu-id="af698-188">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="af698-190">Добавьте пять записей CNAME, необходимых для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="af698-190">Add the five CNAME records that are required for Microsoft 365</span></span>
<span data-ttu-id="af698-191"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="af698-191"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="af698-p112">Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="af698-p112">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="af698-194">На странице **ресурсы** выберите пункт **размещенные зоны**.</span><span class="sxs-lookup"><span data-stu-id="af698-194">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="af698-195">На странице " **размещенные зоны** " в столбце **доменное имя** выберите доменное имя, которое требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="af698-195">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="af698-196">Выберите **создать набор записей**.</span><span class="sxs-lookup"><span data-stu-id="af698-196">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="af698-197">Добавьте первую запись CNAME.</span><span class="sxs-lookup"><span data-stu-id="af698-197">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="af698-198">В поля для новой записи в области **Create Record Set** (Создание набора записей) введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="af698-198">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="af698-199">Выберите в раскрывающихся списках значения параметров **Type** (Тип) и **Routing Policy** (Политика маршрутизации).</span><span class="sxs-lookup"><span data-stu-id="af698-199">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="af698-200">**Name**</span><span class="sxs-lookup"><span data-stu-id="af698-200">**Name**</span></span>|<span data-ttu-id="af698-201">**Тип**</span><span class="sxs-lookup"><span data-stu-id="af698-201">**Type**</span></span>|<span data-ttu-id="af698-202">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="af698-202">**Alias**</span></span>|<span data-ttu-id="af698-203">**TTL (Seconds) (Срок жизни, в секундах)**</span><span class="sxs-lookup"><span data-stu-id="af698-203">**TTL (Seconds)**</span></span>|<span data-ttu-id="af698-204">**Value (Значение)**</span><span class="sxs-lookup"><span data-stu-id="af698-204">**Value**</span></span>|<span data-ttu-id="af698-205">**Routing Policy (Политика маршрутизации)**</span><span class="sxs-lookup"><span data-stu-id="af698-205">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="af698-206">autodiscover</span><span class="sxs-lookup"><span data-stu-id="af698-206">autodiscover</span></span>  <br/> |<span data-ttu-id="af698-207">CNAME  каноническое имя</span><span class="sxs-lookup"><span data-stu-id="af698-207">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="af698-208">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="af698-208">No</span></span>  <br/> |<span data-ttu-id="af698-209">300</span><span class="sxs-lookup"><span data-stu-id="af698-209">300</span></span>  <br/> |<span data-ttu-id="af698-210">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="af698-210">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="af698-211">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="af698-211">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="af698-212">Это совсем не сложно.</span><span class="sxs-lookup"><span data-stu-id="af698-212">Simple</span></span>  <br/> |
    |<span data-ttu-id="af698-213">sip</span><span class="sxs-lookup"><span data-stu-id="af698-213">sip</span></span>  <br/> |<span data-ttu-id="af698-214">CNAME  каноническое имя</span><span class="sxs-lookup"><span data-stu-id="af698-214">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="af698-215">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="af698-215">No</span></span>  <br/> |<span data-ttu-id="af698-216">300</span><span class="sxs-lookup"><span data-stu-id="af698-216">300</span></span>  <br/> |<span data-ttu-id="af698-217">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="af698-217">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="af698-218">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="af698-218">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="af698-219">Это совсем не сложно.</span><span class="sxs-lookup"><span data-stu-id="af698-219">Simple</span></span>  <br/> |
    |<span data-ttu-id="af698-220">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="af698-220">lyncdiscover</span></span>  <br/> |<span data-ttu-id="af698-221">CNAME  каноническое имя</span><span class="sxs-lookup"><span data-stu-id="af698-221">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="af698-222">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="af698-222">No</span></span>  <br/> |<span data-ttu-id="af698-223">300</span><span class="sxs-lookup"><span data-stu-id="af698-223">300</span></span>  <br/> |<span data-ttu-id="af698-224">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="af698-224">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="af698-225">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="af698-225">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="af698-226">Это совсем не сложно.</span><span class="sxs-lookup"><span data-stu-id="af698-226">Simple</span></span>  <br/> |
    |<span data-ttu-id="af698-227">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="af698-227">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="af698-228">CNAME  каноническое имя</span><span class="sxs-lookup"><span data-stu-id="af698-228">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="af698-229">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="af698-229">No</span></span>  <br/> |<span data-ttu-id="af698-230">300</span><span class="sxs-lookup"><span data-stu-id="af698-230">300</span></span>  <br/> |<span data-ttu-id="af698-231">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="af698-231">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="af698-232">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="af698-232">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="af698-233">Simple (Простая)</span><span class="sxs-lookup"><span data-stu-id="af698-233">Simple</span></span>  <br/> |
    |<span data-ttu-id="af698-234">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="af698-234">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="af698-235">CNAME  каноническое имя</span><span class="sxs-lookup"><span data-stu-id="af698-235">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="af698-236">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="af698-236">No</span></span>  <br/> |<span data-ttu-id="af698-237">300</span><span class="sxs-lookup"><span data-stu-id="af698-237">300</span></span>  <br/> |<span data-ttu-id="af698-238">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="af698-238">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="af698-239">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="af698-239">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="af698-240">Это совсем не сложно.</span><span class="sxs-lookup"><span data-stu-id="af698-240">Simple</span></span>  <br/> |
   
    ![AWS — BP — configure – 3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. <span data-ttu-id="af698-242">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="af698-242">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. <span data-ttu-id="af698-244">Добавьте остальные четыре записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="af698-244">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="af698-245">На странице " **размещенные зоны** " выберите **создать набор записей**, создайте запись, используя значения из следующей строки таблицы, а затем еще раз нажмите кнопку **создать** , чтобы завершить эту запись.</span><span class="sxs-lookup"><span data-stu-id="af698-245">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
    <span data-ttu-id="af698-246">Повторяйте эту процедуру, пока не будут созданы все пять записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="af698-246">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="af698-247">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="af698-247">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="af698-248"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="af698-248"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="af698-249">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="af698-249">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="af698-250">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="af698-250">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="af698-251">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="af698-251">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="af698-252">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="af698-252">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="af698-253">Нужны примеры?</span><span class="sxs-lookup"><span data-stu-id="af698-253">Need examples?</span></span> <span data-ttu-id="af698-254">Ознакомьтесь с этими [записями системы внешних доменных имен для продуктов корпорации Майкрософт](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span><span class="sxs-lookup"><span data-stu-id="af698-254">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="af698-255">Чтобы проверить запись SPF, можно использовать один из этих[средств проверки SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="af698-255">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="af698-256">Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="af698-256">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="af698-257">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="af698-257">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="af698-258">На странице **ресурсы** выберите пункт **размещенные зоны**.</span><span class="sxs-lookup"><span data-stu-id="af698-258">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="af698-259">На странице " **размещенные зоны** " в столбце **доменное имя** выберите доменное имя, которое требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="af698-259">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="af698-260">Выберите набор записей **txt** .</span><span class="sxs-lookup"><span data-stu-id="af698-260">Select the **TXT** record set.</span></span> 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. <span data-ttu-id="af698-p115">В области **Edit Record Set** (Изменение набора записей) в конце текущего элемента в поле **Value:** (Значение) существующей записи нажмите клавишу ВВОД, чтобы перейти на новую строку, а затем в этой новой строке (под существующим значением) введите или вставьте значение из таблицы ниже. (Пример приведен на рисунке под таблицей.)</span><span class="sxs-lookup"><span data-stu-id="af698-p115">In the **Edit Record Set** area, at the end of the current entry in the **Value:** box for the existing record, press Enter on your keyboard to create a new line; and then, on that new line (under the existing value), type or copy and paste the value from the following table. (You can see an example in the illustration below the table.)</span></span> 
    
    |<span data-ttu-id="af698-264">**Значение:**</span><span class="sxs-lookup"><span data-stu-id="af698-264">**Value:**</span></span>|
    |:-----|
    |<span data-ttu-id="af698-265">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="af698-265">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="af698-p116">(Кавычки, которые требуются в инструкциях на экране, добавляются автоматически. Вводить их вручную не нужно.)  </span><span class="sxs-lookup"><span data-stu-id="af698-p116">(The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.)  </span></span><br/> <span data-ttu-id="af698-268">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="af698-268">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![AWS — BP — configure – 4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. <span data-ttu-id="af698-270">Выберите **сохранить набор записей**.</span><span class="sxs-lookup"><span data-stu-id="af698-270">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="af698-272">Добавьте две записи SRV, необходимые для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="af698-272">Add the two SRV records that are required for Microsoft 365</span></span>
<span data-ttu-id="af698-273"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="af698-273"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="af698-p117">Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="af698-p117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="af698-276">На странице **ресурсы** выберите пункт **размещенные зоны**.</span><span class="sxs-lookup"><span data-stu-id="af698-276">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="af698-277">На странице " **размещенные зоны** " в столбце **доменное имя** выберите доменное имя, которое требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="af698-277">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="af698-278">Выберите **создать набор записей**.</span><span class="sxs-lookup"><span data-stu-id="af698-278">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="af698-279">Добавьте первую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="af698-279">Add the first SRV record:</span></span>
    
    <span data-ttu-id="af698-280">В поля для новой записи в области **Create Record Set** (Создание набора записей) введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="af698-280">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="af698-281">Выберите в раскрывающихся списках значения параметров **Type** (Тип) и **Routing Policy** (Политика маршрутизации).</span><span class="sxs-lookup"><span data-stu-id="af698-281">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="af698-282">**Name**</span><span class="sxs-lookup"><span data-stu-id="af698-282">**Name**</span></span>|<span data-ttu-id="af698-283">**Тип**</span><span class="sxs-lookup"><span data-stu-id="af698-283">**Type**</span></span>|<span data-ttu-id="af698-284">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="af698-284">**Alias**</span></span>|<span data-ttu-id="af698-285">**TTL (Seconds) (Срок жизни, в секундах)**</span><span class="sxs-lookup"><span data-stu-id="af698-285">**TTL (Seconds)**</span></span>|<span data-ttu-id="af698-286">**Value (Значение)**</span><span class="sxs-lookup"><span data-stu-id="af698-286">**Value**</span></span>|<span data-ttu-id="af698-287">**Routing Policy (Политика маршрутизации)**</span><span class="sxs-lookup"><span data-stu-id="af698-287">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="af698-288">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="af698-288">_sip._tls</span></span>|<span data-ttu-id="af698-289">SRV  указатель служб</span><span class="sxs-lookup"><span data-stu-id="af698-289">SRV - Service locator</span></span>|<span data-ttu-id="af698-290">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="af698-290">No</span></span>|<span data-ttu-id="af698-291">300</span><span class="sxs-lookup"><span data-stu-id="af698-291">300</span></span>|<span data-ttu-id="af698-292">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="af698-292">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="af698-293">**Это значение должно заканчиваться точкой (.).**></span><span class="sxs-lookup"><span data-stu-id="af698-293">**This value MUST end with a period (.)**></span></span><br> <span data-ttu-id="af698-294">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="af698-294">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="af698-295">Simple (Простая)</span><span class="sxs-lookup"><span data-stu-id="af698-295">Simple</span></span>|
    |<span data-ttu-id="af698-296">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="af698-296">_sipfederationtls._tcp</span></span>|<span data-ttu-id="af698-297">SRV  указатель служб</span><span class="sxs-lookup"><span data-stu-id="af698-297">SRV - Service locator</span></span>|<span data-ttu-id="af698-298">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="af698-298">No</span></span>|<span data-ttu-id="af698-299">300</span><span class="sxs-lookup"><span data-stu-id="af698-299">300</span></span>|<span data-ttu-id="af698-300">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="af698-300">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="af698-301">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="af698-301">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="af698-302">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="af698-302">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="af698-303">Простое</span><span class="sxs-lookup"><span data-stu-id="af698-303">Simple</span></span>|
   
    ![AWS — BP — configure – 5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. <span data-ttu-id="af698-305">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="af698-305">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. <span data-ttu-id="af698-307">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="af698-307">To add the other SRV record:</span></span>
    
    <span data-ttu-id="af698-308">На странице " **размещенные зоны** " выберите **создать набор записей**, создайте запись, используя значения из следующей строки таблицы, а затем еще раз нажмите кнопку **создать** , чтобы завершить эту запись.</span><span class="sxs-lookup"><span data-stu-id="af698-308">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="af698-p120">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="af698-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
