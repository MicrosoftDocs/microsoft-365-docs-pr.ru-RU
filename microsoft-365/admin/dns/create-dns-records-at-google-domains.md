---
title: Создание записей DNS для Майкрософт на сайте Google Domains
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Узнайте, как проверить свой домен и настроить записи DNS для электронной почты, Lync и других служб корпорации Майкрософт на сайте Google Domains.
ms.openlocfilehash: e6b1dd1eb90957a4e7fe22bd4b66ac87b2a51d09
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400453"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a><span data-ttu-id="302b3-103">Создание записей DNS для Майкрософт на сайте Google Domains</span><span class="sxs-lookup"><span data-stu-id="302b3-103">Create DNS records at Google Domains for Microsoft</span></span>

 <span data-ttu-id="302b3-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="302b3-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="302b3-105">Если ваш поставщик услуг размещения DNS — Google Domains, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Lync и других служб.</span><span class="sxs-lookup"><span data-stu-id="302b3-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="302b3-106">Когда вы добавите эти записи на сайте Google Domains, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="302b3-106">After you add these records at Google Domains, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="302b3-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="302b3-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="302b3-108">Тем не менее, иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени.</span><span class="sxs-lookup"><span data-stu-id="302b3-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="302b3-109">Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение неполадок после добавления в Майкрософт домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="302b3-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="302b3-110">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="302b3-110">Add a TXT record for verification</span></span>
<span data-ttu-id="302b3-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="302b3-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="302b3-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span><span class="sxs-lookup"><span data-stu-id="302b3-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="302b3-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span><span class="sxs-lookup"><span data-stu-id="302b3-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="302b3-114">This record is used only to verify that you own your domain; it doesn't affect anything else.</span><span class="sxs-lookup"><span data-stu-id="302b3-114">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> <span data-ttu-id="302b3-115">You can delete it later, if you like.</span><span class="sxs-lookup"><span data-stu-id="302b3-115">You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="302b3-116">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar).</span><span class="sxs-lookup"><span data-stu-id="302b3-116">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="302b3-117">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="302b3-117">You'll be prompted to sign in.</span></span> <span data-ttu-id="302b3-118">To do so:</span><span class="sxs-lookup"><span data-stu-id="302b3-118">To do so:</span></span>
    
1. <span data-ttu-id="302b3-119">Нажмите **Sign In** (Войти).</span><span class="sxs-lookup"><span data-stu-id="302b3-119">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="302b3-120">Введите данные для входа и еще раз нажмите кнопку **Sign In** (Войти).</span><span class="sxs-lookup"><span data-stu-id="302b3-120">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="302b3-121">На странице **My domains** (Мои домены) выберите домен, который вы хотите использовать в Майкрософт, и щелкните ссылку **MANAGE** (УПРАВЛЕНИЕ) рядом с ним.</span><span class="sxs-lookup"><span data-stu-id="302b3-121">On the **My domains** page, find the domain you want to use with Microsoft, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="302b3-122">В области навигации слева выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="302b3-122">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="302b3-123">В разделе **Custom resource records** (Настраиваемые записи ресурсов) в полях для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="302b3-123">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="302b3-124">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="302b3-124">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="302b3-125">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="302b3-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="302b3-126">**Имя**</span><span class="sxs-lookup"><span data-stu-id="302b3-126">**Name**</span></span> <br/> |<span data-ttu-id="302b3-127">**Type** (Тип)</span><span class="sxs-lookup"><span data-stu-id="302b3-127">**Type**</span></span> <br/> |<span data-ttu-id="302b3-128">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="302b3-128">**TTL**</span></span> <br/> |<span data-ttu-id="302b3-129">**Data** (Данные)</span><span class="sxs-lookup"><span data-stu-id="302b3-129">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="302b3-130">TXT</span><span class="sxs-lookup"><span data-stu-id="302b3-130">TXT</span></span>  <br/> |<span data-ttu-id="302b3-131">1H (1 ч)</span><span class="sxs-lookup"><span data-stu-id="302b3-131">1H</span></span>  <br/> |<span data-ttu-id="302b3-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="302b3-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="302b3-133">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="302b3-133">**Note:** This is an example.</span></span> <span data-ttu-id="302b3-134">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="302b3-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="302b3-135">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="302b3-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="302b3-136">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="302b3-136">Select **Add**.</span></span>
    
