---
title: Изменение доменных имен для microsoft с MyDomain
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
ms.assetid: c5f6140a-4a12-401b-9bbd-7dfb0d6b0ba3
description: Узнайте, как настроить Майкрософт для управления записями DNS вашего пользовательского домена на сайте MyDomain.
ms.openlocfilehash: fbfa3c495f54a9890be6d9c9e31a7878b21f12fe
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658420"
---
# <a name="change-nameservers-to-set-up-microsoft-with-mydomain"></a><span data-ttu-id="2bfc0-103">Изменение доменных имен для microsoft с MyDomain</span><span class="sxs-lookup"><span data-stu-id="2bfc0-103">Change nameservers to set up Microsoft with MyDomain</span></span>

 <span data-ttu-id="2bfc0-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="2bfc0-105">Следуйте этим инструкциям, если вы хотите, чтобы корпорация Майкрософт управляет вашими записями DNS.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="2bfc0-106">(При этом вы можете управлять всеми своими записями DNS microsoft [на сайте MyDomain.)](create-dns-records-at-mydomain.md)</span><span class="sxs-lookup"><span data-stu-id="2bfc0-106">(If you prefer, you can [manage all your Microsoft DNS records at MyDomain](create-dns-records-at-mydomain.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="2bfc0-107">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="2bfc0-107">Add a TXT record for verification</span></span>

<span data-ttu-id="2bfc0-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2bfc0-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="2bfc0-p104">Чтобы приступить к работе, откройте страницу со своими доменами на сайте MyDomain по предоставленной ссылке. Сначала вам потребуется [выполнить вход](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="2bfc0-p104">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="2bfc0-114">В разделе **My Favorites** (Избранное) выберите **Domain Central** (Центральный домен).</span><span class="sxs-lookup"><span data-stu-id="2bfc0-114">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="2bfc0-115">В поле **Domain** (Домен) выберите доменное имя, которое хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-115">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="2bfc0-116">В строке **Overview** (Обзор) выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-116">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="2bfc0-117">В раскрывающемся списке **Modify** (Изменить) выберите **TXT/SPF Record** (Запись TXT/SPF).</span><span class="sxs-lookup"><span data-stu-id="2bfc0-117">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="2bfc0-118">В разделе **Content** (Контент) в поле для новой записи введите (или скопируйте и вставьте) значение из приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-118">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
||
|:-----|
|<span data-ttu-id="2bfc0-119">**Контент**</span><span class="sxs-lookup"><span data-stu-id="2bfc0-119">**Content**</span></span> <br/> |
|<span data-ttu-id="2bfc0-120">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="2bfc0-120">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="2bfc0-121">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-121">**Note**: This is an example.</span></span> <span data-ttu-id="2bfc0-122">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-122">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="2bfc0-123">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="2bfc0-123">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="2bfc0-124">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="2bfc0-124">Select **Add**.</span></span>
    
