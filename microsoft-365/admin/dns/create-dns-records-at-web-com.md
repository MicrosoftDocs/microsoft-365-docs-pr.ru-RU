---
title: Создание записей DNS для Office 365 в web.com
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу web.com для Office 365.
ms.openlocfilehash: eb231f85e568e81a5e229f0533d8176feb590f48
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42249459"
---
# <a name="create-dns-records-at-webcom-for-office-365"></a><span data-ttu-id="b8a14-103">Создание записей DNS для Office 365 в web.com</span><span class="sxs-lookup"><span data-stu-id="b8a14-103">Create DNS records at web.com for Office 365</span></span>

 <span data-ttu-id="b8a14-104">Если вы не нашли то, что вы ищете, обратитесь к разделу **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="b8a14-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b8a14-105">Если web.com является поставщиком услуг хостинга DNS, выполните действия, описанные в этой статье, чтобы проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и т. д.</span><span class="sxs-lookup"><span data-stu-id="b8a14-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="b8a14-106">Когда вы добавите эти записи на сайте web.com, ваш домен будет настроен для работы со службами Office 365.</span><span class="sxs-lookup"><span data-stu-id="b8a14-106">After you add these records at web.com, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="b8a14-107">Дополнительные сведения о веб-хостинге и DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="b8a14-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="b8a14-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b8a14-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="b8a14-111">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="b8a14-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="b8a14-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="b8a14-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8a14-113">Эту процедуру необходимо выполнить на сайте регистратора доменных имен, на котором вы приобрели и зарегистрировали свой домен.</span><span class="sxs-lookup"><span data-stu-id="b8a14-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="b8a14-114">При регистрации в web.com вы добавили домен с помощью процесса **установки** Web.com.</span><span class="sxs-lookup"><span data-stu-id="b8a14-114">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="b8a14-115">Чтобы проверить и создать записи DNS для вашего домена в Office 365, сначала необходимо изменить серверов доменных имен в регистраторе доменных имен, чтобы они использовали серверов доменных имен Web. com.</span><span class="sxs-lookup"><span data-stu-id="b8a14-115">To verify and create DNS records for your domain in Office 365, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="b8a14-116">Чтобы самостоятельно изменить серверы доменных имен на веб-сайте регистратора доменных имен, выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="b8a14-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="b8a14-117">Найдите на веб-сайте регистратора домена область, в которой можно изменить серверы доменных имен для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="b8a14-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="b8a14-118">Создайте две записи серверов доменных имен, используя значения из приведенной ниже таблицы, либо измените существующие записи серверов доменных имен, чтобы они соответствовали следующим значениям:</span><span class="sxs-lookup"><span data-stu-id="b8a14-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="b8a14-119">Основной сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="b8a14-119">First nameserver</span></span>  <br/> |<span data-ttu-id="b8a14-120">Используйте значение сервера доменных имен, предоставленное web.com.</span><span class="sxs-lookup"><span data-stu-id="b8a14-120">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="b8a14-121">Второстепенный сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="b8a14-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="b8a14-122">Используйте значение сервера доменных имен, предоставленное web.com.</span><span class="sxs-lookup"><span data-stu-id="b8a14-122">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="b8a14-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="b8a14-123">You should use at least two name server records.</span></span> <span data-ttu-id="b8a14-124">Если в списке указаны другие серверы имен, их следует удалить.</span><span class="sxs-lookup"><span data-stu-id="b8a14-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="b8a14-125">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="b8a14-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b8a14-p103">На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов. После этого ваша электронная почта и все остальные службы Office 365 будут настроены на работу с новым доменом.</span><span class="sxs-lookup"><span data-stu-id="b8a14-p103">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b8a14-128">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="b8a14-128">Add a TXT record for verification</span></span>
