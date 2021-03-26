---
title: Создание записей DNS для Майкрософт на сайте Google Domains
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Узнайте, как проверить свой домен и настроить записи DNS для электронной почты, Lync и других служб корпорации Майкрософт на сайте Google Domains.
ms.openlocfilehash: 48e23c180533bab2a73e06dd4a45a9c4016680ae
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2021
ms.locfileid: "51221959"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a><span data-ttu-id="adc52-103">Создание записей DNS для Майкрософт на сайте Google Domains</span><span class="sxs-lookup"><span data-stu-id="adc52-103">Create DNS records at Google Domains for Microsoft</span></span>

 <span data-ttu-id="adc52-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="adc52-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="adc52-105">Если ваш поставщик услуг размещения DNS — Google Domains, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Lync и других служб.</span><span class="sxs-lookup"><span data-stu-id="adc52-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="adc52-106">Когда вы добавите эти записи на сайте Google Domains, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="adc52-106">After you add these records at Google Domains, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="adc52-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="adc52-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="adc52-108">Тем не менее, иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени.</span><span class="sxs-lookup"><span data-stu-id="adc52-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="adc52-109">Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение неполадок после добавления в Майкрософт домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="adc52-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="adc52-110">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="adc52-110">Add a TXT record for verification</span></span>
