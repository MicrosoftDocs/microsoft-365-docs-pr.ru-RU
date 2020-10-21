---
title: Создание записей DNS на сайте web.com для Майкрософт
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу web.com для Майкрософт.
ms.openlocfilehash: 25df88e05e96e2394628bf89c8cc07af2d0eac1e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645759"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a><span data-ttu-id="81b73-103">Создание записей DNS на сайте web.com для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="81b73-103">Create DNS records at web.com for Microsoft</span></span>

 <span data-ttu-id="81b73-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="81b73-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="81b73-105">Если web.com является поставщиком услуг хостинга DNS, выполните действия, описанные в этой статье, чтобы проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и т. д.</span><span class="sxs-lookup"><span data-stu-id="81b73-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="81b73-106">Когда вы добавите эти записи на сайте web.com, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="81b73-106">After you add these records at web.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="81b73-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="81b73-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="81b73-110">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="81b73-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="81b73-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="81b73-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="81b73-112">Эту процедуру необходимо выполнить на сайте регистратора доменных имен, на котором вы приобрели и зарегистрировали свой домен.</span><span class="sxs-lookup"><span data-stu-id="81b73-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="81b73-113">При регистрации в web.com вы добавили домен с помощью процесса **установки** Web.com.</span><span class="sxs-lookup"><span data-stu-id="81b73-113">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="81b73-114">Чтобы проверить и создать записи DNS для вашего домена в корпорации Майкрософт, сначала необходимо изменить серверов доменных имен в вашем регистраторе доменных имен, чтобы они использовали серверов доменных имен Web. com.</span><span class="sxs-lookup"><span data-stu-id="81b73-114">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="81b73-115">Чтобы самостоятельно изменить серверы доменных имен на веб-сайте регистратора доменных имен, выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="81b73-115">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="81b73-116">Найдите на веб-сайте регистратора домена область, в которой можно изменить серверы доменных имен для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="81b73-116">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="81b73-117">Создайте две записи серверов доменных имен, используя значения из приведенной ниже таблицы, либо измените существующие записи серверов доменных имен, чтобы они соответствовали следующим значениям:</span><span class="sxs-lookup"><span data-stu-id="81b73-117">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="81b73-118">Основной сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="81b73-118">First nameserver</span></span>  <br/> |<span data-ttu-id="81b73-119">Используйте значение сервера доменных имен, предоставленное web.com.</span><span class="sxs-lookup"><span data-stu-id="81b73-119">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="81b73-120">Второстепенный сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="81b73-120">Second nameserver</span></span>  <br/> |<span data-ttu-id="81b73-121">Используйте значение сервера доменных имен, предоставленное web.com.</span><span class="sxs-lookup"><span data-stu-id="81b73-121">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="81b73-122">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="81b73-122">You should use at least two name server records.</span></span> <span data-ttu-id="81b73-123">Если в списке указаны другие серверы имен, их следует удалить.</span><span class="sxs-lookup"><span data-stu-id="81b73-123">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="81b73-124">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="81b73-124">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="81b73-125">На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="81b73-125">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="81b73-126">После этого ваша электронная почта Майкрософт и другие службы будут настроены для работы с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="81b73-126">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="81b73-127">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="81b73-127">Add a TXT record for verification</span></span>
<span data-ttu-id="81b73-128"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="81b73-128"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="81b73-p104">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="81b73-p104">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="81b73-p105">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="81b73-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="81b73-133">Чтобы приступить к работе, откройте страницу со своими доменами на сайте web.com, используя [указанную ниже ссылку](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="81b73-133">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="81b73-134">Сначала войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="81b73-134">Log in first.</span></span>
  
