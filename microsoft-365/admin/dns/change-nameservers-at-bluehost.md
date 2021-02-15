---
title: Изменение доменных имен для microsoft с Bluehost
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
ms.assetid: 7712b6af-329c-43a0-af7b-c4e4c1befb0e
description: 'Узнайте, как настроить Майкрософт для управления своими записями DNS на сайте Bluehost. '
ms.openlocfilehash: 78b138a501054a573c2b36cc486dda833be7ae35
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658012"
---
# <a name="change-nameservers-to-set-up-microsoft-with-bluehost"></a><span data-ttu-id="b2a25-103">Изменение доменных имен для microsoft с Bluehost</span><span class="sxs-lookup"><span data-stu-id="b2a25-103">Change nameservers to set up Microsoft with Bluehost</span></span>

 <span data-ttu-id="b2a25-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="b2a25-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b2a25-105">Следуйте этим инструкциям, если вы хотите, чтобы корпорация Майкрософт управляет вашими записями DNS.</span><span class="sxs-lookup"><span data-stu-id="b2a25-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="b2a25-106">(При этом вы можете управлять всеми своими [записями DNS на bluehost.)](create-dns-records-at-bluehost.md)</span><span class="sxs-lookup"><span data-stu-id="b2a25-106">(If you prefer, you can [manage all your DNS records at Bluehost](create-dns-records-at-bluehost.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b2a25-107">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="b2a25-107">Add a TXT record for verification</span></span>

<span data-ttu-id="b2a25-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="b2a25-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b2a25-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="b2a25-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="b2a25-112">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Bluehost по [этой ссылке](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="b2a25-112">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="b2a25-113">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="b2a25-113">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b2a25-114">На странице **доменов** в области **домена** установите флажок домена, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="b2a25-114">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="b2a25-115">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="b2a25-115">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="b2a25-116">В области **domain_name** в строке редактора зон **DNS** выберите **"Управление записями DNS".**</span><span class="sxs-lookup"><span data-stu-id="b2a25-116">In the **domain_name** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="b2a25-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b2a25-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b2a25-118">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="b2a25-118">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b2a25-119">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="b2a25-119">**Host Record**</span></span> <br/> |<span data-ttu-id="b2a25-120">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="b2a25-120">**TTL**</span></span> <br/> |<span data-ttu-id="b2a25-121">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="b2a25-121">**Type**</span></span> <br/> |<span data-ttu-id="b2a25-122">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="b2a25-122">**TXT Value**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="b2a25-123">14400</span><span class="sxs-lookup"><span data-stu-id="b2a25-123">14400</span></span>  <br/> |<span data-ttu-id="b2a25-124">TXT</span><span class="sxs-lookup"><span data-stu-id="b2a25-124">TXT</span></span>  <br/> |<span data-ttu-id="b2a25-125">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b2a25-125">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="b2a25-126">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="b2a25-126">**Note:** This is an example.</span></span> <span data-ttu-id="b2a25-127">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="b2a25-127">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="b2a25-128">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="b2a25-128">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
5. <span data-ttu-id="b2a25-129">Выберите **"Добавить запись".**</span><span class="sxs-lookup"><span data-stu-id="b2a25-129">Select **add record**.</span></span>
    
6. <span data-ttu-id="b2a25-130">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="b2a25-130">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b2a25-131">Теперь, когда вы добавили запись на сайте регистратора доменных имен, вы вернемся в корпорацию Майкрософт и запросите поиск записи.</span><span class="sxs-lookup"><span data-stu-id="b2a25-131">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="b2a25-132">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="b2a25-132">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b2a25-133">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="b2a25-133">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="b2a25-134">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="b2a25-134">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="b2a25-135">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="b2a25-135">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="b2a25-136">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="b2a25-136">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b2a25-p106">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b2a25-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="b2a25-140">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="b2a25-140">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="b2a25-141">Чтобы завершить настройку домена с помощью Майкрософт, измените записи доменных имен своего домена у регистратора доменных имен так, чтобы они указывают на основной и дополнительный серверы имен.</span><span class="sxs-lookup"><span data-stu-id="b2a25-141">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the  primary and secondary name servers.</span></span> <span data-ttu-id="b2a25-142">Это настраивает Майкрософт для обновления записей DNS домена за вас.</span><span class="sxs-lookup"><span data-stu-id="b2a25-142">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="b2a25-143">Мы добавим все записи, так что электронная почта, Skype для бизнеса online и общедоступный веб-сайт будут работать в вашем домене и вам больше не придется ничего настраивать.</span><span class="sxs-lookup"><span data-stu-id="b2a25-143">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="b2a25-144">При изменении записей сервера доменных имен таким образом, чтобы они указывают на серверы доменных имен Майкрософт, это влияет на все службы, связанные с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="b2a25-144">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="b2a25-145">Например, все сообщения электронной почты, отправленные на ваш домен (например, rob@ *your_domain*  .com), после внести это изменение в корпорацию Майкрософт начнут приходить в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b2a25-145">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="b2a25-146">В следующей процедуре покажем, как удалить любые другие нежелательные доменные имена из списка, а также как добавить правильные доменные имена, если они еще не указаны.</span><span class="sxs-lookup"><span data-stu-id="b2a25-146">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="b2a25-147">> После завершения действий, указанных в этом разделе, в списке должны быть указаны только следующие четыре > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b2a25-147">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="b2a25-148">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Bluehost по [этой ссылке](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="b2a25-148">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="b2a25-149">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="b2a25-149">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b2a25-150">На странице **"Домены"** в **области** domain_name выберите свой домен, а затем выберите **серверы доменных имен.**</span><span class="sxs-lookup"><span data-stu-id="b2a25-150">On the **domains** page, in the **domain_name** area, select the checkbox for your domain, and then select **name servers**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-1](../../media/8f384386-197c-4272-9675-82037922dac4.png)
  
3. <span data-ttu-id="b2a25-152">В области **domain_name** выберите **"Использовать настраиваемые доменные имена".**</span><span class="sxs-lookup"><span data-stu-id="b2a25-152">In the **domain_name** area, select **Use Custom Nameservers**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-2](../../media/9fb47d21-c4ce-4eee-af90-c9569870a329.png)
  
