---
title: Создание записей DNS для Office 365 на сайте Register.com
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу Register.com для Office 365.
ms.openlocfilehash: 0210c03a48112d9cc517ae15f879db3b40eb8c94
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2020
ms.locfileid: "42354140"
---
# <a name="create-dns-records-at-registercom-for-office-365"></a><span data-ttu-id="b4982-103">Создание записей DNS для Office 365 на сайте Register.com</span><span class="sxs-lookup"><span data-stu-id="b4982-103">Create DNS records at Register.com for Office 365</span></span>

 <span data-ttu-id="b4982-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="b4982-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b4982-105">Если ваш поставщик услуг размещения DNS  Register.com, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="b4982-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="b4982-106">Ниже перечислены основные записи, которые нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="b4982-106">These are the main records to add.</span></span> <span data-ttu-id="b4982-107">Воспользуйтесь инструкциями ниже или [посмотрите видеоролик](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="b4982-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
- [<span data-ttu-id="b4982-108">Добавление записи TXT на сайте Register.com для подтверждения владения доменом</span><span class="sxs-lookup"><span data-stu-id="b4982-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="b4982-109">Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="b4982-109">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="b4982-110">Добавление записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="b4982-110">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="b4982-111">Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="b4982-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="b4982-112">Добавление двух записей SRV, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="b4982-112">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="b4982-113">Когда вы добавите эти записи на сайте Register.com, ваш домен будет настроен для работы со службами Office 365.</span><span class="sxs-lookup"><span data-stu-id="b4982-113">After you add these records at Register.com, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="b4982-114">Дополнительные сведения о веб-хостинге и DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="b4982-114">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b4982-p102">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b4982-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="b4982-118">Добавление записи TXT на сайте Register.com для подтверждения владения доменом</span><span class="sxs-lookup"><span data-stu-id="b4982-118">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="b4982-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="b4982-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="b4982-p103">Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="b4982-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b4982-p104">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="b4982-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="b4982-124">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="b4982-124">Follow the steps below or [watch the video (start at 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b4982-125">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register.com по [этой ссылке](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="b4982-125">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="b4982-126">Сперва вам потребуется войти в систему.</span><span class="sxs-lookup"><span data-stu-id="b4982-126">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="b4982-127">Выберите раздел **Домены**.</span><span class="sxs-lookup"><span data-stu-id="b4982-127">Select **Domains**.</span></span>
    
3. <span data-ttu-id="b4982-128">Выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="b4982-128">Select **Manage**.</span></span>
    
4. <span data-ttu-id="b4982-129">Найдите строку, содержащую имя домена, который требуется изменить; затем в этой строке выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="b4982-129">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="b4982-130">Прокрутите окно вниз до раздела **Дополнительные технические параметры** и выберите команду **изменить записи TXT (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="b4982-130">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="b4982-131">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b4982-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="b4982-132">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="b4982-132">**Host Name**</span></span> <br/> |<span data-ttu-id="b4982-133">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="b4982-133">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="b4982-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b4982-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="b4982-135">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="b4982-135">**Note:** This is an example.</span></span> <span data-ttu-id="b4982-136">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="b4982-136">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="b4982-137">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="b4982-137">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="b4982-138">Нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="b4982-138">Select **Continue**.</span></span>
    
8. <span data-ttu-id="b4982-139">На следующей странице нажмите кнопку **продолжить** еще раз, чтобы подтвердить изменения.</span><span class="sxs-lookup"><span data-stu-id="b4982-139">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="b4982-140">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="b4982-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b4982-141">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Office 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="b4982-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="b4982-142">Если Office 365 обнаружит правильную запись TXT, это значит, что домен проверен.</span><span class="sxs-lookup"><span data-stu-id="b4982-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b4982-143">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="b4982-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="b4982-144">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="b4982-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="b4982-145">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="b4982-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="b4982-146">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="b4982-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b4982-p107">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b4982-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="b4982-150">Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="b4982-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="b4982-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="b4982-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="b4982-152">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="b4982-152">Follow the steps below or [watch the video (start at 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b4982-153">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register.com по [этой ссылке](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="b4982-153">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="b4982-154">Сперва вам потребуется войти в систему.</span><span class="sxs-lookup"><span data-stu-id="b4982-154">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="b4982-155">Выберите раздел **Домены**.</span><span class="sxs-lookup"><span data-stu-id="b4982-155">Select **Domains**.</span></span>
    
3. <span data-ttu-id="b4982-156">Выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="b4982-156">Select **Manage**.</span></span>
    
4. <span data-ttu-id="b4982-157">Найдите строку, содержащую имя домена, который требуется изменить; затем в этой строке выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="b4982-157">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="b4982-158">Перейдите к разделу **Дополнительные технические параметры** , а затем выберите **изменить записи почтового обменника**.</span><span class="sxs-lookup"><span data-stu-id="b4982-158">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![Выберите Изменить записи почтового обменника](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="b4982-160">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="b4982-160">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="b4982-161">В раскрывающемся списке выберите значение **Priority (приоритет** ).</span><span class="sxs-lookup"><span data-stu-id="b4982-161">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="b4982-162">\*\*\*\*Host Name\*\* (Имя узла)\*\*</span><span class="sxs-lookup"><span data-stu-id="b4982-162">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="b4982-163">\*\*\*\*Priority\*\* (Приоритет)\*\*</span><span class="sxs-lookup"><span data-stu-id="b4982-163">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="b4982-164">\*\*\*\*Mail Server\*\* (Почтовый сервер)\*\*</span><span class="sxs-lookup"><span data-stu-id="b4982-164">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="b4982-165">Высокая</span><span class="sxs-lookup"><span data-stu-id="b4982-165">High</span></span>  <br/> <span data-ttu-id="b4982-166">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="b4982-166">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="b4982-167">*\<ключ_домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b4982-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="b4982-168">**Примечание.**  Получите свой \<*ключ-домена*\> из учетной записи портала Office 365.</span><span class="sxs-lookup"><span data-stu-id="b4982-168">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> <br> [<span data-ttu-id="b4982-169">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="b4982-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Скопируйте и вставьте значение из таблицы](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="b4982-171">Если уже указаны какие-либо другие записи MX, выделите каждую из них и удалите.</span><span class="sxs-lookup"><span data-stu-id="b4982-171">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="b4982-173">Нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="b4982-173">Select **Continue**.</span></span>
    
    ![Нажмите кнопку продолжить.](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="b4982-175">На следующей странице нажмите кнопку **продолжить** еще раз, чтобы подтвердить изменения и сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="b4982-175">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Нажмите кнопку продолжить.](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="b4982-177">Добавление записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="b4982-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="b4982-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="b4982-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="b4982-179">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="b4982-179">Follow the steps below or [watch the video (start at 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b4982-180">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register.com по [этой ссылке](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="b4982-180">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="b4982-181">Сперва вам потребуется войти в систему.</span><span class="sxs-lookup"><span data-stu-id="b4982-181">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="b4982-182">Выберите раздел **Домены**.</span><span class="sxs-lookup"><span data-stu-id="b4982-182">Select **Domains**.</span></span>
    
3. <span data-ttu-id="b4982-183">Выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="b4982-183">Select **Manage**.</span></span>
    
4. <span data-ttu-id="b4982-184">Найдите строку, содержащую имя домена, который требуется изменить; затем в этой строке выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="b4982-184">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="b4982-185">Перейдите к разделу **Дополнительные технические параметры** , а затем выберите команду **изменить записи псевдонимов домена**.</span><span class="sxs-lookup"><span data-stu-id="b4982-185">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![Выберите пункт "изменить записи псевдонимов домена"](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="b4982-187">Выберите **добавить дополнительные псевдонимы доменов**.</span><span class="sxs-lookup"><span data-stu-id="b4982-187">Select **Add more domain aliases**.</span></span>
    
    ![Выберите Добавить другие псевдонимы доменов](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="b4982-189">Добавьте необходимые записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="b4982-189">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="b4982-190">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="b4982-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="b4982-191">\*\*\*\*Первое поле (без подписи)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b4982-191">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="b4982-192">\*\*\*\*Points to\*\* (Указывает на)\*\*</span><span class="sxs-lookup"><span data-stu-id="b4982-192">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="b4982-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="b4982-193">autodiscover</span></span>  <br/> |<span data-ttu-id="b4982-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b4982-194">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="b4982-195">sip</span><span class="sxs-lookup"><span data-stu-id="b4982-195">sip</span></span>  <br/> |<span data-ttu-id="b4982-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b4982-196">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="b4982-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b4982-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b4982-198">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b4982-198">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="b4982-199">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b4982-199">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b4982-200">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="b4982-200">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="b4982-201">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b4982-201">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b4982-202">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b4982-202">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![Копирование и вставка значений DNS из таблицы](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="b4982-204">После добавления всех необходимых записей CNAME нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="b4982-204">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Нажмите кнопку продолжить.](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="b4982-206">На следующей странице нажмите кнопку **продолжить** еще раз, чтобы подтвердить изменения и сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="b4982-206">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Нажмите кнопку продолжить.](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b4982-208">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="b4982-208">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="b4982-209"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="b4982-209"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4982-210">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="b4982-210">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="b4982-211">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="b4982-211">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="b4982-212">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="b4982-212">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="b4982-213">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="b4982-213">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="b4982-214">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="b4982-214">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b4982-215">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register.com по [этой ссылке](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="b4982-215">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="b4982-216">Сперва вам потребуется войти в систему.</span><span class="sxs-lookup"><span data-stu-id="b4982-216">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="b4982-217">Выберите раздел **Домены**.</span><span class="sxs-lookup"><span data-stu-id="b4982-217">Select **Domains**.</span></span>
    
3. <span data-ttu-id="b4982-218">Выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="b4982-218">Select **Manage**.</span></span>
    
4. <span data-ttu-id="b4982-219">Найдите строку, содержащую имя домена, который требуется изменить; затем в этой строке выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="b4982-219">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="b4982-220">Перейдите к разделу **Дополнительные технические параметры** , а затем выберите команду **изменить записи TXT (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="b4982-220">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![Выберите команду Изменить записи TXT (SPF)](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="b4982-222">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="b4982-222">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="b4982-223">\*\*\*\*Host Name\*\* (Имя узла)\*\*</span><span class="sxs-lookup"><span data-stu-id="b4982-223">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="b4982-224">\*\*\*\*TXT Record\*\* (Запись TXT)\*\*</span><span class="sxs-lookup"><span data-stu-id="b4982-224">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="b4982-225">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="b4982-225">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="b4982-226">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="b4982-226">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![Скопируйте и вставьте значения из таблицы](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="b4982-228">Нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="b4982-228">Select **Continue**.</span></span>
    
    ![Нажмите кнопку продолжить.](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="b4982-230">На следующей странице нажмите кнопку **продолжить** еще раз, чтобы подтвердить изменения и сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="b4982-230">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Нажмите кнопку продолжить.](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="b4982-232">Добавление двух записей SRV, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="b4982-232">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="b4982-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="b4982-233"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="b4982-234">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="b4982-234">Follow the steps below or [watch the video (start at 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b4982-p112">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register.com по [этой ссылке](https://www.register.com/myaccount/). Сперва вам потребуется войти в систему.</span><span class="sxs-lookup"><span data-stu-id="b4982-p112">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="b4982-237">Выберите раздел **Домены**.</span><span class="sxs-lookup"><span data-stu-id="b4982-237">Select **Domains**.</span></span>
    
3. <span data-ttu-id="b4982-238">Выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="b4982-238">Select **Manage**.</span></span>
    
4. <span data-ttu-id="b4982-239">Найдите строку, содержащую имя домена, который требуется изменить; затем в этой строке выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="b4982-239">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="b4982-240">Перейдите к разделу **Дополнительные технические параметры** , а затем выберите **изменить записи SRV**.</span><span class="sxs-lookup"><span data-stu-id="b4982-240">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![Выберите Изменить записи SRV](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="b4982-242">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="b4982-242">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="b4982-243">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="b4982-243">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="b4982-244">В раскрывающемся списке выберите значение **Priority (приоритет** ).</span><span class="sxs-lookup"><span data-stu-id="b4982-244">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="b4982-245">\*\*\*\*Service\*\* (Служба)\*\*</span><span class="sxs-lookup"><span data-stu-id="b4982-245">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="b4982-246">\*\*\*\*Proto\*\* (Протокол)\*\*</span><span class="sxs-lookup"><span data-stu-id="b4982-246">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="b4982-247">\*\*\*\*Name\*\* (Имя)\*\*</span><span class="sxs-lookup"><span data-stu-id="b4982-247">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="b4982-248">\*\*\*\*Priority\*\* (Приоритет)\*\*</span><span class="sxs-lookup"><span data-stu-id="b4982-248">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="b4982-249">\*\*\*\*Weight\*\* (Вес)\*\*</span><span class="sxs-lookup"><span data-stu-id="b4982-249">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="b4982-250">\*\*\*\*Port\*\* (Порт)\*\*</span><span class="sxs-lookup"><span data-stu-id="b4982-250">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="b4982-251">\*\*\*\*Target\*\* (Целевое значение)\*\*</span><span class="sxs-lookup"><span data-stu-id="b4982-251">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b4982-252">_sip</span><span class="sxs-lookup"><span data-stu-id="b4982-252">_sip</span></span>  <br/> |<span data-ttu-id="b4982-253">_tls</span><span class="sxs-lookup"><span data-stu-id="b4982-253">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="b4982-254">High (Высокий)</span><span class="sxs-lookup"><span data-stu-id="b4982-254">High</span></span>  <br/> |<span data-ttu-id="b4982-255">1,1</span><span class="sxs-lookup"><span data-stu-id="b4982-255">1</span></span>  <br/> |<span data-ttu-id="b4982-256">443</span><span class="sxs-lookup"><span data-stu-id="b4982-256">443</span></span>  <br/> |<span data-ttu-id="b4982-257">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b4982-257">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="b4982-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="b4982-258">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="b4982-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="b4982-259">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="b4982-260">High (Высокий)</span><span class="sxs-lookup"><span data-stu-id="b4982-260">High</span></span>  <br/> |<span data-ttu-id="b4982-261">1,1</span><span class="sxs-lookup"><span data-stu-id="b4982-261">1</span></span>  <br/> |<span data-ttu-id="b4982-262">5061</span><span class="sxs-lookup"><span data-stu-id="b4982-262">5061</span></span>  <br/> |<span data-ttu-id="b4982-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b4982-263">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![Скопируйте и вставьте значения из таблицы](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="b4982-265">Выберите **добавить дополнительные записи SRV**.</span><span class="sxs-lookup"><span data-stu-id="b4982-265">Select **Add more SRV records**.</span></span>
    
    ![Выберите добавить дополнительные записи SRV](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="b4982-267">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="b4982-267">Add the second SRV record:</span></span>
    
    <span data-ttu-id="b4982-268">В поля для второй записи введите (или скопируйте и вставьте) значения из второй строки приведенной выше таблицы.</span><span class="sxs-lookup"><span data-stu-id="b4982-268">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="b4982-269">После добавления обеих записей SRV нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="b4982-269">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![Нажмите кнопку продолжить.](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="b4982-271">На следующей странице нажмите кнопку **продолжить** еще раз, чтобы подтвердить изменения и сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="b4982-271">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Нажмите кнопку продолжить.](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="b4982-p113">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b4982-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
