---
title: Создание записей DNS для Office 365 на сайте Network Solutions
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
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб в сетевых решениях для Office 365.
ms.openlocfilehash: f94ad49f443e609aa28d634d05604601c7d5e576
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2020
ms.locfileid: "42348540"
---
# <a name="create-dns-records-at-network-solutions-for-office-365"></a><span data-ttu-id="7e621-103">Создание записей DNS для Office 365 на сайте Network Solutions</span><span class="sxs-lookup"><span data-stu-id="7e621-103">Create DNS records at Network Solutions for Office 365</span></span>

 <span data-ttu-id="7e621-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="7e621-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="7e621-105">Если ваш поставщик услуг размещения DNS  Network Solutions, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="7e621-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="7e621-106">Ниже перечислены основные записи, которые нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="7e621-106">These are the main records to add.</span></span> <span data-ttu-id="7e621-107">Воспользуйтесь инструкциями ниже или [посмотрите видеоролик](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="7e621-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> 
  
- [<span data-ttu-id="7e621-108">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="7e621-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="7e621-109">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в Office 365.</span><span class="sxs-lookup"><span data-stu-id="7e621-109">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="7e621-110">Добавление записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="7e621-110">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="7e621-111">Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="7e621-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="7e621-112">Добавьте две записи SRV, необходимые для Office 365.</span><span class="sxs-lookup"><span data-stu-id="7e621-112">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="7e621-113">Добавив эти записи на сайте Network Solutions, вы настроите свой домен для работы со службами Office 365.</span><span class="sxs-lookup"><span data-stu-id="7e621-113">After you add these records at Network Solutions, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="7e621-114">Дополнительные сведения о веб-хостинге и DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="7e621-114">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="7e621-p102">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7e621-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="7e621-118">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="7e621-118">Add a TXT record for verification</span></span>
<span data-ttu-id="7e621-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="7e621-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="7e621-p103">Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="7e621-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7e621-p104">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="7e621-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="7e621-124">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="7e621-124">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="7e621-125">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Network Solutions по [этой ссылке](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="7e621-125">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="7e621-126">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="7e621-126">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7e621-127">Перед нажатием кнопки **Вход** сначала выберите пункт **Управление именами доменов** в раскрывающемся списке **Вход в:** .</span><span class="sxs-lookup"><span data-stu-id="7e621-127">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Выберите Manage My Domain Names (Управление доменными именами) и войдите в систему Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="7e621-129">Установите флажок для доменного имени, которое вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="7e621-129">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Установите флажок для своего домена](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="7e621-131">Выберите **изменить DNS**.</span><span class="sxs-lookup"><span data-stu-id="7e621-131">Select **Edit DNS**.</span></span>
    
    ![Выберите изменить DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="7e621-133">Выберите **Управление расширенными записями DNS**.</span><span class="sxs-lookup"><span data-stu-id="7e621-133">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="7e621-134">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="7e621-134">(You may have to scroll down.)</span></span>
    
    ![Выберите Управление расширенными записями DNS](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="7e621-136">Прокрутите список вниз до раздела **текст (записи TXT)** и выберите команду **изменить записи TXT**.</span><span class="sxs-lookup"><span data-stu-id="7e621-136">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Выберите команду Изменить записи TXT](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="7e621-138">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="7e621-138">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="7e621-139">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="7e621-139">**Host**</span></span>|<span data-ttu-id="7e621-140">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="7e621-140">**TTL**</span></span>|<span data-ttu-id="7e621-141">**Text (Текст)**</span><span class="sxs-lookup"><span data-stu-id="7e621-141">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="7e621-142">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="7e621-142">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="7e621-143">3600</span><span class="sxs-lookup"><span data-stu-id="7e621-143">3600</span></span>  <br/> |<span data-ttu-id="7e621-144">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="7e621-144">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="7e621-145">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="7e621-145">**Note:** This is an example.</span></span> <span data-ttu-id="7e621-146">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="7e621-146">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>  [<span data-ttu-id="7e621-147">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="7e621-147">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![Введите или вставьте значения в поля для новой записи](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="7e621-149">Нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="7e621-149">Select **Continue**.</span></span>
    
    ![Нажмите кнопку продолжить.](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="7e621-151">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="7e621-151">Select **Save Changes**.</span></span>
    
    ![Нажмите кнопку Сохранить изменения](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="7e621-153">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="7e621-153">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="7e621-154">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Office 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="7e621-154">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="7e621-155">Если Office 365 обнаружит правильную запись TXT, это значит, что домен проверен.</span><span class="sxs-lookup"><span data-stu-id="7e621-155">When Office 365 finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="7e621-156">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="7e621-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="7e621-157">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="7e621-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="7e621-158">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="7e621-158">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="7e621-159">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="7e621-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="7e621-p107">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7e621-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="7e621-163">Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="7e621-163">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="7e621-164"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="7e621-164"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="7e621-165">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="7e621-165">Follow the steps below or [watch the video (start at 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="7e621-166">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Network Solutions по [этой ссылке](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="7e621-166">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="7e621-167">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="7e621-167">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7e621-168">Перед нажатием кнопки **Вход** сначала выберите пункт **Управление именами доменов** в раскрывающемся списке **Вход в:** .</span><span class="sxs-lookup"><span data-stu-id="7e621-168">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Выберите Manage My Domain Names (Управление доменными именами) и войдите в систему Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="7e621-170">Установите флажок для доменного имени, которое вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="7e621-170">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Установите флажок для своего домена](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="7e621-172">Выберите **изменить DNS**.</span><span class="sxs-lookup"><span data-stu-id="7e621-172">Select **Edit DNS**.</span></span>
    
    ![Выберите изменить DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="7e621-174">Выберите **Управление расширенными записями DNS**.</span><span class="sxs-lookup"><span data-stu-id="7e621-174">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="7e621-175">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="7e621-175">(You may have to scroll down.)</span></span>
    
    ![Выберите Управление расширенными записями DNS](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="7e621-177">Прокрутите список вниз до раздела **почтовые серверы (записи MX)** и выберите команду **изменить записи MX**.</span><span class="sxs-lookup"><span data-stu-id="7e621-177">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![Выберите Изменить записи MX](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="7e621-179">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="7e621-179">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="7e621-180">**Priority**</span><span class="sxs-lookup"><span data-stu-id="7e621-180">**Priority**</span></span>|<span data-ttu-id="7e621-181">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="7e621-181">**TTL**</span></span>|<span data-ttu-id="7e621-182">**Mail Server (Почтовый сервер)**</span><span class="sxs-lookup"><span data-stu-id="7e621-182">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="7e621-183">10 </span><span class="sxs-lookup"><span data-stu-id="7e621-183">10</span></span>  <br/> <span data-ttu-id="7e621-184">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).   </span><span class="sxs-lookup"><span data-stu-id="7e621-184">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="7e621-185">3600</span><span class="sxs-lookup"><span data-stu-id="7e621-185">3600</span></span>  <br/> | <span data-ttu-id="7e621-186">*\<ключ_домена\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="7e621-186">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="7e621-187">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="7e621-187">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="7e621-188">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Office 365.</span><span class="sxs-lookup"><span data-stu-id="7e621-188">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span> [<span data-ttu-id="7e621-189">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="7e621-189">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![Введите или вставьте значения в поля для новой записи](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="7e621-191">Нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="7e621-191">Select **Continue**.</span></span>
    
    ![Нажмите кнопку продолжить.](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="7e621-193">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="7e621-193">Select **Save Changes**.</span></span>
    
    ![Нажмите кнопку Сохранить изменения](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="7e621-195">Если есть какие-либо другие записи MX, выделите каждую из них и нажмите **Delete** (Удалить).</span><span class="sxs-lookup"><span data-stu-id="7e621-195">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="7e621-197">Когда все будут выбраны, выберите **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="7e621-197">When they are all selected, select **Continue**.</span></span>
    
    ![Нажмите кнопку продолжить.](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="7e621-199">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="7e621-199">Select **Save Changes**.</span></span>
    
    ![Нажмите кнопку Сохранить изменения](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="7e621-201">Добавление записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="7e621-201">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="7e621-202"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="7e621-202"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="7e621-203">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="7e621-203">Follow the steps below or [watch the video (start at 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="7e621-204">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Network Solutions по [этой ссылке](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="7e621-204">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="7e621-205">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="7e621-205">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7e621-206">Перед нажатием кнопки **Вход** сначала выберите пункт **Управление именами доменов** в раскрывающемся списке **Вход в:** .</span><span class="sxs-lookup"><span data-stu-id="7e621-206">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Выберите Manage My Domain Names (Управление доменными именами) и войдите в систему Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="7e621-208">Установите флажок для доменного имени, которое вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="7e621-208">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Установите флажок для своего домена](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="7e621-210">Выберите **изменить DNS**.</span><span class="sxs-lookup"><span data-stu-id="7e621-210">Select **Edit DNS**.</span></span>
    
    ![Выберите изменить DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="7e621-212">Выберите **Управление расширенными записями DNS**.</span><span class="sxs-lookup"><span data-stu-id="7e621-212">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="7e621-213">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="7e621-213">(You may have to scroll down.)</span></span>
    
    ![Выберите Управление расширенными записями DNS](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="7e621-215">Прокрутите список вниз до раздела **псевдонимы узлов (CNAME-записи)** , а затем выберите команду **изменить записи CNAME**.</span><span class="sxs-lookup"><span data-stu-id="7e621-215">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![Выберите Изменить записи CNAME в разделе Псевдонимы узлов](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="7e621-217">В поля для четырех новых записей введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="7e621-217">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="7e621-218">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="7e621-218">**Alias**</span></span>|<span data-ttu-id="7e621-219">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="7e621-219">**TTL**</span></span>|<span data-ttu-id="7e621-220">**Refers to Host Name (Указывает на имя узла)**</span><span class="sxs-lookup"><span data-stu-id="7e621-220">**Refers to Host Name**</span></span>|<span data-ttu-id="7e621-221">**Other Host          (select the **Other Host** option button)**</span><span class="sxs-lookup"><span data-stu-id="7e621-221">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7e621-222">autodiscover</span><span class="sxs-lookup"><span data-stu-id="7e621-222">autodiscover</span></span>  <br/> |<span data-ttu-id="7e621-223">3600</span><span class="sxs-lookup"><span data-stu-id="7e621-223">3600</span></span>  <br/> |<span data-ttu-id="7e621-224">(Нет значения)</span><span class="sxs-lookup"><span data-stu-id="7e621-224">(No setting)</span></span>  <br/> |<span data-ttu-id="7e621-225">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="7e621-225">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="7e621-226">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="7e621-226">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="7e621-227">sip</span><span class="sxs-lookup"><span data-stu-id="7e621-227">sip</span></span>  <br/> |<span data-ttu-id="7e621-228">3600</span><span class="sxs-lookup"><span data-stu-id="7e621-228">3600</span></span>  <br/> |<span data-ttu-id="7e621-229">(Нет значения)</span><span class="sxs-lookup"><span data-stu-id="7e621-229">(No setting)</span></span>  <br/> |<span data-ttu-id="7e621-230">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7e621-230">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="7e621-231">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="7e621-231">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="7e621-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7e621-232">lyncdiscover</span></span>  <br/> |<span data-ttu-id="7e621-233">3600</span><span class="sxs-lookup"><span data-stu-id="7e621-233">3600</span></span>  <br/> |<span data-ttu-id="7e621-234">(Нет значения)</span><span class="sxs-lookup"><span data-stu-id="7e621-234">(No setting)</span></span>  <br/> |<span data-ttu-id="7e621-235">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7e621-235">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="7e621-236">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="7e621-236">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="7e621-237">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="7e621-237">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="7e621-238">3600</span><span class="sxs-lookup"><span data-stu-id="7e621-238">3600</span></span>  <br/> |<span data-ttu-id="7e621-239">(Нет значения)</span><span class="sxs-lookup"><span data-stu-id="7e621-239">(No setting)</span></span>  <br/> |<span data-ttu-id="7e621-240">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="7e621-240">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="7e621-241">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="7e621-241">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="7e621-242">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="7e621-242">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="7e621-243">3600</span><span class="sxs-lookup"><span data-stu-id="7e621-243">3600</span></span>  <br/> |<span data-ttu-id="7e621-244">(Нет значения)</span><span class="sxs-lookup"><span data-stu-id="7e621-244">(No setting)</span></span>  <br/> |<span data-ttu-id="7e621-245">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7e621-245">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="7e621-246">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="7e621-246">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![Ввод или Вставка значений для новых записей](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="7e621-248">После добавления всех необходимых записей CNAME нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="7e621-248">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Нажмите кнопку продолжить.](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="7e621-250">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="7e621-250">Select **Save Changes**.</span></span>
    
    ![Нажмите кнопку Сохранить изменения](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="7e621-252">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="7e621-252">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="7e621-253"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="7e621-253"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="7e621-254">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="7e621-254">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="7e621-255">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="7e621-255">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="7e621-256">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="7e621-256">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="7e621-257">Вместо этого добавьте необходимые значения Office 365 в текущую запись. Таким образом, в *одной* записи SPF будут указаны оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="7e621-257">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="7e621-258">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="7e621-258">Follow the steps below or [watch the video (start at 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="7e621-259">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Network Solutions по [этой ссылке](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="7e621-259">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="7e621-260">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="7e621-260">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7e621-261">Перед нажатием кнопки **Вход** сначала выберите пункт **Управление именами доменов** в раскрывающемся списке **Вход в:** .</span><span class="sxs-lookup"><span data-stu-id="7e621-261">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Выберите Manage My Domain Names (Управление доменными именами) и войдите в систему Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="7e621-263">Установите флажок для доменного имени, которое вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="7e621-263">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Установите флажок для своего домена](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="7e621-265">Выберите **изменить DNS**.</span><span class="sxs-lookup"><span data-stu-id="7e621-265">Select **Edit DNS**.</span></span>
    
    ![Выберите изменить DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="7e621-267">Выберите **Управление расширенными записями DNS**.</span><span class="sxs-lookup"><span data-stu-id="7e621-267">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="7e621-268">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="7e621-268">(You may have to scroll down.)</span></span>
    
    ![Выберите Управление расширенными записями DNS](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="7e621-270">Прокрутите список вниз до раздела **текст (записи TXT)** и выберите команду **изменить записи TXT**.</span><span class="sxs-lookup"><span data-stu-id="7e621-270">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Выберите команду Изменить записи TXT в тексте.](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="7e621-272">В поля для новой записи введите (или скопируйте и вставьте) указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="7e621-272">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="7e621-273">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="7e621-273">**Host**</span></span>|<span data-ttu-id="7e621-274">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="7e621-274">**TTL**</span></span>|<span data-ttu-id="7e621-275">**Text (Текст)**</span><span class="sxs-lookup"><span data-stu-id="7e621-275">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="7e621-276">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="7e621-276">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="7e621-277">3600</span><span class="sxs-lookup"><span data-stu-id="7e621-277">3600</span></span>  <br/> |<span data-ttu-id="7e621-278">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="7e621-278">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="7e621-279">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="7e621-279">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![Ввод или Вставка значений для новой записи](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="7e621-281">Нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="7e621-281">Select **Continue**.</span></span>
    
    ![Нажмите кнопку продолжить.](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="7e621-283">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="7e621-283">Select **Save Changes**.</span></span>
    
    ![Нажмите кнопку Сохранить изменения](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="7e621-285">Добавление двух записей SRV, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="7e621-285">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="7e621-286"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="7e621-286"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="7e621-287">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="7e621-287">Follow the steps below or [watch the video (start at 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="7e621-p113">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Network Solutions по [этой ссылке](https://www.networksolutions.com/manage-it). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="7e621-p113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7e621-290">Перед нажатием кнопки **Вход** сначала выберите пункт **Управление именами доменов** в раскрывающемся списке **Вход в:** .</span><span class="sxs-lookup"><span data-stu-id="7e621-290">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Выберите Manage My Domain Names (Управление доменными именами) и войдите в систему Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="7e621-292">Установите флажок для доменного имени, которое вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="7e621-292">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Установите флажок для своего домена](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="7e621-294">Выберите **изменить DNS**.</span><span class="sxs-lookup"><span data-stu-id="7e621-294">Select **Edit DNS**.</span></span>
    
    ![Выберите изменить DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="7e621-296">Выберите **Управление расширенными записями DNS**.</span><span class="sxs-lookup"><span data-stu-id="7e621-296">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="7e621-297">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="7e621-297">(You may have to scroll down.)</span></span>
    
    ![Выберите Управление расширенными записями DNS](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="7e621-299">Прокрутите вниз до раздела **служба (записи SRV)** , а затем выберите **изменить записи SRV**.</span><span class="sxs-lookup"><span data-stu-id="7e621-299">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![Выберите Изменить записи SRV в разделе Служба](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="7e621-301">В поля для двух новых записей введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="7e621-301">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="7e621-302">(Выберите значения **Service** (Служба) и **Protocol** (Протокол) в раскрывающихся списках.)</span><span class="sxs-lookup"><span data-stu-id="7e621-302">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="7e621-303">**Service (Служба)**</span><span class="sxs-lookup"><span data-stu-id="7e621-303">**Service**</span></span>|<span data-ttu-id="7e621-304">**Protocol (Протокол)**</span><span class="sxs-lookup"><span data-stu-id="7e621-304">**Protocol**</span></span>|<span data-ttu-id="7e621-305">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="7e621-305">**TTL**</span></span>|<span data-ttu-id="7e621-306">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="7e621-306">**Priority**</span></span>|<span data-ttu-id="7e621-307">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="7e621-307">**Weight**</span></span>|<span data-ttu-id="7e621-308">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="7e621-308">**Port**</span></span>|<span data-ttu-id="7e621-309">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="7e621-309">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7e621-310">_sip</span><span class="sxs-lookup"><span data-stu-id="7e621-310">_sip</span></span>  <br/> |<span data-ttu-id="7e621-311">_tls</span><span class="sxs-lookup"><span data-stu-id="7e621-311">_tls</span></span>  <br/> |<span data-ttu-id="7e621-312">3600</span><span class="sxs-lookup"><span data-stu-id="7e621-312">3600</span></span>  <br/> |<span data-ttu-id="7e621-313">100</span><span class="sxs-lookup"><span data-stu-id="7e621-313">100</span></span>  <br/> |<span data-ttu-id="7e621-314">1,1</span><span class="sxs-lookup"><span data-stu-id="7e621-314">1</span></span>  <br/> |<span data-ttu-id="7e621-315">443</span><span class="sxs-lookup"><span data-stu-id="7e621-315">443</span></span>  <br/> |<span data-ttu-id="7e621-316">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7e621-316">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="7e621-317">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="7e621-317">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="7e621-318">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="7e621-318">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="7e621-319">_tcp</span><span class="sxs-lookup"><span data-stu-id="7e621-319">_tcp</span></span>  <br/> |<span data-ttu-id="7e621-320">3600</span><span class="sxs-lookup"><span data-stu-id="7e621-320">3600</span></span>  <br/> |<span data-ttu-id="7e621-321">100</span><span class="sxs-lookup"><span data-stu-id="7e621-321">100</span></span>  <br/> |<span data-ttu-id="7e621-322">1,1</span><span class="sxs-lookup"><span data-stu-id="7e621-322">1</span></span>  <br/> |<span data-ttu-id="7e621-323">5061</span><span class="sxs-lookup"><span data-stu-id="7e621-323">5061</span></span>  <br/> |<span data-ttu-id="7e621-324">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7e621-324">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="7e621-325">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="7e621-325">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![Ввод или Вставка значений для новых записей](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="7e621-327">Нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="7e621-327">Select **Continue**.</span></span>
    
    ![Нажмите кнопку продолжить.](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="7e621-329">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="7e621-329">Select **Save Changes**.</span></span>
    
    ![Нажмите кнопку Сохранить изменения](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="7e621-p114">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7e621-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
