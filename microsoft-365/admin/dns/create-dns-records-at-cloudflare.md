---
title: Создание записей DNS для Майкрософт на сайте Cloudflare
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
description: Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Cloudflare for Microsoft.
ms.openlocfilehash: 8d5dd7779f07fd42dd230ee33c40849da3519d26
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939276"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="8d2f4-103">Создание записей DNS для Майкрософт на сайте Cloudflare</span><span class="sxs-lookup"><span data-stu-id="8d2f4-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="8d2f4-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="8d2f4-105">Если ваш поставщик услуг размещения DNS  Cloudflare, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="8d2f4-106">После добавления этих записей на сайте Cloudflare ваш домен будет настроен для работы со службами Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
  
> [!NOTE]
>  <span data-ttu-id="8d2f4-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8d2f4-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="8d2f4-110">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="8d2f4-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="8d2f4-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="8d2f4-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="8d2f4-112">Эту процедуру необходимо выполнить на сайте регистратора доменных имен, на котором вы приобрели и зарегистрировали свой домен.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="8d2f4-113">При регистрации в Cloudflare вы добавили домен с помощью процесса **настройки**.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-113">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="8d2f4-114">Добавленный домен был приобретен у Cloudflare или у отдельного регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-114">The domain that you added was purchased from Cloudflare or a separate domain registrar.</span></span> <span data-ttu-id="8d2f4-115">Чтобы проверить и создать записи DNS для вашего домена в Microsoft 365, сначала необходимо изменить их в регистраторе доменных имен, чтобы они использовали их.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-115">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="8d2f4-116">Чтобы самостоятельно изменить серверы доменных имен на веб-сайте регистратора доменных имен, выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="8d2f4-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="8d2f4-117">Найдите на веб-сайте регистратора домена область, в которой можно изменить серверы доменных имен для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="8d2f4-118">Создайте две записи серверов доменных имен, используя значения из приведенной ниже таблицы, либо измените существующие записи серверов доменных имен, чтобы они соответствовали следующим значениям:</span><span class="sxs-lookup"><span data-stu-id="8d2f4-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="8d2f4-119">Основной сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="8d2f4-119">First nameserver</span></span>  <br/> |<span data-ttu-id="8d2f4-120">Используйте значение сервера доменных имен, предоставленное Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-120">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="8d2f4-121">Второстепенный сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="8d2f4-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="8d2f4-122">Используйте значение сервера доменных имен, предоставленное Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-122">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="8d2f4-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-123">You should use at least two name server records.</span></span> <span data-ttu-id="8d2f4-124">Если в списке есть другие серверы доменных имен, их следует удалить.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="8d2f4-125">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8d2f4-126">На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="8d2f4-127">Затем ваша почта Майкрософт и другие службы будут настроены для работы с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-127">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="8d2f4-128">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="8d2f4-128">Add a TXT record for verification</span></span>
<span data-ttu-id="8d2f4-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="8d2f4-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="8d2f4-p105">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-p105">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8d2f4-p106">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="8d2f4-p107">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Cloudflare по [этой ссылке](https://www.cloudflare.com/a/login). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-p107">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="8d2f4-136">На **домашней** странице выберите домен, который нужно обновить.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-136">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="8d2f4-137">На странице **"Обзор"** для домена выберите **DNS.**</span><span class="sxs-lookup"><span data-stu-id="8d2f4-137">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="8d2f4-138">На странице **управления DNS** нажмите кнопку **"Добавить запись"** и выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-138">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    | <span data-ttu-id="8d2f4-139">Тип</span><span class="sxs-lookup"><span data-stu-id="8d2f4-139">Type</span></span> | <span data-ttu-id="8d2f4-140">Имя</span><span class="sxs-lookup"><span data-stu-id="8d2f4-140">Name</span></span> | <span data-ttu-id="8d2f4-141">Automatic TTL</span><span class="sxs-lookup"><span data-stu-id="8d2f4-141">Automatic TTL</span></span> | <span data-ttu-id="8d2f4-142">Контент</span><span class="sxs-lookup"><span data-stu-id="8d2f4-142">Content</span></span> |
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="8d2f4-143">TXT</span><span class="sxs-lookup"><span data-stu-id="8d2f4-143">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="8d2f4-144">30 minutes</span><span class="sxs-lookup"><span data-stu-id="8d2f4-144">30 minutes</span></span>  <br/> |<span data-ttu-id="8d2f4-145">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="8d2f4-145">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="8d2f4-146">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-146">**Note:** This is an example.</span></span> <span data-ttu-id="8d2f4-147">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-147">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="8d2f4-148">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="8d2f4-148">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="8d2f4-149">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-149">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="8d2f4-150">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-150">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="8d2f4-151">Теперь, когда вы добавили запись на сайте регистратора доменных имен, вы вернлись в корпорацию Майкрософт и найдите запись.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-151">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="8d2f4-152">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-152">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="8d2f4-153">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-153">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="8d2f4-154">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-154">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="8d2f4-155">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="8d2f4-155">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="8d2f4-156">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-156">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="8d2f4-p109">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8d2f4-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="8d2f4-160">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-160">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="8d2f4-161"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="8d2f4-161"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="8d2f4-p110">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Cloudflare по [этой ссылке](https://www.cloudflare.com/a/login). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-p110">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="8d2f4-164">На **домашней** странице выберите домен, который нужно обновить.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-164">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="8d2f4-165">На странице **"Обзор"** для домена выберите **DNS.**</span><span class="sxs-lookup"><span data-stu-id="8d2f4-165">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="8d2f4-166">На странице **управления DNS** нажмите кнопку **"Добавить запись"** и выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-166">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    | <span data-ttu-id="8d2f4-167">Тип</span><span class="sxs-lookup"><span data-stu-id="8d2f4-167">Type</span></span> | <span data-ttu-id="8d2f4-168">Имя</span><span class="sxs-lookup"><span data-stu-id="8d2f4-168">Name</span></span> | <span data-ttu-id="8d2f4-169">Почтовый сервер</span><span class="sxs-lookup"><span data-stu-id="8d2f4-169">Mail server</span></span> | <span data-ttu-id="8d2f4-170">Priority (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="8d2f4-170">Priority</span></span> | <span data-ttu-id="8d2f4-171">TTL (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="8d2f4-171">TTL</span></span> |
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8d2f4-172">MX</span><span class="sxs-lookup"><span data-stu-id="8d2f4-172">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="8d2f4-173">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="8d2f4-173">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="8d2f4-174">**Примечание.** Получите свою  *\<domain-key\>*  учетную запись Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-174">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   [<span data-ttu-id="8d2f4-175">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="8d2f4-175">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="8d2f4-176">1 </span><span class="sxs-lookup"><span data-stu-id="8d2f4-176">1</span></span>  <br/> <span data-ttu-id="8d2f4-177">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).   </span><span class="sxs-lookup"><span data-stu-id="8d2f4-177">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/>|<span data-ttu-id="8d2f4-178">30 минут</span><span class="sxs-lookup"><span data-stu-id="8d2f4-178">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="8d2f4-179">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-179">Select **Save**.</span></span>
  
9. <span data-ttu-id="8d2f4-180">Если в разделе **MX Records** (Записи MX) есть другая запись MX, удалите ее, щелкнув значок **Delete (X)** (Удалить).</span><span class="sxs-lookup"><span data-stu-id="8d2f4-180">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="8d2f4-181">В диалоговом окне подтверждения выберите **"Удалить",** чтобы подтвердить изменения.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-181">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="8d2f4-182">Добавление шести записей CNAME, необходимых для Корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8d2f4-182">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="8d2f4-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="8d2f4-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="8d2f4-p112">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Cloudflare по [этой ссылке](https://www.cloudflare.com/a/login). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-p112">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="8d2f4-186">На **домашней** странице выберите домен, который нужно обновить.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-186">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="8d2f4-187">На странице **"Обзор"** для домена выберите **DNS.**</span><span class="sxs-lookup"><span data-stu-id="8d2f4-187">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="8d2f4-188">Добавьте первую из пяти записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-188">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="8d2f4-189">На странице **управления DNS** нажмите кнопку **"Добавить запись"** и выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-189">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    | <span data-ttu-id="8d2f4-190">Тип</span><span class="sxs-lookup"><span data-stu-id="8d2f4-190">Type</span></span> | <span data-ttu-id="8d2f4-191">Имя</span><span class="sxs-lookup"><span data-stu-id="8d2f4-191">Name</span></span> | <span data-ttu-id="8d2f4-192">Target</span><span class="sxs-lookup"><span data-stu-id="8d2f4-192">Target</span></span> | <span data-ttu-id="8d2f4-193">TTL</span><span class="sxs-lookup"><span data-stu-id="8d2f4-193">TTL</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8d2f4-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="8d2f4-194">CNAME</span></span>  <br/> |<span data-ttu-id="8d2f4-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="8d2f4-195">autodiscover</span></span>  <br/> |<span data-ttu-id="8d2f4-196">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="8d2f4-196">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="8d2f4-197">30 minutes</span><span class="sxs-lookup"><span data-stu-id="8d2f4-197">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="8d2f4-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="8d2f4-198">CNAME</span></span>  <br/> |<span data-ttu-id="8d2f4-199">sip</span><span class="sxs-lookup"><span data-stu-id="8d2f4-199">sip</span></span>  <br/> |<span data-ttu-id="8d2f4-200">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8d2f4-200">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="8d2f4-201">30 minutes</span><span class="sxs-lookup"><span data-stu-id="8d2f4-201">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="8d2f4-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="8d2f4-202">CNAME</span></span>  <br/> |<span data-ttu-id="8d2f4-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8d2f4-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="8d2f4-204">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8d2f4-204">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="8d2f4-205">30 minutes</span><span class="sxs-lookup"><span data-stu-id="8d2f4-205">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="8d2f4-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="8d2f4-206">CNAME</span></span>  <br/> |<span data-ttu-id="8d2f4-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="8d2f4-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="8d2f4-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="8d2f4-208">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="8d2f4-209">30 minutes</span><span class="sxs-lookup"><span data-stu-id="8d2f4-209">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="8d2f4-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="8d2f4-210">CNAME</span></span>  <br/> |<span data-ttu-id="8d2f4-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="8d2f4-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="8d2f4-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8d2f4-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="8d2f4-213">30 minutes</span><span class="sxs-lookup"><span data-stu-id="8d2f4-213">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="8d2f4-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="8d2f4-214">CNAME</span></span>  <br/> |<span data-ttu-id="8d2f4-215">msoid</span><span class="sxs-lookup"><span data-stu-id="8d2f4-215">msoid</span></span>  <br/> |<span data-ttu-id="8d2f4-216">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="8d2f4-216">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="8d2f4-217">30 minutes</span><span class="sxs-lookup"><span data-stu-id="8d2f4-217">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="8d2f4-218">Выберите **значок трафика DNS** (измените оранжевый облако на серый), чтобы обойти серверы Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-218">Select the **DNS Traffic** icon (change orange cloud to grey) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="8d2f4-219">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-219">Select **Save**.</span></span>
  
7. <span data-ttu-id="8d2f4-220">Добавьте остальные пять записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-220">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="8d2f4-221">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="8d2f4-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="8d2f4-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="8d2f4-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="8d2f4-223">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="8d2f4-224">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="8d2f4-225">Если вы уже указали запись SPF для домена, не создавайте еще одну для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-225">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="8d2f4-226">Вместо этого добавьте необходимые значения Microsoft 365 в текущую запись. Таким образом, в *одной* записи SPF будут указаны оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-226">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="8d2f4-227">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Cloudflare по [этой ссылке](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="8d2f4-227">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="8d2f4-228">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-228">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="8d2f4-229">На **домашней** странице выберите домен, который нужно обновить.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-229">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="8d2f4-230">На странице **"Обзор"** для домена выберите **DNS.**</span><span class="sxs-lookup"><span data-stu-id="8d2f4-230">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="8d2f4-231">На странице **управления DNS** нажмите кнопку **"Добавить запись"** и выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-231">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    | <span data-ttu-id="8d2f4-232">Тип</span><span class="sxs-lookup"><span data-stu-id="8d2f4-232">Type</span></span> | <span data-ttu-id="8d2f4-233">Имя</span><span class="sxs-lookup"><span data-stu-id="8d2f4-233">Name</span></span> | <span data-ttu-id="8d2f4-234">TTL</span><span class="sxs-lookup"><span data-stu-id="8d2f4-234">TTL</span></span> | <span data-ttu-id="8d2f4-235">Контент</span><span class="sxs-lookup"><span data-stu-id="8d2f4-235">Content</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8d2f4-236">TXT</span><span class="sxs-lookup"><span data-stu-id="8d2f4-236">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="8d2f4-237">30 minutes</span><span class="sxs-lookup"><span data-stu-id="8d2f4-237">30 minutes</span></span>  <br/> |<span data-ttu-id="8d2f4-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="8d2f4-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="8d2f4-239">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="8d2f4-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="8d2f4-240">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-240">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="8d2f4-241">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8d2f4-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="8d2f4-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="8d2f4-242"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="8d2f4-243">Помните, что Cloudflare отвечает за обеспечение этой функциональности.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-243">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="8d2f4-244">Если вы видите несоответствия между действиями ниже и текущим графическим пользовательским интерфейсом Cloudflare( Graphical User Interface), используйте [сообщество Cloudflare.](https://community.cloudflare.com/)</span><span class="sxs-lookup"><span data-stu-id="8d2f4-244">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="8d2f4-245">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Cloudflare по [этой ссылке](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="8d2f4-245">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="8d2f4-246">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-246">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="8d2f4-247">На **домашней** странице выберите домен, который нужно обновить.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-247">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="8d2f4-248">На странице **"Обзор"** для домена выберите **DNS.**</span><span class="sxs-lookup"><span data-stu-id="8d2f4-248">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="8d2f4-249">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-249">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="8d2f4-250">На странице **управления DNS** нажмите кнопку **"Добавить** запись" и выберите значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-250">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    | <span data-ttu-id="8d2f4-251">Type</span><span class="sxs-lookup"><span data-stu-id="8d2f4-251">Type</span></span> | <span data-ttu-id="8d2f4-252">Служба</span><span class="sxs-lookup"><span data-stu-id="8d2f4-252">Service</span></span> | <span data-ttu-id="8d2f4-253">Протокол</span><span class="sxs-lookup"><span data-stu-id="8d2f4-253">Protocol</span></span> | <span data-ttu-id="8d2f4-254">Имя</span><span class="sxs-lookup"><span data-stu-id="8d2f4-254">Name</span></span> | <span data-ttu-id="8d2f4-255">TTL</span><span class="sxs-lookup"><span data-stu-id="8d2f4-255">TTL</span></span> | <span data-ttu-id="8d2f4-256">Priority</span><span class="sxs-lookup"><span data-stu-id="8d2f4-256">Priority</span></span> | <span data-ttu-id="8d2f4-257">Насыщенность</span><span class="sxs-lookup"><span data-stu-id="8d2f4-257">Weight</span></span> | <span data-ttu-id="8d2f4-258">Порт</span><span class="sxs-lookup"><span data-stu-id="8d2f4-258">Port</span></span> | <span data-ttu-id="8d2f4-259">Target</span><span class="sxs-lookup"><span data-stu-id="8d2f4-259">Target</span></span> |
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8d2f4-260">SRV</span><span class="sxs-lookup"><span data-stu-id="8d2f4-260">SRV</span></span>|<span data-ttu-id="8d2f4-261">_sip</span><span class="sxs-lookup"><span data-stu-id="8d2f4-261">_sip</span></span> |<span data-ttu-id="8d2f4-262">TLS</span><span class="sxs-lookup"><span data-stu-id="8d2f4-262">TLS</span></span> |<span data-ttu-id="8d2f4-263">Используйте *domain_name;* например, contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d2f4-263">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="8d2f4-264">30 минут</span><span class="sxs-lookup"><span data-stu-id="8d2f4-264">30 minutes</span></span> | <span data-ttu-id="8d2f4-265">100</span><span class="sxs-lookup"><span data-stu-id="8d2f4-265">100</span></span>|<span data-ttu-id="8d2f4-266">1 </span><span class="sxs-lookup"><span data-stu-id="8d2f4-266">1</span></span> |<span data-ttu-id="8d2f4-267">443</span><span class="sxs-lookup"><span data-stu-id="8d2f4-267">443</span></span> |<span data-ttu-id="8d2f4-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8d2f4-268">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="8d2f4-269">SRV</span><span class="sxs-lookup"><span data-stu-id="8d2f4-269">SRV</span></span>|<span data-ttu-id="8d2f4-270">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="8d2f4-270">_sipfederationtls</span></span> | <span data-ttu-id="8d2f4-271">TCP</span><span class="sxs-lookup"><span data-stu-id="8d2f4-271">TCP</span></span>|<span data-ttu-id="8d2f4-272">Используйте *domain_name;* например, contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d2f4-272">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="8d2f4-273">30 минут</span><span class="sxs-lookup"><span data-stu-id="8d2f4-273">30 minutes</span></span> |<span data-ttu-id="8d2f4-274">100</span><span class="sxs-lookup"><span data-stu-id="8d2f4-274">100</span></span> |<span data-ttu-id="8d2f4-275">1 </span><span class="sxs-lookup"><span data-stu-id="8d2f4-275">1</span></span> |<span data-ttu-id="8d2f4-276">5061</span><span class="sxs-lookup"><span data-stu-id="8d2f4-276">5061</span></span> | <span data-ttu-id="8d2f4-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8d2f4-277">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="8d2f4-278">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-278">Select **Save**.</span></span>

  
6. <span data-ttu-id="8d2f4-279">Добавьте другую запись SRV, выбрав значения из второй строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="8d2f4-279">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="8d2f4-p117">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8d2f4-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
