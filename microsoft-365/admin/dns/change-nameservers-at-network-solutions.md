---
title: Изменение серверов доменных имен для настройки Microsoft с помощью сетевых решений
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
ms.assetid: d4ba60f3-4e1c-4180-99bd-250b8955be2a
description: 'Узнайте, как настроить личный домен Майкрософт с сетевыми решениями, если вы хотите, чтобы корпорация Майкрософт управляла своими записями DNS. '
ms.openlocfilehash: 502699cf3760460a13ee067b07737037f31fa4ee
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2020
ms.locfileid: "45079881"
---
# <a name="change-nameservers-to-set-up-microsoft-with-network-solutions"></a><span data-ttu-id="e2928-103">Изменение серверов доменных имен для настройки Microsoft с помощью сетевых решений</span><span class="sxs-lookup"><span data-stu-id="e2928-103">Change nameservers to set up Microsoft with Network Solutions</span></span>

 <span data-ttu-id="e2928-104">Если вы не нашли то, что вы ищете, обратитесь к разделу **[вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="e2928-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="e2928-105">Если вы хотите, чтобы корпорация Майкрософт управляла своими записями DNS, следуйте приведенным ниже инструкциям.</span><span class="sxs-lookup"><span data-stu-id="e2928-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="e2928-106">(При желании вы можете [управлять всеми своими записями DNS Microsoft в сетевых решениях](create-dns-records-at-network-solutions.md).)</span><span class="sxs-lookup"><span data-stu-id="e2928-106">(If you prefer, you can [manage all your Microsoft DNS records at Network Solutions](create-dns-records-at-network-solutions.md).)</span></span>
  
    
## <a name="add-a-txt-record-at-network-solutions-to-verify-that-you-own-the-domain"></a><span data-ttu-id="e2928-107">Добавление записи TXT на сайте Network Solutions для подтверждения права собственности на домен</span><span class="sxs-lookup"><span data-stu-id="e2928-107">Add a TXT record at Network Solutions to verify that you own the domain</span></span>

<span data-ttu-id="e2928-108">Before you use your domain with Microsoft, we have to make sure that you own it.</span><span class="sxs-lookup"><span data-stu-id="e2928-108">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="e2928-109">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span><span class="sxs-lookup"><span data-stu-id="e2928-109">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e2928-110">This record is used only to verify that you own your domain; it doesn't affect anything else.</span><span class="sxs-lookup"><span data-stu-id="e2928-110">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> <span data-ttu-id="e2928-111">You can delete it later, if you like.</span><span class="sxs-lookup"><span data-stu-id="e2928-111">You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="e2928-112">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 0:47)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261).</span><span class="sxs-lookup"><span data-stu-id="e2928-112">Follow the steps below or [watch the video (start at 0:47)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261).</span></span>
  
1. <span data-ttu-id="e2928-113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="e2928-113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="e2928-114">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e2928-114">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e2928-115">Перед нажатием кнопки **Вход** сначала выберите пункт **Управление именами доменов** в раскрывающемся списке **Вход в:** .</span><span class="sxs-lookup"><span data-stu-id="e2928-115">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span>
  
    ![Выберите Manage My Domain Names (Управление доменными именами) и войдите в систему Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="e2928-117">Установите флажок для доменного имени, которое вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="e2928-117">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Установите флажок для своего домена](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="e2928-119">Выберите **изменить DNS**.</span><span class="sxs-lookup"><span data-stu-id="e2928-119">Select **Edit DNS**.</span></span>
    
    ![Выберите изменить DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="e2928-121">Выберите **Управление расширенными записями DNS**.</span><span class="sxs-lookup"><span data-stu-id="e2928-121">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="e2928-122">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="e2928-122">(You may have to scroll down.)</span></span>
    
    ![Выберите Управление расширенными записями DNS](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="e2928-124">Прокрутите список вниз до раздела **текст (записи TXT)** и выберите команду **изменить записи TXT**.</span><span class="sxs-lookup"><span data-stu-id="e2928-124">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Выберите команду Изменить записи TXT](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="e2928-126">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="e2928-126">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
|<span data-ttu-id="e2928-127">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="e2928-127">**Host**</span></span>|<span data-ttu-id="e2928-128">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="e2928-128">**TTL**</span></span>|<span data-ttu-id="e2928-129">**Text (Текст)**</span><span class="sxs-lookup"><span data-stu-id="e2928-129">**Text**</span></span>|
|:-----|:-----|:-----|
|@  <br/> <span data-ttu-id="e2928-130">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="e2928-130">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="e2928-131">3600</span><span class="sxs-lookup"><span data-stu-id="e2928-131">3600</span></span>  <br/> |<span data-ttu-id="e2928-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e2928-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="e2928-133">**Примечание**: это пример.</span><span class="sxs-lookup"><span data-stu-id="e2928-133">**Note**: This is an example.</span></span> <span data-ttu-id="e2928-134">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e2928-134">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="e2928-135">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="e2928-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)
   
    
   ![Введите или вставьте значения в поля для новой записи](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="e2928-137">Нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="e2928-137">Select **Continue**.</span></span>
    
    ![Нажмите кнопку продолжить.](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="e2928-139">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="e2928-139">Select **Save Changes**.</span></span>
    
    ![Нажмите кнопку Сохранить изменения](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="e2928-141">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="e2928-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e2928-142">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Microsoft 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="e2928-142">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="e2928-143">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="e2928-143">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e2928-144">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="e2928-144">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="e2928-145">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="e2928-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="e2928-146">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="e2928-146">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="e2928-147">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="e2928-147">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="e2928-148">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="e2928-148">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="e2928-149">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="e2928-149">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="e2928-150">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e2928-150">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="e2928-151">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="e2928-151">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="e2928-152">Чтобы завершить настройку домена с помощью корпорации Майкрософт, измените записи NS своего домена в регистраторе доменных имен, чтобы они ссылались на основной и дополнительный серверы имен Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e2928-152">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="e2928-153">Эта настройка позволяет настроить Microsoft для обновления записей DNS домена.</span><span class="sxs-lookup"><span data-stu-id="e2928-153">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="e2928-154">Мы добавим все записи, так что электронная почта, Skype для бизнеса online и общедоступный веб-сайт будут работать в вашем домене и вам больше не придется ничего настраивать.</span><span class="sxs-lookup"><span data-stu-id="e2928-154">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="e2928-155">Когда вы изменяете записи NS домена так, чтобы они ссылались на серверы имен Майкрософт, затрагиваются все службы, связанные с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="e2928-155">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="e2928-156">Например, все сообщения электронной почты, отправленные в ваш домен (например, rob@ *your_domain* . com), появятся в корпорацию Майкрософт после внесения этого изменения.</span><span class="sxs-lookup"><span data-stu-id="e2928-156">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span>
  
<span data-ttu-id="e2928-157">Готовы изменить записи сервера доменных имен, чтобы корпорация Майкрософт могла настроить ваш домен?</span><span class="sxs-lookup"><span data-stu-id="e2928-157">Ready to change your NS records so Microsoft can set up your domain?</span></span> <span data-ttu-id="e2928-158">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 2:23)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261).</span><span class="sxs-lookup"><span data-stu-id="e2928-158">Follow the steps below or [watch the video (start at 2:23)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261).</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="e2928-159">После выполнения действий, описанных в этом разделе, *единственным* серверов доменных имен, которые должны быть указаны, являются следующие четыре: **NS1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**и **NS4.BDM.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="e2928-159">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.</span></span> <span data-ttu-id="e2928-160">В приведенной ниже процедуре показано, как удалить из списка все остальные, нежелательные серверы имен, а также как добавить  *правильные*  серверы имен, если их еще нет в данном списке.</span><span class="sxs-lookup"><span data-stu-id="e2928-160">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="e2928-161">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Network Solutions по [этой ссылке](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="e2928-161">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="e2928-162">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="e2928-162">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e2928-163">Перед нажатием кнопки **Вход** сначала выберите пункт **Управление именами доменов** в раскрывающемся списке **Вход в:** .</span><span class="sxs-lookup"><span data-stu-id="e2928-163">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Выберите Manage My Domain Names (Управление доменными именами) и войдите в систему Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="e2928-165">Установите флажок для доменного имени, которое вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="e2928-165">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Установите флажок для своего домена](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="e2928-167">Выберите **изменить DNS**.</span><span class="sxs-lookup"><span data-stu-id="e2928-167">Select **Edit DNS**.</span></span>
    
    ![Выберите изменить DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="e2928-169">Нажмите кнопку **Move DNS (переместить DNS**).</span><span class="sxs-lookup"><span data-stu-id="e2928-169">Select **Move DNS**.</span></span>
    
    ![Нетворксолутионсбп — redelegate — 1-1](../../media/e57a30f3-63d5-4bcb-84c6-c8be21c261a2.png)
  
5. <span data-ttu-id="e2928-171">В зависимости от того, указаны ли уже серверы доменных имен на странице, которая отображается на экране, воспользуйтесь одной из двух процедур.</span><span class="sxs-lookup"><span data-stu-id="e2928-171">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="e2928-172">Если на странице **НЕ УКАЗАНЫ** серверы доменных имен, [На странице НЕ УКАЗАНЫ серверы доменных имен](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="e2928-172">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="e2928-173">Если на странице **УКАЗАНЫ** серверы доменных имен, [На странице УКАЗАНЫ серверы доменных имен](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="e2928-173">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="e2928-174">На странице НЕ УКАЗАНЫ серверы доменных имен</span><span class="sxs-lookup"><span data-stu-id="e2928-174">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="e2928-175">На странице **домены** в разделе **укажите серверы доменных имен** выберите **Добавить серверы имен**.</span><span class="sxs-lookup"><span data-stu-id="e2928-175">On the **Domains** page, in the **Specify Domain Name Servers** section, select **Add More Name Servers**.</span></span>
    
    ![Нетворксолутионсбп — redelegate — 1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
2. <span data-ttu-id="e2928-177">На странице **Domain Names** (Доменные имена) введите (или скопируйте и вставьте) значения серверов из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="e2928-177">On the **Domain Names** page, type or copy and paste the nameserver values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="e2928-178">**Name Server 1** (Сервер доменных имен 1)</span><span class="sxs-lookup"><span data-stu-id="e2928-178">**Name Server 1**</span></span> <br/> |<span data-ttu-id="e2928-179">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e2928-179">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="e2928-180">**Name Server 2** (Сервер доменных имен 2)</span><span class="sxs-lookup"><span data-stu-id="e2928-180">**Name Server 2**</span></span> <br/> |<span data-ttu-id="e2928-181">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e2928-181">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="e2928-182">**Name Server 2** (Сервер доменных имен 2)</span><span class="sxs-lookup"><span data-stu-id="e2928-182">**Name Server 2**</span></span> <br/> |<span data-ttu-id="e2928-183">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e2928-183">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="e2928-184">**Name Server 2** (Сервер доменных имен 2)</span><span class="sxs-lookup"><span data-stu-id="e2928-184">**Name Server 2**</span></span> <br/> |<span data-ttu-id="e2928-185">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e2928-185">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    
![Нетворксолутионсбп — redelegate — 1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
3. <span data-ttu-id="e2928-187">Нажмите кнопку **Move DNS (переместить DNS**).</span><span class="sxs-lookup"><span data-stu-id="e2928-187">Select **Move DNS**.</span></span>
    
    ![Нетворксолутионсбп — redelegate — 1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
4. <span data-ttu-id="e2928-189">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="e2928-189">Select **Save Changes**.</span></span>
    
    ![Нетворксолутионсбп — redelegate — 1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> <span data-ttu-id="e2928-191">На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="e2928-191">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="e2928-192">После этого ваша электронная почта Майкрософт и другие службы будут настроены для работы с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="e2928-192">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="e2928-193">На странице УКАЗАНЫ серверы доменных имен</span><span class="sxs-lookup"><span data-stu-id="e2928-193">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="e2928-194">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers.</span><span class="sxs-lookup"><span data-stu-id="e2928-194">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers.</span></span> <span data-ttu-id="e2928-195">(That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="e2928-195">(That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span>
  
1. <span data-ttu-id="e2928-196">Если на странице указаны другие серверы доменных имен, удалите их, выбирая каждый из них и нажимая клавишу **DELETE**.</span><span class="sxs-lookup"><span data-stu-id="e2928-196">If there are any other nameservers listed, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span>
    
    ![Нетворксолутионс — BP — redelegate — 1-5](../../media/eeb8ad22-bf4a-43a8-b97a-f09c3654d89b.png)
  
2. <span data-ttu-id="e2928-198">Выберите **добавить дополнительные серверы имен**.</span><span class="sxs-lookup"><span data-stu-id="e2928-198">Select **Add More Name Servers**.</span></span>
    
    ![Нетворксолутионсбп — redelegate — 1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
3. <span data-ttu-id="e2928-200">На странице **Domain Names** (Доменные имена) введите (или скопируйте и вставьте) значения серверов из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="e2928-200">On the **Domain Names** page, type or copy and paste the nameserver values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="e2928-201">**Name Server 1** (Сервер доменных имен 1)</span><span class="sxs-lookup"><span data-stu-id="e2928-201">**Name Server 1**</span></span> <br/> |<span data-ttu-id="e2928-202">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e2928-202">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="e2928-203">**Name Server 2** (Сервер доменных имен 2)</span><span class="sxs-lookup"><span data-stu-id="e2928-203">**Name Server 2**</span></span> <br/> |<span data-ttu-id="e2928-204">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e2928-204">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="e2928-205">**Name Server 3** (Сервер доменных имен 3)</span><span class="sxs-lookup"><span data-stu-id="e2928-205">**Name Server 3**</span></span> <br/> |<span data-ttu-id="e2928-206">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e2928-206">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="e2928-207">**Name Server 4** (Сервер доменных имен 4)</span><span class="sxs-lookup"><span data-stu-id="e2928-207">**Name Server 4**</span></span> <br/> |<span data-ttu-id="e2928-208">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e2928-208">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    
![Нетворксолутионсбп — redelegate — 1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
4. <span data-ttu-id="e2928-210">Нажмите кнопку **Move DNS (переместить DNS**).</span><span class="sxs-lookup"><span data-stu-id="e2928-210">Select **Move DNS**.</span></span>
    
    ![Нетворксолутионсбп — redelegate — 1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
5. <span data-ttu-id="e2928-212">Нажмите кнопку **сохранить изменения.**</span><span class="sxs-lookup"><span data-stu-id="e2928-212">Select **Save Changes.**</span></span>
    
    ![Нетворксолутионсбп — redelegate — 1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> <span data-ttu-id="e2928-214">На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="e2928-214">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="e2928-215">После этого ваша электронная почта Майкрософт и другие службы будут настроены для работы с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="e2928-215">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
