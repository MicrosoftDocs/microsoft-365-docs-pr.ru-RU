---
title: Изменение серверов доменных имен для настройки Office 365 у регистратора Bluehost
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
ms.assetid: 7712b6af-329c-43a0-af7b-c4e4c1befb0e
description: 'Узнайте, как настроить Office 365 для управления записями DNS по адресу Bluehost. '
ms.openlocfilehash: dbd06791df2e7f8e6ca085b82dc880e9626c065c
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212345"
---
# <a name="change-nameservers-to-set-up-office-365-with-bluehost"></a><span data-ttu-id="12fc0-103">Изменение серверов доменных имен для настройки Office 365 у регистратора Bluehost</span><span class="sxs-lookup"><span data-stu-id="12fc0-103">Change nameservers to set up Office 365 with Bluehost</span></span>

 <span data-ttu-id="12fc0-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="12fc0-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="12fc0-p101">Следуя этим инструкциям, вы можете передать управление своими записями DNS для Office 365 в Office 365. (При желании вы можете самостоятельно [управлять всеми своими записями DNS для Office 365 на сайте Bluehost](create-dns-records-at-bluehost.md).)</span><span class="sxs-lookup"><span data-stu-id="12fc0-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Bluehost](create-dns-records-at-bluehost.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="12fc0-107">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="12fc0-107">Add a TXT record for verification</span></span>

<span data-ttu-id="12fc0-p102">Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="12fc0-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="12fc0-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="12fc0-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="12fc0-112">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Bluehost по [этой ссылке](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="12fc0-112">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="12fc0-113">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="12fc0-113">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="12fc0-114">На странице **доменов** в области **домена** установите флажок домена, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="12fc0-114">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="12fc0-115">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="12fc0-115">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="12fc0-116">В области **domain_name** в строке **Редактор зоны DNS** выберите **Управление записями DNS**.</span><span class="sxs-lookup"><span data-stu-id="12fc0-116">In the **domain_name** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="12fc0-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="12fc0-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="12fc0-118">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="12fc0-118">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="12fc0-119">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="12fc0-119">**Host Record**</span></span> <br/> |<span data-ttu-id="12fc0-120">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="12fc0-120">**TTL**</span></span> <br/> |<span data-ttu-id="12fc0-121">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="12fc0-121">**Type**</span></span> <br/> |<span data-ttu-id="12fc0-122">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="12fc0-122">**TXT Value**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="12fc0-123">14400</span><span class="sxs-lookup"><span data-stu-id="12fc0-123">14400</span></span>  <br/> |<span data-ttu-id="12fc0-124">TXT</span><span class="sxs-lookup"><span data-stu-id="12fc0-124">TXT</span></span>  <br/> |<span data-ttu-id="12fc0-125">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="12fc0-125">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="12fc0-126">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="12fc0-126">**Note:** This is an example.</span></span> <span data-ttu-id="12fc0-127">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="12fc0-127">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="12fc0-128">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="12fc0-128">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
5. <span data-ttu-id="12fc0-129">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="12fc0-129">Select **add record**.</span></span>
    
