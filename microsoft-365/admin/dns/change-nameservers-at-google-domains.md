---
title: Изменение серверов доменных имен для настройки Microsoft с помощью доменов Google
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
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: Узнайте, как настроить Майкрософт для управления записями DNS в пользовательском домене в Google Domains.
ms.openlocfilehash: ac2f98a6ff783917d88a2bd8d28e8242e0ba41a8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629903"
---
# <a name="change-nameservers-to-set-up-microsoft-with-google-domains"></a><span data-ttu-id="4ca6d-103">Изменение серверов доменных имен для настройки Microsoft с помощью доменов Google</span><span class="sxs-lookup"><span data-stu-id="4ca6d-103">Change nameservers to set up Microsoft with Google Domains</span></span>

 <span data-ttu-id="4ca6d-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="4ca6d-105">Если вы хотите, чтобы корпорация Майкрософт управляла своими записями DNS, следуйте приведенным ниже инструкциям.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="4ca6d-106">(При желании вы можете [управлять всеми своими записями DNS в Google Domains](create-dns-records-at-google-domains.md).)</span><span class="sxs-lookup"><span data-stu-id="4ca6d-106">(If you prefer, you can [manage all your DNS records at Google Domains](create-dns-records-at-google-domains.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="4ca6d-107">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="4ca6d-107">Add a TXT record for verification</span></span>

