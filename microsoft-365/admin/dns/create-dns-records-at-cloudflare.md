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
ms.openlocfilehash: ccd629dfdec24e509144c205b748a883cb65d554
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919631"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="b060d-103">Создание записей DNS на сайте cloudflare для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b060d-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="b060d-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="b060d-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b060d-105">Если ваш поставщик услуг размещения DNS  Cloudflare, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб.</span><span class="sxs-lookup"><span data-stu-id="b060d-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="b060d-106">Когда вы добавите эти записи на сайте cloudflare, ваш домен будет настроен для работы со службами Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b060d-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
<span data-ttu-id="b060d-107">Дополнительные сведения о веб-хостинге и DNS для веб-сайтов при работе с продуктами корпорации Майкрософт см. в статье [Использование общедоступного веб-сайта при работе с продуктами корпорации Майкрософт](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="b060d-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="b060d-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b060d-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="b060d-111">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="b060d-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="b060d-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="b060d-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b060d-113">Эту процедуру необходимо выполнить на сайте регистратора доменных имен, на котором вы приобрели и зарегистрировали свой домен.</span><span class="sxs-lookup"><span data-stu-id="b060d-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="b060d-114">При регистрации в Cloudflare вы добавили домен с помощью процесса **настройки**.</span><span class="sxs-lookup"><span data-stu-id="b060d-114">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="b060d-115">Добавленный домен был приобретен у cloudflare или отдельного регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="b060d-115">The domain that you added was purchased from Cloudflare or a separate domain registrar.</span></span> <span data-ttu-id="b060d-116">Чтобы проверить и создать записи DNS для вашего домена в Microsoft 365, сначала необходимо изменить серверов доменных имен в регистраторе доменных имен, чтобы они использовали cloudflare серверов доменных имен.</span><span class="sxs-lookup"><span data-stu-id="b060d-116">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="b060d-117">Чтобы самостоятельно изменить серверы доменных имен на веб-сайте регистратора доменных имен, выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="b060d-117">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="b060d-118">Найдите на веб-сайте регистратора домена область, в которой можно изменить серверы доменных имен для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="b060d-118">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="b060d-119">Создайте две записи серверов доменных имен, используя значения из приведенной ниже таблицы, либо измените существующие записи серверов доменных имен, чтобы они соответствовали следующим значениям:</span><span class="sxs-lookup"><span data-stu-id="b060d-119">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="b060d-120">Основной сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="b060d-120">First nameserver</span></span>  <br/> |<span data-ttu-id="b060d-121">Используйте значение сервера доменных имен, предоставленное Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="b060d-121">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="b060d-122">Второстепенный сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="b060d-122">Second nameserver</span></span>  <br/> |<span data-ttu-id="b060d-123">Используйте значение сервера доменных имен, предоставленное Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="b060d-123">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="b060d-124">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="b060d-124">You should use at least two name server records.</span></span> <span data-ttu-id="b060d-125">Если в списке указаны другие серверы имен, их следует удалить.</span><span class="sxs-lookup"><span data-stu-id="b060d-125">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="b060d-126">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="b060d-126">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b060d-127">На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="b060d-127">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="b060d-128">После этого ваша электронная почта Майкрософт и другие службы будут настроены для работы с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="b060d-128">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b060d-129">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="b060d-129">Add a TXT record for verification</span></span>
<span data-ttu-id="b060d-130"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="b060d-130"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="b060d-p105">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="b060d-p105">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b060d-p106">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="b060d-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="b060d-135">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Cloudflare по [этой ссылке](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="b060d-135">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="b060d-136">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="b060d-136">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="b060d-137">На **домашней** странице выберите домен, который вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="b060d-137">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="b060d-138">На странице **Обзор** домена выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="b060d-138">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="b060d-139">На странице " **Управление DNS** " нажмите кнопку **Добавить запись**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="b060d-139">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="b060d-140">**Тип**</span><span class="sxs-lookup"><span data-stu-id="b060d-140">**Type**</span></span>|<span data-ttu-id="b060d-141">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="b060d-141">**Name**</span></span>|<span data-ttu-id="b060d-142">**Automatic TTL**</span><span class="sxs-lookup"><span data-stu-id="b060d-142">**Automatic TTL**</span></span>|<span data-ttu-id="b060d-143">**Content (Содержимое)**</span><span class="sxs-lookup"><span data-stu-id="b060d-143">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="b060d-144">TXT</span><span class="sxs-lookup"><span data-stu-id="b060d-144">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="b060d-145">30 мин.</span><span class="sxs-lookup"><span data-stu-id="b060d-145">30 minutes</span></span>  <br/> |<span data-ttu-id="b060d-146">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b060d-146">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="b060d-147">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="b060d-147">**Note:** This is an example.</span></span> <span data-ttu-id="b060d-148">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="b060d-148">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="b060d-149">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="b060d-149">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="b060d-150">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b060d-150">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="b060d-151">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="b060d-151">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b060d-152">Теперь, когда вы добавили запись на сайт регистратора доменных имен, вернитесь в корпорацию Майкрософт и найдите запись.</span><span class="sxs-lookup"><span data-stu-id="b060d-152">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="b060d-153">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="b060d-153">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b060d-154">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="b060d-154">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="b060d-155">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="b060d-155">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="b060d-156">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="b060d-156">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="b060d-157">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="b060d-157">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="b060d-p109">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b060d-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="b060d-161">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b060d-161">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="b060d-162"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="b060d-162"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="b060d-p110">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Cloudflare по [этой ссылке](https://www.cloudflare.com/a/login). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="b060d-p110">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="b060d-165">На **домашней** странице выберите домен, который вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="b060d-165">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="b060d-166">На странице **Обзор** домена выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="b060d-166">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="b060d-167">На странице " **Управление DNS** " нажмите кнопку **Добавить запись**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="b060d-167">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="b060d-168">**Тип**</span><span class="sxs-lookup"><span data-stu-id="b060d-168">**Type**</span></span>|<span data-ttu-id="b060d-169">**Имя**</span><span class="sxs-lookup"><span data-stu-id="b060d-169">**Name**</span></span>|<span data-ttu-id="b060d-170">**Mail Server (Почтовый сервер)**</span><span class="sxs-lookup"><span data-stu-id="b060d-170">**Mail server**</span></span>|<span data-ttu-id="b060d-171">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="b060d-171">**Priority**</span></span>|<span data-ttu-id="b060d-172">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="b060d-172">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b060d-173">MX</span><span class="sxs-lookup"><span data-stu-id="b060d-173">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="b060d-174">*\<ключ-домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b060d-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="b060d-175">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b060d-175">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   [<span data-ttu-id="b060d-176">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="b060d-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="b060d-177">1,1</span><span class="sxs-lookup"><span data-stu-id="b060d-177">1</span></span>  <br/> <span data-ttu-id="b060d-178">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).   </span><span class="sxs-lookup"><span data-stu-id="b060d-178">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/>|<span data-ttu-id="b060d-179">30 мин.</span><span class="sxs-lookup"><span data-stu-id="b060d-179">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="b060d-180">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b060d-180">Select **Save**.</span></span>
  
9. <span data-ttu-id="b060d-181">Если в разделе **MX Records** (Записи MX) есть другая запись MX, удалите ее, щелкнув значок **Delete (X)** (Удалить).</span><span class="sxs-lookup"><span data-stu-id="b060d-181">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="b060d-182">В диалоговом окне подтверждения нажмите кнопку **Удалить** , чтобы подтвердить изменения.</span><span class="sxs-lookup"><span data-stu-id="b060d-182">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="b060d-183">Добавление шести записей CNAME, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b060d-183">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="b060d-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="b060d-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="b060d-p112">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Cloudflare по [этой ссылке](https://www.cloudflare.com/a/login). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="b060d-p112">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="b060d-187">На **домашней** странице выберите домен, который вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="b060d-187">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="b060d-188">На странице **Обзор** домена выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="b060d-188">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="b060d-189">Добавьте первую из пяти записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="b060d-189">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="b060d-190">На странице " **Управление DNS** " нажмите кнопку **Добавить запись**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="b060d-190">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="b060d-191">**Тип**</span><span class="sxs-lookup"><span data-stu-id="b060d-191">**Type**</span></span>|<span data-ttu-id="b060d-192">**Name** (Имя)</span><span class="sxs-lookup"><span data-stu-id="b060d-192">**Name**</span></span>|<span data-ttu-id="b060d-193">**Target** (Целевое значение)</span><span class="sxs-lookup"><span data-stu-id="b060d-193">**Target**</span></span>|<span data-ttu-id="b060d-194">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="b060d-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b060d-195">CNAME</span><span class="sxs-lookup"><span data-stu-id="b060d-195">CNAME</span></span>  <br/> |<span data-ttu-id="b060d-196">autodiscover</span><span class="sxs-lookup"><span data-stu-id="b060d-196">autodiscover</span></span>  <br/> |<span data-ttu-id="b060d-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b060d-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="b060d-198">30 minutes</span><span class="sxs-lookup"><span data-stu-id="b060d-198">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="b060d-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="b060d-199">CNAME</span></span>  <br/> |<span data-ttu-id="b060d-200">sip</span><span class="sxs-lookup"><span data-stu-id="b060d-200">sip</span></span>  <br/> |<span data-ttu-id="b060d-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b060d-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="b060d-202">30 minutes</span><span class="sxs-lookup"><span data-stu-id="b060d-202">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="b060d-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="b060d-203">CNAME</span></span>  <br/> |<span data-ttu-id="b060d-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b060d-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b060d-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b060d-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="b060d-206">30 minutes</span><span class="sxs-lookup"><span data-stu-id="b060d-206">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="b060d-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="b060d-207">CNAME</span></span>  <br/> |<span data-ttu-id="b060d-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b060d-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b060d-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="b060d-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="b060d-210">30 minutes</span><span class="sxs-lookup"><span data-stu-id="b060d-210">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="b060d-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="b060d-211">CNAME</span></span>  <br/> |<span data-ttu-id="b060d-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b060d-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b060d-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b060d-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="b060d-214">30 minutes</span><span class="sxs-lookup"><span data-stu-id="b060d-214">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="b060d-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="b060d-215">CNAME</span></span>  <br/> |<span data-ttu-id="b060d-216">msoid</span><span class="sxs-lookup"><span data-stu-id="b060d-216">msoid</span></span>  <br/> |<span data-ttu-id="b060d-217">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="b060d-217">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="b060d-218">30 minutes</span><span class="sxs-lookup"><span data-stu-id="b060d-218">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="b060d-219">Выберите значок **трафика DNS** (оранжевый облако), чтобы обойти серверы cloudflare.</span><span class="sxs-lookup"><span data-stu-id="b060d-219">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="b060d-220">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b060d-220">Select **Save**.</span></span>
  
7. <span data-ttu-id="b060d-221">Добавьте остальные пять записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="b060d-221">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b060d-222">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="b060d-222">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="b060d-223"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="b060d-223"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b060d-224">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="b060d-224">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="b060d-225">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="b060d-225">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="b060d-226">Если вы уже указали запись SPF для домена, не создавайте еще одну для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b060d-226">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="b060d-227">Вместо этого добавьте необходимые значения Microsoft 365 в текущую запись. Таким образом, в *одной* записи SPF будут указаны оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="b060d-227">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="b060d-228">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Cloudflare по [этой ссылке](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="b060d-228">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="b060d-229">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="b060d-229">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="b060d-230">На **домашней** странице выберите домен, который вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="b060d-230">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="b060d-231">На странице **Обзор** домена выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="b060d-231">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="b060d-232">На странице " **Управление DNS** " нажмите кнопку **Добавить запись**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="b060d-232">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="b060d-233">**Тип**</span><span class="sxs-lookup"><span data-stu-id="b060d-233">**Type**</span></span>|<span data-ttu-id="b060d-234">**Имя**</span><span class="sxs-lookup"><span data-stu-id="b060d-234">**Name**</span></span>|<span data-ttu-id="b060d-235">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="b060d-235">**TTL**</span></span>|<span data-ttu-id="b060d-236">**Content (Содержимое)**</span><span class="sxs-lookup"><span data-stu-id="b060d-236">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b060d-237">TXT</span><span class="sxs-lookup"><span data-stu-id="b060d-237">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="b060d-238">30 мин.</span><span class="sxs-lookup"><span data-stu-id="b060d-238">30 minutes</span></span>  <br/> |<span data-ttu-id="b060d-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="b060d-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="b060d-240">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="b060d-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="b060d-241">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b060d-241">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="b060d-242">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b060d-242">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="b060d-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="b060d-243"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b060d-244">Имейте в виду, что cloudflare отвечает за обеспечение доступности этой функции.</span><span class="sxs-lookup"><span data-stu-id="b060d-244">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="b060d-245">Если вы видите несоответствия между действиями ниже и текущим ГРАФИЧЕСКИм пользовательским интерфейсом cloudflare (графический пользовательский интерфейс), воспользуйтесь [сообществом cloudflare](https://community.cloudflare.com/).</span><span class="sxs-lookup"><span data-stu-id="b060d-245">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="b060d-246">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Cloudflare по [этой ссылке](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="b060d-246">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="b060d-247">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="b060d-247">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="b060d-248">На **домашней** странице выберите домен, который вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="b060d-248">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="b060d-249">На странице **Обзор** домена выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="b060d-249">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="b060d-250">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="b060d-250">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="b060d-251">На странице " **Управление DNS** " нажмите кнопку **Добавить запись**, а затем выберите значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="b060d-251">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="b060d-252">**Тип**</span><span class="sxs-lookup"><span data-stu-id="b060d-252">**Type**</span></span>|<span data-ttu-id="b060d-253">**Service (Служба)**</span><span class="sxs-lookup"><span data-stu-id="b060d-253">**Service**</span></span>|<span data-ttu-id="b060d-254">**Protocol (Протокол)**</span><span class="sxs-lookup"><span data-stu-id="b060d-254">**Protocol**</span></span>|<span data-ttu-id="b060d-255">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="b060d-255">**Name**</span></span>|<span data-ttu-id="b060d-256">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="b060d-256">**TTL**</span></span>|<span data-ttu-id="b060d-257">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="b060d-257">**Priority**</span></span>|<span data-ttu-id="b060d-258">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="b060d-258">**Weight**</span></span>|<span data-ttu-id="b060d-259">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="b060d-259">**Port**</span></span>|<span data-ttu-id="b060d-260">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="b060d-260">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b060d-261">SRV</span><span class="sxs-lookup"><span data-stu-id="b060d-261">SRV</span></span>|<span data-ttu-id="b060d-262">_sip</span><span class="sxs-lookup"><span data-stu-id="b060d-262">_sip</span></span> |<span data-ttu-id="b060d-263">TLS</span><span class="sxs-lookup"><span data-stu-id="b060d-263">TLS</span></span> |<span data-ttu-id="b060d-264">Использование *domain_name*; Например, contoso.com</span><span class="sxs-lookup"><span data-stu-id="b060d-264">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="b060d-265">30 мин.</span><span class="sxs-lookup"><span data-stu-id="b060d-265">30 minutes</span></span> | <span data-ttu-id="b060d-266">100</span><span class="sxs-lookup"><span data-stu-id="b060d-266">100</span></span>|<span data-ttu-id="b060d-267">1,1</span><span class="sxs-lookup"><span data-stu-id="b060d-267">1</span></span> |<span data-ttu-id="b060d-268">443</span><span class="sxs-lookup"><span data-stu-id="b060d-268">443</span></span> |<span data-ttu-id="b060d-269">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b060d-269">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="b060d-270">SRV</span><span class="sxs-lookup"><span data-stu-id="b060d-270">SRV</span></span>|<span data-ttu-id="b060d-271">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="b060d-271">_sipfederationtls</span></span> | <span data-ttu-id="b060d-272">TCP</span><span class="sxs-lookup"><span data-stu-id="b060d-272">TCP</span></span>|<span data-ttu-id="b060d-273">Использование *domain_name*; Например, contoso.com</span><span class="sxs-lookup"><span data-stu-id="b060d-273">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="b060d-274">30 мин.</span><span class="sxs-lookup"><span data-stu-id="b060d-274">30 minutes</span></span> |<span data-ttu-id="b060d-275">100</span><span class="sxs-lookup"><span data-stu-id="b060d-275">100</span></span> |<span data-ttu-id="b060d-276">1,1</span><span class="sxs-lookup"><span data-stu-id="b060d-276">1</span></span> |<span data-ttu-id="b060d-277">5061</span><span class="sxs-lookup"><span data-stu-id="b060d-277">5061</span></span> | <span data-ttu-id="b060d-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b060d-278">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="b060d-279">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b060d-279">Select **Save**.</span></span>

  
6. <span data-ttu-id="b060d-280">Добавьте другую запись SRV, выбрав значения из второй строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="b060d-280">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="b060d-p117">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b060d-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
