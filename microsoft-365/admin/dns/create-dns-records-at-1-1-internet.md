---
title: Создание записей DNS в 1&1 IONOS для Microsoft
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб в 1&1 IONOS для Microsoft.
ms.openlocfilehash: 123abd6d1d93f80eb73f187b7ff75ccd90d02980
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910562"
---
# <a name="create-dns-records-at-11-ionos-for-microsoft"></a><span data-ttu-id="0353c-103">Создание записей DNS в 1&1 IONOS для Microsoft</span><span class="sxs-lookup"><span data-stu-id="0353c-103">Create DNS records at 1&1 IONOS for Microsoft</span></span>

 <span data-ttu-id="0353c-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="0353c-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="0353c-105">Обратите внимание,&1 IONOS не позволяет домену иметь запись MX и запись CNAME с автоматическим открытием верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="0353c-105">Note that 1&1 IONOS doesn't allow a domain to have both an MX record and a top-level Autodiscover CNAME record.</span></span> <span data-ttu-id="0353c-106">Это ограничивает способы настройки Exchange Online для Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0353c-106">This limits the ways in which you can configure Exchange Online for Microsoft.</span></span> <span data-ttu-id="0353c-107">Существует обходное решение, но мы рекомендуем  использовать его только в том случае, если у вас уже есть опыт создания поддоменов в 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="0353c-107">There is a workaround, but we recommend employing it **only** if you already have experience with creating subdomains at 1&1 IONOS.</span></span> <span data-ttu-id="0353c-108">> Если, несмотря [](../setup/domains-faq.yml) на это ограничение службы, вы решите управлять собственными записями Microsoft DNS в 1&1 IONOS, выполните действия в этой статье, чтобы проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и так далее.</span><span class="sxs-lookup"><span data-stu-id="0353c-108">> If despite this [service limitation](../setup/domains-faq.yml) you choose to manage your own Microsoft DNS records at 1&1 IONOS, follow the steps in this article to verify your domain and to set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="0353c-109">После добавления этих записей в 1&1 IONOS домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0353c-109">After you add these records at 1&1 IONOS, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="0353c-p102">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0353c-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="0353c-113">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="0353c-113">Add a TXT record for verification</span></span>

<span data-ttu-id="0353c-p103">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="0353c-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0353c-p104">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="0353c-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="0353c-118">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 0:42)]().</span><span class="sxs-lookup"><span data-stu-id="0353c-118">Follow the steps below or [watch the video (start at 0:42)]().</span></span>
  
1. <span data-ttu-id="0353c-119">Чтобы начать работу, перейдите на страницу доменов в 1&1 IONOS с помощью [этой ссылки.](https://my.1and1.com/)</span><span class="sxs-lookup"><span data-stu-id="0353c-119">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="0353c-120">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="0353c-120">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="0353c-121">Выберите **Управление доменами.**</span><span class="sxs-lookup"><span data-stu-id="0353c-121">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="0353c-122">На странице **Центр домена** найдите домен, который необходимо обновить, а затем выберите панель **управления** **(v)** для этого домена.</span><span class="sxs-lookup"><span data-stu-id="0353c-122">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="0353c-123">В области **Параметры домена** выберите **Изменить параметры DNS.**</span><span class="sxs-lookup"><span data-stu-id="0353c-123">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="0353c-124">В разделе **TXT и SRV Records** выберите **Добавить запись.**</span><span class="sxs-lookup"><span data-stu-id="0353c-124">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="0353c-125">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="0353c-125">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0353c-126">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="0353c-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="0353c-127">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="0353c-127">**Type**</span></span> <br/> |<span data-ttu-id="0353c-128">**Prefix (Префикс)**</span><span class="sxs-lookup"><span data-stu-id="0353c-128">**Prefix**</span></span> <br/> |<span data-ttu-id="0353c-129">**Name Value (Значение имени)**</span><span class="sxs-lookup"><span data-stu-id="0353c-129">**Name Value**</span></span> <br/> |
    |<span data-ttu-id="0353c-130">TXT</span><span class="sxs-lookup"><span data-stu-id="0353c-130">TXT</span></span>  <br/> |<span data-ttu-id="0353c-131">(Оставьте это поле пустым)</span><span class="sxs-lookup"><span data-stu-id="0353c-131">(Leave this field blank)</span></span>  <br/> |<span data-ttu-id="0353c-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="0353c-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="0353c-133">ПРИМЕЧАНИЕ. Это пример.</span><span class="sxs-lookup"><span data-stu-id="0353c-133">NOTE: This is an example.</span></span> <span data-ttu-id="0353c-134">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="0353c-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="0353c-135">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="0353c-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="0353c-136">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0353c-136">Select **Save**.</span></span>
    
8. <span data-ttu-id="0353c-137">Выберите **Сохранить** снова.</span><span class="sxs-lookup"><span data-stu-id="0353c-137">Select **Save** again.</span></span> 
    
9. <span data-ttu-id="0353c-138">В **диалоговом окне Изменить параметры DNS** выберите **Да**.</span><span class="sxs-lookup"><span data-stu-id="0353c-138">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="0353c-139">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="0353c-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="0353c-140">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Microsoft 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="0353c-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="0353c-141">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="0353c-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="0353c-142">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="0353c-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="0353c-143">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="0353c-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="0353c-144">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="0353c-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="0353c-145">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="0353c-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0353c-p107">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0353c-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="0353c-149">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0353c-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="0353c-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="0353c-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="0353c-151">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 3:22)]().</span><span class="sxs-lookup"><span data-stu-id="0353c-151">Follow the steps below or [watch the video (start at 3:22)]().</span></span>
  
