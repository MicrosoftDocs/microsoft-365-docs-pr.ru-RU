---
title: Изменение доменных имен для microsoft с 1&1 IONOS
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
ms.assetid: 31efc571-c8b9-46fb-b42d-203c2fb25289
description: Узнайте, как настроить службу Office 365 под управлением 21Vianet для управления своими записями DNS, если поставщиком услуг размещения DNS является 1&1 Internet.
ms.openlocfilehash: b363718c7d1d1845117f44317ae9e6b24e9a2e28
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658036"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-11-ionos"></a><span data-ttu-id="38fdf-103">Изменение доменных имен для microsoft 365 с 1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="38fdf-103">Change nameservers to set up Microsoft 365 with 1&1 IONOS</span></span>

 <span data-ttu-id="38fdf-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="38fdf-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="38fdf-105">Следуйте этим инструкциям, если хотите, чтобы Microsoft 365 управляет своими записями DNS для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="38fdf-105">Follow these instructions if you want Microsoft 365 to manage your Microsoft 365 DNS records for you.</span></span> <span data-ttu-id="38fdf-106">(При этом вы можете управлять всеми своими записями DNS для [Microsoft 365 на сайте 1&1 IONOS.)](create-dns-records-at-1-1-internet.md)</span><span class="sxs-lookup"><span data-stu-id="38fdf-106">(If you prefer, you can [manage all your Microsoft 365 DNS records at 1&1 IONOS](create-dns-records-at-1-1-internet.md).)</span></span> 
  

    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="38fdf-107">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="38fdf-107">Add a TXT record for verification</span></span>


<span data-ttu-id="38fdf-p102">Прежде чем вы сможете использовать свой домен в Microsoft 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Microsoft 365 подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="38fdf-p102">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="38fdf-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="38fdf-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="38fdf-112">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 0:42)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).</span><span class="sxs-lookup"><span data-stu-id="38fdf-112">Follow the steps below or [watch the video (start at 0:42)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).</span></span>
  
