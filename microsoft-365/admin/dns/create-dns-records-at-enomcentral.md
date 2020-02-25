---
title: Создание DNS-записей для Office 365 на сайте eNomCentral
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу eNomCentral для Office 365.
ms.openlocfilehash: c4cd12667ebf945aa2f354ccfa0bad1688dc9863
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42245219"
---
# <a name="create-dns-records-at-enomcentral-for-office-365"></a><span data-ttu-id="af1f9-103">Создание DNS-записей для Office 365 на сайте eNomCentral</span><span class="sxs-lookup"><span data-stu-id="af1f9-103">Create DNS records at eNomCentral for Office 365</span></span>

 <span data-ttu-id="af1f9-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="af1f9-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="af1f9-105">Если ваш поставщик услуг размещения DNS  eNomCentral, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="af1f9-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="af1f9-106">Когда вы добавите эти записи на сайте eNomCentral, ваш домен будет настроен для работы со службами Office 365.</span><span class="sxs-lookup"><span data-stu-id="af1f9-106">After you add these records at eNomCentral, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="af1f9-107">Дополнительные сведения о веб-хостинге и DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="af1f9-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="af1f9-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="af1f9-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="af1f9-111">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="af1f9-111">Add a TXT record for verification</span></span>
<span data-ttu-id="af1f9-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="af1f9-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="af1f9-p102">Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете данным доменом.</span><span class="sxs-lookup"><span data-stu-id="af1f9-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="af1f9-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="af1f9-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="af1f9-117">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="af1f9-117">Follow the steps below or [watch the video (start at 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="af1f9-p104">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте eNom Central по [этой ссылке](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="af1f9-p104">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom Central — BP — configure – 1-1](../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="af1f9-121">В разделе **My Domains (мои домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="af1f9-121">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom Central — BP — configure – 1-2](../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="af1f9-123">В раскрывающемся списке **Manage Domain** (Управление доменом) выберите пункт **Host Records** (Записи узлов).</span><span class="sxs-lookup"><span data-stu-id="af1f9-123">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom Central — BP — Verify – 1-1](../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. <span data-ttu-id="af1f9-125">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="af1f9-125">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="af1f9-126">(Choose the **Record Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="af1f9-126">(Choose the **Record Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="af1f9-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="af1f9-127">**Host Name**</span></span> <br/> |<span data-ttu-id="af1f9-128">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="af1f9-128">**Record Type**</span></span> <br/> |<span data-ttu-id="af1f9-129">**Address** (Адрес)</span><span class="sxs-lookup"><span data-stu-id="af1f9-129">**Address**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="af1f9-130">TXT</span><span class="sxs-lookup"><span data-stu-id="af1f9-130">TXT</span></span>  <br/> |<span data-ttu-id="af1f9-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="af1f9-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="af1f9-p105">**Примечание.** Это пример. Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.           [Где это находится?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="af1f9-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
       
   ![eNom Central — BP — Verify – 1-2](../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. <span data-ttu-id="af1f9-136">Нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="af1f9-136">Select **save**.</span></span>
    
    ![eNom Central — BP — Verify – 1-3](../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. <span data-ttu-id="af1f9-138">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="af1f9-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="af1f9-139">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="af1f9-139">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="af1f9-140">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="af1f9-140">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="af1f9-141">В центре администрирования перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> **параметров** \> ".</span><span class="sxs-lookup"><span data-stu-id="af1f9-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="af1f9-142">На странице **Domains (домены** ) выберите домен, который вы хотите проверить.</span><span class="sxs-lookup"><span data-stu-id="af1f9-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="af1f9-143">На странице **Настройка** выберите пункт **Запуск программы установки**.</span><span class="sxs-lookup"><span data-stu-id="af1f9-143">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="af1f9-144">На странице **Проверка домена** нажмите кнопку **проверить**.</span><span class="sxs-lookup"><span data-stu-id="af1f9-144">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="af1f9-p106">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="af1f9-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="af1f9-148">Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="af1f9-148">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="af1f9-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="af1f9-149"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="af1f9-150">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="af1f9-150">Follow the steps below or [watch the video (start at 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="af1f9-p107">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте eNom Central по [этой ссылке](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="af1f9-p107">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom Central — BP — configure – 1-1](../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="af1f9-154">В разделе **My Domains (мои домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="af1f9-154">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom Central — BP — configure – 1-2](../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="af1f9-156">В раскрывающемся списке **Manage Domain** (Управление доменом) выберите пункт **Email Settings** (Параметры электронной почты).</span><span class="sxs-lookup"><span data-stu-id="af1f9-156">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>
    
    ![eNom Central — BP — configure – 1-3](../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. <span data-ttu-id="af1f9-158">В раскрывающемся списке **Service Selection** (Выбор службы) выберите пункт **User (MX)** (Пользователь (MX).</span><span class="sxs-lookup"><span data-stu-id="af1f9-158">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>
    
    ![eNom Central — BP — configure – 1-4](../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. <span data-ttu-id="af1f9-160">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="af1f9-160">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="af1f9-161">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="af1f9-161">**Host Name**</span></span>|<span data-ttu-id="af1f9-162">**Address**</span><span class="sxs-lookup"><span data-stu-id="af1f9-162">**Address**</span></span>|<span data-ttu-id="af1f9-163">**Pref (Предпочтение)**</span><span class="sxs-lookup"><span data-stu-id="af1f9-163">**Pref**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> | <span data-ttu-id="af1f9-164">*\<ключ_домена\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="af1f9-164">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="af1f9-165">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="af1f9-165">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="af1f9-166">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Office 365.</span><span class="sxs-lookup"><span data-stu-id="af1f9-166">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="af1f9-167">Где это находится?</span><span class="sxs-lookup"><span data-stu-id="af1f9-167">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="af1f9-168">10 </span><span class="sxs-lookup"><span data-stu-id="af1f9-168">10</span></span>  <br/> <span data-ttu-id="af1f9-169">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).   </span><span class="sxs-lookup"><span data-stu-id="af1f9-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
       
   ![eNom Central — BP — configure – 2-1](../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. <span data-ttu-id="af1f9-171">Нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="af1f9-171">Select **save**.</span></span>
    
    ![eNom Central — BP — configure – 2-2](../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. <span data-ttu-id="af1f9-173">Если в списке указаны другие существующие записи MX, установите для них флажки, чтобы выбрать их.</span><span class="sxs-lookup"><span data-stu-id="af1f9-173">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>
    
    ![eNom Central — BP — configure – 2-3](../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. <span data-ttu-id="af1f9-175">Выберите вариант **Удалить проверено**.</span><span class="sxs-lookup"><span data-stu-id="af1f9-175">Select **delete checked**.</span></span>
    
    ![eNom Central — BP — configure – 2-4](../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="af1f9-177">Добавление записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="af1f9-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="af1f9-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="af1f9-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="af1f9-179">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="af1f9-179">Follow the steps below or [watch the video (start at 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="af1f9-p109">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте eNom Central по [этой ссылке](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="af1f9-p109">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom Central — BP — configure – 1-1](../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="af1f9-183">В разделе **My Domains (мои домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="af1f9-183">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom Central — BP — configure – 1-2](../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="af1f9-185">В раскрывающемся списке **Manage Domain** (Управление доменом) выберите пункт **Host Records** (Записи узлов).</span><span class="sxs-lookup"><span data-stu-id="af1f9-185">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom Central — BP — configure – 1-5](../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="af1f9-187">Выберите пункт **создать строку**.</span><span class="sxs-lookup"><span data-stu-id="af1f9-187">Select **new row**.</span></span>
    
    ![eNom Central — BP — configure – 3-1](../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. <span data-ttu-id="af1f9-189">В поля для шести новых записей введите (или скопируйте и вставьте) следующие значения.</span><span class="sxs-lookup"><span data-stu-id="af1f9-189">In the boxes for the six new records, type or copy and paste the following values.</span></span>
    
        (Choose the **Record Type** value from the drop-down list.) 
        
    |<span data-ttu-id="af1f9-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="af1f9-190">**Host Name**</span></span>|<span data-ttu-id="af1f9-191">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="af1f9-191">**Record Type**</span></span>|<span data-ttu-id="af1f9-192">**Address (Адрес)**</span><span class="sxs-lookup"><span data-stu-id="af1f9-192">**Address**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="af1f9-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="af1f9-193">autodiscover</span></span>  <br/> |<span data-ttu-id="af1f9-194">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="af1f9-194">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="af1f9-195">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="af1f9-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="af1f9-196">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="af1f9-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="af1f9-197">sip</span><span class="sxs-lookup"><span data-stu-id="af1f9-197">sip</span></span>  <br/> |<span data-ttu-id="af1f9-198">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="af1f9-198">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="af1f9-199">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="af1f9-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="af1f9-200">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="af1f9-200">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="af1f9-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="af1f9-201">lyncdiscover</span></span>  <br/> |<span data-ttu-id="af1f9-202">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="af1f9-202">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="af1f9-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="af1f9-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="af1f9-204">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="af1f9-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="af1f9-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="af1f9-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="af1f9-206">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="af1f9-206">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="af1f9-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="af1f9-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="af1f9-208">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="af1f9-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="af1f9-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="af1f9-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="af1f9-210">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="af1f9-210">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="af1f9-211">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="af1f9-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="af1f9-212">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="af1f9-212">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom Central — BP — configure – 3-2](../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. <span data-ttu-id="af1f9-214">Нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="af1f9-214">Select **save**.</span></span>
    
    ![eNom Central — BP — configure – 3-3](../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="af1f9-216">Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="af1f9-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="af1f9-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="af1f9-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="af1f9-218">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="af1f9-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="af1f9-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="af1f9-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="af1f9-220">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="af1f9-220">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="af1f9-221">Вместо этого добавьте необходимые значения Office 365 к текущей записи, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="af1f9-221">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="af1f9-222">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="af1f9-222">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="af1f9-p111">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте eNom Central по [этой ссылке](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="af1f9-p111">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom Central — BP — configure – 1-1](../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="af1f9-226">В разделе **My Domains (мои домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="af1f9-226">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom Central — BP — configure – 1-2](../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="af1f9-228">В раскрывающемся списке **Manage Domain** (Управление доменом) выберите пункт **Host Records** (Записи узлов).</span><span class="sxs-lookup"><span data-stu-id="af1f9-228">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom Central — BP — configure – 1-5](../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="af1f9-230">В поля для новой записи введите (или скопируйте и вставьте) значения из приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="af1f9-230">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="af1f9-231">(Choose the **Record Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="af1f9-231">(Choose the **Record Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="af1f9-232">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="af1f9-232">**Host Name**</span></span>|<span data-ttu-id="af1f9-233">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="af1f9-233">**Record Type**</span></span>|<span data-ttu-id="af1f9-234">**Address** (Адрес)</span><span class="sxs-lookup"><span data-stu-id="af1f9-234">**Address**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="af1f9-235">TXT</span><span class="sxs-lookup"><span data-stu-id="af1f9-235">TXT</span></span>  <br/> |<span data-ttu-id="af1f9-236">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="af1f9-236">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="af1f9-237">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="af1f9-237">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![eNom Central — BP — configure – 4-1](../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. <span data-ttu-id="af1f9-239">Нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="af1f9-239">Select **save**.</span></span>
    
    ![eNom Central — BP — configure – 4-2](../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="af1f9-241">Добавление двух записей SRV, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="af1f9-241">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="af1f9-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="af1f9-242"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="af1f9-243">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="af1f9-243">Follow the steps below or [watch the video (start at 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="af1f9-p112">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте eNom Central по [этой ссылке](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="af1f9-p112">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom Central — BP — configure – 1-1](../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="af1f9-247">В разделе **My Domains (мои домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="af1f9-247">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom Central — BP — configure – 1-2](../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="af1f9-249">В раскрывающемся списке **Manage Domain** (Управление доменом) выберите пункт **Host Records** (Записи узлов).</span><span class="sxs-lookup"><span data-stu-id="af1f9-249">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom Central — BP — configure – 1-5](../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="af1f9-251">Справа от **новой строки**выберите **Добавить запись SRV или SPF**.</span><span class="sxs-lookup"><span data-stu-id="af1f9-251">To the right of **new row**, select **add SRV or SPF record**.</span></span>
    
    ![eNom Central — BP — configure – 5-1](../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. <span data-ttu-id="af1f9-253">В поля для двух новых записей введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="af1f9-253">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="af1f9-254">**Service (Служба)**</span><span class="sxs-lookup"><span data-stu-id="af1f9-254">**Service**</span></span>|<span data-ttu-id="af1f9-255">**Protocol (Протокол)**</span><span class="sxs-lookup"><span data-stu-id="af1f9-255">**Protocol**</span></span>|<span data-ttu-id="af1f9-256">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="af1f9-256">**Priority**</span></span>|<span data-ttu-id="af1f9-257">**Weight (Вес)**</span><span class="sxs-lookup"><span data-stu-id="af1f9-257">**Weight**</span></span>|<span data-ttu-id="af1f9-258">**Port (Порт)**</span><span class="sxs-lookup"><span data-stu-id="af1f9-258">**Port**</span></span>|<span data-ttu-id="af1f9-259">**Target          (Hostname) (Узел назначения)**</span><span class="sxs-lookup"><span data-stu-id="af1f9-259">**Target          (Hostname)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="af1f9-260">_sip</span><span class="sxs-lookup"><span data-stu-id="af1f9-260">_sip</span></span>  <br/> |<span data-ttu-id="af1f9-261">_tls</span><span class="sxs-lookup"><span data-stu-id="af1f9-261">_tls</span></span>  <br/> |<span data-ttu-id="af1f9-262">100</span><span class="sxs-lookup"><span data-stu-id="af1f9-262">100</span></span>  <br/> |<span data-ttu-id="af1f9-263">1,1</span><span class="sxs-lookup"><span data-stu-id="af1f9-263">1</span></span>  <br/> |<span data-ttu-id="af1f9-264">443</span><span class="sxs-lookup"><span data-stu-id="af1f9-264">443</span></span>  <br/> |<span data-ttu-id="af1f9-265">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="af1f9-265">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="af1f9-266">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="af1f9-266">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="af1f9-267">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="af1f9-267">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="af1f9-268">_tcp</span><span class="sxs-lookup"><span data-stu-id="af1f9-268">_tcp</span></span>  <br/> |<span data-ttu-id="af1f9-269">100</span><span class="sxs-lookup"><span data-stu-id="af1f9-269">100</span></span>  <br/> |<span data-ttu-id="af1f9-270">1,1</span><span class="sxs-lookup"><span data-stu-id="af1f9-270">1</span></span>  <br/> |<span data-ttu-id="af1f9-271">5061</span><span class="sxs-lookup"><span data-stu-id="af1f9-271">5061</span></span>  <br/> |<span data-ttu-id="af1f9-272">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="af1f9-272">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="af1f9-273">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="af1f9-273">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom Central — BP — configure – 5-2](../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. <span data-ttu-id="af1f9-275">Нажмите кнопку **сохранить**</span><span class="sxs-lookup"><span data-stu-id="af1f9-275">Select **save**</span></span>
    
    ![eNom Central — BP — configure – 5-3](../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  <span data-ttu-id="af1f9-p113">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="af1f9-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