<span data-ttu-id="4ca6d-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="4ca6d-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="4ca6d-112">Чтобы приступить к работе, перейдите на страницу ваших доменов в Google Domains с помощью [этой ссылки](https://domains.google.com/registrar).</span><span class="sxs-lookup"><span data-stu-id="4ca6d-112">To get started, go to your domains page at Google Domains via [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="4ca6d-113">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-113">You'll be prompted to sign in.</span></span> <span data-ttu-id="4ca6d-114">To do so:</span><span class="sxs-lookup"><span data-stu-id="4ca6d-114">To do so:</span></span>
    
1. <span data-ttu-id="4ca6d-115">Нажмите кнопку **войти**.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-115">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="4ca6d-116">Введите учетные данные для входа и еще раз нажмите кнопку **войти**.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-116">Enter your login credentials and again select **Sign In**.</span></span>
    
2. <span data-ttu-id="4ca6d-117">На странице **домены** в разделе **домен** выберите **Настройка DNS** для домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-117">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="4ca6d-118">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-118">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="4ca6d-119">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="4ca6d-119">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="4ca6d-120">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="4ca6d-120">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4ca6d-121">**Имя**</span><span class="sxs-lookup"><span data-stu-id="4ca6d-121">**Name**</span></span> <br/> |<span data-ttu-id="4ca6d-122">**Тип**</span><span class="sxs-lookup"><span data-stu-id="4ca6d-122">**Type**</span></span> <br/> |<span data-ttu-id="4ca6d-123">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="4ca6d-123">**TTL**</span></span> <br/> |<span data-ttu-id="4ca6d-124">**Data (Данные)**</span><span class="sxs-lookup"><span data-stu-id="4ca6d-124">**Data**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="4ca6d-125">TXT</span><span class="sxs-lookup"><span data-stu-id="4ca6d-125">TXT</span></span>  <br/> |<span data-ttu-id="4ca6d-126">1H</span><span class="sxs-lookup"><span data-stu-id="4ca6d-126">1H</span></span>  <br/> |<span data-ttu-id="4ca6d-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="4ca6d-127">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="4ca6d-128">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-128">**Note:** This is an example.</span></span> <span data-ttu-id="4ca6d-129">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-129">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="4ca6d-130">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="4ca6d-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. <span data-ttu-id="4ca6d-131">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="4ca6d-131">Select **Add**.</span></span>
    
5. <span data-ttu-id="4ca6d-132">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="4ca6d-133">Теперь, когда вы добавили запись на сайт регистратора доменных имен, вернитесь в корпорацию Майкрософт и запросите Поиск записи.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="4ca6d-134">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-134">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="4ca6d-135">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-135">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="4ca6d-136">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="4ca6d-137">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="4ca6d-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="4ca6d-138">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="4ca6d-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4ca6d-p106">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4ca6d-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="4ca6d-142">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="4ca6d-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="4ca6d-143">Чтобы завершить настройку домена с помощью корпорации Майкрософт, измените записи NS своего домена в регистраторе доменных имен, чтобы они ссылались на основной и дополнительный серверы имен Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-143">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="4ca6d-144">Эта настройка позволяет настроить Microsoft для обновления записей DNS домена.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-144">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="4ca6d-145">Мы добавим все записи, так что электронная почта, Skype для бизнеса online и общедоступный веб-сайт будут работать в вашем домене и вам больше не придется ничего настраивать.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-145">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="4ca6d-146">Когда вы изменяете записи NS домена так, чтобы они ссылались на серверы имен Майкрософт, затрагиваются все службы, связанные с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-146">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="4ca6d-147">Например, все сообщения электронной почты, отправленные в ваш домен (например, rob@ *your_domain.*</span><span class="sxs-lookup"><span data-stu-id="4ca6d-147">For example, all email sent to your domain (like rob@ *your_domain.*</span></span>  <span data-ttu-id="4ca6d-148">com) после внесения этого изменения будет начато до корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-148">com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="4ca6d-149">В приведенной ниже процедуре показано, как удалить из списка все остальные, нежелательные серверы имен, а также как добавить правильные серверы имен, если их еще нет в данном списке.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-149">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span></span> <span data-ttu-id="4ca6d-150">> после выполнения действий, описанных в этом разделе, единственным серверов доменных имен, которые должны быть указаны, являются следующие четыре:</span><span class="sxs-lookup"><span data-stu-id="4ca6d-150">> When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span> 
  
1. <span data-ttu-id="4ca6d-p110">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Google Domains по [этой ссылке](https://domains.google.com/registrar). Сначала вам потребуется войти. Вот как это сделать.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-p110">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="4ca6d-154">Нажмите кнопку **войти**.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-154">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="4ca6d-155">Введите свои учетные данные для входа, а затем снова нажмите кнопку **войти**.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-155">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="4ca6d-156">На странице **домены** в разделе **домен** выберите **Настройка DNS** для домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-156">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="4ca6d-157">На странице **Domains** (Домены) в разделе **Name servers** (Серверы доменных имен) выберите параметр **Use custom name servers** (Использовать настраиваемые серверы доменных имен).</span><span class="sxs-lookup"><span data-stu-id="4ca6d-157">On the **Domains** page, in the **Name servers** section, select **Use custom name servers**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-1](../../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. <span data-ttu-id="4ca6d-159">В зависимости от того, указаны ли уже серверы доменных имен на странице, которая отображается на экране, воспользуйтесь одной из двух процедур.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="4ca6d-160">Если на странице **НЕ УКАЗАНЫ** серверы доменных имен, [На странице НЕ УКАЗАНЫ серверы доменных имен](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="4ca6d-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="4ca6d-161">Если на странице **УКАЗАНЫ** серверы доменных имен, [На странице УКАЗАНЫ серверы доменных имен](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="4ca6d-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="4ca6d-162">На странице НЕ УКАЗАНЫ серверы доменных имен</span><span class="sxs-lookup"><span data-stu-id="4ca6d-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="4ca6d-163">Добавьте основной сервер доменных имен.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-163">Add the first nameserver.</span></span>
    
    <span data-ttu-id="4ca6d-164">В разделе **Name servers** (Серверы доменных имен) введите (или скопируйте и вставьте) в поле **NAME SERVER** (Сервер доменных имен) первое значение из приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-164">In the **Name servers** section, in the **NAME SERVER** box, type or copy and paste the first value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="4ca6d-165">**Основной сервер доменных имен**</span><span class="sxs-lookup"><span data-stu-id="4ca6d-165">**First name server**</span></span> <br/> |<span data-ttu-id="4ca6d-166">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4ca6d-166">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="4ca6d-167">**Дополнительный сервер доменных имен**</span><span class="sxs-lookup"><span data-stu-id="4ca6d-167">**Second name server**</span></span> <br/> |<span data-ttu-id="4ca6d-168">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4ca6d-168">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="4ca6d-169">**Третий сервер доменных имен**</span><span class="sxs-lookup"><span data-stu-id="4ca6d-169">**Third name server**</span></span> <br/> |<span data-ttu-id="4ca6d-170">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4ca6d-170">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="4ca6d-171">**Четвертый сервер доменных имен**</span><span class="sxs-lookup"><span data-stu-id="4ca6d-171">**Fourth name server**</span></span> <br/> |<span data-ttu-id="4ca6d-172">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4ca6d-172">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google — домены — BP — redelegate — 1-2](../../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. <span data-ttu-id="4ca6d-174">Выберите элемент управления **+ (Добавить)** , чтобы создать пустую строку.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-174">Select the **+ (add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-3](../../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. <span data-ttu-id="4ca6d-176">Добавьте три другие записи серверов доменных имен.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-176">Add the other three Nameserver records.</span></span>
    
    <span data-ttu-id="4ca6d-177">В разделе **Использование настраиваемых серверов имен** создайте запись, используя значения из следующей строки таблицы, а затем выберите элемент управления **+ (Add)** , чтобы добавить еще одну строку.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-177">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+ (add)** control to add another row.</span></span> 
    
    <span data-ttu-id="4ca6d-178">Повторяйте эти действия, пока не создадите все четыре записи серверов доменных имен.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-178">Repeat this process until you have created all four Nameserver records.</span></span>
    
4. <span data-ttu-id="4ca6d-179">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-179">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="4ca6d-181">На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-181">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="4ca6d-182">После этого ваша электронная почта Майкрософт и другие службы будут настроены для работы с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-182">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="4ca6d-183">На странице УКАЗАНЫ серверы доменных имен</span><span class="sxs-lookup"><span data-stu-id="4ca6d-183">If there ARE nameservers already listed</span></span>

1. <span data-ttu-id="4ca6d-184">Если в списке есть другие серверов доменных имен, нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-184">If there are any other nameservers listed, select **Edit**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="4ca6d-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="4ca6d-186">(То есть удалите только те текущие серверов доменных имен, которые *не* называются **NS1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**или **NS4.BDM.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="4ca6d-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. <span data-ttu-id="4ca6d-188">Удалите каждый сервер, выделив его и нажав клавишу **DELETE**.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-188">Delete each one by selecting it, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. <span data-ttu-id="4ca6d-190">Здесь же, в разделе **Name servers** (Серверы доменных имен), введите (или скопируйте и вставьте) в строках **NAME SERVER** (Сервер доменных имен) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-190">Still in the **Name servers** section, in the **NAME SERVER** rows, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="4ca6d-191">**Основной сервер доменных имен**</span><span class="sxs-lookup"><span data-stu-id="4ca6d-191">**First name server**</span></span> <br/> |<span data-ttu-id="4ca6d-192">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4ca6d-192">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="4ca6d-193">**Дополнительный сервер доменных имен**</span><span class="sxs-lookup"><span data-stu-id="4ca6d-193">**Second name server**</span></span> <br/> |<span data-ttu-id="4ca6d-194">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4ca6d-194">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="4ca6d-195">**Третий сервер доменных имен**</span><span class="sxs-lookup"><span data-stu-id="4ca6d-195">**Third name server**</span></span> <br/> |<span data-ttu-id="4ca6d-196">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4ca6d-196">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="4ca6d-197">**Четвертый сервер доменных имен**</span><span class="sxs-lookup"><span data-stu-id="4ca6d-197">**Fourth name server**</span></span> <br/> |<span data-ttu-id="4ca6d-198">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4ca6d-198">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google — домены — BP — redelegate — 1-7](../../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. <span data-ttu-id="4ca6d-200">Выберите элемент управления **+ (Добавить)** , чтобы создать пустую строку.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-200">Select the **+(add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-8](../../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. <span data-ttu-id="4ca6d-202">Добавьте две другие записи серверов доменных имен.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-202">Add the other two Nameserver records.</span></span>
    
    <span data-ttu-id="4ca6d-203">В разделе **Использование настраиваемых серверов имен** создайте запись, используя значения из следующей строки таблицы, а затем выберите элемент управления **+ (Add)** , чтобы добавить еще одну строку.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-203">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+(add)** control to add another row.</span></span> 
    
    <span data-ttu-id="4ca6d-204">Повторяйте эти действия, пока не создадите все четыре записи серверов доменных имен.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-204">Repeat this process until you have created all four Nameserver records.</span></span>
    
6. <span data-ttu-id="4ca6d-205">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-205">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="4ca6d-207">На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-207">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="4ca6d-208">После этого ваша электронная почта Майкрософт и другие службы будут настроены для работы с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="4ca6d-208">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
