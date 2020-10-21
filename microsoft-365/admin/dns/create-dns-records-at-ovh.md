---
title: Создание записей DNS на сайте OVH для Майкрософт
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу OVH для Майкрософт.
ms.openlocfilehash: 87a2a731a253fdc0593a1aae8020e615dca63c4a
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645819"
---
# <a name="create-dns-records-at-ovh-for-microsoft"></a><span data-ttu-id="8705b-103">Создание записей DNS на сайте OVH для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8705b-103">Create DNS records at OVH for Microsoft</span></span>

<span data-ttu-id="8705b-104">Если вы не нашли нужную информацию, см. [вопросы и ответы по доменам](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="8705b-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="8705b-105">Если ваш поставщик услуг размещения DNS  OVH, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб.</span><span class="sxs-lookup"><span data-stu-id="8705b-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="8705b-106">Ниже перечислены основные записи, которые нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="8705b-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="8705b-107">Создание записей DNS на сайте OVH для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8705b-107">Create DNS records at OVH for Microsoft</span></span>](#create-dns-records-at-ovh-for-microsoft)
    
- [<span data-ttu-id="8705b-108">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8705b-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="8705b-109">Добавление записей CNAME, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8705b-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="8705b-110">Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="8705b-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="8705b-111">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8705b-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="8705b-112">Когда вы добавите эти записи на сайте OVH, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8705b-112">After you add these records at OVH, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="8705b-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8705b-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="8705b-116">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="8705b-116">Add a TXT record for verification</span></span>
<span data-ttu-id="8705b-117"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="8705b-117"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="8705b-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="8705b-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8705b-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="8705b-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="8705b-p104">Чтобы приступить к работе, откройте страницу со своими доменами на сайте OVH по [этой ссылке](https://www.ovh.com/manager/). Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="8705b-p104">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="8705b-125">В разделе **Domains (домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="8705b-125">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="8705b-127">Выберите **зону DNS**.</span><span class="sxs-lookup"><span data-stu-id="8705b-127">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="8705b-129">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="8705b-129">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="8705b-131">Выбор **txt**</span><span class="sxs-lookup"><span data-stu-id="8705b-131">Select **TXT**</span></span>
    
    ![OVH выбрать запись TXT](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="8705b-133">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="8705b-133">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="8705b-134">Чтобы назначить значение TTL, выберите пункт **личное** в раскрывающемся списке, а затем введите значение в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="8705b-134">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="8705b-135">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="8705b-135">**Record type**</span></span>|<span data-ttu-id="8705b-136">**Sub-domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="8705b-136">**Sub-domain**</span></span>|<span data-ttu-id="8705b-137">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8705b-137">**TTL**</span></span>|<span data-ttu-id="8705b-138">**Значение**</span><span class="sxs-lookup"><span data-stu-id="8705b-138">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8705b-139">TXT</span><span class="sxs-lookup"><span data-stu-id="8705b-139">TXT</span></span>  <br/> |<span data-ttu-id="8705b-140">(оставьте пустым)</span><span class="sxs-lookup"><span data-stu-id="8705b-140">(leave blank)</span></span>  <br/> |<span data-ttu-id="8705b-141">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="8705b-141">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="8705b-142">MS=msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="8705b-142">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="8705b-143">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="8705b-143">**Note:** This is an example.</span></span> <span data-ttu-id="8705b-144">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="8705b-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="8705b-145">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="8705b-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="8705b-146">Выберите **Подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="8705b-146">Select **Confirm**.</span></span> 
    
    ![OVH confirm TXT for verification](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="8705b-148">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="8705b-148">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="8705b-149">Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.</span><span class="sxs-lookup"><span data-stu-id="8705b-149">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="8705b-150">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="8705b-150">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="8705b-151">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="8705b-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="8705b-152">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="8705b-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="8705b-153">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="8705b-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="8705b-154">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="8705b-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="8705b-p107">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8705b-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="8705b-158">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8705b-158">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="8705b-159"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="8705b-159"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="8705b-p108">Чтобы приступить к работе, откройте страницу со своими доменами на сайте OVH по [этой ссылке](https://www.ovh.com/manager/). Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="8705b-p108">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="8705b-163">В разделе **Domains (домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="8705b-163">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="8705b-165">Выберите **зону DNS**.</span><span class="sxs-lookup"><span data-stu-id="8705b-165">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="8705b-167">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="8705b-167">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="8705b-169">Выберите элемент **MX**.</span><span class="sxs-lookup"><span data-stu-id="8705b-169">Select **MX**.</span></span>
    
    ![OVH MX record type](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="8705b-171">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="8705b-171">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="8705b-172">Чтобы назначить значение TTL, выберите пункт **личное** в раскрывающемся списке, а затем введите значение в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="8705b-172">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="8705b-173">По умолчанию OVH использует относительную нотацию для целевого значения, которое добавляет доменное имя в конец целевой записи.</span><span class="sxs-lookup"><span data-stu-id="8705b-173">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="8705b-174">Чтобы назначить значение TTL, выберите Personalized (Другое) из раскрывающегося списка, а затем введите значение в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="8705b-174">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="8705b-175">**Примечание.** По умолчанию в OVH используется относительная нотация, при которой в конец целевой записи добавляется доменное имя. Чтобы использовать абсолютную нотацию, добавьте точку в целевую запись, как показано в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="8705b-175">**Record type**</span></span>|<span data-ttu-id="8705b-176">**Sub-domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="8705b-176">**Sub-domain**</span></span>|<span data-ttu-id="8705b-177">**Sub-domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="8705b-177">**TTL**</span></span>|<span data-ttu-id="8705b-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8705b-178">**Priority**</span></span>|<span data-ttu-id="8705b-179">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="8705b-179">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8705b-180">MX</span><span class="sxs-lookup"><span data-stu-id="8705b-180">MX</span></span>  <br/> |<span data-ttu-id="8705b-181">(оставьте пустым)</span><span class="sxs-lookup"><span data-stu-id="8705b-181">(leave blank)</span></span>  <br/> |<span data-ttu-id="8705b-182">(Оставьте пустым)</span><span class="sxs-lookup"><span data-stu-id="8705b-182">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="8705b-183">10 </span><span class="sxs-lookup"><span data-stu-id="8705b-183">10</span></span>  <br/> <span data-ttu-id="8705b-184">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).   </span><span class="sxs-lookup"><span data-stu-id="8705b-184">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="8705b-185">\<domain-key\>. mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="8705b-185">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="8705b-186">**Примечание:** Получение  *\<domain-key\>*  учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8705b-186">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="8705b-187">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="8705b-187">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![Запись MX OVH для почты](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="8705b-189">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8705b-189">Select **Next**.</span></span>
    
    ![OVH MX record select Next](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="8705b-191">Выберите **Подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="8705b-191">Select **Confirm**.</span></span>
    
    ![OVH MX record select Confirm](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="8705b-193">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span><span class="sxs-lookup"><span data-stu-id="8705b-193">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="8705b-194">Выберите каждую запись, а затем в столбце **Actions (действия** ) выберите значок Корзина — можно **Удалить** .</span><span class="sxs-lookup"><span data-stu-id="8705b-194">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![OVH delete MX record](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="8705b-196">Выберите **Подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="8705b-196">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="8705b-197">Добавление записей CNAME, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8705b-197">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="8705b-198"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="8705b-198"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="8705b-p113">Чтобы приступить к работе, откройте страницу со своими доменами на сайте OVH по [этой ссылке](https://www.ovh.com/manager/). Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="8705b-p113">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="8705b-202">В разделе **Domains (домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="8705b-202">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="8705b-204">Выберите **зону DNS**.</span><span class="sxs-lookup"><span data-stu-id="8705b-204">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="8705b-206">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="8705b-206">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="8705b-208">Выберите элемент **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="8705b-208">Select **CNAME**.</span></span>
    
    ![OVH add CNAME record type](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="8705b-210">OVH add CNAME record type</span><span class="sxs-lookup"><span data-stu-id="8705b-210">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="8705b-211">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="8705b-211">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="8705b-212">Чтобы назначить значение TTL, выберите пункт **личное** в раскрывающемся списке, а затем введите значение в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="8705b-212">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="8705b-213">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="8705b-213">**Record type**</span></span>|<span data-ttu-id="8705b-214">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="8705b-214">**Sub-domain**</span></span>|<span data-ttu-id="8705b-215">**Sub-domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="8705b-215">**Target**</span></span>|<span data-ttu-id="8705b-216">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="8705b-216">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8705b-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="8705b-217">CNAME</span></span>  <br/> |<span data-ttu-id="8705b-218">autodiscover</span><span class="sxs-lookup"><span data-stu-id="8705b-218">autodiscover</span></span>  <br/> |<span data-ttu-id="8705b-219">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="8705b-219">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="8705b-220">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="8705b-220">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="8705b-221">3600 секунд</span><span class="sxs-lookup"><span data-stu-id="8705b-221">CNAME</span></span>  <br/> |<span data-ttu-id="8705b-222">sip</span><span class="sxs-lookup"><span data-stu-id="8705b-222">sip</span></span>  <br/> |<span data-ttu-id="8705b-223">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8705b-223">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="8705b-224">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8705b-224">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="8705b-225">3600 секунд</span><span class="sxs-lookup"><span data-stu-id="8705b-225">CNAME</span></span>  <br/> |<span data-ttu-id="8705b-226">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8705b-226">lyncdiscover</span></span>  <br/> |<span data-ttu-id="8705b-227">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8705b-227">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="8705b-228">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8705b-228">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="8705b-229">3600 секунд</span><span class="sxs-lookup"><span data-stu-id="8705b-229">CNAME</span></span>  <br/> |<span data-ttu-id="8705b-230">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="8705b-230">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="8705b-231">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="8705b-231">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="8705b-232">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="8705b-232">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="8705b-233">3600 секунд</span><span class="sxs-lookup"><span data-stu-id="8705b-233">CNAME</span></span>  <br/> |<span data-ttu-id="8705b-234">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="8705b-234">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="8705b-235">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="8705b-235">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="8705b-236">enterpriseenrollment.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="8705b-236">3600 seconds</span></span>  <br/> |
   
    ![Запись CNAME OVH](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="8705b-238">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8705b-238">Select **Next**.</span></span>
    
    ![OVH Add CNAME values and select Next](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="8705b-240">Выберите **Подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="8705b-240">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="8705b-241">Повторив эти действия, создайте пять других записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="8705b-241">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="8705b-242">Создайте пять других записей CNAME, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="8705b-242">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="8705b-243">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="8705b-243">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="8705b-244"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="8705b-244"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="8705b-245">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="8705b-245">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="8705b-246">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="8705b-246">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="8705b-247">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8705b-247">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="8705b-248">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь  *одну*  запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="8705b-248">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="8705b-p116">Чтобы приступить к работе, откройте страницу со своими доменами на сайте OVH по [этой ссылке](https://www.ovh.com/manager/). Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="8705b-p116">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="8705b-252">В разделе **Domains (домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="8705b-252">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="8705b-254">Выберите **зону DNS**.</span><span class="sxs-lookup"><span data-stu-id="8705b-254">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="8705b-256">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="8705b-256">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="8705b-258">Выберите **txt**.</span><span class="sxs-lookup"><span data-stu-id="8705b-258">Select **TXT**.</span></span>
    
6. <span data-ttu-id="8705b-259">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="8705b-259">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="8705b-260">**Record type**</span><span class="sxs-lookup"><span data-stu-id="8705b-260">**Record type**</span></span>|<span data-ttu-id="8705b-261">**Sub-domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="8705b-261">**Sub-domain**</span></span>|<span data-ttu-id="8705b-262">**Sub-domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="8705b-262">**TTL**</span></span>|<span data-ttu-id="8705b-263">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8705b-263">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8705b-264">TXT</span><span class="sxs-lookup"><span data-stu-id="8705b-264">TXT</span></span>  <br/> |<span data-ttu-id="8705b-265">(оставьте пустым)</span><span class="sxs-lookup"><span data-stu-id="8705b-265">(leave blank)</span></span>  <br/> |<span data-ttu-id="8705b-266">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="8705b-266">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="8705b-267">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="8705b-267">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="8705b-268">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="8705b-268">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![OVH Добавление записи TXT для SPF](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="8705b-270">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8705b-270">Select **Next**.</span></span>
    
    ![OVH добавить запись TXT для SPF и нажмите кнопку Далее.](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="8705b-272">Выберите **Подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="8705b-272">Select **Confirm**.</span></span>
    
    ![OVH Add TXT record for SPF and Confirm](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="8705b-274">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8705b-274">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="8705b-275"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="8705b-275"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="8705b-p117">Чтобы приступить к работе, откройте страницу со своими доменами на сайте OVH по [этой ссылке](https://www.ovh.com/manager/). Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="8705b-p117">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="8705b-279">В разделе **Domains (домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="8705b-279">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="8705b-281">Выберите **зону DNS**.</span><span class="sxs-lookup"><span data-stu-id="8705b-281">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="8705b-283">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="8705b-283">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="8705b-285">Выберите пункт **SRV**.</span><span class="sxs-lookup"><span data-stu-id="8705b-285">Select **SRV**.</span></span>
    
    ![OVH select SRV record type](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="8705b-287">Создайте первую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="8705b-287">Create the first SRV record.</span></span>
    
    <span data-ttu-id="8705b-288">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="8705b-288">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="8705b-289">Чтобы назначить значение TTL, выберите пункт **личное** в раскрывающемся списке, а затем введите значение в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="8705b-289">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="8705b-290">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="8705b-290">**Record type**</span></span>|<span data-ttu-id="8705b-291">**Sub-domain (Поддомен)**</span><span class="sxs-lookup"><span data-stu-id="8705b-291">**Sub-domain**</span></span>|<span data-ttu-id="8705b-292">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="8705b-292">**Priority**</span></span>|<span data-ttu-id="8705b-293">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="8705b-293">**Weight**</span></span>|<span data-ttu-id="8705b-294">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="8705b-294">**Port**</span></span>|<span data-ttu-id="8705b-295">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="8705b-295">**TTL**</span></span>|<span data-ttu-id="8705b-296">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="8705b-296">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8705b-297">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="8705b-297">SRV (Service)</span></span>  <br/> |<span data-ttu-id="8705b-298">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="8705b-298">_sip._tls</span></span>  <br/> |<span data-ttu-id="8705b-299">100</span><span class="sxs-lookup"><span data-stu-id="8705b-299">100</span></span>  <br/> |<span data-ttu-id="8705b-300">1,1</span><span class="sxs-lookup"><span data-stu-id="8705b-300">1</span></span>  <br/> |<span data-ttu-id="8705b-301">443</span><span class="sxs-lookup"><span data-stu-id="8705b-301">443</span></span>  <br/> |<span data-ttu-id="8705b-302">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="8705b-302">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="8705b-303">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8705b-303">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="8705b-304">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="8705b-304">SRV (Service)</span></span>  <br/> |<span data-ttu-id="8705b-305">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="8705b-305">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="8705b-306">100</span><span class="sxs-lookup"><span data-stu-id="8705b-306">100</span></span>  <br/> |<span data-ttu-id="8705b-307">1,1</span><span class="sxs-lookup"><span data-stu-id="8705b-307">1</span></span>  <br/> |<span data-ttu-id="8705b-308">5061</span><span class="sxs-lookup"><span data-stu-id="8705b-308">5061</span></span>  <br/> |<span data-ttu-id="8705b-309">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="8705b-309">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="8705b-310">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8705b-310">sipfed.online.lync.com.</span></span>  <br/> |
       
    ![Запись SRV OVH](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="8705b-312">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8705b-312">Select **Next**.</span></span>
    
    ![OVH SRV record select Next](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="8705b-314">Выберите **Подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="8705b-314">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="8705b-p119">Повторите эти действия для другой записи SRV. В поля для второй записи введите (или скопируйте и вставьте) значения из второй строки приведенной выше таблицы.</span><span class="sxs-lookup"><span data-stu-id="8705b-p119">Repeat the previous steps to create the other SRV record. Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="8705b-p120">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8705b-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
