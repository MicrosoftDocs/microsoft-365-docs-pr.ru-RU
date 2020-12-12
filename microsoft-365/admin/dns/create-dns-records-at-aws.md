---
title: Создание записей DNS для Майкрософт на сайте Amazon Web Services (AWS)
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Amazon Web Services (AWS) for Microsoft.
ms.openlocfilehash: bb687b8685aed79f5f768c12d652205bbbed0f59
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657976"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-microsoft"></a><span data-ttu-id="3481b-103">Создание записей DNS для Майкрософт на сайте Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="3481b-103">Create DNS records at Amazon Web Services (AWS) for Microsoft</span></span>

 <span data-ttu-id="3481b-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="3481b-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="3481b-105">Если ваш поставщик услуг размещения DNS AWS, выполните действия, которые необходимо в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype Online для бизнеса и других служб.</span><span class="sxs-lookup"><span data-stu-id="3481b-105">If AWS is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype Online for Business, and so on.</span></span>
  
<span data-ttu-id="3481b-106">После добавления этих записей на веб-сайте AWS ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3481b-106">After you add these records at AWS, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="3481b-p101">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3481b-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="3481b-110">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="3481b-110">Add a TXT record for verification</span></span>
<span data-ttu-id="3481b-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="3481b-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="3481b-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="3481b-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3481b-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="3481b-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="3481b-p104">Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="3481b-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="3481b-118">На странице **"Ресурсы"** выберите **"Hosted Zones".**</span><span class="sxs-lookup"><span data-stu-id="3481b-118">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="3481b-119">На странице **"Hosted Zones" (Hosted Zones)** в столбце **"Имя** домена" выберите имя домена, который необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="3481b-119">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="3481b-120">Выберите **"Создать набор записей"**.</span><span class="sxs-lookup"><span data-stu-id="3481b-120">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="3481b-121">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3481b-121">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3481b-122">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="3481b-122">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="3481b-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="3481b-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3481b-125">**Имя**</span><span class="sxs-lookup"><span data-stu-id="3481b-125">**Name**</span></span> <br/> |<span data-ttu-id="3481b-126">**Тип**</span><span class="sxs-lookup"><span data-stu-id="3481b-126">**Type**</span></span> <br/> |<span data-ttu-id="3481b-127">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="3481b-127">**Alias**</span></span> <br/> |<span data-ttu-id="3481b-128">**TTL (Seconds) (Срок жизни, в секундах)**</span><span class="sxs-lookup"><span data-stu-id="3481b-128">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="3481b-129">**Value (Значение)**</span><span class="sxs-lookup"><span data-stu-id="3481b-129">**Value**</span></span> <br/> |<span data-ttu-id="3481b-130">**Routing Policy (Политика маршрутизации)**</span><span class="sxs-lookup"><span data-stu-id="3481b-130">**Routing Policy**</span></span> <br/> |
    |<span data-ttu-id="3481b-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="3481b-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="3481b-132">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="3481b-132">TXT - Text</span></span>  <br/> |<span data-ttu-id="3481b-133">Нет</span><span class="sxs-lookup"><span data-stu-id="3481b-133">No</span></span>  <br/> |<span data-ttu-id="3481b-134">300</span><span class="sxs-lookup"><span data-stu-id="3481b-134">300</span></span>  <br/> |<span data-ttu-id="3481b-135">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="3481b-135">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="3481b-136">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="3481b-136">**Note:** This is an example.</span></span> <span data-ttu-id="3481b-137">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3481b-137">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="3481b-138">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="3481b-138">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="3481b-139">Simple (Простая)</span><span class="sxs-lookup"><span data-stu-id="3481b-139">Simple</span></span>  <br/> |
   
6. <span data-ttu-id="3481b-140">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="3481b-140">Select **Create**.</span></span>
    