8. <span data-ttu-id="2bfc0-125">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-125">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="2bfc0-126">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Microsoft 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-126">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="2bfc0-127">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-127">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="2bfc0-128">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-128">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="2bfc0-129">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-129">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="2bfc0-130">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="2bfc0-130">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="2bfc0-131">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="2bfc0-131">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2bfc0-p106">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2bfc0-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="2bfc0-135">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="2bfc0-135">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="2bfc0-136">Чтобы завершить настройку домена с помощью Майкрософт, измените записи сервера доменных имен своего домена у регистратора доменных имен, чтобы они указать на основной и дополнительный серверы доменных имен Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-136">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="2bfc0-137">Это настраивает Майкрософт для обновления записей DNS домена за вас.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-137">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="2bfc0-138">Мы добавим все записи, так что электронная почта, Skype для бизнеса online и общедоступный веб-сайт будут работать в вашем домене и вам больше не придется ничего настраивать.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-138">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="2bfc0-139">При изменении записей сервера доменных имен таким образом, чтобы они указывают на серверы доменных имен Майкрософт, это влияет на все службы, связанные с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-139">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="2bfc0-140">Например, все сообщения электронной почты, отправленные на ваш домен (например, rob@ *your_domain.*</span><span class="sxs-lookup"><span data-stu-id="2bfc0-140">For example, all email sent to your domain (like rob@ *your_domain.*</span></span> <span data-ttu-id="2bfc0-141">com) начнется после внести это изменение в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-141">com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="2bfc0-p109">В приведенной ниже процедуре показано, как удалить из списка все остальные, нежелательные серверы имен, а также как добавить правильные серверы имен, если их еще нет в данном списке.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-p109">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. </span></span><br/> <span data-ttu-id="2bfc0-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span><span class="sxs-lookup"><span data-stu-id="2bfc0-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span>
  
1. <span data-ttu-id="2bfc0-p110">Чтобы приступить к работе, откройте страницу со своими доменами на сайте MyDomain по предоставленной ссылке. Сначала вам потребуется [выполнить вход](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="2bfc0-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="2bfc0-146">В разделе **My Favorites** (Избранное) выберите **Domain Central** (Центральный домен).</span><span class="sxs-lookup"><span data-stu-id="2bfc0-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="2bfc0-147">В поле **Domain** (Домен) выберите доменное имя, которое хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="2bfc0-148">В **строке "Обзор"** выберите **"Nameservers" (Доменные имена).**</span><span class="sxs-lookup"><span data-stu-id="2bfc0-148">In the **Overview** row, select **Nameservers**.</span></span>
    
    ![MyDomain-BP-Redelegate-1-1](../../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. <span data-ttu-id="2bfc0-150">В разделе **Update Name Servers** (Обновление серверов доменных имен) выберите **Use different name servers** (Использовать другие серверы доменных имен).</span><span class="sxs-lookup"><span data-stu-id="2bfc0-150">In the **Update Name Servers** section, select **Use different name servers**.</span></span>
    
    ![MyDomain-BP-Redelegate-1-2-1](../../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. <span data-ttu-id="2bfc0-152">В зависимости от того, есть ли на странице, которая отображается сейчас, уже есть или нет, продолжите одну из двух следующих процедур.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-152">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-the-correct-nameservers-are-already-listed"></a><span data-ttu-id="2bfc0-153">Если указаны правильные серверы доменных имен</span><span class="sxs-lookup"><span data-stu-id="2bfc0-153">If the correct nameservers ARE already listed</span></span>

- <span data-ttu-id="2bfc0-154">Если правильные серверы доменных имен уже указаны, пропустите этот шаг.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-154">If the correct nameservers are already listed, you can skip this step.</span></span>
    
    ![MyDomain-BP-Redelegate-1-2-2](../../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a><span data-ttu-id="2bfc0-156">Если правильные серверы доменных имен не указаны</span><span class="sxs-lookup"><span data-stu-id="2bfc0-156">If the correct nameservers are NOT already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="2bfc0-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="2bfc0-158">(То есть удалите только те текущие  доменные имена, которые не **ns1.bdm.microsoftonline.com,** **ns2.bdm.microsoftonline.com,** **ns3.bdm.microsoftonline.com** или **ns4.bdm.microsoftonline.com.)**</span><span class="sxs-lookup"><span data-stu-id="2bfc0-158">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="2bfc0-159">Удалите существующие серверы доменных имен, выбирая соответствующие записи в поле **Nameserver:** (Сервер доменных имен:) и нажимая на клавиатуре клавишу **DELETE**.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-159">Delete the existing nameservers by selecting each entry in the **Nameserver:** field, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![MyDomain-BP-Redelegate-1-3-1](../../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. <span data-ttu-id="2bfc0-161">Дважды **выберите "Добавить еще",** чтобы добавить две новые строки "Nameserver".</span><span class="sxs-lookup"><span data-stu-id="2bfc0-161">Select **Add More** twice to add two new Nameserver rows.</span></span> 
    
    ![MyDomain-BP-Redelegate-1-3-2](../../media/19307893-2f73-4e4d-9221-a5870e09ab48.png)
  
3. <span data-ttu-id="2bfc0-163">В поля для записей введите (или скопируйте и вставьте) значения для серверов доменных имен из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-163">In the boxes for the records, type or copy and paste the nameserver values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="2bfc0-164">**Nameserver 1** (Сервер доменных имен 1)</span><span class="sxs-lookup"><span data-stu-id="2bfc0-164">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="2bfc0-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="2bfc0-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="2bfc0-166">**Nameserver 2** (Сервер доменных имен 2)</span><span class="sxs-lookup"><span data-stu-id="2bfc0-166">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="2bfc0-167">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="2bfc0-167">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="2bfc0-168">**Nameserver 3** (Сервер доменных имен 3)</span><span class="sxs-lookup"><span data-stu-id="2bfc0-168">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="2bfc0-169">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="2bfc0-169">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="2bfc0-170">**Nameserver 4** (Сервер доменных имен 4)</span><span class="sxs-lookup"><span data-stu-id="2bfc0-170">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="2bfc0-171">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="2bfc0-171">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![MyDomain-BP-Redelegate-1-4](../../media/7427e99c-49c7-4a2e-a5bf-66fc46900cd1.png)
  
4. <span data-ttu-id="2bfc0-173">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-173">Select **Save**.</span></span>
    
    ![MyDomain-BP-Redelegate-1-5](../../media/48473816-b881-47f0-9344-74622efa3bf8.png)
  
> [!NOTE]
> <span data-ttu-id="2bfc0-175">На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-175">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="2bfc0-176">Затем ваша почта Майкрософт и другие службы будут настроены для работы с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="2bfc0-176">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