6. <span data-ttu-id="12fc0-130">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="12fc0-130">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="12fc0-131">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Office 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="12fc0-131">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="12fc0-132">Если Office 365 обнаружит правильную запись TXT, это значит, что домен проверен.</span><span class="sxs-lookup"><span data-stu-id="12fc0-132">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="12fc0-133">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="12fc0-133">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="12fc0-134">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="12fc0-134">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="12fc0-135">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="12fc0-135">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="12fc0-136">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="12fc0-136">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="12fc0-p106">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="12fc0-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="12fc0-140">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="12fc0-140">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="12fc0-p107">Чтобы завершить настройку домена для использования в Office 365, измените для него записи серверов имен на сайте вашего регистратора доменных имен таким образом, чтобы они указывали на основной и дополнительный DNS-серверы Office 365. После этого Office 365 обновит записи DNS для вашего домена. Мы добавим все записи, так что электронная почта, Skype для бизнеса online и общедоступный веб-сайт будут работать в вашем домене и вам больше не придется ничего настраивать.</span><span class="sxs-lookup"><span data-stu-id="12fc0-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="12fc0-p108">Когда вы изменяете записи серверов имен своего домена, чтобы они указывали на DNS-серверы Office 365, это оказывает влияние на все службы, которые в настоящий момент связаны с доменом. Например, все сообщения электронной почты, отправленные на адреса в вашем домене (вида kirill@ *ваш_домен*  .com), после этого изменения будут попадать в Office 365.</span><span class="sxs-lookup"><span data-stu-id="12fc0-p108">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="12fc0-146">В следующей процедуре показано, как удалить любые другие нежелательные серверов доменных имен из списка, а также как добавить правильный серверов доменных имен, если они еще не указаны.</span><span class="sxs-lookup"><span data-stu-id="12fc0-146">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="12fc0-147">> после выполнения действий, описанных в этом разделе, необходимо указать только следующие четыре серверов доменных имен: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="12fc0-147">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="12fc0-148">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Bluehost по [этой ссылке](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="12fc0-148">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="12fc0-149">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="12fc0-149">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="12fc0-150">На странице **Domains (домены** ) в области **domain_name** установите флажок для своего домена, а затем выберите **серверы имен**.</span><span class="sxs-lookup"><span data-stu-id="12fc0-150">On the **domains** page, in the **domain_name** area, select the checkbox for your domain, and then select **name servers**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-1](../../media/8f384386-197c-4272-9675-82037922dac4.png)
  
3. <span data-ttu-id="12fc0-152">В области **domain_name** выберите **использовать пользовательские серверов доменных имен**.</span><span class="sxs-lookup"><span data-stu-id="12fc0-152">In the **domain_name** area, select **Use Custom Nameservers**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-2](../../media/9fb47d21-c4ce-4eee-af90-c9569870a329.png)
  
