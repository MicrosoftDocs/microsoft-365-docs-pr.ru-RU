---
title: Создание записей DNS для web.com Майкрософт
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
description: Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at web.com for Microsoft.
ms.openlocfilehash: 943070f3790f532a0cc686270e0ecdea08f802fd
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656895"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a><span data-ttu-id="3560a-103">Создание записей DNS для web.com Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3560a-103">Create DNS records at web.com for Microsoft</span></span>

 <span data-ttu-id="3560a-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="3560a-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="3560a-105">Если web.com ваш поставщик услуг размещения DNS, выполните действия в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб.</span><span class="sxs-lookup"><span data-stu-id="3560a-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="3560a-106">После добавления этих записей web.com домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3560a-106">After you add these records at web.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="3560a-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3560a-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="3560a-110">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="3560a-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="3560a-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="3560a-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="3560a-112">Эту процедуру необходимо выполнить на сайте регистратора доменных имен, на котором вы приобрели и зарегистрировали свой домен.</span><span class="sxs-lookup"><span data-stu-id="3560a-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="3560a-113">При регистрации в web.com домен добавляется с помощью web.com **установки.**</span><span class="sxs-lookup"><span data-stu-id="3560a-113">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="3560a-114">Чтобы проверить и создать записи DNS для домена в Майкрософт, сначала необходимо изменить серверы доменных имен у регистратора доменных имен, чтобы они использовали серверы доменных имен web.com.</span><span class="sxs-lookup"><span data-stu-id="3560a-114">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="3560a-115">Чтобы самостоятельно изменить серверы доменных имен на веб-сайте регистратора доменных имен, выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="3560a-115">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="3560a-116">Найдите на веб-сайте регистратора домена область, в которой можно изменить серверы доменных имен для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="3560a-116">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="3560a-117">Создайте две записи серверов доменных имен, используя значения из приведенной ниже таблицы, либо измените существующие записи серверов доменных имен, чтобы они соответствовали следующим значениям:</span><span class="sxs-lookup"><span data-stu-id="3560a-117">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="3560a-118">Основной сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="3560a-118">First nameserver</span></span>  <br/> |<span data-ttu-id="3560a-119">Используйте значение для доменного имени, предоставленного web.com.</span><span class="sxs-lookup"><span data-stu-id="3560a-119">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="3560a-120">Второстепенный сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="3560a-120">Second nameserver</span></span>  <br/> |<span data-ttu-id="3560a-121">Используйте значение для доменного имени, предоставленного web.com.</span><span class="sxs-lookup"><span data-stu-id="3560a-121">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="3560a-122">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="3560a-122">You should use at least two name server records.</span></span> <span data-ttu-id="3560a-123">Если в списке есть другие серверы доменных имен, их следует удалить.</span><span class="sxs-lookup"><span data-stu-id="3560a-123">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="3560a-124">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="3560a-124">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3560a-125">На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="3560a-125">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="3560a-126">Затем ваша почта Майкрософт и другие службы будут настроены для работы с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="3560a-126">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="3560a-127">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="3560a-127">Add a TXT record for verification</span></span>
<span data-ttu-id="3560a-128"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="3560a-128"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="3560a-p104">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="3560a-p104">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3560a-p105">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="3560a-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="3560a-133">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="3560a-133">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="3560a-134">Сначала войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="3560a-134">Log in first.</span></span>
  
