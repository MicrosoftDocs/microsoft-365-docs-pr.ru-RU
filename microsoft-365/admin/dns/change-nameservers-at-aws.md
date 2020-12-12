---
title: Изменение серверов доменных имен для microsoft с Amazon Web Services (AWS)
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
description: 'Узнайте, как настроить Майкрософт для управления своими записями DNS на сайте Amazon Web Services (AWS). '
ms.openlocfilehash: 4700557c40973ab051cced81c129197a826964ab
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658456"
---
# <a name="change-nameservers-to-set-up-microsoft-with-amazon-web-services-aws"></a><span data-ttu-id="5e6e9-103">Изменение серверов доменных имен для microsoft с Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="5e6e9-103">Change nameservers to set up Microsoft with Amazon Web Services (AWS)</span></span>

 <span data-ttu-id="5e6e9-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="5e6e9-105">Следуйте этим инструкциям, если вы хотите, чтобы корпорация Майкрософт управляет вашими записями DNS.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="5e6e9-106">(При этом вы можете управлять всеми своими записями [DNS microsoft на веб-сайте AWS.)](create-dns-records-at-aws.md)</span><span class="sxs-lookup"><span data-stu-id="5e6e9-106">(If you prefer, you can [manage all your Microsoft DNS records at AWS](create-dns-records-at-aws.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5e6e9-107">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="5e6e9-107">Add a TXT record for verification</span></span>

<span data-ttu-id="5e6e9-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5e6e9-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="5e6e9-p104">Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="5e6e9-114">На странице **"Ресурсы"** выберите **"Hosted Zones".**</span><span class="sxs-lookup"><span data-stu-id="5e6e9-114">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="5e6e9-115">На странице **"Hosted Zones" (Hosted Zones)** в столбце **"Имя** домена" выберите имя домена, который необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-115">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="5e6e9-116">Выберите **"Создать набор записей"**.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-116">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="5e6e9-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5e6e9-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="5e6e9-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="5e6e9-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5e6e9-121">**Имя**</span><span class="sxs-lookup"><span data-stu-id="5e6e9-121">**Name**</span></span> <br/> |<span data-ttu-id="5e6e9-122">**Тип**</span><span class="sxs-lookup"><span data-stu-id="5e6e9-122">**Type**</span></span> <br/> |<span data-ttu-id="5e6e9-123">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="5e6e9-123">**Alias**</span></span> <br/> |<span data-ttu-id="5e6e9-124">**TTL (Seconds) (Срок жизни, в секундах)**</span><span class="sxs-lookup"><span data-stu-id="5e6e9-124">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="5e6e9-125">**Value (Значение)**</span><span class="sxs-lookup"><span data-stu-id="5e6e9-125">**Value**</span></span> <br/> |<span data-ttu-id="5e6e9-126">**Routing Policy (Политика маршрутизации)**</span><span class="sxs-lookup"><span data-stu-id="5e6e9-126">**Routing Policy**</span></span> <br/> |
|<span data-ttu-id="5e6e9-127">(Оставьте это поле пустым)</span><span class="sxs-lookup"><span data-stu-id="5e6e9-127">(Leave this field empty)</span></span>  <br/> |<span data-ttu-id="5e6e9-128">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="5e6e9-128">TXT - Text</span></span>  <br/> |<span data-ttu-id="5e6e9-129">Нет</span><span class="sxs-lookup"><span data-stu-id="5e6e9-129">No</span></span>  <br/> |<span data-ttu-id="5e6e9-130">300</span><span class="sxs-lookup"><span data-stu-id="5e6e9-130">300</span></span>  <br/> |<span data-ttu-id="5e6e9-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5e6e9-131">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="5e6e9-132">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-132">**Note:** This is an example.</span></span> <span data-ttu-id="5e6e9-133">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="5e6e9-134">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="5e6e9-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  <br/>  |<span data-ttu-id="5e6e9-135">Simple (Простая)</span><span class="sxs-lookup"><span data-stu-id="5e6e9-135">Simple</span></span> <br/> |
   
6. <span data-ttu-id="5e6e9-136">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-136">Select **Create**.</span></span>
    
