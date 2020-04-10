---
title: Создание записей DNS для Office 365 на сайте Cloudflare
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
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу cloudflare для Office 365.
ms.openlocfilehash: 8d64824f880bab9e6691ebf47c9508c555562fe4
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211815"
---
# <a name="create-dns-records-at-cloudflare-for-office-365"></a><span data-ttu-id="f05ea-103">Создание записей DNS для Office 365 на сайте Cloudflare</span><span class="sxs-lookup"><span data-stu-id="f05ea-103">Create DNS records at Cloudflare for Office 365</span></span>

 <span data-ttu-id="f05ea-104">Если вы не нашли то, что вы ищете, обратитесь к разделу **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="f05ea-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="f05ea-105">Если ваш поставщик услуг размещения DNS  Cloudflare, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб.</span><span class="sxs-lookup"><span data-stu-id="f05ea-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="f05ea-106">После того как вы добавите эти записи на сайте Cloudflare, ваш домен будет настроен для работы со службами Office 365.</span><span class="sxs-lookup"><span data-stu-id="f05ea-106">After you add these records at Cloudflare, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="f05ea-107">Дополнительные сведения о веб-хостинге и DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="f05ea-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="f05ea-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f05ea-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="f05ea-111">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="f05ea-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="f05ea-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="f05ea-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f05ea-113">Эту процедуру необходимо выполнить на сайте регистратора доменных имен, на котором вы приобрели и зарегистрировали свой домен.</span><span class="sxs-lookup"><span data-stu-id="f05ea-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="f05ea-114">При регистрации в Cloudflare вы добавили домен с помощью процесса **настройки**.</span><span class="sxs-lookup"><span data-stu-id="f05ea-114">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="f05ea-p102">Домен, который вы добавили, был приобретен у стороннего регистратора доменных имен; Cloudflare не предоставляет услуг по регистрации доменных имен. Для проверки и создания записей DNS для вашего домена в Office 365 необходимо сначала изменить серверы доменных имен на веб-сайте регистратора доменных имен, чтобы использовать серверы доменных имен Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="f05ea-p102">The domain that you added was purchased from a separate domain registrar; Cloudflare does not offer domain registration services. To verify and create DNS records for your domain in Office 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="f05ea-117">Чтобы самостоятельно изменить серверы доменных имен на веб-сайте регистратора доменных имен, выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="f05ea-117">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="f05ea-118">Найдите на веб-сайте регистратора домена область, в которой можно изменить серверы доменных имен для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="f05ea-118">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="f05ea-119">Создайте две записи серверов доменных имен, используя значения из приведенной ниже таблицы, либо измените существующие записи серверов доменных имен, чтобы они соответствовали следующим значениям:</span><span class="sxs-lookup"><span data-stu-id="f05ea-119">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="f05ea-120">Основной сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="f05ea-120">First nameserver</span></span>  <br/> |<span data-ttu-id="f05ea-121">Используйте значение сервера доменных имен, предоставленное Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="f05ea-121">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="f05ea-122">Второстепенный сервер доменных имен</span><span class="sxs-lookup"><span data-stu-id="f05ea-122">Second nameserver</span></span>  <br/> |<span data-ttu-id="f05ea-123">Используйте значение сервера доменных имен, предоставленное Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="f05ea-123">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="f05ea-124">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="f05ea-124">You should use at least two name server records.</span></span> <span data-ttu-id="f05ea-125">Если в списке указаны другие серверы имен, их следует удалить.</span><span class="sxs-lookup"><span data-stu-id="f05ea-125">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="f05ea-126">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="f05ea-126">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f05ea-p104">На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов. После этого ваша электронная почта и все остальные службы Office 365 будут настроены на работу с новым доменом.</span><span class="sxs-lookup"><span data-stu-id="f05ea-p104">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="f05ea-129">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="f05ea-129">Add a TXT record for verification</span></span>