2. <span data-ttu-id="3560a-135">На странице **"Диспетчер учетных записей"** выберите **"Мои доменные имена".**</span><span class="sxs-lookup"><span data-stu-id="3560a-135">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="3560a-136">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="3560a-136">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="3560a-137">На странице **"Domain Names"** (Доменные имена) в области **Text (TXT Records) (Записи TXT)** щелкните **"Edit TXT Records"**(Изменить записи TXT) и выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="3560a-137">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="3560a-138">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="3560a-138">**Host**</span></span>|<span data-ttu-id="3560a-139">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="3560a-139">**TTL**</span></span>|<span data-ttu-id="3560a-140">**Text (Текст)**</span><span class="sxs-lookup"><span data-stu-id="3560a-140">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="3560a-141">3600</span><span class="sxs-lookup"><span data-stu-id="3560a-141">3600</span></span>  <br/> |<span data-ttu-id="3560a-142">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="3560a-142">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="3560a-143">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="3560a-143">**Note:** This is an example.</span></span> <span data-ttu-id="3560a-144">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="3560a-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="3560a-145">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="3560a-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="3560a-146">Выберите **"Продолжить"**.</span><span class="sxs-lookup"><span data-stu-id="3560a-146">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="3560a-147">Подождите несколько минут, прежде чем проверить новую запись TXT, чтобы созданная запись была обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="3560a-147">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="3560a-148">Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.</span><span class="sxs-lookup"><span data-stu-id="3560a-148">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="3560a-149">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="3560a-149">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="3560a-150">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="3560a-150">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="3560a-151">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="3560a-151">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="3560a-152">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="3560a-152">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="3560a-153">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="3560a-153">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="3560a-p108">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3560a-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="3560a-157">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3560a-157">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="3560a-158"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="3560a-158"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="3560a-159">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="3560a-159">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="3560a-160">Сначала войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="3560a-160">Log in first.</span></span>
  
2. <span data-ttu-id="3560a-161">На странице **"Диспетчер учетных записей"** выберите **"Мои доменные имена".**</span><span class="sxs-lookup"><span data-stu-id="3560a-161">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="3560a-162">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="3560a-162">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="3560a-163">В **области почтовых серверов (записи MX)** щелкните "Изменить записи **MX"** и выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="3560a-163">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="3560a-164">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="3560a-164">**Priority**</span></span>|<span data-ttu-id="3560a-165">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="3560a-165">**TTL**</span></span>|<span data-ttu-id="3560a-166">**Mail Server (Почтовый сервер)**</span><span class="sxs-lookup"><span data-stu-id="3560a-166">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="3560a-167">1 </span><span class="sxs-lookup"><span data-stu-id="3560a-167">1</span></span>  <br/> <span data-ttu-id="3560a-168">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).   </span><span class="sxs-lookup"><span data-stu-id="3560a-168">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="3560a-169">3600</span><span class="sxs-lookup"><span data-stu-id="3560a-169">3600</span></span>  <br/> |<span data-ttu-id="3560a-170">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="3560a-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="3560a-171">**Примечание.** Получите свою  *\<domain-key\>*  учетную запись Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3560a-171">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="3560a-172">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="3560a-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="3560a-173">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3560a-173">Select **Save**.</span></span>
  