2. <span data-ttu-id="81b73-135">На странице " **Диспетчер учетных записей** " выберите **Мои доменные имена**.</span><span class="sxs-lookup"><span data-stu-id="81b73-135">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="81b73-136">В разделе \* \* Управление \* мой домен \* \* \* выберите **изменить дополнительные записи DNS**.</span><span class="sxs-lookup"><span data-stu-id="81b73-136">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="81b73-137">На странице **доменные имена** в разделе **текст (записи TXT)** щелкните **изменить записи TXT**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="81b73-137">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="81b73-138">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="81b73-138">**Host**</span></span>|<span data-ttu-id="81b73-139">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="81b73-139">**TTL**</span></span>|<span data-ttu-id="81b73-140">**Text (Текст)**</span><span class="sxs-lookup"><span data-stu-id="81b73-140">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="81b73-141">3600</span><span class="sxs-lookup"><span data-stu-id="81b73-141">3600</span></span>  <br/> |<span data-ttu-id="81b73-142">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="81b73-142">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="81b73-143">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="81b73-143">**Note:** This is an example.</span></span> <span data-ttu-id="81b73-144">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="81b73-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="81b73-145">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="81b73-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="81b73-146">Нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="81b73-146">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="81b73-147">Подождите несколько минут, прежде чем проверять новую запись TXT, чтобы созданная запись могла обновляться в Интернете.</span><span class="sxs-lookup"><span data-stu-id="81b73-147">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="81b73-148">Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.</span><span class="sxs-lookup"><span data-stu-id="81b73-148">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="81b73-149">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="81b73-149">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="81b73-150">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="81b73-150">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="81b73-151">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="81b73-151">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="81b73-152">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="81b73-152">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="81b73-153">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="81b73-153">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="81b73-p108">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="81b73-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="81b73-157">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="81b73-157">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="81b73-158"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="81b73-158"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="81b73-159">Чтобы приступить к работе, откройте страницу со своими доменами на сайте web.com, используя [указанную ниже ссылку](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="81b73-159">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="81b73-160">Сначала войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="81b73-160">Log in first.</span></span>
  
2. <span data-ttu-id="81b73-161">На странице " **Диспетчер учетных записей** " выберите **Мои доменные имена**.</span><span class="sxs-lookup"><span data-stu-id="81b73-161">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="81b73-162">В разделе \* \* Управление \* мой домен \* \* \* выберите **изменить дополнительные записи DNS**.</span><span class="sxs-lookup"><span data-stu-id="81b73-162">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="81b73-163">В разделе **почтовые серверы (записи MX)** щелкните **изменить записи MX**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="81b73-163">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="81b73-164">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="81b73-164">**Priority**</span></span>|<span data-ttu-id="81b73-165">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="81b73-165">**TTL**</span></span>|<span data-ttu-id="81b73-166">**Mail Server (Почтовый сервер)**</span><span class="sxs-lookup"><span data-stu-id="81b73-166">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="81b73-167">1,1</span><span class="sxs-lookup"><span data-stu-id="81b73-167">1</span></span>  <br/> <span data-ttu-id="81b73-168">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).   </span><span class="sxs-lookup"><span data-stu-id="81b73-168">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="81b73-169">3600</span><span class="sxs-lookup"><span data-stu-id="81b73-169">3600</span></span>  <br/> |<span data-ttu-id="81b73-170">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="81b73-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="81b73-171">**Примечание:** Получение  *\<domain-key\>*  учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="81b73-171">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="81b73-172">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="81b73-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="81b73-173">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="81b73-173">Select **Save**.</span></span>
  
