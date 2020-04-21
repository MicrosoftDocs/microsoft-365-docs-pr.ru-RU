---
title: Создание записей DNS на сайте cloudflare для Майкрософт
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
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу cloudflare для Майкрософт.
ms.openlocfilehash: f04e4b4a29085a3ddd9b388c7178c1cd638445ea
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629711"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="88171-103">Создание записей DNS на сайте cloudflare для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="88171-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="88171-104">Если вы не нашли то, что вы ищете, обратитесь к разделу **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="88171-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="88171-105">Если ваш поставщик услуг размещения DNS  Cloudflare, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб.</span><span class="sxs-lookup"><span data-stu-id="88171-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="88171-106">Когда вы добавите эти записи на сайте cloudflare, ваш домен будет настроен для работы со службами Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="88171-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
<span data-ttu-id="88171-107">Чтобы узнать о размещении и DNS для веб-сайтов с помощью Microsoft, ознакомьтесь со статьей [использование общедоступного веб-сайта с корпорацией Майкрософт](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="88171-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="88171-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="88171-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="88171-111">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="88171-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="88171-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="88171-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="88171-113">Эту процедуру необходимо выполнить на сайте регистратора доменных имен, на котором вы приобрели и зарегистрировали свой домен.</span><span class="sxs-lookup"><span data-stu-id="88171-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="88171-114">При регистрации в Cloudflare вы добавили домен с помощью процесса **настройки**.</span><span class="sxs-lookup"><span data-stu-id="88171-114">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="88171-115">Домен, который вы добавили, был приобретен у стороннего регистратора доменных имен; Cloudflare не предоставляет услуг по регистрации доменных имен.</span><span class="sxs-lookup"><span data-stu-id="88171-115">The domain that you added was purchased from a separate domain registrar; Cloudflare does not offer domain registration services.</span></span> <span data-ttu-id="88171-116">Чтобы проверить и создать записи DNS для вашего домена в Microsoft 365, сначала необходимо изменить серверов доменных имен в регистраторе доменных имен, чтобы они использовали cloudflare серверов доменных имен.</span><span class="sxs-lookup"><span data-stu-id="88171-116">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="88171-117">Чтобы самостоятельно изменить серверы доменных имен на веб-сайте регистратора доменных имен, выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="88171-117">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="88171-118">Найдите на веб-сайте регистратора домена область, в которой можно изменить серверы доменных имен для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="88171-118">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="88171-119">Создайте две записи серверов доменных имен, используя значения из приведенной ниже таблицы, либо измените существующие записи серверов доменных имен, чтобы они соответствовали следующим значениям:</span><span class="sxs-lookup"><span data-stu-id="88171-119">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="88171-120">Основной сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="88171-120">First nameserver</span></span>  <br/> |<span data-ttu-id="88171-121">Используйте значение сервера доменных имен, предоставленное Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="88171-121">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="88171-122">Второстепенный сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="88171-122">Second nameserver</span></span>  <br/> |<span data-ttu-id="88171-123">Используйте значение сервера доменных имен, предоставленное Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="88171-123">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="88171-124">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="88171-124">You should use at least two name server records.</span></span> <span data-ttu-id="88171-125">Если в списке указаны другие серверы имен, их следует удалить.</span><span class="sxs-lookup"><span data-stu-id="88171-125">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="88171-126">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="88171-126">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="88171-127">На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="88171-127">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="88171-128">После этого ваша электронная почта Майкрософт и другие службы будут настроены для работы с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="88171-128">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="88171-129">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="88171-129">Add a TXT record for verification</span></span>
<span data-ttu-id="88171-130"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="88171-130"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="88171-131">Перед использованием домена с корпорацией Майкрософт необходимо убедиться, что вы являетесь его владельцем.</span><span class="sxs-lookup"><span data-stu-id="88171-131">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="88171-132">Вы можете войти в свою учетную запись у вас в вашем регистраторе доменных имен и создать запись DNS в Майкрософт, если вы владеете этим доменом.</span><span class="sxs-lookup"><span data-stu-id="88171-132">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="88171-p106">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="88171-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="88171-135">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Cloudflare по [этой ссылке](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="88171-135">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="88171-136">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="88171-136">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="88171-137">На **домашней** странице выберите домен, который вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="88171-137">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="88171-138">На странице **Обзор** домена выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="88171-138">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="88171-139">На странице " **Управление DNS** " нажмите кнопку **Добавить запись**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="88171-139">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="88171-140">**Тип**</span><span class="sxs-lookup"><span data-stu-id="88171-140">**Type**</span></span>|<span data-ttu-id="88171-141">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="88171-141">**Name**</span></span>|<span data-ttu-id="88171-142">**Automatic TTL**</span><span class="sxs-lookup"><span data-stu-id="88171-142">**Automatic TTL**</span></span>|<span data-ttu-id="88171-143">**Content (Содержимое)**</span><span class="sxs-lookup"><span data-stu-id="88171-143">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="88171-144">TXT</span><span class="sxs-lookup"><span data-stu-id="88171-144">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="88171-145">30 мин.</span><span class="sxs-lookup"><span data-stu-id="88171-145">30 minutes</span></span>  <br/> |<span data-ttu-id="88171-146">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="88171-146">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="88171-147">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="88171-147">**Note:** This is an example.</span></span> <span data-ttu-id="88171-148">Используйте указанную здесь **конечную точку или значение адреса** из таблицы.</span><span class="sxs-lookup"><span data-stu-id="88171-148">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="88171-149">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="88171-149">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="88171-150">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="88171-150">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="88171-151">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="88171-151">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="88171-152">Теперь, когда вы добавили запись на сайт регистратора доменных имен, вернитесь в корпорацию Майкрософт и найдите запись.</span><span class="sxs-lookup"><span data-stu-id="88171-152">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="88171-153">После того как корпорация Майкрософт обнаружит правильную запись TXT, ваш домен будет проверен.</span><span class="sxs-lookup"><span data-stu-id="88171-153">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="88171-154">В центре администрирования Майкрософт перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> **параметров** \> ".</span><span class="sxs-lookup"><span data-stu-id="88171-154">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="88171-155">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="88171-155">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="88171-156">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="88171-156">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="88171-157">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="88171-157">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="88171-p109">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="88171-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="88171-161">Добавление записи MX для отправки электронной почты для вашего домена в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="88171-161">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="88171-162"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="88171-162"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="88171-p110">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Cloudflare по [этой ссылке](https://www.cloudflare.com/a/login). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="88171-p110">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="88171-165">На **домашней** странице выберите домен, который вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="88171-165">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="88171-166">На странице **Обзор** домена выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="88171-166">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="88171-167">На странице " **Управление DNS** " нажмите кнопку **Добавить запись**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="88171-167">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="88171-168">**Тип**</span><span class="sxs-lookup"><span data-stu-id="88171-168">**Type**</span></span>|<span data-ttu-id="88171-169">**Имя**</span><span class="sxs-lookup"><span data-stu-id="88171-169">**Name**</span></span>|<span data-ttu-id="88171-170">**Mail Server (Почтовый сервер)**</span><span class="sxs-lookup"><span data-stu-id="88171-170">**Mail server**</span></span>|<span data-ttu-id="88171-171">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="88171-171">**Priority**</span></span>|<span data-ttu-id="88171-172">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="88171-172">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="88171-173">MX</span><span class="sxs-lookup"><span data-stu-id="88171-173">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="88171-174">*\<ключ-домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="88171-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="88171-175">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="88171-175">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   [<span data-ttu-id="88171-176">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="88171-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="88171-177">1,1</span><span class="sxs-lookup"><span data-stu-id="88171-177">1</span></span>  <br/> <span data-ttu-id="88171-178">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).   </span><span class="sxs-lookup"><span data-stu-id="88171-178">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/>|<span data-ttu-id="88171-179">30 мин.</span><span class="sxs-lookup"><span data-stu-id="88171-179">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="88171-180">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="88171-180">Select **Save**.</span></span>
  
9. <span data-ttu-id="88171-181">Если в разделе **MX Records** (Записи MX) есть другая запись MX, удалите ее, щелкнув значок **Delete (X)** (Удалить).</span><span class="sxs-lookup"><span data-stu-id="88171-181">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="88171-182">В диалоговом окне подтверждения нажмите кнопку **Удалить** , чтобы подтвердить изменения.</span><span class="sxs-lookup"><span data-stu-id="88171-182">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="88171-183">Добавление шести записей CNAME, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="88171-183">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="88171-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="88171-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="88171-p112">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Cloudflare по [этой ссылке](https://www.cloudflare.com/a/login). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="88171-p112">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="88171-187">На **домашней** странице выберите домен, который вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="88171-187">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="88171-188">На странице **Обзор** домена выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="88171-188">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="88171-189">Добавьте первую из пяти записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="88171-189">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="88171-190">На странице " **Управление DNS** " нажмите кнопку **Добавить запись**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="88171-190">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="88171-191">**Тип**</span><span class="sxs-lookup"><span data-stu-id="88171-191">**Type**</span></span>|<span data-ttu-id="88171-192">**Name** (Имя)</span><span class="sxs-lookup"><span data-stu-id="88171-192">**Name**</span></span>|<span data-ttu-id="88171-193">**Target** (Целевое значение)</span><span class="sxs-lookup"><span data-stu-id="88171-193">**Target**</span></span>|<span data-ttu-id="88171-194">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="88171-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="88171-195">CNAME</span><span class="sxs-lookup"><span data-stu-id="88171-195">CNAME</span></span>  <br/> |<span data-ttu-id="88171-196">autodiscover</span><span class="sxs-lookup"><span data-stu-id="88171-196">autodiscover</span></span>  <br/> |<span data-ttu-id="88171-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="88171-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="88171-198">30 minutes</span><span class="sxs-lookup"><span data-stu-id="88171-198">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="88171-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="88171-199">CNAME</span></span>  <br/> |<span data-ttu-id="88171-200">sip</span><span class="sxs-lookup"><span data-stu-id="88171-200">sip</span></span>  <br/> |<span data-ttu-id="88171-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="88171-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="88171-202">30 minutes</span><span class="sxs-lookup"><span data-stu-id="88171-202">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="88171-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="88171-203">CNAME</span></span>  <br/> |<span data-ttu-id="88171-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="88171-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="88171-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="88171-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="88171-206">30 minutes</span><span class="sxs-lookup"><span data-stu-id="88171-206">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="88171-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="88171-207">CNAME</span></span>  <br/> |<span data-ttu-id="88171-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="88171-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="88171-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="88171-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="88171-210">30 minutes</span><span class="sxs-lookup"><span data-stu-id="88171-210">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="88171-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="88171-211">CNAME</span></span>  <br/> |<span data-ttu-id="88171-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="88171-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="88171-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="88171-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="88171-214">30 minutes</span><span class="sxs-lookup"><span data-stu-id="88171-214">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="88171-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="88171-215">CNAME</span></span>  <br/> |<span data-ttu-id="88171-216">msoid</span><span class="sxs-lookup"><span data-stu-id="88171-216">msoid</span></span>  <br/> |<span data-ttu-id="88171-217">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="88171-217">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="88171-218">30 minutes</span><span class="sxs-lookup"><span data-stu-id="88171-218">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="88171-219">Выберите значок **трафика DNS** (оранжевый облако), чтобы обойти серверы cloudflare.</span><span class="sxs-lookup"><span data-stu-id="88171-219">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="88171-220">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="88171-220">Select **Save**.</span></span>
  
7. <span data-ttu-id="88171-221">Добавьте остальные пять записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="88171-221">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="88171-222">Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама</span><span class="sxs-lookup"><span data-stu-id="88171-222">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="88171-223"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="88171-223"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="88171-224">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="88171-224">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="88171-225">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="88171-225">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="88171-226">Если у вас уже есть запись SPF для вашего домена, не создавайте ее для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="88171-226">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="88171-227">Вместо этого добавьте необходимые значения Microsoft 365 к текущей записи, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="88171-227">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="88171-228">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Cloudflare по [этой ссылке](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="88171-228">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="88171-229">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="88171-229">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="88171-230">На **домашней** странице выберите домен, который вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="88171-230">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="88171-231">На странице **Обзор** домена выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="88171-231">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="88171-232">На странице " **Управление DNS** " нажмите кнопку **Добавить запись**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="88171-232">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="88171-233">**Тип**</span><span class="sxs-lookup"><span data-stu-id="88171-233">**Type**</span></span>|<span data-ttu-id="88171-234">**Имя**</span><span class="sxs-lookup"><span data-stu-id="88171-234">**Name**</span></span>|<span data-ttu-id="88171-235">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="88171-235">**TTL**</span></span>|<span data-ttu-id="88171-236">**Content (Содержимое)**</span><span class="sxs-lookup"><span data-stu-id="88171-236">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="88171-237">TXT</span><span class="sxs-lookup"><span data-stu-id="88171-237">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="88171-238">30 мин.</span><span class="sxs-lookup"><span data-stu-id="88171-238">30 minutes</span></span>  <br/> |<span data-ttu-id="88171-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="88171-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="88171-240">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="88171-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="88171-241">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="88171-241">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="88171-242">Добавление двух записей SRV, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="88171-242">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="88171-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="88171-243"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="88171-244">Имейте в виду, что cloudflare отвечает за обеспечение доступности этой функции.</span><span class="sxs-lookup"><span data-stu-id="88171-244">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="88171-245">Если вы видите несоответствия между действиями ниже и текущим ГРАФИЧЕСКИм пользовательским интерфейсом cloudflare (графический пользовательский интерфейс), воспользуйтесь [сообществом cloudflare](https://community.cloudflare.com/).</span><span class="sxs-lookup"><span data-stu-id="88171-245">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="88171-246">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Cloudflare по [этой ссылке](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="88171-246">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="88171-247">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="88171-247">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="88171-248">На **домашней** странице выберите домен, который вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="88171-248">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="88171-249">На странице **Обзор** домена выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="88171-249">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="88171-250">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="88171-250">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="88171-251">На странице " **Управление DNS** " нажмите кнопку **Добавить запись**, а затем выберите значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="88171-251">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="88171-252">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="88171-252">**Type**</span></span>|<span data-ttu-id="88171-253">**Service (Служба)**</span><span class="sxs-lookup"><span data-stu-id="88171-253">**Service**</span></span>|<span data-ttu-id="88171-254">**Protocol (Протокол)**</span><span class="sxs-lookup"><span data-stu-id="88171-254">**Protocol**</span></span>|<span data-ttu-id="88171-255">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="88171-255">**Name**</span></span>|<span data-ttu-id="88171-256">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="88171-256">**TTL**</span></span>|<span data-ttu-id="88171-257">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="88171-257">**Priority**</span></span>|<span data-ttu-id="88171-258">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="88171-258">**Weight**</span></span>|<span data-ttu-id="88171-259">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="88171-259">**Port**</span></span>|<span data-ttu-id="88171-260">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="88171-260">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="88171-261">SRV</span><span class="sxs-lookup"><span data-stu-id="88171-261">SRV</span></span>|<span data-ttu-id="88171-262">_sip</span><span class="sxs-lookup"><span data-stu-id="88171-262">_sip</span></span> |<span data-ttu-id="88171-263">TLS</span><span class="sxs-lookup"><span data-stu-id="88171-263">TLS</span></span> |<span data-ttu-id="88171-264">Использование *domain_name*; Например, contoso.com</span><span class="sxs-lookup"><span data-stu-id="88171-264">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="88171-265">30 мин.</span><span class="sxs-lookup"><span data-stu-id="88171-265">30 minutes</span></span> | <span data-ttu-id="88171-266">100</span><span class="sxs-lookup"><span data-stu-id="88171-266">100</span></span>|<span data-ttu-id="88171-267">1,1</span><span class="sxs-lookup"><span data-stu-id="88171-267">1</span></span> |<span data-ttu-id="88171-268">443</span><span class="sxs-lookup"><span data-stu-id="88171-268">443</span></span> |<span data-ttu-id="88171-269">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="88171-269">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="88171-270">SRV</span><span class="sxs-lookup"><span data-stu-id="88171-270">SRV</span></span>|<span data-ttu-id="88171-271">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="88171-271">_sipfederationtls</span></span> | <span data-ttu-id="88171-272">TCP</span><span class="sxs-lookup"><span data-stu-id="88171-272">TCP</span></span>|<span data-ttu-id="88171-273">Использование *domain_name*; Например, contoso.com</span><span class="sxs-lookup"><span data-stu-id="88171-273">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="88171-274">30 мин.</span><span class="sxs-lookup"><span data-stu-id="88171-274">30 minutes</span></span> |<span data-ttu-id="88171-275">100</span><span class="sxs-lookup"><span data-stu-id="88171-275">100</span></span> |<span data-ttu-id="88171-276">1,1</span><span class="sxs-lookup"><span data-stu-id="88171-276">1</span></span> |<span data-ttu-id="88171-277">5061</span><span class="sxs-lookup"><span data-stu-id="88171-277">5061</span></span> | <span data-ttu-id="88171-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="88171-278">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="88171-279">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="88171-279">Select **Save**.</span></span>

  
6. <span data-ttu-id="88171-280">Добавьте другую запись SRV, выбрав значения из второй строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="88171-280">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="88171-p117">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="88171-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