6. <span data-ttu-id="3560a-174">Если в разделе "MX **Records"** (Записи MX) указаны другие записи MX, то в разделе "Delete" (Удалить) выберите **"Сохранить" (Сохранить).**</span><span class="sxs-lookup"><span data-stu-id="3560a-174">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="3560a-175">На экране подтверждения выберите **"Сохранить изменения".**</span><span class="sxs-lookup"><span data-stu-id="3560a-175">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="3560a-176">Добавление шести записей CNAME, необходимых для Корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3560a-176">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="3560a-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="3560a-177"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="3560a-178">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="3560a-178">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="3560a-179">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="3560a-179">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="3560a-180">На странице **"Диспетчер учетных записей"** выберите **"Мои доменные имена".**</span><span class="sxs-lookup"><span data-stu-id="3560a-180">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="3560a-181">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="3560a-181">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="3560a-182">Добавьте первую из шести записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="3560a-182">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="3560a-183">В **области "Псевдонимы хоста" (CNAME Records)** щелкните "Изменить **записи CNAME"** и выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="3560a-183">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="3560a-184">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="3560a-184">**Alias**</span></span>|<span data-ttu-id="3560a-185">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="3560a-185">**TTL**</span></span>|<span data-ttu-id="3560a-186">**Refers to Host Name (Указывает на имя узла)**</span><span class="sxs-lookup"><span data-stu-id="3560a-186">**Refers to Host Name**</span></span>|<span data-ttu-id="3560a-187">**Другой хост**</span><span class="sxs-lookup"><span data-stu-id="3560a-187">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3560a-188">autodiscover</span><span class="sxs-lookup"><span data-stu-id="3560a-188">autodiscover</span></span>  <br/> |<span data-ttu-id="3560a-189">3600</span><span class="sxs-lookup"><span data-stu-id="3560a-189">3600</span></span>  <br/> |<span data-ttu-id="3560a-190">@ (нет)</span><span class="sxs-lookup"><span data-stu-id="3560a-190">@ (none)</span></span>  <br/> |<span data-ttu-id="3560a-191">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="3560a-191">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="3560a-192">sip</span><span class="sxs-lookup"><span data-stu-id="3560a-192">sip</span></span>  <br/> |<span data-ttu-id="3560a-193">3600</span><span class="sxs-lookup"><span data-stu-id="3560a-193">3600</span></span>  <br/> |<span data-ttu-id="3560a-194">@ (нет)</span><span class="sxs-lookup"><span data-stu-id="3560a-194">@ (none)</span></span>  <br/> |<span data-ttu-id="3560a-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3560a-195">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="3560a-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3560a-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="3560a-197">3600</span><span class="sxs-lookup"><span data-stu-id="3560a-197">3600</span></span>  <br/> |<span data-ttu-id="3560a-198">@ (нет)</span><span class="sxs-lookup"><span data-stu-id="3560a-198">@ (none)</span></span>  <br/> | <span data-ttu-id="3560a-199">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3560a-199">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="3560a-200">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="3560a-200">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="3560a-201">3600</span><span class="sxs-lookup"><span data-stu-id="3560a-201">3600</span></span>  <br/> |<span data-ttu-id="3560a-202">@ (нет)</span><span class="sxs-lookup"><span data-stu-id="3560a-202">@ (none)</span></span>  <br/> |<span data-ttu-id="3560a-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="3560a-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="3560a-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="3560a-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="3560a-205">3600</span><span class="sxs-lookup"><span data-stu-id="3560a-205">3600</span></span>  <br/> |<span data-ttu-id="3560a-206">@ (нет)</span><span class="sxs-lookup"><span data-stu-id="3560a-206">@ (none)</span></span>  <br/> |<span data-ttu-id="3560a-207">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3560a-207">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="3560a-208">msoid</span><span class="sxs-lookup"><span data-stu-id="3560a-208">msoid</span></span>  <br/> |<span data-ttu-id="3560a-209">3600</span><span class="sxs-lookup"><span data-stu-id="3560a-209">3600</span></span>  <br/> |<span data-ttu-id="3560a-210">@ (нет)</span><span class="sxs-lookup"><span data-stu-id="3560a-210">@ (none)</span></span>  <br/> |<span data-ttu-id="3560a-211">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="3560a-211">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="3560a-212">Выберите **"Продолжить"**.</span><span class="sxs-lookup"><span data-stu-id="3560a-212">Select **Continue**.</span></span>
  
6. <span data-ttu-id="3560a-213">Добавьте остальные пять записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="3560a-213">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="3560a-214">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="3560a-214">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="3560a-215"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="3560a-215"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="3560a-216">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="3560a-216">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="3560a-217">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="3560a-217">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="3560a-218">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3560a-218">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="3560a-219">Вместо этого добавьте необходимые значения Майкрософт в текущую  запись, чтобы иметь одну запись SPF, которая включает оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="3560a-219">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="3560a-220">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="3560a-220">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="3560a-221">Сначала войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="3560a-221">Log in first.</span></span>
    
  
2. <span data-ttu-id="3560a-222">На странице **"Диспетчер учетных записей"** выберите **"Мои доменные имена".**</span><span class="sxs-lookup"><span data-stu-id="3560a-222">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="3560a-223">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="3560a-223">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="3560a-224">На странице **"Domain Names"** (Доменные имена) в области **Text (TXT Records) (Записи TXT)** щелкните **"Edit TXT Records"**(Изменить записи TXT) и выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="3560a-224">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="3560a-225">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="3560a-225">**Host**</span></span>|<span data-ttu-id="3560a-226">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="3560a-226">**TTL**</span></span>|<span data-ttu-id="3560a-227">**Text (Текст)**</span><span class="sxs-lookup"><span data-stu-id="3560a-227">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="3560a-228">3600</span><span class="sxs-lookup"><span data-stu-id="3560a-228">3600</span></span>  <br/> |<span data-ttu-id="3560a-229">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="3560a-229">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="3560a-230">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="3560a-230">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="3560a-231">Выберите **"Продолжить"**.</span><span class="sxs-lookup"><span data-stu-id="3560a-231">Select **Continue**.</span></span>

