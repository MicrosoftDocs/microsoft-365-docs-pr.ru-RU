---
title: Создание записей DNS для Office 365 на сайте OVH
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу OVH для Office 365.
ms.openlocfilehash: 87de24fd47ce048cb88a2b7d4bcff97b1c155456
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42248968"
---
# <a name="create-dns-records-at-ovh-for-office-365"></a><span data-ttu-id="9e7d9-103">Создание записей DNS для Office 365 на сайте OVH</span><span class="sxs-lookup"><span data-stu-id="9e7d9-103">Create DNS records at OVH for Office 365</span></span>

<span data-ttu-id="9e7d9-104">Если вы не нашли нужную информацию, см. [вопросы и ответы по доменам](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="9e7d9-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9e7d9-105">Если ваш поставщик услуг размещения DNS  OVH, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="9e7d9-106">Ниже перечислены основные записи, которые нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="9e7d9-107">Создание записей DNS для Office 365 в OVH</span><span class="sxs-lookup"><span data-stu-id="9e7d9-107">Create DNS records at OVH for Office 365</span></span>](#create-dns-records-at-ovh-for-office-365)
    
- [<span data-ttu-id="9e7d9-108">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в Office 365.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="9e7d9-109">Добавление записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="9e7d9-109">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="9e7d9-110">Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="9e7d9-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="9e7d9-111">Добавление двух записей SRV, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="9e7d9-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="9e7d9-112">Когда вы добавите эти записи на сайте OVH, ваш домен будет настроен для работы со службами Office 365.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-112">After you add these records at OVH, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="9e7d9-113">Дополнительные сведения о веб-хостинге и DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="9e7d9-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="9e7d9-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9e7d9-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="9e7d9-117">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="9e7d9-117">Add a TXT record for verification</span></span>
<span data-ttu-id="9e7d9-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="9e7d9-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="9e7d9-p102">Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете данным доменом.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9e7d9-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="9e7d9-p104">Чтобы приступить к работе, откройте страницу со своими доменами на сайте OVH по [этой ссылке](https://www.ovh.com/manager/). Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-p104">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="9e7d9-126">В разделе **Domains (домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-126">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="9e7d9-128">Выберите **зону DNS**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-128">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="9e7d9-130">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-130">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="9e7d9-132">Выбор **txt**</span><span class="sxs-lookup"><span data-stu-id="9e7d9-132">Select **TXT**</span></span>
    
    ![OVH выбрать запись TXT](../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="9e7d9-134">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-134">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="9e7d9-135">Чтобы назначить значение TTL, выберите пункт **личное** в раскрывающемся списке, а затем введите значение в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-135">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="9e7d9-136">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="9e7d9-136">**Record type**</span></span>|<span data-ttu-id="9e7d9-137">**Sub-domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="9e7d9-137">**Sub-domain**</span></span>|<span data-ttu-id="9e7d9-138">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9e7d9-138">**TTL**</span></span>|<span data-ttu-id="9e7d9-139">**Значение**</span><span class="sxs-lookup"><span data-stu-id="9e7d9-139">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9e7d9-140">TXT</span><span class="sxs-lookup"><span data-stu-id="9e7d9-140">TXT</span></span>  <br/> |<span data-ttu-id="9e7d9-141">(Оставьте пустым)</span><span class="sxs-lookup"><span data-stu-id="9e7d9-141">(leave blank)</span></span>  <br/> |<span data-ttu-id="9e7d9-142">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="9e7d9-142">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="9e7d9-143">MS=msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="9e7d9-143">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="9e7d9-p106">**Примечание.** Это пример. Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.           [Где это находится?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="9e7d9-p106">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
7. <span data-ttu-id="9e7d9-147">Нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-147">Select **Confirm**.</span></span> 
    
    ![OVH confirm TXT for verification](../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="9e7d9-149">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-149">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="9e7d9-150">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-150">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="9e7d9-151">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-151">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9e7d9-152">В центре администрирования перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> **параметров** \> ".</span><span class="sxs-lookup"><span data-stu-id="9e7d9-152">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="9e7d9-153">На странице **Domains (домены** ) выберите домен, который вы хотите проверить.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-153">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="9e7d9-154">На странице **Настройка** выберите пункт **Запуск программы установки**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-154">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="9e7d9-155">На странице **Проверка домена** нажмите кнопку **проверить**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-155">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="9e7d9-p107">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9e7d9-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="9e7d9-159">Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="9e7d9-159">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="9e7d9-160"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="9e7d9-160"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="9e7d9-p108">Чтобы приступить к работе, откройте страницу со своими доменами на сайте OVH по [этой ссылке](https://www.ovh.com/manager/). Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-p108">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="9e7d9-164">В разделе **Domains (домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-164">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="9e7d9-166">Выберите **зону DNS**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-166">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="9e7d9-168">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-168">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="9e7d9-170">Выберите элемент **MX**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-170">Select **MX**.</span></span>
    
    ![OVH MX record type](../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="9e7d9-172">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-172">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="9e7d9-173">Чтобы назначить значение TTL, выберите пункт **личное** в раскрывающемся списке, а затем введите значение в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-173">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="9e7d9-174">По умолчанию OVH использует относительную нотацию для целевого значения, которое добавляет доменное имя в конец целевой записи.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-174">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="9e7d9-175">Чтобы назначить значение TTL, выберите Personalized (Другое) из раскрывающегося списка, а затем введите значение в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-175">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="9e7d9-176">**Примечание.** По умолчанию в OVH используется относительная нотация, при которой в конец целевой записи добавляется доменное имя. Чтобы использовать абсолютную нотацию, добавьте точку в целевую запись, как показано в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-176">**Record type**</span></span>|<span data-ttu-id="9e7d9-177">**Sub-domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="9e7d9-177">**Sub-domain**</span></span>|<span data-ttu-id="9e7d9-178">**Sub-domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="9e7d9-178">**TTL**</span></span>|<span data-ttu-id="9e7d9-179">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9e7d9-179">**Priority**</span></span>|<span data-ttu-id="9e7d9-180">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="9e7d9-180">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9e7d9-181">MX</span><span class="sxs-lookup"><span data-stu-id="9e7d9-181">MX</span></span>  <br/> |<span data-ttu-id="9e7d9-182">(оставьте пустым)</span><span class="sxs-lookup"><span data-stu-id="9e7d9-182">(leave blank)</span></span>  <br/> |<span data-ttu-id="9e7d9-183">(Оставьте пустым)</span><span class="sxs-lookup"><span data-stu-id="9e7d9-183">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="9e7d9-184">10 </span><span class="sxs-lookup"><span data-stu-id="9e7d9-184">10</span></span>  <br/> <span data-ttu-id="9e7d9-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="9e7d9-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="9e7d9-186">\<ключ_домена\>.mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-186">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="9e7d9-187">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Office 365.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-187">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="9e7d9-188">Как найти это значение?</span><span class="sxs-lookup"><span data-stu-id="9e7d9-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![Запись MX OVH для почты](../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="9e7d9-190">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-190">Select **Next**.</span></span>
    
    ![OVH MX record select Next](../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="9e7d9-192">Нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-192">Select **Confirm**.</span></span>
    
    ![OVH MX record select Confirm](../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="9e7d9-194">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-194">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="9e7d9-195">Выберите каждую запись, а затем в столбце **Actions (действия** ) выберите значок Корзина — можно **Удалить** .</span><span class="sxs-lookup"><span data-stu-id="9e7d9-195">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![OVH delete MX record](../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="9e7d9-197">Нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-197">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="9e7d9-198">Добавление записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="9e7d9-198">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="9e7d9-199"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="9e7d9-199"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="9e7d9-p113">Чтобы приступить к работе, откройте страницу со своими доменами на сайте OVH по [этой ссылке](https://www.ovh.com/manager/). Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-p113">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="9e7d9-203">В разделе **Domains (домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-203">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="9e7d9-205">Выберите **зону DNS**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-205">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="9e7d9-207">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-207">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="9e7d9-209">Выберите элемент **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-209">Select **CNAME**.</span></span>
    
    ![OVH add CNAME record type](../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="9e7d9-211">OVH add CNAME record type</span><span class="sxs-lookup"><span data-stu-id="9e7d9-211">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="9e7d9-212">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-212">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="9e7d9-213">Чтобы назначить значение TTL, выберите пункт **личное** в раскрывающемся списке, а затем введите значение в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-213">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="9e7d9-214">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="9e7d9-214">**Record type**</span></span>|<span data-ttu-id="9e7d9-215">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="9e7d9-215">**Sub-domain**</span></span>|<span data-ttu-id="9e7d9-216">**Sub-domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="9e7d9-216">**Target**</span></span>|<span data-ttu-id="9e7d9-217">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="9e7d9-217">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9e7d9-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="9e7d9-218">CNAME</span></span>  <br/> |<span data-ttu-id="9e7d9-219">autodiscover</span><span class="sxs-lookup"><span data-stu-id="9e7d9-219">autodiscover</span></span>  <br/> |<span data-ttu-id="9e7d9-220">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-220">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="9e7d9-221">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-221">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="9e7d9-222">3600 секунд</span><span class="sxs-lookup"><span data-stu-id="9e7d9-222">CNAME</span></span>  <br/> |<span data-ttu-id="9e7d9-223">sip</span><span class="sxs-lookup"><span data-stu-id="9e7d9-223">sip</span></span>  <br/> |<span data-ttu-id="9e7d9-224">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-224">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="9e7d9-225">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-225">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="9e7d9-226">3600 секунд</span><span class="sxs-lookup"><span data-stu-id="9e7d9-226">CNAME</span></span>  <br/> |<span data-ttu-id="9e7d9-227">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9e7d9-227">lyncdiscover</span></span>  <br/> |<span data-ttu-id="9e7d9-228">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-228">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="9e7d9-229">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-229">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="9e7d9-230">3600 секунд</span><span class="sxs-lookup"><span data-stu-id="9e7d9-230">CNAME</span></span>  <br/> |<span data-ttu-id="9e7d9-231">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="9e7d9-231">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="9e7d9-232">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-232">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="9e7d9-233">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-233">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="9e7d9-234">3600 секунд</span><span class="sxs-lookup"><span data-stu-id="9e7d9-234">CNAME</span></span>  <br/> |<span data-ttu-id="9e7d9-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="9e7d9-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="9e7d9-236">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-236">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="9e7d9-237">enterpriseenrollment.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-237">3600 seconds</span></span>  <br/> |
   
    ![Запись CNAME OVH](../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="9e7d9-239">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-239">Select **Next**.</span></span>
    
    ![OVH Add CNAME values and select Next](../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="9e7d9-241">Нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-241">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="9e7d9-242">Повторив эти действия, создайте пять других записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-242">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="9e7d9-243">Создайте пять других записей CNAME, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-243">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="9e7d9-244">Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="9e7d9-244">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="9e7d9-245"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="9e7d9-245"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e7d9-246">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-246">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="9e7d9-247">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-247">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="9e7d9-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="9e7d9-249">Вместо этого добавьте необходимые значения Office 365 к текущей записи, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-249">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="9e7d9-p116">Чтобы приступить к работе, откройте страницу со своими доменами на сайте OVH по [этой ссылке](https://www.ovh.com/manager/). Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-p116">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="9e7d9-253">В разделе **Domains (домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-253">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="9e7d9-255">Выберите **зону DNS**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-255">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="9e7d9-257">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-257">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="9e7d9-259">Выберите **txt**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-259">Select **TXT**.</span></span>
    
6. <span data-ttu-id="9e7d9-260">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-260">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="9e7d9-261">**Record type**</span><span class="sxs-lookup"><span data-stu-id="9e7d9-261">**Record type**</span></span>|<span data-ttu-id="9e7d9-262">**Sub-domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="9e7d9-262">**Sub-domain**</span></span>|<span data-ttu-id="9e7d9-263">**Sub-domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="9e7d9-263">**TTL**</span></span>|<span data-ttu-id="9e7d9-264">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9e7d9-264">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9e7d9-265">TXT</span><span class="sxs-lookup"><span data-stu-id="9e7d9-265">TXT</span></span>  <br/> |<span data-ttu-id="9e7d9-266">(оставьте пустым)</span><span class="sxs-lookup"><span data-stu-id="9e7d9-266">(leave blank)</span></span>  <br/> |<span data-ttu-id="9e7d9-267">(оставьте пустым)</span><span class="sxs-lookup"><span data-stu-id="9e7d9-267">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="9e7d9-268">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="9e7d9-268">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="9e7d9-269">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="9e7d9-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![OVH Добавление записи TXT для SPF](../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="9e7d9-271">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-271">Select **Next**.</span></span>
    
    ![OVH добавить запись TXT для SPF и нажмите кнопку Далее.](../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="9e7d9-273">Нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-273">Select **Confirm**.</span></span>
    
    ![OVH Add TXT record for SPF and Confirm](../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="9e7d9-275">Добавление двух записей SRV, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="9e7d9-275">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="9e7d9-276"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="9e7d9-276"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="9e7d9-p117">Чтобы приступить к работе, откройте страницу со своими доменами на сайте OVH по [этой ссылке](https://www.ovh.com/manager/). Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-p117">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="9e7d9-280">В разделе **Domains (домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-280">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="9e7d9-282">Выберите **зону DNS**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-282">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="9e7d9-284">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-284">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="9e7d9-286">Выберите пункт **SRV**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-286">Select **SRV**.</span></span>
    
    ![OVH select SRV record type](../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="9e7d9-288">Создайте первую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-288">Create the first SRV record.</span></span>
    
    <span data-ttu-id="9e7d9-289">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-289">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="9e7d9-290">Чтобы назначить значение TTL, выберите пункт **личное** в раскрывающемся списке, а затем введите значение в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-290">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="9e7d9-291">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="9e7d9-291">**Record type**</span></span>|<span data-ttu-id="9e7d9-292">**Sub-domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="9e7d9-292">**Sub-domain**</span></span>|<span data-ttu-id="9e7d9-293">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="9e7d9-293">**Priority**</span></span>|<span data-ttu-id="9e7d9-294">**Weight (Вес)**</span><span class="sxs-lookup"><span data-stu-id="9e7d9-294">**Weight**</span></span>|<span data-ttu-id="9e7d9-295">**Port (Порт)**</span><span class="sxs-lookup"><span data-stu-id="9e7d9-295">**Port**</span></span>|<span data-ttu-id="9e7d9-296">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="9e7d9-296">**TTL**</span></span>|<span data-ttu-id="9e7d9-297">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="9e7d9-297">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9e7d9-298">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="9e7d9-298">SRV (Service)</span></span>  <br/> |<span data-ttu-id="9e7d9-299">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="9e7d9-299">_sip._tls</span></span>  <br/> |<span data-ttu-id="9e7d9-300">100</span><span class="sxs-lookup"><span data-stu-id="9e7d9-300">100</span></span>  <br/> |<span data-ttu-id="9e7d9-301">1,1</span><span class="sxs-lookup"><span data-stu-id="9e7d9-301">1</span></span>  <br/> |<span data-ttu-id="9e7d9-302">443</span><span class="sxs-lookup"><span data-stu-id="9e7d9-302">443</span></span>  <br/> |<span data-ttu-id="9e7d9-303">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="9e7d9-303">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="9e7d9-304">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-304">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="9e7d9-305">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="9e7d9-305">SRV (Service)</span></span>  <br/> |<span data-ttu-id="9e7d9-306">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="9e7d9-306">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="9e7d9-307">100</span><span class="sxs-lookup"><span data-stu-id="9e7d9-307">100</span></span>  <br/> |<span data-ttu-id="9e7d9-308">1,1</span><span class="sxs-lookup"><span data-stu-id="9e7d9-308">1</span></span>  <br/> |<span data-ttu-id="9e7d9-309">5061</span><span class="sxs-lookup"><span data-stu-id="9e7d9-309">5061</span></span>  <br/> |<span data-ttu-id="9e7d9-310">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="9e7d9-310">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="9e7d9-311">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-311">sipfed.online.lync.com.</span></span>  <br/> |
       
    ![Запись SRV OVH](../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="9e7d9-313">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-313">Select **Next**.</span></span>
    
    ![OVH SRV record select Next](../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="9e7d9-315">Нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-315">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="9e7d9-p119">Повторите эти действия для другой записи SRV. В поля для второй записи введите (или скопируйте и вставьте) значения из второй строки приведенной выше таблицы.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-p119">Repeat the previous steps to create the other SRV record. Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="9e7d9-p120">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9e7d9-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
