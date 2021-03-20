---
title: Создание записей DNS в сетевых решениях для Microsoft
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
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб в Сетевые решения для Microsoft.
ms.openlocfilehash: f25e21037695c99489adc9038bf70629a103ec7a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910142"
---
# <a name="create-dns-records-at-network-solutions-for-microsoft"></a><span data-ttu-id="8ba95-103">Создание записей DNS в сетевых решениях для Microsoft</span><span class="sxs-lookup"><span data-stu-id="8ba95-103">Create DNS records at Network Solutions for Microsoft</span></span>

 <span data-ttu-id="8ba95-104">**[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="8ba95-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="8ba95-105">Если ваш поставщик услуг размещения DNS  Network Solutions, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="8ba95-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="8ba95-106">Ниже перечислены основные записи, которые нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="8ba95-106">These are the main records to add.</span></span> <span data-ttu-id="8ba95-107">Воспользуйтесь инструкциями ниже или [посмотрите видеоролик](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="8ba95-107">Follow the steps below or [watch the video](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span> 
  
- [<span data-ttu-id="8ba95-108">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="8ba95-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="8ba95-109">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8ba95-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="8ba95-110">Добавление записей CNAME, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8ba95-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="8ba95-111">Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="8ba95-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="8ba95-112">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8ba95-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="8ba95-113">После добавления этих записей в Сетевые решения домен будет настроен на работу с службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8ba95-113">After you add these records at Network Solutions, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="8ba95-p102">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8ba95-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="8ba95-117">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="8ba95-117">Add a TXT record for verification</span></span>
<span data-ttu-id="8ba95-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="8ba95-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="8ba95-p103">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="8ba95-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8ba95-p104">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="8ba95-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="8ba95-123">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 0:47)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="8ba95-123">Follow the steps below or [watch the video (start at 0:47)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="8ba95-p105">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Network Solutions по [этой ссылке](https://www.networksolutions.com/manage-it). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="8ba95-p105">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8ba95-126">Прежде чем выбрать кнопку **Входа,** сначала выберите **Управление** именами доменов в **журнале:** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="8ba95-126">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Выберите Manage My Domain Names (Управление доменными именами) и войдите в систему Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="8ba95-128">Установите флажок для доменного имени, которое вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="8ba95-128">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Установите флажок для своего домена](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="8ba95-130">Выберите **изменить DNS**.</span><span class="sxs-lookup"><span data-stu-id="8ba95-130">Select **Edit DNS**.</span></span>
    
    ![Выберите изменение DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="8ba95-132">Выберите **Управление расширенными записями DNS.**</span><span class="sxs-lookup"><span data-stu-id="8ba95-132">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="8ba95-133">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="8ba95-133">(You may have to scroll down.)</span></span>
    
    ![Выберите управление расширенными записями DNS](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="8ba95-135">Прокрутите вниз **в раздел Text (TXT Records)** и выберите **Изменить записи TXT**.</span><span class="sxs-lookup"><span data-stu-id="8ba95-135">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Выберите Изменение записей TXT](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="8ba95-137">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="8ba95-137">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="8ba95-138">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="8ba95-138">**Host**</span></span>|<span data-ttu-id="8ba95-139">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="8ba95-139">**TTL**</span></span>|<span data-ttu-id="8ba95-140">**Text (Текст)**</span><span class="sxs-lookup"><span data-stu-id="8ba95-140">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="8ba95-141">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="8ba95-141">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="8ba95-142">3600</span><span class="sxs-lookup"><span data-stu-id="8ba95-142">3600</span></span>  <br/> |<span data-ttu-id="8ba95-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="8ba95-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="8ba95-144">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="8ba95-144">**Note:** This is an example.</span></span> <span data-ttu-id="8ba95-145">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="8ba95-145">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="8ba95-146">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="8ba95-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![Введите или введите значения в полях для новой записи](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="8ba95-148">Выберите **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="8ba95-148">Select **Continue**.</span></span>
    
    ![Выберите Продолжить](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="8ba95-150">Выберите **Сохранить изменения.**</span><span class="sxs-lookup"><span data-stu-id="8ba95-150">Select **Save Changes**.</span></span>
    
    ![Выберите сохранить изменения](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="8ba95-152">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="8ba95-152">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="8ba95-153">Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.</span><span class="sxs-lookup"><span data-stu-id="8ba95-153">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="8ba95-154">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="8ba95-154">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="8ba95-155">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="8ba95-155">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="8ba95-156">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="8ba95-156">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="8ba95-157">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="8ba95-157">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="8ba95-158">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="8ba95-158">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="8ba95-p107">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8ba95-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="8ba95-162">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8ba95-162">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="8ba95-163"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="8ba95-163"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="8ba95-164">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 3:51)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="8ba95-164">Follow the steps below or [watch the video (start at 3:51)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="8ba95-p108">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Network Solutions по [этой ссылке](https://www.networksolutions.com/manage-it). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="8ba95-p108">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8ba95-167">Прежде чем выбрать кнопку **Входа,** сначала выберите **Управление** именами доменов в **журнале:** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="8ba95-167">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Выберите Manage My Domain Names (Управление доменными именами) и войдите в систему Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="8ba95-169">Установите флажок для доменного имени, которое вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="8ba95-169">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Установите флажок для своего домена](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="8ba95-171">Выберите **изменить DNS**.</span><span class="sxs-lookup"><span data-stu-id="8ba95-171">Select **Edit DNS**.</span></span>
    
    ![Выберите изменение DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="8ba95-173">Выберите **Управление расширенными записями DNS.**</span><span class="sxs-lookup"><span data-stu-id="8ba95-173">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="8ba95-174">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="8ba95-174">(You may have to scroll down.)</span></span>
    
    ![Выберите управление расширенными записями DNS](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="8ba95-176">Прокрутите вниз в раздел **Mail Servers (MX Records),** а затем выберите **Изменить записи MX**.</span><span class="sxs-lookup"><span data-stu-id="8ba95-176">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![Выберите Изменение записей MX](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="8ba95-178">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="8ba95-178">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="8ba95-179">**Priority**</span><span class="sxs-lookup"><span data-stu-id="8ba95-179">**Priority**</span></span>|<span data-ttu-id="8ba95-180">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="8ba95-180">**TTL**</span></span>|<span data-ttu-id="8ba95-181">**Mail Server (Почтовый сервер)**</span><span class="sxs-lookup"><span data-stu-id="8ba95-181">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="8ba95-182">10 </span><span class="sxs-lookup"><span data-stu-id="8ba95-182">10</span></span>  <br/> <span data-ttu-id="8ba95-183">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](../setup/domains-faq.yml).   </span><span class="sxs-lookup"><span data-stu-id="8ba95-183">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |<span data-ttu-id="8ba95-184">3600</span><span class="sxs-lookup"><span data-stu-id="8ba95-184">3600</span></span>  <br/> | <span data-ttu-id="8ba95-185">*\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="8ba95-185">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="8ba95-186">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="8ba95-186">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="8ba95-187">**Примечание:** Получите вашу  *\<domain-key\>*  учетную запись Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8ba95-187">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span> [<span data-ttu-id="8ba95-188">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="8ba95-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![Введите или введите значения в полях для новой записи](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="8ba95-190">Выберите **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="8ba95-190">Select **Continue**.</span></span>
    
    ![Выберите Продолжить](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="8ba95-192">Выберите **Сохранить изменения.**</span><span class="sxs-lookup"><span data-stu-id="8ba95-192">Select **Save Changes**.</span></span>
    
    ![Выберите сохранить изменения](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="8ba95-194">Если есть какие-либо другие записи MX, выделите каждую из них и нажмите **Delete** (Удалить).</span><span class="sxs-lookup"><span data-stu-id="8ba95-194">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="8ba95-196">Когда все они выбраны, выберите **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="8ba95-196">When they are all selected, select **Continue**.</span></span>
    
    ![Выберите Продолжить](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="8ba95-198">Выберите **Сохранить изменения.**</span><span class="sxs-lookup"><span data-stu-id="8ba95-198">Select **Save Changes**.</span></span>
    
    ![Выберите сохранить изменения](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="8ba95-200">Добавление записей CNAME, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8ba95-200">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="8ba95-201"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="8ba95-201"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="8ba95-202">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 4:43)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="8ba95-202">Follow the steps below or [watch the video (start at 4:43)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="8ba95-p110">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Network Solutions по [этой ссылке](https://www.networksolutions.com/manage-it). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="8ba95-p110">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8ba95-205">Прежде чем выбрать кнопку **Входа,** сначала выберите **Управление** именами доменов в **журнале:** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="8ba95-205">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Выберите Manage My Domain Names (Управление доменными именами) и войдите в систему Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="8ba95-207">Установите флажок для доменного имени, которое вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="8ba95-207">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Установите флажок для своего домена](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="8ba95-209">Выберите **изменить DNS**.</span><span class="sxs-lookup"><span data-stu-id="8ba95-209">Select **Edit DNS**.</span></span>
    
    ![Выберите изменение DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="8ba95-211">Выберите **Управление расширенными записями DNS.**</span><span class="sxs-lookup"><span data-stu-id="8ba95-211">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="8ba95-212">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="8ba95-212">(You may have to scroll down.)</span></span>
    
    ![Выберите управление расширенными записями DNS](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="8ba95-214">Прокрутите вниз в **раздел Host Aliases (CNAME Records),** а затем выберите **Изменить записи CNAME.**</span><span class="sxs-lookup"><span data-stu-id="8ba95-214">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![Выберите Изменение записей CNAME под псевдонимами host](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="8ba95-216">В поля для четырех новых записей введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="8ba95-216">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="8ba95-217">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="8ba95-217">**Alias**</span></span>|<span data-ttu-id="8ba95-218">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="8ba95-218">**TTL**</span></span>|<span data-ttu-id="8ba95-219">**Refers to Host Name (Указывает на имя узла)**</span><span class="sxs-lookup"><span data-stu-id="8ba95-219">**Refers to Host Name**</span></span>|<span data-ttu-id="8ba95-220">**Other Host          (select the **Other Host** option button)**</span><span class="sxs-lookup"><span data-stu-id="8ba95-220">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8ba95-221">autodiscover</span><span class="sxs-lookup"><span data-stu-id="8ba95-221">autodiscover</span></span>  <br/> |<span data-ttu-id="8ba95-222">3600</span><span class="sxs-lookup"><span data-stu-id="8ba95-222">3600</span></span>  <br/> |<span data-ttu-id="8ba95-223">(Нет значения)</span><span class="sxs-lookup"><span data-stu-id="8ba95-223">(No setting)</span></span>  <br/> |<span data-ttu-id="8ba95-224">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="8ba95-224">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="8ba95-225">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="8ba95-225">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="8ba95-226">sip</span><span class="sxs-lookup"><span data-stu-id="8ba95-226">sip</span></span>  <br/> |<span data-ttu-id="8ba95-227">3600</span><span class="sxs-lookup"><span data-stu-id="8ba95-227">3600</span></span>  <br/> |<span data-ttu-id="8ba95-228">(Нет значения)</span><span class="sxs-lookup"><span data-stu-id="8ba95-228">(No setting)</span></span>  <br/> |<span data-ttu-id="8ba95-229">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8ba95-229">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="8ba95-230">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="8ba95-230">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="8ba95-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8ba95-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="8ba95-232">3600</span><span class="sxs-lookup"><span data-stu-id="8ba95-232">3600</span></span>  <br/> |<span data-ttu-id="8ba95-233">(Нет значения)</span><span class="sxs-lookup"><span data-stu-id="8ba95-233">(No setting)</span></span>  <br/> |<span data-ttu-id="8ba95-234">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8ba95-234">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="8ba95-235">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="8ba95-235">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="8ba95-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="8ba95-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="8ba95-237">3600</span><span class="sxs-lookup"><span data-stu-id="8ba95-237">3600</span></span>  <br/> |<span data-ttu-id="8ba95-238">(Нет значения)</span><span class="sxs-lookup"><span data-stu-id="8ba95-238">(No setting)</span></span>  <br/> |<span data-ttu-id="8ba95-239">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="8ba95-239">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="8ba95-240">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="8ba95-240">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="8ba95-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="8ba95-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="8ba95-242">3600</span><span class="sxs-lookup"><span data-stu-id="8ba95-242">3600</span></span>  <br/> |<span data-ttu-id="8ba95-243">(Нет значения)</span><span class="sxs-lookup"><span data-stu-id="8ba95-243">(No setting)</span></span>  <br/> |<span data-ttu-id="8ba95-244">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8ba95-244">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="8ba95-245">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="8ba95-245">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![Введите или введите значения для новых записей](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="8ba95-247">При добавлении всех необходимых записей CNAME выберите **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="8ba95-247">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Выберите Продолжить](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="8ba95-249">Выберите **Сохранить изменения.**</span><span class="sxs-lookup"><span data-stu-id="8ba95-249">Select **Save Changes**.</span></span>
    
    ![Выберите сохранить изменения](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="8ba95-251">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="8ba95-251">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="8ba95-252"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="8ba95-252"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ba95-253">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="8ba95-253">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="8ba95-254">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="8ba95-254">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="8ba95-255">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8ba95-255">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="8ba95-256">Вместо этого добавьте необходимые значения Microsoft в текущую  запись, чтобы у вас была одна запись SPF, которая включает оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="8ba95-256">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="8ba95-257">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 5:35)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="8ba95-257">Follow the steps below or [watch the video (start at 5:35)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="8ba95-p112">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Network Solutions по [этой ссылке](https://www.networksolutions.com/manage-it). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="8ba95-p112">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8ba95-260">Прежде чем выбрать кнопку **Входа,** сначала выберите **Управление** именами доменов в **журнале:** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="8ba95-260">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Выберите Manage My Domain Names (Управление доменными именами) и войдите в систему Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="8ba95-262">Установите флажок для доменного имени, которое вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="8ba95-262">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Установите флажок для своего домена](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="8ba95-264">Выберите **изменить DNS**.</span><span class="sxs-lookup"><span data-stu-id="8ba95-264">Select **Edit DNS**.</span></span>
    
    ![Выберите изменение DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="8ba95-266">Выберите **Управление расширенными записями DNS.**</span><span class="sxs-lookup"><span data-stu-id="8ba95-266">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="8ba95-267">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="8ba95-267">(You may have to scroll down.)</span></span>
    
    ![Выберите управление расширенными записями DNS](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="8ba95-269">Прокрутите вниз **в раздел Text (TXT Records)** и выберите **Изменить записи TXT**.</span><span class="sxs-lookup"><span data-stu-id="8ba95-269">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Выберите Изменение записей TXT в тексте](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="8ba95-271">В поля для новой записи введите (или скопируйте и вставьте) указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="8ba95-271">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="8ba95-272">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="8ba95-272">**Host**</span></span>|<span data-ttu-id="8ba95-273">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="8ba95-273">**TTL**</span></span>|<span data-ttu-id="8ba95-274">**Text (Текст)**</span><span class="sxs-lookup"><span data-stu-id="8ba95-274">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="8ba95-275">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="8ba95-275">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="8ba95-276">3600</span><span class="sxs-lookup"><span data-stu-id="8ba95-276">3600</span></span>  <br/> |<span data-ttu-id="8ba95-277">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="8ba95-277">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="8ba95-278">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="8ba95-278">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![Введите или введите значения для новой записи](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="8ba95-280">Выберите **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="8ba95-280">Select **Continue**.</span></span>
    
    ![Выберите Продолжить](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="8ba95-282">Выберите **Сохранить изменения.**</span><span class="sxs-lookup"><span data-stu-id="8ba95-282">Select **Save Changes**.</span></span>
    
    ![Выберите сохранить изменения](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="8ba95-284">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8ba95-284">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="8ba95-285"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="8ba95-285"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="8ba95-286">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 6:18)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="8ba95-286">Follow the steps below or [watch the video (start at 6:18)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="8ba95-p113">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Network Solutions по [этой ссылке](https://www.networksolutions.com/manage-it). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="8ba95-p113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8ba95-289">Прежде чем выбрать кнопку **Входа,** сначала выберите **Управление** именами доменов в **журнале:** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="8ba95-289">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Выберите Manage My Domain Names (Управление доменными именами) и войдите в систему Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="8ba95-291">Установите флажок для доменного имени, которое вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="8ba95-291">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Установите флажок для своего домена](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="8ba95-293">Выберите **изменить DNS**.</span><span class="sxs-lookup"><span data-stu-id="8ba95-293">Select **Edit DNS**.</span></span>
    
    ![Выберите изменение DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="8ba95-295">Выберите **Управление расширенными записями DNS.**</span><span class="sxs-lookup"><span data-stu-id="8ba95-295">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="8ba95-296">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="8ba95-296">(You may have to scroll down.)</span></span>
    
    ![Выберите управление расширенными записями DNS](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="8ba95-298">Прокрутите **вниз в раздел Service (SRV Records),** а затем выберите Изменить **записи SRV**.</span><span class="sxs-lookup"><span data-stu-id="8ba95-298">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![Выберите Изменение записей SRV в службе](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="8ba95-300">В поля для двух новых записей введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="8ba95-300">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="8ba95-301">(Выберите значения **Service** (Служба) и **Protocol** (Протокол) в раскрывающихся списках.)</span><span class="sxs-lookup"><span data-stu-id="8ba95-301">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="8ba95-302">**Service (Служба)**</span><span class="sxs-lookup"><span data-stu-id="8ba95-302">**Service**</span></span>|<span data-ttu-id="8ba95-303">**Protocol (Протокол)**</span><span class="sxs-lookup"><span data-stu-id="8ba95-303">**Protocol**</span></span>|<span data-ttu-id="8ba95-304">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="8ba95-304">**TTL**</span></span>|<span data-ttu-id="8ba95-305">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="8ba95-305">**Priority**</span></span>|<span data-ttu-id="8ba95-306">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="8ba95-306">**Weight**</span></span>|<span data-ttu-id="8ba95-307">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="8ba95-307">**Port**</span></span>|<span data-ttu-id="8ba95-308">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="8ba95-308">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8ba95-309">_sip</span><span class="sxs-lookup"><span data-stu-id="8ba95-309">_sip</span></span>  <br/> |<span data-ttu-id="8ba95-310">_tls</span><span class="sxs-lookup"><span data-stu-id="8ba95-310">_tls</span></span>  <br/> |<span data-ttu-id="8ba95-311">3600</span><span class="sxs-lookup"><span data-stu-id="8ba95-311">3600</span></span>  <br/> |<span data-ttu-id="8ba95-312">100</span><span class="sxs-lookup"><span data-stu-id="8ba95-312">100</span></span>  <br/> |<span data-ttu-id="8ba95-313">1</span><span class="sxs-lookup"><span data-stu-id="8ba95-313">1</span></span>  <br/> |<span data-ttu-id="8ba95-314">443</span><span class="sxs-lookup"><span data-stu-id="8ba95-314">443</span></span>  <br/> |<span data-ttu-id="8ba95-315">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8ba95-315">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="8ba95-316">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="8ba95-316">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="8ba95-317">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="8ba95-317">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="8ba95-318">_tcp</span><span class="sxs-lookup"><span data-stu-id="8ba95-318">_tcp</span></span>  <br/> |<span data-ttu-id="8ba95-319">3600</span><span class="sxs-lookup"><span data-stu-id="8ba95-319">3600</span></span>  <br/> |<span data-ttu-id="8ba95-320">100</span><span class="sxs-lookup"><span data-stu-id="8ba95-320">100</span></span>  <br/> |<span data-ttu-id="8ba95-321">1</span><span class="sxs-lookup"><span data-stu-id="8ba95-321">1</span></span>  <br/> |<span data-ttu-id="8ba95-322">5061</span><span class="sxs-lookup"><span data-stu-id="8ba95-322">5061</span></span>  <br/> |<span data-ttu-id="8ba95-323">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8ba95-323">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="8ba95-324">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="8ba95-324">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![Введите или введите значения для новых записей](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="8ba95-326">Выберите **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="8ba95-326">Select **Continue**.</span></span>
    
    ![Выберите Продолжить](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="8ba95-328">Выберите **Сохранить изменения.**</span><span class="sxs-lookup"><span data-stu-id="8ba95-328">Select **Save Changes**.</span></span>
    
    ![Выберите сохранить изменения](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="8ba95-p114">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8ba95-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