<span data-ttu-id="f05ea-130"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="f05ea-130"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="f05ea-p105">Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="f05ea-p105">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f05ea-p106">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="f05ea-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="f05ea-135">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Cloudflare по [этой ссылке](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="f05ea-135">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="f05ea-136">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="f05ea-136">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="f05ea-137">На **домашней** странице выберите домен, который вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="f05ea-137">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="f05ea-138">На странице **Обзор** домена выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="f05ea-138">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="f05ea-139">На странице " **Управление DNS** " нажмите кнопку **Добавить запись**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="f05ea-139">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="f05ea-140">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f05ea-140">**Type**</span></span>|<span data-ttu-id="f05ea-141">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="f05ea-141">**Name**</span></span>|<span data-ttu-id="f05ea-142">**Automatic TTL**</span><span class="sxs-lookup"><span data-stu-id="f05ea-142">**Automatic TTL**</span></span>|<span data-ttu-id="f05ea-143">**Content (Содержимое)**</span><span class="sxs-lookup"><span data-stu-id="f05ea-143">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="f05ea-144">TXT</span><span class="sxs-lookup"><span data-stu-id="f05ea-144">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="f05ea-145">30 мин.</span><span class="sxs-lookup"><span data-stu-id="f05ea-145">30 minutes</span></span>  <br/> |<span data-ttu-id="f05ea-146">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f05ea-146">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="f05ea-p108">**Примечание.** Это пример. Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.           [Где это находится?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="f05ea-p108">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>    |
  
    
5. <span data-ttu-id="f05ea-150">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f05ea-150">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="f05ea-151">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="f05ea-151">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="f05ea-152">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Office 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="f05ea-152">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="f05ea-153">Если Office 365 обнаружит правильную запись TXT, это значит, что домен проверен.</span><span class="sxs-lookup"><span data-stu-id="f05ea-153">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="f05ea-154">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="f05ea-154">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="f05ea-155">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="f05ea-155">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="f05ea-156">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="f05ea-156">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="f05ea-157">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="f05ea-157">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="f05ea-p109">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f05ea-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="f05ea-161">Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="f05ea-161">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="f05ea-162"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="f05ea-162"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="f05ea-p110">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Cloudflare по [этой ссылке](https://www.cloudflare.com/a/login). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="f05ea-p110">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="f05ea-165">На **домашней** странице выберите домен, который вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="f05ea-165">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="f05ea-166">На странице **Обзор** домена выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="f05ea-166">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="f05ea-167">На странице " **Управление DNS** " нажмите кнопку **Добавить запись**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="f05ea-167">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="f05ea-168">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f05ea-168">**Type**</span></span>|<span data-ttu-id="f05ea-169">**Имя**</span><span class="sxs-lookup"><span data-stu-id="f05ea-169">**Name**</span></span>|<span data-ttu-id="f05ea-170">**Mail Server (Почтовый сервер)**</span><span class="sxs-lookup"><span data-stu-id="f05ea-170">**Mail server**</span></span>|<span data-ttu-id="f05ea-171">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="f05ea-171">**Priority**</span></span>|<span data-ttu-id="f05ea-172">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="f05ea-172">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f05ea-173">MX</span><span class="sxs-lookup"><span data-stu-id="f05ea-173">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="f05ea-174">*\<ключ-домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f05ea-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="f05ea-175">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Office 365.</span><span class="sxs-lookup"><span data-stu-id="f05ea-175">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="f05ea-176">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="f05ea-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="f05ea-177">1,1</span><span class="sxs-lookup"><span data-stu-id="f05ea-177">1</span></span>  <br/> <span data-ttu-id="f05ea-178">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).   </span><span class="sxs-lookup"><span data-stu-id="f05ea-178">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/>|<span data-ttu-id="f05ea-179">30 мин.</span><span class="sxs-lookup"><span data-stu-id="f05ea-179">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="f05ea-180">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f05ea-180">Select **Save**.</span></span>
  
9. <span data-ttu-id="f05ea-181">Если в разделе **MX Records** (Записи MX) есть другая запись MX, удалите ее, щелкнув значок **Delete (X)** (Удалить).</span><span class="sxs-lookup"><span data-stu-id="f05ea-181">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="f05ea-182">В диалоговом окне подтверждения нажмите кнопку **Удалить** , чтобы подтвердить изменения.</span><span class="sxs-lookup"><span data-stu-id="f05ea-182">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="f05ea-183">Добавление шести записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="f05ea-183">Add the Six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="f05ea-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="f05ea-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="f05ea-p112">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Cloudflare по [этой ссылке](https://www.cloudflare.com/a/login). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="f05ea-p112">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="f05ea-187">На **домашней** странице выберите домен, который вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="f05ea-187">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="f05ea-188">На странице **Обзор** домена выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="f05ea-188">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="f05ea-189">Добавьте первую из пяти записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="f05ea-189">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="f05ea-190">На странице " **Управление DNS** " нажмите кнопку **Добавить запись**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="f05ea-190">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="f05ea-191">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f05ea-191">**Type**</span></span>|<span data-ttu-id="f05ea-192">**Name** (Имя)</span><span class="sxs-lookup"><span data-stu-id="f05ea-192">**Name**</span></span>|<span data-ttu-id="f05ea-193">**Target** (Целевое значение)</span><span class="sxs-lookup"><span data-stu-id="f05ea-193">**Target**</span></span>|<span data-ttu-id="f05ea-194">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="f05ea-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f05ea-195">CNAME</span><span class="sxs-lookup"><span data-stu-id="f05ea-195">CNAME</span></span>  <br/> |<span data-ttu-id="f05ea-196">autodiscover</span><span class="sxs-lookup"><span data-stu-id="f05ea-196">autodiscover</span></span>  <br/> |<span data-ttu-id="f05ea-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f05ea-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="f05ea-198">30 minutes</span><span class="sxs-lookup"><span data-stu-id="f05ea-198">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="f05ea-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="f05ea-199">CNAME</span></span>  <br/> |<span data-ttu-id="f05ea-200">sip</span><span class="sxs-lookup"><span data-stu-id="f05ea-200">sip</span></span>  <br/> |<span data-ttu-id="f05ea-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f05ea-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="f05ea-202">30 minutes</span><span class="sxs-lookup"><span data-stu-id="f05ea-202">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="f05ea-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="f05ea-203">CNAME</span></span>  <br/> |<span data-ttu-id="f05ea-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="f05ea-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="f05ea-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f05ea-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="f05ea-206">30 minutes</span><span class="sxs-lookup"><span data-stu-id="f05ea-206">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="f05ea-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="f05ea-207">CNAME</span></span>  <br/> |<span data-ttu-id="f05ea-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="f05ea-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="f05ea-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="f05ea-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="f05ea-210">30 minutes</span><span class="sxs-lookup"><span data-stu-id="f05ea-210">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="f05ea-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="f05ea-211">CNAME</span></span>  <br/> |<span data-ttu-id="f05ea-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="f05ea-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="f05ea-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f05ea-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="f05ea-214">30 minutes</span><span class="sxs-lookup"><span data-stu-id="f05ea-214">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="f05ea-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="f05ea-215">CNAME</span></span>  <br/> |<span data-ttu-id="f05ea-216">msoid</span><span class="sxs-lookup"><span data-stu-id="f05ea-216">msoid</span></span>  <br/> |<span data-ttu-id="f05ea-217">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="f05ea-217">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="f05ea-218">30 minutes</span><span class="sxs-lookup"><span data-stu-id="f05ea-218">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="f05ea-219">Выберите значок **трафика DNS** (оранжевый облако), чтобы обойти серверы cloudflare.</span><span class="sxs-lookup"><span data-stu-id="f05ea-219">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="f05ea-220">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f05ea-220">Select **Save**.</span></span>
  
7. <span data-ttu-id="f05ea-221">Добавьте остальные пять записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="f05ea-221">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="f05ea-222">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="f05ea-222">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="f05ea-223"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="f05ea-223"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f05ea-224">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="f05ea-224">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="f05ea-225">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="f05ea-225">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="f05ea-226">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="f05ea-226">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="f05ea-227">Вместо этого добавьте необходимые значения Office 365 в текущую запись. Таким образом, в *одной* записи SPF будут указаны оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="f05ea-227">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="f05ea-228">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Cloudflare по [этой ссылке](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="f05ea-228">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="f05ea-229">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="f05ea-229">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="f05ea-230">На **домашней** странице выберите домен, который вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="f05ea-230">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="f05ea-231">На странице **Обзор** домена выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="f05ea-231">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="f05ea-232">На странице " **Управление DNS** " нажмите кнопку **Добавить запись**, а затем выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="f05ea-232">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="f05ea-233">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f05ea-233">**Type**</span></span>|<span data-ttu-id="f05ea-234">**Имя**</span><span class="sxs-lookup"><span data-stu-id="f05ea-234">**Name**</span></span>|<span data-ttu-id="f05ea-235">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="f05ea-235">**TTL**</span></span>|<span data-ttu-id="f05ea-236">**Content (Содержимое)**</span><span class="sxs-lookup"><span data-stu-id="f05ea-236">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f05ea-237">TXT</span><span class="sxs-lookup"><span data-stu-id="f05ea-237">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="f05ea-238">30 мин.</span><span class="sxs-lookup"><span data-stu-id="f05ea-238">30 minutes</span></span>  <br/> |<span data-ttu-id="f05ea-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="f05ea-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="f05ea-240">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="f05ea-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="f05ea-241">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f05ea-241">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="f05ea-242">Добавление двух записей SRV, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="f05ea-242">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="f05ea-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="f05ea-243"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f05ea-244">Имейте в виду, что cloudflare отвечает за обеспечение доступности этой функции.</span><span class="sxs-lookup"><span data-stu-id="f05ea-244">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="f05ea-245">Если вы видите несоответствия между действиями ниже и текущим ГРАФИЧЕСКИм пользовательским интерфейсом cloudflare (графический пользовательский интерфейс), воспользуйтесь [сообществом cloudflare](https://community.cloudflare.com/).</span><span class="sxs-lookup"><span data-stu-id="f05ea-245">In case you see discrepancies between the steps below and the current Cloudflare GUI(Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="f05ea-246">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Cloudflare по [этой ссылке](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="f05ea-246">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="f05ea-247">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="f05ea-247">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="f05ea-248">На **домашней** странице выберите домен, который вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="f05ea-248">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="f05ea-249">На странице **Обзор** домена выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="f05ea-249">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="f05ea-250">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="f05ea-250">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="f05ea-251">На странице " **Управление DNS** " нажмите кнопку **Добавить запись**, а затем выберите значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="f05ea-251">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="f05ea-252">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f05ea-252">**Type**</span></span>|<span data-ttu-id="f05ea-253">**Service (Служба)**</span><span class="sxs-lookup"><span data-stu-id="f05ea-253">**Service**</span></span>|<span data-ttu-id="f05ea-254">**Protocol (Протокол)**</span><span class="sxs-lookup"><span data-stu-id="f05ea-254">**Protocol**</span></span>|<span data-ttu-id="f05ea-255">**Name** (Имя)</span><span class="sxs-lookup"><span data-stu-id="f05ea-255">**Name**</span></span>|<span data-ttu-id="f05ea-256">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="f05ea-256">**TTL**</span></span>|<span data-ttu-id="f05ea-257">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="f05ea-257">**Priority**</span></span>|<span data-ttu-id="f05ea-258">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="f05ea-258">**Weight**</span></span>|<span data-ttu-id="f05ea-259">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="f05ea-259">**Port**</span></span>|<span data-ttu-id="f05ea-260">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="f05ea-260">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f05ea-261">SRV</span><span class="sxs-lookup"><span data-stu-id="f05ea-261">SRV</span></span>|<span data-ttu-id="f05ea-262">_sip</span><span class="sxs-lookup"><span data-stu-id="f05ea-262">_sip</span></span> |<span data-ttu-id="f05ea-263">TLS</span><span class="sxs-lookup"><span data-stu-id="f05ea-263">TLS</span></span> |<span data-ttu-id="f05ea-264">Использование *domain_name*; Например, contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05ea-264">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="f05ea-265">30 мин.</span><span class="sxs-lookup"><span data-stu-id="f05ea-265">30 minutes</span></span> | <span data-ttu-id="f05ea-266">100</span><span class="sxs-lookup"><span data-stu-id="f05ea-266">100</span></span>|<span data-ttu-id="f05ea-267">1,1</span><span class="sxs-lookup"><span data-stu-id="f05ea-267">1</span></span> |<span data-ttu-id="f05ea-268">443</span><span class="sxs-lookup"><span data-stu-id="f05ea-268">443</span></span> |<span data-ttu-id="f05ea-269">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f05ea-269">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="f05ea-270">SRV</span><span class="sxs-lookup"><span data-stu-id="f05ea-270">SRV</span></span>|<span data-ttu-id="f05ea-271">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="f05ea-271">_sipfederationtls</span></span> | <span data-ttu-id="f05ea-272">TCP</span><span class="sxs-lookup"><span data-stu-id="f05ea-272">TCP</span></span>|<span data-ttu-id="f05ea-273">Использование *domain_name*; Например, contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05ea-273">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="f05ea-274">30 мин.</span><span class="sxs-lookup"><span data-stu-id="f05ea-274">30 minutes</span></span> |<span data-ttu-id="f05ea-275">100</span><span class="sxs-lookup"><span data-stu-id="f05ea-275">100</span></span> |<span data-ttu-id="f05ea-276">1,1</span><span class="sxs-lookup"><span data-stu-id="f05ea-276">1</span></span> |<span data-ttu-id="f05ea-277">5061</span><span class="sxs-lookup"><span data-stu-id="f05ea-277">5061</span></span> | <span data-ttu-id="f05ea-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f05ea-278">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="f05ea-279">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f05ea-279">Select **Save**.</span></span>

  
6. <span data-ttu-id="f05ea-280">Добавьте другую запись SRV, выбрав значения из второй строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="f05ea-280">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="f05ea-p117">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f05ea-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