6. <span data-ttu-id="81b73-174">Если в разделе **MX Records (записи MX** ) есть какие-либо другие записи MX, установите флажок рядом с записью в разделе **Delete (удалить**) и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="81b73-174">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="81b73-175">На экране подтверждения нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="81b73-175">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="81b73-176">Добавление шести записей CNAME, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="81b73-176">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="81b73-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="81b73-177"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="81b73-178">Чтобы приступить к работе, откройте страницу со своими доменами на сайте web.com, используя [указанную ниже ссылку](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="81b73-178">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="81b73-179">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="81b73-179">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="81b73-180">На странице " **Диспетчер учетных записей** " выберите **Мои доменные имена**.</span><span class="sxs-lookup"><span data-stu-id="81b73-180">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="81b73-181">В разделе \* \* Управление \* мой домен \* \* \* выберите **изменить дополнительные записи DNS**.</span><span class="sxs-lookup"><span data-stu-id="81b73-181">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="81b73-182">Добавьте первую из шести записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="81b73-182">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="81b73-183">В разделе **псевдонимы узлов (записи CNAME)** щелкните **изменить записи CNAME**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="81b73-183">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="81b73-184">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="81b73-184">**Alias**</span></span>|<span data-ttu-id="81b73-185">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="81b73-185">**TTL**</span></span>|<span data-ttu-id="81b73-186">**Refers to Host Name (Указывает на имя узла)**</span><span class="sxs-lookup"><span data-stu-id="81b73-186">**Refers to Host Name**</span></span>|<span data-ttu-id="81b73-187">**Другой узел**</span><span class="sxs-lookup"><span data-stu-id="81b73-187">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="81b73-188">autodiscover</span><span class="sxs-lookup"><span data-stu-id="81b73-188">autodiscover</span></span>  <br/> |<span data-ttu-id="81b73-189">3600</span><span class="sxs-lookup"><span data-stu-id="81b73-189">3600</span></span>  <br/> |<span data-ttu-id="81b73-190">@ (None)</span><span class="sxs-lookup"><span data-stu-id="81b73-190">@ (none)</span></span>  <br/> |<span data-ttu-id="81b73-191">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="81b73-191">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="81b73-192">sip</span><span class="sxs-lookup"><span data-stu-id="81b73-192">sip</span></span>  <br/> |<span data-ttu-id="81b73-193">3600</span><span class="sxs-lookup"><span data-stu-id="81b73-193">3600</span></span>  <br/> |<span data-ttu-id="81b73-194">@ (None)</span><span class="sxs-lookup"><span data-stu-id="81b73-194">@ (none)</span></span>  <br/> |<span data-ttu-id="81b73-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="81b73-195">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="81b73-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="81b73-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="81b73-197">3600</span><span class="sxs-lookup"><span data-stu-id="81b73-197">3600</span></span>  <br/> |<span data-ttu-id="81b73-198">@ (None)</span><span class="sxs-lookup"><span data-stu-id="81b73-198">@ (none)</span></span>  <br/> | <span data-ttu-id="81b73-199">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="81b73-199">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="81b73-200">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="81b73-200">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="81b73-201">3600</span><span class="sxs-lookup"><span data-stu-id="81b73-201">3600</span></span>  <br/> |<span data-ttu-id="81b73-202">@ (None)</span><span class="sxs-lookup"><span data-stu-id="81b73-202">@ (none)</span></span>  <br/> |<span data-ttu-id="81b73-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="81b73-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="81b73-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="81b73-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="81b73-205">3600</span><span class="sxs-lookup"><span data-stu-id="81b73-205">3600</span></span>  <br/> |<span data-ttu-id="81b73-206">@ (None)</span><span class="sxs-lookup"><span data-stu-id="81b73-206">@ (none)</span></span>  <br/> |<span data-ttu-id="81b73-207">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="81b73-207">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="81b73-208">msoid</span><span class="sxs-lookup"><span data-stu-id="81b73-208">msoid</span></span>  <br/> |<span data-ttu-id="81b73-209">3600</span><span class="sxs-lookup"><span data-stu-id="81b73-209">3600</span></span>  <br/> |<span data-ttu-id="81b73-210">@ (None)</span><span class="sxs-lookup"><span data-stu-id="81b73-210">@ (none)</span></span>  <br/> |<span data-ttu-id="81b73-211">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="81b73-211">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="81b73-212">Нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="81b73-212">Select **Continue**.</span></span>
  
