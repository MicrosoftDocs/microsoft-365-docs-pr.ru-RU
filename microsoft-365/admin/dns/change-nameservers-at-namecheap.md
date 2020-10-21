---
title: Изменение серверов доменных имен для настройки Microsoft с помощью namecheap
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
ms.assetid: 84f467f6-28cf-40f0-94d0-a2a27ddfc2e7
description: 'Если вы хотите, чтобы Майкрософт управляла своими записями DNS, Узнайте, как настроить свой личный домен Майкрософт с помощью namecheap. '
ms.openlocfilehash: e305abb7768b286dbd24336c1dab39d919f9a0ac
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646455"
---
# <a name="change-nameservers-to-set-up-microsoft-with-namecheap"></a><span data-ttu-id="fbd90-103">Изменение серверов доменных имен для настройки Microsoft с помощью namecheap</span><span class="sxs-lookup"><span data-stu-id="fbd90-103">Change nameservers to set up Microsoft with Namecheap</span></span>

 <span data-ttu-id="fbd90-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="fbd90-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="fbd90-105">Если вы хотите, чтобы корпорация Майкрософт управляла своими записями DNS, следуйте приведенным ниже инструкциям.</span><span class="sxs-lookup"><span data-stu-id="fbd90-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="fbd90-106">(При желании вы можете [управлять всеми своими записями Microsoft DNS на сайте Namecheap](create-dns-records-at-namecheap.md).)</span><span class="sxs-lookup"><span data-stu-id="fbd90-106">(If you prefer, you can [manage all your Microsoft DNS records at Namecheap](create-dns-records-at-namecheap.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="fbd90-107">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="fbd90-107">Add a TXT record for verification</span></span>