1. <span data-ttu-id="38fdf-113">To get started, go to your domains page at 1&1 IONOS via [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span><span class="sxs-lookup"><span data-stu-id="38fdf-113">To get started, go to your domains page at 1&1 IONOS via [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="38fdf-114">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="38fdf-114">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="38fdf-115">В **области "МОИ ДОМЕНЫ"** выберите **"Управление доменами".**</span><span class="sxs-lookup"><span data-stu-id="38fdf-115">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="38fdf-116">На странице **"Центр доменов"** найдите домен, который нужно обновить; затем выберите для **этого домена** панель **(v).**</span><span class="sxs-lookup"><span data-stu-id="38fdf-116">On the **Domain Center** page, find the domain that you want to update; then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="38fdf-117">В области **параметров домена** выберите **"Изменить параметры DNS".**</span><span class="sxs-lookup"><span data-stu-id="38fdf-117">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="38fdf-118">В разделе **"Записи TXT и SRV"** выберите **"Добавить запись".**</span><span class="sxs-lookup"><span data-stu-id="38fdf-118">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
    <span data-ttu-id="38fdf-119">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="38fdf-119">(You may have to scroll down.)</span></span> 
    
6. <span data-ttu-id="38fdf-120">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="38fdf-120">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="38fdf-121">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="38fdf-121">**Type**</span></span> <br/> |<span data-ttu-id="38fdf-122">**Prefix (Префикс)**</span><span class="sxs-lookup"><span data-stu-id="38fdf-122">**Prefix**</span></span> <br/> |<span data-ttu-id="38fdf-123">**Name Value (Значение имени)**</span><span class="sxs-lookup"><span data-stu-id="38fdf-123">**Name Value**</span></span> <br/> |
|<span data-ttu-id="38fdf-124">TXT</span><span class="sxs-lookup"><span data-stu-id="38fdf-124">TXT</span></span>  <br/> |<span data-ttu-id="38fdf-125">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="38fdf-125">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="38fdf-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="38fdf-126">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="38fdf-127">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="38fdf-127">**Note**: This is an example.</span></span> <span data-ttu-id="38fdf-128">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="38fdf-128">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="38fdf-129">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="38fdf-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
7. <span data-ttu-id="38fdf-130">Выберите **"Сохранить"** и **"Сохранить** еще раз".</span><span class="sxs-lookup"><span data-stu-id="38fdf-130">Select **Save**, and then **Save** again.</span></span> 
    
8. <span data-ttu-id="38fdf-131">В **диалоговом окне "Изменение параметров DNS"** выберите **"Да".**</span><span class="sxs-lookup"><span data-stu-id="38fdf-131">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
9. <span data-ttu-id="38fdf-132">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="38fdf-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="38fdf-133">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Microsoft 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="38fdf-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="38fdf-134">Если Microsoft 365 обнаружит правильную запись TXT, это значит, что домен проверен.</span><span class="sxs-lookup"><span data-stu-id="38fdf-134">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="38fdf-135">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="38fdf-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="38fdf-136">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="38fdf-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="38fdf-137">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="38fdf-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="38fdf-138">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="38fdf-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="38fdf-139">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="38fdf-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="38fdf-140">Тем не менее, иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени.</span><span class="sxs-lookup"><span data-stu-id="38fdf-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="38fdf-141">Если у вас возникли проблемы с потоком почты или другие проблемы после добавления записей DNS, см. поиск и устранение проблем после добавления домена или [записей DNS в Microsoft 365.](../get-help-with-domains/find-and-fix-issues.md)</span><span class="sxs-lookup"><span data-stu-id="38fdf-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="38fdf-142">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="38fdf-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="38fdf-143">Чтобы завершить настройку домена с помощью Microsoft 365, измените записи сервера доменных имен своего домена у регистратора доменных имен, указав на основной и дополнительный серверы имен Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="38fdf-143">To complete setting up your domain with Microsoft 365, you change your domain's NS records at your domain registrar to point to the Microsoft 365 primary and secondary name servers.</span></span> <span data-ttu-id="38fdf-144">Это настраивает Microsoft 365 для обновления записей DNS домена.</span><span class="sxs-lookup"><span data-stu-id="38fdf-144">This sets up Microsoft 365 to update the domain's DNS records for you.</span></span> <span data-ttu-id="38fdf-145">Мы добавим все записи, так что электронная почта, Skype для бизнеса online и общедоступный веб-сайт будут работать в вашем домене и вам больше не придется ничего настраивать.</span><span class="sxs-lookup"><span data-stu-id="38fdf-145">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="38fdf-146">Когда вы меняете записи доменных имен, чтобы они указывают на серверы имен Microsoft 365, это влияет на все службы, связанные с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="38fdf-146">When you change your domain's NS records to point to the Microsoft 365 name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="38fdf-147">Например, все сообщения электронной почты, отправленные на ваш домен (например, rob@ *your_domain*  .com), начнут приходить в Microsoft 365 после внести это изменение.</span><span class="sxs-lookup"><span data-stu-id="38fdf-147">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft 365 after you make this change.</span></span> 
  
<span data-ttu-id="38fdf-148">Готовы изменить записи доменных имен, чтобы Microsoft 365 могли настроить ваш домен?</span><span class="sxs-lookup"><span data-stu-id="38fdf-148">Ready to change your NS records so Microsoft 365 can set up your domain?</span></span> <span data-ttu-id="38fdf-149">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 2:47)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).</span><span class="sxs-lookup"><span data-stu-id="38fdf-149">Follow the steps below or [watch the video (start at 2:47)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="38fdf-150">В следующей процедуре покажем, как удалить из списка любые другие нежелательные доменные имена, а также как добавить правильные доменные имена, если они еще не указаны.</span><span class="sxs-lookup"><span data-stu-id="38fdf-150">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="38fdf-151">> После завершения действий, указанных в этом разделе, в списке должны быть указаны только следующие четыре > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="38fdf-151">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="38fdf-152">To get started, go to your domains page at 1&1 IONOS by using [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span><span class="sxs-lookup"><span data-stu-id="38fdf-152">To get started, go to your domains page at 1&1 IONOS by using [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="38fdf-153">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="38fdf-153">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="38fdf-154">В **области "МОИ ДОМЕНЫ"** выберите **"Управление доменами".**</span><span class="sxs-lookup"><span data-stu-id="38fdf-154">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="38fdf-155">На странице **"Центр домена"** найдите домен, который  нужно обновить, а затем выберите для этого домена панель **(v).**</span><span class="sxs-lookup"><span data-stu-id="38fdf-155">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="38fdf-156">В области **параметров домена** выберите **"Изменить параметры DNS".**</span><span class="sxs-lookup"><span data-stu-id="38fdf-156">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="38fdf-157">В разделе **Name Server Settings** (Параметры сервера доменных имен) выберите **Other name servers** (Другие серверы доменных имен).</span><span class="sxs-lookup"><span data-stu-id="38fdf-157">In the **Name Server Settings** section, select **Other name servers**.</span></span>
    
    <span data-ttu-id="38fdf-158">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="38fdf-158">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="38fdf-159">В зависимости от того, указаны ли уже серверы доменных имен на странице, которая отображается на экране, воспользуйтесь одной из двух процедур.</span><span class="sxs-lookup"><span data-stu-id="38fdf-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="38fdf-160">Если на странице **НЕ УКАЗАНЫ** серверы доменных имен, [На странице НЕ УКАЗАНЫ серверы доменных имен](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="38fdf-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="38fdf-161">Если на странице **УКАЗАНЫ** серверы доменных имен, [На странице УКАЗАНЫ серверы доменных имен](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="38fdf-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="38fdf-162">На странице НЕ УКАЗАНЫ серверы доменных имен</span><span class="sxs-lookup"><span data-stu-id="38fdf-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="38fdf-163">В поле **Name server 1** (Сервер доменных имен 1) введите (или скопируйте и вставьте) значение из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="38fdf-163">In the **Name server 1** box, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="38fdf-164">**Name server 1**</span><span class="sxs-lookup"><span data-stu-id="38fdf-164">**Name server 1**</span></span> <br/> |<span data-ttu-id="38fdf-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="38fdf-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Ввод значения в поле "Сервер доменных имен 1"](../../media/34509935-461f-427f-9796-c3cf840bd9be.png)
  
2. <span data-ttu-id="38fdf-167">В раскрывающемся списке **Additional name servers** (Дополнительные серверы доменных имен) выберите **My secondary name servers** (Мои дополнительные серверы доменных имен).</span><span class="sxs-lookup"><span data-stu-id="38fdf-167">In the **Additional name servers** drop-down list, choose **My secondary name servers**.</span></span>
    
    ![Choosing My secondary name servers in the list](../../media/7eb14856-86da-45c2-910c-c72312250a18.png)
  
3. <span data-ttu-id="38fdf-169">В полях **Name server 2, 3, and 4** (Серверы доменных имен 2, 3 и 4) введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="38fdf-169">In the **Name server 2, 3, and 4** boxes, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="38fdf-170">**Name Server 2** (Сервер доменных имен 2)</span><span class="sxs-lookup"><span data-stu-id="38fdf-170">**Name server 2**</span></span> <br/> |<span data-ttu-id="38fdf-171">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="38fdf-171">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="38fdf-172">**Name Server 3** (Сервер доменных имен 3)</span><span class="sxs-lookup"><span data-stu-id="38fdf-172">**Name server 3**</span></span> <br/> |<span data-ttu-id="38fdf-173">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="38fdf-173">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="38fdf-174">**Name Server 4** (Сервер доменных имен 4)</span><span class="sxs-lookup"><span data-stu-id="38fdf-174">**Name server 4**</span></span> <br/> |<span data-ttu-id="38fdf-175">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="38fdf-175">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
![Ввод значений сервера доменных имен](../../media/0f15880c-88b6-4133-8f31-62f0d98ee63f.png)
  
4. <span data-ttu-id="38fdf-177">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="38fdf-177">Select **Save**.</span></span>
    
    ![Выбор параметра "Сохранить на странице параметров сервера доменных имен"](../../media/864f7927-7127-4784-b8d2-dadfea2f9dc8.png)
  
5. <span data-ttu-id="38fdf-179">В **диалоговом окне "Изменение параметров DNS"** выберите **"Да".**</span><span class="sxs-lookup"><span data-stu-id="38fdf-179">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![Выбор параметра "Сохранить" в диалоговом окне "Изменение параметров DNS"](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="38fdf-181">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="38fdf-181">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="38fdf-182">Затем ваша почта Майкрософт и другие службы будут настроены для работы с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="38fdf-182">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="38fdf-183">На странице УКАЗАНЫ серверы доменных имен</span><span class="sxs-lookup"><span data-stu-id="38fdf-183">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="38fdf-p113">Выполните эти действия,  *только*  если у вас есть серверы доменных имен, отличные от четырех  *правильных*  серверов. (Т. е. удалите  *только*  серверы доменных имен,  *отличные*  от **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** и **ns4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="38fdf-p113">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="38fdf-186">Если в полях **Name server** (Сервер доменных имен) указаны другие серверы доменных имен, удалите их: выберите каждый из них и нажмите клавишу **DELETE**.</span><span class="sxs-lookup"><span data-stu-id="38fdf-186">If there are already nameservers listed in the **Name server** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting name servers](../../media/af0a68cc-b058-4925-b3b1-52dfded003c1.png)
  
2. <span data-ttu-id="38fdf-188">В полях **Name server 1, 2, 3, and 4** (Серверы доменных имен 1, 2, 3 и 4) введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="38fdf-188">In the **Name server 1, 2, 3, and 4** boxes, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="38fdf-189">**Name server 1** (Сервер доменных имен 1)</span><span class="sxs-lookup"><span data-stu-id="38fdf-189">**Name server 1**</span></span> <br/> |<span data-ttu-id="38fdf-190">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="38fdf-190">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="38fdf-191">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="38fdf-191">**Name server 2**</span></span> <br/> |<span data-ttu-id="38fdf-192">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="38fdf-192">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="38fdf-193">**Name Server 3** (Сервер доменных имен 3)</span><span class="sxs-lookup"><span data-stu-id="38fdf-193">**Name server 3**</span></span> <br/> |<span data-ttu-id="38fdf-194">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="38fdf-194">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="38fdf-195">**Name Server 4** (Сервер доменных имен 4)</span><span class="sxs-lookup"><span data-stu-id="38fdf-195">**Name server 4**</span></span> <br/> |<span data-ttu-id="38fdf-196">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="38fdf-196">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Ввод значений сервера доменных имен](../../media/52826bd1-0596-4103-a728-d5d28b9610d2.png)
  
3. <span data-ttu-id="38fdf-198">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="38fdf-198">Select **Save**.</span></span>
    
    ![Выбор параметра "Сохранить на странице параметров сервера доменных имен"](../../media/cd10e4fb-b7fa-480f-855b-a443f2705cf2.png)
  
4. <span data-ttu-id="38fdf-200">В **диалоговом окне "Изменение параметров DNS"** выберите **"Да".**</span><span class="sxs-lookup"><span data-stu-id="38fdf-200">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![Выбор параметра "Сохранить" в диалоговом окне "Изменение параметров DNS"](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="38fdf-202">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="38fdf-202">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="38fdf-203">Затем ваша почта Майкрософт и другие службы будут настроены для работы с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="38fdf-203">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  