<span data-ttu-id="b8a14-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="b8a14-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="b8a14-p104">Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете данным доменом.</span><span class="sxs-lookup"><span data-stu-id="b8a14-p104">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b8a14-p105">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="b8a14-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="b8a14-134">Чтобы приступить к работе, откройте страницу со своими доменами на сайте web.com, используя [указанную ниже ссылку](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="b8a14-134">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="b8a14-135">Сначала войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="b8a14-135">Log in first.</span></span>
  
2. <span data-ttu-id="b8a14-136">На странице " **Диспетчер учетных записей** " выберите **Мои доменные имена**.</span><span class="sxs-lookup"><span data-stu-id="b8a14-136">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="b8a14-137">В разделе \* \* Управление \* мой домен \* \* \* выберите **изменить дополнительные записи DNS**.</span><span class="sxs-lookup"><span data-stu-id="b8a14-137">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="b8a14-138">На странице **доменные имена** в разделе **текст (записи TXT)** щелкните **изменить записи TXT**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="b8a14-138">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="b8a14-139">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="b8a14-139">**Host**</span></span>|<span data-ttu-id="b8a14-140">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="b8a14-140">**TTL**</span></span>|<span data-ttu-id="b8a14-141">**Text (Текст)**</span><span class="sxs-lookup"><span data-stu-id="b8a14-141">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="b8a14-142">3600</span><span class="sxs-lookup"><span data-stu-id="b8a14-142">3600</span></span>  <br/> |<span data-ttu-id="b8a14-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b8a14-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="b8a14-p107">**Примечание.** Это пример. Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.           [Где это находится?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="b8a14-p107">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>    |
  
    
5. <span data-ttu-id="b8a14-147">Нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="b8a14-147">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="b8a14-148">Подождите несколько минут, прежде чем проверять новую запись TXT, чтобы созданная запись могла обновляться в Интернете.</span><span class="sxs-lookup"><span data-stu-id="b8a14-148">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b8a14-149">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="b8a14-149">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="b8a14-150">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="b8a14-150">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b8a14-151">В центре администрирования перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> **параметров** \> ".</span><span class="sxs-lookup"><span data-stu-id="b8a14-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="b8a14-152">На странице **Domains (домены** ) выберите домен, который вы хотите проверить.</span><span class="sxs-lookup"><span data-stu-id="b8a14-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="b8a14-153">На странице **Настройка** выберите пункт **Запуск программы установки**.</span><span class="sxs-lookup"><span data-stu-id="b8a14-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="b8a14-154">На странице **Проверка домена** нажмите кнопку **проверить**.</span><span class="sxs-lookup"><span data-stu-id="b8a14-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="b8a14-p108">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b8a14-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="b8a14-158">Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="b8a14-158">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="b8a14-159"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="b8a14-159"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="b8a14-160">Чтобы приступить к работе, откройте страницу со своими доменами на сайте web.com, используя [указанную ниже ссылку](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="b8a14-160">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="b8a14-161">Сначала войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="b8a14-161">Log in first.</span></span>
  
2. <span data-ttu-id="b8a14-162">На странице " **Диспетчер учетных записей** " выберите **Мои доменные имена**.</span><span class="sxs-lookup"><span data-stu-id="b8a14-162">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="b8a14-163">В разделе \* \* Управление \* мой домен \* \* \* выберите **изменить дополнительные записи DNS**.</span><span class="sxs-lookup"><span data-stu-id="b8a14-163">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="b8a14-164">В разделе **почтовые серверы (записи MX)** щелкните **изменить записи MX**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="b8a14-164">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="b8a14-165">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="b8a14-165">**Priority**</span></span>|<span data-ttu-id="b8a14-166">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="b8a14-166">**TTL**</span></span>|<span data-ttu-id="b8a14-167">**Mail Server (Почтовый сервер)**</span><span class="sxs-lookup"><span data-stu-id="b8a14-167">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="b8a14-168">1,1</span><span class="sxs-lookup"><span data-stu-id="b8a14-168">1</span></span>  <br/> <span data-ttu-id="b8a14-169">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).   </span><span class="sxs-lookup"><span data-stu-id="b8a14-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="b8a14-170">3600</span><span class="sxs-lookup"><span data-stu-id="b8a14-170">3600</span></span>  <br/> |<span data-ttu-id="b8a14-171">*\<ключ-домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b8a14-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="b8a14-172">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Office 365.</span><span class="sxs-lookup"><span data-stu-id="b8a14-172">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="b8a14-173">Как найти это значение?</span><span class="sxs-lookup"><span data-stu-id="b8a14-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="b8a14-174">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b8a14-174">Select **Save**.</span></span>
  