4. <span data-ttu-id="b2a25-154">В зависимости от того, указаны ли уже серверы доменных имен на странице, которая отображается на экране, воспользуйтесь одной из двух процедур.</span><span class="sxs-lookup"><span data-stu-id="b2a25-154">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="b2a25-155">Если на странице **НЕ УКАЗАНЫ** серверы доменных имен, [На странице НЕ УКАЗАНЫ серверы доменных имен](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="b2a25-155">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="b2a25-156">Если на странице **УКАЗАНЫ** серверы доменных имен, [На странице УКАЗАНЫ серверы доменных имен](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="b2a25-156">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="b2a25-157">На странице НЕ УКАЗАНЫ серверы доменных имен</span><span class="sxs-lookup"><span data-stu-id="b2a25-157">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="b2a25-158">В разделе **Use Custom Nameservers** (Использовать настраиваемые серверы имен) введите (или скопируйте и вставьте) значения из приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="b2a25-158">In the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="b2a25-159">**Первая пустая строка**</span><span class="sxs-lookup"><span data-stu-id="b2a25-159">**First empty row**</span></span> <br/> |<span data-ttu-id="b2a25-160">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b2a25-160">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b2a25-161">**Вторая пустая строка**</span><span class="sxs-lookup"><span data-stu-id="b2a25-161">**Second empty row**</span></span> <br/> |<span data-ttu-id="b2a25-162">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b2a25-162">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3-1](../../media/07b13d6d-a34e-45b5-afd5-48ebd4c1344f.png)
  
2. <span data-ttu-id="b2a25-164">Выберите **"Добавить строку"**.</span><span class="sxs-lookup"><span data-stu-id="b2a25-164">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
3. <span data-ttu-id="b2a25-166">В том же разделе **Use Custom Nameservers** (Использовать настраиваемые серверы имен) в новой пустой строке введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="b2a25-166">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="b2a25-167">**Третья пустая строка**</span><span class="sxs-lookup"><span data-stu-id="b2a25-167">**Third empty row**</span></span> <br/> |<span data-ttu-id="b2a25-168">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b2a25-168">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b2a25-169">**Четвертая пустая строка**</span><span class="sxs-lookup"><span data-stu-id="b2a25-169">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="b2a25-170">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b2a25-170">ns4.bdm.microsoftonline.com</span></span>  <br/> |
  
4. <span data-ttu-id="b2a25-171">Чтобы добавить четвертую запись nameserver, снова выберите "Добавить строку" и создайте запись, используя значения из последней строки таблицы выше. </span><span class="sxs-lookup"><span data-stu-id="b2a25-171">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
5. <span data-ttu-id="b2a25-172">Выберите **параметры сохранения доменных имен.**</span><span class="sxs-lookup"><span data-stu-id="b2a25-172">Select **save nameserver settings**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="b2a25-174">На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="b2a25-174">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="b2a25-175">Затем ваша почта Майкрософт и другие службы будут настроены для работы с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="b2a25-175">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="b2a25-176">На странице УКАЗАНЫ серверы доменных имен</span><span class="sxs-lookup"><span data-stu-id="b2a25-176">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="b2a25-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="b2a25-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="b2a25-178">(То есть удалите только те текущие  доменные имена, которые не **ns1.bdm.microsoftonline.com,** **ns2.bdm.microsoftonline.com,** **ns3.bdm.microsoftonline.com** или **ns4.bdm.microsoftonline.com.)**</span><span class="sxs-lookup"><span data-stu-id="b2a25-178">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="b2a25-179">Если на странице указаны другие серверы доменных имен, удалите их (выберите каждый сервер и нажмите клавишу **DELETE**).</span><span class="sxs-lookup"><span data-stu-id="b2a25-179">If there are any other name servers listed, delete each of them by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Bluehost-BP-Redelegate-1-5](../../media/d1051c43-f8ff-46d7-af26-3975d3f0f621.png)
  
2. <span data-ttu-id="b2a25-181">В том же разделе **Use Custom Nameservers** (Использовать настраиваемые серверы имен) введите (или скопируйте и вставьте) значения из приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="b2a25-181">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="b2a25-182">**Первая пустая строка**</span><span class="sxs-lookup"><span data-stu-id="b2a25-182">**First empty row**</span></span> <br/> |<span data-ttu-id="b2a25-183">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b2a25-183">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b2a25-184">**Вторая пустая строка**</span><span class="sxs-lookup"><span data-stu-id="b2a25-184">**Second empty row**</span></span> <br/> |<span data-ttu-id="b2a25-185">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b2a25-185">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3](../../media/1523debf-5eb0-4765-8e05-bcd56e375c20.png)
  
3. <span data-ttu-id="b2a25-187">Выберите **"Добавить строку"**.</span><span class="sxs-lookup"><span data-stu-id="b2a25-187">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
4. <span data-ttu-id="b2a25-189">В том же разделе **Use Custom Nameservers** (Использовать настраиваемые серверы имен) в новой пустой строке введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="b2a25-189">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="b2a25-190">**Третья пустая строка**</span><span class="sxs-lookup"><span data-stu-id="b2a25-190">**Third empty row**</span></span> <br/> |<span data-ttu-id="b2a25-191">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b2a25-191">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b2a25-192">**Четвертая пустая строка**</span><span class="sxs-lookup"><span data-stu-id="b2a25-192">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="b2a25-193">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b2a25-193">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
5. <span data-ttu-id="b2a25-195">Чтобы добавить четвертую запись nameserver, снова выберите "Добавить строку" и создайте запись, используя значения из последней строки таблицы выше. </span><span class="sxs-lookup"><span data-stu-id="b2a25-195">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
6. <span data-ttu-id="b2a25-196">Выберите **параметры сохранения доменных имен.**</span><span class="sxs-lookup"><span data-stu-id="b2a25-196">Select **save nameserver settings**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="b2a25-198">На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="b2a25-198">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="b2a25-199">Затем ваша почта Майкрософт и другие службы будут настроены для работы с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="b2a25-199">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
