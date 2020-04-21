---
title: Создание записей DNS на сайте web.com для Майкрософт
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу web.com для Майкрософт.
ms.openlocfilehash: ec1d0168fb8a9dfb30d47412146777bc88f90a46
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629255"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a><span data-ttu-id="afe6a-103">Создание записей DNS на сайте web.com для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="afe6a-103">Create DNS records at web.com for Microsoft</span></span>

 <span data-ttu-id="afe6a-104">Если вы не нашли то, что вы ищете, обратитесь к разделу **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="afe6a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="afe6a-105">Если web.com является поставщиком услуг хостинга DNS, выполните действия, описанные в этой статье, чтобы проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и т. д.</span><span class="sxs-lookup"><span data-stu-id="afe6a-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="afe6a-106">Когда вы добавите эти записи на сайте web.com, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="afe6a-106">After you add these records at web.com, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="afe6a-107">Чтобы узнать о размещении и DNS для веб-сайтов с помощью Microsoft, ознакомьтесь со статьей [использование общедоступного веб-сайта с корпорацией Майкрософт](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="afe6a-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="afe6a-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="afe6a-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="afe6a-111">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="afe6a-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="afe6a-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="afe6a-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="afe6a-113">Эту процедуру необходимо выполнить на сайте регистратора доменных имен, на котором вы приобрели и зарегистрировали свой домен.</span><span class="sxs-lookup"><span data-stu-id="afe6a-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="afe6a-114">При регистрации в web.com вы добавили домен с помощью процесса **установки** Web.com.</span><span class="sxs-lookup"><span data-stu-id="afe6a-114">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="afe6a-115">Чтобы проверить и создать записи DNS для вашего домена в корпорации Майкрософт, сначала необходимо изменить серверов доменных имен в вашем регистраторе доменных имен, чтобы они использовали серверов доменных имен Web. com.</span><span class="sxs-lookup"><span data-stu-id="afe6a-115">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="afe6a-116">Чтобы самостоятельно изменить серверы доменных имен на веб-сайте регистратора доменных имен, выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="afe6a-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="afe6a-117">Найдите на веб-сайте регистратора домена область, в которой можно изменить серверы доменных имен для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="afe6a-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="afe6a-118">Создайте две записи серверов доменных имен, используя значения из приведенной ниже таблицы, либо измените существующие записи серверов доменных имен, чтобы они соответствовали следующим значениям:</span><span class="sxs-lookup"><span data-stu-id="afe6a-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="afe6a-119">Основной сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="afe6a-119">First nameserver</span></span>  <br/> |<span data-ttu-id="afe6a-120">Используйте значение сервера доменных имен, предоставленное web.com.</span><span class="sxs-lookup"><span data-stu-id="afe6a-120">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="afe6a-121">Второстепенный сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="afe6a-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="afe6a-122">Используйте значение сервера доменных имен, предоставленное web.com.</span><span class="sxs-lookup"><span data-stu-id="afe6a-122">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="afe6a-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="afe6a-123">You should use at least two name server records.</span></span> <span data-ttu-id="afe6a-124">Если в списке указаны другие серверы имен, их следует удалить.</span><span class="sxs-lookup"><span data-stu-id="afe6a-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="afe6a-125">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="afe6a-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="afe6a-126">На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="afe6a-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="afe6a-127">После этого ваша электронная почта Майкрософт и другие службы будут настроены для работы с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="afe6a-127">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="afe6a-128">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="afe6a-128">Add a TXT record for verification</span></span>
<span data-ttu-id="afe6a-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="afe6a-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="afe6a-130">Перед использованием домена с корпорацией Майкрософт необходимо убедиться, что вы являетесь его владельцем.</span><span class="sxs-lookup"><span data-stu-id="afe6a-130">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="afe6a-131">Вы можете войти в свою учетную запись у вас в вашем регистраторе доменных имен и создать запись DNS в Майкрософт, если вы владеете этим доменом.</span><span class="sxs-lookup"><span data-stu-id="afe6a-131">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="afe6a-p105">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="afe6a-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="afe6a-134">Чтобы приступить к работе, откройте страницу со своими доменами на сайте web.com, используя [указанную ниже ссылку](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="afe6a-134">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="afe6a-135">Сначала войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="afe6a-135">Log in first.</span></span>
  
2. <span data-ttu-id="afe6a-136">На странице " **Диспетчер учетных записей** " выберите **Мои доменные имена**.</span><span class="sxs-lookup"><span data-stu-id="afe6a-136">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="afe6a-137">В разделе \* \* Управление \* мой домен \* \* \* выберите **изменить дополнительные записи DNS**.</span><span class="sxs-lookup"><span data-stu-id="afe6a-137">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="afe6a-138">На странице **доменные имена** в разделе **текст (записи TXT)** щелкните **изменить записи TXT**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="afe6a-138">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="afe6a-139">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="afe6a-139">**Host**</span></span>|<span data-ttu-id="afe6a-140">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="afe6a-140">**TTL**</span></span>|<span data-ttu-id="afe6a-141">**Text (Текст)**</span><span class="sxs-lookup"><span data-stu-id="afe6a-141">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="afe6a-142">3600</span><span class="sxs-lookup"><span data-stu-id="afe6a-142">3600</span></span>  <br/> |<span data-ttu-id="afe6a-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="afe6a-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="afe6a-144">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="afe6a-144">**Note:** This is an example.</span></span> <span data-ttu-id="afe6a-145">Используйте указанную здесь **конечную точку или значение адреса** из таблицы.</span><span class="sxs-lookup"><span data-stu-id="afe6a-145">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="afe6a-146">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="afe6a-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="afe6a-147">Нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="afe6a-147">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="afe6a-148">Подождите несколько минут, прежде чем проверять новую запись TXT, чтобы созданная запись могла обновляться в Интернете.</span><span class="sxs-lookup"><span data-stu-id="afe6a-148">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="afe6a-149">Теперь, когда вы добавили запись на сайте регистратора доменных имен, вернитесь в корпорацию Майкрософт и запросите запись.</span><span class="sxs-lookup"><span data-stu-id="afe6a-149">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="afe6a-150">После того как корпорация Майкрософт обнаружит правильную запись TXT, ваш домен будет проверен.</span><span class="sxs-lookup"><span data-stu-id="afe6a-150">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="afe6a-151">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="afe6a-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="afe6a-152">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="afe6a-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="afe6a-153">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="afe6a-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="afe6a-154">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="afe6a-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="afe6a-p108">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="afe6a-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="afe6a-158">Добавление записи MX для отправки электронной почты для вашего домена в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="afe6a-158">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="afe6a-159"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="afe6a-159"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="afe6a-160">Чтобы приступить к работе, откройте страницу со своими доменами на сайте web.com, используя [указанную ниже ссылку](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="afe6a-160">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="afe6a-161">Сначала войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="afe6a-161">Log in first.</span></span>
  
2. <span data-ttu-id="afe6a-162">На странице " **Диспетчер учетных записей** " выберите **Мои доменные имена**.</span><span class="sxs-lookup"><span data-stu-id="afe6a-162">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="afe6a-163">В разделе \* \* Управление \* мой домен \* \* \* выберите **изменить дополнительные записи DNS**.</span><span class="sxs-lookup"><span data-stu-id="afe6a-163">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="afe6a-164">В разделе **почтовые серверы (записи MX)** щелкните **изменить записи MX**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="afe6a-164">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="afe6a-165">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="afe6a-165">**Priority**</span></span>|<span data-ttu-id="afe6a-166">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="afe6a-166">**TTL**</span></span>|<span data-ttu-id="afe6a-167">**Mail Server (Почтовый сервер)**</span><span class="sxs-lookup"><span data-stu-id="afe6a-167">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="afe6a-168">1,1</span><span class="sxs-lookup"><span data-stu-id="afe6a-168">1</span></span>  <br/> <span data-ttu-id="afe6a-169">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).   </span><span class="sxs-lookup"><span data-stu-id="afe6a-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="afe6a-170">3600</span><span class="sxs-lookup"><span data-stu-id="afe6a-170">3600</span></span>  <br/> |<span data-ttu-id="afe6a-171">*\<ключ_домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="afe6a-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="afe6a-172">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="afe6a-172">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="afe6a-173">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="afe6a-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="afe6a-174">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="afe6a-174">Select **Save**.</span></span>
  
6. <span data-ttu-id="afe6a-175">Если в разделе **MX Records (записи MX** ) есть какие-либо другие записи MX, установите флажок рядом с записью в разделе **Delete (удалить**) и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="afe6a-175">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="afe6a-176">На экране подтверждения нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="afe6a-176">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="afe6a-177">Добавление шести записей CNAME, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="afe6a-177">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="afe6a-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="afe6a-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="afe6a-179">Чтобы приступить к работе, откройте страницу со своими доменами на сайте web.com, используя [указанную ниже ссылку](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="afe6a-179">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="afe6a-180">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="afe6a-180">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="afe6a-181">На странице " **Диспетчер учетных записей** " выберите **Мои доменные имена**.</span><span class="sxs-lookup"><span data-stu-id="afe6a-181">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="afe6a-182">В разделе \* \* Управление \* мой домен \* \* \* выберите **изменить дополнительные записи DNS**.</span><span class="sxs-lookup"><span data-stu-id="afe6a-182">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="afe6a-183">Добавьте первую из шести записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="afe6a-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="afe6a-184">В разделе **псевдонимы узлов (записи CNAME)** щелкните **изменить записи CNAME**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="afe6a-184">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="afe6a-185">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="afe6a-185">**Alias**</span></span>|<span data-ttu-id="afe6a-186">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="afe6a-186">**TTL**</span></span>|<span data-ttu-id="afe6a-187">**Refers to Host Name (Указывает на имя узла)**</span><span class="sxs-lookup"><span data-stu-id="afe6a-187">**Refers to Host Name**</span></span>|<span data-ttu-id="afe6a-188">**Другой узел**</span><span class="sxs-lookup"><span data-stu-id="afe6a-188">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="afe6a-189">autodiscover</span><span class="sxs-lookup"><span data-stu-id="afe6a-189">autodiscover</span></span>  <br/> |<span data-ttu-id="afe6a-190">3600</span><span class="sxs-lookup"><span data-stu-id="afe6a-190">3600</span></span>  <br/> |<span data-ttu-id="afe6a-191">@ (None)</span><span class="sxs-lookup"><span data-stu-id="afe6a-191">@ (none)</span></span>  <br/> |<span data-ttu-id="afe6a-192">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="afe6a-192">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="afe6a-193">sip</span><span class="sxs-lookup"><span data-stu-id="afe6a-193">sip</span></span>  <br/> |<span data-ttu-id="afe6a-194">3600</span><span class="sxs-lookup"><span data-stu-id="afe6a-194">3600</span></span>  <br/> |<span data-ttu-id="afe6a-195">@ (None)</span><span class="sxs-lookup"><span data-stu-id="afe6a-195">@ (none)</span></span>  <br/> |<span data-ttu-id="afe6a-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="afe6a-196">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="afe6a-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="afe6a-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="afe6a-198">3600</span><span class="sxs-lookup"><span data-stu-id="afe6a-198">3600</span></span>  <br/> |<span data-ttu-id="afe6a-199">@ (None)</span><span class="sxs-lookup"><span data-stu-id="afe6a-199">@ (none)</span></span>  <br/> | <span data-ttu-id="afe6a-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="afe6a-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="afe6a-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="afe6a-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="afe6a-202">3600</span><span class="sxs-lookup"><span data-stu-id="afe6a-202">3600</span></span>  <br/> |<span data-ttu-id="afe6a-203">@ (None)</span><span class="sxs-lookup"><span data-stu-id="afe6a-203">@ (none)</span></span>  <br/> |<span data-ttu-id="afe6a-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="afe6a-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="afe6a-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="afe6a-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="afe6a-206">3600</span><span class="sxs-lookup"><span data-stu-id="afe6a-206">3600</span></span>  <br/> |<span data-ttu-id="afe6a-207">@ (None)</span><span class="sxs-lookup"><span data-stu-id="afe6a-207">@ (none)</span></span>  <br/> |<span data-ttu-id="afe6a-208">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="afe6a-208">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="afe6a-209">msoid</span><span class="sxs-lookup"><span data-stu-id="afe6a-209">msoid</span></span>  <br/> |<span data-ttu-id="afe6a-210">3600</span><span class="sxs-lookup"><span data-stu-id="afe6a-210">3600</span></span>  <br/> |<span data-ttu-id="afe6a-211">@ (None)</span><span class="sxs-lookup"><span data-stu-id="afe6a-211">@ (none)</span></span>  <br/> |<span data-ttu-id="afe6a-212">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="afe6a-212">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="afe6a-213">Нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="afe6a-213">Select **Continue**.</span></span>
  
6. <span data-ttu-id="afe6a-214">Добавьте остальные пять записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="afe6a-214">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="afe6a-215">Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама</span><span class="sxs-lookup"><span data-stu-id="afe6a-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="afe6a-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="afe6a-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="afe6a-217">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="afe6a-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="afe6a-218">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="afe6a-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="afe6a-219">Если у вас уже есть запись SPF для вашего домена, не создавайте ее для Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="afe6a-219">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="afe6a-220">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="afe6a-220">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="afe6a-221">Чтобы приступить к работе, откройте страницу со своими доменами на сайте web.com, используя [указанную ниже ссылку](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="afe6a-221">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="afe6a-222">Сначала войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="afe6a-222">Log in first.</span></span>
    
  
2. <span data-ttu-id="afe6a-223">На странице " **Диспетчер учетных записей** " выберите **Мои доменные имена**.</span><span class="sxs-lookup"><span data-stu-id="afe6a-223">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="afe6a-224">В разделе \* \* Управление \* мой домен \* \* \* выберите **изменить дополнительные записи DNS**.</span><span class="sxs-lookup"><span data-stu-id="afe6a-224">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="afe6a-225">На странице **доменные имена** в разделе **текст (записи TXT)** щелкните **изменить записи TXT**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="afe6a-225">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="afe6a-226">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="afe6a-226">**Host**</span></span>|<span data-ttu-id="afe6a-227">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="afe6a-227">**TTL**</span></span>|<span data-ttu-id="afe6a-228">**Text (Текст)**</span><span class="sxs-lookup"><span data-stu-id="afe6a-228">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="afe6a-229">3600</span><span class="sxs-lookup"><span data-stu-id="afe6a-229">3600</span></span>  <br/> |<span data-ttu-id="afe6a-230">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="afe6a-230">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="afe6a-231">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="afe6a-231">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="afe6a-232">Нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="afe6a-232">Select **Continue**.</span></span>

6. <span data-ttu-id="afe6a-233">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="afe6a-233">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="afe6a-234">Добавление двух записей SRV, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="afe6a-234">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="afe6a-235"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="afe6a-235"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="afe6a-236">Имейте в виду, что web.com отвечает за обеспечение доступности этой функции.</span><span class="sxs-lookup"><span data-stu-id="afe6a-236">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="afe6a-237">Если вы видите несоответствия между действиями ниже и текущим ГРАФИЧЕСКИм пользовательским интерфейсом web.com (графический пользовательский интерфейс), воспользуйтесь [Сообществом Web.com](https://community.web.com.com/).</span><span class="sxs-lookup"><span data-stu-id="afe6a-237">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="afe6a-238">Чтобы приступить к работе, откройте страницу со своими доменами на сайте web.com, используя [указанную ниже ссылку](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="afe6a-238">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="afe6a-239">Сначала войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="afe6a-239">Log in first.</span></span>
      
2. <span data-ttu-id="afe6a-240">На странице " **Диспетчер учетных записей** " выберите **Мои доменные имена**.</span><span class="sxs-lookup"><span data-stu-id="afe6a-240">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="afe6a-241">В разделе \* \* Управление \* мой домен \* \* \* выберите **изменить дополнительные записи DNS**.</span><span class="sxs-lookup"><span data-stu-id="afe6a-241">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="afe6a-242">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="afe6a-242">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="afe6a-243">В разделе **служба (записи SRV)** щелкните **изменить записи SRV**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="afe6a-243">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="afe6a-244">**Служба**</span><span class="sxs-lookup"><span data-stu-id="afe6a-244">**Service**</span></span>|<span data-ttu-id="afe6a-245">**Protocol (Протокол)**</span><span class="sxs-lookup"><span data-stu-id="afe6a-245">**Protocol**</span></span>|<span data-ttu-id="afe6a-246">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="afe6a-246">**TTL**</span></span>|<span data-ttu-id="afe6a-247">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="afe6a-247">**Priority**</span></span>|<span data-ttu-id="afe6a-248">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="afe6a-248">**Weight**</span></span>|<span data-ttu-id="afe6a-249">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="afe6a-249">**Port**</span></span>|<span data-ttu-id="afe6a-250">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="afe6a-250">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="afe6a-251">_sip</span><span class="sxs-lookup"><span data-stu-id="afe6a-251">_sip</span></span> |<span data-ttu-id="afe6a-252">_tls</span><span class="sxs-lookup"><span data-stu-id="afe6a-252">_tls</span></span> |<span data-ttu-id="afe6a-253">3600</span><span class="sxs-lookup"><span data-stu-id="afe6a-253">3600</span></span> | <span data-ttu-id="afe6a-254">100</span><span class="sxs-lookup"><span data-stu-id="afe6a-254">100</span></span>|<span data-ttu-id="afe6a-255">1,1</span><span class="sxs-lookup"><span data-stu-id="afe6a-255">1</span></span> |<span data-ttu-id="afe6a-256">443</span><span class="sxs-lookup"><span data-stu-id="afe6a-256">443</span></span> |<span data-ttu-id="afe6a-257">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="afe6a-257">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="afe6a-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="afe6a-258">_sipfederationtls</span></span> |<span data-ttu-id="afe6a-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="afe6a-259">_tcp</span></span> |<span data-ttu-id="afe6a-260">3600</span><span class="sxs-lookup"><span data-stu-id="afe6a-260">3600</span></span> |<span data-ttu-id="afe6a-261">100</span><span class="sxs-lookup"><span data-stu-id="afe6a-261">100</span></span> |<span data-ttu-id="afe6a-262">1,1</span><span class="sxs-lookup"><span data-stu-id="afe6a-262">1</span></span> |<span data-ttu-id="afe6a-263">5061</span><span class="sxs-lookup"><span data-stu-id="afe6a-263">5061</span></span> | <span data-ttu-id="afe6a-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="afe6a-264">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="afe6a-265">Добавьте другую запись SRV, выбрав значения из второй строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="afe6a-265">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="afe6a-266">Нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="afe6a-266">Select **Continue**.</span></span>

7. <span data-ttu-id="afe6a-267">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="afe6a-267">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="afe6a-p116">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="afe6a-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