6. <span data-ttu-id="b8a14-175">Если в разделе **MX Records (записи MX** ) есть какие-либо другие записи MX, установите флажок рядом с записью в разделе **Delete (удалить**) и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b8a14-175">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="b8a14-176">На экране подтверждения нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="b8a14-176">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="b8a14-177">Добавление шести записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="b8a14-177">Add the Six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="b8a14-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="b8a14-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="b8a14-179">Чтобы приступить к работе, откройте страницу со своими доменами на сайте web.com, используя [указанную ниже ссылку](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="b8a14-179">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="b8a14-180">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="b8a14-180">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="b8a14-181">На странице " **Диспетчер учетных записей** " выберите **Мои доменные имена**.</span><span class="sxs-lookup"><span data-stu-id="b8a14-181">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="b8a14-182">В разделе \* \* Управление \* мой домен \* \* \* выберите **изменить дополнительные записи DNS**.</span><span class="sxs-lookup"><span data-stu-id="b8a14-182">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="b8a14-183">Добавьте первую из шести записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="b8a14-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="b8a14-184">В разделе **псевдонимы узлов (записи CNAME)** щелкните **изменить записи CNAME**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="b8a14-184">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="b8a14-185">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="b8a14-185">**Alias**</span></span>|<span data-ttu-id="b8a14-186">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="b8a14-186">**TTL**</span></span>|<span data-ttu-id="b8a14-187">**Refers to Host Name (Указывает на имя узла)**</span><span class="sxs-lookup"><span data-stu-id="b8a14-187">**Refers to Host Name**</span></span>|<span data-ttu-id="b8a14-188">**Другой узел**</span><span class="sxs-lookup"><span data-stu-id="b8a14-188">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b8a14-189">autodiscover</span><span class="sxs-lookup"><span data-stu-id="b8a14-189">autodiscover</span></span>  <br/> |<span data-ttu-id="b8a14-190">3600</span><span class="sxs-lookup"><span data-stu-id="b8a14-190">3600</span></span>  <br/> |<span data-ttu-id="b8a14-191">@ (None)</span><span class="sxs-lookup"><span data-stu-id="b8a14-191">@ (none)</span></span>  <br/> |<span data-ttu-id="b8a14-192">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b8a14-192">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="b8a14-193">sip</span><span class="sxs-lookup"><span data-stu-id="b8a14-193">sip</span></span>  <br/> |<span data-ttu-id="b8a14-194">3600</span><span class="sxs-lookup"><span data-stu-id="b8a14-194">3600</span></span>  <br/> |<span data-ttu-id="b8a14-195">@ (None)</span><span class="sxs-lookup"><span data-stu-id="b8a14-195">@ (none)</span></span>  <br/> |<span data-ttu-id="b8a14-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b8a14-196">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="b8a14-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b8a14-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b8a14-198">3600</span><span class="sxs-lookup"><span data-stu-id="b8a14-198">3600</span></span>  <br/> |<span data-ttu-id="b8a14-199">@ (None)</span><span class="sxs-lookup"><span data-stu-id="b8a14-199">@ (none)</span></span>  <br/> | <span data-ttu-id="b8a14-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b8a14-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="b8a14-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b8a14-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b8a14-202">3600</span><span class="sxs-lookup"><span data-stu-id="b8a14-202">3600</span></span>  <br/> |<span data-ttu-id="b8a14-203">@ (None)</span><span class="sxs-lookup"><span data-stu-id="b8a14-203">@ (none)</span></span>  <br/> |<span data-ttu-id="b8a14-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="b8a14-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="b8a14-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b8a14-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b8a14-206">3600</span><span class="sxs-lookup"><span data-stu-id="b8a14-206">3600</span></span>  <br/> |<span data-ttu-id="b8a14-207">@ (None)</span><span class="sxs-lookup"><span data-stu-id="b8a14-207">@ (none)</span></span>  <br/> |<span data-ttu-id="b8a14-208">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b8a14-208">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="b8a14-209">msoid</span><span class="sxs-lookup"><span data-stu-id="b8a14-209">msoid</span></span>  <br/> |<span data-ttu-id="b8a14-210">3600</span><span class="sxs-lookup"><span data-stu-id="b8a14-210">3600</span></span>  <br/> |<span data-ttu-id="b8a14-211">@ (None)</span><span class="sxs-lookup"><span data-stu-id="b8a14-211">@ (none)</span></span>  <br/> |<span data-ttu-id="b8a14-212">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="b8a14-212">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="b8a14-213">Нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="b8a14-213">Select **Continue**.</span></span>
  
