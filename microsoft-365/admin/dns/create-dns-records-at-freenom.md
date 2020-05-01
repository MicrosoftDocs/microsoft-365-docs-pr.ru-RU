---
title: Создание записей DNS на сайте Freenom для Майкрософт
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
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу Freenom для Майкрософт.
ms.openlocfilehash: a7ad45d3d785478966df5120567836200de316da
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939231"
---
# <a name="create-dns-records-at-freenom-for-microsoft"></a><span data-ttu-id="b6efe-103">Создание записей DNS на сайте Freenom для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b6efe-103">Create DNS records at Freenom for Microsoft</span></span>

<span data-ttu-id="b6efe-104">Если вы не нашли нужную информацию, см. статью [Вопросы и ответы о доменах](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="b6efe-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="b6efe-105">На веб-сайте Freenom не поддерживаются записи SRV, поэтому некоторые функции Skype для бизнеса Online и Outlook Web App не будут работать.</span><span class="sxs-lookup"><span data-stu-id="b6efe-105">The Freenom website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="b6efe-106">Независимо от того, какой план Майкрософт вы используете, существуют существенные ограничения для служб и может потребоваться переключиться на другого поставщика услуг хостинга DNS.</span><span class="sxs-lookup"><span data-stu-id="b6efe-106">No matter which Microsoft plan you use, there are significant service limitations, and you may want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="b6efe-107">Если несмотря на ограничения службы, вы решили управлять собственными записями Microsoft DNS на сайте Freenom, выполнив действия, описанные в этой статье, чтобы проверить домен и настроить записи DNS для электронной почты и других служб.</span><span class="sxs-lookup"><span data-stu-id="b6efe-107">If despite the service limitations, you choose to manage your own Microsoft DNS records at Freenom, follow the steps in this article to verify your domain and set up DNS records for email and other services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="b6efe-p102">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b6efe-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b6efe-111">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="b6efe-111">Add a TXT record for verification</span></span>
<span data-ttu-id="b6efe-112"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="b6efe-112"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="b6efe-p103">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="b6efe-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b6efe-p104">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="b6efe-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="b6efe-117">Чтобы приступить к работе, откройте страницу со своими доменами в Freenom с помощью [этой ссылки](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="b6efe-117">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="b6efe-118">Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="b6efe-118">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="b6efe-120">Выберите **службы**, а затем выберите пункт **Мои домены**.</span><span class="sxs-lookup"><span data-stu-id="b6efe-120">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="b6efe-122">Для домена, который требуется изменить, выберите пункт **Управление доменом**.</span><span class="sxs-lookup"><span data-stu-id="b6efe-122">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="b6efe-124">Выберите **Управление FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="b6efe-124">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom Manage Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. <span data-ttu-id="b6efe-126">В разделе **Add Record** (Добавление записи) в столбце **Type** (Тип) выберите **TXT** в списке.</span><span class="sxs-lookup"><span data-stu-id="b6efe-126">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. <span data-ttu-id="b6efe-128">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="b6efe-128">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="b6efe-129">**Имя**</span><span class="sxs-lookup"><span data-stu-id="b6efe-129">**Name**</span></span>|<span data-ttu-id="b6efe-130">**Тип**</span><span class="sxs-lookup"><span data-stu-id="b6efe-130">**Type**</span></span>|<span data-ttu-id="b6efe-131">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b6efe-131">**TTL**</span></span>|<span data-ttu-id="b6efe-132">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="b6efe-132">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b6efe-133">(Оставьте пустым)</span><span class="sxs-lookup"><span data-stu-id="b6efe-133">(leave blank)</span></span>  <br/> |<span data-ttu-id="b6efe-134">TXT</span><span class="sxs-lookup"><span data-stu-id="b6efe-134">TXT</span></span>  <br/> |<span data-ttu-id="b6efe-135">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="b6efe-135">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="b6efe-136">MS = Мскскскскскскскскс</span><span class="sxs-lookup"><span data-stu-id="b6efe-136">MS=msXXXXXXXX</span></span>  <br/> <span data-ttu-id="b6efe-137">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="b6efe-137">**Note:** This is an example.</span></span> <span data-ttu-id="b6efe-138">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="b6efe-138">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="b6efe-139">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="b6efe-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Freenom TXT values for verification](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. <span data-ttu-id="b6efe-141">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="b6efe-141">Select **Save Changes**.</span></span>
    
    ![Freenom TXT record Save Changes](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. <span data-ttu-id="b6efe-143">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="b6efe-143">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b6efe-144">Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.</span><span class="sxs-lookup"><span data-stu-id="b6efe-144">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="b6efe-145">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="b6efe-145">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b6efe-146">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="b6efe-146">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="b6efe-147">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="b6efe-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="b6efe-148">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="b6efe-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="b6efe-149">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="b6efe-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="b6efe-p107">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b6efe-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="b6efe-153">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b6efe-153">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="b6efe-154"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="b6efe-154"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="b6efe-155">Чтобы приступить к работе, откройте страницу со своими доменами в Freenom с помощью [этой ссылки](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="b6efe-155">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="b6efe-156">Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="b6efe-156">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="b6efe-158">Выберите **службы**, а затем выберите пункт **Мои домены**.</span><span class="sxs-lookup"><span data-stu-id="b6efe-158">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="b6efe-160">Для домена, который требуется изменить, выберите пункт **Управление доменом**.</span><span class="sxs-lookup"><span data-stu-id="b6efe-160">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="b6efe-162">Задайте для домена имя сервера Freenom по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b6efe-162">Set the name serves for your domain to the default Freenom name servers.</span></span> <span data-ttu-id="b6efe-163">Выберите **средства управления**, а затем выберите **серверов доменных имен**.</span><span class="sxs-lookup"><span data-stu-id="b6efe-163">Select **Management Tools**, and then select **Nameservers**.</span></span>
    
    ![Freenom Nameservers setting](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. <span data-ttu-id="b6efe-165">Убедитесь, что установлен флажок **использовать серверов доменных имен по умолчанию** , и нажмите кнопку **изменить серверов доменных имен**.</span><span class="sxs-lookup"><span data-stu-id="b6efe-165">Make sure **Use default nameservers** is selected, and then select **Change Nameservers**.</span></span>
    
    ![Freenom Change Nameservers](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. <span data-ttu-id="b6efe-167">Выберите **Управление FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="b6efe-167">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom выбор управления Freenom DNS](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. <span data-ttu-id="b6efe-169">В разделе **Add Record** (Добавление записи) в столбце **Type** (Тип) выберите **MX** в списке.</span><span class="sxs-lookup"><span data-stu-id="b6efe-169">Under **Add Record**, in the **Type** column, choose **MX** from the menu.</span></span> 
    
    ![Freenom Add Record type MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. <span data-ttu-id="b6efe-171">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="b6efe-171">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="b6efe-172">**Имя**</span><span class="sxs-lookup"><span data-stu-id="b6efe-172">**Name**</span></span>|<span data-ttu-id="b6efe-173">**Тип**</span><span class="sxs-lookup"><span data-stu-id="b6efe-173">**Type**</span></span>|<span data-ttu-id="b6efe-174">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b6efe-174">**TTL**</span></span>|<span data-ttu-id="b6efe-175">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="b6efe-175">**Target**</span></span>|<span data-ttu-id="b6efe-176">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="b6efe-176">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b6efe-177">(оставьте пустым)</span><span class="sxs-lookup"><span data-stu-id="b6efe-177">(leave blank)</span></span>  <br/> |<span data-ttu-id="b6efe-178">MX (почтовый обменник)</span><span class="sxs-lookup"><span data-stu-id="b6efe-178">MX (Mail Exchanger)</span></span>  <br/> |<span data-ttu-id="b6efe-179">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="b6efe-179">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="b6efe-180">\<Domain — key\>. mail.Protection.Outlook.com</span><span class="sxs-lookup"><span data-stu-id="b6efe-180">\<domain-key\>.mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="b6efe-181">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b6efe-181">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="b6efe-182">Где это находится?</span><span class="sxs-lookup"><span data-stu-id="b6efe-182">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="b6efe-183">10 </span><span class="sxs-lookup"><span data-stu-id="b6efe-183">10</span></span>  <br/> <span data-ttu-id="b6efe-184">Дополнительные сведения о приоритете см. в статье [What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9).   </span><span class="sxs-lookup"><span data-stu-id="b6efe-184">For more information about priority, see [What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9)</span></span> <br/> |
   
   ![Freenom MX record](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. <span data-ttu-id="b6efe-186">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="b6efe-186">Select **Save Changes**.</span></span>
    
    ![Freenom MX record Save Changes](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. <span data-ttu-id="b6efe-188">Если существуют какие-либо другие записи MX, удалите их все.</span><span class="sxs-lookup"><span data-stu-id="b6efe-188">If there are any other MX records, delete them all.</span></span> <span data-ttu-id="b6efe-189">Для каждой записи нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="b6efe-189">For each record, select **Delete**.</span></span> <span data-ttu-id="b6efe-190">Когда **вы действительно хотите удалить эту запись?** откроется сообщение, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b6efe-190">When the message **Do you really want to remove this entry?** appears, select **OK**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="b6efe-191">Добавление записей CNAME, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b6efe-191">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="b6efe-192"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="b6efe-192"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="b6efe-193">Чтобы приступить к работе, откройте страницу со своими доменами в Freenom с помощью [этой ссылки](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="b6efe-193">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="b6efe-194">Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="b6efe-194">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="b6efe-196">Выберите **службы**, а затем выберите пункт **Мои домены**.</span><span class="sxs-lookup"><span data-stu-id="b6efe-196">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="b6efe-198">Для домена, который требуется изменить, выберите пункт **Управление доменом**.</span><span class="sxs-lookup"><span data-stu-id="b6efe-198">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="b6efe-200">Выберите **Управление FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="b6efe-200">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom выбор управления Freenom DNS](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. <span data-ttu-id="b6efe-202">В разделе **Add Record** (Добавление записи) в столбце **Type** (Тип) выберите **CNAME** в списке.</span><span class="sxs-lookup"><span data-stu-id="b6efe-202">Under **Add Record**, in the **Type** column, choose **CNAME** from the menu.</span></span> 
    
    ![Freenom Add Record type CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. <span data-ttu-id="b6efe-p113">Создайте первую запись CNAME. В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="b6efe-p113">Create the first CNAME record. In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="b6efe-206">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="b6efe-206">**Name**</span></span>|<span data-ttu-id="b6efe-207">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="b6efe-207">**Record type**</span></span>|<span data-ttu-id="b6efe-208">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="b6efe-208">**TTL**</span></span>|<span data-ttu-id="b6efe-209">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="b6efe-209">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b6efe-210">autodiscover</span><span class="sxs-lookup"><span data-stu-id="b6efe-210">autodiscover</span></span>  <br/> |<span data-ttu-id="b6efe-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="b6efe-211">CNAME</span></span>  <br/> |<span data-ttu-id="b6efe-212">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="b6efe-212">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="b6efe-213">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b6efe-213">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="b6efe-214">sip</span><span class="sxs-lookup"><span data-stu-id="b6efe-214">sip</span></span>  <br/> |<span data-ttu-id="b6efe-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="b6efe-215">CNAME</span></span>  <br/> |<span data-ttu-id="b6efe-216">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="b6efe-216">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="b6efe-217">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b6efe-217">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="b6efe-218">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b6efe-218">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b6efe-219">CNAME</span><span class="sxs-lookup"><span data-stu-id="b6efe-219">CNAME</span></span>  <br/> |<span data-ttu-id="b6efe-220">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="b6efe-220">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="b6efe-221">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b6efe-221">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="b6efe-222">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b6efe-222">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b6efe-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="b6efe-223">CNAME</span></span>  <br/> |<span data-ttu-id="b6efe-224">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="b6efe-224">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="b6efe-225">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="b6efe-225">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="b6efe-226">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b6efe-226">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b6efe-227">CNAME</span><span class="sxs-lookup"><span data-stu-id="b6efe-227">CNAME</span></span>  <br/> |<span data-ttu-id="b6efe-228">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="b6efe-228">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="b6efe-229">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b6efe-229">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Freenom CNAME values](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. <span data-ttu-id="b6efe-231">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="b6efe-231">Select **Save Changes**.</span></span>
    
    ![Freenom CNAME Save Changes](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. <span data-ttu-id="b6efe-233">Повторив эти действия, создайте пять других записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="b6efe-233">Repeat the previous steps to create the other five CNAME records.</span></span> 
    
    <span data-ttu-id="b6efe-234">Создайте пять других записей CNAME, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="b6efe-234">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b6efe-235">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="b6efe-235">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="b6efe-236"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="b6efe-236"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6efe-237">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="b6efe-237">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="b6efe-238">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="b6efe-238">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="b6efe-239">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b6efe-239">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="b6efe-240">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="b6efe-240">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

1. <span data-ttu-id="b6efe-241">Чтобы приступить к работе, откройте страницу со своими доменами в Freenom с помощью [этой ссылки](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="b6efe-241">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="b6efe-242">Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="b6efe-242">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="b6efe-244">Выберите **службы**, а затем выберите пункт **Мои домены**.</span><span class="sxs-lookup"><span data-stu-id="b6efe-244">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="b6efe-246">Для домена, который требуется изменить, выберите пункт **Управление доменом**.</span><span class="sxs-lookup"><span data-stu-id="b6efe-246">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="b6efe-248">Выберите **Управление FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="b6efe-248">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom выбор управления Freenom DNS](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. <span data-ttu-id="b6efe-250">В разделе **Add Record** (Добавление записи) в столбце **Type** (Тип) выберите **TXT** в списке.</span><span class="sxs-lookup"><span data-stu-id="b6efe-250">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. <span data-ttu-id="b6efe-252">В поля для новой записи введите (или скопируйте и вставьте) указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="b6efe-252">In the boxes for the new record, type or copy and paste the following values.</span></span> 
    
    |<span data-ttu-id="b6efe-253">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="b6efe-253">**Name**</span></span>|<span data-ttu-id="b6efe-254">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="b6efe-254">**Record type**</span></span>|<span data-ttu-id="b6efe-255">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="b6efe-255">**TTL**</span></span>|<span data-ttu-id="b6efe-256">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="b6efe-256">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b6efe-257">(оставьте пустым)</span><span class="sxs-lookup"><span data-stu-id="b6efe-257">(leave blank)</span></span>  <br/> |<span data-ttu-id="b6efe-258">TXT</span><span class="sxs-lookup"><span data-stu-id="b6efe-258">TXT</span></span>  <br/> |<span data-ttu-id="b6efe-259">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="b6efe-259">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="b6efe-260">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="b6efe-260">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="b6efe-261">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="b6efe-261">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Freenom TXT values for SPF](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. <span data-ttu-id="b6efe-263">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="b6efe-263">Select **Save Changes**.</span></span>
    
    ![Freenom TXT record for SPF Save Changes](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

