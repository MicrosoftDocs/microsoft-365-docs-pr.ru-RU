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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу cloudflare для Майкрософт.
ms.openlocfilehash: 9b717ddedaf6435f6599f4f75cc0fa7c4e618d59
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400549"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="0fe9a-103">Создание записей DNS на сайте cloudflare для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="0fe9a-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="0fe9a-104">Если вы не нашли то, что вы ищете, обратитесь к разделу **[вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="0fe9a-105">Если ваш поставщик услуг размещения DNS  Cloudflare, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="0fe9a-106">Когда вы добавите эти записи на сайте cloudflare, ваш домен будет настроен для работы со службами Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
  
> [!NOTE]
>  <span data-ttu-id="0fe9a-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0fe9a-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="0fe9a-110">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="0fe9a-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="0fe9a-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="0fe9a-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="0fe9a-112">Эту процедуру необходимо выполнить на сайте регистратора доменных имен, на котором вы приобрели и зарегистрировали свой домен.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="0fe9a-113">При регистрации в Cloudflare вы добавили домен с помощью процесса **настройки**.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-113">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="0fe9a-114">Добавленный домен был приобретен у cloudflare или отдельного регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-114">The domain that you added was purchased from Cloudflare or a separate domain registrar.</span></span> <span data-ttu-id="0fe9a-115">Чтобы проверить и создать записи DNS для вашего домена в Microsoft 365, сначала необходимо изменить серверов доменных имен в регистраторе доменных имен, чтобы они использовали cloudflare серверов доменных имен.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-115">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="0fe9a-116">Чтобы самостоятельно изменить серверы доменных имен на веб-сайте регистратора доменных имен, выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="0fe9a-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="0fe9a-117">Найдите на веб-сайте регистратора домена область, в которой можно изменить серверы доменных имен для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="0fe9a-118">Создайте две записи серверов доменных имен, используя значения из приведенной ниже таблицы, либо измените существующие записи серверов доменных имен, чтобы они соответствовали следующим значениям:</span><span class="sxs-lookup"><span data-stu-id="0fe9a-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="0fe9a-119">Основной сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="0fe9a-119">First nameserver</span></span>  <br/> |<span data-ttu-id="0fe9a-120">Используйте значение сервера доменных имен, предоставленное Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-120">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="0fe9a-121">Второстепенный сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="0fe9a-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="0fe9a-122">Используйте значение сервера доменных имен, предоставленное Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-122">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="0fe9a-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-123">You should use at least two name server records.</span></span> <span data-ttu-id="0fe9a-124">Если в списке указаны другие серверы имен, их следует удалить.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="0fe9a-125">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0fe9a-126">На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="0fe9a-127">После этого ваша электронная почта Майкрософт и другие службы будут настроены для работы с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-127">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="0fe9a-128">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="0fe9a-128">Add a TXT record for verification</span></span>
<span data-ttu-id="0fe9a-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="0fe9a-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="0fe9a-p105">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-p105">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0fe9a-p106">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="0fe9a-134">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Cloudflare по [этой ссылке](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="0fe9a-134">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="0fe9a-135">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-135">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="0fe9a-136">На **домашней** странице выберите домен, который вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-136">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="0fe9a-137">На странице **Обзор** домена выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-137">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="0fe9a-138">На странице " **Управление DNS** " нажмите кнопку **Добавить запись**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-138">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="0fe9a-139">**Тип**</span><span class="sxs-lookup"><span data-stu-id="0fe9a-139">**Type**</span></span>|<span data-ttu-id="0fe9a-140">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="0fe9a-140">**Name**</span></span>|<span data-ttu-id="0fe9a-141">**Automatic TTL**</span><span class="sxs-lookup"><span data-stu-id="0fe9a-141">**Automatic TTL**</span></span>|<span data-ttu-id="0fe9a-142">**Content (Содержимое)**</span><span class="sxs-lookup"><span data-stu-id="0fe9a-142">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="0fe9a-143">TXT</span><span class="sxs-lookup"><span data-stu-id="0fe9a-143">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="0fe9a-144">30 мин.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-144">30 minutes</span></span>  <br/> |<span data-ttu-id="0fe9a-145">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="0fe9a-145">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="0fe9a-146">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-146">**Note:** This is an example.</span></span> <span data-ttu-id="0fe9a-147">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-147">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="0fe9a-148">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="0fe9a-148">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="0fe9a-149">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-149">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="0fe9a-150">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-150">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="0fe9a-151">Теперь, когда вы добавили запись на сайт регистратора доменных имен, вернитесь в корпорацию Майкрософт и найдите запись.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-151">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="0fe9a-152">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-152">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="0fe9a-153">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-153">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="0fe9a-154">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-154">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="0fe9a-155">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="0fe9a-155">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="0fe9a-156">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-156">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="0fe9a-p109">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0fe9a-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="0fe9a-160">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-160">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="0fe9a-161"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="0fe9a-161"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="0fe9a-p110">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Cloudflare по [этой ссылке](https://www.cloudflare.com/a/login). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-p110">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="0fe9a-164">На **домашней** странице выберите домен, который вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-164">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="0fe9a-165">На странице **Обзор** домена выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-165">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="0fe9a-166">На странице " **Управление DNS** " нажмите кнопку **Добавить запись**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-166">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="0fe9a-167">**Тип**</span><span class="sxs-lookup"><span data-stu-id="0fe9a-167">**Type**</span></span>|<span data-ttu-id="0fe9a-168">**Имя**</span><span class="sxs-lookup"><span data-stu-id="0fe9a-168">**Name**</span></span>|<span data-ttu-id="0fe9a-169">**Mail Server (Почтовый сервер)**</span><span class="sxs-lookup"><span data-stu-id="0fe9a-169">**Mail server**</span></span>|<span data-ttu-id="0fe9a-170">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="0fe9a-170">**Priority**</span></span>|<span data-ttu-id="0fe9a-171">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="0fe9a-171">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0fe9a-172">MX</span><span class="sxs-lookup"><span data-stu-id="0fe9a-172">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="0fe9a-173">*\<domain-key\>*. mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="0fe9a-173">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="0fe9a-174">**Примечание:** Получите свою *\<domain-key\>* учетную запись от вашей учетной записи Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-174">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   [<span data-ttu-id="0fe9a-175">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="0fe9a-175">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="0fe9a-176">1 </span><span class="sxs-lookup"><span data-stu-id="0fe9a-176">1</span></span>  <br/> <span data-ttu-id="0fe9a-177">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).   </span><span class="sxs-lookup"><span data-stu-id="0fe9a-177">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/>|<span data-ttu-id="0fe9a-178">30 мин.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-178">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="0fe9a-179">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-179">Select **Save**.</span></span>
  
9. <span data-ttu-id="0fe9a-180">Если в разделе **MX Records** (Записи MX) есть другая запись MX, удалите ее, щелкнув значок **Delete (X)** (Удалить).</span><span class="sxs-lookup"><span data-stu-id="0fe9a-180">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="0fe9a-181">В диалоговом окне подтверждения нажмите кнопку **Удалить** , чтобы подтвердить изменения.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-181">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="0fe9a-182">Добавление шести записей CNAME, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="0fe9a-182">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="0fe9a-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="0fe9a-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="0fe9a-p112">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Cloudflare по [этой ссылке](https://www.cloudflare.com/a/login). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-p112">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="0fe9a-186">На **домашней** странице выберите домен, который вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-186">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="0fe9a-187">На странице **Обзор** домена выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-187">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="0fe9a-188">Добавьте первую из пяти записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-188">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="0fe9a-189">На странице " **Управление DNS** " нажмите кнопку **Добавить запись**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-189">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="0fe9a-190">**Тип**</span><span class="sxs-lookup"><span data-stu-id="0fe9a-190">**Type**</span></span>|<span data-ttu-id="0fe9a-191">**Name** (Имя)</span><span class="sxs-lookup"><span data-stu-id="0fe9a-191">**Name**</span></span>|<span data-ttu-id="0fe9a-192">**Target** (Целевое значение)</span><span class="sxs-lookup"><span data-stu-id="0fe9a-192">**Target**</span></span>|<span data-ttu-id="0fe9a-193">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="0fe9a-193">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0fe9a-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="0fe9a-194">CNAME</span></span>  <br/> |<span data-ttu-id="0fe9a-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="0fe9a-195">autodiscover</span></span>  <br/> |<span data-ttu-id="0fe9a-196">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="0fe9a-196">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="0fe9a-197">30 minutes</span><span class="sxs-lookup"><span data-stu-id="0fe9a-197">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="0fe9a-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="0fe9a-198">CNAME</span></span>  <br/> |<span data-ttu-id="0fe9a-199">sip</span><span class="sxs-lookup"><span data-stu-id="0fe9a-199">sip</span></span>  <br/> |<span data-ttu-id="0fe9a-200">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0fe9a-200">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="0fe9a-201">30 minutes</span><span class="sxs-lookup"><span data-stu-id="0fe9a-201">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="0fe9a-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="0fe9a-202">CNAME</span></span>  <br/> |<span data-ttu-id="0fe9a-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="0fe9a-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="0fe9a-204">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0fe9a-204">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="0fe9a-205">30 minutes</span><span class="sxs-lookup"><span data-stu-id="0fe9a-205">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="0fe9a-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="0fe9a-206">CNAME</span></span>  <br/> |<span data-ttu-id="0fe9a-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="0fe9a-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="0fe9a-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="0fe9a-208">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="0fe9a-209">30 minutes</span><span class="sxs-lookup"><span data-stu-id="0fe9a-209">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="0fe9a-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="0fe9a-210">CNAME</span></span>  <br/> |<span data-ttu-id="0fe9a-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="0fe9a-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="0fe9a-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="0fe9a-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="0fe9a-213">30 minutes</span><span class="sxs-lookup"><span data-stu-id="0fe9a-213">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="0fe9a-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="0fe9a-214">CNAME</span></span>  <br/> |<span data-ttu-id="0fe9a-215">msoid</span><span class="sxs-lookup"><span data-stu-id="0fe9a-215">msoid</span></span>  <br/> |<span data-ttu-id="0fe9a-216">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="0fe9a-216">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="0fe9a-217">30 minutes</span><span class="sxs-lookup"><span data-stu-id="0fe9a-217">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="0fe9a-218">Выберите значок **трафика DNS** (оранжевый облако), чтобы обойти серверы cloudflare.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-218">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="0fe9a-219">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-219">Select **Save**.</span></span>
  
7. <span data-ttu-id="0fe9a-220">Добавьте остальные пять записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-220">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="0fe9a-221">Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама</span><span class="sxs-lookup"><span data-stu-id="0fe9a-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="0fe9a-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="0fe9a-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="0fe9a-223">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="0fe9a-224">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="0fe9a-225">Если вы уже указали запись SPF для домена, не создавайте еще одну для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-225">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="0fe9a-226">Вместо этого добавьте необходимые значения Microsoft 365 в текущую запись. Таким образом, в *одной* записи SPF будут указаны оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-226">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="0fe9a-227">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Cloudflare по [этой ссылке](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="0fe9a-227">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="0fe9a-228">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-228">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="0fe9a-229">На **домашней** странице выберите домен, который вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-229">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="0fe9a-230">На странице **Обзор** домена выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-230">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="0fe9a-231">На странице " **Управление DNS** " нажмите кнопку **Добавить запись**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-231">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="0fe9a-232">**Тип**</span><span class="sxs-lookup"><span data-stu-id="0fe9a-232">**Type**</span></span>|<span data-ttu-id="0fe9a-233">**Имя**</span><span class="sxs-lookup"><span data-stu-id="0fe9a-233">**Name**</span></span>|<span data-ttu-id="0fe9a-234">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="0fe9a-234">**TTL**</span></span>|<span data-ttu-id="0fe9a-235">**Content (Содержимое)**</span><span class="sxs-lookup"><span data-stu-id="0fe9a-235">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0fe9a-236">TXT</span><span class="sxs-lookup"><span data-stu-id="0fe9a-236">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="0fe9a-237">30 мин.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-237">30 minutes</span></span>  <br/> |<span data-ttu-id="0fe9a-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="0fe9a-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="0fe9a-239">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="0fe9a-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="0fe9a-240">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-240">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="0fe9a-241">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="0fe9a-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="0fe9a-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="0fe9a-242"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="0fe9a-243">Имейте в виду, что cloudflare отвечает за обеспечение доступности этой функции.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-243">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="0fe9a-244">Если вы видите несоответствия между действиями ниже и текущим ГРАФИЧЕСКИм пользовательским интерфейсом cloudflare (графический пользовательский интерфейс), воспользуйтесь [сообществом cloudflare](https://community.cloudflare.com/).</span><span class="sxs-lookup"><span data-stu-id="0fe9a-244">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="0fe9a-245">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Cloudflare по [этой ссылке](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="0fe9a-245">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="0fe9a-246">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-246">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="0fe9a-247">На **домашней** странице выберите домен, который вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-247">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="0fe9a-248">На странице **Обзор** домена выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-248">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="0fe9a-249">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-249">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="0fe9a-250">На странице " **Управление DNS** " нажмите кнопку **Добавить запись**, а затем выберите значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-250">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="0fe9a-251">**Тип**</span><span class="sxs-lookup"><span data-stu-id="0fe9a-251">**Type**</span></span>|<span data-ttu-id="0fe9a-252">**Service (Служба)**</span><span class="sxs-lookup"><span data-stu-id="0fe9a-252">**Service**</span></span>|<span data-ttu-id="0fe9a-253">**Protocol (Протокол)**</span><span class="sxs-lookup"><span data-stu-id="0fe9a-253">**Protocol**</span></span>|<span data-ttu-id="0fe9a-254">**Name** (Имя)</span><span class="sxs-lookup"><span data-stu-id="0fe9a-254">**Name**</span></span>|<span data-ttu-id="0fe9a-255">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="0fe9a-255">**TTL**</span></span>|<span data-ttu-id="0fe9a-256">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="0fe9a-256">**Priority**</span></span>|<span data-ttu-id="0fe9a-257">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="0fe9a-257">**Weight**</span></span>|<span data-ttu-id="0fe9a-258">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="0fe9a-258">**Port**</span></span>|<span data-ttu-id="0fe9a-259">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="0fe9a-259">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0fe9a-260">SRV</span><span class="sxs-lookup"><span data-stu-id="0fe9a-260">SRV</span></span>|<span data-ttu-id="0fe9a-261">_sip</span><span class="sxs-lookup"><span data-stu-id="0fe9a-261">_sip</span></span> |<span data-ttu-id="0fe9a-262">TLS</span><span class="sxs-lookup"><span data-stu-id="0fe9a-262">TLS</span></span> |<span data-ttu-id="0fe9a-263">Использование *domain_name*; Например, contoso.com</span><span class="sxs-lookup"><span data-stu-id="0fe9a-263">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="0fe9a-264">30 мин.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-264">30 minutes</span></span> | <span data-ttu-id="0fe9a-265">100</span><span class="sxs-lookup"><span data-stu-id="0fe9a-265">100</span></span>|<span data-ttu-id="0fe9a-266">1 </span><span class="sxs-lookup"><span data-stu-id="0fe9a-266">1</span></span> |<span data-ttu-id="0fe9a-267">443</span><span class="sxs-lookup"><span data-stu-id="0fe9a-267">443</span></span> |<span data-ttu-id="0fe9a-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0fe9a-268">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="0fe9a-269">SRV</span><span class="sxs-lookup"><span data-stu-id="0fe9a-269">SRV</span></span>|<span data-ttu-id="0fe9a-270">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="0fe9a-270">_sipfederationtls</span></span> | <span data-ttu-id="0fe9a-271">TCP</span><span class="sxs-lookup"><span data-stu-id="0fe9a-271">TCP</span></span>|<span data-ttu-id="0fe9a-272">Использование *domain_name*; Например, contoso.com</span><span class="sxs-lookup"><span data-stu-id="0fe9a-272">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="0fe9a-273">30 мин.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-273">30 minutes</span></span> |<span data-ttu-id="0fe9a-274">100</span><span class="sxs-lookup"><span data-stu-id="0fe9a-274">100</span></span> |<span data-ttu-id="0fe9a-275">1 </span><span class="sxs-lookup"><span data-stu-id="0fe9a-275">1</span></span> |<span data-ttu-id="0fe9a-276">5061</span><span class="sxs-lookup"><span data-stu-id="0fe9a-276">5061</span></span> | <span data-ttu-id="0fe9a-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0fe9a-277">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="0fe9a-278">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-278">Select **Save**.</span></span>

  
6. <span data-ttu-id="0fe9a-279">Добавьте другую запись SRV, выбрав значения из второй строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="0fe9a-279">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="0fe9a-p117">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0fe9a-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
