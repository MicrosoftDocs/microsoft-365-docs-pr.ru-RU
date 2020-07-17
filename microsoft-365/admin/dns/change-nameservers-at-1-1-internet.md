---
title: Изменить серверов доменных имен, чтобы настроить Майкрософт с 1&1 ИОНОС
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
ms.assetid: 31efc571-c8b9-46fb-b42d-203c2fb25289
description: Узнайте, как настроить Office 365 под управлением 21Vianet для управления записями DNS, когда 1&1 Интернет-поставщик услуг хостинга DNS.
ms.openlocfilehash: 79870d534e7d825fd59dbbbec54c796227f5faf1
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780377"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-11-ionos"></a><span data-ttu-id="6eebc-103">Измените серверов доменных имен, чтобы настроить Microsoft 365 с 1&1 ИОНОС</span><span class="sxs-lookup"><span data-stu-id="6eebc-103">Change nameservers to set up Microsoft 365 with 1&1 IONOS</span></span>

 <span data-ttu-id="6eebc-104">Если вы не нашли то, что вы ищете, обратитесь к разделу **[вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="6eebc-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="6eebc-105">Следуйте этим инструкциям, если вы хотите, чтобы Microsoft 365 управляла записями DNS Майкрософт 365.</span><span class="sxs-lookup"><span data-stu-id="6eebc-105">Follow these instructions if you want Microsoft 365 to manage your Microsoft 365 DNS records for you.</span></span> <span data-ttu-id="6eebc-106">(При желании вы можете [управлять всеми своими записями DNS для Microsoft 365 на 1&1 ионос](create-dns-records-at-1-1-internet.md).)</span><span class="sxs-lookup"><span data-stu-id="6eebc-106">(If you prefer, you can [manage all your Microsoft 365 DNS records at 1&1 IONOS](create-dns-records-at-1-1-internet.md).)</span></span> 
  

    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="6eebc-107">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="6eebc-107">Add a TXT record for verification</span></span>


<span data-ttu-id="6eebc-p102">Прежде чем вы сможете использовать свой домен в Microsoft 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Microsoft 365 подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="6eebc-p102">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6eebc-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="6eebc-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="6eebc-112">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 0:42)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).</span><span class="sxs-lookup"><span data-stu-id="6eebc-112">Follow the steps below or [watch the video (start at 0:42)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).</span></span>
  
1. <span data-ttu-id="6eebc-113">Чтобы приступить к работе, перейдите на страницу с доменами по адресу 1&1 ИОНОС 1 с помощью [этой ссылки](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span><span class="sxs-lookup"><span data-stu-id="6eebc-113">To get started, go to your domains page at 1&1 IONOS via [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="6eebc-114">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="6eebc-114">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="6eebc-115">В разделе **Мои домены**выберите **Управление доменами**.</span><span class="sxs-lookup"><span data-stu-id="6eebc-115">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="6eebc-116">На странице " **центр домена** " найдите домен, который вы хотите обновить; затем выберите элемент управления **Panel** ( **v**) для этого домена.</span><span class="sxs-lookup"><span data-stu-id="6eebc-116">On the **Domain Center** page, find the domain that you want to update; then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="6eebc-117">В области **Параметры домена** выберите **изменить параметры DNS**.</span><span class="sxs-lookup"><span data-stu-id="6eebc-117">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="6eebc-118">В разделе **txt and SRV Records (записи TXT и SRV** ) выберите **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="6eebc-118">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
    <span data-ttu-id="6eebc-119">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="6eebc-119">(You may have to scroll down.)</span></span> 
    
6. <span data-ttu-id="6eebc-120">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="6eebc-120">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="6eebc-121">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="6eebc-121">**Type**</span></span> <br/> |<span data-ttu-id="6eebc-122">**Prefix (Префикс)**</span><span class="sxs-lookup"><span data-stu-id="6eebc-122">**Prefix**</span></span> <br/> |<span data-ttu-id="6eebc-123">**Name Value (Значение имени)**</span><span class="sxs-lookup"><span data-stu-id="6eebc-123">**Name Value**</span></span> <br/> |
|<span data-ttu-id="6eebc-124">TXT</span><span class="sxs-lookup"><span data-stu-id="6eebc-124">TXT</span></span>  <br/> |<span data-ttu-id="6eebc-125">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="6eebc-125">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="6eebc-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="6eebc-126">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="6eebc-127">**Примечание**: это пример.</span><span class="sxs-lookup"><span data-stu-id="6eebc-127">**Note**: This is an example.</span></span> <span data-ttu-id="6eebc-128">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6eebc-128">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="6eebc-129">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="6eebc-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
7. <span data-ttu-id="6eebc-130">Нажмите кнопку **сохранить**, а затем **Сохраните** еще раз.</span><span class="sxs-lookup"><span data-stu-id="6eebc-130">Select **Save**, and then **Save** again.</span></span> 
    
8. <span data-ttu-id="6eebc-131">В диалоговом окне **изменение параметров DNS** нажмите **кнопку Да**.</span><span class="sxs-lookup"><span data-stu-id="6eebc-131">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
9. <span data-ttu-id="6eebc-132">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="6eebc-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="6eebc-133">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Microsoft 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="6eebc-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="6eebc-134">Если Microsoft 365 обнаружит правильную запись TXT, это значит, что домен проверен.</span><span class="sxs-lookup"><span data-stu-id="6eebc-134">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="6eebc-135">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="6eebc-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="6eebc-136">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="6eebc-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="6eebc-137">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="6eebc-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="6eebc-138">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="6eebc-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6eebc-139">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="6eebc-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="6eebc-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="6eebc-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="6eebc-141">Если при добавлении записей DNS возникают проблемы с почтовыми сообщениями или другими проблемами, ознакомьтесь со статьей [Поиск и устранение проблем после добавления домена или записей DNS в Microsoft 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6eebc-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="6eebc-142">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="6eebc-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="6eebc-143">Чтобы завершить настройку домена с помощью Microsoft 365, измените записи NS домена в регистраторе доменных имен, чтобы они ссылались на основной и дополнительный серверы имен Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6eebc-143">To complete setting up your domain with Microsoft 365, you change your domain's NS records at your domain registrar to point to the Microsoft 365 primary and secondary name servers.</span></span> <span data-ttu-id="6eebc-144">При этом Microsoft 365 настраивается на обновление записей DNS домена.</span><span class="sxs-lookup"><span data-stu-id="6eebc-144">This sets up Microsoft 365 to update the domain's DNS records for you.</span></span> <span data-ttu-id="6eebc-145">Мы добавим все записи, так что электронная почта, Skype для бизнеса online и общедоступный веб-сайт будут работать в вашем домене и вам больше не придется ничего настраивать.</span><span class="sxs-lookup"><span data-stu-id="6eebc-145">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="6eebc-146">Когда вы изменяете записи NS домена так, чтобы они ссылались на серверы имен Microsoft 365, затрагиваются все службы, которые в настоящее время связаны с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="6eebc-146">When you change your domain's NS records to point to the Microsoft 365 name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="6eebc-147">Например, все сообщения электронной почты, отправленные в ваш домен (например, rob@ *your_domain* . com), появятся в Microsoft 365 после внесения этого изменения.</span><span class="sxs-lookup"><span data-stu-id="6eebc-147">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft 365 after you make this change.</span></span> 
  
<span data-ttu-id="6eebc-148">Вы готовы изменить записи сервера доменных имен, чтобы Microsoft 365 мог настроить ваш домен?</span><span class="sxs-lookup"><span data-stu-id="6eebc-148">Ready to change your NS records so Microsoft 365 can set up your domain?</span></span> <span data-ttu-id="6eebc-149">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 2:47)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).</span><span class="sxs-lookup"><span data-stu-id="6eebc-149">Follow the steps below or [watch the video (start at 2:47)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="6eebc-150">В следующей процедуре показано, как удалить любые другие нежелательные серверов доменных имен из списка, а также как добавить правильный серверов доменных имен, если они еще не указаны.</span><span class="sxs-lookup"><span data-stu-id="6eebc-150">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="6eebc-151">> после выполнения действий, описанных в этом разделе, необходимо указать только следующие четыре серверов доменных имен: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6eebc-151">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="6eebc-152">Чтобы приступить к работе, перейдите на страницу своих доменов по адресу 1&1 ИОНОС, используя [эту ссылку](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span><span class="sxs-lookup"><span data-stu-id="6eebc-152">To get started, go to your domains page at 1&1 IONOS by using [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="6eebc-153">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="6eebc-153">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="6eebc-154">В разделе **Мои домены**выберите **Управление доменами**.</span><span class="sxs-lookup"><span data-stu-id="6eebc-154">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="6eebc-155">На странице " **центр домена** " найдите домен, который необходимо обновить, а затем выберите элемент управления **Panel** ( **v**) для этого домена.</span><span class="sxs-lookup"><span data-stu-id="6eebc-155">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="6eebc-156">В области **Параметры домена** выберите **изменить параметры DNS**.</span><span class="sxs-lookup"><span data-stu-id="6eebc-156">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="6eebc-157">В разделе **Name Server Settings** (Параметры сервера доменных имен) выберите **Other name servers** (Другие серверы доменных имен).</span><span class="sxs-lookup"><span data-stu-id="6eebc-157">In the **Name Server Settings** section, select **Other name servers**.</span></span>
    
    <span data-ttu-id="6eebc-158">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="6eebc-158">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="6eebc-159">В зависимости от того, указаны ли уже серверы доменных имен на странице, которая отображается на экране, воспользуйтесь одной из двух процедур.</span><span class="sxs-lookup"><span data-stu-id="6eebc-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="6eebc-160">Если на странице **НЕ УКАЗАНЫ** серверы доменных имен, [На странице НЕ УКАЗАНЫ серверы доменных имен](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="6eebc-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="6eebc-161">Если на странице **УКАЗАНЫ** серверы доменных имен, [На странице УКАЗАНЫ серверы доменных имен](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="6eebc-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="6eebc-162">На странице НЕ УКАЗАНЫ серверы доменных имен</span><span class="sxs-lookup"><span data-stu-id="6eebc-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="6eebc-163">В поле **Name server 1** (Сервер доменных имен 1) введите (или скопируйте и вставьте) значение из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="6eebc-163">In the **Name server 1** box, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="6eebc-164">**Name server 1**</span><span class="sxs-lookup"><span data-stu-id="6eebc-164">**Name server 1**</span></span> <br/> |<span data-ttu-id="6eebc-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6eebc-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Ввод значения в поле "сервер имен 1"](../../media/34509935-461f-427f-9796-c3cf840bd9be.png)
  
2. <span data-ttu-id="6eebc-167">В раскрывающемся списке **Additional name servers** (Дополнительные серверы доменных имен) выберите **My secondary name servers** (Мои дополнительные серверы доменных имен).</span><span class="sxs-lookup"><span data-stu-id="6eebc-167">In the **Additional name servers** drop-down list, choose **My secondary name servers**.</span></span>
    
    ![Choosing My secondary name servers in the list](../../media/7eb14856-86da-45c2-910c-c72312250a18.png)
  
3. <span data-ttu-id="6eebc-169">В полях **Name server 2, 3, and 4** (Серверы доменных имен 2, 3 и 4) введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="6eebc-169">In the **Name server 2, 3, and 4** boxes, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="6eebc-170">**Name Server 2** (Сервер доменных имен 2)</span><span class="sxs-lookup"><span data-stu-id="6eebc-170">**Name server 2**</span></span> <br/> |<span data-ttu-id="6eebc-171">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6eebc-171">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6eebc-172">**Name Server 3** (Сервер доменных имен 3)</span><span class="sxs-lookup"><span data-stu-id="6eebc-172">**Name server 3**</span></span> <br/> |<span data-ttu-id="6eebc-173">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6eebc-173">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6eebc-174">**Name Server 4** (Сервер доменных имен 4)</span><span class="sxs-lookup"><span data-stu-id="6eebc-174">**Name server 4**</span></span> <br/> |<span data-ttu-id="6eebc-175">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6eebc-175">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
![Ввод значений сервера имен](../../media/0f15880c-88b6-4133-8f31-62f0d98ee63f.png)
  
4. <span data-ttu-id="6eebc-177">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="6eebc-177">Select **Save**.</span></span>
    
    ![Выбор параметра "Сохранить" на странице "Параметры сервера имен"](../../media/864f7927-7127-4784-b8d2-dadfea2f9dc8.png)
  
5. <span data-ttu-id="6eebc-179">В диалоговом окне **изменение параметров DNS** нажмите **кнопку Да**.</span><span class="sxs-lookup"><span data-stu-id="6eebc-179">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![Выбор параметра "Сохранить" в диалоговом окне изменения параметров DNS](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="6eebc-181">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="6eebc-181">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="6eebc-182">После этого ваша электронная почта Майкрософт и другие службы будут настроены для работы с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="6eebc-182">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="6eebc-183">На странице УКАЗАНЫ серверы доменных имен</span><span class="sxs-lookup"><span data-stu-id="6eebc-183">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="6eebc-p113">Выполните эти действия,  *только*  если у вас есть серверы доменных имен, отличные от четырех  *правильных*  серверов. (Т. е. удалите  *только*  серверы доменных имен,  *отличные*  от **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** и **ns4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="6eebc-p113">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="6eebc-186">Если в полях **Name server** (Сервер доменных имен) указаны другие серверы доменных имен, удалите их: выберите каждый из них и нажмите клавишу **DELETE**.</span><span class="sxs-lookup"><span data-stu-id="6eebc-186">If there are already nameservers listed in the **Name server** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting name servers](../../media/af0a68cc-b058-4925-b3b1-52dfded003c1.png)
  
2. <span data-ttu-id="6eebc-188">В полях **Name server 1, 2, 3, and 4** (Серверы доменных имен 1, 2, 3 и 4) введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="6eebc-188">In the **Name server 1, 2, 3, and 4** boxes, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="6eebc-189">**Name server 1** (Сервер доменных имен 1)</span><span class="sxs-lookup"><span data-stu-id="6eebc-189">**Name server 1**</span></span> <br/> |<span data-ttu-id="6eebc-190">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6eebc-190">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6eebc-191">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="6eebc-191">**Name server 2**</span></span> <br/> |<span data-ttu-id="6eebc-192">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6eebc-192">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6eebc-193">**Name Server 3** (Сервер доменных имен 3)</span><span class="sxs-lookup"><span data-stu-id="6eebc-193">**Name server 3**</span></span> <br/> |<span data-ttu-id="6eebc-194">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6eebc-194">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6eebc-195">**Name Server 4** (Сервер доменных имен 4)</span><span class="sxs-lookup"><span data-stu-id="6eebc-195">**Name server 4**</span></span> <br/> |<span data-ttu-id="6eebc-196">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6eebc-196">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Ввод значений сервера имен](../../media/52826bd1-0596-4103-a728-d5d28b9610d2.png)
  
3. <span data-ttu-id="6eebc-198">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="6eebc-198">Select **Save**.</span></span>
    
    ![Выбор параметра "Сохранить" на странице "Параметры сервера имен"](../../media/cd10e4fb-b7fa-480f-855b-a443f2705cf2.png)
  
4. <span data-ttu-id="6eebc-200">В диалоговом окне **изменение параметров DNS** нажмите **кнопку Да**.</span><span class="sxs-lookup"><span data-stu-id="6eebc-200">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![Выбор параметра "Сохранить" в диалоговом окне изменения параметров DNS](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="6eebc-202">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="6eebc-202">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="6eebc-203">После этого ваша электронная почта Майкрософт и другие службы будут настроены для работы с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="6eebc-203">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  


