---
title: Изменение доменных имен для microsoft с доменами Google
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
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: Узнайте, как настроить Майкрософт для управления записями DNS вашего пользовательского домена на сайте Google Domains.
ms.openlocfilehash: e475e222b6f1c9717008a49b172b0ecac5ec6fc7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658444"
---
# <a name="change-nameservers-to-set-up-microsoft-with-google-domains"></a><span data-ttu-id="b9a96-103">Изменение доменных имен для microsoft с доменами Google</span><span class="sxs-lookup"><span data-stu-id="b9a96-103">Change nameservers to set up Microsoft with Google Domains</span></span>

 <span data-ttu-id="b9a96-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="b9a96-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b9a96-105">Следуйте этим инструкциям, если вы хотите, чтобы корпорация Майкрософт управляет вашими записями DNS.</span><span class="sxs-lookup"><span data-stu-id="b9a96-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="b9a96-106">(При этом вы можете управлять всеми своими [записями DNS на сайте Google Domains.)](create-dns-records-at-google-domains.md)</span><span class="sxs-lookup"><span data-stu-id="b9a96-106">(If you prefer, you can [manage all your DNS records at Google Domains](create-dns-records-at-google-domains.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b9a96-107">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="b9a96-107">Add a TXT record for verification</span></span>

<span data-ttu-id="b9a96-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="b9a96-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="b9a96-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="b9a96-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="b9a96-112">To get started, go to your domains page at Google Domains via [this link](https://domains.google.com/registrar).</span><span class="sxs-lookup"><span data-stu-id="b9a96-112">To get started, go to your domains page at Google Domains via [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="b9a96-113">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="b9a96-113">You'll be prompted to sign in.</span></span> <span data-ttu-id="b9a96-114">To do so:</span><span class="sxs-lookup"><span data-stu-id="b9a96-114">To do so:</span></span>
    
1. <span data-ttu-id="b9a96-115">Нажмите **Sign In** (Войти).</span><span class="sxs-lookup"><span data-stu-id="b9a96-115">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="b9a96-116">Введите учетные данные для входа и снова выберите **"Вход".**</span><span class="sxs-lookup"><span data-stu-id="b9a96-116">Enter your login credentials and again select **Sign In**.</span></span>
    
2. <span data-ttu-id="b9a96-117">На странице **Domains** (Домены) в разделе **Domain** (Домен) выберите команду **Configure DNS** (Настроить DNS) для того домена, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="b9a96-117">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="b9a96-118">В разделе **Custom resource records** (Настраиваемые записи ресурсов) в полях для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="b9a96-118">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b9a96-119">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="b9a96-119">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="b9a96-120">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="b9a96-120">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b9a96-121">**Имя**</span><span class="sxs-lookup"><span data-stu-id="b9a96-121">**Name**</span></span> <br/> |<span data-ttu-id="b9a96-122">**Type** (Тип)</span><span class="sxs-lookup"><span data-stu-id="b9a96-122">**Type**</span></span> <br/> |<span data-ttu-id="b9a96-123">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="b9a96-123">**TTL**</span></span> <br/> |<span data-ttu-id="b9a96-124">**Data** (Данные)</span><span class="sxs-lookup"><span data-stu-id="b9a96-124">**Data**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="b9a96-125">TXT</span><span class="sxs-lookup"><span data-stu-id="b9a96-125">TXT</span></span>  <br/> |<span data-ttu-id="b9a96-126">1H (1 ч)</span><span class="sxs-lookup"><span data-stu-id="b9a96-126">1H</span></span>  <br/> |<span data-ttu-id="b9a96-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b9a96-127">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="b9a96-128">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="b9a96-128">**Note:** This is an example.</span></span> <span data-ttu-id="b9a96-129">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="b9a96-129">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="b9a96-130">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="b9a96-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. <span data-ttu-id="b9a96-131">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="b9a96-131">Select **Add**.</span></span>
    
5. <span data-ttu-id="b9a96-132">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="b9a96-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b9a96-133">Теперь, когда вы добавили запись на сайте регистратора доменных имен, вы вернемся в корпорацию Майкрософт и запросите поиск записи.</span><span class="sxs-lookup"><span data-stu-id="b9a96-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="b9a96-134">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="b9a96-134">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b9a96-135">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="b9a96-135">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="b9a96-136">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="b9a96-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="b9a96-137">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="b9a96-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="b9a96-138">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="b9a96-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b9a96-p106">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b9a96-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="b9a96-142">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="b9a96-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="b9a96-143">Чтобы завершить настройку домена с помощью Майкрософт, измените записи сервера доменных имен своего домена у регистратора доменных имен, чтобы они указать на основной и дополнительный серверы доменных имен Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b9a96-143">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="b9a96-144">Это настраивает Майкрософт для обновления записей DNS домена за вас.</span><span class="sxs-lookup"><span data-stu-id="b9a96-144">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="b9a96-145">Мы добавим все записи, так что электронная почта, Skype для бизнеса online и общедоступный веб-сайт будут работать в вашем домене и вам больше не придется ничего настраивать.</span><span class="sxs-lookup"><span data-stu-id="b9a96-145">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="b9a96-146">При изменении записей сервера доменных имен таким образом, чтобы они указывают на серверы доменных имен Майкрософт, это влияет на все службы, связанные с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="b9a96-146">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="b9a96-147">Например, все сообщения электронной почты, отправленные на ваш домен (например, rob@ *your_domain.*</span><span class="sxs-lookup"><span data-stu-id="b9a96-147">For example, all email sent to your domain (like rob@ *your_domain.*</span></span>  <span data-ttu-id="b9a96-148">com) начнется после внести это изменение в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b9a96-148">com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b9a96-149">В приведенной ниже процедуре показано, как удалить из списка все остальные, нежелательные серверы имен, а также как добавить правильные серверы имен, если их еще нет в данном списке.</span><span class="sxs-lookup"><span data-stu-id="b9a96-149">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span></span> <span data-ttu-id="b9a96-150">> после завершения действий, указанных в этом разделе, в списке должны быть указаны только следующие четыре.</span><span class="sxs-lookup"><span data-stu-id="b9a96-150">> When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span> 
  
1. <span data-ttu-id="b9a96-p110">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Google Domains по [этой ссылке](https://domains.google.com/registrar). Сначала вам потребуется войти. Вот как это сделать.</span><span class="sxs-lookup"><span data-stu-id="b9a96-p110">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="b9a96-154">Нажмите **Sign In** (Войти).</span><span class="sxs-lookup"><span data-stu-id="b9a96-154">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="b9a96-155">Введите данные для входа и еще раз нажмите кнопку **Sign In** (Войти).</span><span class="sxs-lookup"><span data-stu-id="b9a96-155">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="b9a96-156">На странице **Domains** (Домены) в разделе **Domain** (Домен) выберите команду **Configure DNS** (Настроить DNS) для того домена, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="b9a96-156">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="b9a96-157">На странице **Domains** (Домены) в разделе **Name servers** (Серверы доменных имен) выберите параметр **Use custom name servers** (Использовать настраиваемые серверы доменных имен).</span><span class="sxs-lookup"><span data-stu-id="b9a96-157">On the **Domains** page, in the **Name servers** section, select **Use custom name servers**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-1](../../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. <span data-ttu-id="b9a96-159">В зависимости от того, указаны ли уже серверы доменных имен на странице, которая отображается на экране, воспользуйтесь одной из двух процедур.</span><span class="sxs-lookup"><span data-stu-id="b9a96-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="b9a96-160">Если на странице **НЕ УКАЗАНЫ** серверы доменных имен, [На странице НЕ УКАЗАНЫ серверы доменных имен](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="b9a96-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="b9a96-161">Если на странице **УКАЗАНЫ** серверы доменных имен, [На странице УКАЗАНЫ серверы доменных имен](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="b9a96-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="b9a96-162">На странице НЕ УКАЗАНЫ серверы доменных имен</span><span class="sxs-lookup"><span data-stu-id="b9a96-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="b9a96-163">Добавьте основной сервер доменных имен.</span><span class="sxs-lookup"><span data-stu-id="b9a96-163">Add the first nameserver.</span></span>
    
    <span data-ttu-id="b9a96-164">В разделе **Name servers** (Серверы доменных имен) введите (или скопируйте и вставьте) в поле **NAME SERVER** (Сервер доменных имен) первое значение из приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="b9a96-164">In the **Name servers** section, in the **NAME SERVER** box, type or copy and paste the first value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="b9a96-165">**Основной сервер доменных имен**</span><span class="sxs-lookup"><span data-stu-id="b9a96-165">**First name server**</span></span> <br/> |<span data-ttu-id="b9a96-166">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b9a96-166">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b9a96-167">**Дополнительный сервер доменных имен**</span><span class="sxs-lookup"><span data-stu-id="b9a96-167">**Second name server**</span></span> <br/> |<span data-ttu-id="b9a96-168">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b9a96-168">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b9a96-169">**Третий сервер доменных имен**</span><span class="sxs-lookup"><span data-stu-id="b9a96-169">**Third name server**</span></span> <br/> |<span data-ttu-id="b9a96-170">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b9a96-170">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b9a96-171">**Четвертый сервер доменных имен**</span><span class="sxs-lookup"><span data-stu-id="b9a96-171">**Fourth name server**</span></span> <br/> |<span data-ttu-id="b9a96-172">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b9a96-172">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-Domains-BP-Redelegate-1-2](../../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. <span data-ttu-id="b9a96-174">Выберите **кнопку +(добавить),** чтобы создать пустую строку.</span><span class="sxs-lookup"><span data-stu-id="b9a96-174">Select the **+ (add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-3](../../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. <span data-ttu-id="b9a96-176">Добавьте три другие записи серверов доменных имен.</span><span class="sxs-lookup"><span data-stu-id="b9a96-176">Add the other three Nameserver records.</span></span>
    
    <span data-ttu-id="b9a96-177">В разделе **"Использование** пользовательских серверов имен" создайте запись, используя значения из следующей строки таблицы, а затем выберите кнопку **+(добавить),** чтобы добавить другую строку.</span><span class="sxs-lookup"><span data-stu-id="b9a96-177">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+ (add)** control to add another row.</span></span> 
    
    <span data-ttu-id="b9a96-178">Повторяйте эти действия, пока не создадите все четыре записи серверов доменных имен.</span><span class="sxs-lookup"><span data-stu-id="b9a96-178">Repeat this process until you have created all four Nameserver records.</span></span>
    
4. <span data-ttu-id="b9a96-179">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b9a96-179">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="b9a96-181">На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="b9a96-181">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="b9a96-182">Затем ваша почта Майкрософт и другие службы будут настроены для работы с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="b9a96-182">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="b9a96-183">На странице УКАЗАНЫ серверы доменных имен</span><span class="sxs-lookup"><span data-stu-id="b9a96-183">If there ARE nameservers already listed</span></span>

1. <span data-ttu-id="b9a96-184">Если в списке есть другие доменные имена, выберите **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="b9a96-184">If there are any other nameservers listed, select **Edit**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="b9a96-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="b9a96-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="b9a96-186">(То есть удалите только те текущие  доменные имена, которые не **ns1.bdm.microsoftonline.com,** **ns2.bdm.microsoftonline.com,** **ns3.bdm.microsoftonline.com** или **ns4.bdm.microsoftonline.com.)**</span><span class="sxs-lookup"><span data-stu-id="b9a96-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. <span data-ttu-id="b9a96-188">Удалите каждый сервер, выделив его и нажав клавишу **DELETE**.</span><span class="sxs-lookup"><span data-stu-id="b9a96-188">Delete each one by selecting it, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. <span data-ttu-id="b9a96-190">Здесь же, в разделе **Name servers** (Серверы доменных имен), введите (или скопируйте и вставьте) в строках **NAME SERVER** (Сервер доменных имен) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="b9a96-190">Still in the **Name servers** section, in the **NAME SERVER** rows, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="b9a96-191">**Основной сервер доменных имен**</span><span class="sxs-lookup"><span data-stu-id="b9a96-191">**First name server**</span></span> <br/> |<span data-ttu-id="b9a96-192">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b9a96-192">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b9a96-193">**Дополнительный сервер доменных имен**</span><span class="sxs-lookup"><span data-stu-id="b9a96-193">**Second name server**</span></span> <br/> |<span data-ttu-id="b9a96-194">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b9a96-194">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b9a96-195">**Третий сервер доменных имен**</span><span class="sxs-lookup"><span data-stu-id="b9a96-195">**Third name server**</span></span> <br/> |<span data-ttu-id="b9a96-196">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b9a96-196">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b9a96-197">**Четвертый сервер доменных имен**</span><span class="sxs-lookup"><span data-stu-id="b9a96-197">**Fourth name server**</span></span> <br/> |<span data-ttu-id="b9a96-198">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b9a96-198">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-Domains-BP-Redelegate-1-7](../../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. <span data-ttu-id="b9a96-200">Выберите **"+(add"),** чтобы создать пустую строку.</span><span class="sxs-lookup"><span data-stu-id="b9a96-200">Select the **+(add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-8](../../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. <span data-ttu-id="b9a96-202">Добавьте две другие записи серверов доменных имен.</span><span class="sxs-lookup"><span data-stu-id="b9a96-202">Add the other two Nameserver records.</span></span>
    
    <span data-ttu-id="b9a96-203">В разделе **"Использование** пользовательских серверов имен" создайте запись, используя значения из следующей строки таблицы, а затем выберите **"+(add"),** чтобы добавить другую строку.</span><span class="sxs-lookup"><span data-stu-id="b9a96-203">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+(add)** control to add another row.</span></span> 
    
    <span data-ttu-id="b9a96-204">Повторяйте эти действия, пока не создадите все четыре записи серверов доменных имен.</span><span class="sxs-lookup"><span data-stu-id="b9a96-204">Repeat this process until you have created all four Nameserver records.</span></span>
    
6. <span data-ttu-id="b9a96-205">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b9a96-205">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="b9a96-207">На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="b9a96-207">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="b9a96-208">Затем ваша почта Майкрософт и другие службы будут настроены для работы с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="b9a96-208">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
