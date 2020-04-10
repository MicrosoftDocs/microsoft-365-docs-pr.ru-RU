---
title: Изменение серверов доменных имен для настройки Office 365 с помощью веб-служб Amazon
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
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: 'Узнайте, как настроить Office 365 для управления записями DNS в веб-службах Amazon (AWS). '
ms.openlocfilehash: a7125cf0add8200fe152c426f47e7f27a8f6226c
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212357"
---
# <a name="change-nameservers-to-set-up-office-365-with-amazon-web-services-aws"></a><span data-ttu-id="0c627-103">Изменение серверов доменных имен для настройки Office 365 с помощью веб-служб Amazon</span><span class="sxs-lookup"><span data-stu-id="0c627-103">Change nameservers to set up Office 365 with Amazon Web Services (AWS)</span></span>

 <span data-ttu-id="0c627-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="0c627-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="0c627-p101">Следуя этим инструкциям, вы можете передать управление своими записями DNS для Office 365 в Office 365. (При желании вы можете самостоятельно [управлять всеми своими записями DNS для Office 365 на сайте AWS](create-dns-records-at-aws.md).)</span><span class="sxs-lookup"><span data-stu-id="0c627-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at AWS](create-dns-records-at-aws.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="0c627-107">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="0c627-107">Add a TXT record for verification</span></span>

<span data-ttu-id="0c627-p102">Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="0c627-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0c627-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="0c627-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="0c627-p104">Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="0c627-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0c627-114">На странице **ресурсы** выберите пункт **размещенные зоны**.</span><span class="sxs-lookup"><span data-stu-id="0c627-114">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="0c627-115">На странице " **размещенные зоны** " в столбце **доменное имя** выберите доменное имя, которое требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="0c627-115">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="0c627-116">Выберите **создать набор записей**.</span><span class="sxs-lookup"><span data-stu-id="0c627-116">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="0c627-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="0c627-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0c627-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="0c627-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="0c627-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="0c627-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0c627-121">**Имя**</span><span class="sxs-lookup"><span data-stu-id="0c627-121">**Name**</span></span> <br/> |<span data-ttu-id="0c627-122">**Тип**</span><span class="sxs-lookup"><span data-stu-id="0c627-122">**Type**</span></span> <br/> |<span data-ttu-id="0c627-123">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="0c627-123">**Alias**</span></span> <br/> |<span data-ttu-id="0c627-124">**TTL (Seconds) (Срок жизни, в секундах)**</span><span class="sxs-lookup"><span data-stu-id="0c627-124">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="0c627-125">**Value (Значение)**</span><span class="sxs-lookup"><span data-stu-id="0c627-125">**Value**</span></span> <br/> |<span data-ttu-id="0c627-126">**Routing Policy (Политика маршрутизации)**</span><span class="sxs-lookup"><span data-stu-id="0c627-126">**Routing Policy**</span></span> <br/> |
|<span data-ttu-id="0c627-127">(Оставьте это поле пустым)</span><span class="sxs-lookup"><span data-stu-id="0c627-127">(Leave this field empty)</span></span>  <br/> |<span data-ttu-id="0c627-128">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="0c627-128">TXT - Text</span></span>  <br/> |<span data-ttu-id="0c627-129">Нет</span><span class="sxs-lookup"><span data-stu-id="0c627-129">No</span></span>  <br/> |<span data-ttu-id="0c627-130">300</span><span class="sxs-lookup"><span data-stu-id="0c627-130">300</span></span>  <br/> |<span data-ttu-id="0c627-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="0c627-131">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="0c627-132">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="0c627-132">**Note:** This is an example.</span></span> <span data-ttu-id="0c627-133">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="0c627-133">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="0c627-134">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="0c627-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  <br/>  |<span data-ttu-id="0c627-135">Simple (Простая)</span><span class="sxs-lookup"><span data-stu-id="0c627-135">Simple</span></span> <br/> |
   
6. <span data-ttu-id="0c627-136">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="0c627-136">Select **Create**.</span></span>
    
