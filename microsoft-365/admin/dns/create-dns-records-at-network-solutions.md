---
title: Создание записей DNS в сетевых решениях для Майкрософт
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
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб в сетевых решениях для Майкрософт.
ms.openlocfilehash: f488ad3511c9901eae70691f616dcff52036c71d
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645951"
---
# <a name="create-dns-records-at-network-solutions-for-microsoft"></a><span data-ttu-id="1de5e-103">Создание записей DNS в сетевых решениях для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="1de5e-103">Create DNS records at Network Solutions for Microsoft</span></span>

 <span data-ttu-id="1de5e-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="1de5e-105">Если ваш поставщик услуг размещения DNS  Network Solutions, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="1de5e-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="1de5e-106">Ниже перечислены основные записи, которые нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="1de5e-106">These are the main records to add.</span></span> <span data-ttu-id="1de5e-107">Воспользуйтесь инструкциями ниже или [посмотрите видеоролик](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="1de5e-107">Follow the steps below or [watch the video](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span> 
  
- [<span data-ttu-id="1de5e-108">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="1de5e-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="1de5e-109">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1de5e-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="1de5e-110">Добавление записей CNAME, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="1de5e-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="1de5e-111">Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="1de5e-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="1de5e-112">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="1de5e-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="1de5e-113">Когда вы добавите эти записи в сетевых решениях, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1de5e-113">After you add these records at Network Solutions, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="1de5e-p102">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1de5e-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="1de5e-117">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="1de5e-117">Add a TXT record for verification</span></span>
<span data-ttu-id="1de5e-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="1de5e-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="1de5e-p103">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="1de5e-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1de5e-p104">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="1de5e-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="1de5e-123">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 0:47)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="1de5e-123">Follow the steps below or [watch the video (start at 0:47)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="1de5e-p105">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Network Solutions по [этой ссылке](https://www.networksolutions.com/manage-it). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="1de5e-p105">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1de5e-126">Перед нажатием кнопки **Вход** сначала выберите пункт **Управление именами доменов** в раскрывающемся списке **Вход в:** .</span><span class="sxs-lookup"><span data-stu-id="1de5e-126">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Выберите Manage My Domain Names (Управление доменными именами) и войдите в систему Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="1de5e-128">Установите флажок для доменного имени, которое вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="1de5e-128">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Установите флажок для своего домена](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="1de5e-130">Выберите **изменить DNS**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-130">Select **Edit DNS**.</span></span>
    
    ![Выберите изменить DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="1de5e-132">Выберите **Управление расширенными записями DNS**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-132">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="1de5e-133">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="1de5e-133">(You may have to scroll down.)</span></span>
    
    ![Выберите Управление расширенными записями DNS](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="1de5e-135">Прокрутите список вниз до раздела **текст (записи TXT)** и выберите команду **изменить записи TXT**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-135">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Выберите команду Изменить записи TXT](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="1de5e-137">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="1de5e-137">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="1de5e-138">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="1de5e-138">**Host**</span></span>|<span data-ttu-id="1de5e-139">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="1de5e-139">**TTL**</span></span>|<span data-ttu-id="1de5e-140">**Text (Текст)**</span><span class="sxs-lookup"><span data-stu-id="1de5e-140">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="1de5e-141">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="1de5e-141">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="1de5e-142">3600</span><span class="sxs-lookup"><span data-stu-id="1de5e-142">3600</span></span>  <br/> |<span data-ttu-id="1de5e-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="1de5e-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="1de5e-144">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="1de5e-144">**Note:** This is an example.</span></span> <span data-ttu-id="1de5e-145">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="1de5e-145">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="1de5e-146">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="1de5e-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![Введите или вставьте значения в поля для новой записи](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="1de5e-148">Нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-148">Select **Continue**.</span></span>
    
    ![Нажмите кнопку продолжить.](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="1de5e-150">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-150">Select **Save Changes**.</span></span>
    
    ![Нажмите кнопку Сохранить изменения](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="1de5e-152">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="1de5e-152">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="1de5e-153">Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.</span><span class="sxs-lookup"><span data-stu-id="1de5e-153">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="1de5e-154">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="1de5e-154">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="1de5e-155">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="1de5e-155">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="1de5e-156">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="1de5e-156">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="1de5e-157">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="1de5e-157">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="1de5e-158">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-158">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="1de5e-p107">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1de5e-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="1de5e-162">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1de5e-162">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="1de5e-163"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="1de5e-163"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="1de5e-164">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 3:51)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="1de5e-164">Follow the steps below or [watch the video (start at 3:51)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="1de5e-p108">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Network Solutions по [этой ссылке](https://www.networksolutions.com/manage-it). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="1de5e-p108">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1de5e-167">Перед нажатием кнопки **Вход** сначала выберите пункт **Управление именами доменов** в раскрывающемся списке **Вход в:** .</span><span class="sxs-lookup"><span data-stu-id="1de5e-167">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Выберите Manage My Domain Names (Управление доменными именами) и войдите в систему Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="1de5e-169">Установите флажок для доменного имени, которое вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="1de5e-169">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Установите флажок для своего домена](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="1de5e-171">Выберите **изменить DNS**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-171">Select **Edit DNS**.</span></span>
    
    ![Выберите изменить DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="1de5e-173">Выберите **Управление расширенными записями DNS**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-173">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="1de5e-174">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="1de5e-174">(You may have to scroll down.)</span></span>
    
    ![Выберите Управление расширенными записями DNS](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="1de5e-176">Прокрутите список вниз до раздела **почтовые серверы (записи MX)** и выберите команду **изменить записи MX**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-176">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![Выберите Изменить записи MX](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="1de5e-178">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="1de5e-178">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="1de5e-179">**Priority**</span><span class="sxs-lookup"><span data-stu-id="1de5e-179">**Priority**</span></span>|<span data-ttu-id="1de5e-180">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="1de5e-180">**TTL**</span></span>|<span data-ttu-id="1de5e-181">**Mail Server (Почтовый сервер)**</span><span class="sxs-lookup"><span data-stu-id="1de5e-181">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="1de5e-182">10 </span><span class="sxs-lookup"><span data-stu-id="1de5e-182">10</span></span>  <br/> <span data-ttu-id="1de5e-183">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).   </span><span class="sxs-lookup"><span data-stu-id="1de5e-183">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="1de5e-184">3600</span><span class="sxs-lookup"><span data-stu-id="1de5e-184">3600</span></span>  <br/> | <span data-ttu-id="1de5e-185">*\<domain-key\>*  . mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="1de5e-185">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="1de5e-186">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="1de5e-186">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="1de5e-187">**Примечание:** Получение  *\<domain-key\>*  учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1de5e-187">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span> [<span data-ttu-id="1de5e-188">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="1de5e-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![Введите или вставьте значения в поля для новой записи](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="1de5e-190">Нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-190">Select **Continue**.</span></span>
    
    ![Нажмите кнопку продолжить.](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="1de5e-192">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-192">Select **Save Changes**.</span></span>
    
    ![Нажмите кнопку Сохранить изменения](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="1de5e-194">Если есть какие-либо другие записи MX, выделите каждую из них и нажмите **Delete** (Удалить).</span><span class="sxs-lookup"><span data-stu-id="1de5e-194">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="1de5e-196">Когда все будут выбраны, выберите **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-196">When they are all selected, select **Continue**.</span></span>
    
    ![Нажмите кнопку продолжить.](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="1de5e-198">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-198">Select **Save Changes**.</span></span>
    
    ![Нажмите кнопку Сохранить изменения](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="1de5e-200">Добавление записей CNAME, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="1de5e-200">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="1de5e-201"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="1de5e-201"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="1de5e-202">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 4:43)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="1de5e-202">Follow the steps below or [watch the video (start at 4:43)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="1de5e-p110">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Network Solutions по [этой ссылке](https://www.networksolutions.com/manage-it). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="1de5e-p110">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1de5e-205">Перед нажатием кнопки **Вход** сначала выберите пункт **Управление именами доменов** в раскрывающемся списке **Вход в:** .</span><span class="sxs-lookup"><span data-stu-id="1de5e-205">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Выберите Manage My Domain Names (Управление доменными именами) и войдите в систему Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="1de5e-207">Установите флажок для доменного имени, которое вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="1de5e-207">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Установите флажок для своего домена](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="1de5e-209">Выберите **изменить DNS**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-209">Select **Edit DNS**.</span></span>
    
    ![Выберите изменить DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="1de5e-211">Выберите **Управление расширенными записями DNS**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-211">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="1de5e-212">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="1de5e-212">(You may have to scroll down.)</span></span>
    
    ![Выберите Управление расширенными записями DNS](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="1de5e-214">Прокрутите список вниз до раздела **псевдонимы узлов (CNAME-записи)** , а затем выберите команду **изменить записи CNAME**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-214">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![Выберите Изменить записи CNAME в разделе Псевдонимы узлов](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="1de5e-216">В поля для четырех новых записей введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="1de5e-216">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="1de5e-217">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="1de5e-217">**Alias**</span></span>|<span data-ttu-id="1de5e-218">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="1de5e-218">**TTL**</span></span>|<span data-ttu-id="1de5e-219">**Refers to Host Name (Указывает на имя узла)**</span><span class="sxs-lookup"><span data-stu-id="1de5e-219">**Refers to Host Name**</span></span>|<span data-ttu-id="1de5e-220">**Other Host          (select the **Other Host** option button)**</span><span class="sxs-lookup"><span data-stu-id="1de5e-220">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1de5e-221">autodiscover</span><span class="sxs-lookup"><span data-stu-id="1de5e-221">autodiscover</span></span>  <br/> |<span data-ttu-id="1de5e-222">3600</span><span class="sxs-lookup"><span data-stu-id="1de5e-222">3600</span></span>  <br/> |<span data-ttu-id="1de5e-223">(Нет значения)</span><span class="sxs-lookup"><span data-stu-id="1de5e-223">(No setting)</span></span>  <br/> |<span data-ttu-id="1de5e-224">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="1de5e-224">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="1de5e-225">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="1de5e-225">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="1de5e-226">sip</span><span class="sxs-lookup"><span data-stu-id="1de5e-226">sip</span></span>  <br/> |<span data-ttu-id="1de5e-227">3600</span><span class="sxs-lookup"><span data-stu-id="1de5e-227">3600</span></span>  <br/> |<span data-ttu-id="1de5e-228">(Нет значения)</span><span class="sxs-lookup"><span data-stu-id="1de5e-228">(No setting)</span></span>  <br/> |<span data-ttu-id="1de5e-229">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1de5e-229">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1de5e-230">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="1de5e-230">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="1de5e-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1de5e-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="1de5e-232">3600</span><span class="sxs-lookup"><span data-stu-id="1de5e-232">3600</span></span>  <br/> |<span data-ttu-id="1de5e-233">(Нет значения)</span><span class="sxs-lookup"><span data-stu-id="1de5e-233">(No setting)</span></span>  <br/> |<span data-ttu-id="1de5e-234">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1de5e-234">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1de5e-235">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="1de5e-235">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="1de5e-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="1de5e-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="1de5e-237">3600</span><span class="sxs-lookup"><span data-stu-id="1de5e-237">3600</span></span>  <br/> |<span data-ttu-id="1de5e-238">(Нет значения)</span><span class="sxs-lookup"><span data-stu-id="1de5e-238">(No setting)</span></span>  <br/> |<span data-ttu-id="1de5e-239">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="1de5e-239">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="1de5e-240">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="1de5e-240">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="1de5e-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="1de5e-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="1de5e-242">3600</span><span class="sxs-lookup"><span data-stu-id="1de5e-242">3600</span></span>  <br/> |<span data-ttu-id="1de5e-243">(Нет значения)</span><span class="sxs-lookup"><span data-stu-id="1de5e-243">(No setting)</span></span>  <br/> |<span data-ttu-id="1de5e-244">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1de5e-244">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="1de5e-245">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="1de5e-245">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![Ввод или Вставка значений для новых записей](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="1de5e-247">После добавления всех необходимых записей CNAME нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-247">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Нажмите кнопку продолжить.](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="1de5e-249">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-249">Select **Save Changes**.</span></span>
    
    ![Нажмите кнопку Сохранить изменения](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="1de5e-251">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="1de5e-251">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="1de5e-252"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="1de5e-252"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="1de5e-253">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="1de5e-253">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="1de5e-254">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="1de5e-254">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="1de5e-255">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1de5e-255">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="1de5e-256">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь  *одну*  запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="1de5e-256">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="1de5e-257">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 5:35)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="1de5e-257">Follow the steps below or [watch the video (start at 5:35)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="1de5e-p112">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Network Solutions по [этой ссылке](https://www.networksolutions.com/manage-it). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="1de5e-p112">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1de5e-260">Перед нажатием кнопки **Вход** сначала выберите пункт **Управление именами доменов** в раскрывающемся списке **Вход в:** .</span><span class="sxs-lookup"><span data-stu-id="1de5e-260">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Выберите Manage My Domain Names (Управление доменными именами) и войдите в систему Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="1de5e-262">Установите флажок для доменного имени, которое вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="1de5e-262">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Установите флажок для своего домена](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="1de5e-264">Выберите **изменить DNS**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-264">Select **Edit DNS**.</span></span>
    
    ![Выберите изменить DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="1de5e-266">Выберите **Управление расширенными записями DNS**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-266">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="1de5e-267">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="1de5e-267">(You may have to scroll down.)</span></span>
    
    ![Выберите Управление расширенными записями DNS](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="1de5e-269">Прокрутите список вниз до раздела **текст (записи TXT)** и выберите команду **изменить записи TXT**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-269">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Выберите команду Изменить записи TXT в тексте.](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="1de5e-271">В поля для новой записи введите (или скопируйте и вставьте) указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="1de5e-271">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="1de5e-272">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="1de5e-272">**Host**</span></span>|<span data-ttu-id="1de5e-273">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="1de5e-273">**TTL**</span></span>|<span data-ttu-id="1de5e-274">**Text (Текст)**</span><span class="sxs-lookup"><span data-stu-id="1de5e-274">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="1de5e-275">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="1de5e-275">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="1de5e-276">3600</span><span class="sxs-lookup"><span data-stu-id="1de5e-276">3600</span></span>  <br/> |<span data-ttu-id="1de5e-277">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="1de5e-277">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="1de5e-278">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="1de5e-278">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![Ввод или Вставка значений для новой записи](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="1de5e-280">Нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-280">Select **Continue**.</span></span>
    
    ![Нажмите кнопку продолжить.](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="1de5e-282">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-282">Select **Save Changes**.</span></span>
    
    ![Нажмите кнопку Сохранить изменения](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="1de5e-284">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="1de5e-284">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="1de5e-285"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="1de5e-285"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="1de5e-286">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 6:18)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="1de5e-286">Follow the steps below or [watch the video (start at 6:18)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="1de5e-p113">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Network Solutions по [этой ссылке](https://www.networksolutions.com/manage-it). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="1de5e-p113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1de5e-289">Перед нажатием кнопки **Вход** сначала выберите пункт **Управление именами доменов** в раскрывающемся списке **Вход в:** .</span><span class="sxs-lookup"><span data-stu-id="1de5e-289">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Выберите Manage My Domain Names (Управление доменными именами) и войдите в систему Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="1de5e-291">Установите флажок для доменного имени, которое вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="1de5e-291">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Установите флажок для своего домена](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="1de5e-293">Выберите **изменить DNS**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-293">Select **Edit DNS**.</span></span>
    
    ![Выберите изменить DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="1de5e-295">Выберите **Управление расширенными записями DNS**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-295">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="1de5e-296">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="1de5e-296">(You may have to scroll down.)</span></span>
    
    ![Выберите Управление расширенными записями DNS](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="1de5e-298">Прокрутите вниз до раздела **служба (записи SRV)** , а затем выберите **изменить записи SRV**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-298">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![Выберите Изменить записи SRV в разделе Служба](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="1de5e-300">В поля для двух новых записей введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="1de5e-300">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="1de5e-301">(Выберите значения **Service** (Служба) и **Protocol** (Протокол) в раскрывающихся списках.)</span><span class="sxs-lookup"><span data-stu-id="1de5e-301">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="1de5e-302">**Service (Служба)**</span><span class="sxs-lookup"><span data-stu-id="1de5e-302">**Service**</span></span>|<span data-ttu-id="1de5e-303">**Protocol (Протокол)**</span><span class="sxs-lookup"><span data-stu-id="1de5e-303">**Protocol**</span></span>|<span data-ttu-id="1de5e-304">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="1de5e-304">**TTL**</span></span>|<span data-ttu-id="1de5e-305">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="1de5e-305">**Priority**</span></span>|<span data-ttu-id="1de5e-306">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="1de5e-306">**Weight**</span></span>|<span data-ttu-id="1de5e-307">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="1de5e-307">**Port**</span></span>|<span data-ttu-id="1de5e-308">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="1de5e-308">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1de5e-309">_sip</span><span class="sxs-lookup"><span data-stu-id="1de5e-309">_sip</span></span>  <br/> |<span data-ttu-id="1de5e-310">_tls</span><span class="sxs-lookup"><span data-stu-id="1de5e-310">_tls</span></span>  <br/> |<span data-ttu-id="1de5e-311">3600</span><span class="sxs-lookup"><span data-stu-id="1de5e-311">3600</span></span>  <br/> |<span data-ttu-id="1de5e-312">100</span><span class="sxs-lookup"><span data-stu-id="1de5e-312">100</span></span>  <br/> |<span data-ttu-id="1de5e-313">1,1</span><span class="sxs-lookup"><span data-stu-id="1de5e-313">1</span></span>  <br/> |<span data-ttu-id="1de5e-314">443</span><span class="sxs-lookup"><span data-stu-id="1de5e-314">443</span></span>  <br/> |<span data-ttu-id="1de5e-315">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1de5e-315">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1de5e-316">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="1de5e-316">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="1de5e-317">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="1de5e-317">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="1de5e-318">_tcp</span><span class="sxs-lookup"><span data-stu-id="1de5e-318">_tcp</span></span>  <br/> |<span data-ttu-id="1de5e-319">3600</span><span class="sxs-lookup"><span data-stu-id="1de5e-319">3600</span></span>  <br/> |<span data-ttu-id="1de5e-320">100</span><span class="sxs-lookup"><span data-stu-id="1de5e-320">100</span></span>  <br/> |<span data-ttu-id="1de5e-321">1,1</span><span class="sxs-lookup"><span data-stu-id="1de5e-321">1</span></span>  <br/> |<span data-ttu-id="1de5e-322">5061</span><span class="sxs-lookup"><span data-stu-id="1de5e-322">5061</span></span>  <br/> |<span data-ttu-id="1de5e-323">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1de5e-323">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="1de5e-324">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="1de5e-324">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![Ввод или Вставка значений для новых записей](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="1de5e-326">Нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-326">Select **Continue**.</span></span>
    
    ![Нажмите кнопку продолжить.](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="1de5e-328">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="1de5e-328">Select **Save Changes**.</span></span>
    
    ![Нажмите кнопку Сохранить изменения](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="1de5e-p114">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1de5e-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