6. <span data-ttu-id="81b73-213">Добавьте остальные пять записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="81b73-213">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="81b73-214">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="81b73-214">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="81b73-215"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="81b73-215"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="81b73-216">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="81b73-216">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="81b73-217">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="81b73-217">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="81b73-218">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="81b73-218">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="81b73-219">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь  *одну*  запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="81b73-219">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="81b73-220">Чтобы приступить к работе, откройте страницу со своими доменами на сайте web.com, используя [указанную ниже ссылку](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="81b73-220">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="81b73-221">Сначала войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="81b73-221">Log in first.</span></span>
    
  
2. <span data-ttu-id="81b73-222">На странице " **Диспетчер учетных записей** " выберите **Мои доменные имена**.</span><span class="sxs-lookup"><span data-stu-id="81b73-222">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="81b73-223">В разделе \* \* Управление \* мой домен \* \* \* выберите **изменить дополнительные записи DNS**.</span><span class="sxs-lookup"><span data-stu-id="81b73-223">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="81b73-224">На странице **доменные имена** в разделе **текст (записи TXT)** щелкните **изменить записи TXT**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="81b73-224">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="81b73-225">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="81b73-225">**Host**</span></span>|<span data-ttu-id="81b73-226">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="81b73-226">**TTL**</span></span>|<span data-ttu-id="81b73-227">**Text (Текст)**</span><span class="sxs-lookup"><span data-stu-id="81b73-227">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="81b73-228">3600</span><span class="sxs-lookup"><span data-stu-id="81b73-228">3600</span></span>  <br/> |<span data-ttu-id="81b73-229">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="81b73-229">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="81b73-230">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="81b73-230">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="81b73-231">Нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="81b73-231">Select **Continue**.</span></span>

6. <span data-ttu-id="81b73-232">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="81b73-232">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="81b73-233">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="81b73-233">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="81b73-234"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="81b73-234"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="81b73-235">Имейте в виду, что web.com отвечает за обеспечение доступности этой функции.</span><span class="sxs-lookup"><span data-stu-id="81b73-235">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="81b73-236">Если вы видите несоответствия между действиями ниже и текущим ГРАФИЧЕСКИм пользовательским интерфейсом web.com (графический пользовательский интерфейс), воспользуйтесь [Сообществом Web.com](https://community.web.com.com/).</span><span class="sxs-lookup"><span data-stu-id="81b73-236">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="81b73-237">Чтобы приступить к работе, откройте страницу со своими доменами на сайте web.com, используя [указанную ниже ссылку](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="81b73-237">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="81b73-238">Сначала войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="81b73-238">Log in first.</span></span>
      
2. <span data-ttu-id="81b73-239">На странице " **Диспетчер учетных записей** " выберите **Мои доменные имена**.</span><span class="sxs-lookup"><span data-stu-id="81b73-239">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="81b73-240">В разделе \* \* Управление \* мой домен \* \* \* выберите **изменить дополнительные записи DNS**.</span><span class="sxs-lookup"><span data-stu-id="81b73-240">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="81b73-241">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="81b73-241">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="81b73-242">В разделе **служба (записи SRV)** щелкните **изменить записи SRV**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="81b73-242">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="81b73-243">**Служба**</span><span class="sxs-lookup"><span data-stu-id="81b73-243">**Service**</span></span>|<span data-ttu-id="81b73-244">**Protocol (Протокол)**</span><span class="sxs-lookup"><span data-stu-id="81b73-244">**Protocol**</span></span>|<span data-ttu-id="81b73-245">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="81b73-245">**TTL**</span></span>|<span data-ttu-id="81b73-246">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="81b73-246">**Priority**</span></span>|<span data-ttu-id="81b73-247">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="81b73-247">**Weight**</span></span>|<span data-ttu-id="81b73-248">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="81b73-248">**Port**</span></span>|<span data-ttu-id="81b73-249">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="81b73-249">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="81b73-250">_sip</span><span class="sxs-lookup"><span data-stu-id="81b73-250">_sip</span></span> |<span data-ttu-id="81b73-251">_tls</span><span class="sxs-lookup"><span data-stu-id="81b73-251">_tls</span></span> |<span data-ttu-id="81b73-252">3600</span><span class="sxs-lookup"><span data-stu-id="81b73-252">3600</span></span> | <span data-ttu-id="81b73-253">100</span><span class="sxs-lookup"><span data-stu-id="81b73-253">100</span></span>|<span data-ttu-id="81b73-254">1,1</span><span class="sxs-lookup"><span data-stu-id="81b73-254">1</span></span> |<span data-ttu-id="81b73-255">443</span><span class="sxs-lookup"><span data-stu-id="81b73-255">443</span></span> |<span data-ttu-id="81b73-256">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="81b73-256">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="81b73-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="81b73-257">_sipfederationtls</span></span> |<span data-ttu-id="81b73-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="81b73-258">_tcp</span></span> |<span data-ttu-id="81b73-259">3600</span><span class="sxs-lookup"><span data-stu-id="81b73-259">3600</span></span> |<span data-ttu-id="81b73-260">100</span><span class="sxs-lookup"><span data-stu-id="81b73-260">100</span></span> |<span data-ttu-id="81b73-261">1,1</span><span class="sxs-lookup"><span data-stu-id="81b73-261">1</span></span> |<span data-ttu-id="81b73-262">5061</span><span class="sxs-lookup"><span data-stu-id="81b73-262">5061</span></span> | <span data-ttu-id="81b73-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="81b73-263">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="81b73-264">Добавьте другую запись SRV, выбрав значения из второй строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="81b73-264">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="81b73-265">Нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="81b73-265">Select **Continue**.</span></span>

7. <span data-ttu-id="81b73-266">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="81b73-266">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="81b73-p116">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="81b73-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
