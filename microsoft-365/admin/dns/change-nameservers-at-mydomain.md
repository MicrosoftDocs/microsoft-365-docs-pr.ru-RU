---
title: Изменение серверов доменных имен для настройки Office 365 у регистратора MyDomain
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
ms.assetid: c5f6140a-4a12-401b-9bbd-7dfb0d6b0ba3
description: Узнайте, как настроить Office 365 для управления записями DNS в пользовательском домене на MyDomain.
ms.openlocfilehash: 90f1469bdf2f281be14e2a9e15a9fe7ac4a8cbee
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2020
ms.locfileid: "42351620"
---
# <a name="change-nameservers-to-set-up-office-365-with-mydomain"></a><span data-ttu-id="d4838-103">Изменение серверов доменных имен для настройки Office 365 у регистратора MyDomain</span><span class="sxs-lookup"><span data-stu-id="d4838-103">Change nameservers to set up Office 365 with MyDomain</span></span>

 <span data-ttu-id="d4838-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="d4838-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="d4838-p101">Следуя этим инструкциям, вы можете передать управление своими записями DNS для Office 365 в Office 365. (При желании вы можете самостоятельно [управлять всеми своими записями DNS для Office 365 на сайте MyDomain](create-dns-records-at-mydomain.md).)</span><span class="sxs-lookup"><span data-stu-id="d4838-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at MyDomain](create-dns-records-at-mydomain.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d4838-107">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="d4838-107">Add a TXT record for verification</span></span>

