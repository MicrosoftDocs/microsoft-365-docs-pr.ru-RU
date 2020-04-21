---
title: Создание записей DNS на сайте OVH для Майкрософт
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу OVH для Майкрософт.
ms.openlocfilehash: 01c455f54a7ee2efc6114dba1c01170b97ea5f71
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629291"
---
# <a name="create-dns-records-at-ovh-for-microsoft"></a><span data-ttu-id="e8f43-103">Создание записей DNS на сайте OVH для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e8f43-103">Create DNS records at OVH for Microsoft</span></span>

<span data-ttu-id="e8f43-104">Если вы не нашли нужную информацию, см. [вопросы и ответы по доменам](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="e8f43-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e8f43-105">Если ваш поставщик услуг размещения DNS  OVH, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб.</span><span class="sxs-lookup"><span data-stu-id="e8f43-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="e8f43-106">Ниже перечислены основные записи, которые нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="e8f43-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="e8f43-107">Создание записей DNS на сайте OVH для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e8f43-107">Create DNS records at OVH for Microsoft</span></span>](#create-dns-records-at-ovh-for-microsoft)
    
- [<span data-ttu-id="e8f43-108">Добавление записи MX для отправки электронной почты для вашего домена в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e8f43-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="e8f43-109">Добавление записей CNAME, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e8f43-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="e8f43-110">Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="e8f43-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="e8f43-111">Добавление двух записей SRV, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e8f43-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="e8f43-112">Когда вы добавите эти записи на сайте OVH, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e8f43-112">After you add these records at OVH, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="e8f43-113">Чтобы узнать о размещении и DNS для веб-сайтов с помощью Microsoft, ознакомьтесь со статьей [использование общедоступного веб-сайта с корпорацией Майкрософт](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="e8f43-113">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="e8f43-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e8f43-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e8f43-117">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="e8f43-117">Add a TXT record for verification</span></span>
<span data-ttu-id="e8f43-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="e8f43-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="e8f43-119">Перед использованием домена с корпорацией Майкрософт необходимо убедиться, что вы являетесь его владельцем.</span><span class="sxs-lookup"><span data-stu-id="e8f43-119">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="e8f43-120">Вы можете войти в свою учетную запись у вас в вашем регистраторе доменных имен и создать запись DNS в Майкрософт, если вы владеете этим доменом.</span><span class="sxs-lookup"><span data-stu-id="e8f43-120">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e8f43-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="e8f43-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="e8f43-p104">Чтобы приступить к работе, откройте страницу со своими доменами на сайте OVH по [этой ссылке](https://www.ovh.com/manager/). Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="e8f43-p104">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="e8f43-126">В разделе **Domains (домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="e8f43-126">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="e8f43-128">Выберите **зону DNS**.</span><span class="sxs-lookup"><span data-stu-id="e8f43-128">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="e8f43-130">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="e8f43-130">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="e8f43-132">Выбор **txt**</span><span class="sxs-lookup"><span data-stu-id="e8f43-132">Select **TXT**</span></span>
    
    ![OVH выбрать запись TXT](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="e8f43-134">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="e8f43-134">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="e8f43-135">Чтобы назначить значение TTL, выберите пункт **личное** в раскрывающемся списке, а затем введите значение в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="e8f43-135">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="e8f43-136">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="e8f43-136">**Record type**</span></span>|<span data-ttu-id="e8f43-137">**Sub-domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="e8f43-137">**Sub-domain**</span></span>|<span data-ttu-id="e8f43-138">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e8f43-138">**TTL**</span></span>|<span data-ttu-id="e8f43-139">**Значение**</span><span class="sxs-lookup"><span data-stu-id="e8f43-139">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e8f43-140">TXT</span><span class="sxs-lookup"><span data-stu-id="e8f43-140">TXT</span></span>  <br/> |<span data-ttu-id="e8f43-141">(Оставьте пустым)</span><span class="sxs-lookup"><span data-stu-id="e8f43-141">(leave blank)</span></span>  <br/> |<span data-ttu-id="e8f43-142">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="e8f43-142">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e8f43-143">MS=msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="e8f43-143">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="e8f43-144">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="e8f43-144">**Note:** This is an example.</span></span> <span data-ttu-id="e8f43-145">Используйте указанную здесь **конечную точку или значение адреса** из таблицы.</span><span class="sxs-lookup"><span data-stu-id="e8f43-145">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="e8f43-146">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="e8f43-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="e8f43-147">Нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="e8f43-147">Select **Confirm**.</span></span> 
    
    ![OVH confirm TXT for verification](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="e8f43-149">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="e8f43-149">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e8f43-150">Теперь, когда вы добавили запись на сайте регистратора доменных имен, вернитесь в корпорацию Майкрософт и запросите запись.</span><span class="sxs-lookup"><span data-stu-id="e8f43-150">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="e8f43-151">После того как корпорация Майкрософт обнаружит правильную запись TXT, ваш домен будет проверен.</span><span class="sxs-lookup"><span data-stu-id="e8f43-151">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e8f43-152">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="e8f43-152">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="e8f43-153">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="e8f43-153">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="e8f43-154">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="e8f43-154">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="e8f43-155">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="e8f43-155">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="e8f43-p107">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e8f43-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="e8f43-159">Добавление записи MX для отправки электронной почты для вашего домена в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e8f43-159">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="e8f43-160"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="e8f43-160"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="e8f43-p108">Чтобы приступить к работе, откройте страницу со своими доменами на сайте OVH по [этой ссылке](https://www.ovh.com/manager/). Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="e8f43-p108">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="e8f43-164">В разделе **Domains (домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="e8f43-164">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="e8f43-166">Выберите **зону DNS**.</span><span class="sxs-lookup"><span data-stu-id="e8f43-166">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="e8f43-168">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="e8f43-168">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="e8f43-170">Выберите элемент **MX**.</span><span class="sxs-lookup"><span data-stu-id="e8f43-170">Select **MX**.</span></span>
    
    ![OVH MX record type](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="e8f43-172">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="e8f43-172">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="e8f43-173">Чтобы назначить значение TTL, выберите пункт **личное** в раскрывающемся списке, а затем введите значение в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="e8f43-173">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e8f43-174">По умолчанию OVH использует относительную нотацию для целевого значения, которое добавляет доменное имя в конец целевой записи.</span><span class="sxs-lookup"><span data-stu-id="e8f43-174">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="e8f43-175">Чтобы назначить значение TTL, выберите Personalized (Другое) из раскрывающегося списка, а затем введите значение в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="e8f43-175">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="e8f43-176">**Примечание.** По умолчанию в OVH используется относительная нотация, при которой в конец целевой записи добавляется доменное имя. Чтобы использовать абсолютную нотацию, добавьте точку в целевую запись, как показано в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="e8f43-176">**Record type**</span></span>|<span data-ttu-id="e8f43-177">**Sub-domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="e8f43-177">**Sub-domain**</span></span>|<span data-ttu-id="e8f43-178">**Sub-domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="e8f43-178">**TTL**</span></span>|<span data-ttu-id="e8f43-179">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e8f43-179">**Priority**</span></span>|<span data-ttu-id="e8f43-180">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="e8f43-180">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e8f43-181">MX</span><span class="sxs-lookup"><span data-stu-id="e8f43-181">MX</span></span>  <br/> |<span data-ttu-id="e8f43-182">(оставьте пустым)</span><span class="sxs-lookup"><span data-stu-id="e8f43-182">(leave blank)</span></span>  <br/> |<span data-ttu-id="e8f43-183">(Оставьте пустым)</span><span class="sxs-lookup"><span data-stu-id="e8f43-183">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e8f43-184">10 </span><span class="sxs-lookup"><span data-stu-id="e8f43-184">10</span></span>  <br/> <span data-ttu-id="e8f43-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="e8f43-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="e8f43-186">\<ключ_домена\>.mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="e8f43-186">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="e8f43-187">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e8f43-187">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="e8f43-188">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="e8f43-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![Запись MX OVH для почты](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="e8f43-190">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e8f43-190">Select **Next**.</span></span>
    
    ![OVH MX record select Next](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="e8f43-192">Нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="e8f43-192">Select **Confirm**.</span></span>
    
    ![OVH MX record select Confirm](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="e8f43-194">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span><span class="sxs-lookup"><span data-stu-id="e8f43-194">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="e8f43-195">Выберите каждую запись, а затем в столбце **Actions (действия** ) выберите значок Корзина — можно **Удалить** .</span><span class="sxs-lookup"><span data-stu-id="e8f43-195">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![OVH delete MX record](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="e8f43-197">Нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="e8f43-197">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="e8f43-198">Добавление записей CNAME, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e8f43-198">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="e8f43-199"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="e8f43-199"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="e8f43-p113">Чтобы приступить к работе, откройте страницу со своими доменами на сайте OVH по [этой ссылке](https://www.ovh.com/manager/). Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="e8f43-p113">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="e8f43-203">В разделе **Domains (домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="e8f43-203">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="e8f43-205">Выберите **зону DNS**.</span><span class="sxs-lookup"><span data-stu-id="e8f43-205">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="e8f43-207">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="e8f43-207">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="e8f43-209">Выберите элемент **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="e8f43-209">Select **CNAME**.</span></span>
    
    ![OVH add CNAME record type](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="e8f43-211">OVH add CNAME record type</span><span class="sxs-lookup"><span data-stu-id="e8f43-211">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="e8f43-212">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="e8f43-212">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="e8f43-213">Чтобы назначить значение TTL, выберите пункт **личное** в раскрывающемся списке, а затем введите значение в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="e8f43-213">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="e8f43-214">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="e8f43-214">**Record type**</span></span>|<span data-ttu-id="e8f43-215">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="e8f43-215">**Sub-domain**</span></span>|<span data-ttu-id="e8f43-216">**Sub-domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="e8f43-216">**Target**</span></span>|<span data-ttu-id="e8f43-217">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="e8f43-217">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e8f43-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="e8f43-218">CNAME</span></span>  <br/> |<span data-ttu-id="e8f43-219">autodiscover</span><span class="sxs-lookup"><span data-stu-id="e8f43-219">autodiscover</span></span>  <br/> |<span data-ttu-id="e8f43-220">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="e8f43-220">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="e8f43-221">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="e8f43-221">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="e8f43-222">3600 секунд</span><span class="sxs-lookup"><span data-stu-id="e8f43-222">CNAME</span></span>  <br/> |<span data-ttu-id="e8f43-223">sip</span><span class="sxs-lookup"><span data-stu-id="e8f43-223">sip</span></span>  <br/> |<span data-ttu-id="e8f43-224">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e8f43-224">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="e8f43-225">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e8f43-225">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="e8f43-226">3600 секунд</span><span class="sxs-lookup"><span data-stu-id="e8f43-226">CNAME</span></span>  <br/> |<span data-ttu-id="e8f43-227">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e8f43-227">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e8f43-228">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e8f43-228">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="e8f43-229">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e8f43-229">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="e8f43-230">3600 секунд</span><span class="sxs-lookup"><span data-stu-id="e8f43-230">CNAME</span></span>  <br/> |<span data-ttu-id="e8f43-231">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e8f43-231">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e8f43-232">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="e8f43-232">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="e8f43-233">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="e8f43-233">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="e8f43-234">3600 секунд</span><span class="sxs-lookup"><span data-stu-id="e8f43-234">CNAME</span></span>  <br/> |<span data-ttu-id="e8f43-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e8f43-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e8f43-236">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e8f43-236">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="e8f43-237">enterpriseenrollment.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e8f43-237">3600 seconds</span></span>  <br/> |
   
    ![Запись CNAME OVH](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="e8f43-239">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e8f43-239">Select **Next**.</span></span>
    
    ![OVH Add CNAME values and select Next](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="e8f43-241">Нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="e8f43-241">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="e8f43-242">Повторив эти действия, создайте пять других записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="e8f43-242">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="e8f43-243">Создайте пять других записей CNAME, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="e8f43-243">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e8f43-244">Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама</span><span class="sxs-lookup"><span data-stu-id="e8f43-244">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="e8f43-245"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="e8f43-245"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e8f43-246">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="e8f43-246">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e8f43-247">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="e8f43-247">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e8f43-248">Если у вас уже есть запись SPF для вашего домена, не создавайте ее для Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e8f43-248">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="e8f43-249">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="e8f43-249">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="e8f43-p116">Чтобы приступить к работе, откройте страницу со своими доменами на сайте OVH по [этой ссылке](https://www.ovh.com/manager/). Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="e8f43-p116">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="e8f43-253">В разделе **Domains (домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="e8f43-253">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="e8f43-255">Выберите **зону DNS**.</span><span class="sxs-lookup"><span data-stu-id="e8f43-255">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="e8f43-257">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="e8f43-257">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="e8f43-259">Выберите **txt**.</span><span class="sxs-lookup"><span data-stu-id="e8f43-259">Select **TXT**.</span></span>
    
6. <span data-ttu-id="e8f43-260">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="e8f43-260">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="e8f43-261">**Record type**</span><span class="sxs-lookup"><span data-stu-id="e8f43-261">**Record type**</span></span>|<span data-ttu-id="e8f43-262">**Sub-domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="e8f43-262">**Sub-domain**</span></span>|<span data-ttu-id="e8f43-263">**Sub-domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="e8f43-263">**TTL**</span></span>|<span data-ttu-id="e8f43-264">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e8f43-264">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e8f43-265">TXT</span><span class="sxs-lookup"><span data-stu-id="e8f43-265">TXT</span></span>  <br/> |<span data-ttu-id="e8f43-266">(оставьте пустым)</span><span class="sxs-lookup"><span data-stu-id="e8f43-266">(leave blank)</span></span>  <br/> |<span data-ttu-id="e8f43-267">(оставьте пустым)</span><span class="sxs-lookup"><span data-stu-id="e8f43-267">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e8f43-268">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e8f43-268">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="e8f43-269">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="e8f43-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![OVH Добавление записи TXT для SPF](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="e8f43-271">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e8f43-271">Select **Next**.</span></span>
    
    ![OVH добавить запись TXT для SPF и нажмите кнопку Далее.](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="e8f43-273">Нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="e8f43-273">Select **Confirm**.</span></span>
    
    ![OVH Add TXT record for SPF and Confirm](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="e8f43-275">Добавление двух записей SRV, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e8f43-275">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="e8f43-276"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="e8f43-276"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="e8f43-p117">Чтобы приступить к работе, откройте страницу со своими доменами на сайте OVH по [этой ссылке](https://www.ovh.com/manager/). Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="e8f43-p117">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="e8f43-280">В разделе **Domains (домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="e8f43-280">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="e8f43-282">Выберите **зону DNS**.</span><span class="sxs-lookup"><span data-stu-id="e8f43-282">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="e8f43-284">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="e8f43-284">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="e8f43-286">Выберите пункт **SRV**.</span><span class="sxs-lookup"><span data-stu-id="e8f43-286">Select **SRV**.</span></span>
    
    ![OVH select SRV record type](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="e8f43-288">Создайте первую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="e8f43-288">Create the first SRV record.</span></span>
    
    <span data-ttu-id="e8f43-289">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="e8f43-289">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="e8f43-290">Чтобы назначить значение TTL, выберите пункт **личное** в раскрывающемся списке, а затем введите значение в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="e8f43-290">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="e8f43-291">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="e8f43-291">**Record type**</span></span>|<span data-ttu-id="e8f43-292">**Sub-domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="e8f43-292">**Sub-domain**</span></span>|<span data-ttu-id="e8f43-293">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="e8f43-293">**Priority**</span></span>|<span data-ttu-id="e8f43-294">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="e8f43-294">**Weight**</span></span>|<span data-ttu-id="e8f43-295">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="e8f43-295">**Port**</span></span>|<span data-ttu-id="e8f43-296">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="e8f43-296">**TTL**</span></span>|<span data-ttu-id="e8f43-297">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="e8f43-297">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e8f43-298">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="e8f43-298">SRV (Service)</span></span>  <br/> |<span data-ttu-id="e8f43-299">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="e8f43-299">_sip._tls</span></span>  <br/> |<span data-ttu-id="e8f43-300">100</span><span class="sxs-lookup"><span data-stu-id="e8f43-300">100</span></span>  <br/> |<span data-ttu-id="e8f43-301">1,1</span><span class="sxs-lookup"><span data-stu-id="e8f43-301">1</span></span>  <br/> |<span data-ttu-id="e8f43-302">443</span><span class="sxs-lookup"><span data-stu-id="e8f43-302">443</span></span>  <br/> |<span data-ttu-id="e8f43-303">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="e8f43-303">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e8f43-304">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e8f43-304">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="e8f43-305">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="e8f43-305">SRV (Service)</span></span>  <br/> |<span data-ttu-id="e8f43-306">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="e8f43-306">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="e8f43-307">100</span><span class="sxs-lookup"><span data-stu-id="e8f43-307">100</span></span>  <br/> |<span data-ttu-id="e8f43-308">1,1</span><span class="sxs-lookup"><span data-stu-id="e8f43-308">1</span></span>  <br/> |<span data-ttu-id="e8f43-309">5061</span><span class="sxs-lookup"><span data-stu-id="e8f43-309">5061</span></span>  <br/> |<span data-ttu-id="e8f43-310">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="e8f43-310">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e8f43-311">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e8f43-311">sipfed.online.lync.com.</span></span>  <br/> |
       
    ![Запись SRV OVH](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="e8f43-313">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e8f43-313">Select **Next**.</span></span>
    
    ![OVH SRV record select Next](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="e8f43-315">Нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="e8f43-315">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="e8f43-p119">Повторите эти действия для другой записи SRV. В поля для второй записи введите (или скопируйте и вставьте) значения из второй строки приведенной выше таблицы.</span><span class="sxs-lookup"><span data-stu-id="e8f43-p119">Repeat the previous steps to create the other SRV record. Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="e8f43-p120">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e8f43-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