7. <span data-ttu-id="0c627-137">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="0c627-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="0c627-138">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Office 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="0c627-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="0c627-139">Если Office 365 обнаружит правильную запись TXT, это значит, что домен проверен.</span><span class="sxs-lookup"><span data-stu-id="0c627-139">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="0c627-140">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="0c627-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="0c627-141">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="0c627-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="0c627-142">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="0c627-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="0c627-143">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="0c627-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0c627-p107">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0c627-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="0c627-147">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="0c627-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="0c627-p108">Чтобы завершить настройку домена для использования в Office 365, измените для него записи серверов имен на сайте вашего регистратора доменных имен таким образом, чтобы они указывали на основной и дополнительный DNS-серверы Office 365. После этого Office 365 обновит записи DNS для вашего домена. Мы добавим все записи, так что электронная почта, Skype для бизнеса online и общедоступный веб-сайт будут работать в вашем домене и вам больше не придется ничего настраивать.</span><span class="sxs-lookup"><span data-stu-id="0c627-p108">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="0c627-p109">Когда вы изменяете записи серверов имен своего домена, чтобы они указывали на DNS-серверы Office 365, это оказывает влияние на все службы, которые в настоящий момент связаны с доменом. Например, все сообщения электронной почты, отправленные на адреса в вашем домене (вида kirill@ *ваш_домен*  .com), после этого изменения будут попадать в Office 365.</span><span class="sxs-lookup"><span data-stu-id="0c627-p109">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="0c627-153">В следующей процедуре показано, как удалить любые другие нежелательные серверов доменных имен из списка, а также как добавить правильный серверов доменных имен, если они еще не указаны.</span><span class="sxs-lookup"><span data-stu-id="0c627-153">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="0c627-154">> после выполнения действий, описанных в этом разделе, необходимо указать только следующие четыре серверов доменных имен: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="0c627-154">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="0c627-155">Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="0c627-155">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="0c627-156">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="0c627-156">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0c627-157">На странице **ресурсы** выберите пункт **размещенные зоны**.</span><span class="sxs-lookup"><span data-stu-id="0c627-157">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="0c627-158">На странице " **размещенные зоны** " в столбце **доменное имя** выберите доменное имя, которое требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="0c627-158">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="0c627-159">Выберите набор записей **сервера доменных имен**.</span><span class="sxs-lookup"><span data-stu-id="0c627-159">Select the **Nameserver** record set.</span></span> 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. <span data-ttu-id="0c627-161">Для набора записей **NS - Name server** (NS -сервер доменных имен) в поле **Value** (Значение) удалите все серверы доменных имен (выберите их все и нажмите клавишу **DELETE** на клавиатуре).</span><span class="sxs-lookup"><span data-stu-id="0c627-161">In the **NS - Name server** record set in the **Value** box, delete all of the nameservers by selecting them all and then pressing the **Delete** key on your keyboard.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="0c627-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="0c627-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="0c627-163">(То есть удалите только те текущие серверов доменных имен, которые *не* называются **NS1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**или **NS4.BDM.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="0c627-163">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. <span data-ttu-id="0c627-165">В области **TTL (секунды):** выберите **1h** (1 час).</span><span class="sxs-lookup"><span data-stu-id="0c627-165">In the **TTL (Seconds):** area, select **1h** (1 Hour).</span></span> 
    
    ![Выберите 1H в течение одного часа](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. <span data-ttu-id="0c627-167">В том же наборе записей **NS - Name server** (NS  сервер доменных имен) в том же поле **Value** (Значение) введите (или скопируйте и вставьте) значение **первой строки** из показанной ниже таблицы, а затем нажмите клавишу **ВВОД** и введите (или скопируйте и вставьте) значение **следующей строки**.</span><span class="sxs-lookup"><span data-stu-id="0c627-167">Still in the **NS - Name server** record set, in the **Value** box, type or copy and paste the **First line** value from the following table, then press the **Enter** key on your keyboard and type or copy and paste the next **line** value.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="0c627-168">Каждое значение сервера доменных имен  *необходимо*  указывать в отдельной строке в поле **Value** (Значение), как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="0c627-168">Each nameserver value  *must*  be on its own separate line within the **Value** box, as shown in the following illustration.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0c627-169">**Первая строка**</span><span class="sxs-lookup"><span data-stu-id="0c627-169">**First line**</span></span> <br/> |<span data-ttu-id="0c627-170">ns1.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="0c627-170">ns1.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="0c627-171">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="0c627-171">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="0c627-172">**Вторая строка**</span><span class="sxs-lookup"><span data-stu-id="0c627-172">**Second line**</span></span> <br/> |<span data-ttu-id="0c627-173">ns2.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="0c627-173">ns2.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="0c627-174">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="0c627-174">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="0c627-175">**Третья строка**</span><span class="sxs-lookup"><span data-stu-id="0c627-175">**Third line**</span></span> <br/> |<span data-ttu-id="0c627-176">ns3.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="0c627-176">ns3.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="0c627-177">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="0c627-177">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="0c627-178">**Четвертая строка**</span><span class="sxs-lookup"><span data-stu-id="0c627-178">**Fourth line**</span></span> <br/> |<span data-ttu-id="0c627-179">ns4.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="0c627-179">ns4.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="0c627-180">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="0c627-180">**This value MUST end with a period (.)**</span></span> <br/> |
   
   ![Введите или вставьте значение первой строки в поле значение.](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. <span data-ttu-id="0c627-182">Выберите **сохранить набор записей**.</span><span class="sxs-lookup"><span data-stu-id="0c627-182">Select **Save Record Set**.</span></span>
    
    ![Выберите сохранить набор записей](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> <span data-ttu-id="0c627-p113">На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов. После этого ваша электронная почта и все остальные службы Office 365 будут настроены на работу с новым доменом.</span><span class="sxs-lookup"><span data-stu-id="0c627-p113">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
