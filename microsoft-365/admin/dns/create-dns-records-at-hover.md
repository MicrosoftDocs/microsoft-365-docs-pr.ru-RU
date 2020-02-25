---
title: Создание записей DNS для Office 365 на сайте Hover
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
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб при наведении указателя на Office 365.
ms.openlocfilehash: 54ff58963dcd66f692507f1d778fb9a8d24f82fa
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42249272"
---
# <a name="create-dns-records-at-hover-for-office-365"></a><span data-ttu-id="cc083-103">Создание записей DNS для Office 365 на сайте Hover</span><span class="sxs-lookup"><span data-stu-id="cc083-103">Create DNS records at Hover for Office 365</span></span>

 <span data-ttu-id="cc083-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="cc083-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="cc083-105">Если ваш поставщик услуг размещения DNS  Hover, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="cc083-105">If Hover is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
     
<span data-ttu-id="cc083-106">Когда вы добавите эти записи на сайте Hover, ваш домен будет настроен для работы со службами Office 365.</span><span class="sxs-lookup"><span data-stu-id="cc083-106">After you add these records at Hover, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="cc083-107">Дополнительные сведения о веб-хостинге и DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="cc083-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="cc083-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cc083-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="cc083-111">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="cc083-111">Add a TXT record for verification</span></span>
<span data-ttu-id="cc083-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="cc083-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="cc083-p102">Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете данным доменом.</span><span class="sxs-lookup"><span data-stu-id="cc083-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cc083-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="cc083-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="cc083-117">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="cc083-117">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="cc083-p104">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Hover по [этой ссылке](https://www.hover.com/domains). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="cc083-p104">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Вход](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="cc083-121">В разделе **Управление доменами**выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="cc083-121">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Выбор домена](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="cc083-123">Перейдите на вкладку **DNS** .</span><span class="sxs-lookup"><span data-stu-id="cc083-123">Select the **DNS** tab.</span></span> 
    
    ![Выбор вкладки DNS](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="cc083-125">Нажмите кнопку **Добавить новый**.</span><span class="sxs-lookup"><span data-stu-id="cc083-125">Select **Add New**.</span></span>
    
    ![Нажмите кнопку Добавить новый](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="cc083-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="cc083-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="cc083-128">Hostname (Имя узла)</span><span class="sxs-lookup"><span data-stu-id="cc083-128">Hostname</span></span>  <br/> |<span data-ttu-id="cc083-129">Record Type</span><span class="sxs-lookup"><span data-stu-id="cc083-129">Record Type</span></span>  <br/> |<span data-ttu-id="cc083-130">Value (Значение)</span><span class="sxs-lookup"><span data-stu-id="cc083-130">Value</span></span>  <br/> |
    |@  <br/> |<span data-ttu-id="cc083-131">TXT</span><span class="sxs-lookup"><span data-stu-id="cc083-131">TXT</span></span>  <br/> |<span data-ttu-id="cc083-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="cc083-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="cc083-p105">**Примечание.** Это пример. Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.           [Где это находится?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="cc083-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![Введите (или скопируйте и вставьте) значения DNS](../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. <span data-ttu-id="cc083-137">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cc083-137">Select **Save**.</span></span>
    
    ![Нажмите кнопку Сохранить](../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. <span data-ttu-id="cc083-139">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="cc083-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="cc083-140">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="cc083-140">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="cc083-141">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="cc083-141">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="cc083-142">В центре администрирования перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> **параметров** \> ".</span><span class="sxs-lookup"><span data-stu-id="cc083-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="cc083-143">На странице **Domains (домены** ) выберите домен, который вы хотите проверить.</span><span class="sxs-lookup"><span data-stu-id="cc083-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="cc083-144">На странице **Настройка** выберите пункт **Запуск программы установки**.</span><span class="sxs-lookup"><span data-stu-id="cc083-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="cc083-145">На странице **Проверка домена** нажмите кнопку **проверить**.</span><span class="sxs-lookup"><span data-stu-id="cc083-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="cc083-p106">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cc083-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="cc083-149">Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="cc083-149">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="cc083-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="cc083-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="cc083-151">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="cc083-151">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="cc083-p107">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Hover по [этой ссылке](https://www.hover.com/domains). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="cc083-p107">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Вход](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="cc083-155">В разделе **Управление доменами**выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="cc083-155">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Выбор домена](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="cc083-157">Перейдите на вкладку **DNS** .</span><span class="sxs-lookup"><span data-stu-id="cc083-157">Select the **DNS** tab.</span></span> 
    
    ![Выбор вкладки DNS](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="cc083-159">Нажмите кнопку **Добавить новый**.</span><span class="sxs-lookup"><span data-stu-id="cc083-159">Select **Add New**.</span></span>
    
    ![Нажмите кнопку Добавить новый](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="cc083-161">В полях для новой записи выберите значение **MX** для параметра **Record Type** (Тип записи) и введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="cc083-161">In the boxes for the new record, select **MX** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="cc083-162">**Hostname (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="cc083-162">**Hostname**</span></span>|<span data-ttu-id="cc083-163">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="cc083-163">**Record Type**</span></span>|<span data-ttu-id="cc083-164">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="cc083-164">**Priority**</span></span>|<span data-ttu-id="cc083-165">**Hostname (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="cc083-165">**Hostname**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="cc083-166">MX</span><span class="sxs-lookup"><span data-stu-id="cc083-166">MX</span></span>  <br/> |<span data-ttu-id="cc083-167">нуль</span><span class="sxs-lookup"><span data-stu-id="cc083-167">0</span></span>  <br/> <span data-ttu-id="cc083-168">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).   </span><span class="sxs-lookup"><span data-stu-id="cc083-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="cc083-169">*\<ключ_домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="cc083-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="cc083-170">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Office 365.</span><span class="sxs-lookup"><span data-stu-id="cc083-170">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="cc083-171">Как найти это значение?</span><span class="sxs-lookup"><span data-stu-id="cc083-171">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Введите (или скопируйте и вставьте) значения DNS](../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. <span data-ttu-id="cc083-173">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cc083-173">Select **Save**.</span></span>
    
    ![Нажмите кнопку Сохранить](../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. <span data-ttu-id="cc083-175">Если есть какие-либо другие записи MX, удалите каждую из них, выполнив двухшаговую процедуру.</span><span class="sxs-lookup"><span data-stu-id="cc083-175">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="cc083-176">Сначала маусинг запись, которую нужно удалить, и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="cc083-176">First, mousing over a record that you want to remove, select **Delete**.</span></span>
    
    ![Наведите указатель мыши на пункт и выберите Delete (удалить)](../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    <span data-ttu-id="cc083-178">Во вторых, нажмите **кнопку Да** , чтобы подтвердить каждое удаление.</span><span class="sxs-lookup"><span data-stu-id="cc083-178">Second, select **Yes** to confirm each deletion.</span></span> 
    
    ![Выберите Да, чтобы подтвердить удаление](../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    <span data-ttu-id="cc083-180">Повторяйте эту процедуру, пока не будут удалены все записи MX, кроме той, которую вы добавили на предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="cc083-180">Repeat this process until you have deleted all MX records except for the one that you added earlier in this procedure.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="cc083-181">Добавление записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="cc083-181">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="cc083-182"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="cc083-182"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="cc083-183">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="cc083-183">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="cc083-p109">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Hover по [этой ссылке](https://www.hover.com/domains). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="cc083-p109">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Вход](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="cc083-187">В разделе **Управление доменами**выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="cc083-187">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Выбор домена](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="cc083-189">Перейдите на вкладку **DNS** .</span><span class="sxs-lookup"><span data-stu-id="cc083-189">Select the **DNS** tab.</span></span> 
    
    ![Выбор вкладки DNS](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="cc083-191">Добавьте первую из шести записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="cc083-191">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="cc083-192">Нажмите кнопку **Добавить новый**.</span><span class="sxs-lookup"><span data-stu-id="cc083-192">Select **Add New**.</span></span>
    
    ![Нажмите кнопку Добавить новый](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="cc083-194">В пустых полях для новой записи выберите значение **CNAME** для параметра **Record Type** (Тип записи) и введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="cc083-194">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="cc083-195">**Hostname (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="cc083-195">**Hostname**</span></span>|<span data-ttu-id="cc083-196">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="cc083-196">**Record Type**</span></span>|<span data-ttu-id="cc083-197">**Target Host (Целевой узел)**</span><span class="sxs-lookup"><span data-stu-id="cc083-197">**Target Host**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="cc083-198">autodiscover</span><span class="sxs-lookup"><span data-stu-id="cc083-198">autodiscover</span></span>  <br/> |<span data-ttu-id="cc083-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="cc083-199">CNAME</span></span>  <br/> |<span data-ttu-id="cc083-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="cc083-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="cc083-201">sip</span><span class="sxs-lookup"><span data-stu-id="cc083-201">sip</span></span>  <br/> |<span data-ttu-id="cc083-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="cc083-202">CNAME</span></span>  <br/> |<span data-ttu-id="cc083-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cc083-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="cc083-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="cc083-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="cc083-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="cc083-205">CNAME</span></span>  <br/> |<span data-ttu-id="cc083-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cc083-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="cc083-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="cc083-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="cc083-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="cc083-208">CNAME</span></span>  <br/> |<span data-ttu-id="cc083-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="cc083-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="cc083-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="cc083-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="cc083-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="cc083-211">CNAME</span></span>  <br/> |<span data-ttu-id="cc083-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cc083-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Введите (или скопируйте и вставьте) значения DNS](../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. <span data-ttu-id="cc083-214">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cc083-214">Select **Save**.</span></span>
    
    ![Нажмите кнопку Сохранить](../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. <span data-ttu-id="cc083-216">Повторяйте три описанных выше шага, используя значения из пяти других строк таблицы, чтобы добавить остальные записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="cc083-216">Using the preceding three steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="cc083-217">Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="cc083-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="cc083-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="cc083-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc083-219">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="cc083-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="cc083-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="cc083-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="cc083-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="cc083-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="cc083-222">Вместо этого добавьте необходимые значения Office 365 к текущей записи, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="cc083-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="cc083-223">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="cc083-223">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="cc083-p111">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Hover по [этой ссылке](https://www.hover.com/domains). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="cc083-p111">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Вход](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="cc083-227">В разделе **Управление доменами**выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="cc083-227">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Выбор домена](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="cc083-229">Перейдите на вкладку **DNS** .</span><span class="sxs-lookup"><span data-stu-id="cc083-229">Select the **DNS** tab.</span></span> 
    
    ![Выбор вкладки DNS](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="cc083-231">Нажмите кнопку **Добавить новый**.</span><span class="sxs-lookup"><span data-stu-id="cc083-231">Select **Add New**.</span></span>
    
    ![Нажмите кнопку Добавить новый](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="cc083-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="cc083-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="cc083-234">**Hostname (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="cc083-234">**Hostname**</span></span>|<span data-ttu-id="cc083-235">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="cc083-235">**Record Type**</span></span>|<span data-ttu-id="cc083-236">**Value (Значение)**</span><span class="sxs-lookup"><span data-stu-id="cc083-236">**Value**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="cc083-237">TXT</span><span class="sxs-lookup"><span data-stu-id="cc083-237">TXT</span></span>  <br/> |<span data-ttu-id="cc083-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="cc083-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="cc083-239">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="cc083-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Введите (или скопируйте и вставьте) значения DNS](../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. <span data-ttu-id="cc083-241">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cc083-241">Select **Save**.</span></span>
    
    ![Нажмите кнопку Сохранить](../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="cc083-243">Добавление двух записей SRV, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="cc083-243">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="cc083-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="cc083-244"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="cc083-245">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="cc083-245">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="cc083-p112">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Hover по [этой ссылке](https://www.hover.com/domains). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="cc083-p112">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Вход](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="cc083-249">В разделе **Управление доменами**выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="cc083-249">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Выбор домена](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="cc083-251">Перейдите на вкладку **DNS** .</span><span class="sxs-lookup"><span data-stu-id="cc083-251">Select the **DNS** tab.</span></span> 
    
    ![Выбор вкладки DNS](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="cc083-253">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="cc083-253">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="cc083-254">Нажмите кнопку **Добавить новый**.</span><span class="sxs-lookup"><span data-stu-id="cc083-254">Select **Add New**.</span></span>
    
    ![Нажмите кнопку Добавить новый](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="cc083-256">В пустых полях для новой записи выберите значение **SRV** для параметра **Record Type** (Тип записи) и введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="cc083-256">In the empty boxes for the new record, select **SRV** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="cc083-257">**Hostname (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="cc083-257">**Hostname**</span></span>|<span data-ttu-id="cc083-258">**Record Type (Тип записи)**</span><span class="sxs-lookup"><span data-stu-id="cc083-258">**Record Type**</span></span>|<span data-ttu-id="cc083-259">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="cc083-259">**Priority**</span></span>|<span data-ttu-id="cc083-260">**Weight (Вес)**</span><span class="sxs-lookup"><span data-stu-id="cc083-260">**Weight**</span></span>|<span data-ttu-id="cc083-261">**Port (Порт)**</span><span class="sxs-lookup"><span data-stu-id="cc083-261">**Port**</span></span>|<span data-ttu-id="cc083-262">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="cc083-262">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cc083-263">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="cc083-263">_sip._tls</span></span>  <br/> |<span data-ttu-id="cc083-264">SRV</span><span class="sxs-lookup"><span data-stu-id="cc083-264">SRV</span></span>  <br/> |<span data-ttu-id="cc083-265">100</span><span class="sxs-lookup"><span data-stu-id="cc083-265">100</span></span>  <br/> |<span data-ttu-id="cc083-266">1,1</span><span class="sxs-lookup"><span data-stu-id="cc083-266">1</span></span>  <br/> |<span data-ttu-id="cc083-267">443</span><span class="sxs-lookup"><span data-stu-id="cc083-267">443</span></span>  <br/> |<span data-ttu-id="cc083-268">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cc083-268">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="cc083-269">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="cc083-269">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="cc083-270">SRV</span><span class="sxs-lookup"><span data-stu-id="cc083-270">SRV</span></span>  <br/> |<span data-ttu-id="cc083-271">100</span><span class="sxs-lookup"><span data-stu-id="cc083-271">100</span></span>  <br/> |<span data-ttu-id="cc083-272">1,1</span><span class="sxs-lookup"><span data-stu-id="cc083-272">1</span></span>  <br/> |<span data-ttu-id="cc083-273">5061</span><span class="sxs-lookup"><span data-stu-id="cc083-273">5061</span></span>  <br/> |<span data-ttu-id="cc083-274">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cc083-274">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Введите (или скопируйте и вставьте) значения DNS](../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. <span data-ttu-id="cc083-276">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cc083-276">Select **Save**.</span></span>
    
    ![Нажмите кнопку Сохранить](../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. <span data-ttu-id="cc083-278">Повторите три описанных выше шага, используя значения из второй строки таблицы, чтобы добавить еще одну запись SRV.</span><span class="sxs-lookup"><span data-stu-id="cc083-278">Using the preceding three steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cc083-p113">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cc083-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