<span data-ttu-id="d4838-p102">Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="d4838-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d4838-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="d4838-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="d4838-p104">Чтобы приступить к работе, откройте страницу со своими доменами на сайте MyDomain по предоставленной ссылке. Сначала вам потребуется [выполнить вход](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="d4838-p104">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d4838-114">В разделе **My Favorites** (Избранное) выберите **Domain Central** (Центральный домен).</span><span class="sxs-lookup"><span data-stu-id="d4838-114">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="d4838-115">В поле **Domain** (Домен) выберите доменное имя, которое хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="d4838-115">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="d4838-116">В строке **Overview** (Обзор) выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="d4838-116">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="d4838-117">В раскрывающемся списке **Modify** (Изменить) выберите **TXT/SPF Record** (Запись TXT/SPF).</span><span class="sxs-lookup"><span data-stu-id="d4838-117">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="d4838-118">В разделе **Content** (Контент) в поле для новой записи введите (или скопируйте и вставьте) значение из приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="d4838-118">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
||
|:-----|
|<span data-ttu-id="d4838-119">**Контент**</span><span class="sxs-lookup"><span data-stu-id="d4838-119">**Content**</span></span> <br/> |
|<span data-ttu-id="d4838-120">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d4838-120">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="d4838-121">**Примечание**: это пример.</span><span class="sxs-lookup"><span data-stu-id="d4838-121">**Note**: This is an example.</span></span> <span data-ttu-id="d4838-122">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="d4838-122">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="d4838-123">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="d4838-123">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="d4838-124">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="d4838-124">Select **Add**.</span></span>
    
8. <span data-ttu-id="d4838-125">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="d4838-125">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d4838-126">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Office 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="d4838-126">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="d4838-127">Если Office 365 обнаружит правильную запись TXT, это значит, что домен проверен.</span><span class="sxs-lookup"><span data-stu-id="d4838-127">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d4838-128">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="d4838-128">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="d4838-129">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="d4838-129">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="d4838-130">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="d4838-130">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="d4838-131">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="d4838-131">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d4838-p106">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d4838-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="d4838-135">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="d4838-135">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="d4838-p107">Чтобы завершить настройку домена для использования в Office 365, измените для него записи серверов имен на сайте вашего регистратора доменных имен таким образом, чтобы они указывали на основной и дополнительный DNS-серверы Office 365. После этого Office 365 обновит записи DNS для вашего домена. Мы добавим все записи, так что электронная почта, Skype для бизнеса online и общедоступный веб-сайт будут работать в вашем домене и вам больше не придется ничего настраивать.</span><span class="sxs-lookup"><span data-stu-id="d4838-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="d4838-139">Когда вы изменяете записи серверов имен своего домена, чтобы они указывали на DNS-серверы Office 365, это оказывает влияние на все службы, которые в настоящий момент связаны с доменом.</span><span class="sxs-lookup"><span data-stu-id="d4838-139">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="d4838-140">Например, все сообщения электронной почты, отправленные в ваш домен (например, rob@ *your_domain.*</span><span class="sxs-lookup"><span data-stu-id="d4838-140">For example, all email sent to your domain (like rob@ *your_domain.*</span></span> <span data-ttu-id="d4838-141">com) будет начинаться с Office 365 после внесения этого изменения.</span><span class="sxs-lookup"><span data-stu-id="d4838-141">com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="d4838-p109">В приведенной ниже процедуре показано, как удалить из списка все остальные, нежелательные серверы имен, а также как добавить правильные серверы имен, если их еще нет в данном списке.</span><span class="sxs-lookup"><span data-stu-id="d4838-p109">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. </span></span><br/> <span data-ttu-id="d4838-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span><span class="sxs-lookup"><span data-stu-id="d4838-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span>
  
1. <span data-ttu-id="d4838-p110">Чтобы приступить к работе, откройте страницу со своими доменами на сайте MyDomain по предоставленной ссылке. Сначала вам потребуется [выполнить вход](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="d4838-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d4838-146">В разделе **My Favorites** (Избранное) выберите **Domain Central** (Центральный домен).</span><span class="sxs-lookup"><span data-stu-id="d4838-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="d4838-147">В поле **Domain** (Домен) выберите доменное имя, которое хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="d4838-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="d4838-148">В строке **Overview (обзор** ) выберите **серверов доменных имен**.</span><span class="sxs-lookup"><span data-stu-id="d4838-148">In the **Overview** row, select **Nameservers**.</span></span>
    
    ![MyDomain — BP — redelegate — 1-1](../../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. <span data-ttu-id="d4838-150">В разделе **Update Name Servers** (Обновление серверов доменных имен) выберите **Use different name servers** (Использовать другие серверы доменных имен).</span><span class="sxs-lookup"><span data-stu-id="d4838-150">In the **Update Name Servers** section, select **Use different name servers**.</span></span>
    
    ![MyDomain — BP — redelegate — 1-2-1](../../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. <span data-ttu-id="d4838-152">В зависимости от того, есть ли у вас уже серверов доменных имен на отображаемой странице, перейдите к одной из двух указанных ниже процедур.</span><span class="sxs-lookup"><span data-stu-id="d4838-152">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-the-correct-nameservers-are-already-listed"></a><span data-ttu-id="d4838-153">Если указаны правильные серверы доменных имен</span><span class="sxs-lookup"><span data-stu-id="d4838-153">If the correct nameservers ARE already listed</span></span>

- <span data-ttu-id="d4838-154">Если правильные серверы доменных имен уже указаны, пропустите этот шаг.</span><span class="sxs-lookup"><span data-stu-id="d4838-154">If the correct nameservers are already listed, you can skip this step.</span></span>
    
    ![MyDomain — BP — redelegate — 1-2-2](../../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a><span data-ttu-id="d4838-156">Если правильные серверы доменных имен не указаны</span><span class="sxs-lookup"><span data-stu-id="d4838-156">If the correct nameservers are NOT already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="d4838-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="d4838-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="d4838-158">(То есть удалите только те текущие серверов доменных имен, которые *не* называются **NS1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**или **NS4.BDM.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="d4838-158">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="d4838-159">Удалите существующие серверы доменных имен, выбирая соответствующие записи в поле **Nameserver:** (Сервер доменных имен:) и нажимая на клавиатуре клавишу **DELETE**.</span><span class="sxs-lookup"><span data-stu-id="d4838-159">Delete the existing nameservers by selecting each entry in the **Nameserver:** field, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![MyDomain — BP — redelegate — 1-3-1](../../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. <span data-ttu-id="d4838-161">Дважды нажмите кнопку **Добавить** , чтобы добавить две новые строки серверов доменных имен.</span><span class="sxs-lookup"><span data-stu-id="d4838-161">Select **Add More** twice to add two new Nameserver rows.</span></span> 
    
    ![MyDomain — BP — redelegate — 1-3-2](../../media/19307893-2f73-4e4d-9221-a5870e09ab48.png)
  
3. <span data-ttu-id="d4838-163">В поля для записей введите (или скопируйте и вставьте) значения для серверов доменных имен из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="d4838-163">In the boxes for the records, type or copy and paste the nameserver values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="d4838-164">**Nameserver 1** (Сервер доменных имен 1)</span><span class="sxs-lookup"><span data-stu-id="d4838-164">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="d4838-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="d4838-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="d4838-166">**Nameserver 2** (Сервер доменных имен 2)</span><span class="sxs-lookup"><span data-stu-id="d4838-166">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="d4838-167">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="d4838-167">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="d4838-168">**Nameserver 3** (Сервер доменных имен 3)</span><span class="sxs-lookup"><span data-stu-id="d4838-168">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="d4838-169">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="d4838-169">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="d4838-170">**Nameserver 4** (Сервер доменных имен 4)</span><span class="sxs-lookup"><span data-stu-id="d4838-170">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="d4838-171">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="d4838-171">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![MyDomain — BP — redelegate — 1-4](../../media/7427e99c-49c7-4a2e-a5bf-66fc46900cd1.png)
  
4. <span data-ttu-id="d4838-173">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d4838-173">Select **Save**.</span></span>
    
    ![MyDomain — BP — redelegate — 1-5](../../media/48473816-b881-47f0-9344-74622efa3bf8.png)
  
> [!NOTE]
> <span data-ttu-id="d4838-p112">На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов. После этого ваша электронная почта и все остальные службы Office 365 будут настроены на работу с новым доменом.</span><span class="sxs-lookup"><span data-stu-id="d4838-p112">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