1. <span data-ttu-id="fbd90-p102">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Namecheap по [этой ссылке](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Вам потребуется войти в службу.</span><span class="sxs-lookup"><span data-stu-id="fbd90-p102">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="fbd90-111">На **начальной** странице в разделе **учетная запись**выберите **список доменов** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="fbd90-111">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="fbd90-113">На странице **список доменов** найдите имя домена, который требуется изменить, и выберите пункт **Управление**.</span><span class="sxs-lookup"><span data-stu-id="fbd90-113">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="fbd90-115">Выберите **Advanced DNS**.</span><span class="sxs-lookup"><span data-stu-id="fbd90-115">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="fbd90-117">В разделе **записи узла** выберите **Добавить новую запись**.</span><span class="sxs-lookup"><span data-stu-id="fbd90-117">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="fbd90-119">В раскрывающемся списке **Type** (Тип) выберите **TXT Record** (Запись TXT).</span><span class="sxs-lookup"><span data-stu-id="fbd90-119">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fbd90-120">Раскрывающийся список **типов** автоматически отображается при выборе параметра **Добавить новую запись**.</span><span class="sxs-lookup"><span data-stu-id="fbd90-120">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span>
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="fbd90-122">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="fbd90-122">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="fbd90-123">В раскрывающемся списке выберите значение **TTL (срок жизни** ).</span><span class="sxs-lookup"><span data-stu-id="fbd90-123">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
|<span data-ttu-id="fbd90-124">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="fbd90-124">**Type**</span></span>|<span data-ttu-id="fbd90-125">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="fbd90-125">**Host**</span></span>|<span data-ttu-id="fbd90-126">**Value** (Значение)</span><span class="sxs-lookup"><span data-stu-id="fbd90-126">**Value**</span></span>|<span data-ttu-id="fbd90-127">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="fbd90-127">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fbd90-128">TXT</span><span class="sxs-lookup"><span data-stu-id="fbd90-128">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="fbd90-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="fbd90-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="fbd90-130">**Примечание**: это пример.</span><span class="sxs-lookup"><span data-stu-id="fbd90-130">**Note**: This is an example.</span></span> <span data-ttu-id="fbd90-131">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="fbd90-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="fbd90-132">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="fbd90-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="fbd90-133">30 мин</span><span class="sxs-lookup"><span data-stu-id="fbd90-133">30 min</span></span>  <br/> |
   
   ![Namecheap — BP — Verify – 1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="fbd90-135">Выберите элемент управления **Сохранение изменений** (галочка).</span><span class="sxs-lookup"><span data-stu-id="fbd90-135">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="fbd90-137">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="fbd90-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="fbd90-138">Теперь, когда вы добавили запись на сайт регистратора доменных имен, вернитесь в корпорацию Майкрософт и запросите Поиск записи.</span><span class="sxs-lookup"><span data-stu-id="fbd90-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="fbd90-139">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="fbd90-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="fbd90-140">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="fbd90-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="fbd90-141">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="fbd90-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="fbd90-142">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="fbd90-142">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="fbd90-143">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="fbd90-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="fbd90-p104">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fbd90-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="fbd90-147">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="fbd90-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="fbd90-148">Чтобы завершить настройку домена с помощью корпорации Майкрософт, измените записи NS своего домена в регистраторе доменных имен, чтобы они ссылались на основной и дополнительный серверы имен Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fbd90-148">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="fbd90-149">Эта настройка позволяет настроить Microsoft для обновления записей DNS домена.</span><span class="sxs-lookup"><span data-stu-id="fbd90-149">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="fbd90-150">Мы добавим все записи, так что электронная почта, Skype для бизнеса online и общедоступный веб-сайт будут работать в вашем домене и вам больше не придется ничего настраивать.</span><span class="sxs-lookup"><span data-stu-id="fbd90-150">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="fbd90-151">Когда вы изменяете записи NS домена так, чтобы они ссылались на серверы имен Майкрософт, затрагиваются все службы, связанные с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="fbd90-151">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="fbd90-152">Например, все сообщения электронной почты, отправленные в ваш домен (например, rob@ *your_domain*  . com), появятся в корпорацию Майкрософт после внесения этого изменения.</span><span class="sxs-lookup"><span data-stu-id="fbd90-152">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="fbd90-153">После выполнения действий, описанных в этом разделе, в списке должны быть указаны  *только*  следующие четыре сервера имен: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  В приведенной ниже процедуре показано, как удалить из списка все остальные, нежелательные серверы имен, а также как добавить  *правильные*  серверы имен, если их еще нет в данном списке.</span><span class="sxs-lookup"><span data-stu-id="fbd90-153">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="fbd90-p107">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Namecheap по [этой ссылке](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Вам потребуется войти в службу.</span><span class="sxs-lookup"><span data-stu-id="fbd90-p107">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="fbd90-157">На **начальной** странице в разделе **учетная запись**выберите **список доменов** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="fbd90-157">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="fbd90-159">На странице **список доменов** найдите имя домена, который требуется изменить, и выберите пункт **Управление**.</span><span class="sxs-lookup"><span data-stu-id="fbd90-159">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="fbd90-161">Выберите **домен**.</span><span class="sxs-lookup"><span data-stu-id="fbd90-161">Select **Domain**.</span></span>
    
    ![Namecheap-BP-Redelegate-1-1](../../media/59588406-794e-4ae4-8526-35e3111b5791.png)
  
5. <span data-ttu-id="fbd90-163">Найдите раздел **NAMESERVERS** (Серверы доменных имен), а затем выберите **Custom** (Другое) в раскрывающемся списке **Namecheap Default** (Значения Namecheap по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="fbd90-163">Find the **NAMESERVERS** section, and then select **Custom** from the **Namecheap Default** drop-down list.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-2](../../media/7df56295-fdb3-472f-9442-13f780c2c93e.png)
  
6. <span data-ttu-id="fbd90-165">В зависимости от того, есть ли у вас уже серверов доменных имен на отображаемой странице, перейдите к одной из двух указанных ниже процедур.</span><span class="sxs-lookup"><span data-stu-id="fbd90-165">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="fbd90-166">На странице НЕ УКАЗАНЫ серверы доменных имен</span><span class="sxs-lookup"><span data-stu-id="fbd90-166">If there are NO nameservers already listed</span></span>
<span data-ttu-id="fbd90-167"><a name="BKMK_ProcedureWithOUT"> </a></span><span class="sxs-lookup"><span data-stu-id="fbd90-167"><a name="BKMK_ProcedureWithOUT"> </a></span></span>

1. <span data-ttu-id="fbd90-168">Дважды нажмите кнопку **Добавить nameserver** , чтобы добавить две новые строки.</span><span class="sxs-lookup"><span data-stu-id="fbd90-168">Select **ADD NAMESERVER** twice to add two new rows.</span></span>
    
    ![Namecheap — BP — redelegate — 1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
2. <span data-ttu-id="fbd90-170">В поля **Nameserver** (Сервер доменных имен) введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="fbd90-170">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="fbd90-171">**Nameserver 1** (Сервер доменных имен 1)</span><span class="sxs-lookup"><span data-stu-id="fbd90-171">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="fbd90-172">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fbd90-172">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="fbd90-173">**Nameserver 2** (Сервер доменных имен 2)</span><span class="sxs-lookup"><span data-stu-id="fbd90-173">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="fbd90-174">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fbd90-174">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="fbd90-175">**Nameserver 3** (Сервер доменных имен 3)</span><span class="sxs-lookup"><span data-stu-id="fbd90-175">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="fbd90-176">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fbd90-176">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="fbd90-177">**Nameserver 4** (Сервер доменных имен 4)</span><span class="sxs-lookup"><span data-stu-id="fbd90-177">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="fbd90-178">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fbd90-178">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Namecheap — BP — redelegate — 1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
3. <span data-ttu-id="fbd90-180">Выберите элемент управления " **сохранить** " (галочка).</span><span class="sxs-lookup"><span data-stu-id="fbd90-180">Select the **Save** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="fbd90-182">На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="fbd90-182">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="fbd90-183">После этого ваша электронная почта Майкрософт и другие службы будут настроены для работы с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="fbd90-183">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="fbd90-184">На странице УКАЗАНЫ серверы доменных имен</span><span class="sxs-lookup"><span data-stu-id="fbd90-184">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="fbd90-p109">Выполните эти действия,  *только*  если у вас есть серверы доменных имен, отличные от четырех  *правильных*  серверов. (Т. е. удалите  *только*  серверы доменных имен,  *отличные*  от **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** и **ns4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="fbd90-p109">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="fbd90-187">Если в полях **Nameserver** (Сервер доменных имен) указаны другие серверы доменных имен, удалите их: выберите каждый из них и нажмите клавишу **DELETE**.</span><span class="sxs-lookup"><span data-stu-id="fbd90-187">If there are any other nameservers listed in the **Nameserver** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-4](../../media/3270603a-c4f4-40b7-acad-733d56e2f53c.png)
  
2. <span data-ttu-id="fbd90-189">Дважды нажмите кнопку **Добавить nameserver** , чтобы добавить две новые строки.</span><span class="sxs-lookup"><span data-stu-id="fbd90-189">Select **ADD NAMESERVER** twice to add two new rows.</span></span> 
    
    ![Namecheap — BP — redelegate — 1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
3. <span data-ttu-id="fbd90-191">В поля **Nameserver** (Сервер доменных имен) введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="fbd90-191">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
 
    
|||
|:-----|:-----|
|<span data-ttu-id="fbd90-192">**Name Server 1** (Сервер доменных имен 1)</span><span class="sxs-lookup"><span data-stu-id="fbd90-192">**Name Server 1**</span></span> <br/> |<span data-ttu-id="fbd90-193">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fbd90-193">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="fbd90-194">**Name Server 2** (Сервер доменных имен 2)</span><span class="sxs-lookup"><span data-stu-id="fbd90-194">**Name Server 2**</span></span> <br/> |<span data-ttu-id="fbd90-195">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fbd90-195">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="fbd90-196">**Nameserver 3** (Сервер доменных имен 3)</span><span class="sxs-lookup"><span data-stu-id="fbd90-196">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="fbd90-197">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fbd90-197">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="fbd90-198">**Nameserver 4** (Сервер доменных имен 4)</span><span class="sxs-lookup"><span data-stu-id="fbd90-198">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="fbd90-199">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fbd90-199">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Namecheap — BP — redelegate — 1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
4. <span data-ttu-id="fbd90-201">Выберите элемент управления " **сохранить** " (галочка).</span><span class="sxs-lookup"><span data-stu-id="fbd90-201">Select the **Save** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="fbd90-203">На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="fbd90-203">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="fbd90-204">После этого ваша электронная почта Майкрософт и другие службы будут настроены для работы с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="fbd90-204">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