5. <span data-ttu-id="302b3-137">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="302b3-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="302b3-138">Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.</span><span class="sxs-lookup"><span data-stu-id="302b3-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="302b3-139">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="302b3-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="302b3-140">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="302b3-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="302b3-141">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="302b3-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="302b3-142">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="302b3-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="302b3-143">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="302b3-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="302b3-144">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="302b3-144">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="302b3-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="302b3-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="302b3-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="302b3-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="302b3-147">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="302b3-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="302b3-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="302b3-148"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="302b3-149">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar).</span><span class="sxs-lookup"><span data-stu-id="302b3-149">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="302b3-150">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="302b3-150">You'll be prompted to sign in.</span></span> <span data-ttu-id="302b3-151">To do so:</span><span class="sxs-lookup"><span data-stu-id="302b3-151">To do so:</span></span>
    
2. <span data-ttu-id="302b3-152">Нажмите **Sign In** (Войти).</span><span class="sxs-lookup"><span data-stu-id="302b3-152">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="302b3-153">Введите данные для входа и еще раз нажмите кнопку **Sign In** (Войти).</span><span class="sxs-lookup"><span data-stu-id="302b3-153">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="302b3-154">На странице **Domains** (Домены) в разделе **Domain** (Домен) выберите команду **Configure DNS** (Настроить DNS) для того домена, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="302b3-154">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="302b3-155">Если вы используете учетную запись электронной почты G Suite, сначала необходимо удалить записи MX, которые с ней связаны.</span><span class="sxs-lookup"><span data-stu-id="302b3-155">If you have a G Suite email account, you must first delete the MX records associated with that account.</span></span> <span data-ttu-id="302b3-156">Существующие записи MX для G Suite препятствуют добавлению каких-либо других записей MX, включая те, которые требуются для использования служб Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="302b3-156">The G Suite MX records prevent you from adding any other MX records, including those required for Microsoft.</span></span> <span data-ttu-id="302b3-157">Обратите внимание, что при удалении записей для G Suite учетная запись G Suite не удаляется.</span><span class="sxs-lookup"><span data-stu-id="302b3-157">Note that deleting the G Suite records does not delete your G Suite account.</span></span> <span data-ttu-id="302b3-158">Чтобы удалить записи MX для G Suite, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="302b3-158">To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="302b3-159">В разделе **Synthetic records** (Синтетические записи) в области **G Suite** нажмите кнопку **Delete** (Удалить).</span><span class="sxs-lookup"><span data-stu-id="302b3-159">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="302b3-160">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="302b3-160">(You may have to scroll down.)</span></span>
    
    ![Нажатие кнопки Delete (Удалить) в разделе Synthetic records (Синтетические записи)](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="302b3-162">Выберите **Delete** (Удалить).</span><span class="sxs-lookup"><span data-stu-id="302b3-162">Select **Delete**.</span></span>
    
    ![Выберите Delete (Удалить)](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="302b3-164">В разделе **Custom resource records** (Настраиваемые записи ресурсов) в полях для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="302b3-164">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="302b3-165">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="302b3-165">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="302b3-166">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="302b3-166">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="302b3-167">**Имя**</span><span class="sxs-lookup"><span data-stu-id="302b3-167">**Name**</span></span>|<span data-ttu-id="302b3-168">**Type** (Тип)</span><span class="sxs-lookup"><span data-stu-id="302b3-168">**Type**</span></span>|<span data-ttu-id="302b3-169">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="302b3-169">**TTL**</span></span>|<span data-ttu-id="302b3-170">**Data** (Данные)</span><span class="sxs-lookup"><span data-stu-id="302b3-170">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="302b3-171">MX</span><span class="sxs-lookup"><span data-stu-id="302b3-171">MX</span></span>  <br/> |<span data-ttu-id="302b3-172">1H (1 ч)</span><span class="sxs-lookup"><span data-stu-id="302b3-172">1H</span></span>  <br/> |<span data-ttu-id="302b3-173">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="302b3-173">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="302b3-174">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="302b3-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="302b3-175">The **0** is the MX priority value.</span><span class="sxs-lookup"><span data-stu-id="302b3-175">The **0** is the MX priority value.</span></span> <span data-ttu-id="302b3-176">Add it to the beginning of the MX value, separated from the remainder of the value by a space.</span><span class="sxs-lookup"><span data-stu-id="302b3-176">Add it to the beginning of the MX value, separated from the remainder of the value by a space.</span></span>  <br/> <span data-ttu-id="302b3-177">**Примечание.**  Получите свой \<*domain-key*\> из учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="302b3-177">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span>  [<span data-ttu-id="302b3-178">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="302b3-178">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="302b3-179">Дополнительные сведения о приоритете см. в статье [Что такое приоритет записей MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="302b3-179">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
    ![Введите или вставьте значения в разделе Custom resource records (Настраиваемые записи ресурсов)](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="302b3-181">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="302b3-181">Select **Add**.</span></span>
    
    ![Нажмите кнопку Add (Добавить)](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="302b3-183">Если есть другие настраиваемые записи MX, удалите их.</span><span class="sxs-lookup"><span data-stu-id="302b3-183">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="302b3-184">В строке записи MX нажмите **Edit** (Изменить).</span><span class="sxs-lookup"><span data-stu-id="302b3-184">Select **Edit** in the MX record row.</span></span> 
    
    ![В строке записи MX нажмите Edit (Изменить)](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="302b3-186">Для каждой из прочих настраиваемых записей MX выделите содержимое поля **Data** (Данные) и нажмите на клавиатуре клавишу **DELETE**, чтобы удалить его.</span><span class="sxs-lookup"><span data-stu-id="302b3-186">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="302b3-187">Повторяйте эти действия, чтобы удалить содержимое поля **Data** каждой из лишних записей MX.</span><span class="sxs-lookup"><span data-stu-id="302b3-187">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="302b3-189">Когда содержимое поля **Data** (Данные) каждой записи MX будет удалено, нажмите кнопку **Save** (Сохранить), чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="302b3-189">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![Нажмите Save (Сохранить)](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="302b3-191">Добавление пяти записей CNAME, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="302b3-191">Add the five CNAME records that are required for Microsoft</span></span>

1. <span data-ttu-id="302b3-192">Чтобы приступить к работе, перейдите на страницу [страница Google Domains] (https://domains.google.com/registrar) и выполните вход.</span><span class="sxs-lookup"><span data-stu-id="302b3-192">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="302b3-193">На странице **Domains** (Домены) в разделе **Domain** (Домен) выберите команду **Configure DNS** (Настроить DNS) для того домена, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="302b3-193">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="302b3-194">Добавьте первую запись CNAME.</span><span class="sxs-lookup"><span data-stu-id="302b3-194">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="302b3-195">В разделе **Custom resource records** (Настраиваемые записи ресурсов) в полях для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="302b3-195">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="302b3-196">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="302b3-196">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="302b3-197">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="302b3-197">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="302b3-198">**Имя**</span><span class="sxs-lookup"><span data-stu-id="302b3-198">**Name**</span></span>|<span data-ttu-id="302b3-199">**Type** (Тип)</span><span class="sxs-lookup"><span data-stu-id="302b3-199">**Type**</span></span>|<span data-ttu-id="302b3-200">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="302b3-200">**TTL**</span></span>|<span data-ttu-id="302b3-201">**Data** (Данные)</span><span class="sxs-lookup"><span data-stu-id="302b3-201">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="302b3-202">autodiscover</span><span class="sxs-lookup"><span data-stu-id="302b3-202">autodiscover</span></span>  <br/> |<span data-ttu-id="302b3-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="302b3-203">CNAME</span></span>  <br/> |<span data-ttu-id="302b3-204">1H (1 ч)</span><span class="sxs-lookup"><span data-stu-id="302b3-204">1H</span></span>  <br/> |<span data-ttu-id="302b3-205">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="302b3-205">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="302b3-206">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="302b3-206">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="302b3-207">sip</span><span class="sxs-lookup"><span data-stu-id="302b3-207">sip</span></span>  <br/> |<span data-ttu-id="302b3-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="302b3-208">CNAME</span></span>  <br/> |<span data-ttu-id="302b3-209">1H (1 ч)</span><span class="sxs-lookup"><span data-stu-id="302b3-209">1H</span></span>  <br/> |<span data-ttu-id="302b3-210">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="302b3-210">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="302b3-211">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="302b3-211">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="302b3-212">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="302b3-212">lyncdiscover</span></span>  <br/> |<span data-ttu-id="302b3-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="302b3-213">CNAME</span></span>  <br/> |<span data-ttu-id="302b3-214">1H (1 ч)</span><span class="sxs-lookup"><span data-stu-id="302b3-214">1H</span></span>  <br/> |<span data-ttu-id="302b3-215">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="302b3-215">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="302b3-216">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="302b3-216">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="302b3-217">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="302b3-217">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="302b3-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="302b3-218">CNAME</span></span>  <br/> |<span data-ttu-id="302b3-219">1H (1 ч)</span><span class="sxs-lookup"><span data-stu-id="302b3-219">1H</span></span>  <br/> |<span data-ttu-id="302b3-220">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="302b3-220">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="302b3-221">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="302b3-221">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="302b3-222">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="302b3-222">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="302b3-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="302b3-223">CNAME</span></span>  <br/> |<span data-ttu-id="302b3-224">1H (1 ч)</span><span class="sxs-lookup"><span data-stu-id="302b3-224">1H</span></span>  <br/> |<span data-ttu-id="302b3-225">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="302b3-225">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="302b3-226">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="302b3-226">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Введите или вставьте значения в разделе Custom resource records (Настраиваемые записи ресурсов)](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="302b3-228">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="302b3-228">Select **Add**.</span></span>
    
    ![Нажмите кнопку Add (Добавить)](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="302b3-230">Добавьте остальные четыре записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="302b3-230">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="302b3-231">В разделе **Custom resource records** (Настраиваемые записи ресурсов) создайте запись, используя значения из следующей строки таблицы, и снова нажмите **Add** (Добавить), чтобы завершить ввод этой записи.</span><span class="sxs-lookup"><span data-stu-id="302b3-231">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="302b3-232">Повторяйте эти действия, пока не будут созданы все требуемые записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="302b3-232">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="302b3-233">Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама</span><span class="sxs-lookup"><span data-stu-id="302b3-233">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="302b3-234">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="302b3-234">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="302b3-235">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="302b3-235">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="302b3-236">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="302b3-236">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="302b3-237">Вместо этого добавьте необходимые значения для продуктов корпорации Майкрософт в текущую запись. Таким образом, в одной записи SPF будут указаны оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="302b3-237">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="302b3-238">Нужны примеры?</span><span class="sxs-lookup"><span data-stu-id="302b3-238">Need examples?</span></span> <span data-ttu-id="302b3-239">Ознакомьтесь с этими [записями системы внешних доменных имен для продуктов корпорации Майкрософт](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="302b3-239">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span></span> <span data-ttu-id="302b3-240">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="302b3-240">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="302b3-241">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar).</span><span class="sxs-lookup"><span data-stu-id="302b3-241">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="302b3-242">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="302b3-242">You'll be prompted to sign in.</span></span> <span data-ttu-id="302b3-243">To do so:</span><span class="sxs-lookup"><span data-stu-id="302b3-243">To do so:</span></span>
    
1. <span data-ttu-id="302b3-244">Нажмите **Sign In** (Войти).</span><span class="sxs-lookup"><span data-stu-id="302b3-244">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="302b3-245">Введите данные для входа и еще раз нажмите кнопку **Sign In** (Войти).</span><span class="sxs-lookup"><span data-stu-id="302b3-245">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="302b3-246">На странице **Domains** (Домены) в разделе **Domain** (Домен) выберите команду **Configure DNS** (Настроить DNS) для того домена, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="302b3-246">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="302b3-247">В разделе **Custom resource records** (Настраиваемые записи ресурсов) в строке записи TXT нажмите кнопку **Edit** (Изменить).</span><span class="sxs-lookup"><span data-stu-id="302b3-247">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="302b3-248">Google Domains stores TXT records as a set that may contain multiple records.</span><span class="sxs-lookup"><span data-stu-id="302b3-248">Google Domains stores TXT records as a set that may contain multiple records.</span></span> <span data-ttu-id="302b3-249">When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set.</span><span class="sxs-lookup"><span data-stu-id="302b3-249">When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set.</span></span> <span data-ttu-id="302b3-250">Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span><span class="sxs-lookup"><span data-stu-id="302b3-250">Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![В строке записи TXT нажмите Edit (Изменить)](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="302b3-252">Щелкните элемент управления **(+)**.</span><span class="sxs-lookup"><span data-stu-id="302b3-252">Select the **(+)** control.</span></span> 
    
    ![Щелкните элемент управления "плюс"](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="302b3-254">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="302b3-254">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="302b3-255">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="302b3-255">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="302b3-256">**Данные**</span><span class="sxs-lookup"><span data-stu-id="302b3-256">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="302b3-257">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="302b3-257">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="302b3-258">Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.</span><span class="sxs-lookup"><span data-stu-id="302b3-258">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![Введите или вставьте значения в разделе Custom resource records (Настраиваемые записи ресурсов)](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="302b3-260">Нажмите **Save** (Сохранить).</span><span class="sxs-lookup"><span data-stu-id="302b3-260">Select **Save**.</span></span>
    
    ![Нажмите Save (Сохранить)](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="302b3-262">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="302b3-262">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="302b3-263"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="302b3-263"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="302b3-264">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar).</span><span class="sxs-lookup"><span data-stu-id="302b3-264">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="302b3-265">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="302b3-265">You'll be prompted to sign in.</span></span> <span data-ttu-id="302b3-266">To do so:</span><span class="sxs-lookup"><span data-stu-id="302b3-266">To do so:</span></span>
    
2. <span data-ttu-id="302b3-267">Нажмите **Sign In** (Войти).</span><span class="sxs-lookup"><span data-stu-id="302b3-267">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="302b3-268">Введите данные для входа и еще раз нажмите кнопку **Sign In** (Войти).</span><span class="sxs-lookup"><span data-stu-id="302b3-268">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="302b3-269">На странице **Domains** (Домены) в разделе **Domain** (Домен) выберите команду **Configure DNS** (Настроить DNS) для того домена, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="302b3-269">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="302b3-270">Добавьте первую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="302b3-270">Add the first SRV record.</span></span>
    
    <span data-ttu-id="302b3-271">В разделе **Custom resource records** (Настраиваемые записи ресурсов) в полях для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="302b3-271">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="302b3-272">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="302b3-272">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="302b3-273">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="302b3-273">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="302b3-274">**Имя**</span><span class="sxs-lookup"><span data-stu-id="302b3-274">**Name**</span></span>|<span data-ttu-id="302b3-275">**Type** (Тип)</span><span class="sxs-lookup"><span data-stu-id="302b3-275">**Type**</span></span>|<span data-ttu-id="302b3-276">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="302b3-276">**TTL**</span></span>|<span data-ttu-id="302b3-277">**Данные**</span><span class="sxs-lookup"><span data-stu-id="302b3-277">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="302b3-278">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="302b3-278">_sip._tls</span></span>|<span data-ttu-id="302b3-279">SRV</span><span class="sxs-lookup"><span data-stu-id="302b3-279">SRV</span></span>|<span data-ttu-id="302b3-280">1H (1 ч)</span><span class="sxs-lookup"><span data-stu-id="302b3-280">1H</span></span>|<span data-ttu-id="302b3-281">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="302b3-281">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="302b3-282">**Это значение ДОЛЖНО оканчиваться точкой (.).** **Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.</span><span class="sxs-lookup"><span data-stu-id="302b3-282">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="302b3-283">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="302b3-283">_sipfederationtls._tcp</span></span>|<span data-ttu-id="302b3-284">SRV</span><span class="sxs-lookup"><span data-stu-id="302b3-284">SRV</span></span>|<span data-ttu-id="302b3-285">1H (1 ч)</span><span class="sxs-lookup"><span data-stu-id="302b3-285">1H</span></span>|<span data-ttu-id="302b3-286">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="302b3-286">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="302b3-287">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="302b3-287">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="302b3-288">Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.</span><span class="sxs-lookup"><span data-stu-id="302b3-288">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![Введите или вставьте значения в разделе Custom resource records (Настраиваемые записи ресурсов)](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="302b3-290">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="302b3-290">Select **Add**.</span></span>
    
    ![Нажмите кнопку Add (Добавить)](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="302b3-292">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="302b3-292">Add the other SRV record.</span></span>
    
    <span data-ttu-id="302b3-293">В разделе **Custom resource records** (Настраиваемые записи ресурсов) создайте запись, используя значения из второй строки таблицы, и снова нажмите **Add** (Добавить), чтобы завершить ввод этой записи.</span><span class="sxs-lookup"><span data-stu-id="302b3-293">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="302b3-294">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="302b3-294">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="302b3-295">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="302b3-295">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="302b3-296">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="302b3-296">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