6. <span data-ttu-id="b8a14-214">Добавьте остальные пять записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="b8a14-214">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b8a14-215">Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="b8a14-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="b8a14-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="b8a14-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8a14-217">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="b8a14-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="b8a14-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="b8a14-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="b8a14-219">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="b8a14-219">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="b8a14-220">Вместо этого добавьте необходимые значения Office 365 к текущей записи, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="b8a14-220">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="b8a14-221">Чтобы приступить к работе, откройте страницу со своими доменами на сайте web.com, используя [указанную ниже ссылку](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="b8a14-221">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="b8a14-222">Сначала войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="b8a14-222">Log in first.</span></span>
    
  
2. <span data-ttu-id="b8a14-223">На странице " **Диспетчер учетных записей** " выберите **Мои доменные имена**.</span><span class="sxs-lookup"><span data-stu-id="b8a14-223">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="b8a14-224">В разделе \* \* Управление \* мой домен \* \* \* выберите **изменить дополнительные записи DNS**.</span><span class="sxs-lookup"><span data-stu-id="b8a14-224">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="b8a14-225">На странице **доменные имена** в разделе **текст (записи TXT)** щелкните **изменить записи TXT**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="b8a14-225">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="b8a14-226">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="b8a14-226">**Host**</span></span>|<span data-ttu-id="b8a14-227">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="b8a14-227">**TTL**</span></span>|<span data-ttu-id="b8a14-228">**Text (Текст)**</span><span class="sxs-lookup"><span data-stu-id="b8a14-228">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="b8a14-229">3600</span><span class="sxs-lookup"><span data-stu-id="b8a14-229">3600</span></span>  <br/> |<span data-ttu-id="b8a14-230">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="b8a14-230">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="b8a14-231">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="b8a14-231">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="b8a14-232">Нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="b8a14-232">Select **Continue**.</span></span>

6. <span data-ttu-id="b8a14-233">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="b8a14-233">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="b8a14-234">Добавление двух записей SRV, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="b8a14-234">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="b8a14-235"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="b8a14-235"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8a14-236">Имейте в виду, что web.com отвечает за обеспечение доступности этой функции.</span><span class="sxs-lookup"><span data-stu-id="b8a14-236">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="b8a14-237">Если вы видите несоответствия между действиями ниже и текущим ГРАФИЧЕСКИм пользовательским интерфейсом web.com (графический пользовательский интерфейс), воспользуйтесь [Сообществом Web.com](https://community.web.com.com/).</span><span class="sxs-lookup"><span data-stu-id="b8a14-237">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="b8a14-238">Чтобы приступить к работе, откройте страницу со своими доменами на сайте web.com, используя [указанную ниже ссылку](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="b8a14-238">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="b8a14-239">Сначала войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="b8a14-239">Log in first.</span></span>
      
2. <span data-ttu-id="b8a14-240">На странице " **Диспетчер учетных записей** " выберите **Мои доменные имена**.</span><span class="sxs-lookup"><span data-stu-id="b8a14-240">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="b8a14-241">В разделе \* \* Управление \* мой домен \* \* \* выберите **изменить дополнительные записи DNS**.</span><span class="sxs-lookup"><span data-stu-id="b8a14-241">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="b8a14-242">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="b8a14-242">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="b8a14-243">В разделе **служба (записи SRV)** щелкните **изменить записи SRV**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="b8a14-243">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="b8a14-244">**Служба**</span><span class="sxs-lookup"><span data-stu-id="b8a14-244">**Service**</span></span>|<span data-ttu-id="b8a14-245">**Protocol (Протокол)**</span><span class="sxs-lookup"><span data-stu-id="b8a14-245">**Protocol**</span></span>|<span data-ttu-id="b8a14-246">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="b8a14-246">**TTL**</span></span>|<span data-ttu-id="b8a14-247">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="b8a14-247">**Priority**</span></span>|<span data-ttu-id="b8a14-248">**Weight (Вес)**</span><span class="sxs-lookup"><span data-stu-id="b8a14-248">**Weight**</span></span>|<span data-ttu-id="b8a14-249">**Port (Порт)**</span><span class="sxs-lookup"><span data-stu-id="b8a14-249">**Port**</span></span>|<span data-ttu-id="b8a14-250">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="b8a14-250">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b8a14-251">_sip</span><span class="sxs-lookup"><span data-stu-id="b8a14-251">_sip</span></span> |<span data-ttu-id="b8a14-252">_tls</span><span class="sxs-lookup"><span data-stu-id="b8a14-252">_tls</span></span> |<span data-ttu-id="b8a14-253">3600</span><span class="sxs-lookup"><span data-stu-id="b8a14-253">3600</span></span> | <span data-ttu-id="b8a14-254">100</span><span class="sxs-lookup"><span data-stu-id="b8a14-254">100</span></span>|<span data-ttu-id="b8a14-255">1,1</span><span class="sxs-lookup"><span data-stu-id="b8a14-255">1</span></span> |<span data-ttu-id="b8a14-256">443</span><span class="sxs-lookup"><span data-stu-id="b8a14-256">443</span></span> |<span data-ttu-id="b8a14-257">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b8a14-257">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="b8a14-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="b8a14-258">_sipfederationtls</span></span> |<span data-ttu-id="b8a14-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="b8a14-259">_tcp</span></span> |<span data-ttu-id="b8a14-260">3600</span><span class="sxs-lookup"><span data-stu-id="b8a14-260">3600</span></span> |<span data-ttu-id="b8a14-261">100</span><span class="sxs-lookup"><span data-stu-id="b8a14-261">100</span></span> |<span data-ttu-id="b8a14-262">1,1</span><span class="sxs-lookup"><span data-stu-id="b8a14-262">1</span></span> |<span data-ttu-id="b8a14-263">5061</span><span class="sxs-lookup"><span data-stu-id="b8a14-263">5061</span></span> | <span data-ttu-id="b8a14-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b8a14-264">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="b8a14-265">Добавьте другую запись SRV, выбрав значения из второй строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="b8a14-265">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="b8a14-266">Нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="b8a14-266">Select **Continue**.</span></span>

7. <span data-ttu-id="b8a14-267">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="b8a14-267">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="b8a14-p116">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b8a14-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
