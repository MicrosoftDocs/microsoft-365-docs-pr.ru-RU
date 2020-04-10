---
title: Создание записей DNS для Office 365 на сайте Freenom
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу Freenom для Office 365.
ms.openlocfilehash: d8c33df611a0ef1be95d32026f5d6b99808258f6
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211755"
---
# <a name="create-dns-records-at-freenom-for-office-365"></a><span data-ttu-id="16561-103">Создание записей DNS для Office 365 на сайте Freenom</span><span class="sxs-lookup"><span data-stu-id="16561-103">Create DNS records at Freenom for Office 365</span></span>

<span data-ttu-id="16561-104">Если вы не нашли нужную информацию, см. статью [Вопросы и ответы о доменах](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="16561-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="16561-p101">На веб-сайте Freenom не поддерживаются записи SRV, поэтому некоторые функции Skype для бизнеса Online и Outlook Web App не будут работать. Независимо от того, какой план Office 365 вы используете, на веб-сайте Freenom могут действовать существенные ограничения служб, поэтому стоит задуматься о переходе на другого поставщика услуг размещения DNS.</span><span class="sxs-lookup"><span data-stu-id="16561-p101">The Freenom website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, there are significant service limitations, and you may want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="16561-107">Если несмотря на ограничения службы, вы решили управлять собственными записями DNS для Office 365 по адресу Freenom, выполнив действия, описанные в этой статье, чтобы проверить домен и настроить записи DNS для электронной почты и других служб.</span><span class="sxs-lookup"><span data-stu-id="16561-107">If despite the service limitations, you choose to manage your own Office 365 DNS records at Freenom, follow the steps in this article to verify your domain and set up DNS records for email and other services.</span></span>
  
<span data-ttu-id="16561-108">Дополнительные сведения о веб-хостинге и DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="16561-108">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="16561-p102">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="16561-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="16561-112">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="16561-112">Add a TXT record for verification</span></span>
<span data-ttu-id="16561-113"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="16561-113"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="16561-p103">Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="16561-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="16561-p104">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="16561-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="16561-118">Чтобы приступить к работе, откройте страницу со своими доменами в Freenom с помощью [этой ссылки](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="16561-118">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="16561-119">Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="16561-119">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="16561-121">Выберите **службы**, а затем выберите пункт **Мои домены**.</span><span class="sxs-lookup"><span data-stu-id="16561-121">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="16561-123">Для домена, который требуется изменить, выберите пункт **Управление доменом**.</span><span class="sxs-lookup"><span data-stu-id="16561-123">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="16561-125">Выберите **Управление FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="16561-125">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom Manage Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. <span data-ttu-id="16561-127">В разделе **Add Record** (Добавление записи) в столбце **Type** (Тип) выберите **TXT** в списке.</span><span class="sxs-lookup"><span data-stu-id="16561-127">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. <span data-ttu-id="16561-129">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="16561-129">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="16561-130">**Имя**</span><span class="sxs-lookup"><span data-stu-id="16561-130">**Name**</span></span>|<span data-ttu-id="16561-131">**Тип**</span><span class="sxs-lookup"><span data-stu-id="16561-131">**Type**</span></span>|<span data-ttu-id="16561-132">**TTL**</span><span class="sxs-lookup"><span data-stu-id="16561-132">**TTL**</span></span>|<span data-ttu-id="16561-133">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="16561-133">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="16561-134">(Оставьте пустым)</span><span class="sxs-lookup"><span data-stu-id="16561-134">(leave blank)</span></span>  <br/> |<span data-ttu-id="16561-135">TXT</span><span class="sxs-lookup"><span data-stu-id="16561-135">TXT</span></span>  <br/> |<span data-ttu-id="16561-136">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="16561-136">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="16561-137">MS = Мскскскскскскскскс</span><span class="sxs-lookup"><span data-stu-id="16561-137">MS=msXXXXXXXX</span></span>  <br/> <span data-ttu-id="16561-p106">**Примечание.** Это пример. Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.           [Где это находится?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="16561-p106">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![Freenom TXT values for verification](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. <span data-ttu-id="16561-142">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="16561-142">Select **Save Changes**.</span></span>
    
    ![Freenom TXT record Save Changes](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. <span data-ttu-id="16561-144">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="16561-144">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="16561-145">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Office 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="16561-145">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="16561-146">Если Office 365 обнаружит правильную запись TXT, это значит, что домен проверен.</span><span class="sxs-lookup"><span data-stu-id="16561-146">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="16561-147">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="16561-147">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="16561-148">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="16561-148">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="16561-149">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="16561-149">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="16561-150">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="16561-150">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="16561-p107">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="16561-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="16561-154">Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="16561-154">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="16561-155"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="16561-155"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="16561-156">Чтобы приступить к работе, откройте страницу со своими доменами в Freenom с помощью [этой ссылки](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="16561-156">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="16561-157">Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="16561-157">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="16561-159">Выберите **службы**, а затем выберите пункт **Мои домены**.</span><span class="sxs-lookup"><span data-stu-id="16561-159">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="16561-161">Для домена, который требуется изменить, выберите пункт **Управление доменом**.</span><span class="sxs-lookup"><span data-stu-id="16561-161">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="16561-163">Задайте для домена имя сервера Freenom по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="16561-163">Set the name serves for your domain to the default Freenom name servers.</span></span> <span data-ttu-id="16561-164">Выберите **средства управления**, а затем выберите **серверов доменных имен**.</span><span class="sxs-lookup"><span data-stu-id="16561-164">Select **Management Tools**, and then select **Nameservers**.</span></span>
    
    ![Freenom Nameservers setting](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. <span data-ttu-id="16561-166">Убедитесь, что установлен флажок **использовать серверов доменных имен по умолчанию** , и нажмите кнопку **изменить серверов доменных имен**.</span><span class="sxs-lookup"><span data-stu-id="16561-166">Make sure **Use default nameservers** is selected, and then select **Change Nameservers**.</span></span>
    
    ![Freenom Change Nameservers](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. <span data-ttu-id="16561-168">Выберите **Управление FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="16561-168">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom выбор управления Freenom DNS](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. <span data-ttu-id="16561-170">В разделе **Add Record** (Добавление записи) в столбце **Type** (Тип) выберите **MX** в списке.</span><span class="sxs-lookup"><span data-stu-id="16561-170">Under **Add Record**, in the **Type** column, choose **MX** from the menu.</span></span> 
    
    ![Freenom Add Record type MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. <span data-ttu-id="16561-172">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="16561-172">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="16561-173">**Имя**</span><span class="sxs-lookup"><span data-stu-id="16561-173">**Name**</span></span>|<span data-ttu-id="16561-174">**Тип**</span><span class="sxs-lookup"><span data-stu-id="16561-174">**Type**</span></span>|<span data-ttu-id="16561-175">**TTL**</span><span class="sxs-lookup"><span data-stu-id="16561-175">**TTL**</span></span>|<span data-ttu-id="16561-176">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="16561-176">**Target**</span></span>|<span data-ttu-id="16561-177">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="16561-177">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="16561-178">(оставьте пустым)</span><span class="sxs-lookup"><span data-stu-id="16561-178">(leave blank)</span></span>  <br/> |<span data-ttu-id="16561-179">MX (почтовый обменник)</span><span class="sxs-lookup"><span data-stu-id="16561-179">MX (Mail Exchanger)</span></span>  <br/> |<span data-ttu-id="16561-180">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="16561-180">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="16561-181">\<Domain — key\>. mail.Protection.Outlook.com</span><span class="sxs-lookup"><span data-stu-id="16561-181">\<domain-key\>.mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="16561-182">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Office 365.</span><span class="sxs-lookup"><span data-stu-id="16561-182">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="16561-183">Где это находится?</span><span class="sxs-lookup"><span data-stu-id="16561-183">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="16561-184">10 </span><span class="sxs-lookup"><span data-stu-id="16561-184">10</span></span>  <br/> <span data-ttu-id="16561-185">Дополнительные сведения о приоритете см. в статье [What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9).   </span><span class="sxs-lookup"><span data-stu-id="16561-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9)</span></span> <br/> |
   
   ![Freenom MX record](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. <span data-ttu-id="16561-187">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="16561-187">Select **Save Changes**.</span></span>
    
    ![Freenom MX record Save Changes](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. <span data-ttu-id="16561-189">Если существуют какие-либо другие записи MX, удалите их все.</span><span class="sxs-lookup"><span data-stu-id="16561-189">If there are any other MX records, delete them all.</span></span> <span data-ttu-id="16561-190">Для каждой записи нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="16561-190">For each record, select **Delete**.</span></span> <span data-ttu-id="16561-191">Когда **вы действительно хотите удалить эту запись?** откроется сообщение, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="16561-191">When the message **Do you really want to remove this entry?** appears, select **OK**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="16561-192">Добавление записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="16561-192">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="16561-193"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="16561-193"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="16561-194">Чтобы приступить к работе, откройте страницу со своими доменами в Freenom с помощью [этой ссылки](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="16561-194">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="16561-195">Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="16561-195">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="16561-197">Выберите **службы**, а затем выберите пункт **Мои домены**.</span><span class="sxs-lookup"><span data-stu-id="16561-197">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="16561-199">Для домена, который требуется изменить, выберите пункт **Управление доменом**.</span><span class="sxs-lookup"><span data-stu-id="16561-199">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="16561-201">Выберите **Управление FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="16561-201">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom выбор управления Freenom DNS](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. <span data-ttu-id="16561-203">В разделе **Add Record** (Добавление записи) в столбце **Type** (Тип) выберите **CNAME** в списке.</span><span class="sxs-lookup"><span data-stu-id="16561-203">Under **Add Record**, in the **Type** column, choose **CNAME** from the menu.</span></span> 
    
    ![Freenom Add Record type CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. <span data-ttu-id="16561-p113">Создайте первую запись CNAME. В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="16561-p113">Create the first CNAME record. In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="16561-207">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="16561-207">**Name**</span></span>|<span data-ttu-id="16561-208">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="16561-208">**Record type**</span></span>|<span data-ttu-id="16561-209">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="16561-209">**TTL**</span></span>|<span data-ttu-id="16561-210">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="16561-210">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="16561-211">autodiscover</span><span class="sxs-lookup"><span data-stu-id="16561-211">autodiscover</span></span>  <br/> |<span data-ttu-id="16561-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="16561-212">CNAME</span></span>  <br/> |<span data-ttu-id="16561-213">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="16561-213">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="16561-214">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="16561-214">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="16561-215">sip</span><span class="sxs-lookup"><span data-stu-id="16561-215">sip</span></span>  <br/> |<span data-ttu-id="16561-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="16561-216">CNAME</span></span>  <br/> |<span data-ttu-id="16561-217">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="16561-217">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="16561-218">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="16561-218">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="16561-219">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="16561-219">lyncdiscover</span></span>  <br/> |<span data-ttu-id="16561-220">CNAME</span><span class="sxs-lookup"><span data-stu-id="16561-220">CNAME</span></span>  <br/> |<span data-ttu-id="16561-221">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="16561-221">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="16561-222">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="16561-222">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="16561-223">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="16561-223">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="16561-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="16561-224">CNAME</span></span>  <br/> |<span data-ttu-id="16561-225">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="16561-225">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="16561-226">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="16561-226">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="16561-227">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="16561-227">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="16561-228">CNAME</span><span class="sxs-lookup"><span data-stu-id="16561-228">CNAME</span></span>  <br/> |<span data-ttu-id="16561-229">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="16561-229">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="16561-230">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="16561-230">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Freenom CNAME values](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. <span data-ttu-id="16561-232">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="16561-232">Select **Save Changes**.</span></span>
    
    ![Freenom CNAME Save Changes](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. <span data-ttu-id="16561-234">Повторив эти действия, создайте пять других записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="16561-234">Repeat the previous steps to create the other five CNAME records.</span></span> 
    
    <span data-ttu-id="16561-235">Создайте пять других записей CNAME, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="16561-235">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="16561-236">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="16561-236">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="16561-237"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="16561-237"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="16561-238">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="16561-238">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="16561-239">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="16561-239">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="16561-240">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="16561-240">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="16561-241">Вместо этого добавьте необходимые значения Office 365 в текущую запись. Таким образом, в *одной* записи SPF будут указаны оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="16561-241">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

1. <span data-ttu-id="16561-242">Чтобы приступить к работе, откройте страницу со своими доменами в Freenom с помощью [этой ссылки](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="16561-242">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="16561-243">Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="16561-243">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="16561-245">Выберите **службы**, а затем выберите пункт **Мои домены**.</span><span class="sxs-lookup"><span data-stu-id="16561-245">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="16561-247">Для домена, который требуется изменить, выберите пункт **Управление доменом**.</span><span class="sxs-lookup"><span data-stu-id="16561-247">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="16561-249">Выберите **Управление FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="16561-249">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom выбор управления Freenom DNS](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. <span data-ttu-id="16561-251">В разделе **Add Record** (Добавление записи) в столбце **Type** (Тип) выберите **TXT** в списке.</span><span class="sxs-lookup"><span data-stu-id="16561-251">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. <span data-ttu-id="16561-253">В поля для новой записи введите (или скопируйте и вставьте) указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="16561-253">In the boxes for the new record, type or copy and paste the following values.</span></span> 
    
    |<span data-ttu-id="16561-254">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="16561-254">**Name**</span></span>|<span data-ttu-id="16561-255">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="16561-255">**Record type**</span></span>|<span data-ttu-id="16561-256">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="16561-256">**TTL**</span></span>|<span data-ttu-id="16561-257">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="16561-257">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="16561-258">(оставьте пустым)</span><span class="sxs-lookup"><span data-stu-id="16561-258">(leave blank)</span></span>  <br/> |<span data-ttu-id="16561-259">TXT</span><span class="sxs-lookup"><span data-stu-id="16561-259">TXT</span></span>  <br/> |<span data-ttu-id="16561-260">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="16561-260">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="16561-261">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="16561-261">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="16561-262">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="16561-262">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Freenom TXT values for SPF](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. <span data-ttu-id="16561-264">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="16561-264">Select **Save Changes**.</span></span>
    
    ![Freenom TXT record for SPF Save Changes](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

