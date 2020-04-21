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
ms.openlocfilehash: 328020dffe5d6549f7a0418a01d99b18ef9c5035
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629519"
---
# <a name="create-dns-records-at-hover-for-microsoft"></a><span data-ttu-id="2cc88-103">Создание записей DNS при наведении курсора на Майкрософт</span><span class="sxs-lookup"><span data-stu-id="2cc88-103">Create DNS records at Hover for Microsoft</span></span>

 <span data-ttu-id="2cc88-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="2cc88-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="2cc88-105">Если ваш поставщик услуг размещения DNS  Hover, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="2cc88-105">If Hover is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
     
<span data-ttu-id="2cc88-106">Когда вы добавите эти записи при наведении указателя, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2cc88-106">After you add these records at Hover, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="2cc88-107">Чтобы узнать о размещении и DNS для веб-сайтов с помощью Microsoft, ознакомьтесь со статьей [использование общедоступного веб-сайта с корпорацией Майкрософт](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="2cc88-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="2cc88-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2cc88-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="2cc88-111">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="2cc88-111">Add a TXT record for verification</span></span>
<span data-ttu-id="2cc88-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="2cc88-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="2cc88-113">Перед использованием домена с корпорацией Майкрософт необходимо убедиться, что вы являетесь его владельцем.</span><span class="sxs-lookup"><span data-stu-id="2cc88-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="2cc88-114">Вы можете войти в свою учетную запись у вас в вашем регистраторе доменных имен и создать запись DNS в Майкрософт, если вы владеете этим доменом.</span><span class="sxs-lookup"><span data-stu-id="2cc88-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2cc88-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="2cc88-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="2cc88-117">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="2cc88-117">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="2cc88-p104">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Hover по [этой ссылке](https://www.hover.com/domains). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="2cc88-p104">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Вход](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="2cc88-121">В разделе **Управление доменами**выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="2cc88-121">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Выбор домена](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="2cc88-123">Перейдите на вкладку **DNS** .</span><span class="sxs-lookup"><span data-stu-id="2cc88-123">Select the **DNS** tab.</span></span> 
    
    ![Выбор вкладки DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="2cc88-125">Нажмите кнопку **Добавить новый**.</span><span class="sxs-lookup"><span data-stu-id="2cc88-125">Select **Add New**.</span></span>
    
    ![Нажмите кнопку Добавить новый](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="2cc88-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="2cc88-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="2cc88-128">Hostname (Имя узла)</span><span class="sxs-lookup"><span data-stu-id="2cc88-128">Hostname</span></span>  <br/> |<span data-ttu-id="2cc88-129">Record Type</span><span class="sxs-lookup"><span data-stu-id="2cc88-129">Record Type</span></span>  <br/> |<span data-ttu-id="2cc88-130">Value (Значение)</span><span class="sxs-lookup"><span data-stu-id="2cc88-130">Value</span></span>  <br/> |
    |@  <br/> |<span data-ttu-id="2cc88-131">TXT</span><span class="sxs-lookup"><span data-stu-id="2cc88-131">TXT</span></span>  <br/> |<span data-ttu-id="2cc88-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="2cc88-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="2cc88-133">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="2cc88-133">**Note:** This is an example.</span></span> <span data-ttu-id="2cc88-134">Используйте указанную здесь **конечную точку или значение адреса** из таблицы.</span><span class="sxs-lookup"><span data-stu-id="2cc88-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="2cc88-135">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="2cc88-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Введите (или скопируйте и вставьте) значения DNS](../../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. <span data-ttu-id="2cc88-137">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2cc88-137">Select **Save**.</span></span>
    
    ![Нажмите кнопку Сохранить](../../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. <span data-ttu-id="2cc88-139">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="2cc88-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="2cc88-140">Теперь, когда вы добавили запись на сайт регистратора доменных имен, вернитесь в Microsoft 365 и запросите Microsoft 365, чтобы найти запись.</span><span class="sxs-lookup"><span data-stu-id="2cc88-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="2cc88-141">После того как корпорация Майкрософт обнаружит правильную запись TXT, ваш домен будет проверен.</span><span class="sxs-lookup"><span data-stu-id="2cc88-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="2cc88-142">В центре администрирования Майкрософт перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> **параметров** \> ".</span><span class="sxs-lookup"><span data-stu-id="2cc88-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="2cc88-143">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="2cc88-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="2cc88-144">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="2cc88-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="2cc88-145">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="2cc88-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="2cc88-p106">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2cc88-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="2cc88-149">Добавление записи MX для отправки электронной почты для вашего домена в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="2cc88-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="2cc88-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="2cc88-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="2cc88-151">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="2cc88-151">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="2cc88-p107">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Hover по [этой ссылке](https://www.hover.com/domains). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="2cc88-p107">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Вход](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="2cc88-155">В разделе **Управление доменами**выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="2cc88-155">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Выбор домена](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="2cc88-157">Перейдите на вкладку **DNS** .</span><span class="sxs-lookup"><span data-stu-id="2cc88-157">Select the **DNS** tab.</span></span> 
    
    ![Выбор вкладки DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="2cc88-159">Нажмите кнопку **Добавить новый**.</span><span class="sxs-lookup"><span data-stu-id="2cc88-159">Select **Add New**.</span></span>
    
    ![Нажмите кнопку Добавить новый](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="2cc88-161">В полях для новой записи выберите значение **MX** для параметра **Record Type** (Тип записи) и введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="2cc88-161">In the boxes for the new record, select **MX** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="2cc88-162">**Hostname (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="2cc88-162">**Hostname**</span></span>|<span data-ttu-id="2cc88-163">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="2cc88-163">**Record Type**</span></span>|<span data-ttu-id="2cc88-164">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="2cc88-164">**Priority**</span></span>|<span data-ttu-id="2cc88-165">**Hostname (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="2cc88-165">**Hostname**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="2cc88-166">MX</span><span class="sxs-lookup"><span data-stu-id="2cc88-166">MX</span></span>  <br/> |<span data-ttu-id="2cc88-167">нуль</span><span class="sxs-lookup"><span data-stu-id="2cc88-167">0</span></span>  <br/> <span data-ttu-id="2cc88-168">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="2cc88-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="2cc88-169">*\<ключ_домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="2cc88-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="2cc88-170">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2cc88-170">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="2cc88-171">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="2cc88-171">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Введите (или скопируйте и вставьте) значения DNS](../../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. <span data-ttu-id="2cc88-173">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2cc88-173">Select **Save**.</span></span>
    
    ![Нажмите кнопку Сохранить](../../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. <span data-ttu-id="2cc88-175">Если есть какие-либо другие записи MX, удалите каждую из них, выполнив двухшаговую процедуру.</span><span class="sxs-lookup"><span data-stu-id="2cc88-175">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="2cc88-176">Сначала маусинг запись, которую нужно удалить, и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="2cc88-176">First, mousing over a record that you want to remove, select **Delete**.</span></span>
    
    ![Наведите указатель мыши на пункт и выберите Delete (удалить)](../../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    <span data-ttu-id="2cc88-178">Во вторых, нажмите **кнопку Да** , чтобы подтвердить каждое удаление.</span><span class="sxs-lookup"><span data-stu-id="2cc88-178">Second, select **Yes** to confirm each deletion.</span></span> 
    
    ![Выберите Да, чтобы подтвердить удаление](../../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    <span data-ttu-id="2cc88-180">Повторяйте эту процедуру, пока не будут удалены все записи MX, кроме той, которую вы добавили на предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="2cc88-180">Repeat this process until you have deleted all MX records except for the one that you added earlier in this procedure.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="2cc88-181">Добавление записей CNAME, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="2cc88-181">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="2cc88-182"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="2cc88-182"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="2cc88-183">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="2cc88-183">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="2cc88-p109">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Hover по [этой ссылке](https://www.hover.com/domains). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="2cc88-p109">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Вход](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="2cc88-187">В разделе **Управление доменами**выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="2cc88-187">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Выбор домена](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="2cc88-189">Перейдите на вкладку **DNS** .</span><span class="sxs-lookup"><span data-stu-id="2cc88-189">Select the **DNS** tab.</span></span> 
    
    ![Выбор вкладки DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="2cc88-191">Добавьте первую из шести записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="2cc88-191">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="2cc88-192">Нажмите кнопку **Добавить новый**.</span><span class="sxs-lookup"><span data-stu-id="2cc88-192">Select **Add New**.</span></span>
    
    ![Нажмите кнопку Добавить новый](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="2cc88-194">В пустых полях для новой записи выберите значение **CNAME** для параметра **Record Type** (Тип записи) и введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="2cc88-194">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="2cc88-195">**Hostname (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="2cc88-195">**Hostname**</span></span>|<span data-ttu-id="2cc88-196">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="2cc88-196">**Record Type**</span></span>|<span data-ttu-id="2cc88-197">**Target Host (Целевой узел)**</span><span class="sxs-lookup"><span data-stu-id="2cc88-197">**Target Host**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="2cc88-198">autodiscover</span><span class="sxs-lookup"><span data-stu-id="2cc88-198">autodiscover</span></span>  <br/> |<span data-ttu-id="2cc88-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="2cc88-199">CNAME</span></span>  <br/> |<span data-ttu-id="2cc88-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="2cc88-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="2cc88-201">sip</span><span class="sxs-lookup"><span data-stu-id="2cc88-201">sip</span></span>  <br/> |<span data-ttu-id="2cc88-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="2cc88-202">CNAME</span></span>  <br/> |<span data-ttu-id="2cc88-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2cc88-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="2cc88-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="2cc88-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="2cc88-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="2cc88-205">CNAME</span></span>  <br/> |<span data-ttu-id="2cc88-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2cc88-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="2cc88-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="2cc88-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="2cc88-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="2cc88-208">CNAME</span></span>  <br/> |<span data-ttu-id="2cc88-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="2cc88-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="2cc88-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="2cc88-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="2cc88-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="2cc88-211">CNAME</span></span>  <br/> |<span data-ttu-id="2cc88-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2cc88-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Введите (или скопируйте и вставьте) значения DNS](../../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. <span data-ttu-id="2cc88-214">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2cc88-214">Select **Save**.</span></span>
    
    ![Нажмите кнопку Сохранить](../../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. <span data-ttu-id="2cc88-216">Повторяйте три описанных выше шага, используя значения из пяти других строк таблицы, чтобы добавить остальные записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="2cc88-216">Using the preceding three steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="2cc88-217">Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама</span><span class="sxs-lookup"><span data-stu-id="2cc88-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="2cc88-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="2cc88-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="2cc88-219">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="2cc88-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="2cc88-220">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="2cc88-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="2cc88-221">Если у вас уже есть запись SPF для вашего домена, не создавайте ее для Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2cc88-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="2cc88-222">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="2cc88-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="2cc88-223">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="2cc88-223">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="2cc88-p111">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Hover по [этой ссылке](https://www.hover.com/domains). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="2cc88-p111">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Вход](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="2cc88-227">В разделе **Управление доменами**выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="2cc88-227">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Выбор домена](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="2cc88-229">Перейдите на вкладку **DNS** .</span><span class="sxs-lookup"><span data-stu-id="2cc88-229">Select the **DNS** tab.</span></span> 
    
    ![Выбор вкладки DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="2cc88-231">Нажмите кнопку **Добавить новый**.</span><span class="sxs-lookup"><span data-stu-id="2cc88-231">Select **Add New**.</span></span>
    
    ![Нажмите кнопку Добавить новый](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="2cc88-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="2cc88-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="2cc88-234">**Hostname (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="2cc88-234">**Hostname**</span></span>|<span data-ttu-id="2cc88-235">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="2cc88-235">**Record Type**</span></span>|<span data-ttu-id="2cc88-236">**Value (Значение)**</span><span class="sxs-lookup"><span data-stu-id="2cc88-236">**Value**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="2cc88-237">TXT</span><span class="sxs-lookup"><span data-stu-id="2cc88-237">TXT</span></span>  <br/> |<span data-ttu-id="2cc88-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="2cc88-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="2cc88-239">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="2cc88-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Введите (или скопируйте и вставьте) значения DNS](../../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. <span data-ttu-id="2cc88-241">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2cc88-241">Select **Save**.</span></span>
    
    ![Нажмите кнопку Сохранить](../../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="2cc88-243">Добавление двух записей SRV, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="2cc88-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="2cc88-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="2cc88-244"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="2cc88-245">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="2cc88-245">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="2cc88-p112">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Hover по [этой ссылке](https://www.hover.com/domains). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="2cc88-p112">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Вход](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="2cc88-249">В разделе **Управление доменами**выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="2cc88-249">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Выбор домена](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="2cc88-251">Перейдите на вкладку **DNS** .</span><span class="sxs-lookup"><span data-stu-id="2cc88-251">Select the **DNS** tab.</span></span> 
    
    ![Выбор вкладки DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="2cc88-253">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="2cc88-253">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="2cc88-254">Нажмите кнопку **Добавить новый**.</span><span class="sxs-lookup"><span data-stu-id="2cc88-254">Select **Add New**.</span></span>
    
    ![Нажмите кнопку Добавить новый](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="2cc88-256">В пустых полях для новой записи выберите значение **SRV** для параметра **Record Type** (Тип записи) и введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="2cc88-256">In the empty boxes for the new record, select **SRV** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="2cc88-257">**Hostname (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="2cc88-257">**Hostname**</span></span>|<span data-ttu-id="2cc88-258">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="2cc88-258">**Record Type**</span></span>|<span data-ttu-id="2cc88-259">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="2cc88-259">**Priority**</span></span>|<span data-ttu-id="2cc88-260">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="2cc88-260">**Weight**</span></span>|<span data-ttu-id="2cc88-261">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="2cc88-261">**Port**</span></span>|<span data-ttu-id="2cc88-262">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="2cc88-262">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="2cc88-263">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="2cc88-263">_sip._tls</span></span>  <br/> |<span data-ttu-id="2cc88-264">SRV</span><span class="sxs-lookup"><span data-stu-id="2cc88-264">SRV</span></span>  <br/> |<span data-ttu-id="2cc88-265">100</span><span class="sxs-lookup"><span data-stu-id="2cc88-265">100</span></span>  <br/> |<span data-ttu-id="2cc88-266">1,1</span><span class="sxs-lookup"><span data-stu-id="2cc88-266">1</span></span>  <br/> |<span data-ttu-id="2cc88-267">443</span><span class="sxs-lookup"><span data-stu-id="2cc88-267">443</span></span>  <br/> |<span data-ttu-id="2cc88-268">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2cc88-268">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="2cc88-269">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="2cc88-269">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="2cc88-270">SRV</span><span class="sxs-lookup"><span data-stu-id="2cc88-270">SRV</span></span>  <br/> |<span data-ttu-id="2cc88-271">100</span><span class="sxs-lookup"><span data-stu-id="2cc88-271">100</span></span>  <br/> |<span data-ttu-id="2cc88-272">1,1</span><span class="sxs-lookup"><span data-stu-id="2cc88-272">1</span></span>  <br/> |<span data-ttu-id="2cc88-273">5061</span><span class="sxs-lookup"><span data-stu-id="2cc88-273">5061</span></span>  <br/> |<span data-ttu-id="2cc88-274">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2cc88-274">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Введите (или скопируйте и вставьте) значения DNS](../../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. <span data-ttu-id="2cc88-276">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2cc88-276">Select **Save**.</span></span>
    
    ![Нажмите кнопку Сохранить](../../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. <span data-ttu-id="2cc88-278">Повторите три описанных выше шага, используя значения из второй строки таблицы, чтобы добавить еще одну запись SRV.</span><span class="sxs-lookup"><span data-stu-id="2cc88-278">Using the preceding three steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2cc88-p113">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2cc88-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
