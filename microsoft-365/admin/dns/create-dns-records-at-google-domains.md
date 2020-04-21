---
title: Создание записей DNS в доменах Google для Майкрософт
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Lync и других служб в доменах Google для Майкрософт.
ms.openlocfilehash: 20a3ba9baefcdb26936d2d0a5fda7ed1b5db971e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629543"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a><span data-ttu-id="18532-103">Создание записей DNS в доменах Google для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="18532-103">Create DNS records at Google Domains for Microsoft</span></span>

 <span data-ttu-id="18532-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="18532-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="18532-105">Если ваш поставщик услуг размещения DNS  Google Domains, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Lync и других служб.</span><span class="sxs-lookup"><span data-stu-id="18532-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="18532-106">Когда вы добавите эти записи в домены Google, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="18532-106">After you add these records at Google Domains, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="18532-107">Чтобы узнать о размещении и DNS для веб-сайтов с помощью Microsoft, ознакомьтесь со статьей [использование общедоступного веб-сайта с корпорацией Майкрософт](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="18532-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="18532-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="18532-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="18532-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="18532-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="18532-110">Если при добавлении записей DNS возникают проблемы с почтовыми сообщениями или другими проблемами, ознакомьтесь со статьей [Поиск и устранение проблем после добавления домена или записей DNS в корпорацию Майкрософт](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="18532-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="18532-111">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="18532-111">Add a TXT record for verification</span></span>
<span data-ttu-id="18532-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="18532-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="18532-113">Перед использованием домена с корпорацией Майкрософт необходимо убедиться, что вы являетесь его владельцем.</span><span class="sxs-lookup"><span data-stu-id="18532-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="18532-114">Вы можете войти в свою учетную запись у вас в вашем регистраторе доменных имен и создать запись DNS в Майкрософт, если вы владеете этим доменом.</span><span class="sxs-lookup"><span data-stu-id="18532-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="18532-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="18532-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="18532-p104">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Google Domains по [этой ссылке](https://domains.google.com/registrar). Сначала вам потребуется войти. Вот как это сделать.</span><span class="sxs-lookup"><span data-stu-id="18532-p104">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="18532-120">Нажмите кнопку **войти**.</span><span class="sxs-lookup"><span data-stu-id="18532-120">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="18532-121">Введите свои учетные данные для входа, а затем снова нажмите кнопку **войти**.</span><span class="sxs-lookup"><span data-stu-id="18532-121">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="18532-122">На странице **My Domains (мои домены** ) найдите домен, который вы хотите использовать в Майкрософт, и щелкните ссылку **Управление** рядом с ней.</span><span class="sxs-lookup"><span data-stu-id="18532-122">On the **My domains** page, find the domain you want to use with Microsoft, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="18532-123">В области навигации слева выберите пункт **DNS**.</span><span class="sxs-lookup"><span data-stu-id="18532-123">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="18532-124">В поля для новой записи в разделе \* \* Настраиваемые записи ресурсов \* \* введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="18532-124">In the \*\* Custom resource records \*\* section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="18532-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="18532-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="18532-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="18532-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="18532-127">**Имя**</span><span class="sxs-lookup"><span data-stu-id="18532-127">**Name**</span></span> <br/> |<span data-ttu-id="18532-128">**Тип**</span><span class="sxs-lookup"><span data-stu-id="18532-128">**Type**</span></span> <br/> |<span data-ttu-id="18532-129">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="18532-129">**TTL**</span></span> <br/> |<span data-ttu-id="18532-130">**Data (Данные)**</span><span class="sxs-lookup"><span data-stu-id="18532-130">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="18532-131">TXT</span><span class="sxs-lookup"><span data-stu-id="18532-131">TXT</span></span>  <br/> |<span data-ttu-id="18532-132">1H</span><span class="sxs-lookup"><span data-stu-id="18532-132">1H</span></span>  <br/> |<span data-ttu-id="18532-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="18532-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="18532-134">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="18532-134">**Note:** This is an example.</span></span> <span data-ttu-id="18532-135">Используйте указанную здесь **конечную точку или значение адреса** из таблицы.</span><span class="sxs-lookup"><span data-stu-id="18532-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="18532-136">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="18532-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="18532-137">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="18532-137">Select **Add**.</span></span>
    
5. <span data-ttu-id="18532-138">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="18532-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="18532-139">Теперь, когда вы добавили запись на сайте регистратора доменных имен, вернитесь в корпорацию Майкрософт и запросите запись.</span><span class="sxs-lookup"><span data-stu-id="18532-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="18532-140">После того как корпорация Майкрософт обнаружит правильную запись TXT, ваш домен будет проверен.</span><span class="sxs-lookup"><span data-stu-id="18532-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="18532-141">В центре администрирования Майкрософт перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> **параметров** \> ".</span><span class="sxs-lookup"><span data-stu-id="18532-141">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="18532-142">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="18532-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="18532-143">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="18532-143">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="18532-144">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="18532-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="18532-145">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="18532-145">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="18532-146">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="18532-146">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="18532-147">Если у вас возникли проблемы с процессом обработки почты или другими проблемами после добавления записей DNS, ознакомьтесь с разрешениями [и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="18532-147">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="18532-148">Добавление записи MX для отправки электронной почты для вашего домена в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="18532-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="18532-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="18532-149"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="18532-p108">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Google Domains по [этой ссылке](https://domains.google.com/registrar). Сначала вам потребуется войти. Вот как это сделать.</span><span class="sxs-lookup"><span data-stu-id="18532-p108">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="18532-153">Нажмите кнопку **войти**.</span><span class="sxs-lookup"><span data-stu-id="18532-153">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="18532-154">Введите свои учетные данные для входа, а затем снова нажмите кнопку **войти**.</span><span class="sxs-lookup"><span data-stu-id="18532-154">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="18532-155">На странице **домены** в разделе **домен** выберите **Настройка DNS** для домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="18532-155">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="18532-156">Если вы используете учетную запись электронной почты G Suite, сначала необходимо удалить записи MX, которые с ней связаны.</span><span class="sxs-lookup"><span data-stu-id="18532-156">If you have a G Suite email account, you must first delete the MX records associated with that account.</span></span> <span data-ttu-id="18532-157">Записи MX набора MX не позволяют добавлять какие-либо другие записи MX, в том числе те, которые необходимы корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="18532-157">The G Suite MX records prevent you from adding any other MX records, including those required for Microsoft.</span></span> <span data-ttu-id="18532-158">Обратите внимание, что при удалении записей для G Suite учетная запись G Suite не удаляется.</span><span class="sxs-lookup"><span data-stu-id="18532-158">Note that deleting the G Suite records does not delete your G Suite account.</span></span> <span data-ttu-id="18532-159">Чтобы удалить записи MX для G Suite, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="18532-159">To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="18532-160">В разделе **искусственные записи** в области **G Suite** нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="18532-160">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="18532-161">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="18532-161">(You may have to scroll down.)</span></span>
    
    ![Выберите команду Удалить в разделе искусственные записи](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="18532-163">Выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="18532-163">Select **Delete**.</span></span>
    
    ![Нажмите кнопку Удалить](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="18532-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="18532-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="18532-166">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="18532-166">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="18532-167">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="18532-167">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="18532-168">**Имя**</span><span class="sxs-lookup"><span data-stu-id="18532-168">**Name**</span></span>|<span data-ttu-id="18532-169">**Тип**</span><span class="sxs-lookup"><span data-stu-id="18532-169">**Type**</span></span>|<span data-ttu-id="18532-170">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="18532-170">**TTL**</span></span>|<span data-ttu-id="18532-171">**Data (Данные)**</span><span class="sxs-lookup"><span data-stu-id="18532-171">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="18532-172">MX</span><span class="sxs-lookup"><span data-stu-id="18532-172">MX</span></span>  <br/> |<span data-ttu-id="18532-173">1H</span><span class="sxs-lookup"><span data-stu-id="18532-173">1H</span></span>  <br/> |<span data-ttu-id="18532-174">0  *\<ключ_домена\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="18532-174">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="18532-175">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="18532-175">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="18532-p110">**0**  значение приоритета MX. Добавьте его в начало значения MX, отделив от остальной части пробелом.  </span><span class="sxs-lookup"><span data-stu-id="18532-p110">The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="18532-178">**Примечание:** \<Получите *ключ* \> домена из учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="18532-178">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span>  [<span data-ttu-id="18532-179">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="18532-179">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="18532-180">Дополнительные сведения о приоритете см. в статье [Что такое приоритет записей MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="18532-180">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![Введите или вставьте значения в разделе "настраиваемые записи ресурсов"](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="18532-182">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="18532-182">Select **Add**.</span></span>
    
    ![Нажмите кнопку Добавить](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="18532-184">Если есть другие настраиваемые записи MX, удалите их.</span><span class="sxs-lookup"><span data-stu-id="18532-184">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="18532-185">Выберите команду **изменить** в строке записи MX.</span><span class="sxs-lookup"><span data-stu-id="18532-185">Select **Edit** in the MX record row.</span></span> 
    
    ![Выберите команду изменить в строке записи MX.](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="18532-187">Для каждой из остальных настраиваемых записей MX выберите запись в поле **данные** , а затем нажмите клавишу **Delete** на клавиатуре, чтобы удалить эту запись.</span><span class="sxs-lookup"><span data-stu-id="18532-187">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="18532-188">Повторяйте эти действия, чтобы удалить содержимое поля **Data** каждой из лишних записей MX.</span><span class="sxs-lookup"><span data-stu-id="18532-188">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="18532-190">После удаления записи **данных** для каждой из остальных записей MX нажмите кнопку **сохранить** , чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="18532-190">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![Нажмите кнопку Сохранить](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="18532-192">Добавление пяти записей CNAME, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="18532-192">Add the five CNAME records that are required for Microsoft</span></span>

1. <span data-ttu-id="18532-193">Чтобы приступить к работе, перейдите на страницу [домены Googlehttps://domains.google.com/registrar) ] (и войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="18532-193">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="18532-194">На странице **домены** в разделе **домен** выберите **Настройка DNS** для домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="18532-194">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="18532-195">Добавьте первую запись CNAME.</span><span class="sxs-lookup"><span data-stu-id="18532-195">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="18532-196">В разделе **Custom resource records** (Настраиваемые записи ресурсов) в полях для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="18532-196">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="18532-197">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="18532-197">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="18532-198">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="18532-198">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="18532-199">**Имя**</span><span class="sxs-lookup"><span data-stu-id="18532-199">**Name**</span></span>|<span data-ttu-id="18532-200">**Тип**</span><span class="sxs-lookup"><span data-stu-id="18532-200">**Type**</span></span>|<span data-ttu-id="18532-201">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="18532-201">**TTL**</span></span>|<span data-ttu-id="18532-202">**Data (Данные)**</span><span class="sxs-lookup"><span data-stu-id="18532-202">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="18532-203">autodiscover</span><span class="sxs-lookup"><span data-stu-id="18532-203">autodiscover</span></span>  <br/> |<span data-ttu-id="18532-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="18532-204">CNAME</span></span>  <br/> |<span data-ttu-id="18532-205">1H</span><span class="sxs-lookup"><span data-stu-id="18532-205">1H</span></span>  <br/> |<span data-ttu-id="18532-206">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="18532-206">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="18532-207">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="18532-207">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="18532-208">sip</span><span class="sxs-lookup"><span data-stu-id="18532-208">sip</span></span>  <br/> |<span data-ttu-id="18532-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="18532-209">CNAME</span></span>  <br/> |<span data-ttu-id="18532-210">1H</span><span class="sxs-lookup"><span data-stu-id="18532-210">1H</span></span>  <br/> |<span data-ttu-id="18532-211">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="18532-211">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="18532-212">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="18532-212">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="18532-213">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="18532-213">lyncdiscover</span></span>  <br/> |<span data-ttu-id="18532-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="18532-214">CNAME</span></span>  <br/> |<span data-ttu-id="18532-215">1H</span><span class="sxs-lookup"><span data-stu-id="18532-215">1H</span></span>  <br/> |<span data-ttu-id="18532-216">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="18532-216">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="18532-217">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="18532-217">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="18532-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="18532-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="18532-219">CNAME</span><span class="sxs-lookup"><span data-stu-id="18532-219">CNAME</span></span>  <br/> |<span data-ttu-id="18532-220">1H</span><span class="sxs-lookup"><span data-stu-id="18532-220">1H</span></span>  <br/> |<span data-ttu-id="18532-221">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="18532-221">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="18532-222">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="18532-222">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="18532-223">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="18532-223">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="18532-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="18532-224">CNAME</span></span>  <br/> |<span data-ttu-id="18532-225">1H</span><span class="sxs-lookup"><span data-stu-id="18532-225">1H</span></span>  <br/> |<span data-ttu-id="18532-226">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="18532-226">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="18532-227">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="18532-227">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Введите или вставьте значения в разделе "настраиваемые записи ресурсов"](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="18532-229">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="18532-229">Select **Add**.</span></span>
    
    ![Нажмите кнопку Добавить](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="18532-231">Добавьте остальные четыре записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="18532-231">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="18532-232">В разделе **Настраиваемые записи ресурсов** создайте запись, используя значения из следующей строки таблицы, а затем снова нажмите кнопку **Добавить** , чтобы завершить эту запись.</span><span class="sxs-lookup"><span data-stu-id="18532-232">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="18532-233">Повторяйте эту процедуру, пока не будут созданы все необходимые записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="18532-233">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="18532-234">Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама</span><span class="sxs-lookup"><span data-stu-id="18532-234">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18532-235">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="18532-235">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="18532-236">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="18532-236">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="18532-237">Если у вас уже есть запись SPF для вашего домена, не создавайте ее для Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="18532-237">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="18532-238">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь одну запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="18532-238">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="18532-239">Нужны примеры?</span><span class="sxs-lookup"><span data-stu-id="18532-239">Need examples?</span></span> <span data-ttu-id="18532-240">Ознакомьтесь с этими [записями о внешних доменных именах для Майкрософт](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="18532-240">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="18532-241">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="18532-241">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="18532-p113">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Google Domains по [этой ссылке](https://domains.google.com/registrar). Сначала вам потребуется войти. Вот как это сделать.</span><span class="sxs-lookup"><span data-stu-id="18532-p113">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="18532-245">Нажмите кнопку **войти**.</span><span class="sxs-lookup"><span data-stu-id="18532-245">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="18532-246">Введите свои учетные данные для входа, а затем снова нажмите кнопку **войти**.</span><span class="sxs-lookup"><span data-stu-id="18532-246">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="18532-247">На странице **домены** в разделе **домен** выберите **Настройка DNS** для домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="18532-247">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="18532-248">В разделе " **Настраиваемые записи ресурсов** " в строке запись TXT нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="18532-248">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="18532-p114">Google Domains хранит записи TXT в виде наборов, которые могут содержать сразу несколько записей. Если у вас есть хотя бы еще одна запись TXT, с помощью которой вы подтверждали домен, вам нужно добавлять новые записи TXT к ней. Попытка ввести дополнительные записи TXT отдельно приведет к ошибке **Duplicate record** (Повторяющаяся запись).</span><span class="sxs-lookup"><span data-stu-id="18532-p114">Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![Выберите команду изменить в строке записи TXT](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="18532-253">Выберите элемент управления **(+)** .</span><span class="sxs-lookup"><span data-stu-id="18532-253">Select the **(+)** control.</span></span> 
    
    ![Выбор элемента управления "плюс"](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="18532-255">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="18532-255">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="18532-256">(Возможно, потребуется прокрутить страницу вниз.)</span><span class="sxs-lookup"><span data-stu-id="18532-256">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="18532-257">**Data (Данные)**</span><span class="sxs-lookup"><span data-stu-id="18532-257">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="18532-258">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="18532-258">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="18532-259">Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.</span><span class="sxs-lookup"><span data-stu-id="18532-259">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![Введите или вставьте значения в разделе "настраиваемые записи ресурсов"](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="18532-261">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="18532-261">Select **Save**.</span></span>
    
    ![Нажмите кнопку Сохранить](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="18532-263">Добавление двух записей SRV, необходимых для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="18532-263">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="18532-264"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="18532-264"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="18532-p115">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Google Domains по [этой ссылке](https://domains.google.com/registrar). Сначала вам потребуется войти. Вот как это сделать.</span><span class="sxs-lookup"><span data-stu-id="18532-p115">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="18532-268">Нажмите кнопку **войти**.</span><span class="sxs-lookup"><span data-stu-id="18532-268">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="18532-269">Введите свои учетные данные для входа, а затем снова нажмите кнопку **войти**.</span><span class="sxs-lookup"><span data-stu-id="18532-269">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="18532-270">На странице **домены** в разделе **домен** выберите **Настройка DNS** для домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="18532-270">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="18532-271">Добавьте первую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="18532-271">Add the first SRV record.</span></span>
    
    <span data-ttu-id="18532-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="18532-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="18532-273">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="18532-273">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="18532-274">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="18532-274">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="18532-275">**Имя**</span><span class="sxs-lookup"><span data-stu-id="18532-275">**Name**</span></span>|<span data-ttu-id="18532-276">**Тип**</span><span class="sxs-lookup"><span data-stu-id="18532-276">**Type**</span></span>|<span data-ttu-id="18532-277">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="18532-277">**TTL**</span></span>|<span data-ttu-id="18532-278">**Data (Данные)**</span><span class="sxs-lookup"><span data-stu-id="18532-278">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="18532-279">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="18532-279">_sip._tls</span></span>|<span data-ttu-id="18532-280">SRV</span><span class="sxs-lookup"><span data-stu-id="18532-280">SRV</span></span>|<span data-ttu-id="18532-281">1H</span><span class="sxs-lookup"><span data-stu-id="18532-281">1H</span></span>|<span data-ttu-id="18532-282">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="18532-282">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="18532-283">**Это значение должно заканчиваться точкой (.)** . **Примечание:** Мы рекомендуем копировать и вставлять эту запись, чтобы все интервалы оставались правильными.</span><span class="sxs-lookup"><span data-stu-id="18532-283">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="18532-284">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="18532-284">_sipfederationtls._tcp</span></span>|<span data-ttu-id="18532-285">SRV</span><span class="sxs-lookup"><span data-stu-id="18532-285">SRV</span></span>|<span data-ttu-id="18532-286">1H</span><span class="sxs-lookup"><span data-stu-id="18532-286">1H</span></span>|<span data-ttu-id="18532-287">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="18532-287">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="18532-288">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="18532-288">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="18532-289">Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.</span><span class="sxs-lookup"><span data-stu-id="18532-289">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![Введите или вставьте значения в разделе "настраиваемые записи ресурсов"](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="18532-291">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="18532-291">Select **Add**.</span></span>
    
    ![Нажмите кнопку Добавить](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="18532-293">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="18532-293">Add the other SRV record.</span></span>
    
    <span data-ttu-id="18532-294">В разделе **Настраиваемые записи ресурсов** создайте запись, используя значения из второй строки таблицы, а затем еще раз нажмите кнопку **Добавить** , чтобы завершить эту запись.</span><span class="sxs-lookup"><span data-stu-id="18532-294">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="18532-295">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="18532-295">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="18532-296">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="18532-296">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="18532-297">Если у вас возникли проблемы с процессом обработки почты или другими проблемами после добавления записей DNS, ознакомьтесь с разрешениями [и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="18532-297">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