7. <span data-ttu-id="5e6e9-137">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="5e6e9-138">Теперь, когда вы добавили запись на сайте регистратора доменных имен, вы вернемся в корпорацию Майкрософт и запросите поиск записи.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="5e6e9-139">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5e6e9-140">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="5e6e9-141">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="5e6e9-142">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="5e6e9-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="5e6e9-143">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="5e6e9-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5e6e9-p107">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5e6e9-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="5e6e9-147">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="5e6e9-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="5e6e9-148">Чтобы завершить настройку домена с помощью Майкрософт, измените записи сервера доменных имен своего домена у регистратора доменных имен, чтобы они указать на основной и дополнительный серверы доменных имен Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-148">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="5e6e9-149">Это настраивает Майкрософт для обновления записей DNS домена за вас.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-149">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="5e6e9-150">Мы добавим все записи, так что электронная почта, Skype для бизнеса online и общедоступный веб-сайт будут работать в вашем домене и вам больше не придется ничего настраивать.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-150">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="5e6e9-151">При изменении записей сервера доменных имен таким образом, чтобы они указывают на серверы доменных имен Майкрософт, это влияет на все службы, связанные с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-151">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="5e6e9-152">Например, все сообщения электронной почты, отправленные на ваш домен (например, rob@ *your_domain*  .com), после внести это изменение в корпорацию Майкрософт начнут приходить в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-152">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="5e6e9-153">В следующей процедуре покажем, как удалить из списка любые другие нежелательные доменные имена, а также как добавить правильные доменные имена, если они еще не указаны.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-153">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="5e6e9-154">> После завершения действий, указанных в этом разделе, в списке должны быть указаны только следующие четыре > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5e6e9-154">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="5e6e9-155">Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="5e6e9-155">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="5e6e9-156">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-156">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="5e6e9-157">На странице **"Ресурсы"** выберите **"Hosted Zones".**</span><span class="sxs-lookup"><span data-stu-id="5e6e9-157">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="5e6e9-158">На странице **"Hosted Zones" (Hosted Zones)** в столбце **"Имя** домена" выберите имя домена, который необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-158">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="5e6e9-159">Выберите набор записей **сервера доменных имен**.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-159">Select the **Nameserver** record set.</span></span> 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. <span data-ttu-id="5e6e9-161">Для набора записей **NS - Name server** (NS -сервер доменных имен) в поле **Value** (Значение) удалите все серверы доменных имен (выберите их все и нажмите клавишу **DELETE** на клавиатуре).</span><span class="sxs-lookup"><span data-stu-id="5e6e9-161">In the **NS - Name server** record set in the **Value** box, delete all of the nameservers by selecting them all and then pressing the **Delete** key on your keyboard.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="5e6e9-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="5e6e9-163">(То есть удалите только те текущие  доменные имена, которые не **ns1.bdm.microsoftonline.com,** **ns2.bdm.microsoftonline.com,** **ns3.bdm.microsoftonline.com** или **ns4.bdm.microsoftonline.com.)**</span><span class="sxs-lookup"><span data-stu-id="5e6e9-163">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. <span data-ttu-id="5e6e9-165">В области **TTL (Секунды):** выберите **1 ч** (1 час).</span><span class="sxs-lookup"><span data-stu-id="5e6e9-165">In the **TTL (Seconds):** area, select **1h** (1 Hour).</span></span> 
    
    ![Выберите 1H в течение одного часа](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. <span data-ttu-id="5e6e9-167">В том же наборе записей **NS - Name server** (NS  сервер доменных имен) в том же поле **Value** (Значение) введите (или скопируйте и вставьте) значение **первой строки** из показанной ниже таблицы, а затем нажмите клавишу **ВВОД** и введите (или скопируйте и вставьте) значение **следующей строки**.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-167">Still in the **NS - Name server** record set, in the **Value** box, type or copy and paste the **First line** value from the following table, then press the **Enter** key on your keyboard and type or copy and paste the next **line** value.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="5e6e9-168">Каждое значение сервера доменных имен  *необходимо*  указывать в отдельной строке в поле **Value** (Значение), как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-168">Each nameserver value  *must*  be on its own separate line within the **Value** box, as shown in the following illustration.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="5e6e9-169">**Первая строка**</span><span class="sxs-lookup"><span data-stu-id="5e6e9-169">**First line**</span></span> <br/> |<span data-ttu-id="5e6e9-170">ns1.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-170">ns1.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="5e6e9-171">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="5e6e9-171">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="5e6e9-172">**Вторая строка**</span><span class="sxs-lookup"><span data-stu-id="5e6e9-172">**Second line**</span></span> <br/> |<span data-ttu-id="5e6e9-173">ns2.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-173">ns2.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="5e6e9-174">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="5e6e9-174">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="5e6e9-175">**Третья строка**</span><span class="sxs-lookup"><span data-stu-id="5e6e9-175">**Third line**</span></span> <br/> |<span data-ttu-id="5e6e9-176">ns3.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-176">ns3.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="5e6e9-177">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="5e6e9-177">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="5e6e9-178">**Четвертая строка**</span><span class="sxs-lookup"><span data-stu-id="5e6e9-178">**Fourth line**</span></span> <br/> |<span data-ttu-id="5e6e9-179">ns4.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-179">ns4.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="5e6e9-180">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="5e6e9-180">**This value MUST end with a period (.)**</span></span> <br/> |
   
   ![Введите или введите значение первой строки в поле "Значение"](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. <span data-ttu-id="5e6e9-182">Выберите **"Сохранить набор записей".**</span><span class="sxs-lookup"><span data-stu-id="5e6e9-182">Select **Save Record Set**.</span></span>
    
    ![Выбор "Сохранить набор записей"](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> <span data-ttu-id="5e6e9-184">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-184">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="5e6e9-185">Затем ваша почта Майкрософт и другие службы будут настроены для работы с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="5e6e9-185">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