6. <span data-ttu-id="3560a-232">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="3560a-232">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="3560a-233">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3560a-233">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="3560a-234"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="3560a-234"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="3560a-235">Помните, что web.com за обеспечение этой функциональности.</span><span class="sxs-lookup"><span data-stu-id="3560a-235">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="3560a-236">Если вы видите несоответствия между действиями ниже и текущим графическим пользовательским интерфейсом web.com(Графический пользовательский интерфейс), используйте сообщество [web.com.](https://community.web.com.com/)</span><span class="sxs-lookup"><span data-stu-id="3560a-236">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="3560a-237">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="3560a-237">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="3560a-238">Сначала войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="3560a-238">Log in first.</span></span>
      
2. <span data-ttu-id="3560a-239">На странице **"Диспетчер учетных записей"** выберите **"Мои доменные имена".**</span><span class="sxs-lookup"><span data-stu-id="3560a-239">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="3560a-240">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="3560a-240">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="3560a-241">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="3560a-241">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="3560a-242">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3560a-242">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="3560a-243">**Служба**</span><span class="sxs-lookup"><span data-stu-id="3560a-243">**Service**</span></span>|<span data-ttu-id="3560a-244">**Protocol (Протокол)**</span><span class="sxs-lookup"><span data-stu-id="3560a-244">**Protocol**</span></span>|<span data-ttu-id="3560a-245">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="3560a-245">**TTL**</span></span>|<span data-ttu-id="3560a-246">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="3560a-246">**Priority**</span></span>|<span data-ttu-id="3560a-247">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="3560a-247">**Weight**</span></span>|<span data-ttu-id="3560a-248">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="3560a-248">**Port**</span></span>|<span data-ttu-id="3560a-249">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="3560a-249">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3560a-250">_sip</span><span class="sxs-lookup"><span data-stu-id="3560a-250">_sip</span></span> |<span data-ttu-id="3560a-251">_tls</span><span class="sxs-lookup"><span data-stu-id="3560a-251">_tls</span></span> |<span data-ttu-id="3560a-252">3600</span><span class="sxs-lookup"><span data-stu-id="3560a-252">3600</span></span> | <span data-ttu-id="3560a-253">100</span><span class="sxs-lookup"><span data-stu-id="3560a-253">100</span></span>|<span data-ttu-id="3560a-254">1 </span><span class="sxs-lookup"><span data-stu-id="3560a-254">1</span></span> |<span data-ttu-id="3560a-255">443</span><span class="sxs-lookup"><span data-stu-id="3560a-255">443</span></span> |<span data-ttu-id="3560a-256">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3560a-256">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="3560a-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="3560a-257">_sipfederationtls</span></span> |<span data-ttu-id="3560a-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="3560a-258">_tcp</span></span> |<span data-ttu-id="3560a-259">3600</span><span class="sxs-lookup"><span data-stu-id="3560a-259">3600</span></span> |<span data-ttu-id="3560a-260">100</span><span class="sxs-lookup"><span data-stu-id="3560a-260">100</span></span> |<span data-ttu-id="3560a-261">1 </span><span class="sxs-lookup"><span data-stu-id="3560a-261">1</span></span> |<span data-ttu-id="3560a-262">5061</span><span class="sxs-lookup"><span data-stu-id="3560a-262">5061</span></span> | <span data-ttu-id="3560a-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3560a-263">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="3560a-264">Добавьте другую запись SRV, выбрав значения из второй строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="3560a-264">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="3560a-265">Выберите **"Продолжить"**.</span><span class="sxs-lookup"><span data-stu-id="3560a-265">Select **Continue**.</span></span>

7. <span data-ttu-id="3560a-266">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="3560a-266">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="3560a-p116">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3560a-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
