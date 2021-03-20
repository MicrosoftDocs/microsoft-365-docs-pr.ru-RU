---
title: Создание записей DNS в Register.com microsoft
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб в Register.com Microsoft.
ms.openlocfilehash: 439b96ef7ad2fd70b94c3945519d4fa270e43fd2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910058"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a><span data-ttu-id="b10ca-103">Создание записей DNS в Register.com microsoft</span><span class="sxs-lookup"><span data-stu-id="b10ca-103">Create DNS records at Register.com for Microsoft</span></span>

 <span data-ttu-id="b10ca-104">**[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="b10ca-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b10ca-105">Если ваш поставщик услуг размещения DNS  Register.com, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="b10ca-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="b10ca-106">Ниже перечислены основные записи, которые нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="b10ca-106">These are the main records to add.</span></span> <span data-ttu-id="b10ca-107">Воспользуйтесь инструкциями ниже или [посмотрите видеоролик](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="b10ca-107">Follow the steps below or [watch the video](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
- [<span data-ttu-id="b10ca-108">Добавление записи TXT на сайте Register.com для подтверждения владения доменом</span><span class="sxs-lookup"><span data-stu-id="b10ca-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="b10ca-109">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b10ca-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="b10ca-110">Добавление записей CNAME, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b10ca-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="b10ca-111">Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="b10ca-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="b10ca-112">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b10ca-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="b10ca-113">После добавления этих записей в Register.com домен будет настроен для работы с службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b10ca-113">After you add these records at Register.com, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="b10ca-p102">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b10ca-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="b10ca-117">Добавление записи TXT на сайте Register.com для подтверждения владения доменом</span><span class="sxs-lookup"><span data-stu-id="b10ca-117">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="b10ca-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="b10ca-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="b10ca-p103">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="b10ca-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b10ca-p104">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="b10ca-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="b10ca-123">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 0:44)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="b10ca-123">Follow the steps below or [watch the video (start at 0:44)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="b10ca-p105">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register.com по [этой ссылке](https://www.register.com/myaccount/). Сперва вам потребуется войти в систему.</span><span class="sxs-lookup"><span data-stu-id="b10ca-p105">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="b10ca-126">Выберите раздел **Домены**.</span><span class="sxs-lookup"><span data-stu-id="b10ca-126">Select **Domains**.</span></span>
    
3. <span data-ttu-id="b10ca-127">Выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="b10ca-127">Select **Manage**.</span></span>
    
4. <span data-ttu-id="b10ca-128">Найдите строку, содержаную имя домена, который необходимо изменить; а затем в этой строке выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="b10ca-128">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="b10ca-129">Прокрутите вниз в раздел **Расширенные технические параметры,** а затем выберите **Изменить TXT Records (SPF).**</span><span class="sxs-lookup"><span data-stu-id="b10ca-129">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="b10ca-130">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b10ca-130">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="b10ca-131">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="b10ca-131">**Host Name**</span></span> <br/> |<span data-ttu-id="b10ca-132">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="b10ca-132">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="b10ca-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b10ca-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="b10ca-134">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="b10ca-134">**Note:** This is an example.</span></span> <span data-ttu-id="b10ca-135">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="b10ca-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="b10ca-136">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="b10ca-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="b10ca-137">Выберите **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="b10ca-137">Select **Continue**.</span></span>
    
8. <span data-ttu-id="b10ca-138">На следующей странице выберите **Продолжить еще** раз, чтобы подтвердить изменения.</span><span class="sxs-lookup"><span data-stu-id="b10ca-138">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="b10ca-139">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="b10ca-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b10ca-140">Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.</span><span class="sxs-lookup"><span data-stu-id="b10ca-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="b10ca-141">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="b10ca-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b10ca-142">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="b10ca-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="b10ca-143">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="b10ca-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="b10ca-144">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="b10ca-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="b10ca-145">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="b10ca-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b10ca-p107">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b10ca-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="b10ca-149">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b10ca-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="b10ca-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="b10ca-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="b10ca-151">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 3:32)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="b10ca-151">Follow the steps below or [watch the video (start at 3:32)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="b10ca-p108">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register.com по [этой ссылке](https://www.register.com/myaccount/). Сперва вам потребуется войти в систему.</span><span class="sxs-lookup"><span data-stu-id="b10ca-p108">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="b10ca-154">Выберите раздел **Домены**.</span><span class="sxs-lookup"><span data-stu-id="b10ca-154">Select **Domains**.</span></span>
    
3. <span data-ttu-id="b10ca-155">Выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="b10ca-155">Select **Manage**.</span></span>
    
4. <span data-ttu-id="b10ca-156">Найдите строку, содержаную имя домена, который необходимо изменить; а затем в этой строке выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="b10ca-156">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="b10ca-157">Прокрутите в **раздел Расширенные технические параметры,** а затем выберите **Изменить записи обменник почты**.</span><span class="sxs-lookup"><span data-stu-id="b10ca-157">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![Выберите Изменение записей обменного почтового ящика](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="b10ca-159">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="b10ca-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="b10ca-160">(Выберите **значение Priority** из выпадаемого списка.)</span><span class="sxs-lookup"><span data-stu-id="b10ca-160">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="b10ca-161">\*\*\*\*Host Name\*\* (Имя узла)\*\*</span><span class="sxs-lookup"><span data-stu-id="b10ca-161">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="b10ca-162">\*\*\*\*Priority\*\* (Приоритет)\*\*</span><span class="sxs-lookup"><span data-stu-id="b10ca-162">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="b10ca-163">\*\*\*\*Mail Server\*\* (Почтовый сервер)\*\*</span><span class="sxs-lookup"><span data-stu-id="b10ca-163">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="b10ca-164">High (Высокий)</span><span class="sxs-lookup"><span data-stu-id="b10ca-164">High</span></span>  <br/> <span data-ttu-id="b10ca-165">Дополнительные сведения о приоритете см. в статье [Что такое приоритет записей MX?](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="b10ca-165">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> | <span data-ttu-id="b10ca-166">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b10ca-166">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="b10ca-167">**Примечание.**  Получите свой \<*domain-key*\> из учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b10ca-167">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> <br> [<span data-ttu-id="b10ca-168">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="b10ca-168">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Копирование и вклейка значения из таблицы](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="b10ca-170">Если уже указаны какие-либо другие записи MX, выделите каждую из них и удалите.</span><span class="sxs-lookup"><span data-stu-id="b10ca-170">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="b10ca-172">Выберите **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="b10ca-172">Select **Continue**.</span></span>
    
    ![Выберите Продолжить](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="b10ca-174">На следующей странице выберите **Продолжить снова,** чтобы подтвердить и сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="b10ca-174">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Выберите Продолжить](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="b10ca-176">Добавление записей CNAME, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b10ca-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="b10ca-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="b10ca-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="b10ca-178">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 4:23)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="b10ca-178">Follow the steps below or [watch the video (start at 4:23)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="b10ca-p109">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register.com по [этой ссылке](https://www.register.com/myaccount/). Сперва вам потребуется войти в систему.</span><span class="sxs-lookup"><span data-stu-id="b10ca-p109">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="b10ca-181">Выберите раздел **Домены**.</span><span class="sxs-lookup"><span data-stu-id="b10ca-181">Select **Domains**.</span></span>
    
3. <span data-ttu-id="b10ca-182">Выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="b10ca-182">Select **Manage**.</span></span>
    
4. <span data-ttu-id="b10ca-183">Найдите строку, содержаную имя домена, который необходимо изменить; а затем в этой строке выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="b10ca-183">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="b10ca-184">Прокрутите в **раздел Расширенные технические параметры,** а затем выберите **Изменить записи псевдонимов домена.**</span><span class="sxs-lookup"><span data-stu-id="b10ca-184">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![Выберите Изменение записей псевдонимов домена](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="b10ca-186">Выберите **Дополнительные псевдонимы домена**.</span><span class="sxs-lookup"><span data-stu-id="b10ca-186">Select **Add more domain aliases**.</span></span>
    
    ![Выберите дополнительные псевдонимы доменов](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="b10ca-188">Добавьте необходимые записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="b10ca-188">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="b10ca-189">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="b10ca-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="b10ca-190">\*\*\*\*Первое поле (без подписи)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b10ca-190">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="b10ca-191">\*\*\*\*Points to\*\* (Указывает на)\*\*</span><span class="sxs-lookup"><span data-stu-id="b10ca-191">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="b10ca-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="b10ca-192">autodiscover</span></span>  <br/> |<span data-ttu-id="b10ca-193">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b10ca-193">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="b10ca-194">sip</span><span class="sxs-lookup"><span data-stu-id="b10ca-194">sip</span></span>  <br/> |<span data-ttu-id="b10ca-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b10ca-195">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="b10ca-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b10ca-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b10ca-197">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b10ca-197">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="b10ca-198">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b10ca-198">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b10ca-199">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="b10ca-199">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="b10ca-200">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b10ca-200">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b10ca-201">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b10ca-201">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![Копирование и вклейка значений DNS из таблицы](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="b10ca-203">При добавлении всех необходимых записей CNAME выберите **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="b10ca-203">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Выберите Продолжить](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="b10ca-205">На следующей странице выберите **Продолжить снова,** чтобы подтвердить и сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="b10ca-205">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Выберите Продолжить](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b10ca-207">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="b10ca-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="b10ca-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="b10ca-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b10ca-209">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="b10ca-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="b10ca-210">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="b10ca-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="b10ca-211">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b10ca-211">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="b10ca-212">Вместо этого добавьте необходимые значения для продуктов корпорации Майкрософт в текущую запись. Таким образом, в одной записи SPF будут указаны оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="b10ca-212">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="b10ca-213">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 5:12)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="b10ca-213">Follow the steps below or [watch the video (start at 5:12)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="b10ca-p111">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register.com по [этой ссылке](https://www.register.com/myaccount/). Сперва вам потребуется войти в систему.</span><span class="sxs-lookup"><span data-stu-id="b10ca-p111">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="b10ca-216">Выберите раздел **Домены**.</span><span class="sxs-lookup"><span data-stu-id="b10ca-216">Select **Domains**.</span></span>
    
3. <span data-ttu-id="b10ca-217">Выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="b10ca-217">Select **Manage**.</span></span>
    
4. <span data-ttu-id="b10ca-218">Найдите строку, содержаную имя домена, который необходимо изменить; а затем в этой строке выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="b10ca-218">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="b10ca-219">Прокрутите раздел **Расширенные технические параметры,** а затем выберите **Изменить TXT Records (SPF).**</span><span class="sxs-lookup"><span data-stu-id="b10ca-219">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![Выберите Изменение записей TXT (SPF)](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="b10ca-221">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="b10ca-221">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="b10ca-222">\*\*\*\*Host Name\*\* (Имя узла)\*\*</span><span class="sxs-lookup"><span data-stu-id="b10ca-222">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="b10ca-223">\*\*\*\*TXT Record\*\* (Запись TXT)\*\*</span><span class="sxs-lookup"><span data-stu-id="b10ca-223">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="b10ca-224">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="b10ca-224">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="b10ca-225">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="b10ca-225">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![Копирование и вклейка значений из таблицы](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="b10ca-227">Выберите **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="b10ca-227">Select **Continue**.</span></span>
    
    ![Выберите Продолжить](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="b10ca-229">На следующей странице выберите **Продолжить снова,** чтобы подтвердить и сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="b10ca-229">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Выберите Продолжить](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="b10ca-231">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b10ca-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="b10ca-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="b10ca-232"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="b10ca-233">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 5:55)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="b10ca-233">Follow the steps below or [watch the video (start at 5:55)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="b10ca-p112">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register.com по [этой ссылке](https://www.register.com/myaccount/). Сперва вам потребуется войти в систему.</span><span class="sxs-lookup"><span data-stu-id="b10ca-p112">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="b10ca-236">Выберите раздел **Домены**.</span><span class="sxs-lookup"><span data-stu-id="b10ca-236">Select **Domains**.</span></span>
    
3. <span data-ttu-id="b10ca-237">Выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="b10ca-237">Select **Manage**.</span></span>
    
4. <span data-ttu-id="b10ca-238">Найдите строку, содержаную имя домена, который необходимо изменить; а затем в этой строке выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="b10ca-238">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="b10ca-239">Прокрутите в **раздел Расширенные технические параметры,** а затем выберите **Изменить записи SRV**.</span><span class="sxs-lookup"><span data-stu-id="b10ca-239">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![Выберите изменение записей SRV](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="b10ca-241">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="b10ca-241">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="b10ca-242">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="b10ca-242">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="b10ca-243">(Выберите **значение Priority** из выпадаемого списка.)</span><span class="sxs-lookup"><span data-stu-id="b10ca-243">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="b10ca-244">\*\*\*\*Service\*\* (Служба)\*\*</span><span class="sxs-lookup"><span data-stu-id="b10ca-244">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="b10ca-245">\*\*\*\*Proto\*\* (Протокол)\*\*</span><span class="sxs-lookup"><span data-stu-id="b10ca-245">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="b10ca-246">\*\*\*\*Name\*\* (Имя)\*\*</span><span class="sxs-lookup"><span data-stu-id="b10ca-246">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="b10ca-247">\*\*\*\*Priority\*\* (Приоритет)\*\*</span><span class="sxs-lookup"><span data-stu-id="b10ca-247">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="b10ca-248">\*\*\*\*Weight\*\* (Вес)\*\*</span><span class="sxs-lookup"><span data-stu-id="b10ca-248">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="b10ca-249">\*\*\*\*Port\*\* (Порт)\*\*</span><span class="sxs-lookup"><span data-stu-id="b10ca-249">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="b10ca-250">\*\*\*\*Target\*\* (Целевое значение)\*\*</span><span class="sxs-lookup"><span data-stu-id="b10ca-250">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b10ca-251">_sip</span><span class="sxs-lookup"><span data-stu-id="b10ca-251">_sip</span></span>  <br/> |<span data-ttu-id="b10ca-252">_tls</span><span class="sxs-lookup"><span data-stu-id="b10ca-252">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="b10ca-253">High (Высокий)</span><span class="sxs-lookup"><span data-stu-id="b10ca-253">High</span></span>  <br/> |<span data-ttu-id="b10ca-254">1</span><span class="sxs-lookup"><span data-stu-id="b10ca-254">1</span></span>  <br/> |<span data-ttu-id="b10ca-255">443</span><span class="sxs-lookup"><span data-stu-id="b10ca-255">443</span></span>  <br/> |<span data-ttu-id="b10ca-256">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b10ca-256">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="b10ca-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="b10ca-257">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="b10ca-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="b10ca-258">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="b10ca-259">High (Высокий)</span><span class="sxs-lookup"><span data-stu-id="b10ca-259">High</span></span>  <br/> |<span data-ttu-id="b10ca-260">1</span><span class="sxs-lookup"><span data-stu-id="b10ca-260">1</span></span>  <br/> |<span data-ttu-id="b10ca-261">5061</span><span class="sxs-lookup"><span data-stu-id="b10ca-261">5061</span></span>  <br/> |<span data-ttu-id="b10ca-262">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b10ca-262">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![Копирование и вклейка значений из таблицы](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="b10ca-264">Выберите **Добавить дополнительные записи SRV**.</span><span class="sxs-lookup"><span data-stu-id="b10ca-264">Select **Add more SRV records**.</span></span>
    
    ![Выберите Добавление дополнительных записей SRV](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="b10ca-266">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="b10ca-266">Add the second SRV record:</span></span>
    
    <span data-ttu-id="b10ca-267">В поля для второй записи введите (или скопируйте и вставьте) значения из второй строки приведенной выше таблицы.</span><span class="sxs-lookup"><span data-stu-id="b10ca-267">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="b10ca-268">При добавлении обеих записей SRV выберите **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="b10ca-268">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![Выберите Продолжить](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="b10ca-270">На следующей странице выберите **Продолжить снова,** чтобы подтвердить и сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="b10ca-270">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Выберите Продолжить](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="b10ca-p113">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b10ca-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
