---
title: Создание записей DNS для зон DNS Azure
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
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб в зонах DNS Azure для Майкрософт.
ms.openlocfilehash: 7104fb18a6581b7ebc853f938b85171ae1886cfd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629147"
---
# <a name="create-dns-records-for-azure-dns-zones"></a><span data-ttu-id="a5269-103">Создание записей DNS для зон DNS Azure</span><span class="sxs-lookup"><span data-stu-id="a5269-103">Create DNS records for Azure DNS zones</span></span>

 <span data-ttu-id="a5269-104">Если вы не нашли то, что вы ищете, обратитесь к разделу **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="a5269-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a5269-105">Если Azure является поставщиком услуг хостинга DNS, выполните действия, описанные в этой статье, чтобы проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и т. д.</span><span class="sxs-lookup"><span data-stu-id="a5269-105">If Azure is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="a5269-106">Ниже перечислены основные записи, которые нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="a5269-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="a5269-107">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="a5269-107">Change your domain's nameserver (NS) records</span></span>](#change-your-domains-nameserver-ns-records)
    
- [<span data-ttu-id="a5269-108">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="a5269-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)

- [<span data-ttu-id="a5269-109">Добавление записи MX для отправки электронной почты для вашего домена в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a5269-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="a5269-110">Добавление четырех записей CNAME, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a5269-110">Add the four CNAME records that are required for Microsoft</span></span>](#add-the-four-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="a5269-111">Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="a5269-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="a5269-112">Добавление двух записей SRV, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a5269-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="a5269-113">Когда вы добавите эти записи в Azure, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a5269-113">After you add these records at Azure, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a5269-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a5269-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="a5269-117">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="a5269-117">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="a5269-118"><a name="BKMK_NS"> </a></span><span class="sxs-lookup"><span data-stu-id="a5269-118"><a name="BKMK_NS"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a5269-119">Эту процедуру необходимо выполнить на сайте регистратора доменных имен, на котором вы приобрели и зарегистрировали свой домен.</span><span class="sxs-lookup"><span data-stu-id="a5269-119">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="a5269-120">При регистрации в Azure вы создали группу ресурсов в зоне DNS и назначили имя домена этой группе ресурсов.</span><span class="sxs-lookup"><span data-stu-id="a5269-120">When you signed up for Azure, you created a resource group within a DNS zone, and then assigned your domain name to that resource group.</span></span> <span data-ttu-id="a5269-121">Это имя домена регистрируется во внешнем регистраторе доменов; Azure не предоставляет службы регистрации доменов.</span><span class="sxs-lookup"><span data-stu-id="a5269-121">That domain name is registered to an external domain registrar; Azure does not offer domain registration services.</span></span>
  
<span data-ttu-id="a5269-122">Чтобы проверить и создать записи DNS для вашего домена в корпорации Майкрософт, сначала необходимо изменить серверов доменных имен в регистраторе доменных имен, чтобы они использовали серверов доменных имен Azure, назначенные группе ресурсов.</span><span class="sxs-lookup"><span data-stu-id="a5269-122">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use the Azure nameservers assigned to your resource group.</span></span>
  
<span data-ttu-id="a5269-123">Чтобы самостоятельно изменить серверы доменных имен на веб-сайте регистратора доменных имен, выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="a5269-123">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="a5269-124">Найдите на веб-сайте регистратора домена область, в которой можно изменить серверы доменных имен для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="a5269-124">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="a5269-125">Создайте две записи серверов доменных имен, используя значения из приведенной ниже таблицы, либо измените существующие записи серверов доменных имен, чтобы они соответствовали следующим значениям:</span><span class="sxs-lookup"><span data-stu-id="a5269-125">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span> <span data-ttu-id="a5269-126">Ниже приведен пример назначенного серверов доменных имен Azure.</span><span class="sxs-lookup"><span data-stu-id="a5269-126">An example of Azure assigned nameservers is shown below.</span></span>
    


<span data-ttu-id="a5269-127">**Первое имя** сервера доменных имен: Используйте значение сервера имен, назначенное Azure.</span><span class="sxs-lookup"><span data-stu-id="a5269-127">**First nameserver:** Use the name server value assigned by Azure.</span></span>  
<span data-ttu-id="a5269-128">**Второе nameserver:** Используйте значение сервера имен, назначенное Azure.</span><span class="sxs-lookup"><span data-stu-id="a5269-128">**Second nameserver:** Use the name server value assigned by Azure.</span></span>  

![Azure — BP — redelegate — 1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> <span data-ttu-id="a5269-130">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="a5269-130">You should use at least two name server records.</span></span> <span data-ttu-id="a5269-131">Если на веб-сайте регистратора доменных имен указаны другие серверы, их следует удалить.</span><span class="sxs-lookup"><span data-stu-id="a5269-131">If there are any other name servers listed at your domain registrar's website, you should delete them.</span></span> 
  
3. <span data-ttu-id="a5269-132">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="a5269-132">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a5269-133">На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="a5269-133">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="a5269-134">После этого ваша электронная почта Майкрософт и другие службы будут настроены для работы с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="a5269-134">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a5269-135">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="a5269-135">Add a TXT record for verification</span></span>
<span data-ttu-id="a5269-136"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a5269-136"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a5269-137">Перед использованием домена с корпорацией Майкрософт необходимо убедиться, что вы являетесь его владельцем.</span><span class="sxs-lookup"><span data-stu-id="a5269-137">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="a5269-138">Вы можете войти в свою учетную запись у вас в вашем регистраторе доменных имен и создать запись DNS в Майкрософт, если вы владеете этим доменом.</span><span class="sxs-lookup"><span data-stu-id="a5269-138">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a5269-p107">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="a5269-p107">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="a5269-141">Чтобы приступить к работе, перейдите на страницу ваших доменов в Azure, используя [эту ссылку](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="a5269-141">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="a5269-142">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="a5269-142">You'll be prompted to log in first.</span></span>
    
    ![Azure — BP — configure – 1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="a5269-144">С помощью **панели поиска** на странице **панели мониторинга** введите **DNS-зоны**.</span><span class="sxs-lookup"><span data-stu-id="a5269-144">Using the **search bar** on the **Dashboard** page, type in **DNS zones**.</span></span> <span data-ttu-id="a5269-145">В окне Отображение результатов выберите пункт **зоны DNS** в разделе **службы** .</span><span class="sxs-lookup"><span data-stu-id="a5269-145">In the results display, select **DNS zones** under the **Services** portion.</span></span> <span data-ttu-id="a5269-146">После перенаправления выберите домен, который вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="a5269-146">Once you've been redirected, select the domain that you want to update.</span></span>
    
    ![Azure — BP — configure – 1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="a5269-148">На странице **Параметры** домена в области **зона DNS** выберите пункт **+ набор записей**.</span><span class="sxs-lookup"><span data-stu-id="a5269-148">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure — BP — configure – 1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="a5269-150">В поля для нового набора записей в области **Добавление набора записей** выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="a5269-150">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="a5269-151">В раскрывающихся списках выберите значения **Type (тип** ) и **TTL (TTL** ).</span><span class="sxs-lookup"><span data-stu-id="a5269-151">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="a5269-152">**Имя**</span><span class="sxs-lookup"><span data-stu-id="a5269-152">**Name**</span></span>|<span data-ttu-id="a5269-153">**Тип**</span><span class="sxs-lookup"><span data-stu-id="a5269-153">**Type**</span></span>|<span data-ttu-id="a5269-154">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="a5269-154">**TTL**</span></span>|<span data-ttu-id="a5269-155">**Единица срока жизни**</span><span class="sxs-lookup"><span data-stu-id="a5269-155">**TTL unit**</span></span>|<span data-ttu-id="a5269-156">**Значение**</span><span class="sxs-lookup"><span data-stu-id="a5269-156">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="a5269-157">TXT</span><span class="sxs-lookup"><span data-stu-id="a5269-157">TXT</span></span>  <br/> |<span data-ttu-id="a5269-158">1,1</span><span class="sxs-lookup"><span data-stu-id="a5269-158">1</span></span>  <br/> |<span data-ttu-id="a5269-159">Часы</span><span class="sxs-lookup"><span data-stu-id="a5269-159">Hours</span></span>  <br/> |<span data-ttu-id="a5269-160">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a5269-160">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a5269-161">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="a5269-161">**Note:** This is an example.</span></span> <span data-ttu-id="a5269-162">Используйте указанную здесь **конечную точку или значение адреса** из таблицы.</span><span class="sxs-lookup"><span data-stu-id="a5269-162">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="a5269-163">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="a5269-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Azure — BP — проверка — 1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. <span data-ttu-id="a5269-165">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a5269-165">Select **OK**.</span></span>
  
6. <span data-ttu-id="a5269-166">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="a5269-166">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a5269-167">Теперь, когда вы добавили запись на сайте регистратора доменных имен, вернитесь в корпорацию Майкрософт и запросите запись.</span><span class="sxs-lookup"><span data-stu-id="a5269-167">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="a5269-168">После того как корпорация Майкрософт обнаружит правильную запись TXT, ваш домен будет проверен.</span><span class="sxs-lookup"><span data-stu-id="a5269-168">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a5269-169">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="a5269-169">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="a5269-170">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="a5269-170">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="a5269-171">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="a5269-171">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="a5269-172">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="a5269-172">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="a5269-p111">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a5269-p111">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="a5269-176">Добавление записи MX для отправки электронной почты для вашего домена в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a5269-176">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="a5269-177"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a5269-177"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="a5269-178">Чтобы приступить к работе, перейдите на страницу ваших доменов в Azure, используя [эту ссылку](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="a5269-178">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="a5269-179">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="a5269-179">You'll be prompted to log in first.</span></span>
    
    ![Azure — BP — configure – 1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="a5269-181">На странице **"панель мониторинга"** в области " **все ресурсы** " выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="a5269-181">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure — BP — configure – 1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="a5269-183">На странице **Параметры** домена в области **зона DNS** выберите пункт **+ набор записей**.</span><span class="sxs-lookup"><span data-stu-id="a5269-183">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure — BP — configure – 1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="a5269-185">В поля для нового набора записей в области **Добавление набора записей** выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="a5269-185">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="a5269-186">В раскрывающихся списках выберите значения **Type (тип** ) и **TTL (TTL** ).</span><span class="sxs-lookup"><span data-stu-id="a5269-186">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="a5269-187">**Имя**</span><span class="sxs-lookup"><span data-stu-id="a5269-187">**Name**</span></span>|<span data-ttu-id="a5269-188">**Тип**</span><span class="sxs-lookup"><span data-stu-id="a5269-188">**Type**</span></span>|<span data-ttu-id="a5269-189">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="a5269-189">**TTL**</span></span>|<span data-ttu-id="a5269-190">**Единица срока жизни**</span><span class="sxs-lookup"><span data-stu-id="a5269-190">**TTL unit**</span></span>|<span data-ttu-id="a5269-191">**Preference (Предпочтение)**</span><span class="sxs-lookup"><span data-stu-id="a5269-191">**Preference**</span></span>|<span data-ttu-id="a5269-192">**Обмен сообщениями**</span><span class="sxs-lookup"><span data-stu-id="a5269-192">**Mail Exchange**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="a5269-193">MX</span><span class="sxs-lookup"><span data-stu-id="a5269-193">MX</span></span>  <br/> |<span data-ttu-id="a5269-194">1,1</span><span class="sxs-lookup"><span data-stu-id="a5269-194">1</span></span>  <br/> |<span data-ttu-id="a5269-195">Часы</span><span class="sxs-lookup"><span data-stu-id="a5269-195">Hours</span></span>  <br/> |<span data-ttu-id="a5269-196">10 </span><span class="sxs-lookup"><span data-stu-id="a5269-196">10</span></span>  <br/> <span data-ttu-id="a5269-197">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="a5269-197">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="a5269-198">*\<ключ_домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a5269-198">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="a5269-199">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a5269-199">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="a5269-200">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="a5269-200">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure — BP — configure – 2-1](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. <span data-ttu-id="a5269-202">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a5269-202">Select **OK**.</span></span>
    
    ![Azure — BP — configure – 2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. <span data-ttu-id="a5269-204">Если в разделе **MX Records (записи MX** ) указаны другие записи MX, их необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="a5269-204">If there are any other MX records listed in the **MX Records** section, you must delete them.</span></span> 
    
    <span data-ttu-id="a5269-205">Сначала в области **зона DNS** выберите **набор записей MX**.</span><span class="sxs-lookup"><span data-stu-id="a5269-205">First, in the **DNS zone** area, select the **MX Record set**.</span></span>
    
    ![Azure — BP — configure – 2-3](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    <span data-ttu-id="a5269-207">Затем выберите запись MX, которую нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="a5269-207">Next, select the MX record you want to delete.</span></span>
    
    ![Azure — BP — configure – 2-4](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. <span data-ttu-id="a5269-209">Выберите **контекстное меню (...)**, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="a5269-209">Select the **Context menu (…)**, and then choose **Remove**.</span></span>
    
    ![Azure — BP — configure – 2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. <span data-ttu-id="a5269-211">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a5269-211">Select **Save**.</span></span>
    
    ![Azure — BP — configure – 2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="a5269-213">Добавление четырех записей CNAME, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a5269-213">Add the four CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="a5269-214"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a5269-214"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="a5269-215">Чтобы приступить к работе, перейдите на страницу ваших доменов в Azure, используя [эту ссылку](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="a5269-215">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="a5269-216">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="a5269-216">You'll be prompted to log in first.</span></span>
    
    ![Azure — BP — configure – 1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="a5269-218">На странице **"панель мониторинга"** в области " **все ресурсы** " выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="a5269-218">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure — BP — configure – 1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="a5269-220">На странице **Параметры** домена в области **зона DNS** выберите пункт **+ набор записей**.</span><span class="sxs-lookup"><span data-stu-id="a5269-220">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure — BP — configure – 1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="a5269-222">Добавьте первую из четырех записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="a5269-222">Add the first of the four CNAME records.</span></span>
    
    <span data-ttu-id="a5269-223">В поля для нового набора записей в области **Добавление набора записей** введите (или скопируйте и вставьте) значения из первой строки в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="a5269-223">In the **Add record set** area, in the boxes for the new record set, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="a5269-224">В раскрывающихся списках выберите значения **Type (тип** ) и **TTL (TTL** ).</span><span class="sxs-lookup"><span data-stu-id="a5269-224">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="a5269-225">**Имя**</span><span class="sxs-lookup"><span data-stu-id="a5269-225">**Name**</span></span>|<span data-ttu-id="a5269-226">**Тип**</span><span class="sxs-lookup"><span data-stu-id="a5269-226">**Type**</span></span>|<span data-ttu-id="a5269-227">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="a5269-227">**TTL**</span></span>|<span data-ttu-id="a5269-228">**Единица срока жизни**</span><span class="sxs-lookup"><span data-stu-id="a5269-228">**TTL unit**</span></span>|<span data-ttu-id="a5269-229">**Alias**</span><span class="sxs-lookup"><span data-stu-id="a5269-229">**Alias**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a5269-230">autodiscover</span><span class="sxs-lookup"><span data-stu-id="a5269-230">autodiscover</span></span>  <br/> |<span data-ttu-id="a5269-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="a5269-231">CNAME</span></span>  <br/> |<span data-ttu-id="a5269-232">1,1</span><span class="sxs-lookup"><span data-stu-id="a5269-232">1</span></span>  <br/> |<span data-ttu-id="a5269-233">Часы</span><span class="sxs-lookup"><span data-stu-id="a5269-233">Hours</span></span>  <br/> |<span data-ttu-id="a5269-234">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a5269-234">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="a5269-235">sip</span><span class="sxs-lookup"><span data-stu-id="a5269-235">sip</span></span>  <br/> |<span data-ttu-id="a5269-236">CNAME</span><span class="sxs-lookup"><span data-stu-id="a5269-236">CNAME</span></span>  <br/> |<span data-ttu-id="a5269-237">1,1</span><span class="sxs-lookup"><span data-stu-id="a5269-237">1</span></span>  <br/> |<span data-ttu-id="a5269-238">Часы</span><span class="sxs-lookup"><span data-stu-id="a5269-238">Hours</span></span>  <br/> |<span data-ttu-id="a5269-239">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a5269-239">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a5269-240">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a5269-240">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a5269-241">CNAME</span><span class="sxs-lookup"><span data-stu-id="a5269-241">CNAME</span></span>  <br/> |<span data-ttu-id="a5269-242">1,1</span><span class="sxs-lookup"><span data-stu-id="a5269-242">1</span></span>  <br/> |<span data-ttu-id="a5269-243">Часы</span><span class="sxs-lookup"><span data-stu-id="a5269-243">Hours</span></span>  <br/> |<span data-ttu-id="a5269-244">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a5269-244">webdir.online.lync.com</span></span>  <br/> |
    
   
    ![Azure — BP — configure – 3-1](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. <span data-ttu-id="a5269-246">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a5269-246">Select **OK**.</span></span>
    
    ![Azure — BP — configure – 3-2](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. <span data-ttu-id="a5269-248">Добавьте остальные три записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="a5269-248">Add each of the other three CNAME records.</span></span>
    
    <span data-ttu-id="a5269-249">В области **зона DNS** выберите **+ набор записей**.</span><span class="sxs-lookup"><span data-stu-id="a5269-249">In the **DNS zone** area, select **+ Record set**.</span></span> <span data-ttu-id="a5269-250">Затем в пустом наборе записей создайте запись, используя значения из следующей строки таблицы, и снова нажмите кнопку **ОК** , чтобы завершить эту запись.</span><span class="sxs-lookup"><span data-stu-id="a5269-250">Then, in the empty record set, create a record by using the values from the next row in the table, and again select **OK** to complete that record.</span></span> 
    
    <span data-ttu-id="a5269-251">Повторяйте эту процедуру, пока не будут созданы все четыре записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="a5269-251">Repeat this process until you have created all four CNAME records.</span></span>
    
7.  <span data-ttu-id="a5269-252">Необязательно Добавьте 2 записи CNAME для MDM.</span><span class="sxs-lookup"><span data-stu-id="a5269-252">(Optional) Add 2 CNAME records for MDM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a5269-253">Если у вас есть управление мобильными устройствами (MDM) для Майкрософт, необходимо создать две дополнительные записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="a5269-253">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="a5269-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="a5269-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="a5269-255">(Если MDM нет, вы можете пропустить этот шаг.)</span><span class="sxs-lookup"><span data-stu-id="a5269-255">(If you do not have MDM, you can skip this step.)</span></span> 
  
|<span data-ttu-id="a5269-256">**Имя**</span><span class="sxs-lookup"><span data-stu-id="a5269-256">**Name**</span></span>|<span data-ttu-id="a5269-257">**Тип**</span><span class="sxs-lookup"><span data-stu-id="a5269-257">**Type**</span></span>|<span data-ttu-id="a5269-258">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="a5269-258">**TTL**</span></span>|<span data-ttu-id="a5269-259">**Единица срока жизни**</span><span class="sxs-lookup"><span data-stu-id="a5269-259">**TTL unit**</span></span>|<span data-ttu-id="a5269-260">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="a5269-260">**Alias**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a5269-261">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a5269-261">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a5269-262">CNAME</span><span class="sxs-lookup"><span data-stu-id="a5269-262">CNAME</span></span>  <br/> |<span data-ttu-id="a5269-263">1,1</span><span class="sxs-lookup"><span data-stu-id="a5269-263">1</span></span>  <br/> |<span data-ttu-id="a5269-264">Часы</span><span class="sxs-lookup"><span data-stu-id="a5269-264">Hours</span></span>  <br/> |<span data-ttu-id="a5269-265">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="a5269-265">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="a5269-266">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a5269-266">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a5269-267">CNAME</span><span class="sxs-lookup"><span data-stu-id="a5269-267">CNAME</span></span>  <br/> |<span data-ttu-id="a5269-268">1,1</span><span class="sxs-lookup"><span data-stu-id="a5269-268">1</span></span>  <br/> |<span data-ttu-id="a5269-269">Часы</span><span class="sxs-lookup"><span data-stu-id="a5269-269">Hours</span></span>  <br/> |<span data-ttu-id="a5269-270">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a5269-270">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a5269-271">Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама</span><span class="sxs-lookup"><span data-stu-id="a5269-271">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a5269-272"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a5269-272"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a5269-273">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="a5269-273">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a5269-274">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="a5269-274">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a5269-275">Если у вас уже есть запись SPF для вашего домена, не создавайте ее для Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a5269-275">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="a5269-276">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="a5269-276">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="a5269-277">Чтобы приступить к работе, перейдите на страницу ваших доменов в Azure, используя [эту ссылку](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="a5269-277">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="a5269-278">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="a5269-278">You'll be prompted to log in first.</span></span>
    
    ![Azure — BP — configure – 1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="a5269-280">На странице **"панель мониторинга"** в области " **все ресурсы** " выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="a5269-280">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure — BP — configure – 1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="a5269-282">В области **зона DNS** выберите **набор записей TXT**.</span><span class="sxs-lookup"><span data-stu-id="a5269-282">In the **DNS zone** area, select the **TXT record set**.</span></span>
    
    ![Azure — BP — configure – 4-1](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. <span data-ttu-id="a5269-284">В полях для нового набора записей в области **Свойства набора записей** выберите значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="a5269-284">In the **Record set properties** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="a5269-285">В раскрывающихся списках выберите значения **Type (тип** ) и **TTL (TTL** ).</span><span class="sxs-lookup"><span data-stu-id="a5269-285">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="a5269-286">**Имя**</span><span class="sxs-lookup"><span data-stu-id="a5269-286">**Name**</span></span>|<span data-ttu-id="a5269-287">**Тип**</span><span class="sxs-lookup"><span data-stu-id="a5269-287">**Type**</span></span>|<span data-ttu-id="a5269-288">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="a5269-288">**TTL**</span></span>|<span data-ttu-id="a5269-289">**Единица срока жизни**</span><span class="sxs-lookup"><span data-stu-id="a5269-289">**TTL unit**</span></span>|<span data-ttu-id="a5269-290">**Значение**</span><span class="sxs-lookup"><span data-stu-id="a5269-290">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="a5269-291">TXT</span><span class="sxs-lookup"><span data-stu-id="a5269-291">TXT</span></span>  <br/> |<span data-ttu-id="a5269-292">1,1</span><span class="sxs-lookup"><span data-stu-id="a5269-292">1</span></span>  <br/> |<span data-ttu-id="a5269-293">Часы</span><span class="sxs-lookup"><span data-stu-id="a5269-293">Hours</span></span>  <br/> |<span data-ttu-id="a5269-294">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a5269-294">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="a5269-295">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="a5269-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           

    ![Azure — BP — configure – 4-2](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. <span data-ttu-id="a5269-297">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a5269-297">Select **Save**.</span></span>
    
    ![Azure — BP — configure – 4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="a5269-299">Добавление двух записей SRV, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a5269-299">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="a5269-300"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a5269-300"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="a5269-301">Чтобы приступить к работе, перейдите на страницу ваших доменов в Azure, используя [эту ссылку](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="a5269-301">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="a5269-302">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="a5269-302">You'll be prompted to log in first.</span></span>
    
    ![Azure — BP — configure – 1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="a5269-304">На странице **"панель мониторинга"** в области " **все ресурсы** " выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="a5269-304">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure — BP — configure – 1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="a5269-306">На странице **Параметры** домена в области **зона DNS** выберите пункт **+ набор записей**.</span><span class="sxs-lookup"><span data-stu-id="a5269-306">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure — BP — configure – 1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="a5269-308">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="a5269-308">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="a5269-309">В поля для нового набора записей в области **Добавление набора записей** выберите значения из первой строки в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="a5269-309">In the **Add record set** area, in the boxes for the new record set, select the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="a5269-310">В раскрывающихся списках выберите значения **Type (тип** ) и **TTL (TTL** ).</span><span class="sxs-lookup"><span data-stu-id="a5269-310">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="a5269-311">**Имя**</span><span class="sxs-lookup"><span data-stu-id="a5269-311">**Name**</span></span>|<span data-ttu-id="a5269-312">**Тип**</span><span class="sxs-lookup"><span data-stu-id="a5269-312">**Type**</span></span>|<span data-ttu-id="a5269-313">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="a5269-313">**TTL**</span></span>|<span data-ttu-id="a5269-314">**Единица срока жизни**</span><span class="sxs-lookup"><span data-stu-id="a5269-314">**TTL unit**</span></span>|<span data-ttu-id="a5269-315">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="a5269-315">**Priority**</span></span>|<span data-ttu-id="a5269-316">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="a5269-316">**Weight**</span></span>|<span data-ttu-id="a5269-317">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="a5269-317">**Port**</span></span>|<span data-ttu-id="a5269-318">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="a5269-318">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a5269-319">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="a5269-319">_sip._tls</span></span>  <br/> |<span data-ttu-id="a5269-320">SRV</span><span class="sxs-lookup"><span data-stu-id="a5269-320">SRV</span></span>  <br/> |<span data-ttu-id="a5269-321">1,1</span><span class="sxs-lookup"><span data-stu-id="a5269-321">1</span></span>  <br/> |<span data-ttu-id="a5269-322">Часы</span><span class="sxs-lookup"><span data-stu-id="a5269-322">Hours</span></span>  <br/> |<span data-ttu-id="a5269-323">100</span><span class="sxs-lookup"><span data-stu-id="a5269-323">100</span></span>  <br/> |<span data-ttu-id="a5269-324">1,1</span><span class="sxs-lookup"><span data-stu-id="a5269-324">1</span></span>  <br/> |<span data-ttu-id="a5269-325">443</span><span class="sxs-lookup"><span data-stu-id="a5269-325">443</span></span>  <br/> |<span data-ttu-id="a5269-326">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a5269-326">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a5269-327">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="a5269-327">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="a5269-328">SRV</span><span class="sxs-lookup"><span data-stu-id="a5269-328">SRV</span></span>  <br/> |<span data-ttu-id="a5269-329">1,1</span><span class="sxs-lookup"><span data-stu-id="a5269-329">1</span></span>  <br/> |<span data-ttu-id="a5269-330">Часы</span><span class="sxs-lookup"><span data-stu-id="a5269-330">Hours</span></span>  <br/> |<span data-ttu-id="a5269-331">100</span><span class="sxs-lookup"><span data-stu-id="a5269-331">100</span></span>  <br/> |<span data-ttu-id="a5269-332">1,1</span><span class="sxs-lookup"><span data-stu-id="a5269-332">1</span></span>  <br/> |<span data-ttu-id="a5269-333">5061</span><span class="sxs-lookup"><span data-stu-id="a5269-333">5061</span></span>  <br/> |<span data-ttu-id="a5269-334">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a5269-334">sipfed.online.lync.com</span></span>  <br/> 

    ![Azure — BP — configure – 5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. <span data-ttu-id="a5269-336">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a5269-336">Select **OK**.</span></span>
    
    ![Azure — BP — configure – 5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. <span data-ttu-id="a5269-338">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="a5269-338">Add the other SRV record.</span></span>
    
    <span data-ttu-id="a5269-339">В поля для новой записи введите (или скопируйте и вставьте) значения из второй строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="a5269-339">In the boxes for the new record, type or copy and paste the values from the second row of the table.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a5269-p120">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a5269-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