> [!NOTE]
> <span data-ttu-id="0353c-152">Если вы зарегистрировались в 1und1.de, [вопишите здесь](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="0353c-152">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="0353c-153">Чтобы начать работу, перейдите на страницу доменов в 1&1 IONOS с помощью [этой ссылки.](https://my.1and1.com/)</span><span class="sxs-lookup"><span data-stu-id="0353c-153">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="0353c-154">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="0353c-154">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="0353c-155">Выберите **Управление доменами.**</span><span class="sxs-lookup"><span data-stu-id="0353c-155">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="0353c-156">На странице **Центр домена** найдите домен, который необходимо обновить, а затем выберите панель **управления** **(v)** для этого домена.</span><span class="sxs-lookup"><span data-stu-id="0353c-156">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="0353c-157">В области **Параметры домена** выберите **Изменить параметры DNS.**</span><span class="sxs-lookup"><span data-stu-id="0353c-157">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="0353c-158">В разделе **MX Records** в области **Mail Exchanger (MX Record)** выберите **Другой почтовый сервер**.</span><span class="sxs-lookup"><span data-stu-id="0353c-158">In the **MX Records** section, in the **Mail Exchanger (MX Record)** area, select **Other mail server**.</span></span><br/><span data-ttu-id="0353c-159">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="0353c-159">(You may have to scroll down.)</span></span><br/><span data-ttu-id="0353c-160">![1 &amp; 1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span><span class="sxs-lookup"><span data-stu-id="0353c-160">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span></span> <br/>
  
6. <span data-ttu-id="0353c-161">Если уже указаны другие записи MX, удалите их, выбрав каждую из них и нажав клавишу **DELETE**.</span><span class="sxs-lookup"><span data-stu-id="0353c-161">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span></span><br/><span data-ttu-id="0353c-162">(Если записи MX не указаны, перейдите к следующему действию.)</span><span class="sxs-lookup"><span data-stu-id="0353c-162">(If there are no MX records already listed, continue to the next step.)</span></span><br/><span data-ttu-id="0353c-163">![1 &amp; 1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span><span class="sxs-lookup"><span data-stu-id="0353c-163">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span></span><br/>
  
7. <span data-ttu-id="0353c-164">В поля для записи **MX 1** введите (или скопируйте и вставьте) значения из приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="0353c-164">In the boxes for the **MX 1** record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="0353c-165">**MX 1**</span><span class="sxs-lookup"><span data-stu-id="0353c-165">**MX 1**</span></span>|<span data-ttu-id="0353c-166">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="0353c-166">**Priority**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="0353c-167">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="0353c-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <span data-ttu-id="0353c-168">ПРИМЕЧАНИЕ. Получите \<domain-key\> из учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0353c-168">NOTE: Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="0353c-169">Где это находится?</span><span class="sxs-lookup"><span data-stu-id="0353c-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="0353c-170">10 </span><span class="sxs-lookup"><span data-stu-id="0353c-170">10</span></span>  <br/> <span data-ttu-id="0353c-171">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](../setup/domains-faq.yml).   </span><span class="sxs-lookup"><span data-stu-id="0353c-171">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> | 
    
    ![1 и 1 — настройка 2 и 3](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. <span data-ttu-id="0353c-173">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0353c-173">Select **Save**.</span></span><br/><span data-ttu-id="0353c-174">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="0353c-174">(You may have to scroll down.)</span></span><br/><span data-ttu-id="0353c-175">![1 &amp; 1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span><span class="sxs-lookup"><span data-stu-id="0353c-175">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span></span>
  
9. <span data-ttu-id="0353c-176">В **диалоговом окне Изменить параметры DNS** выберите **Да**.</span><span class="sxs-lookup"><span data-stu-id="0353c-176">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="0353c-177">![Выбор да в диалоговом окне Изменить параметры DNS](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="0353c-177">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="0353c-178">Добавление шести записей CNAME, необходимых для Корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="0353c-178">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="0353c-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="0353c-179"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="0353c-180">1&1 IONOS требуется обходное решение, чтобы можно было использовать запись MX вместе с записями CNAME, которые необходимы для служб электронной почты Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0353c-180">1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records that are required for Microsoft email services.</span></span> <span data-ttu-id="0353c-181">Для этого необходимо создать набор поддоменов в 1&1 IONOS и назначить их записям CNAME.</span><span class="sxs-lookup"><span data-stu-id="0353c-181">This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0353c-182">Прежде чем начать эту процедуру, убедитесь в том, что доступно по крайней мере два поддомена.</span><span class="sxs-lookup"><span data-stu-id="0353c-182">Make sure that you have at least two available subdomains before starting this procedure.</span></span> <span data-ttu-id="0353c-183">Мы рекомендуем это решение, только если у вас уже есть опыт создания поддоменов в 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="0353c-183">We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.</span></span> 
  
### <a name="basic-cname-records"></a><span data-ttu-id="0353c-184">Основные записи CNAME</span><span class="sxs-lookup"><span data-stu-id="0353c-184">Basic CNAME records</span></span>

<span data-ttu-id="0353c-185">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 3:57)]().</span><span class="sxs-lookup"><span data-stu-id="0353c-185">Follow the steps below or [watch the video (start at 3:57)]().</span></span>
  
> [!NOTE]
> <span data-ttu-id="0353c-186">Если вы зарегистрировались в 1und1.de, [вопишите здесь](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="0353c-186">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="0353c-187">Чтобы начать работу, перейдите на страницу доменов в 1&1 IONOS с помощью [этой ссылки.](https://my.1and1.com/)</span><span class="sxs-lookup"><span data-stu-id="0353c-187">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="0353c-188">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="0353c-188">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="0353c-189">Выберите **Управление доменами.**</span><span class="sxs-lookup"><span data-stu-id="0353c-189">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="0353c-190">На странице **Центр домена** найдите домен, который необходимо обновить, а затем выберите **Управление поддоменами.**</span><span class="sxs-lookup"><span data-stu-id="0353c-190">On the **Domain Center** page, find the domain that you want to update, and then select **Manage Subdomains**.</span></span><br/><span data-ttu-id="0353c-191">![1 &amp; 1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span><span class="sxs-lookup"><span data-stu-id="0353c-191">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span></span> <br/><span data-ttu-id="0353c-192">Теперь нужно создать два поддомена и задать для каждого из них значение **Alias** (Псевдоним).</span><span class="sxs-lookup"><span data-stu-id="0353c-192">Now you'll create two subdomains and set an **Alias** value for each.</span></span><br/><span data-ttu-id="0353c-193">(Это необходимо, так как 1&1 IONOS поддерживает только одну запись CNAME верхнего уровня, но Microsoft требует несколько записей CNAME.)</span><span class="sxs-lookup"><span data-stu-id="0353c-193">(This is required because 1&1 IONOS supports only one top-level CNAME record, but Microsoft requires several CNAME records.)</span></span><br/><span data-ttu-id="0353c-194">Сначала необходимо создать поддомен автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="0353c-194">First, you'll create the Autodiscover subdomain.</span></span>
    
4. <span data-ttu-id="0353c-195">В разделе **Обзор subdomain** выберите **Создать Subdomain**.</span><span class="sxs-lookup"><span data-stu-id="0353c-195">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. <span data-ttu-id="0353c-p113">В поле **Create Subdomain** (Создать поддомен) для нового поддомена введите или скопируйте и вставьте только значение **Create Subdomain** из приведенной ниже таблицы. (Вы добавите значение **Alias** (Псевдоним) на следующем шаге.)</span><span class="sxs-lookup"><span data-stu-id="0353c-p113">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span>

    |<span data-ttu-id="0353c-199">**Create Subdomain (Создать поддомен)**</span><span class="sxs-lookup"><span data-stu-id="0353c-199">**Create Subdomain**</span></span>|<span data-ttu-id="0353c-200">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="0353c-200">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="0353c-201">autodiscover</span><span class="sxs-lookup"><span data-stu-id="0353c-201">autodiscover</span></span>  <br/> |<span data-ttu-id="0353c-202">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="0353c-202">autodiscover.outlook.com</span></span>   | 

    ![1 &amp; 1-BP-Configure-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. <span data-ttu-id="0353c-204">Выберите **Создать Subdomain**.</span><span class="sxs-lookup"><span data-stu-id="0353c-204">Select **Create Subdomain**.</span></span><br/><span data-ttu-id="0353c-205">![1 &amp; 1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span><span class="sxs-lookup"><span data-stu-id="0353c-205">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span></span>
  
7. <span data-ttu-id="0353c-206">В разделе **Обзор subdomain**  найдите только что созданный поддомен автообнаружания, а затем выберите контроль **Панели (v)** для этого поддомена.</span><span class="sxs-lookup"><span data-stu-id="0353c-206">In the **Subdomain Overview** section, locate the **autodiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="0353c-207">![1 &amp; 1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span><span class="sxs-lookup"><span data-stu-id="0353c-207">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span></span>
  
8. <span data-ttu-id="0353c-208">В области **Параметры subdomain** выберите **Изменить параметры DNS.**</span><span class="sxs-lookup"><span data-stu-id="0353c-208">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span> <br/><span data-ttu-id="0353c-209">![1 &amp; 1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span><span class="sxs-lookup"><span data-stu-id="0353c-209">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span></span>
  
9. <span data-ttu-id="0353c-210">В разделе **A/AAAA Records (IP-адреса)** в области **IP-адрес (Запись)** выберите **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="0353c-210">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span><br/><span data-ttu-id="0353c-211">![1 &amp; 1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span><span class="sxs-lookup"><span data-stu-id="0353c-211">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span></span>
  
10. <span data-ttu-id="0353c-212">В поле **Alias** (Псевдоним) введите (или скопируйте и вставьте) значение **Alias** из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="0353c-212">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span><br/> 
    
    |<span data-ttu-id="0353c-213">**Create Subdomain (Создать поддомен)**</span><span class="sxs-lookup"><span data-stu-id="0353c-213">**Create Subdomain**</span></span>|<span data-ttu-id="0353c-214">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="0353c-214">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="0353c-215">autodiscover</span><span class="sxs-lookup"><span data-stu-id="0353c-215">autodiscover</span></span>  <br/> |<span data-ttu-id="0353c-216">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="0353c-216">autodiscover.outlook.com</span></span>   |

    ![1 &amp; 1-BP-Configure-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. <span data-ttu-id="0353c-218">Установите флажок в отказе от ответственности **I am aware** (Я понимаю).</span><span class="sxs-lookup"><span data-stu-id="0353c-218">Select the check box for the **I am aware** disclaimer.</span></span><br/><span data-ttu-id="0353c-219">![1 &amp; 1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span><span class="sxs-lookup"><span data-stu-id="0353c-219">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span></span>
  
12. <span data-ttu-id="0353c-220">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0353c-220">Select **Save**.</span></span><br/><span data-ttu-id="0353c-221">![1 &amp; 1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span><span class="sxs-lookup"><span data-stu-id="0353c-221">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span></span>
  
  
### <a name="additional-cname-records"></a><span data-ttu-id="0353c-222">Дополнительные записи CNAME</span><span class="sxs-lookup"><span data-stu-id="0353c-222">Additional CNAME records</span></span>

<span data-ttu-id="0353c-p114">Дополнительные записи CNAME, которые создаются с помощью этой процедуры, обеспечивают работу служб Skype для бизнеса online. Вы выполните те же действия, которые использовались для создания двух записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="0353c-p114">The additional CNAME records created in the following procedure enable Skype for Business Online services. You will employ the same steps that you used to create the two CNAME records you have already created.</span></span>
  
1. <span data-ttu-id="0353c-225">Создайте третий поддомен (Lyncdiscover).</span><span class="sxs-lookup"><span data-stu-id="0353c-225">Create the third subdomain (Lyncdiscover).</span></span><br/><span data-ttu-id="0353c-226">В разделе **Обзор subdomain выберите** **Create Subdomain**.</span><span class="sxs-lookup"><span data-stu-id="0353c-226">On the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
2. <span data-ttu-id="0353c-p115">В поле **Create Subdomain** (Создать поддомен) для нового поддомена введите или скопируйте и вставьте только значение **Create Subdomain** из приведенной ниже таблицы. (Вы добавите значение **Alias** (Псевдоним) на следующем шаге.)</span><span class="sxs-lookup"><span data-stu-id="0353c-p115">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span><br/> 
    
    |<span data-ttu-id="0353c-229">**Create Subdomain (Создать поддомен)**</span><span class="sxs-lookup"><span data-stu-id="0353c-229">**Create Subdomain**</span></span>|<span data-ttu-id="0353c-230">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="0353c-230">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="0353c-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="0353c-231">lyncdiscover</span></span>   |<span data-ttu-id="0353c-232">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0353c-232">webdir.online.lync.com</span></span>  |
   
3. <span data-ttu-id="0353c-233">Выберите **Создать Subdomain**.</span><span class="sxs-lookup"><span data-stu-id="0353c-233">Select **Create Subdomain**.</span></span>
    
4. <span data-ttu-id="0353c-234">На странице **Центр домена** выберите **Управление поддоменами.**</span><span class="sxs-lookup"><span data-stu-id="0353c-234">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
5. <span data-ttu-id="0353c-235">В разделе **Обзор subdomain** найдите только что созданный поддомаин **lyncdiscover,** а затем выберите для этого поддомена управление **Панель (v).**</span><span class="sxs-lookup"><span data-stu-id="0353c-235">In the **Subdomain Overview** section, find the **lyncdiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="0353c-236">В области **Параметры subdomain** выберите **Изменить параметры DNS.**</span><span class="sxs-lookup"><span data-stu-id="0353c-236">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
6. <span data-ttu-id="0353c-237">В разделе **A/AAAA Records (IP-адреса)** в области **IP-адрес (Запись)** выберите **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="0353c-237">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
7. <span data-ttu-id="0353c-238">В поле **Alias** (Псевдоним) введите (или скопируйте и вставьте) значение **Alias** из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="0353c-238">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> <br/>
    
    |<span data-ttu-id="0353c-239">**Create Subdomain (Создать поддомен)**</span><span class="sxs-lookup"><span data-stu-id="0353c-239">**Create Subdomain**</span></span>|<span data-ttu-id="0353c-240">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="0353c-240">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="0353c-241">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="0353c-241">lyncdiscover</span></span>  <br/> |<span data-ttu-id="0353c-242">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0353c-242">webdir.online.lync.com</span></span>  <br/> |
   
8. <span data-ttu-id="0353c-243">Выберите контрольный ящик для **обязвеца I am aware,** а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0353c-243">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
9. <span data-ttu-id="0353c-244">В **диалоговом окне Изменить параметры DNS** выберите **Да**.</span><span class="sxs-lookup"><span data-stu-id="0353c-244">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="0353c-245">Создание четвертого поддомена (SIP)</span><span class="sxs-lookup"><span data-stu-id="0353c-245">Create the fourth subdomain (SIP):</span></span> <br/><span data-ttu-id="0353c-246">В разделе **Обзор subdomain** выберите **Создать Subdomain**.</span><span class="sxs-lookup"><span data-stu-id="0353c-246">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
11. <span data-ttu-id="0353c-p116">В поле **Create Subdomain** (Создать поддомен) для нового поддомена введите или скопируйте и вставьте только значение **Create Subdomain** из приведенной ниже таблицы. (Вы добавите значение **Alias** (Псевдоним) на следующем шаге.)</span><span class="sxs-lookup"><span data-stu-id="0353c-p116">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.) </span></span><br/>
    
    |<span data-ttu-id="0353c-249">**Create Subdomain (Создать поддомен)**</span><span class="sxs-lookup"><span data-stu-id="0353c-249">**Create Subdomain**</span></span>|<span data-ttu-id="0353c-250">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="0353c-250">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="0353c-251">sip</span><span class="sxs-lookup"><span data-stu-id="0353c-251">sip</span></span>  <br/> |<span data-ttu-id="0353c-252">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0353c-252">sipdir.online.lync.com</span></span>  <br/> |
   
12. <span data-ttu-id="0353c-253">Выберите **Создать Subdomain**.</span><span class="sxs-lookup"><span data-stu-id="0353c-253">Select **Create Subdomain**.</span></span>
    
13. <span data-ttu-id="0353c-254">На странице **Центр домена** выберите **Управление поддоменами.**</span><span class="sxs-lookup"><span data-stu-id="0353c-254">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
14. <span data-ttu-id="0353c-255">В разделе **Обзор subdomain** найдите поддомаин **sip,** который вы только что создали, а затем выберите управление **Панель (v)** для этого поддомена.</span><span class="sxs-lookup"><span data-stu-id="0353c-255">In the **Subdomain Overview** section, find the **sip** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="0353c-256">В области **Параметры subdomain** выберите **Изменить параметры DNS.**</span><span class="sxs-lookup"><span data-stu-id="0353c-256">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
15. <span data-ttu-id="0353c-257">В разделе **A/AAAA Records (IP-адреса)** в области **IP-адрес (Запись)** выберите **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="0353c-257">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
16. <span data-ttu-id="0353c-258">В поле **Alias** (Псевдоним) введите (или скопируйте и вставьте) значение **Alias** из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="0353c-258">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> 
    
    |<span data-ttu-id="0353c-259">**Create Subdomain (Создать поддомен)**</span><span class="sxs-lookup"><span data-stu-id="0353c-259">**Create Subdomain**</span></span>|<span data-ttu-id="0353c-260">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="0353c-260">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="0353c-261">sip</span><span class="sxs-lookup"><span data-stu-id="0353c-261">sip</span></span>  <br/> |<span data-ttu-id="0353c-262">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0353c-262">sipdir.online.lync.com</span></span>  <br/> |
   
17. <span data-ttu-id="0353c-263">Выберите контрольный ящик для **обязвеца I am aware,** а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0353c-263">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
18. <span data-ttu-id="0353c-264">В **диалоговом окне Изменить параметры DNS** выберите **Да**.</span><span class="sxs-lookup"><span data-stu-id="0353c-264">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
### <a name="cname-records-needed-for-mdm"></a><span data-ttu-id="0353c-265">Записи CNAME, необходимые для MDM</span><span class="sxs-lookup"><span data-stu-id="0353c-265">CNAME records needed for MDM</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0353c-266">Повторите действия, которые вы совершали при добавлении предыдущих четырех записей CNAME, подставив значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="0353c-266">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> 
  
|<span data-ttu-id="0353c-267">**Create Subdomain (Создать поддомен)**</span><span class="sxs-lookup"><span data-stu-id="0353c-267">**Create Subdomain**</span></span>|<span data-ttu-id="0353c-268">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="0353c-268">**Alias**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0353c-269">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="0353c-269">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="0353c-270">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="0353c-270">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="0353c-271">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="0353c-271">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="0353c-272">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="0353c-272">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="0353c-273">Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама</span><span class="sxs-lookup"><span data-stu-id="0353c-273">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0353c-274">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="0353c-274">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="0353c-275">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="0353c-275">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="0353c-276">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0353c-276">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="0353c-277">Вместо этого добавьте необходимые значения Microsoft в текущую  запись, чтобы у вас была одна запись SPF, которая включает оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="0353c-277">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="0353c-278">Нужны примеры?</span><span class="sxs-lookup"><span data-stu-id="0353c-278">Need examples?</span></span> <span data-ttu-id="0353c-279">Ознакомьтесь с этими [записями системы внешних доменных имен для продуктов корпорации Майкрософт](../../enterprise/external-domain-name-system-records.md).</span><span class="sxs-lookup"><span data-stu-id="0353c-279">Check out these [External Domain Name System records for Microsoft](../../enterprise/external-domain-name-system-records.md).</span></span> <span data-ttu-id="0353c-280">Для проверки записи SPF можно использовать один из этих средств проверки[SPF.](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="0353c-280">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
<span data-ttu-id="0353c-281">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 5:09)]().</span><span class="sxs-lookup"><span data-stu-id="0353c-281">Follow the steps below or [watch the video (start at 5:09)]().</span></span>
  
> [!NOTE]
> <span data-ttu-id="0353c-282">Если вы зарегистрировались в 1und1.de, [вопишите здесь](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="0353c-282">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="0353c-283">Чтобы начать работу, перейдите на страницу доменов в 1&1 IONOS с помощью [этой ссылки.](https://my.1and1.com/)</span><span class="sxs-lookup"><span data-stu-id="0353c-283">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="0353c-284">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="0353c-284">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="0353c-285">Выберите **Управление доменами.**</span><span class="sxs-lookup"><span data-stu-id="0353c-285">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="0353c-286">На странице **Центр домена** найдите домен, который необходимо обновить, а затем выберите панель **управления** **(v)** для этого домена.</span><span class="sxs-lookup"><span data-stu-id="0353c-286">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** (**v**) control for that domain.</span></span>
    
4. <span data-ttu-id="0353c-287">В области **Параметры домена** выберите **Изменить параметры DNS.**</span><span class="sxs-lookup"><span data-stu-id="0353c-287">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="0353c-288">В разделе **TXT и SRV Records** выберите **Добавить запись.**</span><span class="sxs-lookup"><span data-stu-id="0353c-288">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="0353c-289">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="0353c-289">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="0353c-290">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="0353c-290">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> <br/><span data-ttu-id="0353c-291">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="0353c-291">(Choose the **Type** value from the drop-down list.)</span></span> <br/>
    
    |<span data-ttu-id="0353c-292">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="0353c-292">**Type**</span></span>|<span data-ttu-id="0353c-293">**Prefix (Префикс)**</span><span class="sxs-lookup"><span data-stu-id="0353c-293">**Prefix**</span></span>|<span data-ttu-id="0353c-294">**Name Value (Значение имени)**</span><span class="sxs-lookup"><span data-stu-id="0353c-294">**Name Value**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="0353c-295">TXT</span><span class="sxs-lookup"><span data-stu-id="0353c-295">TXT</span></span>  <br/> |<span data-ttu-id="0353c-296">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="0353c-296">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="0353c-297">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="0353c-297">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="0353c-298">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="0353c-298">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           | 
    
    ![Запись TXT](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. <span data-ttu-id="0353c-300">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0353c-300">Select **Save**.</span></span><br/><span data-ttu-id="0353c-301">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span><span class="sxs-lookup"><span data-stu-id="0353c-301">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span></span>
  
8. <span data-ttu-id="0353c-302">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0353c-302">Select **Save**.</span></span><br/><span data-ttu-id="0353c-303">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span><span class="sxs-lookup"><span data-stu-id="0353c-303">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span></span>
  
9. <span data-ttu-id="0353c-304">В **диалоговом окне Изменить параметры DNS** выберите **Да**.</span><span class="sxs-lookup"><span data-stu-id="0353c-304">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="0353c-305">![Выбор да в диалоговом окне Изменить параметры DNS](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="0353c-305">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="0353c-306">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="0353c-306">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="0353c-307">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 5:51)]().</span><span class="sxs-lookup"><span data-stu-id="0353c-307">Follow the steps below or [watch the video (start at 5:51)]().</span></span>
  
> [!NOTE]
> <span data-ttu-id="0353c-308">Если вы зарегистрировались в 1und1.de, [вопишите здесь](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="0353c-308">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="0353c-309">Чтобы начать работу, перейдите на страницу доменов в 1&1 IONOS с помощью [этой ссылки.](https://my.1and1.com/)</span><span class="sxs-lookup"><span data-stu-id="0353c-309">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="0353c-310">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="0353c-310">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="0353c-311">Выберите **Управление доменами.**</span><span class="sxs-lookup"><span data-stu-id="0353c-311">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="0353c-312">На странице **Центр домена** найдите домен, который необходимо обновить, а затем выберите панель **управления** **(v)** для этого домена.</span><span class="sxs-lookup"><span data-stu-id="0353c-312">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="0353c-313">В области **Параметры домена** выберите **Изменить параметры DNS.**</span><span class="sxs-lookup"><span data-stu-id="0353c-313">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="0353c-314">В разделе **TXT и SRV Records** выберите **Добавить запись.**</span><span class="sxs-lookup"><span data-stu-id="0353c-314">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="0353c-315">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="0353c-315">Add the first of the two SRV records.</span></span><br/><span data-ttu-id="0353c-316">В поля для новой записи в области **Add Record** (Добавление записи) введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="0353c-316">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> <br/><span data-ttu-id="0353c-317">(Выберите **значения Type** и **TTL** из выпадаемого списка.)</span><span class="sxs-lookup"><span data-stu-id="0353c-317">(Choose the **Type** and **TTL** values from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="0353c-318">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="0353c-318">**Type**</span></span>|<span data-ttu-id="0353c-319">**Service (Служба)**</span><span class="sxs-lookup"><span data-stu-id="0353c-319">**Service**</span></span>|<span data-ttu-id="0353c-320">**Protocol (Протокол)**</span><span class="sxs-lookup"><span data-stu-id="0353c-320">**Protocol**</span></span>|<span data-ttu-id="0353c-321">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="0353c-321">**Name**</span></span>|<span data-ttu-id="0353c-322">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="0353c-322">**Host**</span></span>|<span data-ttu-id="0353c-323">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="0353c-323">**Priority**</span></span>|<span data-ttu-id="0353c-324">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="0353c-324">**Weight**</span></span>|<span data-ttu-id="0353c-325">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="0353c-325">**Port**</span></span>|<span data-ttu-id="0353c-326">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="0353c-326">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0353c-327">SRV</span><span class="sxs-lookup"><span data-stu-id="0353c-327">SRV</span></span>  <br/> |<span data-ttu-id="0353c-328">sip</span><span class="sxs-lookup"><span data-stu-id="0353c-328">sip</span></span>  <br/> |<span data-ttu-id="0353c-329">tls</span><span class="sxs-lookup"><span data-stu-id="0353c-329">tls</span></span>  <br/> |<span data-ttu-id="0353c-330">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="0353c-330">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="0353c-331">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0353c-331">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="0353c-332">100</span><span class="sxs-lookup"><span data-stu-id="0353c-332">100</span></span>  <br/> |<span data-ttu-id="0353c-333">1</span><span class="sxs-lookup"><span data-stu-id="0353c-333">1</span></span>  <br/> |<span data-ttu-id="0353c-334">443</span><span class="sxs-lookup"><span data-stu-id="0353c-334">443</span></span>  <br/> |<span data-ttu-id="0353c-335">3600 (1 ч)</span><span class="sxs-lookup"><span data-stu-id="0353c-335">3600 (1 h)</span></span>  <br/> |
    |<span data-ttu-id="0353c-336">SRV</span><span class="sxs-lookup"><span data-stu-id="0353c-336">SRV</span></span>  <br/> |<span data-ttu-id="0353c-337">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="0353c-337">sipfederationtls</span></span>  <br/> |<span data-ttu-id="0353c-338">tcp</span><span class="sxs-lookup"><span data-stu-id="0353c-338">tcp</span></span>  <br/> |<span data-ttu-id="0353c-339">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="0353c-339">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="0353c-340">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0353c-340">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="0353c-341">100</span><span class="sxs-lookup"><span data-stu-id="0353c-341">100</span></span>  <br/> |<span data-ttu-id="0353c-342">1</span><span class="sxs-lookup"><span data-stu-id="0353c-342">1</span></span>  <br/> |<span data-ttu-id="0353c-343">5061</span><span class="sxs-lookup"><span data-stu-id="0353c-343">5061</span></span>  <br/> |<span data-ttu-id="0353c-344">3600 (1 ч)</span><span class="sxs-lookup"><span data-stu-id="0353c-344">3600 (1 h)</span></span>  <br/> |  
    
    ![1 &amp; 1-BP-Configure-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. <span data-ttu-id="0353c-346">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0353c-346">Select **Save**.</span></span> <br/><span data-ttu-id="0353c-347">![1 &amp; 1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span><span class="sxs-lookup"><span data-stu-id="0353c-347">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span></span>
  
8. <span data-ttu-id="0353c-348">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0353c-348">Select **Save**.</span></span> <br/><span data-ttu-id="0353c-349">![1 &amp; 1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span><span class="sxs-lookup"><span data-stu-id="0353c-349">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span></span>
  
9. <span data-ttu-id="0353c-350">В **диалоговом окне Изменить параметры DNS** выберите **Да**.</span><span class="sxs-lookup"><span data-stu-id="0353c-350">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span> <br/><span data-ttu-id="0353c-351">![Выбор да в диалоговом окне Изменить параметры DNS](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="0353c-351">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
10. <span data-ttu-id="0353c-352">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="0353c-352">Add the other SRV record.</span></span> <br/><span data-ttu-id="0353c-353">В разделе **TXT и SRV Records** выберите **Добавить запись.**</span><span class="sxs-lookup"><span data-stu-id="0353c-353">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="0353c-354">В области Добавить **запись** создайте запись с помощью значений из другой строки в таблице, а затем снова выберите **Добавить,** **Сохранить** и Да, чтобы завершить запись. </span><span class="sxs-lookup"><span data-stu-id="0353c-354">In the **Add Record** area, create a record using the values from the other row in the table, and then again select **Add**, **Save**, and **Yes** to complete the record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="0353c-p120">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0353c-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