4. <span data-ttu-id="12fc0-154">В зависимости от того, указаны ли уже серверы доменных имен на странице, которая отображается на экране, воспользуйтесь одной из двух процедур.</span><span class="sxs-lookup"><span data-stu-id="12fc0-154">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="12fc0-155">Если на странице **НЕ УКАЗАНЫ** серверы доменных имен, [На странице НЕ УКАЗАНЫ серверы доменных имен](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="12fc0-155">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="12fc0-156">Если на странице **УКАЗАНЫ** серверы доменных имен, [На странице УКАЗАНЫ серверы доменных имен](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="12fc0-156">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="12fc0-157">На странице НЕ УКАЗАНЫ серверы доменных имен</span><span class="sxs-lookup"><span data-stu-id="12fc0-157">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="12fc0-158">В разделе **Use Custom Nameservers** (Использовать настраиваемые серверы имен) введите (или скопируйте и вставьте) значения из приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="12fc0-158">In the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="12fc0-159">**Первая пустая строка**</span><span class="sxs-lookup"><span data-stu-id="12fc0-159">**First empty row**</span></span> <br/> |<span data-ttu-id="12fc0-160">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="12fc0-160">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="12fc0-161">**Вторая пустая строка**</span><span class="sxs-lookup"><span data-stu-id="12fc0-161">**Second empty row**</span></span> <br/> |<span data-ttu-id="12fc0-162">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="12fc0-162">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost — BP — redelegate — 1-3-1](../../media/07b13d6d-a34e-45b5-afd5-48ebd4c1344f.png)
  
2. <span data-ttu-id="12fc0-164">Нажмите кнопку **Добавить строку**.</span><span class="sxs-lookup"><span data-stu-id="12fc0-164">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
3. <span data-ttu-id="12fc0-166">В том же разделе **Use Custom Nameservers** (Использовать настраиваемые серверы имен) в новой пустой строке введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="12fc0-166">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="12fc0-167">**Третья пустая строка**</span><span class="sxs-lookup"><span data-stu-id="12fc0-167">**Third empty row**</span></span> <br/> |<span data-ttu-id="12fc0-168">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="12fc0-168">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="12fc0-169">**Четвертая пустая строка**</span><span class="sxs-lookup"><span data-stu-id="12fc0-169">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="12fc0-170">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="12fc0-170">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    ![Bluehost-BP-Redelegate-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
4. <span data-ttu-id="12fc0-171">Чтобы добавить четвертую запись сервера доменных имен, нажмите кнопку **Добавить строку** еще раз и создайте запись, используя значения из последней строки приведенной выше таблицы.</span><span class="sxs-lookup"><span data-stu-id="12fc0-171">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
5. <span data-ttu-id="12fc0-172">Нажмите кнопку **сохранить параметры nameserver**.</span><span class="sxs-lookup"><span data-stu-id="12fc0-172">Select **save nameserver settings**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="12fc0-p111">На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов. После этого ваша электронная почта и все остальные службы Office 365 будут настроены на работу с новым доменом.</span><span class="sxs-lookup"><span data-stu-id="12fc0-p111">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="12fc0-176">На странице УКАЗАНЫ серверы доменных имен</span><span class="sxs-lookup"><span data-stu-id="12fc0-176">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="12fc0-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="12fc0-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="12fc0-178">(То есть удалите только те текущие серверов доменных имен, которые *не* называются **NS1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**или **NS4.BDM.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="12fc0-178">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="12fc0-179">Если на странице указаны другие серверы доменных имен, удалите их (выберите каждый сервер и нажмите клавишу **DELETE**).</span><span class="sxs-lookup"><span data-stu-id="12fc0-179">If there are any other name servers listed, delete each of them by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Bluehost-BP-Redelegate-1-5](../../media/d1051c43-f8ff-46d7-af26-3975d3f0f621.png)
  
2. <span data-ttu-id="12fc0-181">В том же разделе **Use Custom Nameservers** (Использовать настраиваемые серверы имен) введите (или скопируйте и вставьте) значения из приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="12fc0-181">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="12fc0-182">**Первая пустая строка**</span><span class="sxs-lookup"><span data-stu-id="12fc0-182">**First empty row**</span></span> <br/> |<span data-ttu-id="12fc0-183">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="12fc0-183">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="12fc0-184">**Вторая пустая строка**</span><span class="sxs-lookup"><span data-stu-id="12fc0-184">**Second empty row**</span></span> <br/> |<span data-ttu-id="12fc0-185">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="12fc0-185">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost — BP — redelegate — 1-3](../../media/1523debf-5eb0-4765-8e05-bcd56e375c20.png)
  
3. <span data-ttu-id="12fc0-187">Нажмите кнопку **Добавить строку**.</span><span class="sxs-lookup"><span data-stu-id="12fc0-187">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
4. <span data-ttu-id="12fc0-189">В том же разделе **Use Custom Nameservers** (Использовать настраиваемые серверы имен) в новой пустой строке введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="12fc0-189">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="12fc0-190">**Третья пустая строка**</span><span class="sxs-lookup"><span data-stu-id="12fc0-190">**Third empty row**</span></span> <br/> |<span data-ttu-id="12fc0-191">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="12fc0-191">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="12fc0-192">**Четвертая пустая строка**</span><span class="sxs-lookup"><span data-stu-id="12fc0-192">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="12fc0-193">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="12fc0-193">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost — BP — redelegate — 1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
5. <span data-ttu-id="12fc0-195">Чтобы добавить четвертую запись сервера доменных имен, нажмите кнопку **Добавить строку** еще раз и создайте запись, используя значения из последней строки приведенной выше таблицы.</span><span class="sxs-lookup"><span data-stu-id="12fc0-195">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
6. <span data-ttu-id="12fc0-196">Нажмите кнопку **сохранить параметры nameserver**.</span><span class="sxs-lookup"><span data-stu-id="12fc0-196">Select **save nameserver settings**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="12fc0-p113">На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов. После этого ваша электронная почта и все остальные службы Office 365 будут настроены на работу с новым доменом.</span><span class="sxs-lookup"><span data-stu-id="12fc0-p113">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
