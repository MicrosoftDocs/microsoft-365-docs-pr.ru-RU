---
title: Создание записей DNS при наведении курсора на Майкрософт
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
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб при наведении курсора на Майкрософт.
ms.openlocfilehash: 4779b8f6fadcd4b134d3954d2c6c133da40c19e6
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048991"
---
# <a name="create-dns-records-at-hover-for-microsoft"></a><span data-ttu-id="2af0b-103">Создание записей DNS при наведении курсора на Майкрософт</span><span class="sxs-lookup"><span data-stu-id="2af0b-103">Create DNS records at Hover for Microsoft</span></span>

 <span data-ttu-id="2af0b-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="2af0b-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="2af0b-105">Если ваш поставщик услуг размещения DNS  Hover, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="2af0b-105">If Hover is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
     
<span data-ttu-id="2af0b-106">Когда вы добавите эти записи при наведении указателя, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2af0b-106">After you add these records at Hover, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="2af0b-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2af0b-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="2af0b-110">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="2af0b-110">Add a TXT record for verification</span></span>
<span data-ttu-id="2af0b-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="2af0b-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="2af0b-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="2af0b-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2af0b-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="2af0b-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="2af0b-116">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="2af0b-116">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="2af0b-p104">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Hover по [этой ссылке](https://www.hover.com/domains). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="2af0b-p104">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Вход](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="2af0b-120">В разделе **Управление доменами**выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="2af0b-120">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Выбор домена](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="2af0b-122">Перейдите на вкладку **DNS** .</span><span class="sxs-lookup"><span data-stu-id="2af0b-122">Select the **DNS** tab.</span></span> 
    
    ![Выбор вкладки DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="2af0b-124">Нажмите кнопку **Добавить новый**.</span><span class="sxs-lookup"><span data-stu-id="2af0b-124">Select **Add New**.</span></span>
    
    ![Нажмите кнопку Добавить новый](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="2af0b-126">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="2af0b-126">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="2af0b-127">Hostname (Имя узла)</span><span class="sxs-lookup"><span data-stu-id="2af0b-127">Hostname</span></span>  <br/> |<span data-ttu-id="2af0b-128">Record Type</span><span class="sxs-lookup"><span data-stu-id="2af0b-128">Record Type</span></span>  <br/> |<span data-ttu-id="2af0b-129">Value (Значение)</span><span class="sxs-lookup"><span data-stu-id="2af0b-129">Value</span></span>  <br/> |
    |@  <br/> |<span data-ttu-id="2af0b-130">TXT</span><span class="sxs-lookup"><span data-stu-id="2af0b-130">TXT</span></span>  <br/> |<span data-ttu-id="2af0b-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="2af0b-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="2af0b-132">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="2af0b-132">**Note:** This is an example.</span></span> <span data-ttu-id="2af0b-133">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="2af0b-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="2af0b-134">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="2af0b-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Введите (или скопируйте и вставьте) значения DNS](../../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. <span data-ttu-id="2af0b-136">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2af0b-136">Select **Save**.</span></span>
    
    ![Нажмите кнопку Сохранить](../../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. <span data-ttu-id="2af0b-138">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="2af0b-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="2af0b-139">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Microsoft 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="2af0b-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="2af0b-140">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="2af0b-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="2af0b-141">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="2af0b-141">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="2af0b-142">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="2af0b-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="2af0b-143">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="2af0b-143">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="2af0b-144">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="2af0b-144">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="2af0b-p106">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2af0b-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="2af0b-148">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2af0b-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="2af0b-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="2af0b-149"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="2af0b-150">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="2af0b-150">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="2af0b-p107">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Hover по [этой ссылке](https://www.hover.com/domains). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="2af0b-p107">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Вход](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="2af0b-154">В разделе **Управление доменами**выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="2af0b-154">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Выбор домена](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="2af0b-156">Перейдите на вкладку **DNS** .</span><span class="sxs-lookup"><span data-stu-id="2af0b-156">Select the **DNS** tab.</span></span> 
    
    ![Выбор вкладки DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="2af0b-158">Нажмите кнопку **Добавить новый**.</span><span class="sxs-lookup"><span data-stu-id="2af0b-158">Select **Add New**.</span></span>
    
    ![Нажмите кнопку Добавить новый](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="2af0b-160">В полях для новой записи выберите значение **MX** для параметра **Record Type** (Тип записи) и введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="2af0b-160">In the boxes for the new record, select **MX** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="2af0b-161">**Hostname (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="2af0b-161">**Hostname**</span></span>|<span data-ttu-id="2af0b-162">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="2af0b-162">**Record Type**</span></span>|<span data-ttu-id="2af0b-163">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="2af0b-163">**Priority**</span></span>|<span data-ttu-id="2af0b-164">**Hostname (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="2af0b-164">**Hostname**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="2af0b-165">MX</span><span class="sxs-lookup"><span data-stu-id="2af0b-165">MX</span></span>  <br/> |<span data-ttu-id="2af0b-166">нуль</span><span class="sxs-lookup"><span data-stu-id="2af0b-166">0</span></span>  <br/> <span data-ttu-id="2af0b-167">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="2af0b-167">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="2af0b-168">*\<ключ_домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="2af0b-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="2af0b-169">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2af0b-169">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="2af0b-170">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="2af0b-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Введите (или скопируйте и вставьте) значения DNS](../../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. <span data-ttu-id="2af0b-172">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2af0b-172">Select **Save**.</span></span>
    
    ![Нажмите кнопку Сохранить](../../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. <span data-ttu-id="2af0b-174">Если есть какие-либо другие записи MX, удалите каждую из них, выполнив двухшаговую процедуру.</span><span class="sxs-lookup"><span data-stu-id="2af0b-174">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="2af0b-175">Сначала маусинг запись, которую нужно удалить, и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="2af0b-175">First, mousing over a record that you want to remove, select **Delete**.</span></span>
    
    ![Наведите указатель мыши на пункт и выберите Delete (удалить)](../../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    <span data-ttu-id="2af0b-177">Во вторых, нажмите **кнопку Да** , чтобы подтвердить каждое удаление.</span><span class="sxs-lookup"><span data-stu-id="2af0b-177">Second, select **Yes** to confirm each deletion.</span></span> 
    
    ![Выберите Да, чтобы подтвердить удаление](../../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    <span data-ttu-id="2af0b-179">Повторяйте эту процедуру, пока не будут удалены все записи MX, кроме той, которую вы добавили на предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="2af0b-179">Repeat this process until you have deleted all MX records except for the one that you added earlier in this procedure.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="2af0b-180">Добавление записей CNAME, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="2af0b-180">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="2af0b-181"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="2af0b-181"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="2af0b-182">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="2af0b-182">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="2af0b-p109">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Hover по [этой ссылке](https://www.hover.com/domains). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="2af0b-p109">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Вход](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="2af0b-186">В разделе **Управление доменами**выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="2af0b-186">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Выбор домена](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="2af0b-188">Перейдите на вкладку **DNS** .</span><span class="sxs-lookup"><span data-stu-id="2af0b-188">Select the **DNS** tab.</span></span> 
    
    ![Выбор вкладки DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="2af0b-190">Добавьте первую из шести записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="2af0b-190">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="2af0b-191">Нажмите кнопку **Добавить новый**.</span><span class="sxs-lookup"><span data-stu-id="2af0b-191">Select **Add New**.</span></span>
    
    ![Нажмите кнопку Добавить новый](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="2af0b-193">В пустых полях для новой записи выберите значение **CNAME** для параметра **Record Type** (Тип записи) и введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="2af0b-193">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="2af0b-194">**Hostname (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="2af0b-194">**Hostname**</span></span>|<span data-ttu-id="2af0b-195">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="2af0b-195">**Record Type**</span></span>|<span data-ttu-id="2af0b-196">**Target Host (Целевой узел)**</span><span class="sxs-lookup"><span data-stu-id="2af0b-196">**Target Host**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="2af0b-197">autodiscover</span><span class="sxs-lookup"><span data-stu-id="2af0b-197">autodiscover</span></span>  <br/> |<span data-ttu-id="2af0b-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="2af0b-198">CNAME</span></span>  <br/> |<span data-ttu-id="2af0b-199">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="2af0b-199">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="2af0b-200">sip</span><span class="sxs-lookup"><span data-stu-id="2af0b-200">sip</span></span>  <br/> |<span data-ttu-id="2af0b-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="2af0b-201">CNAME</span></span>  <br/> |<span data-ttu-id="2af0b-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2af0b-202">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="2af0b-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="2af0b-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="2af0b-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="2af0b-204">CNAME</span></span>  <br/> |<span data-ttu-id="2af0b-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2af0b-205">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="2af0b-206">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="2af0b-206">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="2af0b-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="2af0b-207">CNAME</span></span>  <br/> |<span data-ttu-id="2af0b-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="2af0b-208">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="2af0b-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="2af0b-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="2af0b-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="2af0b-210">CNAME</span></span>  <br/> |<span data-ttu-id="2af0b-211">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2af0b-211">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Введите (или скопируйте и вставьте) значения DNS](../../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. <span data-ttu-id="2af0b-213">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2af0b-213">Select **Save**.</span></span>
    
    ![Нажмите кнопку Сохранить](../../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. <span data-ttu-id="2af0b-215">Повторяйте три описанных выше шага, используя значения из пяти других строк таблицы, чтобы добавить остальные записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="2af0b-215">Using the preceding three steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="2af0b-216">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="2af0b-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="2af0b-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="2af0b-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="2af0b-218">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="2af0b-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="2af0b-219">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="2af0b-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="2af0b-220">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2af0b-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="2af0b-221">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="2af0b-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="2af0b-222">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="2af0b-222">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="2af0b-p111">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Hover по [этой ссылке](https://www.hover.com/domains). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="2af0b-p111">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Вход](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="2af0b-226">В разделе **Управление доменами**выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="2af0b-226">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Выбор домена](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="2af0b-228">Перейдите на вкладку **DNS** .</span><span class="sxs-lookup"><span data-stu-id="2af0b-228">Select the **DNS** tab.</span></span> 
    
    ![Выбор вкладки DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="2af0b-230">Нажмите кнопку **Добавить новый**.</span><span class="sxs-lookup"><span data-stu-id="2af0b-230">Select **Add New**.</span></span>
    
    ![Нажмите кнопку Добавить новый](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="2af0b-232">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="2af0b-232">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="2af0b-233">**Hostname (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="2af0b-233">**Hostname**</span></span>|<span data-ttu-id="2af0b-234">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="2af0b-234">**Record Type**</span></span>|<span data-ttu-id="2af0b-235">**Value (Значение)**</span><span class="sxs-lookup"><span data-stu-id="2af0b-235">**Value**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="2af0b-236">TXT</span><span class="sxs-lookup"><span data-stu-id="2af0b-236">TXT</span></span>  <br/> |<span data-ttu-id="2af0b-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="2af0b-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="2af0b-238">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="2af0b-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Введите (или скопируйте и вставьте) значения DNS](../../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. <span data-ttu-id="2af0b-240">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2af0b-240">Select **Save**.</span></span>
    
    ![Нажмите кнопку Сохранить](../../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="2af0b-242">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="2af0b-242">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="2af0b-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="2af0b-243"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="2af0b-244">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="2af0b-244">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="2af0b-p112">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Hover по [этой ссылке](https://www.hover.com/domains). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="2af0b-p112">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Вход](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="2af0b-248">В разделе **Управление доменами**выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="2af0b-248">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Выбор домена](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="2af0b-250">Перейдите на вкладку **DNS** .</span><span class="sxs-lookup"><span data-stu-id="2af0b-250">Select the **DNS** tab.</span></span> 
    
    ![Выбор вкладки DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="2af0b-252">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="2af0b-252">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="2af0b-253">Нажмите кнопку **Добавить новый**.</span><span class="sxs-lookup"><span data-stu-id="2af0b-253">Select **Add New**.</span></span>
    
    ![Нажмите кнопку Добавить новый](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="2af0b-255">В пустых полях для новой записи выберите значение **SRV** для параметра **Record Type** (Тип записи) и введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="2af0b-255">In the empty boxes for the new record, select **SRV** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="2af0b-256">**Hostname (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="2af0b-256">**Hostname**</span></span>|<span data-ttu-id="2af0b-257">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="2af0b-257">**Record Type**</span></span>|<span data-ttu-id="2af0b-258">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="2af0b-258">**Priority**</span></span>|<span data-ttu-id="2af0b-259">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="2af0b-259">**Weight**</span></span>|<span data-ttu-id="2af0b-260">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="2af0b-260">**Port**</span></span>|<span data-ttu-id="2af0b-261">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="2af0b-261">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="2af0b-262">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="2af0b-262">_sip._tls</span></span>  <br/> |<span data-ttu-id="2af0b-263">SRV</span><span class="sxs-lookup"><span data-stu-id="2af0b-263">SRV</span></span>  <br/> |<span data-ttu-id="2af0b-264">100</span><span class="sxs-lookup"><span data-stu-id="2af0b-264">100</span></span>  <br/> |<span data-ttu-id="2af0b-265">1,1</span><span class="sxs-lookup"><span data-stu-id="2af0b-265">1</span></span>  <br/> |<span data-ttu-id="2af0b-266">443</span><span class="sxs-lookup"><span data-stu-id="2af0b-266">443</span></span>  <br/> |<span data-ttu-id="2af0b-267">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2af0b-267">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="2af0b-268">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="2af0b-268">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="2af0b-269">SRV</span><span class="sxs-lookup"><span data-stu-id="2af0b-269">SRV</span></span>  <br/> |<span data-ttu-id="2af0b-270">100</span><span class="sxs-lookup"><span data-stu-id="2af0b-270">100</span></span>  <br/> |<span data-ttu-id="2af0b-271">1,1</span><span class="sxs-lookup"><span data-stu-id="2af0b-271">1</span></span>  <br/> |<span data-ttu-id="2af0b-272">5061</span><span class="sxs-lookup"><span data-stu-id="2af0b-272">5061</span></span>  <br/> |<span data-ttu-id="2af0b-273">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2af0b-273">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Введите (или скопируйте и вставьте) значения DNS](../../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. <span data-ttu-id="2af0b-275">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2af0b-275">Select **Save**.</span></span>
    
    ![Нажмите кнопку Сохранить](../../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. <span data-ttu-id="2af0b-277">Повторите три описанных выше шага, используя значения из второй строки таблицы, чтобы добавить еще одну запись SRV.</span><span class="sxs-lookup"><span data-stu-id="2af0b-277">Using the preceding three steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2af0b-p113">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2af0b-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
