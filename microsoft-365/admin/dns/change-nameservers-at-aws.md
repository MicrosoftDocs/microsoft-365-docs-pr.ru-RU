---
title: Изменение серверов доменных имен для настройки Майкрософт с помощью веб-служб Amazon (AWS)
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
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: 'Узнайте, как настроить Майкрософт для управления записями DNS в веб-службах Amazon (AWS). '
ms.openlocfilehash: 9f5bfd54020dfb793bbaad9aa8e081e87abc5ce8
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646491"
---
# <a name="change-nameservers-to-set-up-microsoft-with-amazon-web-services-aws"></a><span data-ttu-id="d992b-103">Изменение серверов доменных имен для настройки Майкрософт с помощью веб-служб Amazon (AWS)</span><span class="sxs-lookup"><span data-stu-id="d992b-103">Change nameservers to set up Microsoft with Amazon Web Services (AWS)</span></span>

 <span data-ttu-id="d992b-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="d992b-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d992b-105">Если вы хотите, чтобы корпорация Майкрософт управляла своими записями DNS, следуйте приведенным ниже инструкциям.</span><span class="sxs-lookup"><span data-stu-id="d992b-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="d992b-106">(При желании вы можете [управлять всеми своими записями Microsoft DNS на сайте AWS](create-dns-records-at-aws.md).)</span><span class="sxs-lookup"><span data-stu-id="d992b-106">(If you prefer, you can [manage all your Microsoft DNS records at AWS](create-dns-records-at-aws.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d992b-107">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="d992b-107">Add a TXT record for verification</span></span>

<span data-ttu-id="d992b-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="d992b-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d992b-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="d992b-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="d992b-p104">Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="d992b-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d992b-114">На странице **ресурсы** выберите пункт **размещенные зоны**.</span><span class="sxs-lookup"><span data-stu-id="d992b-114">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="d992b-115">На странице " **размещенные зоны** " в столбце **доменное имя** выберите доменное имя, которое требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="d992b-115">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="d992b-116">Выберите **создать набор записей**.</span><span class="sxs-lookup"><span data-stu-id="d992b-116">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="d992b-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d992b-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d992b-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="d992b-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="d992b-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="d992b-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d992b-121">**Имя**</span><span class="sxs-lookup"><span data-stu-id="d992b-121">**Name**</span></span> <br/> |<span data-ttu-id="d992b-122">**Тип**</span><span class="sxs-lookup"><span data-stu-id="d992b-122">**Type**</span></span> <br/> |<span data-ttu-id="d992b-123">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="d992b-123">**Alias**</span></span> <br/> |<span data-ttu-id="d992b-124">**TTL (Seconds) (Срок жизни, в секундах)**</span><span class="sxs-lookup"><span data-stu-id="d992b-124">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="d992b-125">**Value (Значение)**</span><span class="sxs-lookup"><span data-stu-id="d992b-125">**Value**</span></span> <br/> |<span data-ttu-id="d992b-126">**Routing Policy (Политика маршрутизации)**</span><span class="sxs-lookup"><span data-stu-id="d992b-126">**Routing Policy**</span></span> <br/> |
|<span data-ttu-id="d992b-127">(Оставьте это поле пустым)</span><span class="sxs-lookup"><span data-stu-id="d992b-127">(Leave this field empty)</span></span>  <br/> |<span data-ttu-id="d992b-128">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="d992b-128">TXT - Text</span></span>  <br/> |<span data-ttu-id="d992b-129">Нет</span><span class="sxs-lookup"><span data-stu-id="d992b-129">No</span></span>  <br/> |<span data-ttu-id="d992b-130">300</span><span class="sxs-lookup"><span data-stu-id="d992b-130">300</span></span>  <br/> |<span data-ttu-id="d992b-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d992b-131">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="d992b-132">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="d992b-132">**Note:** This is an example.</span></span> <span data-ttu-id="d992b-133">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="d992b-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="d992b-134">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="d992b-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  <br/>  |<span data-ttu-id="d992b-135">Simple (Простая)</span><span class="sxs-lookup"><span data-stu-id="d992b-135">Simple</span></span> <br/> |
   
6. <span data-ttu-id="d992b-136">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="d992b-136">Select **Create**.</span></span>
    
7. <span data-ttu-id="d992b-137">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="d992b-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d992b-138">Теперь, когда вы добавили запись на сайт регистратора доменных имен, вернитесь в корпорацию Майкрософт и запросите Поиск записи.</span><span class="sxs-lookup"><span data-stu-id="d992b-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="d992b-139">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="d992b-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d992b-140">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="d992b-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="d992b-141">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="d992b-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="d992b-142">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="d992b-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="d992b-143">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="d992b-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d992b-p107">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d992b-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="d992b-147">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="d992b-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="d992b-148">Чтобы завершить настройку домена с помощью корпорации Майкрософт, измените записи NS своего домена в регистраторе доменных имен, чтобы они ссылались на основной и дополнительный серверы имен Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d992b-148">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="d992b-149">Эта настройка позволяет настроить Microsoft для обновления записей DNS домена.</span><span class="sxs-lookup"><span data-stu-id="d992b-149">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="d992b-150">Мы добавим все записи, так что электронная почта, Skype для бизнеса online и общедоступный веб-сайт будут работать в вашем домене и вам больше не придется ничего настраивать.</span><span class="sxs-lookup"><span data-stu-id="d992b-150">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="d992b-151">Когда вы изменяете записи NS домена так, чтобы они ссылались на серверы имен Майкрософт, затрагиваются все службы, связанные с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="d992b-151">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="d992b-152">Например, все сообщения электронной почты, отправленные в ваш домен (например, rob@ *your_domain*  . com), появятся в корпорацию Майкрософт после внесения этого изменения.</span><span class="sxs-lookup"><span data-stu-id="d992b-152">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="d992b-153">В следующей процедуре показано, как удалить любые другие нежелательные серверов доменных имен из списка, а также как добавить правильный серверов доменных имен, если они еще не указаны.</span><span class="sxs-lookup"><span data-stu-id="d992b-153">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="d992b-154">> после выполнения действий, описанных в этом разделе, необходимо указать только следующие четыре серверов доменных имен: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="d992b-154">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="d992b-155">Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="d992b-155">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="d992b-156">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="d992b-156">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d992b-157">На странице **ресурсы** выберите пункт **размещенные зоны**.</span><span class="sxs-lookup"><span data-stu-id="d992b-157">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="d992b-158">На странице " **размещенные зоны** " в столбце **доменное имя** выберите доменное имя, которое требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="d992b-158">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="d992b-159">Выберите набор записей **сервера доменных имен**.</span><span class="sxs-lookup"><span data-stu-id="d992b-159">Select the **Nameserver** record set.</span></span> 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. <span data-ttu-id="d992b-161">Для набора записей **NS - Name server** (NS -сервер доменных имен) в поле **Value** (Значение) удалите все серверы доменных имен (выберите их все и нажмите клавишу **DELETE** на клавиатуре).</span><span class="sxs-lookup"><span data-stu-id="d992b-161">In the **NS - Name server** record set in the **Value** box, delete all of the nameservers by selecting them all and then pressing the **Delete** key on your keyboard.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="d992b-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="d992b-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="d992b-163">(То есть удалите только те текущие серверов доменных имен, которые  *не*  называются **NS1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**или **NS4.BDM.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="d992b-163">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. <span data-ttu-id="d992b-165">В области **TTL (секунды):** выберите **1h** (1 час).</span><span class="sxs-lookup"><span data-stu-id="d992b-165">In the **TTL (Seconds):** area, select **1h** (1 Hour).</span></span> 
    
    ![Выберите 1H в течение одного часа](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. <span data-ttu-id="d992b-167">В том же наборе записей **NS - Name server** (NS  сервер доменных имен) в том же поле **Value** (Значение) введите (или скопируйте и вставьте) значение **первой строки** из показанной ниже таблицы, а затем нажмите клавишу **ВВОД** и введите (или скопируйте и вставьте) значение **следующей строки**.</span><span class="sxs-lookup"><span data-stu-id="d992b-167">Still in the **NS - Name server** record set, in the **Value** box, type or copy and paste the **First line** value from the following table, then press the **Enter** key on your keyboard and type or copy and paste the next **line** value.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="d992b-168">Каждое значение сервера доменных имен  *необходимо*  указывать в отдельной строке в поле **Value** (Значение), как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="d992b-168">Each nameserver value  *must*  be on its own separate line within the **Value** box, as shown in the following illustration.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d992b-169">**Первая строка**</span><span class="sxs-lookup"><span data-stu-id="d992b-169">**First line**</span></span> <br/> |<span data-ttu-id="d992b-170">ns1.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="d992b-170">ns1.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="d992b-171">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="d992b-171">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="d992b-172">**Вторая строка**</span><span class="sxs-lookup"><span data-stu-id="d992b-172">**Second line**</span></span> <br/> |<span data-ttu-id="d992b-173">ns2.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="d992b-173">ns2.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="d992b-174">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="d992b-174">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="d992b-175">**Третья строка**</span><span class="sxs-lookup"><span data-stu-id="d992b-175">**Third line**</span></span> <br/> |<span data-ttu-id="d992b-176">ns3.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="d992b-176">ns3.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="d992b-177">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="d992b-177">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="d992b-178">**Четвертая строка**</span><span class="sxs-lookup"><span data-stu-id="d992b-178">**Fourth line**</span></span> <br/> |<span data-ttu-id="d992b-179">ns4.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="d992b-179">ns4.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="d992b-180">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="d992b-180">**This value MUST end with a period (.)**</span></span> <br/> |
   
   ![Введите или вставьте значение первой строки в поле значение.](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. <span data-ttu-id="d992b-182">Выберите **сохранить набор записей**.</span><span class="sxs-lookup"><span data-stu-id="d992b-182">Select **Save Record Set**.</span></span>
    
    ![Выберите сохранить набор записей](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> <span data-ttu-id="d992b-184">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="d992b-184">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="d992b-185">После этого ваша электронная почта Майкрософт и другие службы будут настроены для работы с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="d992b-185">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
