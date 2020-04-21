---
title: Создание записей DNS на сайте Register.com для Майкрософт
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу Register.com для Майкрософт.
ms.openlocfilehash: 8badcff89b2a8d8cc9901ef4f10c0a6b31de13d7
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629279"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a><span data-ttu-id="5e8a6-103">Создание записей DNS на сайте Register.com для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5e8a6-103">Create DNS records at Register.com for Microsoft</span></span>

 <span data-ttu-id="5e8a6-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="5e8a6-105">Если ваш поставщик услуг размещения DNS  Register.com, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="5e8a6-106">Ниже перечислены основные записи, которые нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-106">These are the main records to add.</span></span> <span data-ttu-id="5e8a6-107">Воспользуйтесь инструкциями ниже или [посмотрите видеоролик](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="5e8a6-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
- [<span data-ttu-id="5e8a6-108">Добавление записи TXT на сайте Register.com для подтверждения владения доменом</span><span class="sxs-lookup"><span data-stu-id="5e8a6-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="5e8a6-109">Добавление записи MX для отправки электронной почты для вашего домена в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5e8a6-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="5e8a6-110">Добавление записей CNAME, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5e8a6-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="5e8a6-111">Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="5e8a6-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="5e8a6-112">Добавление двух записей SRV, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5e8a6-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="5e8a6-113">Когда вы добавите эти записи на сайте Register.com, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-113">After you add these records at Register.com, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="5e8a6-114">Чтобы узнать о размещении и DNS для веб-сайтов с помощью Microsoft, ознакомьтесь со статьей [использование общедоступного веб-сайта с корпорацией Майкрософт](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="5e8a6-114">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5e8a6-115">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-115">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="5e8a6-116">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-116">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="5e8a6-117">Если у вас возникли проблемы с процессом обработки почты или другими проблемами после добавления записей DNS, ознакомьтесь с разрешениями [и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5e8a6-117">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="5e8a6-118">Добавление записи TXT на сайте Register.com для подтверждения владения доменом</span><span class="sxs-lookup"><span data-stu-id="5e8a6-118">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="5e8a6-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="5e8a6-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="5e8a6-120">Перед использованием домена с корпорацией Майкрософт необходимо убедиться, что вы являетесь его владельцем.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-120">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="5e8a6-121">Вы можете войти в свою учетную запись у вас в вашем регистраторе доменных имен и создать запись DNS в Майкрософт, если вы владеете этим доменом.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-121">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5e8a6-p104">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="5e8a6-124">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="5e8a6-124">Follow the steps below or [watch the video (start at 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="5e8a6-125">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register.com по [этой ссылке](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="5e8a6-125">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="5e8a6-126">Сперва вам потребуется войти в систему.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-126">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="5e8a6-127">Выберите раздел **Домены**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-127">Select **Domains**.</span></span>
    
3. <span data-ttu-id="5e8a6-128">Выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-128">Select **Manage**.</span></span>
    
4. <span data-ttu-id="5e8a6-129">Найдите строку, содержащую имя домена, который требуется изменить; затем в этой строке выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-129">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="5e8a6-130">Прокрутите окно вниз до раздела **Дополнительные технические параметры** и выберите команду **изменить записи TXT (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-130">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="5e8a6-131">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="5e8a6-132">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="5e8a6-132">**Host Name**</span></span> <br/> |<span data-ttu-id="5e8a6-133">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="5e8a6-133">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="5e8a6-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5e8a6-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="5e8a6-135">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-135">**Note:** This is an example.</span></span> <span data-ttu-id="5e8a6-136">Используйте указанную здесь **конечную точку или значение адреса** из таблицы.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-136">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="5e8a6-137">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="5e8a6-137">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="5e8a6-138">Нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-138">Select **Continue**.</span></span>
    
8. <span data-ttu-id="5e8a6-139">На следующей странице нажмите кнопку **продолжить** еще раз, чтобы подтвердить изменения.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-139">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="5e8a6-140">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="5e8a6-141">Теперь, когда вы добавили запись на сайте регистратора доменных имен, вернитесь в корпорацию Майкрософт и запросите запись.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="5e8a6-142">После того как корпорация Майкрософт обнаружит правильную запись TXT, ваш домен будет проверен.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5e8a6-143">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="5e8a6-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="5e8a6-144">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="5e8a6-145">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="5e8a6-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="5e8a6-146">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5e8a6-147">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-147">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="5e8a6-148">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-148">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="5e8a6-149">Если у вас возникли проблемы с процессом обработки почты или другими проблемами после добавления записей DNS, ознакомьтесь с разрешениями [и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5e8a6-149">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="5e8a6-150">Добавление записи MX для отправки электронной почты для вашего домена в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5e8a6-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="5e8a6-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="5e8a6-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="5e8a6-152">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="5e8a6-152">Follow the steps below or [watch the video (start at 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="5e8a6-153">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register.com по [этой ссылке](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="5e8a6-153">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="5e8a6-154">Сперва вам потребуется войти в систему.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-154">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="5e8a6-155">Выберите раздел **Домены**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-155">Select **Domains**.</span></span>
    
3. <span data-ttu-id="5e8a6-156">Выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-156">Select **Manage**.</span></span>
    
4. <span data-ttu-id="5e8a6-157">Найдите строку, содержащую имя домена, который требуется изменить; затем в этой строке выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-157">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="5e8a6-158">Перейдите к разделу **Дополнительные технические параметры** , а затем выберите **изменить записи почтового обменника**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-158">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![Выберите Изменить записи почтового обменника](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="5e8a6-160">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-160">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="5e8a6-161">В раскрывающемся списке выберите значение **Priority (приоритет** ).</span><span class="sxs-lookup"><span data-stu-id="5e8a6-161">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="5e8a6-162">\*\*\*\*Host Name\*\* (Имя узла)\*\*</span><span class="sxs-lookup"><span data-stu-id="5e8a6-162">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="5e8a6-163">\*\*\*\*Priority\*\* (Приоритет)\*\*</span><span class="sxs-lookup"><span data-stu-id="5e8a6-163">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="5e8a6-164">\*\*\*\*Mail Server\*\* (Почтовый сервер)\*\*</span><span class="sxs-lookup"><span data-stu-id="5e8a6-164">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="5e8a6-165">High (Высокий)</span><span class="sxs-lookup"><span data-stu-id="5e8a6-165">High</span></span>  <br/> <span data-ttu-id="5e8a6-166">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="5e8a6-166">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="5e8a6-167">*\<ключ_домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5e8a6-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="5e8a6-168">**Примечание:** \<Получите *ключ* \> домена из учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-168">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> <br> [<span data-ttu-id="5e8a6-169">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="5e8a6-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Скопируйте и вставьте значение из таблицы](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="5e8a6-171">Если уже указаны какие-либо другие записи MX, выделите каждую из них и удалите.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-171">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="5e8a6-173">Нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-173">Select **Continue**.</span></span>
    
    ![Нажмите кнопку продолжить.](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="5e8a6-175">На следующей странице нажмите кнопку **продолжить** еще раз, чтобы подтвердить изменения и сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-175">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Нажмите кнопку продолжить.](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="5e8a6-177">Добавление записей CNAME, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5e8a6-177">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="5e8a6-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="5e8a6-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="5e8a6-179">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="5e8a6-179">Follow the steps below or [watch the video (start at 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="5e8a6-180">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register.com по [этой ссылке](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="5e8a6-180">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="5e8a6-181">Сперва вам потребуется войти в систему.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-181">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="5e8a6-182">Выберите раздел **Домены**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-182">Select **Domains**.</span></span>
    
3. <span data-ttu-id="5e8a6-183">Выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-183">Select **Manage**.</span></span>
    
4. <span data-ttu-id="5e8a6-184">Найдите строку, содержащую имя домена, который требуется изменить; затем в этой строке выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-184">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="5e8a6-185">Перейдите к разделу **Дополнительные технические параметры** , а затем выберите команду **изменить записи псевдонимов домена**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-185">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![Выберите пункт "изменить записи псевдонимов домена"](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="5e8a6-187">Выберите **добавить дополнительные псевдонимы доменов**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-187">Select **Add more domain aliases**.</span></span>
    
    ![Выберите Добавить другие псевдонимы доменов](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="5e8a6-189">Добавьте необходимые записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-189">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="5e8a6-190">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="5e8a6-191">\*\*\*\*Первое поле (без подписи)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="5e8a6-191">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="5e8a6-192">\*\*\*\*Points to\*\* (Указывает на)\*\*</span><span class="sxs-lookup"><span data-stu-id="5e8a6-192">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="5e8a6-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="5e8a6-193">autodiscover</span></span>  <br/> |<span data-ttu-id="5e8a6-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5e8a6-194">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="5e8a6-195">sip</span><span class="sxs-lookup"><span data-stu-id="5e8a6-195">sip</span></span>  <br/> |<span data-ttu-id="5e8a6-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5e8a6-196">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="5e8a6-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5e8a6-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="5e8a6-198">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5e8a6-198">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="5e8a6-199">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="5e8a6-199">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="5e8a6-200">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="5e8a6-200">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="5e8a6-201">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="5e8a6-201">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="5e8a6-202">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5e8a6-202">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![Копирование и вставка значений DNS из таблицы](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="5e8a6-204">После добавления всех необходимых записей CNAME нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-204">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Нажмите кнопку продолжить.](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="5e8a6-206">На следующей странице нажмите кнопку **продолжить** еще раз, чтобы подтвердить изменения и сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-206">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Нажмите кнопку продолжить.](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="5e8a6-208">Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама</span><span class="sxs-lookup"><span data-stu-id="5e8a6-208">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="5e8a6-209"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="5e8a6-209"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5e8a6-210">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-210">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="5e8a6-211">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-211">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="5e8a6-212">Если у вас уже есть запись SPF для вашего домена, не создавайте ее для Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-212">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="5e8a6-213">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь одну запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-213">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="5e8a6-214">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="5e8a6-214">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="5e8a6-215">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register.com по [этой ссылке](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="5e8a6-215">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="5e8a6-216">Сперва вам потребуется войти в систему.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-216">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="5e8a6-217">Выберите раздел **Домены**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-217">Select **Domains**.</span></span>
    
3. <span data-ttu-id="5e8a6-218">Выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-218">Select **Manage**.</span></span>
    
4. <span data-ttu-id="5e8a6-219">Найдите строку, содержащую имя домена, который требуется изменить; затем в этой строке выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-219">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="5e8a6-220">Перейдите к разделу **Дополнительные технические параметры** , а затем выберите команду **изменить записи TXT (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-220">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![Выберите команду Изменить записи TXT (SPF)](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="5e8a6-222">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-222">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="5e8a6-223">\*\*\*\*Host Name\*\* (Имя узла)\*\*</span><span class="sxs-lookup"><span data-stu-id="5e8a6-223">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="5e8a6-224">\*\*\*\*TXT Record\*\* (Запись TXT)\*\*</span><span class="sxs-lookup"><span data-stu-id="5e8a6-224">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="5e8a6-225">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="5e8a6-225">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="5e8a6-226">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="5e8a6-226">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![Скопируйте и вставьте значения из таблицы](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="5e8a6-228">Нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-228">Select **Continue**.</span></span>
    
    ![Нажмите кнопку продолжить.](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="5e8a6-230">На следующей странице нажмите кнопку **продолжить** еще раз, чтобы подтвердить изменения и сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-230">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Нажмите кнопку продолжить.](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="5e8a6-232">Добавление двух записей SRV, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5e8a6-232">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="5e8a6-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="5e8a6-233"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="5e8a6-234">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="5e8a6-234">Follow the steps below or [watch the video (start at 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="5e8a6-p112">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register.com по [этой ссылке](https://www.register.com/myaccount/). Сперва вам потребуется войти в систему.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-p112">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="5e8a6-237">Выберите раздел **Домены**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-237">Select **Domains**.</span></span>
    
3. <span data-ttu-id="5e8a6-238">Выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-238">Select **Manage**.</span></span>
    
4. <span data-ttu-id="5e8a6-239">Найдите строку, содержащую имя домена, который требуется изменить; затем в этой строке выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-239">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="5e8a6-240">Перейдите к разделу **Дополнительные технические параметры** , а затем выберите **изменить записи SRV**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-240">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![Выберите Изменить записи SRV](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="5e8a6-242">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-242">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="5e8a6-243">В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-243">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="5e8a6-244">В раскрывающемся списке выберите значение **Priority (приоритет** ).</span><span class="sxs-lookup"><span data-stu-id="5e8a6-244">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="5e8a6-245">\*\*\*\*Service\*\* (Служба)\*\*</span><span class="sxs-lookup"><span data-stu-id="5e8a6-245">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="5e8a6-246">\*\*\*\*Proto\*\* (Протокол)\*\*</span><span class="sxs-lookup"><span data-stu-id="5e8a6-246">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="5e8a6-247">\*\*\*\*Name\*\* (Имя)\*\*</span><span class="sxs-lookup"><span data-stu-id="5e8a6-247">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="5e8a6-248">\*\*\*\*Priority\*\* (Приоритет)\*\*</span><span class="sxs-lookup"><span data-stu-id="5e8a6-248">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="5e8a6-249">\*\*\*\*Weight\*\* (Вес)\*\*</span><span class="sxs-lookup"><span data-stu-id="5e8a6-249">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="5e8a6-250">\*\*\*\*Port\*\* (Порт)\*\*</span><span class="sxs-lookup"><span data-stu-id="5e8a6-250">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="5e8a6-251">\*\*\*\*Target\*\* (Целевое значение)\*\*</span><span class="sxs-lookup"><span data-stu-id="5e8a6-251">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5e8a6-252">_sip</span><span class="sxs-lookup"><span data-stu-id="5e8a6-252">_sip</span></span>  <br/> |<span data-ttu-id="5e8a6-253">_tls</span><span class="sxs-lookup"><span data-stu-id="5e8a6-253">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="5e8a6-254">High (Высокий)</span><span class="sxs-lookup"><span data-stu-id="5e8a6-254">High</span></span>  <br/> |<span data-ttu-id="5e8a6-255">1,1</span><span class="sxs-lookup"><span data-stu-id="5e8a6-255">1</span></span>  <br/> |<span data-ttu-id="5e8a6-256">443</span><span class="sxs-lookup"><span data-stu-id="5e8a6-256">443</span></span>  <br/> |<span data-ttu-id="5e8a6-257">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5e8a6-257">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="5e8a6-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="5e8a6-258">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="5e8a6-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="5e8a6-259">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="5e8a6-260">High (Высокий)</span><span class="sxs-lookup"><span data-stu-id="5e8a6-260">High</span></span>  <br/> |<span data-ttu-id="5e8a6-261">1,1</span><span class="sxs-lookup"><span data-stu-id="5e8a6-261">1</span></span>  <br/> |<span data-ttu-id="5e8a6-262">5061</span><span class="sxs-lookup"><span data-stu-id="5e8a6-262">5061</span></span>  <br/> |<span data-ttu-id="5e8a6-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5e8a6-263">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![Скопируйте и вставьте значения из таблицы](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="5e8a6-265">Выберите **добавить дополнительные записи SRV**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-265">Select **Add more SRV records**.</span></span>
    
    ![Выберите добавить дополнительные записи SRV](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="5e8a6-267">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-267">Add the second SRV record:</span></span>
    
    <span data-ttu-id="5e8a6-268">В поля для второй записи введите (или скопируйте и вставьте) значения из второй строки приведенной выше таблицы.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-268">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="5e8a6-269">После добавления обеих записей SRV нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-269">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![Нажмите кнопку продолжить.](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="5e8a6-271">На следующей странице нажмите кнопку **продолжить** еще раз, чтобы подтвердить изменения и сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-271">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Нажмите кнопку продолжить.](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="5e8a6-273">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-273">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="5e8a6-274">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-274">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="5e8a6-275">Если у вас возникли проблемы с процессом обработки почты или другими проблемами после добавления записей DNS, ознакомьтесь с разрешениями [и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5e8a6-275">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