7. <span data-ttu-id="3481b-141">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="3481b-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="3481b-142">Теперь, когда вы добавили запись на сайте регистратора доменных имен, вы вернемся в корпорацию Майкрософт и запросите поиск записи.</span><span class="sxs-lookup"><span data-stu-id="3481b-142">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="3481b-143">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="3481b-143">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="3481b-144">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="3481b-144">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="3481b-145">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="3481b-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="3481b-146">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="3481b-146">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="3481b-147">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="3481b-147">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3481b-p107">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3481b-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a><span data-ttu-id="3481b-151">Добавьте запись MX, чтобы электронная почта для вашего домена была отправлена в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3481b-151">Add an MX record so email for your domain will come to Microsoft 365</span></span>
<span data-ttu-id="3481b-152"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="3481b-152"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="3481b-p108">Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="3481b-p108">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="3481b-155">На странице **"Ресурсы"** выберите **"Hosted Zones".**</span><span class="sxs-lookup"><span data-stu-id="3481b-155">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="3481b-156">На странице **"Hosted Zones" (Hosted Zones)** в столбце **"Имя** домена" выберите имя домена, который необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="3481b-156">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="3481b-157">Выберите **"Создать набор записей".**</span><span class="sxs-lookup"><span data-stu-id="3481b-157">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="3481b-158">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3481b-158">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3481b-159">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="3481b-159">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="3481b-160">**Имя**</span><span class="sxs-lookup"><span data-stu-id="3481b-160">**Name**</span></span>|<span data-ttu-id="3481b-161">**Тип**</span><span class="sxs-lookup"><span data-stu-id="3481b-161">**Type**</span></span>|<span data-ttu-id="3481b-162">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="3481b-162">**Alias**</span></span>|<span data-ttu-id="3481b-163">**TTL (Seconds) (Срок жизни, в секундах)**</span><span class="sxs-lookup"><span data-stu-id="3481b-163">**TTL (Seconds)**</span></span>|<span data-ttu-id="3481b-164">**Value (Значение)**</span><span class="sxs-lookup"><span data-stu-id="3481b-164">**Value**</span></span>|<span data-ttu-id="3481b-165">**Routing Policy (Политика маршрутизации)**</span><span class="sxs-lookup"><span data-stu-id="3481b-165">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3481b-166">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="3481b-166">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="3481b-167">MX  почтовый обменник</span><span class="sxs-lookup"><span data-stu-id="3481b-167">MX - Mail exchange</span></span>  <br/> |<span data-ttu-id="3481b-168">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="3481b-168">No</span></span>  <br/> |<span data-ttu-id="3481b-169">300</span><span class="sxs-lookup"><span data-stu-id="3481b-169">300</span></span>  <br/> |<span data-ttu-id="3481b-170">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="3481b-170">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="3481b-p109">0  значение приоритета MX. Добавьте его в начало значения MX, отделив от остальной части пробелом.  </span><span class="sxs-lookup"><span data-stu-id="3481b-p109">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="3481b-173">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="3481b-173">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="3481b-174">**Примечание.** Получите свою \<*domain-key*\> учетную запись Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3481b-174">**Note:** Get your \<*domain-key*\> from your Microsoft 365 account.</span></span> [<span data-ttu-id="3481b-175">Как найти это значение?</span><span class="sxs-lookup"><span data-stu-id="3481b-175">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="3481b-176">Simple (Простая)</span><span class="sxs-lookup"><span data-stu-id="3481b-176">Simple</span></span>  <br/> |
       
    ![AWS-BP-Configure-2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. <span data-ttu-id="3481b-178">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="3481b-178">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. <span data-ttu-id="3481b-180">Если есть другие записи MX, удалите их.</span><span class="sxs-lookup"><span data-stu-id="3481b-180">If there are any other MX records, remove them.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="3481b-181">AWS хранит записи MX в виде наборов, которые могут содержать сразу несколько записей.</span><span class="sxs-lookup"><span data-stu-id="3481b-181">AWS stores MX records as a set that may contain multiple records.</span></span> <span data-ttu-id="3481b-182">**НЕ выбирайте** **"Удалить набор записей",** так как при этом будут удаляться все записи MX, в том числе только что добавленные.</span><span class="sxs-lookup"><span data-stu-id="3481b-182">**DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added.</span></span> <span data-ttu-id="3481b-183">Вместо этого сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="3481b-183">Use the following instructions instead.</span></span> 
  
    <span data-ttu-id="3481b-184">Сначала выберите набор записей MX.</span><span class="sxs-lookup"><span data-stu-id="3481b-184">First, select the MX record set.</span></span>
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    <span data-ttu-id="3481b-186">Затем в области **Edit Record Set** (Изменить набор записей) удалите каждую из устаревших записей MX, выбрав ее в поле **Value** (Значение) и нажав клавишу **DELETE**.</span><span class="sxs-lookup"><span data-stu-id="3481b-186">Next, in the **Edit Record Set** area, delete each obsolete MX record by selecting the entry in the **Value** box and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. <span data-ttu-id="3481b-188">Выберите **"Сохранить набор записей".**</span><span class="sxs-lookup"><span data-stu-id="3481b-188">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="3481b-190">Добавьте пять записей CNAME, необходимых для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3481b-190">Add the five CNAME records that are required for Microsoft 365</span></span>
<span data-ttu-id="3481b-191"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="3481b-191"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="3481b-p112">Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="3481b-p112">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="3481b-194">На странице **"Ресурсы"** выберите **"Hosted Zones".**</span><span class="sxs-lookup"><span data-stu-id="3481b-194">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="3481b-195">На странице **"Hosted Zones" (Hosted Zones)** в столбце **"Имя** домена" выберите имя домена, который необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="3481b-195">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="3481b-196">Выберите **"Создать набор записей"**.</span><span class="sxs-lookup"><span data-stu-id="3481b-196">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="3481b-197">Добавьте первую запись CNAME.</span><span class="sxs-lookup"><span data-stu-id="3481b-197">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="3481b-198">В поля для новой записи в области **Create Record Set** (Создание набора записей) введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="3481b-198">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="3481b-199">Выберите в раскрывающихся списках значения параметров **Type** (Тип) и **Routing Policy** (Политика маршрутизации).</span><span class="sxs-lookup"><span data-stu-id="3481b-199">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="3481b-200">**Имя**</span><span class="sxs-lookup"><span data-stu-id="3481b-200">**Name**</span></span>|<span data-ttu-id="3481b-201">**Тип**</span><span class="sxs-lookup"><span data-stu-id="3481b-201">**Type**</span></span>|<span data-ttu-id="3481b-202">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="3481b-202">**Alias**</span></span>|<span data-ttu-id="3481b-203">**TTL (Seconds) (Срок жизни, в секундах)**</span><span class="sxs-lookup"><span data-stu-id="3481b-203">**TTL (Seconds)**</span></span>|<span data-ttu-id="3481b-204">**Value (Значение)**</span><span class="sxs-lookup"><span data-stu-id="3481b-204">**Value**</span></span>|<span data-ttu-id="3481b-205">**Routing Policy (Политика маршрутизации)**</span><span class="sxs-lookup"><span data-stu-id="3481b-205">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3481b-206">autodiscover</span><span class="sxs-lookup"><span data-stu-id="3481b-206">autodiscover</span></span>  <br/> |<span data-ttu-id="3481b-207">CNAME  каноническое имя</span><span class="sxs-lookup"><span data-stu-id="3481b-207">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="3481b-208">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="3481b-208">No</span></span>  <br/> |<span data-ttu-id="3481b-209">300</span><span class="sxs-lookup"><span data-stu-id="3481b-209">300</span></span>  <br/> |<span data-ttu-id="3481b-210">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="3481b-210">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="3481b-211">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="3481b-211">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="3481b-212">Simple (Простая)</span><span class="sxs-lookup"><span data-stu-id="3481b-212">Simple</span></span>  <br/> |
    |<span data-ttu-id="3481b-213">sip</span><span class="sxs-lookup"><span data-stu-id="3481b-213">sip</span></span>  <br/> |<span data-ttu-id="3481b-214">CNAME  каноническое имя</span><span class="sxs-lookup"><span data-stu-id="3481b-214">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="3481b-215">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="3481b-215">No</span></span>  <br/> |<span data-ttu-id="3481b-216">300</span><span class="sxs-lookup"><span data-stu-id="3481b-216">300</span></span>  <br/> |<span data-ttu-id="3481b-217">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3481b-217">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="3481b-218">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="3481b-218">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="3481b-219">Simple (Простая)</span><span class="sxs-lookup"><span data-stu-id="3481b-219">Simple</span></span>  <br/> |
    |<span data-ttu-id="3481b-220">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3481b-220">lyncdiscover</span></span>  <br/> |<span data-ttu-id="3481b-221">CNAME  каноническое имя</span><span class="sxs-lookup"><span data-stu-id="3481b-221">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="3481b-222">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="3481b-222">No</span></span>  <br/> |<span data-ttu-id="3481b-223">300</span><span class="sxs-lookup"><span data-stu-id="3481b-223">300</span></span>  <br/> |<span data-ttu-id="3481b-224">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3481b-224">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="3481b-225">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="3481b-225">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="3481b-226">Это совсем не сложно.</span><span class="sxs-lookup"><span data-stu-id="3481b-226">Simple</span></span>  <br/> |
    |<span data-ttu-id="3481b-227">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="3481b-227">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="3481b-228">CNAME  каноническое имя</span><span class="sxs-lookup"><span data-stu-id="3481b-228">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="3481b-229">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="3481b-229">No</span></span>  <br/> |<span data-ttu-id="3481b-230">300</span><span class="sxs-lookup"><span data-stu-id="3481b-230">300</span></span>  <br/> |<span data-ttu-id="3481b-231">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="3481b-231">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="3481b-232">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="3481b-232">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="3481b-233">Simple (Простая)</span><span class="sxs-lookup"><span data-stu-id="3481b-233">Simple</span></span>  <br/> |
    |<span data-ttu-id="3481b-234">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="3481b-234">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="3481b-235">CNAME  каноническое имя</span><span class="sxs-lookup"><span data-stu-id="3481b-235">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="3481b-236">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="3481b-236">No</span></span>  <br/> |<span data-ttu-id="3481b-237">300</span><span class="sxs-lookup"><span data-stu-id="3481b-237">300</span></span>  <br/> |<span data-ttu-id="3481b-238">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="3481b-238">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="3481b-239">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="3481b-239">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="3481b-240">Simple (Простая)</span><span class="sxs-lookup"><span data-stu-id="3481b-240">Simple</span></span>  <br/> |
   
    ![AWS-BP-Configure-3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. <span data-ttu-id="3481b-242">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="3481b-242">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. <span data-ttu-id="3481b-244">Добавьте остальные четыре записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="3481b-244">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="3481b-245">На странице  **"Hosted Zones" (Hosted Zones)** выберите "Создать набор записей", создайте запись, используя значения из следующей строки таблицы, и снова выберите "Создать", чтобы завершить запись. </span><span class="sxs-lookup"><span data-stu-id="3481b-245">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
    <span data-ttu-id="3481b-246">Повторяйте этот процесс, пока не создайте все пять записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="3481b-246">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="3481b-247">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="3481b-247">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="3481b-248"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="3481b-248"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="3481b-249">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="3481b-249">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="3481b-250">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="3481b-250">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="3481b-251">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3481b-251">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="3481b-252">Вместо этого добавьте необходимые значения Майкрософт в текущую  запись, чтобы иметь одну запись SPF, которая включает оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="3481b-252">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="3481b-253">Нужны примеры?</span><span class="sxs-lookup"><span data-stu-id="3481b-253">Need examples?</span></span> <span data-ttu-id="3481b-254">Ознакомьтесь с этими [записями системы внешних доменных имен для продуктов корпорации Майкрософт](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span><span class="sxs-lookup"><span data-stu-id="3481b-254">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="3481b-255">Для проверки записи SPF можно использовать одно из этих средств[проверки SPF.](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="3481b-255">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="3481b-256">Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="3481b-256">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="3481b-257">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="3481b-257">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="3481b-258">На странице **"Ресурсы"** выберите **"Hosted Zones".**</span><span class="sxs-lookup"><span data-stu-id="3481b-258">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="3481b-259">На странице **"Hosted Zones" (Hosted Zones)** в столбце **"Имя** домена" выберите имя домена, который необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="3481b-259">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="3481b-260">Выберите набор **записей TXT.**</span><span class="sxs-lookup"><span data-stu-id="3481b-260">Select the **TXT** record set.</span></span> 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. <span data-ttu-id="3481b-p115">В области **Edit Record Set** (Изменение набора записей) в конце текущего элемента в поле **Value:** (Значение) существующей записи нажмите клавишу ВВОД, чтобы перейти на новую строку, а затем в этой новой строке (под существующим значением) введите или вставьте значение из таблицы ниже. (Пример приведен на рисунке под таблицей.)</span><span class="sxs-lookup"><span data-stu-id="3481b-p115">In the **Edit Record Set** area, at the end of the current entry in the **Value:** box for the existing record, press Enter on your keyboard to create a new line; and then, on that new line (under the existing value), type or copy and paste the value from the following table. (You can see an example in the illustration below the table.)</span></span> 
    
    |<span data-ttu-id="3481b-264">**Значение:**</span><span class="sxs-lookup"><span data-stu-id="3481b-264">**Value:**</span></span>|
    |:-----|
    |<span data-ttu-id="3481b-265">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="3481b-265">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="3481b-p116">(Кавычки, которые требуются в инструкциях на экране, добавляются автоматически. Вводить их вручную не нужно.)  </span><span class="sxs-lookup"><span data-stu-id="3481b-p116">(The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.)  </span></span><br/> <span data-ttu-id="3481b-268">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="3481b-268">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![AWS-BP-Configure-4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. <span data-ttu-id="3481b-270">Выберите **"Сохранить набор записей".**</span><span class="sxs-lookup"><span data-stu-id="3481b-270">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="3481b-272">Добавьте две записи SRV, необходимые для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3481b-272">Add the two SRV records that are required for Microsoft 365</span></span>
<span data-ttu-id="3481b-273"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="3481b-273"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="3481b-p117">Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="3481b-p117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="3481b-276">На странице **"Ресурсы"** выберите **"Hosted Zones".**</span><span class="sxs-lookup"><span data-stu-id="3481b-276">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="3481b-277">На странице **"Hosted Zones" (Hosted Zones)** в столбце **"Имя** домена" выберите имя домена, который необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="3481b-277">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="3481b-278">Выберите **"Создать набор записей"**.</span><span class="sxs-lookup"><span data-stu-id="3481b-278">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="3481b-279">Добавьте первую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="3481b-279">Add the first SRV record:</span></span>
    
    <span data-ttu-id="3481b-280">В поля для новой записи в области **Create Record Set** (Создание набора записей) введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="3481b-280">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="3481b-281">Выберите в раскрывающихся списках значения параметров **Type** (Тип) и **Routing Policy** (Политика маршрутизации).</span><span class="sxs-lookup"><span data-stu-id="3481b-281">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="3481b-282">**Имя**</span><span class="sxs-lookup"><span data-stu-id="3481b-282">**Name**</span></span>|<span data-ttu-id="3481b-283">**Тип**</span><span class="sxs-lookup"><span data-stu-id="3481b-283">**Type**</span></span>|<span data-ttu-id="3481b-284">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="3481b-284">**Alias**</span></span>|<span data-ttu-id="3481b-285">**TTL (Seconds) (Срок жизни, в секундах)**</span><span class="sxs-lookup"><span data-stu-id="3481b-285">**TTL (Seconds)**</span></span>|<span data-ttu-id="3481b-286">**Value (Значение)**</span><span class="sxs-lookup"><span data-stu-id="3481b-286">**Value**</span></span>|<span data-ttu-id="3481b-287">**Routing Policy (Политика маршрутизации)**</span><span class="sxs-lookup"><span data-stu-id="3481b-287">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3481b-288">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="3481b-288">_sip._tls</span></span>|<span data-ttu-id="3481b-289">SRV  указатель служб</span><span class="sxs-lookup"><span data-stu-id="3481b-289">SRV - Service locator</span></span>|<span data-ttu-id="3481b-290">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="3481b-290">No</span></span>|<span data-ttu-id="3481b-291">300</span><span class="sxs-lookup"><span data-stu-id="3481b-291">300</span></span>|<span data-ttu-id="3481b-292">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3481b-292">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="3481b-293">**Это значение ДОЛЖНО заканчиваются периодом (.)**></span><span class="sxs-lookup"><span data-stu-id="3481b-293">**This value MUST end with a period (.)**></span></span><br> <span data-ttu-id="3481b-294">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="3481b-294">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="3481b-295">Simple (Простая)</span><span class="sxs-lookup"><span data-stu-id="3481b-295">Simple</span></span>|
    |<span data-ttu-id="3481b-296">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="3481b-296">_sipfederationtls._tcp</span></span>|<span data-ttu-id="3481b-297">SRV  указатель служб</span><span class="sxs-lookup"><span data-stu-id="3481b-297">SRV - Service locator</span></span>|<span data-ttu-id="3481b-298">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="3481b-298">No</span></span>|<span data-ttu-id="3481b-299">300</span><span class="sxs-lookup"><span data-stu-id="3481b-299">300</span></span>|<span data-ttu-id="3481b-300">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3481b-300">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="3481b-301">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="3481b-301">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="3481b-302">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="3481b-302">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="3481b-303">Простой</span><span class="sxs-lookup"><span data-stu-id="3481b-303">Simple</span></span>|
   
    ![AWS-BP-Configure-5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. <span data-ttu-id="3481b-305">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="3481b-305">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. <span data-ttu-id="3481b-307">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="3481b-307">To add the other SRV record:</span></span>
    
    <span data-ttu-id="3481b-308">На странице  **"Hosted Zones" (Hosted Zones)** выберите "Создать набор записей", создайте запись, используя значения из следующей строки таблицы, и снова выберите "Создать", чтобы завершить запись. </span><span class="sxs-lookup"><span data-stu-id="3481b-308">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="3481b-p120">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3481b-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