<span data-ttu-id="adc52-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="adc52-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="adc52-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="adc52-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="adc52-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="adc52-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="adc52-p104">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Google Domains по [этой ссылке](https://domains.google.com/registrar). Сначала вам потребуется войти. Вот как это сделать.</span><span class="sxs-lookup"><span data-stu-id="adc52-p104">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="adc52-119">Нажмите **Sign In** (Войти).</span><span class="sxs-lookup"><span data-stu-id="adc52-119">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="adc52-120">Введите данные для входа и еще раз нажмите кнопку **Sign In** (Войти).</span><span class="sxs-lookup"><span data-stu-id="adc52-120">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="adc52-121">На странице **My domains** (Мои домены) выберите домен, который вы хотите использовать в Майкрософт, и щелкните ссылку **MANAGE** (УПРАВЛЕНИЕ) рядом с ним.</span><span class="sxs-lookup"><span data-stu-id="adc52-121">On the **My domains** page, find the domain you want to use with Microsoft, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="adc52-122">В области навигации слева выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="adc52-122">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="adc52-123">В разделе **Custom resource records** (Настраиваемые записи ресурсов) в полях для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="adc52-123">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="adc52-124">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="adc52-124">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="adc52-125">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="adc52-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="adc52-126">**Имя**</span><span class="sxs-lookup"><span data-stu-id="adc52-126">**Name**</span></span> <br/> |<span data-ttu-id="adc52-127">**Type** (Тип)</span><span class="sxs-lookup"><span data-stu-id="adc52-127">**Type**</span></span> <br/> |<span data-ttu-id="adc52-128">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="adc52-128">**TTL**</span></span> <br/> |<span data-ttu-id="adc52-129">**Data** (Данные)</span><span class="sxs-lookup"><span data-stu-id="adc52-129">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="adc52-130">TXT</span><span class="sxs-lookup"><span data-stu-id="adc52-130">TXT</span></span>  <br/> |<span data-ttu-id="adc52-131">1H (1 ч)</span><span class="sxs-lookup"><span data-stu-id="adc52-131">1H</span></span>  <br/> |<span data-ttu-id="adc52-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="adc52-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="adc52-133">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="adc52-133">**Note:** This is an example.</span></span> <span data-ttu-id="adc52-134">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="adc52-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="adc52-135">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="adc52-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="adc52-136">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="adc52-136">Select **Add**.</span></span>
    
5. <span data-ttu-id="adc52-137">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="adc52-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="adc52-138">Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.</span><span class="sxs-lookup"><span data-stu-id="adc52-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="adc52-139">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="adc52-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="adc52-140">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="adc52-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="adc52-141">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="adc52-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="adc52-142">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="adc52-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="adc52-143">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="adc52-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="adc52-p107">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="adc52-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="adc52-147">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="adc52-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="adc52-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="adc52-148"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="adc52-p108">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Google Domains по [этой ссылке](https://domains.google.com/registrar). Сначала вам потребуется войти. Вот как это сделать.</span><span class="sxs-lookup"><span data-stu-id="adc52-p108">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="adc52-152">Нажмите **Sign In** (Войти).</span><span class="sxs-lookup"><span data-stu-id="adc52-152">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="adc52-153">Введите данные для входа и еще раз нажмите кнопку **Sign In** (Войти).</span><span class="sxs-lookup"><span data-stu-id="adc52-153">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="adc52-154">На странице **Domains** (Домены) в разделе **Domain** (Домен) выберите команду **Configure DNS** (Настроить DNS) для того домена, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="adc52-154">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="adc52-155">Если вы используете учетную запись электронной почты G Suite, сначала необходимо удалить записи MX, которые с ней связаны.</span><span class="sxs-lookup"><span data-stu-id="adc52-155">If you have a G Suite email account, you must first delete the MX records associated with that account.</span></span> <span data-ttu-id="adc52-156">Существующие записи MX для G Suite препятствуют добавлению каких-либо других записей MX, включая те, которые требуются для использования служб Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="adc52-156">The G Suite MX records prevent you from adding any other MX records, including those required for Microsoft.</span></span> <span data-ttu-id="adc52-157">Обратите внимание, что при удалении записей для G Suite учетная запись G Suite не удаляется.</span><span class="sxs-lookup"><span data-stu-id="adc52-157">Note that deleting the G Suite records does not delete your G Suite account.</span></span> <span data-ttu-id="adc52-158">Чтобы удалить записи MX для G Suite, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="adc52-158">To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="adc52-159">В разделе **Synthetic records** (Синтетические записи) в области **G Suite** нажмите кнопку **Delete** (Удалить).</span><span class="sxs-lookup"><span data-stu-id="adc52-159">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="adc52-160">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="adc52-160">(You may have to scroll down.)</span></span>
    
    ![Нажатие кнопки Delete (Удалить) в разделе Synthetic records (Синтетические записи)](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="adc52-162">Выберите **Delete** (Удалить).</span><span class="sxs-lookup"><span data-stu-id="adc52-162">Select **Delete**.</span></span>
    
    ![Выберите Delete (Удалить)](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="adc52-164">В разделе **Custom resource records** (Настраиваемые записи ресурсов) в полях для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="adc52-164">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="adc52-165">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="adc52-165">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="adc52-166">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="adc52-166">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="adc52-167">**Имя**</span><span class="sxs-lookup"><span data-stu-id="adc52-167">**Name**</span></span>|<span data-ttu-id="adc52-168">**Type** (Тип)</span><span class="sxs-lookup"><span data-stu-id="adc52-168">**Type**</span></span>|<span data-ttu-id="adc52-169">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="adc52-169">**TTL**</span></span>|<span data-ttu-id="adc52-170">**Data** (Данные)</span><span class="sxs-lookup"><span data-stu-id="adc52-170">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="adc52-171">MX</span><span class="sxs-lookup"><span data-stu-id="adc52-171">MX</span></span>  <br/> |<span data-ttu-id="adc52-172">1H (1 ч)</span><span class="sxs-lookup"><span data-stu-id="adc52-172">1H</span></span>  <br/> |<span data-ttu-id="adc52-173">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="adc52-173">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="adc52-174">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="adc52-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="adc52-p110">**0** — значение приоритета MX. Добавьте его в начало значения MX, отделив от остальной части пробелом.  </span><span class="sxs-lookup"><span data-stu-id="adc52-p110">The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="adc52-177">**Примечание.**  Получите свой \<*domain-key*\> из учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="adc52-177">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span>  [<span data-ttu-id="adc52-178">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="adc52-178">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="adc52-179">Дополнительные сведения о приоритете см. в статье [Что такое приоритет записей MX?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="adc52-179">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |
   
    ![Введите или вставьте значения в разделе Custom resource records (Настраиваемые записи ресурсов)](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="adc52-181">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="adc52-181">Select **Add**.</span></span>
    
    ![Нажмите кнопку Add (Добавить)](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="adc52-183">Если есть другие настраиваемые записи MX, удалите их.</span><span class="sxs-lookup"><span data-stu-id="adc52-183">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="adc52-184">В строке записи MX нажмите **Edit** (Изменить).</span><span class="sxs-lookup"><span data-stu-id="adc52-184">Select **Edit** in the MX record row.</span></span> 
    
    ![В строке записи MX нажмите Edit (Изменить)](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="adc52-186">Для каждой из прочих настраиваемых записей MX выделите содержимое поля **Data** (Данные) и нажмите на клавиатуре клавишу **DELETE**, чтобы удалить его.</span><span class="sxs-lookup"><span data-stu-id="adc52-186">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="adc52-187">Повторяйте эти действия, чтобы удалить содержимое поля **Data** каждой из лишних записей MX.</span><span class="sxs-lookup"><span data-stu-id="adc52-187">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="adc52-189">Когда содержимое поля **Data** (Данные) каждой записи MX будет удалено, нажмите кнопку **Save** (Сохранить), чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="adc52-189">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![Нажмите Save (Сохранить)](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="adc52-191">Добавление пяти записей CNAME, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="adc52-191">Add the five CNAME records that are required for Microsoft</span></span>

1. <span data-ttu-id="adc52-192">Чтобы приступить к работе, перейдите на страницу [страница Google Domains] (https://domains.google.com/registrar) и выполните вход.</span><span class="sxs-lookup"><span data-stu-id="adc52-192">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="adc52-193">На странице **Domains** (Домены) в разделе **Domain** (Домен) выберите команду **Configure DNS** (Настроить DNS) для того домена, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="adc52-193">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="adc52-194">Добавьте первую запись CNAME.</span><span class="sxs-lookup"><span data-stu-id="adc52-194">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="adc52-195">В разделе **Custom resource records** (Настраиваемые записи ресурсов) в полях для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="adc52-195">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="adc52-196">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="adc52-196">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="adc52-197">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="adc52-197">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="adc52-198">**Имя**</span><span class="sxs-lookup"><span data-stu-id="adc52-198">**Name**</span></span>|<span data-ttu-id="adc52-199">**Type** (Тип)</span><span class="sxs-lookup"><span data-stu-id="adc52-199">**Type**</span></span>|<span data-ttu-id="adc52-200">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="adc52-200">**TTL**</span></span>|<span data-ttu-id="adc52-201">**Data** (Данные)</span><span class="sxs-lookup"><span data-stu-id="adc52-201">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="adc52-202">autodiscover</span><span class="sxs-lookup"><span data-stu-id="adc52-202">autodiscover</span></span>  <br/> |<span data-ttu-id="adc52-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="adc52-203">CNAME</span></span>  <br/> |<span data-ttu-id="adc52-204">1H (1 ч)</span><span class="sxs-lookup"><span data-stu-id="adc52-204">1H</span></span>  <br/> |<span data-ttu-id="adc52-205">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="adc52-205">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="adc52-206">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="adc52-206">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="adc52-207">sip</span><span class="sxs-lookup"><span data-stu-id="adc52-207">sip</span></span>  <br/> |<span data-ttu-id="adc52-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="adc52-208">CNAME</span></span>  <br/> |<span data-ttu-id="adc52-209">1H (1 ч)</span><span class="sxs-lookup"><span data-stu-id="adc52-209">1H</span></span>  <br/> |<span data-ttu-id="adc52-210">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="adc52-210">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="adc52-211">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="adc52-211">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="adc52-212">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="adc52-212">lyncdiscover</span></span>  <br/> |<span data-ttu-id="adc52-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="adc52-213">CNAME</span></span>  <br/> |<span data-ttu-id="adc52-214">1H (1 ч)</span><span class="sxs-lookup"><span data-stu-id="adc52-214">1H</span></span>  <br/> |<span data-ttu-id="adc52-215">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="adc52-215">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="adc52-216">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="adc52-216">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="adc52-217">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="adc52-217">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="adc52-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="adc52-218">CNAME</span></span>  <br/> |<span data-ttu-id="adc52-219">1H (1 ч)</span><span class="sxs-lookup"><span data-stu-id="adc52-219">1H</span></span>  <br/> |<span data-ttu-id="adc52-220">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="adc52-220">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="adc52-221">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="adc52-221">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="adc52-222">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="adc52-222">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="adc52-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="adc52-223">CNAME</span></span>  <br/> |<span data-ttu-id="adc52-224">1H (1 ч)</span><span class="sxs-lookup"><span data-stu-id="adc52-224">1H</span></span>  <br/> |<span data-ttu-id="adc52-225">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="adc52-225">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="adc52-226">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="adc52-226">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Введите или вставьте значения в разделе Custom resource records (Настраиваемые записи ресурсов)](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="adc52-228">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="adc52-228">Select **Add**.</span></span>
    
    ![Нажмите кнопку Add (Добавить)](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="adc52-230">Добавьте остальные четыре записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="adc52-230">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="adc52-231">В разделе **Custom resource records** (Настраиваемые записи ресурсов) создайте запись, используя значения из следующей строки таблицы, и снова нажмите **Add** (Добавить), чтобы завершить ввод этой записи.</span><span class="sxs-lookup"><span data-stu-id="adc52-231">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="adc52-232">Повторяйте эти действия, пока не будут созданы все требуемые записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="adc52-232">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="adc52-233">Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама</span><span class="sxs-lookup"><span data-stu-id="adc52-233">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="adc52-234">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="adc52-234">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="adc52-235">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="adc52-235">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="adc52-236">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="adc52-236">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="adc52-237">Вместо этого добавьте необходимые значения для продуктов корпорации Майкрософт в текущую запись. Таким образом, в одной записи SPF будут указаны оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="adc52-237">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="adc52-238">Нужны примеры?</span><span class="sxs-lookup"><span data-stu-id="adc52-238">Need examples?</span></span> <span data-ttu-id="adc52-239">Ознакомьтесь с этими [записями системы внешних доменных имен для продуктов корпорации Майкрософт](../../enterprise/external-domain-name-system-records.md).</span><span class="sxs-lookup"><span data-stu-id="adc52-239">Check out these [External Domain Name System records for Microsoft](../../enterprise/external-domain-name-system-records.md).</span></span> <span data-ttu-id="adc52-240">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="adc52-240">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="adc52-p113">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Google Domains по [этой ссылке](https://domains.google.com/registrar). Сначала вам потребуется войти. Вот как это сделать.</span><span class="sxs-lookup"><span data-stu-id="adc52-p113">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="adc52-244">Нажмите **Sign In** (Войти).</span><span class="sxs-lookup"><span data-stu-id="adc52-244">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="adc52-245">Введите данные для входа и еще раз нажмите кнопку **Sign In** (Войти).</span><span class="sxs-lookup"><span data-stu-id="adc52-245">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="adc52-246">На странице **Domains** (Домены) в разделе **Domain** (Домен) выберите команду **Configure DNS** (Настроить DNS) для того домена, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="adc52-246">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="adc52-247">В разделе **Custom resource records** (Настраиваемые записи ресурсов) в строке записи TXT нажмите кнопку **Edit** (Изменить).</span><span class="sxs-lookup"><span data-stu-id="adc52-247">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="adc52-p114">Google Domains хранит записи TXT в виде наборов, которые могут содержать сразу несколько записей. Если у вас есть хотя бы еще одна запись TXT, с помощью которой вы подтверждали домен, вам нужно добавлять новые записи TXT к ней. Попытка ввести дополнительные записи TXT отдельно приведет к ошибке **Duplicate record** (Повторяющаяся запись).</span><span class="sxs-lookup"><span data-stu-id="adc52-p114">Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![В строке записи TXT нажмите Edit (Изменить)](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="adc52-252">Щелкните элемент управления **(+)**.</span><span class="sxs-lookup"><span data-stu-id="adc52-252">Select the **(+)** control.</span></span> 
    
    ![Щелкните элемент управления "плюс"](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="adc52-254">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="adc52-254">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="adc52-255">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="adc52-255">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="adc52-256">**Данные**</span><span class="sxs-lookup"><span data-stu-id="adc52-256">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="adc52-257">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="adc52-257">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="adc52-258">Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.</span><span class="sxs-lookup"><span data-stu-id="adc52-258">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![Введите или вставьте значения в разделе Custom resource records (Настраиваемые записи ресурсов)](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="adc52-260">Нажмите **Save** (Сохранить).</span><span class="sxs-lookup"><span data-stu-id="adc52-260">Select **Save**.</span></span>
    
    ![Нажмите Save (Сохранить)](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="adc52-262">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="adc52-262">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="adc52-263"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="adc52-263"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="adc52-p115">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Google Domains по [этой ссылке](https://domains.google.com/registrar). Сначала вам потребуется войти. Вот как это сделать.</span><span class="sxs-lookup"><span data-stu-id="adc52-p115">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="adc52-267">Нажмите **Sign In** (Войти).</span><span class="sxs-lookup"><span data-stu-id="adc52-267">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="adc52-268">Введите данные для входа и еще раз нажмите кнопку **Sign In** (Войти).</span><span class="sxs-lookup"><span data-stu-id="adc52-268">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="adc52-269">На странице **Domains** (Домены) в разделе **Domain** (Домен) выберите команду **Configure DNS** (Настроить DNS) для того домена, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="adc52-269">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="adc52-270">Добавьте первую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="adc52-270">Add the first SRV record.</span></span>
    
    <span data-ttu-id="adc52-271">В разделе **Custom resource records** (Настраиваемые записи ресурсов) в полях для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="adc52-271">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="adc52-272">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="adc52-272">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="adc52-273">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="adc52-273">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="adc52-274">**Имя**</span><span class="sxs-lookup"><span data-stu-id="adc52-274">**Name**</span></span>|<span data-ttu-id="adc52-275">**Type** (Тип)</span><span class="sxs-lookup"><span data-stu-id="adc52-275">**Type**</span></span>|<span data-ttu-id="adc52-276">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="adc52-276">**TTL**</span></span>|<span data-ttu-id="adc52-277">**Данные**</span><span class="sxs-lookup"><span data-stu-id="adc52-277">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="adc52-278">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="adc52-278">_sip._tls</span></span>|<span data-ttu-id="adc52-279">SRV</span><span class="sxs-lookup"><span data-stu-id="adc52-279">SRV</span></span>|<span data-ttu-id="adc52-280">1H (1 ч)</span><span class="sxs-lookup"><span data-stu-id="adc52-280">1H</span></span>|<span data-ttu-id="adc52-281">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="adc52-281">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="adc52-282">**Это значение ДОЛЖНО оканчиваться точкой (.).** **Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.</span><span class="sxs-lookup"><span data-stu-id="adc52-282">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="adc52-283">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="adc52-283">_sipfederationtls._tcp</span></span>|<span data-ttu-id="adc52-284">SRV</span><span class="sxs-lookup"><span data-stu-id="adc52-284">SRV</span></span>|<span data-ttu-id="adc52-285">1H (1 ч)</span><span class="sxs-lookup"><span data-stu-id="adc52-285">1H</span></span>|<span data-ttu-id="adc52-286">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="adc52-286">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="adc52-287">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="adc52-287">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="adc52-288">Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.</span><span class="sxs-lookup"><span data-stu-id="adc52-288">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![Введите или вставьте значения в разделе Custom resource records (Настраиваемые записи ресурсов)](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="adc52-290">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="adc52-290">Select **Add**.</span></span>
    
    ![Нажмите кнопку Add (Добавить)](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="adc52-292">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="adc52-292">Add the other SRV record.</span></span>
    
    <span data-ttu-id="adc52-293">В разделе **Custom resource records** (Настраиваемые записи ресурсов) создайте запись, используя значения из второй строки таблицы, и снова нажмите **Add** (Добавить), чтобы завершить ввод этой записи.</span><span class="sxs-lookup"><span data-stu-id="adc52-293">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="adc52-p118">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="adc52-p118">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
